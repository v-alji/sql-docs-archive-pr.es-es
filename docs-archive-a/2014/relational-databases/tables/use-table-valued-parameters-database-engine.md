---
title: Usar parámetros con valores de tabla (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
f1_keywords:
- DECLARE
- CREATE TYPE
helpviewer_keywords:
- table-valued parameters
- table-valued parameters, about table-valued parameters
- parameters [SQL Server], table-valued
- TVP See table-valued parameters
ms.assetid: 5e95a382-1e01-4c74-81f5-055612c2ad99
author: stevestein
ms.author: sstein
ms.openlocfilehash: fa7013fddc6b2ce12ad9ad0f9fcb511d93915e05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672856"
---
# <a name="use-table-valued-parameters-database-engine"></a><span data-ttu-id="0ee52-102">Usar parámetros con valores de tabla (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="0ee52-102">Use Table-Valued Parameters (Database Engine)</span></span>
  <span data-ttu-id="0ee52-103">Los parámetros con valores de tabla se declaran utilizando tipos de tabla definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="0ee52-103">Table-valued parameters are declared by using user-defined table types.</span></span> <span data-ttu-id="0ee52-104">Puede utilizar parámetros con valores de tabla para enviar varias filas de datos a una rutina o una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] , como un procedimiento almacenado o una función, sin crear una tabla temporal o muchos parámetros.</span><span class="sxs-lookup"><span data-stu-id="0ee52-104">You can use table-valued parameters to send multiple rows of data to a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement or a routine, such as a stored procedure or function, without creating a temporary table or many parameters.</span></span>  
  
 <span data-ttu-id="0ee52-105">Los parámetros con valores de tabla son como las matrices de parámetros en OLE DB y ODBC, pero proporcionan más flexibilidad y una integración más estrecha con [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ee52-105">Table-valued parameters are like parameter arrays in OLE DB and ODBC, but offer more flexibility and closer integration with [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0ee52-106">Los parámetros con valores de tabla también tienen la ventaja de poder participar en operaciones basadas en conjuntos.</span><span class="sxs-lookup"><span data-stu-id="0ee52-106">Table-valued parameters also have the benefit of being able to participate in set-based operations.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="0ee52-107">pasa parámetros con valores de tabla a rutinas por referencia para evitar la realización de una copia de los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="0ee52-107">passes table-valued parameters to routines by reference to avoid making a copy of the input data.</span></span> <span data-ttu-id="0ee52-108">Puede crear y ejecutar rutinas [!INCLUDE[tsql](../../includes/tsql-md.md)] con parámetros con valores de tabla y llamarlas desde código de [!INCLUDE[tsql](../../includes/tsql-md.md)] , clientes nativos y administrados en cualquier lenguaje administrado.</span><span class="sxs-lookup"><span data-stu-id="0ee52-108">You can create and execute [!INCLUDE[tsql](../../includes/tsql-md.md)] routines with table-valued parameters, and call them from [!INCLUDE[tsql](../../includes/tsql-md.md)] code, managed and native clients in any managed language.</span></span>  
  
 <span data-ttu-id="0ee52-109">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="0ee52-109">**In This Topic:**</span></span>  
  
 [<span data-ttu-id="0ee52-110">Ventajas</span><span class="sxs-lookup"><span data-stu-id="0ee52-110">Benefits</span></span>](#Benefits)  
  
 [<span data-ttu-id="0ee52-111">Restricciones</span><span class="sxs-lookup"><span data-stu-id="0ee52-111">Restrictions</span></span>](#Restrictions)  
  
 [<span data-ttu-id="0ee52-112">Parámetros con valores de tabla frente a operaciones BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="0ee52-112">Table-Valued Parameters vs. BULK INSERT Operations</span></span>](#BulkInsert)  
  
 [<span data-ttu-id="0ee52-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ee52-113">Example</span></span>](#Example)  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="0ee52-114">Ventajas</span><span class="sxs-lookup"><span data-stu-id="0ee52-114">Benefits</span></span>  
 <span data-ttu-id="0ee52-115">Un parámetro con valores de tabla está incluido en el ámbito de procedimiento almacenado, función o texto [!INCLUDE[tsql](../../includes/tsql-md.md)] dinámico, exactamente igual que los demás parámetros.</span><span class="sxs-lookup"><span data-stu-id="0ee52-115">A table-valued parameter is scoped to the stored procedure, function, or dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] text, exactly like other parameters.</span></span> <span data-ttu-id="0ee52-116">Del mismo modo, una variable de tipo de tabla tiene el mismo ámbito que cualquier otra variable local creada mediante una instrucción DECLARE.</span><span class="sxs-lookup"><span data-stu-id="0ee52-116">Similarly, a variable of table type has scope like any other local variable that is created by using a DECLARE statement.</span></span> <span data-ttu-id="0ee52-117">Puede declarar variables con valores de tabla en instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] dinámicas y pasar estas variables como parámetros con valores de tabla a procedimientos almacenados y funciones.</span><span class="sxs-lookup"><span data-stu-id="0ee52-117">You can declare table-valued variables within dynamic [!INCLUDE[tsql](../../includes/tsql-md.md)] statements and pass these variables as table-valued parameters to stored procedures and functions.</span></span>  
  
 <span data-ttu-id="0ee52-118">Los parámetros con valores de tabla proporcionan más flexibilidad y, en algunos casos, un rendimiento mayor que las tablas temporales u otros medios para pasar una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="0ee52-118">Table-valued parameters offer more flexibility and in some cases better performance than temporary tables or other ways to pass a list of parameters.</span></span> <span data-ttu-id="0ee52-119">Los parámetros con valores de tabla proporcionan las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="0ee52-119">Table-valued parameters offer the following benefits:</span></span>  
  
-   <span data-ttu-id="0ee52-120">No adquieren bloqueos para el rellenado inicial de datos de un cliente.</span><span class="sxs-lookup"><span data-stu-id="0ee52-120">Do not acquire locks for the initial population of data from a client.</span></span>  
  
-   <span data-ttu-id="0ee52-121">Proporcionan un modelo de programación simple.</span><span class="sxs-lookup"><span data-stu-id="0ee52-121">Provide a simple programming model.</span></span>  
  
-   <span data-ttu-id="0ee52-122">Permiten la inclusión de lógica comercial compleja en una rutina única.</span><span class="sxs-lookup"><span data-stu-id="0ee52-122">Enable you to include complex business logic in a single routine.</span></span>  
  
-   <span data-ttu-id="0ee52-123">Reducen los viajes de ida y vuelta al servidor.</span><span class="sxs-lookup"><span data-stu-id="0ee52-123">Reduce round trips to the server.</span></span>  
  
-   <span data-ttu-id="0ee52-124">Pueden tener una estructura de tabla de cardinalidad diferente.</span><span class="sxs-lookup"><span data-stu-id="0ee52-124">Can have a table structure of different cardinality.</span></span>  
  
-   <span data-ttu-id="0ee52-125">Tienen establecimiento inflexible de tipos.</span><span class="sxs-lookup"><span data-stu-id="0ee52-125">Are strongly typed.</span></span>  
  
-   <span data-ttu-id="0ee52-126">Permiten al cliente especificar un criterio de ordenación y claves únicas.</span><span class="sxs-lookup"><span data-stu-id="0ee52-126">Enable the client to specify sort order and unique keys.</span></span>  
  
-   <span data-ttu-id="0ee52-127">Se almacenan en caché como una tabla temporal cuando se usa en un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0ee52-127">Are cached like a temp table when used in a stored procedure.</span></span> <span data-ttu-id="0ee52-128">A partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], los parámetros con valores de tabla también se almacenan en caché para las consultas con parámetros.</span><span class="sxs-lookup"><span data-stu-id="0ee52-128">Starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], table-valued parameters are also cached for parameterized queries.</span></span>  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0ee52-129">Restricciones</span><span class="sxs-lookup"><span data-stu-id="0ee52-129">Restrictions</span></span>  
 <span data-ttu-id="0ee52-130">Los parámetros con valores de tabla tienen las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0ee52-130">Table-valued parameters have the following restrictions:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0ee52-131">no mantiene estadísticas en las columnas de parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ee52-131">does not maintain statistics on columns of table-valued parameters.</span></span>  
  
-   <span data-ttu-id="0ee52-132">Los parámetros con valores de tabla se deben pasar como parámetros READONLY de entrada a rutinas [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ee52-132">Table-valued parameters must be passed as input READONLY parameters to [!INCLUDE[tsql](../../includes/tsql-md.md)] routines.</span></span> <span data-ttu-id="0ee52-133">No se pueden realizar operaciones de DML como UPDATE, DELETE o INSERT en un parámetro con valores de tabla en el cuerpo de una rutina.</span><span class="sxs-lookup"><span data-stu-id="0ee52-133">You cannot perform DML operations such as UPDATE, DELETE, or INSERT on a table-valued parameter in the body of a routine.</span></span>  
  
-   <span data-ttu-id="0ee52-134">No se puede utilizar un parámetro con valores de tabla como destino de una instrucción SELECT INTO o INSERT EXEC.</span><span class="sxs-lookup"><span data-stu-id="0ee52-134">You cannot use a table-valued parameter as target of a SELECT INTO or INSERT EXEC statement.</span></span> <span data-ttu-id="0ee52-135">Un parámetro con valores de tabla puede estar en la cláusula FROM de SELECT INTO o en el procedimiento almacenado o la cadena INSERT EXEC.</span><span class="sxs-lookup"><span data-stu-id="0ee52-135">A table-valued parameter can be in the FROM clause of SELECT INTO or in the INSERT EXEC string or stored procedure.</span></span>  
  
##  <a name="table-valued-parameters-vs-bulk-insert-operations"></a><a name="BulkInsert"></a><span data-ttu-id="0ee52-136">Parámetros con valores de tabla frente a operaciones de BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="0ee52-136">Table-Valued Parameters vs. BULK INSERT Operations</span></span>  
 <span data-ttu-id="0ee52-137">El uso de parámetros con valores de tabla es comparable a otras formas de uso de variables basadas en conjuntos; sin embargo, el uso de parámetros con valores de tabla puede ser con frecuencia más rápido para grandes conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="0ee52-137">Using table-valued parameters is comparable to other ways of using set-based variables; however, using table-valued parameters frequently can be faster for large data sets.</span></span> <span data-ttu-id="0ee52-138">Si se comparan con operaciones masivas que tienen un costo de inicio mayor que los parámetros con valores de tabla, el comportamiento de los parámetros con valores de tabla es excelente cuando se insertan menos de 1.000 filas.</span><span class="sxs-lookup"><span data-stu-id="0ee52-138">Compared to bulk operations that have a greater startup cost than table-valued parameters, table-valued parameters perform well for inserting less than 1000 rows.</span></span>  
  
 <span data-ttu-id="0ee52-139">Los parámetros con valores de tabla que se vuelven a utilizar se benefician del almacenamiento en caché de tablas temporales.</span><span class="sxs-lookup"><span data-stu-id="0ee52-139">Table-valued parameters that are reused benefit from temporary table caching.</span></span> <span data-ttu-id="0ee52-140">Este almacenamiento en memoria caché de tablas proporciona una escalabilidad mejor que en el caso de operaciones BULK INSERT equivalentes.</span><span class="sxs-lookup"><span data-stu-id="0ee52-140">This table caching enables better scalability than equivalent BULK INSERT operations.</span></span> <span data-ttu-id="0ee52-141">Si se usan pequeñas operaciones de inserción de filas, se puede conseguir una ligera mejora del rendimiento utilizando listas de parámetros o instrucciones por lotes en lugar de operaciones BULK INSERT o parámetros con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="0ee52-141">By using small row-insert operations a small performance benefit might be gained by using parameter lists or batched statements instead of BULK INSERT operations or table-valued parameters.</span></span> <span data-ttu-id="0ee52-142">Sin embargo, estos métodos son menos apropiados para programar, y el rendimiento disminuye rápidamente cuando aumentan las filas.</span><span class="sxs-lookup"><span data-stu-id="0ee52-142">However, these methods are less convenient to program, and performance decreases quickly as rows increase.</span></span>  
  
 <span data-ttu-id="0ee52-143">Los parámetros con valores de tabla se comportan tan bien o mejor que una implementación de matriz de parámetros equivalente.</span><span class="sxs-lookup"><span data-stu-id="0ee52-143">Table-valued parameters perform equally well or better than an equivalent parameter array implementation.</span></span>  
  
##  <a name="example"></a><a name="Example"></a> <span data-ttu-id="0ee52-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ee52-144">Example</span></span>  
 <span data-ttu-id="0ee52-145">En el ejemplo siguiente se utiliza [!INCLUDE[tsql](../../includes/tsql-md.md)] y se muestra la forma de crear un tipo de parámetro con valores de tabla, declarar una variable para hacer referencia a ella, rellenar la lista de parámetros y, a continuación, pasar los valores a un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="0ee52-145">The following example uses [!INCLUDE[tsql](../../includes/tsql-md.md)] and shows you how to create a table-valued parameter type, declare a variable to reference it, fill the parameter list, and then pass the values to a stored procedure.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
/* Create a table type. */  
CREATE TYPE LocationTableType AS TABLE   
( LocationName VARCHAR(50)  
, CostRate INT );  
GO  
  
/* Create a procedure to receive data for the table-valued parameter. */  
CREATE PROCEDURE dbo. usp_InsertProductionLocation  
    @TVP LocationTableType READONLY  
    AS   
    SET NOCOUNT ON  
    INSERT INTO AdventureWorks2012.Production.Location  
           (Name  
           ,CostRate  
           ,Availability  
           ,ModifiedDate)  
        SELECT *, 0, GETDATE()  
        FROM  @TVP;  
        GO  
  
/* Declare a variable that references the type. */  
DECLARE @LocationTVP AS LocationTableType;  
  
/* Add data to the table variable. */  
INSERT INTO @LocationTVP (LocationName, CostRate)  
    SELECT Name, 0.00  
    FROM AdventureWorks2012.Person.StateProvince;  
  
/* Pass the table variable data to a stored procedure. */  
EXEC usp_InsertProductionLocation @LocationTVP;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ee52-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ee52-146">See Also</span></span>  
 <span data-ttu-id="0ee52-147">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ee52-147">[CREATE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-type-transact-sql) </span></span>  
 <span data-ttu-id="0ee52-148">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ee52-148">[DECLARE @local_variable &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-local-variable-transact-sql) </span></span>  
 <span data-ttu-id="0ee52-149">[Sys. Types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ee52-149">[sys.types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-types-transact-sql) </span></span>  
 <span data-ttu-id="0ee52-150">[Sys. Parameters &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ee52-150">[sys.parameters &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameters-transact-sql) </span></span>  
 <span data-ttu-id="0ee52-151">[Sys. parameter_type_usages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ee52-151">[sys.parameter_type_usages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-parameter-type-usages-transact-sql) </span></span>  
 <span data-ttu-id="0ee52-152">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0ee52-152">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 [<span data-ttu-id="0ee52-153">CREATE FUNCTION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0ee52-153">CREATE FUNCTION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-function-transact-sql)  
  
  
