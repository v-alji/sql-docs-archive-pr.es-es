---
title: Especificar condiciones para grupos (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- HAVING clause, query groups
- group query conditions [SQL Server]
ms.assetid: 269ad9c5-3261-4526-badf-7be3c869f229
author: stevestein
ms.author: sstein
ms.openlocfilehash: da9bc1b70fbfae8bf2a68a3a3ba332020020f310
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661740"
---
# <a name="specify-conditions-for-groups-visual-database-tools"></a><span data-ttu-id="a9e89-102">Especificar condiciones para grupos (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a9e89-102">Specify Conditions for Groups (Visual Database Tools)</span></span>
  <span data-ttu-id="a9e89-103">Puede limitar los grupos que aparecen en una consulta si especifica una condición que se aplique a los grupos en su totalidad: una cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="a9e89-103">You can limit the groups that appear in a query by specifying a condition that applies to groups as a whole - a HAVING clause.</span></span> <span data-ttu-id="a9e89-104">Una vez agrupados y agregados los datos, se aplican las condiciones de la cláusula HAVING.</span><span class="sxs-lookup"><span data-stu-id="a9e89-104">After the data has been grouped and aggregated, the conditions in the HAVING clause are applied.</span></span> <span data-ttu-id="a9e89-105">Solo aparecen en la consulta los grupos que cumplen las condiciones.</span><span class="sxs-lookup"><span data-stu-id="a9e89-105">Only the groups that meet the conditions appear in the query.</span></span>  
  
 <span data-ttu-id="a9e89-106">Por ejemplo, es posible que desee ver el precio medio de todos los libros de cada editorial en la tabla `titles` , pero únicamente cuando el precio medio supere los 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="a9e89-106">For example, you might want to see the average price of all books for each publisher in a `titles` table, but only if the average price exceeds $10.00.</span></span> <span data-ttu-id="a9e89-107">En ese caso, podría especificar una cláusula HAVING con una condición como `AVG(price) > 10`.</span><span class="sxs-lookup"><span data-stu-id="a9e89-107">In that case, you could specify a HAVING clause with a condition such as `AVG(price) > 10`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9e89-108">En algunas ocasiones, quizás desee excluir algunas filas de los grupos antes de aplicar una condición a la totalidad de los grupos.</span><span class="sxs-lookup"><span data-stu-id="a9e89-108">In some instances, you might want to exclude individual rows from groups before applying a condition to groups as a whole.</span></span> <span data-ttu-id="a9e89-109">Para detalles, consulte [Usar cláusulas HAVING y WHERE en la misma consulta &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a9e89-109">For details, see [Use HAVING and WHERE Clauses in the Same Query &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="a9e89-110">Puede crear condiciones complejas para una cláusula HAVING utilizando AND y OR para unir condiciones.</span><span class="sxs-lookup"><span data-stu-id="a9e89-110">You can create complex conditions for a HAVING clause by using AND and OR to link conditions.</span></span> <span data-ttu-id="a9e89-111">Para detalles sobre cómo usar AND y OR en las condiciones de búsqueda, consulte [Especificar varias condiciones de búsqueda para una columna &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a9e89-111">For details about using AND and OR in search conditions, see [Specify Multiple Search Conditions for One Column &#40;Visual Database Tools&#41;](specify-multiple-search-conditions-for-one-column-visual-database-tools.md).</span></span>  
  
### <a name="to-specify-a-condition-for-a-group"></a><span data-ttu-id="a9e89-112">Para especificar una condición para un grupo</span><span class="sxs-lookup"><span data-stu-id="a9e89-112">To specify a condition for a group</span></span>  
  
1.  <span data-ttu-id="a9e89-113">Especifique los grupos de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a9e89-113">Specify the groups for your query.</span></span> <span data-ttu-id="a9e89-114">Para detalles, consulte [Agrupar filas en los resultados de la consulta &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a9e89-114">For details, see [Group Rows in Query Results &#40;Visual Database Tools&#41;](group-rows-in-query-results-visual-database-tools.md).</span></span>  
  
2.  <span data-ttu-id="a9e89-115">Si aún no está en el [panel Criterios](criteria-pane-visual-database-tools.md), agregue la columna en la que desea basar la condición.</span><span class="sxs-lookup"><span data-stu-id="a9e89-115">If it is not already in the [Criteria pane](criteria-pane-visual-database-tools.md), add the column on which you want to base the condition.</span></span> <span data-ttu-id="a9e89-116">Normalmente, la condición se aplica a una columna que ya es un grupo o una columna de resumen. No puede utilizar una columna que no forme parte de una función de agregado o de la cláusula GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="a9e89-116">(Most often the condition involves a column that is already a group or summary column.) You cannot use a column that is not part of an aggregate function or of the GROUP BY clause.</span></span>  
  
3.  <span data-ttu-id="a9e89-117">En la columna **Filtro**, especifique la condición que se aplica al agrupo.</span><span class="sxs-lookup"><span data-stu-id="a9e89-117">In the **Filter** column, specify the condition to apply to the group.</span></span>  
  
     <span data-ttu-id="a9e89-118">El [Diseñador de consultas y vistas](query-and-view-designer-tools-visual-database-tools.md) crea automáticamente una cláusula HAVING en la instrucción del [panel SQL](sql-pane-visual-database-tools.md), como la que se incluye en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9e89-118">The [Query and View Designer](query-and-view-designer-tools-visual-database-tools.md) automatically creates a HAVING clause in the statement in the [SQL pane](sql-pane-visual-database-tools.md), such as in the following example:</span></span>  
  
    ```  
    SELECT pub_id, AVG(price)  
    FROM titles  
    GROUP BY pub_id  
    HAVING (AVG(price) > 10)  
  
    ```  
  
4.  <span data-ttu-id="a9e89-119">Repita los pasos 2 y 3 para las demás condiciones que desee especificar.</span><span class="sxs-lookup"><span data-stu-id="a9e89-119">Repeat steps 2 and 3 for each additional condition you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e89-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9e89-120">See Also</span></span>  
 [<span data-ttu-id="a9e89-121">Ordenar y agrupar los resultados de una consulta &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="a9e89-121">Sort and Group Query Results &#40;Visual Database Tools&#41;</span></span>](sort-and-group-query-results-visual-database-tools.md)  
  
  
