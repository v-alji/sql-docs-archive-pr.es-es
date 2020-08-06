---
title: Resumir o agregar valores para todas las filas de una tabla (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- aggregate functions [SQL Server], summarizing query results
ms.assetid: f5af876e-f937-4110-ba09-07999c35a699
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5c4d80c8ab2b811b8e796f0a37b2180a2866c332
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747855"
---
# <a name="summarize-or-aggregate-values-for-all-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="36de9-102">Resumir o agregar los valores de todas las filas de una tabla (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="36de9-102">Summarize or Aggregate Values for All Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="36de9-103">Mediante una función de agregado, puede crear un resumen de todos los valores de una tabla.</span><span class="sxs-lookup"><span data-stu-id="36de9-103">Using an aggregate function, you can create a summary for all the values in a table.</span></span> <span data-ttu-id="36de9-104">Por ejemplo, se puede crear una consulta como la que se muestra a continuación para mostrar el precio total de todos los libros de la tabla `titles` :</span><span class="sxs-lookup"><span data-stu-id="36de9-104">For example, you can create a query such as the following to display the total price for all books in the `titles` table:</span></span>  
  
```  
SELECT SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="36de9-105">Puede crear varios tipos de agregaciones en la misma consulta utilizando funciones de agregado con varias columnas.</span><span class="sxs-lookup"><span data-stu-id="36de9-105">You can create multiple aggregations in the same query by using aggregate functions with more than one column.</span></span> <span data-ttu-id="36de9-106">Puede crear, por ejemplo, una consulta que calcule el total de la columna `price` y el valor medio de la columna `discount` .</span><span class="sxs-lookup"><span data-stu-id="36de9-106">For example, you can create a query that calculates the total of the `price` column and the average of the `discount` column.</span></span>  
  
 <span data-ttu-id="36de9-107">También se puede agregar la misma columna de maneras diferentes (como calculando el total, contando y calculando el promedio) en la misma consulta.</span><span class="sxs-lookup"><span data-stu-id="36de9-107">You can also aggregate the same column in different ways (such as totaling, counting, and averaging) in the same query.</span></span> <span data-ttu-id="36de9-108">Por ejemplo, la siguiente consulta calcula el promedio y resume la columna `price` de la tabla `titles` :</span><span class="sxs-lookup"><span data-stu-id="36de9-108">For example, the following query averages and summarizes the `price` column from the `titles` table:</span></span>  
  
```  
SELECT AVG(price), SUM(price)  
FROM titles  
```  
  
 <span data-ttu-id="36de9-109">Si agrega una condición de búsqueda, puede agregar el subconjunto de filas que satisfacen esa condición.</span><span class="sxs-lookup"><span data-stu-id="36de9-109">If you add a search condition, you can aggregate the subset of rows that meet that condition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36de9-110">También puede contar todas las filas de la tabla o las que satisfacen una condición específica.</span><span class="sxs-lookup"><span data-stu-id="36de9-110">You can also count all the rows in the table or the ones that meet a specific condition.</span></span> <span data-ttu-id="36de9-111">Para detalles, consulte [Contar las filas de una tabla &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="36de9-111">For details, see [Count Rows in a Table &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="36de9-112">Cuando se crea un único valor de agregación para todas las filas de una tabla, solo se muestran los propios valores de agregado.</span><span class="sxs-lookup"><span data-stu-id="36de9-112">When you create a single aggregation value for all rows in a table, you display only the aggregate values themselves.</span></span> <span data-ttu-id="36de9-113">Por ejemplo, si calcula el total del valor de la columna `price` de la tabla `titles` , no se mostrarán los títulos individuales, los nombres de las editoriales, etc.</span><span class="sxs-lookup"><span data-stu-id="36de9-113">For example, if you are totaling the value of the `price` column of the `titles` table, you would not also display individual titles, publisher names, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36de9-114">Si calcula subtotales (es decir, si crea grupos) puede mostrar los valores de columna de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="36de9-114">If you are subtotaling - that is, creating groups - you can display column values for each group.</span></span> <span data-ttu-id="36de9-115">Para detalles, consulte [Agrupar filas en los resultados de la consulta &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="36de9-115">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
### <a name="to-aggregate-values-for-all-rows"></a><span data-ttu-id="36de9-116">Para agregar valores de todas las filas</span><span class="sxs-lookup"><span data-stu-id="36de9-116">To aggregate values for all rows</span></span>  
  
1.  <span data-ttu-id="36de9-117">Asegúrese de que la tabla que desea agregar ya esté presente en el panel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="36de9-117">Be sure the table you want to aggregate is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="36de9-118">Haga clic con el botón derecho en el fondo del panel Diagrama y, a continuación, elija **Agrupar por** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="36de9-118">Right-click the background of the Diagram pane, then choose **Group By** from the shortcut menu.</span></span> <span data-ttu-id="36de9-119">El [Diseñador de consultas y vistas](query-and-view-designer-tools-visual-database-tools.md) agrega una columna **Agrupar por** a la cuadrícula en el panel criterios.</span><span class="sxs-lookup"><span data-stu-id="36de9-119">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="36de9-120">Agregue la columna que desee al panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="36de9-120">Add the column you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="36de9-121">Asegúrese de que la columna está marcada para el resultado.</span><span class="sxs-lookup"><span data-stu-id="36de9-121">Be sure that the column is marked for output.</span></span>  
  
     <span data-ttu-id="36de9-122">El Diseñador de consultas y vistas asigna automáticamente un alias a la columna que va a resumir.</span><span class="sxs-lookup"><span data-stu-id="36de9-122">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="36de9-123">Puede sustituir este alias por otro más significativo.</span><span class="sxs-lookup"><span data-stu-id="36de9-123">You can replace this alias with a more meaningful one.</span></span> <span data-ttu-id="36de9-124">Para detalles, consulte [Crear alias de columna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="36de9-124">For details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="36de9-125">En la columna de cuadrícula **Agrupar por**, seleccione la función de agregado correspondiente, como: **Sum**, **Avg**, **Min**, **Max** o **Count**.</span><span class="sxs-lookup"><span data-stu-id="36de9-125">In the **Group By** grid column, select the appropriate aggregate function, such as: **Sum**, **Avg**, **Min**, **Max**, **Count**.</span></span> <span data-ttu-id="36de9-126">Si solo desea agregar filas únicas en el conjunto de resultados, elija una función de agregado con las opciones DISTINCT, como **Min Distinct**.</span><span class="sxs-lookup"><span data-stu-id="36de9-126">If you want to aggregate only unique rows in the result set, choose an aggregate function with the DISTINCT options, such as **Min Distinct**.</span></span> <span data-ttu-id="36de9-127">No elija **Group By**, **Expression**o **Where**, ya que estas opciones no se aplican cuando se agregan todas las filas.</span><span class="sxs-lookup"><span data-stu-id="36de9-127">Do not choose **Group By**, **Expression**, or **Where**, because those options do not apply when you are aggregating all rows.</span></span>  
  
     <span data-ttu-id="36de9-128">El Diseñador de consultas y vistas sustituye el nombre de columna en la instrucción del [panel SQL](sql-pane-visual-database-tools.md) por la función de agregado que especifique.</span><span class="sxs-lookup"><span data-stu-id="36de9-128">The Query and View Designer replaces the column name in the statement in the [SQL pane](sql-pane-visual-database-tools.md) with the aggregate function that you specify.</span></span> <span data-ttu-id="36de9-129">Por ejemplo, la instrucción SQL podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="36de9-129">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT SUM(price)  
    FROM titles  
    ```  
  
5.  <span data-ttu-id="36de9-130">Si desea crear más de una agregación en la consulta repita los pasos 3 y 4.</span><span class="sxs-lookup"><span data-stu-id="36de9-130">If you want to create more than one aggregation in the query, repeat steps 3 and 4.</span></span>  
  
     <span data-ttu-id="36de9-131">Cuando se agrega otra columna a la lista de resultados de la consulta o la lista de ordenación, el Diseñador de consultas y vistas incluye automáticamente el término **Group By** en la columna **Agrupar por** de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="36de9-131">When you add another column to the query output list or order by list, the Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span> <span data-ttu-id="36de9-132">Seleccione la función de agregado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="36de9-132">Select the appropriate aggregate function.</span></span>  
  
6.  <span data-ttu-id="36de9-133">Agregue condiciones de búsqueda, si es necesario, para especificar el subconjunto de filas que desea resumir.</span><span class="sxs-lookup"><span data-stu-id="36de9-133">Add search conditions, if any, to specify the subset of rows you want to summarize.</span></span>  
  
 <span data-ttu-id="36de9-134">Cuando ejecute la consulta, en el panel Resultados se mostrarán las agregaciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="36de9-134">When you execute the query, the Results pane displays the aggregations that you specified.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36de9-135">El Diseñador de consultas y vistas mantiene las funciones de agregado como parte de la instrucción SQL en el panel SQL hasta que se desactiva explícitamente el modo Agrupar por.</span><span class="sxs-lookup"><span data-stu-id="36de9-135">The Query and View Designer maintains aggregate functions as part of the SQL statement in the SQL pane until you explicitly turn off Group By mode.</span></span> <span data-ttu-id="36de9-136">Por tanto, si se modifica una columna asignándole otro tipo distinto o cambiando las tablas o los objetos con valores de tablas que aparecen en el panel Diagrama, la consulta resultante podría incluir funciones de agregado no válidas.</span><span class="sxs-lookup"><span data-stu-id="36de9-136">Therefore, if you modify your query by changing its type or by changing which tables or table-valued objects are present in the Diagram pane, the resulting query might include invalid aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36de9-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36de9-137">See Also</span></span>  
 <span data-ttu-id="36de9-138">[Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="36de9-138">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="36de9-139">Resumir los resultados de una consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="36de9-139">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
