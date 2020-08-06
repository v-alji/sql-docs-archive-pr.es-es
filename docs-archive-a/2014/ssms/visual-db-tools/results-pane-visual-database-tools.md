---
title: Panel Resultados (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- View Designer, Results pane
- result sets [SQL Server], queries
- synchronization [SQL Server], query results with definition
- displaying query results in grid
- grid showing query results [SQL Server]
- showing query results in grid
- Query Designer [SQL Server], Results pane
- results [SQL Server], query
- viewing query results
- queries [SQL Server], results
- Results pane
ms.assetid: 6309a1bc-a628-4141-8bb5-b35924bd19f9
author: stevestein
ms.author: sstein
ms.openlocfilehash: f0db32336931f74777be56befcde9501dc484b69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662458"
---
# <a name="results-pane-visual-database-tools"></a><span data-ttu-id="45b8c-102">Panel Resultados (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="45b8c-102">Results Pane (Visual Database Tools)</span></span>
  <span data-ttu-id="45b8c-103">El panel Resultados muestra los resultados de la consulta SELECT que se ha ejecutado más recientemente</span><span class="sxs-lookup"><span data-stu-id="45b8c-103">The Results pane shows the results of the most recently executed SELECT query.</span></span> <span data-ttu-id="45b8c-104">(Los resultados de otros tipos de consultas se muestran en cuadros de mensaje). Para abrir el panel de resultados, abra o cree una consulta, o vea o devuelva los datos de una tabla.</span><span class="sxs-lookup"><span data-stu-id="45b8c-104">(The results of other query types are displayed in message boxes.) To open the results pane, open or create a query or view or return a table's data.</span></span> <span data-ttu-id="45b8c-105">Si el panel de resultados no aparece de manera predeterminada, en el menú **Diseñador de consultas** , elija **Panel**y, a continuación, haga clic en **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="45b8c-105">If the results pane doesn't show by default, from the **Query Designer** menu, point to **Pane**, and then click **Results**.</span></span>  
  
## <a name="what-you-can-do-in-the-results-pane"></a><span data-ttu-id="45b8c-106">Lo que se puede hacer en el panel Resultados</span><span class="sxs-lookup"><span data-stu-id="45b8c-106">What You Can Do in the Results Pane</span></span>  
  
-   <span data-ttu-id="45b8c-107">Ver el conjunto de resultados de la consulta SELECT ejecutada más recientemente en una cuadrícula con forma de hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="45b8c-107">View the result set for the most recently executed SELECT query in a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="45b8c-108">Para las consultas o vistas que muestran datos de una única tabla o vista, puede editar los valores en columnas individuales en el conjunto de resultados, agregar nuevas filas y eliminar las filas existentes.</span><span class="sxs-lookup"><span data-stu-id="45b8c-108">For queries or views that show data from a single table or view, you can edit the values in individual columns in the result set, add new rows, and delete existing rows.</span></span>  
  
## <a name="limitations-in-the-results-pane"></a><span data-ttu-id="45b8c-109">Limitaciones del panel Resultados</span><span class="sxs-lookup"><span data-stu-id="45b8c-109">Limitations in the Results Pane</span></span>  
  
-   <span data-ttu-id="45b8c-110">Los resultados devueltos mediante funciones con valores de tabla solo pueden actualizarse en algunos casos.</span><span class="sxs-lookup"><span data-stu-id="45b8c-110">Results returned by table-valued functions can only be updated in some cases.</span></span>  
  
-   <span data-ttu-id="45b8c-111">Las consultas o vistas que incluyen columnas de más de una tabla o vista no pueden actualizarse.</span><span class="sxs-lookup"><span data-stu-id="45b8c-111">Queries or views that include columns from more than one table or view cannot be updated.</span></span>  
  
-   <span data-ttu-id="45b8c-112">Los resultados devueltos mediante un procedimiento almacenado no pueden actualizarse.</span><span class="sxs-lookup"><span data-stu-id="45b8c-112">Results returned by a stored procedure cannot be updated.</span></span>  
  
-   <span data-ttu-id="45b8c-113">Las consultas o vistas que utilizan las cláusulas GROUP BY o DISTINCT no se pueden actualizar.</span><span class="sxs-lookup"><span data-stu-id="45b8c-113">Queries or views using the GROUP BY or DISTINCT clauses are not updatable.</span></span>  
  
## <a name="navigating-in-the-results-pane"></a><span data-ttu-id="45b8c-114">Desplazarse por el panel de resultados</span><span class="sxs-lookup"><span data-stu-id="45b8c-114">Navigating in the Results Pane</span></span>  
 <span data-ttu-id="45b8c-115">Puede navegar rápidamente por los registros utilizando la barra de navegación de la parte inferior del panel Resultados.</span><span class="sxs-lookup"><span data-stu-id="45b8c-115">You can quickly navigate through the records using the navigation bar at the bottom of the Results pane.</span></span>  
  
 <span data-ttu-id="45b8c-116">Hay botones para ir al primer y último registro, al registro anterior y siguiente, y para ir a un registro concreto.</span><span class="sxs-lookup"><span data-stu-id="45b8c-116">There are buttons for going to the first and last records, the next and previous records, and for going to a particular record.</span></span>  
  
 <span data-ttu-id="45b8c-117">Para ir a un registro concreto, escriba el número de la fila en el cuadro de texto de la barra de navegación y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="45b8c-117">To go to a particular record, type the number of the row in the text box in the navigation bar and then press ENTER.</span></span>  
  
 <span data-ttu-id="45b8c-118">Para información sobre cómo usar los métodos abreviados de teclado en el Diseñador de consultas y vistas, consulte [Desplazarse por el Diseñador de consultas y vistas &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="45b8c-118">For information about using keyboard shortcuts in the Query and View Designer see [Navigate in the Query and View Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
## <a name="keeping-the-results-set-synchronized-with-the-query-definition"></a><span data-ttu-id="45b8c-119">Mantener el conjunto de resultados sincronizado con la definición de la consulta</span><span class="sxs-lookup"><span data-stu-id="45b8c-119">Keeping the Results Set Synchronized with the Query Definition</span></span>  
 <span data-ttu-id="45b8c-120">Es posible que, mientras se trabaja con los resultados de una consulta o vista, los registros del panel de resultados dejen de estar sincronizados con la definición de la consulta.</span><span class="sxs-lookup"><span data-stu-id="45b8c-120">While you are working on the results of a query or view it is possible for the records in the results pane to get out of synchronization with the query's definition.</span></span> <span data-ttu-id="45b8c-121">Por ejemplo, si se ejecuta una consulta para cuatro de las cinco columnas de una tabla y, a continuación, se utiliza el panel Diagrama para agregar la quinta columna a la definición de la consulta, los datos de esa quinta columna no se agregarán automáticamente al panel Resultados.</span><span class="sxs-lookup"><span data-stu-id="45b8c-121">For example, if you run a query for four out of five columns in a table, and then use the Diagram pane to add the fifth column to the definition of the query, that fifth column's data will not automatically be added to the Results pane.</span></span> <span data-ttu-id="45b8c-122">Para hacer que el panel de resultados refleje la nueva definición, vuelva a ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="45b8c-122">To make the results pane reflect the new query definition, run the query again.</span></span>  
  
 <span data-ttu-id="45b8c-123">Si se cambia una consulta, aparecerá un icono de alerta y el texto "Consulta cambiada" en la esquina inferior derecha del panel de resultados.</span><span class="sxs-lookup"><span data-stu-id="45b8c-123">If a query changes, an alert icon and the text "Query Changed" appears in the lower-right corner of the results pane.</span></span> <span data-ttu-id="45b8c-124">El icono aparecerá repetido en la esquina superior izquierda del panel.</span><span class="sxs-lookup"><span data-stu-id="45b8c-124">The icon is repeated in the upper-left corner of the pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45b8c-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45b8c-125">See Also</span></span>  
 <span data-ttu-id="45b8c-126">[Crear consultas &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="45b8c-126">[Create Queries &#40;Visual Database Tools&#41;](create-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="45b8c-127">[Ejecutar consultas &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="45b8c-127">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 <span data-ttu-id="45b8c-128">[Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="45b8c-128">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](design-queries-and-views-how-to-topics-visual-database-tools.md) </span></span>  
 <span data-ttu-id="45b8c-129">[Panel Diagrama &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="45b8c-129">[Diagram Pane &#40;Visual Database Tools&#41;](diagram-pane-visual-database-tools.md) </span></span>  
 <span data-ttu-id="45b8c-130">[Panel criterios &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="45b8c-130">[Criteria Pane &#40;Visual Database Tools&#41;](criteria-pane-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="45b8c-131">Trabajar con datos en el panel Resultados &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="45b8c-131">Work with Data in the Results Pane &#40;Visual Database Tools&#41;</span></span>](results-pane-visual-database-tools.md)  
  
  
