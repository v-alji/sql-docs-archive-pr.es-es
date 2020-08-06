---
title: Eliminar relaciones (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d40e3f05-54e8-4c4b-807a-0b06f446079b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c63324918eb6919ce0abd65b5ee0765f9d7243b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744380"
---
# <a name="delete-relationships-ssas-tabular"></a><span data-ttu-id="82075-102">Eliminar relaciones (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="82075-102">Delete Relationships (SSAS Tabular)</span></span>
  <span data-ttu-id="82075-103">Puede eliminar las relaciones existentes utilizando el diseñador de modelos en la Vista de diagrama o utilizando el cuadro de diálogo Administrar relaciones.</span><span class="sxs-lookup"><span data-stu-id="82075-103">You can delete existing relationships by using the model designer in Diagram View or by using the Manage Relationships dialog box.</span></span> <span data-ttu-id="82075-104">Para más información sobre cómo se usan las relaciones en los modelos tabulares, vea [Relaciones &#40;SSAS tabular&#41;](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="82075-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="considerations-for-deleting-relationships"></a><span data-ttu-id="82075-105">Aspectos que se deben tener en cuenta al eliminar relaciones</span><span class="sxs-lookup"><span data-stu-id="82075-105">Considerations for Deleting Relationships</span></span>  
 <span data-ttu-id="82075-106">Tenga en cuenta los siguientes problemas a la hora de decidir si va a eliminar una relación:</span><span class="sxs-lookup"><span data-stu-id="82075-106">Keep the following issues in mind when deciding whether to delete a relationship:</span></span>  
  
-   <span data-ttu-id="82075-107">No hay ninguna manera de deshacer la eliminación de una relación.</span><span class="sxs-lookup"><span data-stu-id="82075-107">There is no way to undo the deletion of a relationship.</span></span> <span data-ttu-id="82075-108">Puede volver a crearla, pero esta acción requiere que se vuelvan a calcular completamente las fórmulas del modelo.</span><span class="sxs-lookup"><span data-stu-id="82075-108">You can re-create the relationship, but this action requires a complete recalculation of formulas in the model.</span></span> <span data-ttu-id="82075-109">Por consiguiente, compruebe siempre si una relación se usa en fórmulas antes de eliminarla.</span><span class="sxs-lookup"><span data-stu-id="82075-109">Therefore, always check first before deleting a relationship that is used in formulas.</span></span>  
  
-   <span data-ttu-id="82075-110">Eliminar una relación entre dos tablas puede provocar errores en las fórmulas que hacen referencia a estas tablas.</span><span class="sxs-lookup"><span data-stu-id="82075-110">Deleting a relationship between two tables can cause errors in formulas that reference these tables.</span></span>  
  
-   <span data-ttu-id="82075-111">La función RELATED de las Expresiones de análisis de datos (DAX) usa las relaciones entre tablas para buscar valores relacionados en otra tabla.</span><span class="sxs-lookup"><span data-stu-id="82075-111">The Data Analysis Expression (DAX) RELATED function uses the relationships between tables to look up related values in another table.</span></span> <span data-ttu-id="82075-112">Devolverá resultados diferentes una vez eliminada la relación.</span><span class="sxs-lookup"><span data-stu-id="82075-112">It will return different results after the relationship is deleted.</span></span> <span data-ttu-id="82075-113">Para obtener más información, vea la función RELATED (DAX).</span><span class="sxs-lookup"><span data-stu-id="82075-113">For more information, see the RELATED Function (DAX).</span></span>  
  
-   <span data-ttu-id="82075-114">Además de cambiar los resultados de las fórmulas y las tablas dinámicas, tanto la creación como la eliminación de relaciones harán que el libro se vuelva a calcular, lo que puede tardar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="82075-114">In addition to changing PivotTable and formula results, both the creation and deletion of relationships will cause the workbook to be recalculated, which can take some time.</span></span>  
  
## <a name="delete-relationships"></a><span data-ttu-id="82075-115">Eliminar relaciones</span><span class="sxs-lookup"><span data-stu-id="82075-115">Delete Relationships</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-diagram-view"></a><span data-ttu-id="82075-116">Para eliminar una relación utilizando la Vista de diagrama</span><span class="sxs-lookup"><span data-stu-id="82075-116">To delete a relationship by using Diagram View</span></span>  
  
1.  <span data-ttu-id="82075-117">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga clic en el menú **Modelo** , elija **Vista de modelo**y haga clic en **Vista de diagrama**.</span><span class="sxs-lookup"><span data-stu-id="82075-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="82075-118">Haga clic con el botón derecho en una línea de relación entre dos tablas y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="82075-118">Right-click a relationship line between two tables, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-the-manage-relationships-dialog-box"></a><span data-ttu-id="82075-119">Para eliminar una relación utilizando el cuadro de diálogo Administrar relaciones</span><span class="sxs-lookup"><span data-stu-id="82075-119">To delete a relationship by using the Manage Relationships dialog box</span></span>  
  
1.  <span data-ttu-id="82075-120">En [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], haga clic en el menú **Tabla** y, a continuación, haga clic en **Administrar relaciones**.</span><span class="sxs-lookup"><span data-stu-id="82075-120">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Manage Relationships**.</span></span>  
  
2.  <span data-ttu-id="82075-121">En el cuadro de diálogo **Administrar relaciones** , seleccione una o más relaciones en la lista.</span><span class="sxs-lookup"><span data-stu-id="82075-121">In the **Manage Relationships** dialog box, select one or more relationships from the list.</span></span>  
  
     <span data-ttu-id="82075-122">Para seleccionar varias relaciones, mantenga presionada la tecla CTRL mientras hace clic en cada una.</span><span class="sxs-lookup"><span data-stu-id="82075-122">To select multiple relationships, hold down CTRL while you click each relationship.</span></span>  
  
3.  <span data-ttu-id="82075-123">Haga clic en **Eliminar relación**.</span><span class="sxs-lookup"><span data-stu-id="82075-123">Click **Delete Relationship**.</span></span>  
  
4.  <span data-ttu-id="82075-124">En el cuadro de diálogo **Administrar las relaciones** , haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="82075-124">In the **Manage Relationships** dialog box, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82075-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82075-125">See Also</span></span>  
 <span data-ttu-id="82075-126">[Relaciones &#40;&#41;tabular de SSAS](relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="82075-126">[Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="82075-127">Crear una relación entre dos tablas &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="82075-127">Create a Relationship Between Two Tables &#40;SSAS Tabular&#41;</span></span>](create-a-relationship-between-two-tables-ssas-tabular.md)  
  
  
