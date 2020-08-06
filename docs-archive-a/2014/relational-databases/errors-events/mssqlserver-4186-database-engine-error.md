---
title: MSSQLSERVER_4186 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4186 (Database Engine error)
ms.assetid: 1ae88554-f291-45bc-a186-6f41d9cd0fca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 525c1c3bd6e631044b8bc7f17b2c2a01aeb1ef8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662988"
---
# <a name="mssqlserver_4186"></a><span data-ttu-id="5589f-102">MSSQLSERVER_4186</span><span class="sxs-lookup"><span data-stu-id="5589f-102">MSSQLSERVER_4186</span></span>
    
## <a name="details"></a><span data-ttu-id="5589f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5589f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5589f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="5589f-104">Product Name</span></span>|<span data-ttu-id="5589f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5589f-105">SQL Server</span></span>|  
|<span data-ttu-id="5589f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="5589f-106">Event ID</span></span>|<span data-ttu-id="5589f-107">4186</span><span class="sxs-lookup"><span data-stu-id="5589f-107">4186</span></span>|  
|<span data-ttu-id="5589f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="5589f-108">Event Source</span></span>|<span data-ttu-id="5589f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5589f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5589f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5589f-110">Component</span></span>|<span data-ttu-id="5589f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5589f-111">SQLEngine</span></span>|  
|<span data-ttu-id="5589f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5589f-112">Symbolic Name</span></span>||  
|<span data-ttu-id="5589f-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5589f-113">Message Text</span></span>|<span data-ttu-id="5589f-114">No se puede hacer referencia a la columna '%ls.%.\*ls' en la cláusula OUTPUT porque la definición de columna contiene una subconsulta o hace referencia a una función que obtiene acceso a datos de usuario o del sistema.</span><span class="sxs-lookup"><span data-stu-id="5589f-114">Column '%ls.%.\*ls' cannot be referenced in the OUTPUT clause because the column definition contains a subquery or references a function that performs user or system data access.</span></span> <span data-ttu-id="5589f-115">De forma predeterminada, se asume que una función obtiene acceso a los datos si no está enlazada a un esquema.</span><span class="sxs-lookup"><span data-stu-id="5589f-115">A function is assumed by default to perform data access if it is not schemabound.</span></span> <span data-ttu-id="5589f-116">Considere la posibilidad de quitar la subconsulta o la función de la definición de columna o quitar la columna de la cláusula OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="5589f-116">Consider removing the subquery or function from the column definition or removing the column from the OUTPUT clause.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5589f-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="5589f-117">Explanation</span></span>  
 <span data-ttu-id="5589f-118">Para evitar un comportamiento no determinista, la cláusula OUTPUT no puede hacer referencia a una columna desde una vista o una función insertada con valores de tabla si dicha tabla se ha definido mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5589f-118">To prevent nondeterministic behavior, the OUTPUT clause cannot reference a column from a view or inline table-valued function when that column is defined by one of the following methods:</span></span>  
  
-   <span data-ttu-id="5589f-119">Una subconsulta.</span><span class="sxs-lookup"><span data-stu-id="5589f-119">A subquery.</span></span>  
  
-   <span data-ttu-id="5589f-120">Una función definida por el usuario que obtiene acceso a datos de usuario o del sistema, o que se asume que obtiene dicho acceso.</span><span class="sxs-lookup"><span data-stu-id="5589f-120">A user-defined function that performs user or system data access, or is assumed to perform such access.</span></span>  
  
-   <span data-ttu-id="5589f-121">Una columna calculada que contiene una función definida por el usuario que obtiene acceso a datos de usuario o del sistema en su definición.</span><span class="sxs-lookup"><span data-stu-id="5589f-121">A computed column that contains a user-defined function that performs user or system data access in its definition.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="5589f-122">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5589f-122">Examples</span></span>  
 <span data-ttu-id="5589f-123">**Columna de vista definida por una subconsulta**</span><span class="sxs-lookup"><span data-stu-id="5589f-123">**View Column Defined by a Subquery**</span></span>  
  
 <span data-ttu-id="5589f-124">En el ejemplo siguiente se crea una vista que usa una subconsulta en la lista de selección para definir la columna `State`.</span><span class="sxs-lookup"><span data-stu-id="5589f-124">The following example creates a view that uses a subquery in the select list to define the column `State`.</span></span> <span data-ttu-id="5589f-125">A continuación, una instrucción UPDATE hace referencia a la columna `State` en la cláusula OUTPUT y produce un error a causa de la subconsulta en la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="5589f-125">An UPDATE statement then references the `State` column in the OUTPUT clause and fails because ob the subquery in the select list.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW dbo.V1  
AS  
    SELECT City,  
-- subquery to return the State name  
           (SELECT Name FROM Person.StateProvince AS sp   
            WHERE sp.StateProvinceID = a.StateProvinceID) AS State  
    FROM Person.Address AS a;  
GO  
--Reference the State column in the OUTPUT clause of an UPDATE statement  
UPDATE dbo.V1   
SET City = City + 'Test'   
OUTPUT deleted.City, deleted.State, inserted.City, inserted.State  
WHERE State = 'Texas';  
GO  
```  
  
 <span data-ttu-id="5589f-126">**Columna de vista definida por una función**</span><span class="sxs-lookup"><span data-stu-id="5589f-126">**View Column Defined by a Function**</span></span>  
  
 <span data-ttu-id="5589f-127">En el ejemplo siguiente se crea una vista que usa la función escalar de acceso a datos `dbo.ufnGetStock`de la lista de selección para definir la columna `CurrentInventory`.</span><span class="sxs-lookup"><span data-stu-id="5589f-127">The following example creates a view that uses the data accessing, scalar function `dbo.ufnGetStock` in the select list to define the column `CurrentInventory`.</span></span> <span data-ttu-id="5589f-128">A continuación, una instrucción UPDATE hace referencia a la columna `CurrentInventory` en la cláusula OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="5589f-128">An UPDATE statement then references the `CurrentInventory` column in the OUTPUT clause .</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE VIEW Production.ReorderLevels  
AS  
    SELECT ProductID, ProductModelID, ReorderPoint,  
           dbo.ufnGetStock(ProductID) AS CurrentInventory  
    FROM Production.Product;  
GO  
  
UPDATE Production.ReorderLevels  
SET ReorderPoint += CurrentInventory  
OUTPUT deleted.ReorderPoint, deleted.CurrentInventory,  
       inserted.ReorderPoint, inserted.CurrentInventory  
WHERE ProductModelID BETWEEN 75 and 80;  
```  
  
## <a name="user-action"></a><span data-ttu-id="5589f-129">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5589f-129">User Action</span></span>  
 <span data-ttu-id="5589f-130">El error 4186 se puede corregir de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="5589f-130">Error 4186 can be corrected in one of the following ways:</span></span>  
  
-   <span data-ttu-id="5589f-131">Use combinaciones en lugar de subconsultas para definir la columna en la vista o en la función.</span><span class="sxs-lookup"><span data-stu-id="5589f-131">Use joins instead of subqueries to define the column in the view or function.</span></span> <span data-ttu-id="5589f-132">Por ejemplo, puede volver a escribir la vista `dbo.V1` como sigue.</span><span class="sxs-lookup"><span data-stu-id="5589f-132">For example, you can rewrite the view `dbo.V1` as follows.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE VIEW dbo.V1  
    AS  
        SELECT City, sp.Name AS State  
        FROM Person.Address AS a   
        JOIN Person.StateProvince AS sp   
        ON sp.StateProvinceID = a.StateProvinceID;  
    ```  
  
-   <span data-ttu-id="5589f-133">Examine la definición de la función definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5589f-133">Examine the definition of the user-defined function.</span></span> <span data-ttu-id="5589f-134">Si la función no obtiene acceso a datos de usuario o del sistema, modifíquela para que incluya la cláusula WITH SCHEMABINDING.</span><span class="sxs-lookup"><span data-stu-id="5589f-134">If the function does not perform user or system data access, alter the function to include the WITH SCHEMABINDING clause.</span></span>  
  
-   <span data-ttu-id="5589f-135">Quite la columna de la cláusula OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="5589f-135">Remove the column from the OUTPUT clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5589f-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5589f-136">See Also</span></span>  
 [<span data-ttu-id="5589f-137">OUTPUT Clause &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5589f-137">OUTPUT Clause &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/output-clause-transact-sql)  
  
  
