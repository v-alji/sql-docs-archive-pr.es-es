---
title: MSSQLSERVER_4104 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 4104 (Database Engine error)
ms.assetid: 52dc32d8-97ad-4ef0-834d-2e68f215d007
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cbbc28a3e15af6fdc8fd44633ccbdfc46e49149d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675426"
---
# <a name="mssqlserver_4104"></a><span data-ttu-id="dc059-102">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="dc059-102">MSSQLSERVER_4104</span></span>
    
## <a name="details"></a><span data-ttu-id="dc059-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="dc059-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc059-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="dc059-104">Product Name</span></span>|<span data-ttu-id="dc059-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc059-105">SQL Server</span></span>|  
|<span data-ttu-id="dc059-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="dc059-106">Event ID</span></span>|<span data-ttu-id="dc059-107">4104</span><span class="sxs-lookup"><span data-stu-id="dc059-107">4104</span></span>|  
|<span data-ttu-id="dc059-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="dc059-108">Event Source</span></span>|<span data-ttu-id="dc059-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dc059-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dc059-110">Componente</span><span class="sxs-lookup"><span data-stu-id="dc059-110">Component</span></span>|<span data-ttu-id="dc059-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dc059-111">SQLEngine</span></span>|  
|<span data-ttu-id="dc059-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="dc059-112">Symbolic Name</span></span>|<span data-ttu-id="dc059-113">ALG_MULTI_ID_BAD</span><span class="sxs-lookup"><span data-stu-id="dc059-113">ALG_MULTI_ID_BAD</span></span>|  
|<span data-ttu-id="dc059-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="dc059-114">Message Text</span></span>|<span data-ttu-id="dc059-115">El identificador formado por varias partes "%.\*ls" no se pudo enlazar.</span><span class="sxs-lookup"><span data-stu-id="dc059-115">The multi-part identifier "%.\*ls" could not be bound.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dc059-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="dc059-116">Explanation</span></span>  
 <span data-ttu-id="dc059-117">El nombre de una entidad en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se conoce como su *identificador*.</span><span class="sxs-lookup"><span data-stu-id="dc059-117">The name of an entity in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is referred to as its *identifier*.</span></span> <span data-ttu-id="dc059-118">Los identificadores se usan siempre que se hace referencia a entidades, por ejemplo, al especificar nombres de tabla y de columna en una consulta.</span><span class="sxs-lookup"><span data-stu-id="dc059-118">You use identifiers whenever you reference entities, for example, by specifying column and table names in a query.</span></span> <span data-ttu-id="dc059-119">Un identificador formado por varias partes contiene uno o varios calificadores como prefijo del identificador.</span><span class="sxs-lookup"><span data-stu-id="dc059-119">A multi-part identifier contains one or more qualifiers as a prefix for the identifier.</span></span> <span data-ttu-id="dc059-120">Por ejemplo, un identificador de tabla puede tener como prefijo calificadores como el nombre de la base de datos y el nombre del esquema que la contienen, o un identificador de columna puede tener como prefijo calificadores como el nombre o el alias de una tabla.</span><span class="sxs-lookup"><span data-stu-id="dc059-120">For example, a table identifier may be prefixed with qualifiers such as the database name and schema name in which the table is contained, or a column identifier may be prefixed with qualifiers such as a table name or table alias.</span></span>  
  
 <span data-ttu-id="dc059-121">El error 4104 indica que el identificador formado por varias partes especificado no se pudo asignar a una entidad existente.</span><span class="sxs-lookup"><span data-stu-id="dc059-121">Error 4104 indicates that the specified multi-part identifier could not be mapped to an existing entity.</span></span> <span data-ttu-id="dc059-122">Este error se puede devolver en las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc059-122">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="dc059-123">El calificador proporcionado como prefijo para un nombre de columna no corresponde a ningún nombre de alias o tabla utilizado en la consulta.</span><span class="sxs-lookup"><span data-stu-id="dc059-123">The qualifier supplied as a prefix for a column name does not correspond to any table or alias name used in the query.</span></span>  
  
     <span data-ttu-id="dc059-124">Por ejemplo, la instrucción siguiente utiliza un alias de tabla (`Dept`) como prefijo de columna, pero no se hace referencia al alias de tabla en la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="dc059-124">For example, the following statement uses a table alias (`Dept`) as a column prefix, but the table alias is not referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department;  
    ```  
  
     <span data-ttu-id="dc059-125">En las instrucciones siguientes, se especifica un identificador de columna formado por varias partes `TableB.KeyCol` en la cláusula WHERE como parte de una condición JOIN entre dos tablas; sin embargo, no se hace referencia explícita a `TableB` en la consulta.</span><span class="sxs-lookup"><span data-stu-id="dc059-125">In the following statements, a multi-part column identifier `TableB.KeyCol` is specified in the WHERE clause as part of a JOIN condition between two tables, however, `TableB` is not explicitly referenced in the query.</span></span>  
  
    ```  
    DELETE FROM TableA WHERE TableA.KeyCol = TableB.KeyCol;  
    ```  
  
    ```  
    SELECT 'X' FROM TableA WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="dc059-126">En la cláusula FROM se proporciona un nombre de alias para la tabla, pero el calificador proporcionado para una columna es el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="dc059-126">An alias name for the table is supplied in the FROM clause, but the qualifier supplied for a column is the table name.</span></span> <span data-ttu-id="dc059-127">Por ejemplo, la instrucción siguiente utiliza el nombre de tabla `Department` como prefijo de columna; sin embargo, la tabla tiene un alias (`Dept`) al que se hace referencia en la cláusula FROM.</span><span class="sxs-lookup"><span data-stu-id="dc059-127">For example, the following statement uses the table name `Department` as the column prefix; however, the table has an alias (`Dept`) referenced in the FROM clause.</span></span>  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department AS Dept;  
    ```  
  
     <span data-ttu-id="dc059-128">Cuando se utiliza un alias, el nombre de la tabla no se puede utilizar en ninguna otra parte de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="dc059-128">When an alias is used, the table name cannot be used elsewhere in the statement.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dc059-129">no puede determinar si el identificador formado por varias partes hace referencia a una columna con una tabla como prefijo o a una propiedad de un tipo de datos definido por el usuario (UDT) de CLR con una columna como prefijo.</span><span class="sxs-lookup"><span data-stu-id="dc059-129">is unable to determine if the multi-part identifier refers to a column prefixed by a table or to a property of a CLR user-defined data type (UDT) prefixed by a column.</span></span> <span data-ttu-id="dc059-130">Esto sucede porque a las propiedades de las columnas UDT se hace referencia utilizando el separador punto (.) entre el nombre de la columna y el nombre de la propiedad del mismo modo que un nombre de columna tiene como prefijo un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="dc059-130">This happens because properties of UDT columns are referenced by using the period separator (.) between the column name and the property name in the same way that a column name is prefixed with a table name.</span></span> <span data-ttu-id="dc059-131">En el siguiente ejemplo se crean dos tablas: `a` y `b`.</span><span class="sxs-lookup"><span data-stu-id="dc059-131">The following example creates two tables, `a` and `b`.</span></span> <span data-ttu-id="dc059-132">La tabla `b` contiene la columna `a`, que usa un UDT `dbo.myudt2` de CLR como tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="dc059-132">Table `b` contains column `a`, which uses a CLR UDT `dbo.myudt2` as its data type.</span></span> <span data-ttu-id="dc059-133">La instrucción SELECT contiene un identificador `a.c2` formado por varias partes.</span><span class="sxs-lookup"><span data-stu-id="dc059-133">The SELECT statement contains a multi-part identifier `a.c2`.</span></span>  
  
    ```  
    CREATE TABLE a (c2 int);   
    GO  
    ```  
  
    ```  
    CREATE TABLE b (a dbo.myudt2);   
    GO  
    ```  
  
    ```  
    SELECT a.c2 FROM a, b;   
    ```  
  
     <span data-ttu-id="dc059-134">Suponiendo que el UDT `myudt2` no tiene una propiedad denominada `c2`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no puede determinar si el identificador `a.c2` hace referencia a la columna `c2` de la tabla `a` o a la columna `a`, propiedad `c2` de la tabla `b`.</span><span class="sxs-lookup"><span data-stu-id="dc059-134">Assuming that the UDT `myudt2` does not have a property named `c2`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot determine whether identifier `a.c2`refers to column `c2` in table `a` or to the column `a`, property `c2` in table `b`.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc059-135">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="dc059-135">User Action</span></span>  
  
-   <span data-ttu-id="dc059-136">Haga coincidir los prefijos de columna con los nombres de tabla o con los nombres de alias especificados en la cláusula FROM de la consulta.</span><span class="sxs-lookup"><span data-stu-id="dc059-136">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="dc059-137">Si se define un alias para un nombre de tabla en la cláusula FROM, solo puede utilizar el alias como calificador para las columnas asociadas a esa tabla.</span><span class="sxs-lookup"><span data-stu-id="dc059-137">If an alias is defined for a table name in the FROM clause, you can only use the alias as a qualifier for columns associated with that table.</span></span>  
  
     <span data-ttu-id="dc059-138">Las instrucciones anteriores que hacen referencia a la tabla `HumanResources.Department` se pueden corregir de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc059-138">The statements above that reference the `HumanResources.Department` table can be corrected as follows:</span></span>  
  
    ```  
    SELECT Dept.Name FROM HumanResources.Department AS Dept;  
    GO  
    ```  
  
    ```  
    SELECT Department.Name FROM HumanResources.Department;  
    GO  
    ```  
  
-   <span data-ttu-id="dc059-139">Asegúrese de que todas las tablas se especifican en la consulta y que las condiciones JOIN entre las tablas se especifican correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc059-139">Ensure that all tables are specified in the query and that the JOIN conditions between tables are specified correctly.</span></span> <span data-ttu-id="dc059-140">La instrucción DELETE anterior se puede corregir de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc059-140">The DELETE statement above can be corrected as follows:</span></span>  
  
    ```  
    DELETE FROM dbo.TableA  
    WHERE TableA.KeyCol = (SELECT TableB.KeyCol   
                            FROM TableB   
                            WHERE TableA.KeyCol = TableB.KeyCol);  
    GO  
    ```  
  
     <span data-ttu-id="dc059-141">La instrucción SELECT anterior para `TableA` se puede corregir de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc059-141">The SELECT statement above for `TableA` can be corrected as follows:</span></span>  
  
    ```  
    SELECT 'X' FROM TableA, TableB WHERE TableB.KeyCol = TableA.KeyCol;  
    ```  
  
     <span data-ttu-id="dc059-142">or</span><span class="sxs-lookup"><span data-stu-id="dc059-142">or</span></span>  
  
    ```  
    SELECT 'X' FROM TableA INNER JOIN TableB ON TableB.KeyCol = TableA.KeyCol;  
    ```  
  
-   <span data-ttu-id="dc059-143">Utilice nombres únicos y definidos claramente para los identificadores.</span><span class="sxs-lookup"><span data-stu-id="dc059-143">Use unique, clearly defined names for identifiers.</span></span> <span data-ttu-id="dc059-144">De este modo, el código es más fácil de leer y mantener, y también se reduce al mínimo el riesgo de que haya referencias ambiguas a varias entidades.</span><span class="sxs-lookup"><span data-stu-id="dc059-144">Doing so makes your code easier to read and maintain, and it also minimizes the risk of ambiguous references to multiple entities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc059-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc059-145">See Also</span></span>  
 <span data-ttu-id="dc059-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="dc059-146">[MSSQLSERVER_107](mssqlserver-107-database-engine-error.md) </span></span>  
 [<span data-ttu-id="dc059-147">Identificadores de base de datos</span><span class="sxs-lookup"><span data-stu-id="dc059-147">Database Identifiers</span></span>](../databases/database-identifiers.md)  
  
  
