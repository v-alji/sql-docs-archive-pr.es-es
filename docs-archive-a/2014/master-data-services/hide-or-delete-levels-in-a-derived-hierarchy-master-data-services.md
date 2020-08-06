---
title: Ocultar o eliminar niveles en una jerarquía derivada (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, hiding levels
- derived hierarchies, deleting levels
ms.assetid: e00582b9-9415-4b66-b4a7-9f590d83875f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 039b05633bcd1fdc69d226e565b3dc5211e9734f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674178"
---
# <a name="hide-or-delete-levels-in-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="364d9-102">Ocultar o eliminar niveles en una jerarquía derivada (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="364d9-102">Hide or Delete Levels in a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="364d9-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], oculte un nivel en una jerarquía derivada cuando requiera el nivel para agrupar, pero no necesite mostrarlo.</span><span class="sxs-lookup"><span data-stu-id="364d9-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], hide a level in a derived hierarchy when you require the level for grouping but you do not need to show the level.</span></span> <span data-ttu-id="364d9-104">Elimine un nivel cuando no desee usarlo para la agrupación.</span><span class="sxs-lookup"><span data-stu-id="364d9-104">Delete a level when you do not want to use it for grouping.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="364d9-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="364d9-105">Prerequisites</span></span>  
 <span data-ttu-id="364d9-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="364d9-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="364d9-107">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="364d9-107">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="364d9-108">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="364d9-108">You must be a model administrator.</span></span> <span data-ttu-id="364d9-109">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="364d9-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-hide-or-delete-levels-in-a-derived-hierarchy"></a><span data-ttu-id="364d9-110">Para ocultar o eliminar niveles en una jerarquía derivada</span><span class="sxs-lookup"><span data-stu-id="364d9-110">To hide or delete levels in a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="364d9-111">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="364d9-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="364d9-112">En la página **vista de modelo** , en la barra de menús, seleccione **administrar** y haga clic en **jerarquías derivadas**.</span><span class="sxs-lookup"><span data-stu-id="364d9-112">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="364d9-113">En la página **Mantenimiento de jerarquías derivadas** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="364d9-113">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="364d9-114">Seleccione la fila de la jerarquía derivada que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="364d9-114">Select the row for the derived hierarchy you want to edit.</span></span>  
  
5.  <span data-ttu-id="364d9-115">Haga clic en **Editar jerarquía derivada seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="364d9-115">Click **Edit selected derived hierarchy**.</span></span>  
  
6.  <span data-ttu-id="364d9-116">En el panel **Niveles actuales** :</span><span class="sxs-lookup"><span data-stu-id="364d9-116">In the **Current Levels** pane:</span></span>  
  
    -   <span data-ttu-id="364d9-117">Para ocultar un nivel, haga clic en un nivel distinto de la parte superior o inferior.</span><span class="sxs-lookup"><span data-stu-id="364d9-117">To hide a level, click a level other than the top or bottom.</span></span> <span data-ttu-id="364d9-118">En la lista **Visible** , seleccione **No**.</span><span class="sxs-lookup"><span data-stu-id="364d9-118">From the **Visible** list, select **No**.</span></span> <span data-ttu-id="364d9-119">A continuación, haga clic en **Guardar elemento de jerarquía seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="364d9-119">Then click **Save selected hierarchy item**.</span></span>  
  
    -   <span data-ttu-id="364d9-120">Para eliminar el nivel superior, haga clic en **Eliminar elemento de jerarquía seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="364d9-120">To delete the top level, click **Delete selected hierarchy item**.</span></span> <span data-ttu-id="364d9-121">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="364d9-121">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="364d9-122">Solo puede eliminar el nivel superior.</span><span class="sxs-lookup"><span data-stu-id="364d9-122">You can delete the top level only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="364d9-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="364d9-123">See Also</span></span>  
 <span data-ttu-id="364d9-124">[Movimiento de miembros dentro de una jerarquía &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="364d9-124">[Move Members within a Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="364d9-125">Jerarquías derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="364d9-125">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)  
  
  
