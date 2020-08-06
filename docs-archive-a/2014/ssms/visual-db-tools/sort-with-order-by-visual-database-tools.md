---
title: Ordenar con ORDER BY (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- ORDER BY clause [Visual Database Tools]
ms.assetid: 459f5640-8058-4c24-97e7-7bbd6168bc39
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93bdb9ed01c7935c5b9dae543804fca758a9262d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748450"
---
# <a name="sort-with-order-by-visual-database-tools"></a><span data-ttu-id="39f00-102">Ordenar con ORDER BY (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="39f00-102">Sort with ORDER BY (Visual Database Tools)</span></span>
  <span data-ttu-id="39f00-103">Puede ordenar los resultados de la consulta por una o más de las columnas de las filas devueltas utilizando una cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="39f00-103">You can sort query results by one or more of the columns in the returned rows by using an ORDER BY clause.</span></span> <span data-ttu-id="39f00-104">Puede definir una cláusula ORDER BY eligiendo opciones en el panel Detalles de los criterios.</span><span class="sxs-lookup"><span data-stu-id="39f00-104">You can define an ORDER BY clause by choosing options in the Criteria Details pane.</span></span>  
  
### <a name="to-sort-a-query-using-an-order-by-clause"></a><span data-ttu-id="39f00-105">Para ordenar una consulta utilizando una cláusula ORDER BY</span><span class="sxs-lookup"><span data-stu-id="39f00-105">To sort a query using an ORDER BY clause</span></span>  
  
1.  <span data-ttu-id="39f00-106">Abra una consulta o cree una nueva.</span><span class="sxs-lookup"><span data-stu-id="39f00-106">Open a query or create a new one.</span></span>  
  
2.  <span data-ttu-id="39f00-107">En el [panel Criterios](visual-database-tools.md), haga clic en la columna **Tipo de orden** de la fila correspondiente a la columna que desea utilizar para ordenar los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="39f00-107">In the [Criteria Pane](visual-database-tools.md), click the **Sort Type** column for the row corresponding to the column that you want to use to sort your query results.</span></span>  
  
3.  <span data-ttu-id="39f00-108">Elija *Ascendente* o *Descendente* en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="39f00-108">Choose *Ascending* or *Descending* from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39f00-109">Al borrar la entrada **Tipo de orden** de una columna, ésta se quita de la cláusula ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="39f00-109">Clearing the **Sort Type** entry for a column removes that column from the ORDER BY clause.</span></span>  
  
 <span data-ttu-id="39f00-110">Observe que cuando se trabaja en el panel Criterios, la cláusula UNION de la consulta cambia para coincidir con las acciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="39f00-110">Notice that as you work in the Criteria pane, your query's UNION clause changes to match your most recent actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39f00-111">Al ordenar los resultados por más de una columna, especifique el orden de prioridad que se seguirá al realizar búsquedas en las columnas utilizando la columna **Criterio de ordenación** .</span><span class="sxs-lookup"><span data-stu-id="39f00-111">When sorting results by more than one column, specify the order in which columns are searched relative to each other by using the **Sort Order** column.</span></span> <span data-ttu-id="39f00-112">Para más información, consulte **Ordenar varias columnas de las consultas**.</span><span class="sxs-lookup"><span data-stu-id="39f00-112">For more information, see **How to: Sort Multiple Columns in Queries**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f00-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39f00-113">See Also</span></span>  
 <span data-ttu-id="39f00-114">[Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="39f00-114">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 <span data-ttu-id="39f00-115">[Resumir los resultados de una consulta &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="39f00-115">[Summarize Query Results &#40;Visual Database Tools&#41;](summarize-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="39f00-116">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="39f00-116">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
