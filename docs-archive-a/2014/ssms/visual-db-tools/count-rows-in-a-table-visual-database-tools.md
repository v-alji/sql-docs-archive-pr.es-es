---
title: Contar las filas de una tabla (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- totals [SQL Server], row counts
- row counts [SQL Server]
- column values [SQL Server]
- number of rows
- number of values
- counting rows
ms.assetid: dda4296a-1d16-4e77-8d6f-e295f6dd4e87
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6dca92fb955b776f56d9b51f28b1a486b89f18f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746066"
---
# <a name="count-rows-in-a-table-visual-database-tools"></a><span data-ttu-id="a27fe-102">Contar las filas de una tabla (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a27fe-102">Count Rows in a Table (Visual Database Tools)</span></span>
  <span data-ttu-id="a27fe-103">Puede contar las filas de una tabla para determinar:</span><span class="sxs-lookup"><span data-stu-id="a27fe-103">You can count rows in a table to determine:</span></span>  
  
-   <span data-ttu-id="a27fe-104">El número total de filas de una tabla, como por ejemplo, la suma de todos los libros de una tabla `titles` .</span><span class="sxs-lookup"><span data-stu-id="a27fe-104">The total number of rows in a table, for example, a count of all the books in a `titles` table.</span></span>  
  
-   <span data-ttu-id="a27fe-105">El número de filas de una tabla que satisfacen una condición específica, como por ejemplo, el número de libros de una editorial en una tabla `titles` .</span><span class="sxs-lookup"><span data-stu-id="a27fe-105">The number of rows in a table that meet a specific condition, for example, the number of books by one publisher in a `titles` table.</span></span>  
  
-   <span data-ttu-id="a27fe-106">El número de valores de una determinada columna.</span><span class="sxs-lookup"><span data-stu-id="a27fe-106">The number of values in a particular column.</span></span>  
  
 <span data-ttu-id="a27fe-107">Cuando se cuentan los valores de una columna, no se incluyen los valores NULL en el recuento.</span><span class="sxs-lookup"><span data-stu-id="a27fe-107">When you count values in a column, nulls are not included in the count.</span></span> <span data-ttu-id="a27fe-108">Por ejemplo, es posible que desee hacer el recuento del número de libros de una tabla `titles` que tiene valores en la columna `advance` .</span><span class="sxs-lookup"><span data-stu-id="a27fe-108">For example, you might count the number of books in a `titles` table that have values in the `advance` column.</span></span> <span data-ttu-id="a27fe-109">De forma predeterminada, el recuento incluirá todos los valores y no solo los valores únicos.</span><span class="sxs-lookup"><span data-stu-id="a27fe-109">By default, the count includes all values, not just unique values.</span></span>  
  
 <span data-ttu-id="a27fe-110">Los procedimientos para los tres tipos de recuentos son similares.</span><span class="sxs-lookup"><span data-stu-id="a27fe-110">The procedures for all three types of counts are similar.</span></span>  
  
### <a name="to-count-all-the-rows-in-a-table"></a><span data-ttu-id="a27fe-111">Para contar todas las filas de una tabla</span><span class="sxs-lookup"><span data-stu-id="a27fe-111">To count all the rows in a table</span></span>  
  
1.  <span data-ttu-id="a27fe-112">Asegúrese de que la tabla que desea resumir ya esté presente en el panel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="a27fe-112">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="a27fe-113">Haga clic con el botón derecho en el fondo del panel Diagrama y, a continuación, elija **Agregar grupo por** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="a27fe-113">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="a27fe-114">El [Diseñador de consultas y vistas](visual-database-tools.md) agrega una columna **Agrupar por** a la cuadrícula en el panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="a27fe-114">The [Query and View Designer](visual-database-tools.md) adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="a27fe-115">Seleccione \*\* \* (todas las columnas)\*\* en el rectángulo que representa la tabla o el objeto con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="a27fe-115">Select **\* (All Columns)** in the rectangle representing the table or table-valued object.</span></span>  
  
     <span data-ttu-id="a27fe-116">El Diseñador de consultas y vistas escribe automáticamente el término **Recuento** en la columna **Agrupar por** del panel Criterios y asigna un alias a la columna que se va a resumir.</span><span class="sxs-lookup"><span data-stu-id="a27fe-116">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="a27fe-117">Puede sustituir este alias generado automáticamente por otro más significativo.</span><span class="sxs-lookup"><span data-stu-id="a27fe-117">You can replace this automatically generated alias with a more meaningful one.</span></span> <span data-ttu-id="a27fe-118">Para más información, consulte [Crear alias de columna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a27fe-118">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="a27fe-119">Ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="a27fe-119">Run the query.</span></span>  
  
### <a name="to-count-all-the-rows-that-meet-a-condition"></a><span data-ttu-id="a27fe-120">Para contar todas las filas que cumplen una condición</span><span class="sxs-lookup"><span data-stu-id="a27fe-120">To count all the rows that meet a condition</span></span>  
  
1.  <span data-ttu-id="a27fe-121">Asegúrese de que la tabla que desea resumir ya esté presente en el panel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="a27fe-121">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="a27fe-122">Haga clic con el botón derecho en el fondo del panel Diagrama y, a continuación, elija **Agregar grupo por** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="a27fe-122">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="a27fe-123">El Diseñador de consultas y vistas agrega una columna **Agrupar por** a la cuadrícula en el panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="a27fe-123">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="a27fe-124">Seleccione \*\* \* (todas las columnas)\*\* en el rectángulo que representa la tabla o el objeto con estructura de tabla.</span><span class="sxs-lookup"><span data-stu-id="a27fe-124">Select **\*(All Columns)** in the rectangle representing the table or table-structured object.</span></span>  
  
     <span data-ttu-id="a27fe-125">El Diseñador de consultas y vistas escribe automáticamente el término **Recuento** en la columna **Agrupar por** del panel Criterios y asigna un alias a la columna que se va a resumir.</span><span class="sxs-lookup"><span data-stu-id="a27fe-125">The Query and View Designer automatically fills the term **Count** into the **Group By** column in the Criteria pane and assigns a column alias to the column you are summarizing.</span></span> <span data-ttu-id="a27fe-126">Para crear un encabezado de columna más útil en el resultado de la consulta, vea [Crear alias de columna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a27fe-126">To create a more useful column heading in query output, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
4.  <span data-ttu-id="a27fe-127">Agregue la columna de datos que desea buscar y, a continuación, desactive la casilla de la columna **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="a27fe-127">Add the data column that you want to search, and then clear the check box in the **Output** column.</span></span>  
  
     <span data-ttu-id="a27fe-128">El Diseñador de consultas y vistas incluye automáticamente el término **Agrupar por** en la columna **Agrupar por** de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a27fe-128">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
5.  <span data-ttu-id="a27fe-129">Cambie **Agrupar por** en la columna **Agrupar por** por **Ubicación**.</span><span class="sxs-lookup"><span data-stu-id="a27fe-129">Change **Group By** in the **Group By** column to **Where**.</span></span>  
  
6.  <span data-ttu-id="a27fe-130">En la columna **Filtro** de la columna de datos en la que va a realizar la búsqueda, especifique la condición de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a27fe-130">In the **Filter** column for the data column to search, enter the search condition.</span></span>  
  
7.  <span data-ttu-id="a27fe-131">Ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="a27fe-131">Run the query.</span></span>  
  
### <a name="to-count-the-values-in-a-column"></a><span data-ttu-id="a27fe-132">Para contar los valores de una columna</span><span class="sxs-lookup"><span data-stu-id="a27fe-132">To count the values in a column</span></span>  
  
1.  <span data-ttu-id="a27fe-133">Asegúrese de que la tabla que desea resumir ya esté presente en el panel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="a27fe-133">Be sure the table you want to summarize is already present in the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="a27fe-134">Haga clic con el botón derecho en el fondo del panel Diagrama y, a continuación, elija **Agregar grupo por** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="a27fe-134">Right-click the background of the Diagram pane, then choose **Add Group By** from the shortcut menu.</span></span> <span data-ttu-id="a27fe-135">El Diseñador de consultas y vistas agrega una columna **Agrupar por** a la cuadrícula en el panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="a27fe-135">The Query and View Designer adds a **Group By** column to the grid in the Criteria pane.</span></span>  
  
3.  <span data-ttu-id="a27fe-136">Agregue la columna que desea contar al panel Criterios.</span><span class="sxs-lookup"><span data-stu-id="a27fe-136">Add the column that you want to count to the Criteria pane.</span></span>  
  
     <span data-ttu-id="a27fe-137">El Diseñador de consultas y vistas incluye automáticamente el término **Agrupar por** en la columna **Agrupar por** de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a27fe-137">The Query and View Designer automatically fills the term **Group By** into the **Group By** column of the grid.</span></span>  
  
4.  <span data-ttu-id="a27fe-138">Cambie **Agrupar por** en la columna **Agrupar por** por **Recuento**.</span><span class="sxs-lookup"><span data-stu-id="a27fe-138">Change **Group By** in the **Group By** column to **Count**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a27fe-139">Para contar solo valores únicos, elija **Count Distinct**.</span><span class="sxs-lookup"><span data-stu-id="a27fe-139">To count only unique values, choose **Count Distinct**.</span></span>  
  
5.  <span data-ttu-id="a27fe-140">Ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="a27fe-140">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a27fe-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a27fe-141">See Also</span></span>  
 <span data-ttu-id="a27fe-142">[Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="a27fe-142">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="a27fe-143">Resumir los resultados de una consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a27fe-143">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
