---
title: Ordenar en orden ascendente o descendente (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- descending sorts
- ascending sorts
ms.assetid: d61cc55b-9ee8-4ecf-a32f-6459ae43910b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b5e6b00f62cfc297cc5930bc8cf3a41314a2f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676776"
---
# <a name="sort-in-ascending-or-descending-order-visual-database-tools"></a><span data-ttu-id="ca507-102">Ordenar en orden ascendente o descendente (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ca507-102">Sort in Ascending or Descending Order (Visual Database Tools)</span></span>
  <span data-ttu-id="ca507-103">Puede ordenar los resultados de la consulta en orden ascendente o descendente en una o más columnas del conjunto de resultados utilizando las palabras clave `ASC` o `DESC` con la cláusula `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="ca507-103">You can sort query results in ascending or descending order on one or more of the columns in the result set by using the `ASC` or `DESC` keywords with the `ORDER BY` clause.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca507-104">La secuencia de intercalación de la columna determina en parte el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ca507-104">The sort order is determined in part by the column's collation sequence.</span></span> <span data-ttu-id="ca507-105">La secuencia de intercalación se puede modificar en el [cuadro de diálogo Intercalación](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca507-105">You can change the collation sequence in the [Collation Dialog Box](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="ca507-106">El procedimiento siguiente asume que en el Diseñador de consultas y vistas hay una consulta abierta que utiliza la cláusula ORDER BY para ordenar una o más columnas.</span><span class="sxs-lookup"><span data-stu-id="ca507-106">The following procedure assumes that you have a query open in Query and View Designer that uses the ORDER BY clause to sort one or more columns.</span></span>  
  
### <a name="to-specify-or-change-the-order-in-which-results-are-sorted"></a><span data-ttu-id="ca507-107">Para especificar o cambiar el criterio de ordenación de los resultados</span><span class="sxs-lookup"><span data-stu-id="ca507-107">To specify or change the order in which results are sorted</span></span>  
  
1.  <span data-ttu-id="ca507-108">En el [panel Criterios](criteria-pane-visual-database-tools.md), haga clic en el campo **Tipo de orden** de la columna que desea reordenar.</span><span class="sxs-lookup"><span data-stu-id="ca507-108">In the [Criteria pane](criteria-pane-visual-database-tools.md), click the **Sort Type** field for the column that you want to reorder.</span></span>  
  
2.  <span data-ttu-id="ca507-109">Elija **Ascendente** o **Descendente** para especificar el criterio de ordenación de la columna.</span><span class="sxs-lookup"><span data-stu-id="ca507-109">Choose **Ascending** or **Descending** to specify the sort order for the column.</span></span>  
  
 <span data-ttu-id="ca507-110">Observe que cuando se trabaja en el panel Criterios, la cláusula UNION de la consulta cambia para coincidir con las acciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="ca507-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca507-111">Al ordenar los resultados por más de una columna, especifique el orden de prioridad que se seguirá al realizar búsquedas en las columnas utilizando la columna Criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ca507-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the Sort Order column.</span></span> <span data-ttu-id="ca507-112">Para más información, consulte [Ordenar varias columnas en las consultas &#40;Visual Database Tools&#41;](sort-multiple-columns-in-queries-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ca507-112">For more information, see [Sort Multiple Columns in Queries &#40;Visual Database Tools&#41;](sort-multiple-columns-in-queries-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca507-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca507-113">See Also</span></span>  
 <span data-ttu-id="ca507-114">[Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ca507-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="ca507-115">[Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="ca507-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="ca507-116">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ca507-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
