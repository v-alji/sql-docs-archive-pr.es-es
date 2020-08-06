---
title: MSSQLSERVER_207 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 207 (Database Engine error)
ms.assetid: d1ab00c7-0331-437a-84fe-bae53b82feec
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd6044c08ecd5a73f539bfbc1139d6257c2db9d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745315"
---
# <a name="mssqlserver_207"></a><span data-ttu-id="31fbf-102">MSSQLSERVER_207</span><span class="sxs-lookup"><span data-stu-id="31fbf-102">MSSQLSERVER_207</span></span>
    
## <a name="details"></a><span data-ttu-id="31fbf-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="31fbf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31fbf-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="31fbf-104">Product Name</span></span>|<span data-ttu-id="31fbf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="31fbf-105">SQL Server</span></span>|  
|<span data-ttu-id="31fbf-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="31fbf-106">Event ID</span></span>|<span data-ttu-id="31fbf-107">207</span><span class="sxs-lookup"><span data-stu-id="31fbf-107">207</span></span>|  
|<span data-ttu-id="31fbf-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="31fbf-108">Event Source</span></span>|<span data-ttu-id="31fbf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="31fbf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="31fbf-110">Componente</span><span class="sxs-lookup"><span data-stu-id="31fbf-110">Component</span></span>|<span data-ttu-id="31fbf-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="31fbf-111">SQLEngine</span></span>|  
|<span data-ttu-id="31fbf-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="31fbf-112">Symbolic Name</span></span>|<span data-ttu-id="31fbf-113">SQ_BADCOL</span><span class="sxs-lookup"><span data-stu-id="31fbf-113">SQ_BADCOL</span></span>|  
|<span data-ttu-id="31fbf-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="31fbf-114">Message Text</span></span>|<span data-ttu-id="31fbf-115">El nombre de columna '%.\*ls' no es válido.</span><span class="sxs-lookup"><span data-stu-id="31fbf-115">Invalid column name '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="31fbf-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="31fbf-116">Explanation</span></span>  
 <span data-ttu-id="31fbf-117">Este error de consulta puede deberse a uno de los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="31fbf-117">This query error can be caused by one of the following problems.</span></span>  
  
-   <span data-ttu-id="31fbf-118">El nombre de la columna no se ha escrito correctamente o la columna no existe en ninguna de las tablas especificadas.</span><span class="sxs-lookup"><span data-stu-id="31fbf-118">The column name is misspelled or the column does not exist in any of the specified tables.</span></span>  
  
-   <span data-ttu-id="31fbf-119">La intercalación de la base de datos distingue entre mayúsculas y minúsculas, y la grafía del nombre de columna especificado en la consulta no coincide con el de la columna definida en la tabla.</span><span class="sxs-lookup"><span data-stu-id="31fbf-119">The collation of the database is case-sensitive and the case of the column name specified in the query does not match the case of the column defined in the table.</span></span> <span data-ttu-id="31fbf-120">Por ejemplo, cuando una columna se define en una tabla como **LastName** y la base de datos usa una intercalación con distinción entre mayúsculas y minúsculas, las consultas que hacen referencia a la columna como **Lastname** o como **lastname** harán que se devuelva el error 207 porque el nombre de columna no coincide.</span><span class="sxs-lookup"><span data-stu-id="31fbf-120">For example, when a column is defined in a table as **LastName** and the database uses a case-sensitive collation, queries that refer to the column as **Lastname** or **lastname** will cause error 207 to return because the column name does not match.</span></span>  
  
-   <span data-ttu-id="31fbf-121">Otras cláusulas como WHERE o GROUP BY hacen referencia a un alias de columna, definido en la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="31fbf-121">A column alias, defined in the SELECT clause, is referenced in another clause such as a WHERE or GROUP BY clause.</span></span> <span data-ttu-id="31fbf-122">Por ejemplo, la siguiente consulta define el alias de columna `Year` en la cláusula SELECT y hace referencia a él en la cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="31fbf-122">For example, the following query defines the column alias `Year` in the SELECT clause and refers to it in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year, SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY Year;  
    ```  
  
     <span data-ttu-id="31fbf-123">Debido al orden en el que las cláusulas de consulta se procesan de manera lógica, el ejemplo devuelve el error 207.</span><span class="sxs-lookup"><span data-stu-id="31fbf-123">Due to the order in which query clauses are logically processed, the example returns error 207.</span></span> <span data-ttu-id="31fbf-124">El orden de procesamiento es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="31fbf-124">The processing order is as follows:</span></span>  
  
    1.  <span data-ttu-id="31fbf-125">FROM</span><span class="sxs-lookup"><span data-stu-id="31fbf-125">FROM</span></span>  
  
    2.  <span data-ttu-id="31fbf-126">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="31fbf-126">ON</span></span>  
  
    3.  <span data-ttu-id="31fbf-127">JOIN</span><span class="sxs-lookup"><span data-stu-id="31fbf-127">JOIN</span></span>  
  
    4.  <span data-ttu-id="31fbf-128">WHERE</span><span class="sxs-lookup"><span data-stu-id="31fbf-128">WHERE</span></span>  
  
    5.  <span data-ttu-id="31fbf-129">GROUP BY</span><span class="sxs-lookup"><span data-stu-id="31fbf-129">GROUP BY</span></span>  
  
    6.  <span data-ttu-id="31fbf-130">WITH CUBE o WITH ROLLUP</span><span class="sxs-lookup"><span data-stu-id="31fbf-130">WITH CUBE or WITH ROLLUP</span></span>  
  
    7.  <span data-ttu-id="31fbf-131">HAVING</span><span class="sxs-lookup"><span data-stu-id="31fbf-131">HAVING</span></span>  
  
    8.  <span data-ttu-id="31fbf-132">SELECT</span><span class="sxs-lookup"><span data-stu-id="31fbf-132">SELECT</span></span>  
  
    9. <span data-ttu-id="31fbf-133">DISTINCT</span><span class="sxs-lookup"><span data-stu-id="31fbf-133">DISTINCT</span></span>  
  
    10. <span data-ttu-id="31fbf-134">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="31fbf-134">ORDER BY</span></span>  
  
    11. <span data-ttu-id="31fbf-135">TOP</span><span class="sxs-lookup"><span data-stu-id="31fbf-135">TOP</span></span>  
  
     <span data-ttu-id="31fbf-136">Puesto que un alias de columna no se define hasta que se procesa la cláusula SELECT, no se conoce el nombre de alias cuando se procesa la cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="31fbf-136">Because a column alias is not defined until the SELECT clause is processed, the alias name is unknown when the GROUP BY clause is processed.</span></span>  
  
-   <span data-ttu-id="31fbf-137">La instrucción MERGE genera este error cuando la cláusula *<merge_matched>* hace referencia a las columnas de la tabla de origen, pero la tabla de origen de la cláusula WHEN NOT MATCHED BY SOURCE no devuelve ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="31fbf-137">The MERGE statement raises this error when the *<merge_matched>* clause references columns in the source table but no rows are returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="31fbf-138">El error ocurre porque no se puede obtener acceso a las columnas de la tabla de origen cuando no se devuelven filas a la consulta.</span><span class="sxs-lookup"><span data-stu-id="31fbf-138">The error occurs because the columns in the source table cannot be accessed when no rows are returned to the query.</span></span> <span data-ttu-id="31fbf-139">Por ejemplo, la cláusula `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` puede hacer que la instrucción genere un error si `Col1` en la tabla de origen es inaccesible.</span><span class="sxs-lookup"><span data-stu-id="31fbf-139">For example, the clause `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = SourceTable.Col1` may cause the statement to fail if `Col1` in the source table is inaccessible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="31fbf-140">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="31fbf-140">User Action</span></span>  
 <span data-ttu-id="31fbf-141">Compruebe la información siguiente y corrija la instrucción según corresponda.</span><span class="sxs-lookup"><span data-stu-id="31fbf-141">Verify the following information and correct the statement as appropriate.</span></span>  
  
-   <span data-ttu-id="31fbf-142">El nombre de columna existe en la tabla y está correctamente escrito.</span><span class="sxs-lookup"><span data-stu-id="31fbf-142">The column name exists in the table and is spelled correctly.</span></span> <span data-ttu-id="31fbf-143">En el siguiente ejemplo, se consulta a la vista de catálogo **sys.columns** para que devuelva todos los nombres de columna para una tabla determinada.</span><span class="sxs-lookup"><span data-stu-id="31fbf-143">The following example queries the **sys.columns** catalog view to return all column names for a given table.</span></span>  
  
    ```  
    SELECT name FROM sys.columns WHERE object_id = OBJECT_ID('schema_name.table_name');  
    ```  
  
-   <span data-ttu-id="31fbf-144">La distinción entre mayúsculas y minúsculas de la intercalación de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="31fbf-144">The case sensitivity of the database collation.</span></span> <span data-ttu-id="31fbf-145">La siguiente instrucción devuelve la intercalación de la base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="31fbf-145">The following statement returns the collation of the specified database.</span></span>  
  
    ```  
    SELECT collation_name FROM sys.databases WHERE name = 'database_name';  
    ```  
  
     <span data-ttu-id="31fbf-146">La abreviatura CS en el nombre de la intercalación indica que distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="31fbf-146">The abbreviation CS in the collation name indicates the collation is case-sensitive.</span></span> <span data-ttu-id="31fbf-147">Por ejemplo, Latin1_General_CS_AS es una intercalación que distingue mayúsculas de minúsculas que distingue acentos.</span><span class="sxs-lookup"><span data-stu-id="31fbf-147">For example, Latin1_General_CS_AS is a case-sensitive and accent-sensitive collation.</span></span> <span data-ttu-id="31fbf-148">Modifique el nombre de columna para que la grafía coincida con el nombre de columna definido en la tabla.</span><span class="sxs-lookup"><span data-stu-id="31fbf-148">Modify the column name to match the case of the column name as it is defined in the table.</span></span>  
  
-   <span data-ttu-id="31fbf-149">La referencia a un alias de columna no es correcta.</span><span class="sxs-lookup"><span data-stu-id="31fbf-149">A column alias is referenced incorrectly.</span></span> <span data-ttu-id="31fbf-150">Modifique la instrucción repitiendo la expresión que define el alias en la cláusula apropiada o usando una tabla derivada.</span><span class="sxs-lookup"><span data-stu-id="31fbf-150">Modify the statement by repeating the expression that defines the alias in the appropriate clause or by using a derived table.</span></span> <span data-ttu-id="31fbf-151">El siguiente ejemplo repite las expresiones que define el alias `Year` en la cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="31fbf-151">The following example repeats the expressions that define the `Year` alias in the GROUP BY clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT DATEPART(yyyy,OrderDate) AS Year ,SUM(TotalDue) AS Total  
    FROM Sales.SalesOrderHeader  
    GROUP BY DATEPART(yyyy,OrderDate);  
    ```  
  
     <span data-ttu-id="31fbf-152">El siguiente ejemplo usa una tabla derivada para que otras cláusulas de la consulta puedan disponer del nombre de alias.</span><span class="sxs-lookup"><span data-stu-id="31fbf-152">The following example uses a derived table to make the alias name available to other clauses in the query.</span></span> <span data-ttu-id="31fbf-153">Tenga en cuenta que el alias `Year` se define en la cláusula FROM, que se procesa en primer lugar, y por lo tanto otras cláusulas de la consulta pueden disponer de él.</span><span class="sxs-lookup"><span data-stu-id="31fbf-153">Notice that the alias `Year` is defined in the FROM clause, which is processed first, and so makes the alias available for use in other clauses in the query.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT d.Year, SUM(TotalDue) AS Total  
    FROM (SELECT DATEPART(yyyy,OrderDate) AS Year, TotalDue  
          FROM Sales.SalesOrderHeader)AS d  
    GROUP BY Year;  
    ```  
  
-   <span data-ttu-id="31fbf-154">La cláusula WHEN NOT MATCHED BY SOURCE de la instrucción MERGE hace referencia a un valor al que se puede tener acceso.</span><span class="sxs-lookup"><span data-stu-id="31fbf-154">The WHEN NOT MATCHED BY SOURCE clause in the MERGE statement refers to a value that can be accessed.</span></span> <span data-ttu-id="31fbf-155">Modifique la instrucción MERGE para que la tabla de origen devuelva al menos una fila en la cláusula WHEN NOT MATCHED BY SOURCE.</span><span class="sxs-lookup"><span data-stu-id="31fbf-155">Modify the MERGE statement so that at least one row is returned by the source table in the WHEN NOT MATCHED BY SOURCE clause.</span></span> <span data-ttu-id="31fbf-156">Por ejemplo, puede que tenga que agregar o revisar la condición de búsqueda especificada para la cláusula.</span><span class="sxs-lookup"><span data-stu-id="31fbf-156">For example, you might need to add or revise the search condition specified for the clause.</span></span> <span data-ttu-id="31fbf-157">De manera alternativa, puede modificar la cláusula para que especifique un valor que no haga referencia a la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="31fbf-157">Alternatively, you can modify the clause to specify a value that does not reference the source table.</span></span> <span data-ttu-id="31fbf-158">Por ejemplo, `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span><span class="sxs-lookup"><span data-stu-id="31fbf-158">For example, `WHEN NOT MATCHED BY SOURCE THEN UPDATE SET TargetTable.Col1 = <expression, or other available value>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31fbf-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31fbf-159">See Also</span></span>  
 <span data-ttu-id="31fbf-160">[MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="31fbf-160">[MERGE &#40;Transact-SQL&#41;](/sql/t-sql/statements/merge-transact-sql) </span></span>  
 <span data-ttu-id="31fbf-161">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="31fbf-161">[FROM &#40;Transact-SQL&#41;](/sql/t-sql/queries/from-transact-sql) </span></span>  
 <span data-ttu-id="31fbf-162">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="31fbf-162">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="31fbf-163">UPDATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="31fbf-163">UPDATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/update-transact-sql)  
  
  
