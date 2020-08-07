---
title: Implementar el operador OR en procedimientos almacenados compilados de forma nativa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f2528e74-2b1c-48cb-861b-c4e57b51ac35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ed762e062cbc6831eb46784ef71fc7889850676
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747183"
---
# <a name="implementing-the-or-operator-in-natively-compiled-stored-procedures"></a><span data-ttu-id="bbeb9-102">Implementar el operador OR en procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="bbeb9-102">Implementing the OR Operator in Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="bbeb9-103">No se admiten operadores OR en predicados de consulta en procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-103">OR operators are not supported in query predicates in natively compiled stored procedures.</span></span> <span data-ttu-id="bbeb9-104">Puesto que tampoco se admiten operadores NOT en los predicados de consulta en los procedimientos almacenados compilados de forma nativa, los efectos de los operadores OR no se pueden simular mediante el uso de operadores lógicos equivalentes solamente.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-104">Because NOT operators are also not supported in query predicates in natively compiled stored procedures, the effects of OR operators cannot be simulated through the use of equivalent logical operators alone.</span></span> <span data-ttu-id="bbeb9-105">Sin embargo, los efectos de un operador OR se pueden simular con variables de tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-105">However, the effects of an OR operator may be simulated with memory-optimized table variables.</span></span>  
  
## <a name="or-operator-in-where-clause"></a><span data-ttu-id="bbeb9-106">Operador OR en una cláusula WHERE</span><span class="sxs-lookup"><span data-stu-id="bbeb9-106">OR Operator in WHERE Clause</span></span>  
 <span data-ttu-id="bbeb9-107">Si tiene un operador OR en una cláusula WHERE, puede usar el método siguiente para simular su comportamiento:</span><span class="sxs-lookup"><span data-stu-id="bbeb9-107">If you have an OR operator in a WHERE clause, you can use the following approach to simulate its behavior:</span></span>  
  
1.  <span data-ttu-id="bbeb9-108">Cree una variable de tabla optimizada para memoria con el esquema correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-108">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="bbeb9-109">Para ello se necesita un tipo de tabla optimizada para memoria predefinido.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-109">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="bbeb9-110">Empezando por el operador OR de nivel superior, separe la cláusula WHERE en dos partes según los predicados combinados mediante el operador OR.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-110">Starting with the top level OR operator, separate the WHERE clause into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="bbeb9-111">Si tiene más de un operador OR en una cláusula WHERE, puede ser necesario hacerlo más de una vez.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-111">If you have more than one OR operator in a WHERE clause, you may need to do this more than once.</span></span> <span data-ttu-id="bbeb9-112">Repita este paso hasta que no queden operadores OR.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-112">Repeat this step until no OR operators remain.</span></span> <span data-ttu-id="bbeb9-113">Por ejemplo, si tiene el predicado siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbeb9-113">For example, if you have the following predicate:</span></span>  
  
    ```  
    pred1 OR (pred2 AND (pred3 OR pred4)) OR (pred5 AND pred6)  
    ```  
  
     <span data-ttu-id="bbeb9-114">Después de este paso, debe tener los predicados siguientes:</span><span class="sxs-lookup"><span data-stu-id="bbeb9-114">After this step, you should have the following predicates:</span></span>  
  
    ```  
    pred1  
    pred5 AND pred6  
    pred2 AND pred3  
    pred2 AND pred4  
    ```  
  
3.  <span data-ttu-id="bbeb9-115">Ejecute una consulta con cada una de las dos partes del paso 2 como predicado.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-115">Execute a query with each of the two parts found in Step 2 as the predicate.</span></span> <span data-ttu-id="bbeb9-116">Inserte el resultado de cada consulta en la variable de tabla optimizada para memoria creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-116">Insert the result for each query into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="bbeb9-117">Si es necesario, quite los duplicados de la variable de tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-117">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="bbeb9-118">Use el contenido de la variable de tabla optimizada para memoria como el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-118">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="bbeb9-119">En el ejemplo siguiente se usan tablas de la base de datos AdventureWorks2012 que se actualizaron para [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbeb9-119">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="bbeb9-120">Para descargar los archivos de este ejemplo, vaya a [bases de datos de AdventureWorks: 2012, 2008R2 y 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="bbeb9-120">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="bbeb9-121">Para aplicar el [!INCLUDE[hek_2](../includes/hek-2-md.md)] ejemplo de código a AdventureWorks2012, vaya a [SQL Server 2014 en el ejemplo de OLTP en memoria](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="bbeb9-121">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="bbeb9-122">Agregue el procedimiento almacenado siguiente a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-122">Add the following stored procedure to the database.</span></span> <span data-ttu-id="bbeb9-123">Convertiremos este procedimiento almacenado para que use compilación nativa.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-123">We will convert this stored procedure to use native compilation.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_ondisk  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
AS BEGIN  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  WHERE  s.SalesOrderId = @SalesOrderId  
      OR s.SalesOrderDetailId = @SalesOrderDetailId  
      OR s.CarrierTrackingNumber = @CarrierTrackingNumber  
      OR s.ProductID = @ProductId  
      OR (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
END  
GO  
```  
  
 <span data-ttu-id="bbeb9-124">Después de la conversión, el esquema de tabla y de procedimiento almacenado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbeb9-124">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesOrderDetailType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesOrderDetailTempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  recordcount int not null  
  INDEX ix_fuzzySearchSalesOrderDetailTempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesOrderDetail_inmem  
  @SalesOrderId int = 0, @SalesOrderDetailId int = 0,   
  @CarrierTrackingNumber nvarchar(25) = N'', @ProductId int = 0,   
  @minUnitPrice money = 0, @maxUnitPrice money = 0  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.fuzzySearchSalesOrderDetailType  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderId = @SalesOrderId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.SalesOrderDetailId = @SalesOrderDetailId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.CarrierTrackingNumber COLLATE Latin1_General_BIN2 = @CarrierTrackingNumber COLLATE Latin1_General_BIN2   
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE s.ProductID = @ProductId  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, ModifiedDate)  
  SELECT SalesOrderId, SalesOrderDetailId, ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  WHERE (s.UnitPrice > @minUnitPrice AND s.UnitPrice < @maxUnitPrice)  
  
  -- After the above statements, there will be duplicates inside @retValue  
  -- Delete the duplicates from @retValue  
  DECLARE @duplicates Sales.fuzzySearchSalesOrderDetailTempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, recordcount)   
  SELECT SalesOrderId, SalesOrderDetailId, COUNT(*) AS recordCount  
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId  
  
  -- Now we have one row per pair  
  -- clear and rebuild the result set  
  DELETE FROM @retValue  
  
  INSERT INTO @retValue  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates d ON s.SalesOrderId = d.SalesOrderId AND s.SalesOrderDetailId = d.SalesOrderDetailId  
  
  -- After this every pair of (SalesOrderId, SalesOrderDetailId) in @retValue should be unique.  
  SELECT SalesorderId, SalesOrderDetailId, ModifiedDate FROM @retValue  
END  
GO  
```  
  
## <a name="or-operator-in-join-condition"></a><span data-ttu-id="bbeb9-125">Operador OR en una condición JOIN</span><span class="sxs-lookup"><span data-stu-id="bbeb9-125">OR Operator in JOIN Condition</span></span>  
 <span data-ttu-id="bbeb9-126">Si tiene un operador OR en una condición JOIN de una instrucción SELECT, puede usar el método siguiente para simular su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-126">If you have an OR operator in a JOIN condition of a SELECT statement, you may use the following approach to simulate its behavior.</span></span> <span data-ttu-id="bbeb9-127">Si tiene más de un operador OR en una condición JOIN o tiene varias condiciones JOIN con operadores OR, puede ser necesario hacerlo más de una vez.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-127">If you have more than one OR operator in a JOIN condition or you have multiple JOIN condition with OR operators, you may need to do this more than once.</span></span>  
  
 <span data-ttu-id="bbeb9-128">Si tiene condiciones OUTER JOIN, puede combinar esta solución alternativa con la solución para las condiciones OUTER JOIN.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-128">If you have OUTER JOIN conditions, you may combine this workaround with the workaround for OUTER JOIN conditions.</span></span>  
  
1.  <span data-ttu-id="bbeb9-129">Cree una variable de tabla optimizada para memoria con el esquema correspondiente.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-129">Create a memory-optimized table variable with the appropriate schema.</span></span> <span data-ttu-id="bbeb9-130">Para ello se necesita un tipo de tabla optimizada para memoria predefinido.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-130">This requires a predefined memory-optimized table type.</span></span>  
  
2.  <span data-ttu-id="bbeb9-131">Separe el predicado de la condición JOIN en dos partes según los predicados combinados mediante el operador OR.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-131">Separate the predicate in the JOIN condition into two parts according to the predicates joined by the OR operator.</span></span> <span data-ttu-id="bbeb9-132">Si tiene varias condiciones JOIN, puede que necesite hacerlo para cada condición JOIN y crear después un conjunto de combinaciones de los fragmentos resultantes.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-132">If you have multiple JOIN conditions, you may need to do this for each JOIN condition and then create a set of combinations of the resulting fragments.</span></span> <span data-ttu-id="bbeb9-133">Por ejemplo, si tiene tres condiciones JOIN con un operador OR en cada condición JOIN, puede tener 2x2x2=8 predicados.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-133">For example, if you have three JOIN conditions with one OR operator in each JOIN condition, you may have 2x2x2=8 predicates.</span></span>  
  
3.  <span data-ttu-id="bbeb9-134">Para cada predicado generado por el paso 2, cree una consulta que inserte su resultado en la variable de tabla optimizada para memoria creada en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-134">For each predicate produced by Step 2, create a query that will insert its result into the memory-optimized table variable created in Step 1.</span></span>  
  
4.  <span data-ttu-id="bbeb9-135">Si es necesario, quite los duplicados de la variable de tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-135">If necessary, remove duplicates from the memory-optimized table variable.</span></span>  
  
5.  <span data-ttu-id="bbeb9-136">Use el contenido de la variable de tabla optimizada para memoria como el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-136">Use the content of the memory-optimized table variable as the result from the query.</span></span>  
  
 <span data-ttu-id="bbeb9-137">En el ejemplo siguiente se usan tablas de la base de datos AdventureWorks2012 que se actualizaron para [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bbeb9-137">The following sample uses tables from the AdventureWorks2012 database that were updated for [!INCLUDE[hek_2](../includes/hek-2-md.md)].</span></span> <span data-ttu-id="bbeb9-138">Para descargar los archivos de este ejemplo, vaya a [bases de datos de AdventureWorks: 2012, 2008R2 y 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span><span class="sxs-lookup"><span data-stu-id="bbeb9-138">To download the files for this sample, goto [AdventureWorks Databases - 2012, 2008R2 and 2008](https://msftdbprodsamples.codeplex.com/releases/view/93587).</span></span> <span data-ttu-id="bbeb9-139">Para aplicar el [!INCLUDE[hek_2](../includes/hek-2-md.md)] ejemplo de código a AdventureWorks2012, vaya a [SQL Server 2014 en el ejemplo de OLTP en memoria](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span><span class="sxs-lookup"><span data-stu-id="bbeb9-139">To apply [!INCLUDE[hek_2](../includes/hek-2-md.md)] code sample to AdventureWorks2012, go to [SQL Server 2014 In-Memory OLTP Sample](https://msftdbprodsamples.codeplex.com/releases/view/114491).</span></span>  
  
 <span data-ttu-id="bbeb9-140">Agregue el procedimiento almacenado siguiente a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-140">Add the following stored procedure to the database.</span></span> <span data-ttu-id="bbeb9-141">Convertiremos este procedimiento almacenado para que use compilación nativa.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-141">We will convert this stored procedure to use native compilation.</span></span> <span data-ttu-id="bbeb9-142">En este ejemplo se usan condiciones INNER JOIN.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-142">This sample uses INNER JOIN conditions.</span></span>  
  
```  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_ondisk  
  @SpecialOfferId int  
AS BEGIN  
  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_ondisk s  
  JOIN Sales.SpecialOffer_onDisk offer   
    ON s.SpecialOfferID = offer.SpecialOfferID   
    OR s.ProductID IN (SELECT ProductId FROM Sales.SpecialOfferProduct sop WHERE sop.SpecialOfferID = @SpecialOfferId)  
END  
```  
  
 <span data-ttu-id="bbeb9-143">Después de la conversión, el esquema de tabla y de procedimiento almacenado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbeb9-143">After conversion, the table and stored procedure schema is as follows,</span></span>  
  
```  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_Type AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  ModifiedDate datetime2(7) not null  
  INDEX ix_fuzzySearchSalesSpecialOffers_Type NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE TYPE Sales.fuzzySearchSalesSpecialOffers_TempType AS TABLE  
(  
  SalesOrderId int not null,  
  SalesOrderDetailId int not null,  
  SpecialOfferId int not null,  
  recordcount int null  
  INDEX ix_fuzzySearchSalesSpecialOffers_TempType NONCLUSTERED (SalesOrderId, SalesOrderDetailId)  
) WITH (MEMORY_OPTIMIZED = ON)  
GO  
  
CREATE PROCEDURE Sales.usp_fuzzySearchSalesSpecialOffers_inmem  
  @SpecialOfferId int  
WITH NATIVE_COMPILATION, SCHEMABINDING, EXECUTE AS OWNER  
AS BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE = N'ENGLISH')  
  
  DECLARE @retValue Sales.FuzzySearchSalesSpecialOffers_Type  
  
  -- Find all special offers matching the conditions  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOffer_inmem offer   
    ON s.SpecialOfferID = offer.SpecialOfferID  
  
  INSERT INTO @retValue (SalesOrderId, SalesOrderDetailId, SpecialOfferid, ModifiedDate)  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN Sales.SpecialOfferProduct_inmem sop   
    ON sop.SpecialOfferId = @SpecialOfferId AND s.ProductID = sop.ProductId  
  
  -- Now we need to remove the duplicates from @matchingSpecialOffers  
  DECLARE @duplicates Sales.fuzzySearchSalesSpecialOffers_TempType  
  
  INSERT INTO @duplicates (SalesOrderId, SalesOrderDetailId, SpecialOfferid, recordcount)  
  SELECT SalesOrderId, SalesOrderDetailId, SpecialOfferId, COUNT(*)   
  FROM @retValue  
  GROUP BY SalesOrderId, SalesOrderDetailId, SpecialOfferId  
  
  -- now there should be no duplicates within @duplicate  
  -- use @duplicate for join.  
  SELECT s.SalesOrderId, s.SalesOrderDetailId, s.SpecialOfferID, s.ModifiedDate  
  FROM Sales.SalesOrderDetail_inmem s  
  JOIN @duplicates offer   
    ON    s.SalesOrderId = offer.SalesOrderId   
      AND s.SalesOrderDetailId = offer.SalesOrderDetailID   
      AND s.SpecialOfferId = offer.SpecialOfferId  
END  
GO  
```  
  
## <a name="side-effects"></a><span data-ttu-id="bbeb9-144">Efectos secundarios</span><span class="sxs-lookup"><span data-stu-id="bbeb9-144">Side Effects</span></span>  
 <span data-ttu-id="bbeb9-145">Si tiene más de un operador OR en la cláusula WHERE o la condición JOIN, el número de consultas que necesita ejecutar para simular el comportamiento puede aumentar exponencialmente.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-145">If you have more than one OR operator in the WHERE clause or JOIN condition, the number of queries you need to execute to simulate the behavior may increase exponentially.</span></span> <span data-ttu-id="bbeb9-146">Esto puede ralentizar el rendimiento de las consultas y aumentar la utilización de memoria debido a la necesidad de usar variables de tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="bbeb9-146">This may slow down query performance and may increase memory usage due to the need to use memory-optimized table variables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbeb9-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bbeb9-147">See Also</span></span>  
 [<span data-ttu-id="bbeb9-148">Problemas de migración para los procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="bbeb9-148">Migration Issues for Natively Compiled Stored Procedures</span></span>](../relational-databases/in-memory-oltp/migration-issues-for-natively-compiled-stored-procedures.md)  
  
