---
title: Agrupar filas en los resultados de la consulta (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing table subsets
- grouping rows
- grouping query results
ms.assetid: b07082d5-4d55-4903-9af9-4c470554c6d3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52de25c86425d95f5917d89c8a3f4fec8939fb16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673976"
---
# <a name="group-rows-in-query-results-visual-database-tools"></a><span data-ttu-id="7f234-102">Agrupar filas en los resultados de la consulta (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7f234-102">Group Rows in Query Results (Visual Database Tools)</span></span>
  <span data-ttu-id="7f234-103">Si desea crear subtotales o mostrar otra información de resumen para los subconjuntos de una tabla, debe crear grupos mediante una consulta de funciones agregadas.</span><span class="sxs-lookup"><span data-stu-id="7f234-103">If you want to create subtotals or show other summary information for subsets of a table, you create groups using an aggregate query.</span></span> <span data-ttu-id="7f234-104">Cada grupo resume los datos para todas las filas de la tabla que tienen el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="7f234-104">Each group summarizes the data for all the rows in the table that have the same value.</span></span>  
  
 <span data-ttu-id="7f234-105">Por ejemplo, es posible que desee ver el precio medio de un libro en la tabla `titles` , pero con los resultados desglosados por editorial.</span><span class="sxs-lookup"><span data-stu-id="7f234-105">For example, you might want to see the average price of a book in the `titles` table, but break the results down by publisher.</span></span> <span data-ttu-id="7f234-106">Para ello, agrupe la consulta por editorial (por ejemplo, `pub_id`).</span><span class="sxs-lookup"><span data-stu-id="7f234-106">To do so, you group the query by publisher (for example, `pub_id`).</span></span> <span data-ttu-id="7f234-107">El resultado de la consulta podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="7f234-107">The resulting query output might look like this:</span></span>  
  
 <span data-ttu-id="7f234-108">![Resultados de la consulta: precio medio agrupado por publicador](../../database-engine/media//dv3w9e1.gif "Resultados de la consulta: precio medio agrupado por publicador")</span><span class="sxs-lookup"><span data-stu-id="7f234-108">![Query results: average price grouped by publisher](../../database-engine/media//dv3w9e1.gif "Query results: average price grouped by publisher")</span></span>  
  
 <span data-ttu-id="7f234-109">Cuando se agrupan datos, solo se pueden mostrar valores resumidos o agrupados, como:</span><span class="sxs-lookup"><span data-stu-id="7f234-109">When you group data, you can display only summary or grouped data, such as:</span></span>  
  
-   <span data-ttu-id="7f234-110">Los valores de las columnas agrupadas (aquellos que aparecen en la cláusula GROUP BY).</span><span class="sxs-lookup"><span data-stu-id="7f234-110">The values of the grouped columns (those that appear in the GROUP BY clause).</span></span> <span data-ttu-id="7f234-111">En el ejemplo anterior, `pub_id` es la columna agrupada.</span><span class="sxs-lookup"><span data-stu-id="7f234-111">In the example above, `pub_id` is the grouped column.</span></span>  
  
-   <span data-ttu-id="7f234-112">Valores generados por funciones de agregado como SUM( ) y AVG( ).</span><span class="sxs-lookup"><span data-stu-id="7f234-112">Values produced by aggregate functions such as SUM( ) and AVG( ).</span></span> <span data-ttu-id="7f234-113">En el ejemplo anterior, la segunda columna se genera usando la función AVG( ) con la columna `price` .</span><span class="sxs-lookup"><span data-stu-id="7f234-113">In the example above, the second column is produced by using the AVG( ) function with the `price` column.</span></span>  
  
 <span data-ttu-id="7f234-114">No se pueden mostrar valores de filas individuales.</span><span class="sxs-lookup"><span data-stu-id="7f234-114">You cannot display values from individual rows.</span></span> <span data-ttu-id="7f234-115">Por ejemplo, si agrupa únicamente por editorial, no podrá mostrar tampoco los títulos individuales en la consulta.</span><span class="sxs-lookup"><span data-stu-id="7f234-115">For example, if you group only by publisher, you cannot also display individual titles in the query.</span></span> <span data-ttu-id="7f234-116">Por tanto, si se agregan columnas al resultado de la consulta, el [Diseñador de consultas y vistas](visual-database-tools.md) las agregará automáticamente a la cláusula GROUP BY de la instrucción en el [panel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-116">Therefore, if you add columns to the query output, the [Query and View Designer](visual-database-tools.md) automatically adds them to the GROUP BY clause of the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span> <span data-ttu-id="7f234-117">Si, en su lugar, se desea agregar una columna, se puede especificar una función de agregado para esa columna.</span><span class="sxs-lookup"><span data-stu-id="7f234-117">If you want a column to be aggregated instead, you can specify an aggregate function for that column.</span></span>  
  
 <span data-ttu-id="7f234-118">Si utiliza varias columnas para la agrupación, en cada grupo de la consulta se muestran los valores de agregado de todas las columnas de agrupación.</span><span class="sxs-lookup"><span data-stu-id="7f234-118">If you group by more than one column, each group in the query shows the aggregate values for all grouping columns.</span></span>  
  
 <span data-ttu-id="7f234-119">Por ejemplo, la siguiente consulta de la tabla `titles` agrupa por editorial (`pub_id`) y por tipo de libro (`type`).</span><span class="sxs-lookup"><span data-stu-id="7f234-119">For example, the following query against the `titles` table groups by publisher (`pub_id`) and also by book type (`type`).</span></span> <span data-ttu-id="7f234-120">Los resultados de la consulta se ordenan por editorial e incluyen información de resumen para cada tipo de libro diferente producido por la editorial:</span><span class="sxs-lookup"><span data-stu-id="7f234-120">The query results are ordered by publisher and show summary information for each different type of book that the publisher produces:</span></span>  
  
```  
SELECT pub_id, type, SUM(price) Total_price  
FROM titles  
GROUP BY pub_id, type  
```  
  
 <span data-ttu-id="7f234-121">El resultado de la consulta podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="7f234-121">The resulting output might look like this:</span></span>  
  
 <span data-ttu-id="7f234-122">![Resultados de la consulta: precio agrupado por publicador y tipo](../../database-engine/media//dv3w9e2.gif "Resultados de la consulta: precio agrupado por publicador y tipo")</span><span class="sxs-lookup"><span data-stu-id="7f234-122">![Query results: price grouped by publisher and type](../../database-engine/media//dv3w9e2.gif "Query results: price grouped by publisher and type")</span></span>  
  
### <a name="to-group-rows"></a><span data-ttu-id="7f234-123">Para agrupar filas</span><span class="sxs-lookup"><span data-stu-id="7f234-123">To group rows</span></span>  
  
1.  <span data-ttu-id="7f234-124">Inicie la consulta agregando las tablas que desea resumir al panel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="7f234-124">Start the query by adding the tables you want to summarize to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="7f234-125">Haga clic con el botón derecho en el fondo del panel Diagrama y, a continuación, elija **Agregar grupo por** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="7f234-125">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="7f234-126">El Diseñador de consultas y vistas agrega una columna **Agrupar por** a la cuadrícula en el panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="7f234-126">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="7f234-127">Agregue la columna o columnas que desea agrupar al panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="7f234-127">Add the column or columns you want to group to the Criteria pane.</span></span> <span data-ttu-id="7f234-128">Si desea que la columna aparezca en los resultados de la consulta, asegúrese de que la columna **Resultados** está seleccionada para el resultado.</span><span class="sxs-lookup"><span data-stu-id="7f234-128">If you want the column to appear in the query output, be sure that the **Output** column is selected for output.</span></span>  
  
     <span data-ttu-id="7f234-129">El Diseñador de consultas y vistas agrega una cláusula GROUP BY a la instrucción en el panel SQL.</span><span class="sxs-lookup"><span data-stu-id="7f234-129">The Query and View Designer adds a GROUP BY clause to the statement in the SQL pane.</span></span> <span data-ttu-id="7f234-130">Por ejemplo, la instrucción SQL podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="7f234-130">For example, the SQL statement might look like this:</span></span>  
  
    ```  
    SELECT pub_id  
    FROM titles  
    GROUP BY pub_id  
    ```  
  
4.  <span data-ttu-id="7f234-131">Agregue la columna o columnas que desea agregar al panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="7f234-131">Add the column or columns you want to aggregate to the Criteria pane.</span></span> <span data-ttu-id="7f234-132">Asegúrese de que la columna está marcada para el resultado.</span><span class="sxs-lookup"><span data-stu-id="7f234-132">Be sure that the column is marked for output.</span></span>  
  
5.  <span data-ttu-id="7f234-133">En la celda de cuadrícula **Agrupar por** de la columna que se va a agregar, seleccione la función de agregado correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7f234-133">In the **Group By** grid cell for the column that is going to be aggregated, select the appropriate aggregate function.</span></span>  
  
     <span data-ttu-id="7f234-134">El Diseñador de consultas y vistas asigna automáticamente un alias a la columna que va a resumir.</span><span class="sxs-lookup"><span data-stu-id="7f234-134">The Query and View Designer automatically assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="7f234-135">Puede sustituir este alias generado automáticamente por otro más significativo.</span><span class="sxs-lookup"><span data-stu-id="7f234-135">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="7f234-136">Para más información, consulte [Crear alias de columna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7f234-136">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
     <span data-ttu-id="7f234-137">![Agregar un alias de columna al conjunto de resultados de la consulta](../../database-engine/media//dv3w9e3.gif "Agregar un alias de columna al conjunto de resultados de la consulta")</span><span class="sxs-lookup"><span data-stu-id="7f234-137">![Adding a column alias to the query result set](../../database-engine/media//dv3w9e3.gif "Adding a column alias to the query result set")</span></span>  
  
     <span data-ttu-id="7f234-138">La instrucción correspondiente en el panel **SQL** podría tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="7f234-138">The corresponding statement in the **SQL** pane might look like this:</span></span>  
  
    ```  
    SELECT   pub_id, SUM(price) AS Totalprice  
    FROM     titles  
    GROUP BY pub_id  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7f234-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f234-139">See Also</span></span>  
 [<span data-ttu-id="7f234-140">Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7f234-140">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
