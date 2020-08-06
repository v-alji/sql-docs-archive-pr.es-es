---
title: Crear consultas de eliminación (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- row removal [SQL Server], Delete query
- Delete query
- queries [SQL Server], types
- removing rows
- removing data
- data deletions [SQL Server]
- deleting rows
- deleting data
ms.assetid: 0db3af43-1ec4-48c8-b769-2bb9c76d3434
author: stevestein
ms.author: sstein
ms.openlocfilehash: a76c3aaef623365e419f40f3058308f6217d75d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677322"
---
# <a name="create-delete-queries-visual-database-tools"></a><span data-ttu-id="2dca9-102">Crear consultas de eliminación (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2dca9-102">Create Delete Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="2dca9-103">Puede eliminar todas las filas de una tabla utilizando una consulta de eliminación.</span><span class="sxs-lookup"><span data-stu-id="2dca9-103">You can delete all rows in a table by using a Delete query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2dca9-104">Cuando se eliminan todas las filas de una tabla, se borran los datos, pero no la tabla.</span><span class="sxs-lookup"><span data-stu-id="2dca9-104">Deleting all rows from a table clears the data in the table but does not delete the table itself.</span></span> <span data-ttu-id="2dca9-105">Para eliminar una tabla de una base de datos, haga clic en la tabla con el botón derecho en el Explorador de objetos y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="2dca9-105">To delete a table from a database, right-click the table in Object Explorer and click **Delete**.</span></span>  
  
 <span data-ttu-id="2dca9-106">Cuando se crea una consulta de eliminación, el panel Criterios cambia para reflejar las opciones disponibles para eliminar filas.</span><span class="sxs-lookup"><span data-stu-id="2dca9-106">When you create a Delete query, the Criteria pane changes to reflect the options available for deleting rows.</span></span> <span data-ttu-id="2dca9-107">Dado que en una consulta Eliminar no se muestran datos, se quitan las columnas Resultados, Ordenar por y Criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="2dca9-107">Because you do not display data in a Delete query, the Output, Sort By, and Sort Order columns are removed.</span></span> <span data-ttu-id="2dca9-108">Asimismo, como no se pueden especificar columnas individuales para eliminarlas, no aparecerán las casillas situadas junto a los nombres de columna en el rectángulo que representa la tabla o el objeto con valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="2dca9-108">In addition, the check boxes next to the column names in the rectangle representing the table or table-valued object are removed because you cannot specify individual columns to delete.</span></span>  
  
 <span data-ttu-id="2dca9-109">Si el Diseñador de consultas y vistas no puede eliminar una o varias filas, no se eliminará ninguna de ellas y recibirá un mensaje en el que se indicarán las filas que contienen información que no se puede eliminar de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2dca9-109">If the Query and View Designer can't delete one or more of the rows none of them will be deleted and you will receive a message telling you which row(s) contain information that can't be deleted from the database.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="2dca9-110">No es posible deshacer la operación de ejecutar una consulta de eliminación.</span><span class="sxs-lookup"><span data-stu-id="2dca9-110">You cannot undo the action of executing a Delete query.</span></span> <span data-ttu-id="2dca9-111">Como medida de precaución, haga una copia de seguridad de los datos antes de ejecutar una consulta Eliminar.</span><span class="sxs-lookup"><span data-stu-id="2dca9-111">As a precaution, back up your data before executing a Delete query.</span></span>  
  
### <a name="to-create-a-delete-query"></a><span data-ttu-id="2dca9-112">Para crear una consulta Eliminar</span><span class="sxs-lookup"><span data-stu-id="2dca9-112">To create a Delete query</span></span>  
  
1.  <span data-ttu-id="2dca9-113">Agregue tabla de la que se van a eliminar filas al panel Diagrama.</span><span class="sxs-lookup"><span data-stu-id="2dca9-113">Add the table to delete rows from to the Diagram pane.</span></span>  
  
2.  <span data-ttu-id="2dca9-114">En el menú **Diseñador de consultas** , seleccione **Cambiar tipo**y, luego, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="2dca9-114">From the **Query Designer** menu, point to **Change Type**, and then click **Delete**.</span></span> <span data-ttu-id="2dca9-115">**Nota** Si aparece más de una tabla en el panel Diagrama al iniciar la consulta de eliminación, el Diseñador de consultas y vistas mostrará el [cuadro de diálogo Eliminar tabla](visual-database-tools.md) para solicitar el nombre de la tabla de la que se van a eliminar filas.</span><span class="sxs-lookup"><span data-stu-id="2dca9-115">**Note** If more than one table is displayed in the Diagram pane when you start the Delete query, the Query and View Designer displays the [Delete Table Dialog Box](visual-database-tools.md) to prompt you for the name of the table to delete rows from.</span></span>  
  
 <span data-ttu-id="2dca9-116">Al ejecutar una consulta de eliminación, no se muestra ningún resultado en el [panel Resultados](results-pane-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2dca9-116">When you execute the Delete query, no results are reported in the [Results Pane](results-pane-visual-database-tools.md).</span></span> <span data-ttu-id="2dca9-117">En su lugar, aparece un mensaje que indica cuántas filas se han eliminado.</span><span class="sxs-lookup"><span data-stu-id="2dca9-117">Instead, a message appears indicating how many rows were deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dca9-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2dca9-118">See Also</span></span>  
 <span data-ttu-id="2dca9-119">[Tipos de consultas admitidos &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2dca9-119">[Supported Query Types &#40;Visual Database Tools&#41;](supported-query-types-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="2dca9-120">Temas de procedimientos de diseño de consultas y vistas &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2dca9-120">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](design-queries-and-views-how-to-topics-visual-database-tools.md)  
  
  
