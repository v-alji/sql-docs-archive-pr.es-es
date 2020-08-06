---
title: Quitar combinaciones (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- removing joins
- joins [SQL Server], removing
- deleting joins
ms.assetid: ccc212a1-fd13-48d6-85e5-5ff310c34bbd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b037e317b629671f6ec5ea1fa90edfca6fafa627
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661741"
---
# <a name="remove-joins-visual-database-tools"></a><span data-ttu-id="8fce4-102">Quitar combinaciones (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8fce4-102">Remove Joins (Visual Database Tools)</span></span>
  <span data-ttu-id="8fce4-103">Si no desea que las tablas se combinen mediante una combinación interna o externa, puede quitar la combinación existente entre ellas.</span><span class="sxs-lookup"><span data-stu-id="8fce4-103">If you do not want tables to be joined via an inner join or an outer join, you can remove the join between them.</span></span> <span data-ttu-id="8fce4-104">Por ejemplo, puede quitar una combinación que el [Diseñador de consultas y vistas](visual-database-tools.md) haya creado automáticamente entre dos tablas.</span><span class="sxs-lookup"><span data-stu-id="8fce4-104">For example, you might remove a join that the [Query and View Designer](visual-database-tools.md) has been created automatically between two tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8fce4-105">Cuando se quita una combinación de una consulta, no se modifica la relación subyacente en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8fce4-105">Removing a join from a query does not alter the underlying relationship in the database.</span></span>  
  
 <span data-ttu-id="8fce4-106">Si dos tablas combinadas forman parte de la consulta y quita todas las condiciones de combinación que existen entre ellas, la consulta resultante es el producto de ambas tablas, es decir, una instancia CROSS JOIN.</span><span class="sxs-lookup"><span data-stu-id="8fce4-106">If two joined tables are part of your query and you remove all join conditions between them, the resulting query becomes the product of both tables - that is, it becomes a CROSS JOIN.</span></span>  
  
### <a name="to-remove-a-join"></a><span data-ttu-id="8fce4-107">Para quitar una combinación</span><span class="sxs-lookup"><span data-stu-id="8fce4-107">To remove a join</span></span>  
  
-   <span data-ttu-id="8fce4-108">En el [panel Diagrama](diagram-pane-visual-database-tools.md), seleccione la línea de combinación de la combinación que desea quitar y, a continuación, presione la tecla SUPR.</span><span class="sxs-lookup"><span data-stu-id="8fce4-108">In the [Diagram pane](diagram-pane-visual-database-tools.md), select the join line for the join to remove, and then press the DELETE key.</span></span> <span data-ttu-id="8fce4-109">Puede seleccionar y eliminar varias líneas de combinación al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="8fce4-109">You can select and delete multiple join lines at one time.</span></span>  
  
 <span data-ttu-id="8fce4-110">El Diseñador de consultas y vistas quita la línea de combinación y modifica la instrucción en el [panel SQL](sql-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8fce4-110">The Query and View Designer removes the join line and alters the statement in the [SQL pane](sql-pane-visual-database-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fce4-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8fce4-111">See Also</span></span>  
 <span data-ttu-id="8fce4-112">[Combinar tablas automáticamente &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8fce4-112">[Join Tables Automatically &#40;Visual Database Tools&#41;](join-tables-automatically-visual-database-tools.md) </span></span>  
 <span data-ttu-id="8fce4-113">[Combinar tablas manualmente &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8fce4-113">[Join Tables Manually &#40;Visual Database Tools&#41;](join-tables-manually-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="8fce4-114">Realizar consultas con combinaciones &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8fce4-114">Query with Joins &#40;Visual Database Tools&#41;</span></span>](query-with-joins-visual-database-tools.md)  
  
  
