---
title: Eliminar una tabla (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: be4ed45f-fde3-466c-9869-49bd3ddb505e
author: minewiskan
ms.author: owend
ms.openlocfilehash: c72fa90426440c1be84318a15cf0d761ef16aca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675511"
---
# <a name="delete-a-table-ssas-tabular"></a><span data-ttu-id="174b0-102">Eliminar una tabla (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="174b0-102">Delete a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="174b0-103">En el diseñador de modelos, puede eliminar las tablas de la base de datos del área de trabajo del modelo que no necesite.</span><span class="sxs-lookup"><span data-stu-id="174b0-103">In the model designer, you can delete tables in your model workspace database that you no longer need.</span></span> <span data-ttu-id="174b0-104">Eliminar una tabla no afecta a los datos de origen originales, solo a los datos que importó y con los que trabajó.</span><span class="sxs-lookup"><span data-stu-id="174b0-104">Deleting a table does not affect the original source data, only the data that you imported and were working with.</span></span> <span data-ttu-id="174b0-105">No puede deshacer la eliminación de una tabla.</span><span class="sxs-lookup"><span data-stu-id="174b0-105">You cannot undo the deletion of a table.</span></span>  
  
### <a name="to-delete-a-table"></a><span data-ttu-id="174b0-106">Para eliminar una tabla</span><span class="sxs-lookup"><span data-stu-id="174b0-106">To delete a table</span></span>  
  
-   <span data-ttu-id="174b0-107">Haga clic con el botón derecho en la pestaña de la parte inferior del diseñador de modelos para la tabla que quiera eliminar y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="174b0-107">Right-click the tab at the bottom of the model designer for the table that you want to delete, and then click **Delete**.</span></span>  
  
## <a name="considerations-when-deleting-tables"></a><span data-ttu-id="174b0-108">Aspectos que se deben tener en cuenta al eliminar tablas</span><span class="sxs-lookup"><span data-stu-id="174b0-108">Considerations when Deleting Tables</span></span>  
  
-   <span data-ttu-id="174b0-109">Al eliminar una tabla, se elimina la pestaña completa en la que estaba la tabla.</span><span class="sxs-lookup"><span data-stu-id="174b0-109">When you delete a table, the entire tab that the table was on is deleted.</span></span>  
  
-   <span data-ttu-id="174b0-110">Si hubiera alguna medida asociada a esa tabla, también se eliminará la definición de la medida.</span><span class="sxs-lookup"><span data-stu-id="174b0-110">If any measures were associated with that table, the definition of the measure will also be deleted.</span></span>  
  
-   <span data-ttu-id="174b0-111">Si creó alguna columna calculada usando esa tabla, también se eliminan las columnas de esa tabla; cualquier columna calculada de otras tablas que usen columnas de la tabla eliminada mostrará un error.</span><span class="sxs-lookup"><span data-stu-id="174b0-111">If you created any calculated columns using that table, columns in that table are also deleted; any calculated columns in other tables that use columns from the deleted table will display an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="174b0-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="174b0-112">See Also</span></span>  
 [<span data-ttu-id="174b0-113">Definir tablas y columnas &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="174b0-113">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tables-and-columns-ssas-tabular.md)  
  
  
