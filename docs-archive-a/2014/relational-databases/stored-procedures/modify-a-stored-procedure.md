---
title: Modificación de un procedimiento almacenado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying stored procedures
- editing stored procedures
- stored procedures [SQL Server], modifying
ms.assetid: 13396239-6100-48ce-aa34-461358d99c92
author: stevestein
ms.author: sstein
ms.openlocfilehash: 906f0e06650da505094d18774ce86dab53d53f38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744021"
---
# <a name="modify-a-stored-procedure"></a><span data-ttu-id="93273-102">Modificar un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="93273-102">Modify a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-modify-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="93273-103">En este tema se describe cómo modificar un procedimiento almacenado [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93273-103">This topic describes how to modify a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="93273-104">**Antes de empezar:**  [Limitaciones y restricciones](#Restrictions), [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="93273-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="93273-105">**Para modificar un procedimiento con:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="93273-105">**To alter a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="93273-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="93273-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="93273-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="93273-107">Limitations and Restrictions</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="93273-108">no se pueden modificar para que sean procedimientos almacenados CLR y viceversa.</span><span class="sxs-lookup"><span data-stu-id="93273-108">stored procedures cannot be modified to be CLR stored procedures and vice versa.</span></span>  
  
 <span data-ttu-id="93273-109">Si anteriormente se creó la definición de procedimiento mediante WITH ENCRYPTION o WITH RECOMPILE, estas opciones solo se habilitan si se incluyen en la instrucción ALTER PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="93273-109">If the previous procedure definition was created using WITH ENCRYPTION or WITH RECOMPILE, these options are enabled only if they are included in the ALTER PROCEDURE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="93273-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="93273-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="93273-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="93273-111">Permissions</span></span>  
 <span data-ttu-id="93273-112">Es necesario el permiso ALTER PROCEDURE en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="93273-112">Requires ALTER PROCEDURE permission on the procedure.</span></span>  
  
##  <a name="how-to-modify-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="93273-113">Cómo modificar un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="93273-113">How to Modify a Stored Procedure</span></span>  
 <span data-ttu-id="93273-114">Puede usar cualquiera de los siguientes medios:</span><span class="sxs-lookup"><span data-stu-id="93273-114">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="93273-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93273-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="93273-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93273-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="93273-117">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="93273-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="93273-118">**Para modificar un procedimiento en Management Studio**</span><span class="sxs-lookup"><span data-stu-id="93273-118">**To modify a procedure in Management Studio**</span></span>  
  
1.  <span data-ttu-id="93273-119">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="93273-119">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="93273-120">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento y, a continuación, expanda **Programación**.</span><span class="sxs-lookup"><span data-stu-id="93273-120">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="93273-121">Expanda **Procedimientos almacenados**, haga clic con el botón derecho en el procedimiento que quiere modificar y luego haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="93273-121">Expand **Stored Procedures**, right-click the procedure to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="93273-122">Modifique el texto del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="93273-122">Modify the text of the stored procedure.</span></span>  
  
5.  <span data-ttu-id="93273-123">Para probar la sintaxis, en el menú **Consulta** , haga clic en **Analizar**.</span><span class="sxs-lookup"><span data-stu-id="93273-123">To test the syntax, on the **Query** menu, click **Parse**.</span></span>  
  
6.  <span data-ttu-id="93273-124">Para guardar las modificaciones en la definición de procedimiento, en el menú **Consulta** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="93273-124">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
7.  <span data-ttu-id="93273-125">Para guardar la definición de procedimiento actualizada como un script de [!INCLUDE[tsql](../../includes/tsql-md.md)] , en el menú **Archivo** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="93273-125">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="93273-126">Acepte el nombre de archivo o reemplácelo por un nombre nuevo y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="93273-126">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="93273-127">Valide todos los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="93273-127">Validate all user input.</span></span> <span data-ttu-id="93273-128">No concatene ninguna entrada de usuario antes de validarla.</span><span class="sxs-lookup"><span data-stu-id="93273-128">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="93273-129">No ejecute nunca un comando creado a partir de una entrada de usuario no validada.</span><span class="sxs-lookup"><span data-stu-id="93273-129">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="93273-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="93273-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="93273-131">**Para modificar un procedimiento en el Editor de consultas**</span><span class="sxs-lookup"><span data-stu-id="93273-131">**To modify a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="93273-132">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="93273-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="93273-133">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="93273-133">Expand **Databases**, expand the database in which the procedure belongs.</span></span> <span data-ttu-id="93273-134">O bien, en la barra de herramientas, seleccione la base de datos en la lista de bases de datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="93273-134">Or, from the tool bar, select the database from the list of available databases.</span></span> <span data-ttu-id="93273-135">En este ejemplo, seleccione la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93273-135">For this example, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
3.  <span data-ttu-id="93273-136">En el menú **Archivo** , haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="93273-136">On the **File** menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="93273-137">Copie y pegue el ejemplo siguiente en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="93273-137">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="93273-138">El ejemplo crea el procedimiento `uspVendorAllInfo` , que devuelve los nombres de todos los proveedores en la base de datos [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , los productos que suministran, su solvencia y su disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="93273-138">The example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
    ```  
  
    IF OBJECT_ID ( 'Purchasing.uspVendorAllInfo', 'P' ) IS NOT NULL   
        DROP PROCEDURE Purchasing.uspVendorAllInfo;  
    GO  
    CREATE PROCEDURE Purchasing.uspVendorAllInfo  
    WITH EXECUTE AS CALLER  
    AS  
        SET NOCOUNT ON;  
        SELECT v.Name AS Vendor, p.Name AS 'Product name',   
          v.CreditRating AS 'Rating',   
          v.ActiveFlag AS Availability  
        FROM Purchasing.Vendor v   
        INNER JOIN Purchasing.ProductVendor pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product p  
          ON pv.ProductID = p.ProductID   
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
5.  <span data-ttu-id="93273-139">En el menú **Archivo** , haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="93273-139">On the **File** menu, click **New Query**.</span></span>  
  
6.  <span data-ttu-id="93273-140">Copie y pegue el ejemplo siguiente en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="93273-140">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="93273-141">El ejemplo modifica el procedimiento `uspVendorAllInfo` .</span><span class="sxs-lookup"><span data-stu-id="93273-141">The example modifies the `uspVendorAllInfo` procedure.</span></span> <span data-ttu-id="93273-142">La cláusula EXECUTE AS CALLER se quita y el cuerpo del procedimiento se modifica para devolver solo los proveedores que proporcionan el producto especificado.</span><span class="sxs-lookup"><span data-stu-id="93273-142">The EXECUTE AS CALLER clause is removed and the body of the procedure is modified to return only those vendors that supply the specified product.</span></span> <span data-ttu-id="93273-143">Las funciones `LEFT` y `CASE` permiten personalizar la apariencia del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="93273-143">The `LEFT` and `CASE` functions customize the appearance of the result set.</span></span>  
  
    ```  
    ALTER PROCEDURE Purchasing.uspVendorAllInfo  
        @Product varchar(25)   
    AS  
        SET NOCOUNT ON;  
        SELECT LEFT(v.Name, 25) AS Vendor, LEFT(p.Name, 25) AS 'Product name',   
        'Rating' = CASE v.CreditRating   
            WHEN 1 THEN 'Superior'  
            WHEN 2 THEN 'Excellent'  
            WHEN 3 THEN 'Above average'  
            WHEN 4 THEN 'Average'  
            WHEN 5 THEN 'Below average'  
            ELSE 'No rating'  
            END  
        , Availability = CASE v.ActiveFlag  
            WHEN 1 THEN 'Yes'  
            ELSE 'No'  
            END  
        FROM Purchasing.Vendor AS v   
        INNER JOIN Purchasing.ProductVendor AS pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product AS p   
          ON pv.ProductID = p.ProductID   
        WHERE p.Name LIKE @Product  
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="93273-144">Para guardar las modificaciones en la definición de procedimiento, en el menú **Consulta** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="93273-144">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
8.  <span data-ttu-id="93273-145">Para guardar la definición de procedimiento actualizada como un script de [!INCLUDE[tsql](../../includes/tsql-md.md)] , en el menú **Archivo** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="93273-145">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="93273-146">Acepte el nombre de archivo o reemplácelo por un nombre nuevo y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="93273-146">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="93273-147">Para ejecutar el procedimiento almacenado modificado, ejecute el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="93273-147">To run the modified stored procedure, execute the following example.</span></span>  
  
    ```  
    EXEC Purchasing.uspVendorAllInfo N'LL Crankarm';  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="93273-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93273-148">See Also</span></span>  
 [<span data-ttu-id="93273-149">ALTER PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="93273-149">ALTER PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)  
  
  
