---
title: Creación de funciones definidas por el usuario (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- SCHEMABINDING clause
- schema-bound functions [SQL Server]
- user-defined functions [SQL Server], creating
- CREATE FUNCTION statement
- valid statements [SQL Server]
ms.assetid: f0d5dd10-73fd-4e05-9177-07f56552bdf7
author: rothja
ms.author: jroth
ms.openlocfilehash: 790fa1b969f933890e050311173fcde3f12c37ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676904"
---
# <a name="create-user-defined-functions-database-engine"></a><span data-ttu-id="647ad-102">Crear funciones definidas por el usuario (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="647ad-102">Create User-defined Functions (Database Engine)</span></span>
  <span data-ttu-id="647ad-103">En este tema se describe cómo crear una función definida por el usuario en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="647ad-103">This topic describes how to create a user-defined function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="647ad-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="647ad-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="647ad-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="647ad-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="647ad-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="647ad-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="647ad-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="647ad-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="647ad-108">**Para crear una función definida por el usuario:**</span><span class="sxs-lookup"><span data-stu-id="647ad-108">**To create a user-defined function:**</span></span>  
  
     [<span data-ttu-id="647ad-109">Crear una función escalar</span><span class="sxs-lookup"><span data-stu-id="647ad-109">Create a Scalar Function</span></span>](#Scalar)  
  
     [<span data-ttu-id="647ad-110">Crear una función con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="647ad-110">Create a Table-valued Function</span></span>](#TVF)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="647ad-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="647ad-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="647ad-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="647ad-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="647ad-113">Las funciones definidas por el usuario no se pueden utilizar para realizar acciones que modifican el estado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="647ad-113">User-defined functions cannot be used to perform actions that modify the database state.</span></span>  
  
-   <span data-ttu-id="647ad-114">Las funciones definidas por el usuario no pueden tener una cláusula OUTPUT INTO que tenga una tabla como destino.</span><span class="sxs-lookup"><span data-stu-id="647ad-114">User-defined functions cannot contain an OUTPUT INTO clause that has a table as its target.</span></span>  
  
-   <span data-ttu-id="647ad-115">Las funciones definidas por el usuario no pueden devolver varios conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="647ad-115">User-defined functions can not return multiple result sets.</span></span> <span data-ttu-id="647ad-116">Utilice un procedimiento almacenado si necesita devolver varios conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="647ad-116">Use a stored procedure if you need to return multiple result sets.</span></span>  
  
-   <span data-ttu-id="647ad-117">El control de errores está restringido en una función definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="647ad-117">Error handling is restricted in a user-defined function.</span></span> <span data-ttu-id="647ad-118">Una UDF no admite TRY... CATCH @ERROR o RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="647ad-118">A UDF does not support TRY...CATCH, @ERROR or RAISERROR.</span></span>  
  
-   <span data-ttu-id="647ad-119">Las funciones definidas por el usuario no pueden llamar a un procedimiento almacenado, pero pueden llamar a un procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="647ad-119">User-defined functions cannot call a stored procedure, but can call an extended stored procedure.</span></span>  
  
-   <span data-ttu-id="647ad-120">Las funciones definidas por el usuario no pueden utilizar tablas temporales o SQL dinámicas.</span><span class="sxs-lookup"><span data-stu-id="647ad-120">User-defined functions cannot make use of dynamic SQL or temp tables.</span></span> <span data-ttu-id="647ad-121">Se permiten las variables de tabla.</span><span class="sxs-lookup"><span data-stu-id="647ad-121">Table variables are allowed.</span></span>  
  
-   <span data-ttu-id="647ad-122">Las instrucciones SET no se permiten en una función definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="647ad-122">SET statements are not allowed in a user-defined function.</span></span>  
  
-   <span data-ttu-id="647ad-123">No se admite la cláusula FOR XML</span><span class="sxs-lookup"><span data-stu-id="647ad-123">The FOR XML clause is not allowed</span></span>  
  
-   <span data-ttu-id="647ad-124">Las funciones definidas por el usuario se pueden anidar; es decir, una función definida por el usuario puede llamar a otra.</span><span class="sxs-lookup"><span data-stu-id="647ad-124">User-defined functions can be nested; that is, one user-defined function can call another.</span></span> <span data-ttu-id="647ad-125">El nivel de anidamiento aumenta cuando se empieza a ejecutar la función llamada y disminuye cuando se termina de ejecutar la función llamada.</span><span class="sxs-lookup"><span data-stu-id="647ad-125">The nesting level is incremented when the called function starts execution, and decremented when the called function finishes execution.</span></span> <span data-ttu-id="647ad-126">Las funciones definidas por el usuario se pueden anidar hasta un máximo de 32 niveles.</span><span class="sxs-lookup"><span data-stu-id="647ad-126">User-defined functions can be nested up to 32 levels.</span></span> <span data-ttu-id="647ad-127">Si se superan los niveles máximos de anidamiento, la cadena completa de funciones de llamada produce un error.</span><span class="sxs-lookup"><span data-stu-id="647ad-127">Exceeding the maximum levels of nesting causes the whole calling function chain to fail.</span></span> <span data-ttu-id="647ad-128">Cualquier referencia a código administrado desde una función Transact-SQL definida por el usuario cuenta como uno de los 32 niveles de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="647ad-128">Any reference to managed code from a Transact-SQL user-defined function counts as one level against the 32-level nesting limit.</span></span> <span data-ttu-id="647ad-129">Los métodos invocados desde el código administrado no cuentan para este límite.</span><span class="sxs-lookup"><span data-stu-id="647ad-129">Methods invoked from within managed code do not count against this limit.</span></span>  
  
-   <span data-ttu-id="647ad-130">Las siguientes instrucciones de Service Broker no se pueden incluir en la definición de una función Transact-SQL definida por el usuario:</span><span class="sxs-lookup"><span data-stu-id="647ad-130">The following Service Broker statements cannot be included in the definition of a Transact-SQL user-defined function:</span></span>  
  
    -   <span data-ttu-id="647ad-131">EMPEZAR CONVERSACIÓN DE DIÁLOGO</span><span class="sxs-lookup"><span data-stu-id="647ad-131">BEGIN DIALOG CONVERSATION</span></span>  
  
    -   <span data-ttu-id="647ad-132">FINALIZAR CONVERSACIÓN</span><span class="sxs-lookup"><span data-stu-id="647ad-132">END CONVERSATION</span></span>  
  
    -   <span data-ttu-id="647ad-133">GET CONVERSATION GROUP</span><span class="sxs-lookup"><span data-stu-id="647ad-133">GET CONVERSATION GROUP</span></span>  
  
    -   <span data-ttu-id="647ad-134">MOVE CONVERSATION</span><span class="sxs-lookup"><span data-stu-id="647ad-134">MOVE CONVERSATION</span></span>  
  
    -   <span data-ttu-id="647ad-135">RECEIVE</span><span class="sxs-lookup"><span data-stu-id="647ad-135">RECEIVE</span></span>  
  
    -   <span data-ttu-id="647ad-136">ENVIAR</span><span class="sxs-lookup"><span data-stu-id="647ad-136">SEND</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="647ad-137">Seguridad</span><span class="sxs-lookup"><span data-stu-id="647ad-137">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="647ad-138">Permisos</span><span class="sxs-lookup"><span data-stu-id="647ad-138">Permissions</span></span>  
 <span data-ttu-id="647ad-139">Se requiere el permiso CREATE FUNCTION en la base de datos y el permiso ALTER en el esquema en el que se va a crear la función.</span><span class="sxs-lookup"><span data-stu-id="647ad-139">Requires CREATE FUNCTION permission in the database and ALTER permission on the schema in which the function is being created.</span></span> <span data-ttu-id="647ad-140">Si la función especifica un tipo definido por el usuario, requiere el permiso EXECUTE para ese tipo.</span><span class="sxs-lookup"><span data-stu-id="647ad-140">If the function specifies a user-defined type, requires EXECUTE permission on the type.</span></span>  
  
##  <a name="scalar-functions"></a><a name="Scalar"></a><span data-ttu-id="647ad-141">Funciones escalares</span><span class="sxs-lookup"><span data-stu-id="647ad-141">Scalar Functions</span></span>  
 <span data-ttu-id="647ad-142">En el ejemplo siguiente se crea una función escalar de varias instrucciones en la base de datos [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="647ad-142">The following example creates a multistatement scalar function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="647ad-143">La función toma un valor de entrada, `ProductID`, y devuelve un valor de devolución único, la cantidad agregada del producto especificado en el inventario.</span><span class="sxs-lookup"><span data-stu-id="647ad-143">The function takes one input value, a `ProductID`, and returns a single data value, the aggregated quantity of the specified product in inventory.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufnGetInventoryStock', N'FN') IS NOT NULL  
    DROP FUNCTION ufnGetInventoryStock;  
GO  
CREATE FUNCTION dbo.ufnGetInventoryStock(@ProductID int)  
RETURNS int   
AS   
-- Returns the stock level for the product.  
BEGIN  
    DECLARE @ret int;  
    SELECT @ret = SUM(p.Quantity)   
    FROM Production.ProductInventory p   
    WHERE p.ProductID = @ProductID   
        AND p.LocationID = '6';  
     IF (@ret IS NULL)   
        SET @ret = 0;  
    RETURN @ret;  
END;  
GO  
  
```  
  
 <span data-ttu-id="647ad-144">En el ejemplo siguiente se utiliza la función `ufnGetInventoryStock` para devolver la cantidad de inventario actual de aquellos productos que tienen un `ProductModelID` entre 75 y 80.</span><span class="sxs-lookup"><span data-stu-id="647ad-144">The following example uses the `ufnGetInventoryStock` function to return the current inventory quantity for products that have a `ProductModelID` between 75 and 80.</span></span>  
  
```  
SELECT ProductModelID, Name, dbo.ufnGetInventoryStock(ProductID)AS CurrentSupply  
FROM Production.Product  
WHERE ProductModelID BETWEEN 75 and 80;  
  
```  
  
##  <a name="table-valued-functions"></a><a name="TVF"></a><span data-ttu-id="647ad-145">Funciones con valores de tabla</span><span class="sxs-lookup"><span data-stu-id="647ad-145">Table-Valued Functions</span></span>  
 <span data-ttu-id="647ad-146">En el ejemplo siguiente se crea una función insertada con valores de tabla en la base de datos [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="647ad-146">The following example creates an inline table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="647ad-147">La función toma un parámetro de entrada, Id. de cliente (almacén), y devuelve las columnas `ProductID`, `Name`, y el agregado de las ventas del año hasta la fecha como `YTD Total` para cada producto vendido en el almacén.</span><span class="sxs-lookup"><span data-stu-id="647ad-147">The function takes one input parameter, a customer (store) ID, and returns the columns `ProductID`, `Name`, and the aggregate of year-to-date sales as `YTD Total` for each product sold to the store.</span></span>  
  
```  
IF OBJECT_ID (N'Sales.ufn_SalesByStore', N'IF') IS NOT NULL  
    DROP FUNCTION Sales.ufn_SalesByStore;  
GO  
CREATE FUNCTION Sales.ufn_SalesByStore (@storeid int)  
RETURNS TABLE  
AS  
RETURN   
(  
    SELECT P.ProductID, P.Name, SUM(SD.LineTotal) AS 'Total'  
    FROM Production.Product AS P   
    JOIN Sales.SalesOrderDetail AS SD ON SD.ProductID = P.ProductID  
    JOIN Sales.SalesOrderHeader AS SH ON SH.SalesOrderID = SD.SalesOrderID  
    JOIN Sales.Customer AS C ON SH.CustomerID = C.CustomerID  
    WHERE C.StoreID = @storeid  
    GROUP BY P.ProductID, P.Name  
);  
  
```  
  
 <span data-ttu-id="647ad-148">En el ejemplo siguiente se invoca la función y se especifica el identificador de cliente 602.</span><span class="sxs-lookup"><span data-stu-id="647ad-148">The following example invokes the function and specifies customer ID 602.</span></span>  
  
```  
SELECT * FROM Sales.ufn_SalesByStore (602);  
  
```  
  
 <span data-ttu-id="647ad-149">En el ejemplo siguiente se crea una función con valores de tabla en la base de datos [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="647ad-149">The following example creates a table-valued function in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="647ad-150">La función toma un único parámetro de entrada, `EmployeeID` , y devuelve una lista de todos los empleados que dependen directa o indirectamente del empleado especificado.</span><span class="sxs-lookup"><span data-stu-id="647ad-150">The function takes a single input parameter, an `EmployeeID` and returns a list of all the employees who report to the specified employee directly or indirectly.</span></span> <span data-ttu-id="647ad-151">La función se invoca luego especificando el empleado ID 109.</span><span class="sxs-lookup"><span data-stu-id="647ad-151">The function is then invoked specifying employee ID 109.</span></span>  
  
```  
IF OBJECT_ID (N'dbo.ufn_FindReports', N'TF') IS NOT NULL  
    DROP FUNCTION dbo.ufn_FindReports;  
GO  
CREATE FUNCTION dbo.ufn_FindReports (@InEmpID INTEGER)  
RETURNS @retFindReports TABLE   
(  
    EmployeeID int primary key NOT NULL,  
    FirstName nvarchar(255) NOT NULL,  
    LastName nvarchar(255) NOT NULL,  
    JobTitle nvarchar(50) NOT NULL,  
    RecursionLevel int NOT NULL  
)  
--Returns a result set that lists all the employees who report to the   
--specific employee directly or indirectly.*/  
AS  
BEGIN  
WITH EMP_cte(EmployeeID, OrganizationNode, FirstName, LastName, JobTitle, RecursionLevel) -- CTE name and columns  
    AS (  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, 0 -- Get the initial list of Employees for Manager n  
        FROM HumanResources.Employee e   
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        WHERE e.BusinessEntityID = @InEmpID  
        UNION ALL  
        SELECT e.BusinessEntityID, e.OrganizationNode, p.FirstName, p.LastName, e.JobTitle, RecursionLevel + 1 -- Join recursive member to anchor  
        FROM HumanResources.Employee e   
            INNER JOIN EMP_cte  
            ON e.OrganizationNode.GetAncestor(1) = EMP_cte.OrganizationNode  
INNER JOIN Person.Person p   
ON p.BusinessEntityID = e.BusinessEntityID  
        )  
-- copy the required columns to the result of the function   
   INSERT @retFindReports  
   SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
   FROM EMP_cte   
   RETURN  
END;  
GO  
-- Example invocation  
SELECT EmployeeID, FirstName, LastName, JobTitle, RecursionLevel  
FROM dbo.ufn_FindReports(1);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="647ad-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="647ad-152">See Also</span></span>  
 <span data-ttu-id="647ad-153">[Funciones definidas por el usuario](user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="647ad-153">[User-Defined Functions](user-defined-functions.md) </span></span>  
 [<span data-ttu-id="647ad-154">CREATE FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="647ad-154">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
