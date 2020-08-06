---
title: Eliminar un grupo de atributos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting attribute groups [Master Data Services]
- attribute groups [Master Data Services], deleting
ms.assetid: f915e89b-629d-4725-aea6-a7f051978244
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 833c5cf327034b25d68af123a1fc134372bd6f10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677180"
---
# <a name="delete-an-attribute-group-master-data-services"></a><span data-ttu-id="36567-102">Eliminar un grupo de atributos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="36567-102">Delete an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="36567-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], elimine un grupo de atributos cuando ya no necesite que la pestaña se muestre en el área funcional del **explorador** de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36567-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute group when you no longer need the tab to display in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="36567-104">**Nota** Cuando existan grupos de atributos, los atributos que no pertenezcan a un grupo de atributos no se muestran en el **explorador**.</span><span class="sxs-lookup"><span data-stu-id="36567-104">**Note** When attribute groups exist, attributes that do not belong to an attribute group are not displayed in **Explorer**.</span></span> <span data-ttu-id="36567-105">Cuando no existe ningún grupo de atributos, se muestran todos.</span><span class="sxs-lookup"><span data-stu-id="36567-105">When no attribute groups exist, all attributes are displayed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="36567-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="36567-106">Prerequisites</span></span>  
 <span data-ttu-id="36567-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="36567-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="36567-108">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="36567-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="36567-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="36567-109">You must be a model administrator.</span></span> <span data-ttu-id="36567-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="36567-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute-group"></a><span data-ttu-id="36567-111">Para eliminar un grupo de atributos</span><span class="sxs-lookup"><span data-stu-id="36567-111">To delete an attribute group</span></span>  
  
1.  <span data-ttu-id="36567-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="36567-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="36567-113">En la página **vista de modelo** , en la barra de menús, seleccione **administrar** y haga clic en grupos de **atributos**.</span><span class="sxs-lookup"><span data-stu-id="36567-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="36567-114">En la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="36567-114">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="36567-115">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="36567-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="36567-116">Haga clic en el signo más para expandir **grupos hoja**, **grupos consolidados**o **grupos de recopilación**, según el tipo de grupo que desee eliminar.</span><span class="sxs-lookup"><span data-stu-id="36567-116">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to delete.</span></span>  
  
6.  <span data-ttu-id="36567-117">Haga clic en el grupo de atributos que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="36567-117">Click the attribute group you want to delete.</span></span>  
  
7.  <span data-ttu-id="36567-118">Haga clic en **Eliminar grupo seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="36567-118">Click **Delete selected group**.</span></span>  
  
8.  <span data-ttu-id="36567-119">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="36567-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="36567-120">En el cuadro de diálogo de confirmación adicional, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="36567-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36567-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36567-121">See Also</span></span>  
 <span data-ttu-id="36567-122">[Grupos de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="36567-122">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="36567-123">Crear un grupo de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="36567-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  
