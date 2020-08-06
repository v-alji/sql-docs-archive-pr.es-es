---
title: Resumir o agregar valores mediante expresiones personalizadas (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- summarizing query results
- custom expressions to aggregate values [SQL Server]
ms.assetid: 34130ac1-0106-4766-b324-acb0b7bb6f6e
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9f03f82842178a68c8a3d04ebc1bd738c0ab0b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747853"
---
# <a name="summarize-or-aggregate-values-using-custom-expressions-visual-database-tools"></a><span data-ttu-id="33bd9-102">Resumir o agregar valores mediante expresiones personalizadas (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="33bd9-102">Summarize or Aggregate Values Using Custom Expressions (Visual Database Tools)</span></span>
  <span data-ttu-id="33bd9-103">Además de utilizar las funciones de agregado para agregar datos, puede crear expresiones personalizadas para generar valores de agregado.</span><span class="sxs-lookup"><span data-stu-id="33bd9-103">In addition to using aggregate functions to aggregate data, you can create custom expressions to produce aggregate values.</span></span> <span data-ttu-id="33bd9-104">Estas expresiones se pueden utilizar en lugar de las funciones de agregado en cualquier lugar de una consulta de funciones agregadas.</span><span class="sxs-lookup"><span data-stu-id="33bd9-104">You can use custom expressions in place of aggregate functions anywhere in an aggregate query.</span></span>  
  
 <span data-ttu-id="33bd9-105">Por ejemplo, en la tabla `titles` podría crear una consulta que mostrara no solo el precio medio, sino el precio medio resultante si se aplicara un descuento.</span><span class="sxs-lookup"><span data-stu-id="33bd9-105">For example, in the `titles` table you might want to create a query that shows not just the average price, but what the average price would be if it were discounted.</span></span>  
  
 <span data-ttu-id="33bd9-106">No se pueden incluir expresiones basadas en cálculos en los que solo se utilicen filas individuales de la tabla; las expresiones deben basarse en valores agregados, ya que solo estos valores están disponibles cuando se calcula la expresión.</span><span class="sxs-lookup"><span data-stu-id="33bd9-106">You cannot include an expression that is based on calculations involving only individual rows in the table; the expression must be based on an aggregate value, because only the aggregate values are available at the time the expression is calculated.</span></span>  
  
### <a name="to-specify-a-custom-expression-for-a-summary-value"></a><span data-ttu-id="33bd9-107">Para especificar una expresión personalizada para un valor de resumen</span><span class="sxs-lookup"><span data-stu-id="33bd9-107">To specify a custom expression for a summary value</span></span>  
  
1.  <span data-ttu-id="33bd9-108">Especifique los grupos de la consulta.</span><span class="sxs-lookup"><span data-stu-id="33bd9-108">Specify the groups for your query.</span></span> <span data-ttu-id="33bd9-109">Para detalles, consulte [Agrupar filas en los resultados de la consulta &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="33bd9-109">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="33bd9-110">Desplácese a una fila vacía del panel Criterios y escriba la expresión en la columna **Columnas**.</span><span class="sxs-lookup"><span data-stu-id="33bd9-110">Move to a blank row of the Criteria pane, and then type the expression in the **Columns** column.</span></span>  
  
     <span data-ttu-id="33bd9-111">El [Diseñador de consultas y vistas](query-and-view-designer-tools-visual-database-tools.md) asigna automáticamente un alias de columna a la expresión para crear un encabezado de columna útil en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="33bd9-111">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically assigns a column alias to the expression to create a useful column heading in query output.</span></span> <span data-ttu-id="33bd9-112">Para más información, consulte [Crear alias de columna &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="33bd9-112">For more details, see [Create Column Aliases &#40;Visual Database Tools&#41;](create-column-aliases-visual-database-tools.md).</span></span>  
  
3.  <span data-ttu-id="33bd9-113">En la columna **Agrupar por** de la expresión, seleccione **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="33bd9-113">In the **Group By** column for the expression, select **Expression**.</span></span>  
  
4.  <span data-ttu-id="33bd9-114">Ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="33bd9-114">Run the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33bd9-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33bd9-115">See Also</span></span>  
 <span data-ttu-id="33bd9-116">[Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="33bd9-116">[Sort and Group Query Results &#40;Visual Database Tools&#41;](sort-and-group-query-results-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="33bd9-117">Resumir los resultados de una consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="33bd9-117">Summarize Query Results &#40;Visual Database Tools&#41;</span></span>](summarize-query-results-visual-database-tools.md)  
  
  
