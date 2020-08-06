---
title: Eliminar una jerarquía explícita (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, deleting
- deleting explicit hierarchies [Master Data Services]
ms.assetid: 4ce177b0-9884-47a2-9cea-212e845dd762
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 744f96a2705a3abbc2318ecd3c9b0c7fffb7605e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678228"
---
# <a name="delete-an-explicit-hierarchy-master-data-services"></a><span data-ttu-id="0e969-102">Eliminar una jerarquía explícita (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0e969-102">Delete an Explicit Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="0e969-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], elimine una jerarquía explícita cuando ya no la necesite.</span><span class="sxs-lookup"><span data-stu-id="0e969-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an explicit hierarchy when you no longer need it.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="0e969-104">Cuando elimine una jerarquía explícita, se eliminarán también todos los miembros consolidados de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="0e969-104">When you delete an explicit hierarchy, all consolidated members in the hierarchy are deleted also.</span></span> <span data-ttu-id="0e969-105">Si elimina todas las jerarquías explícitas de una entidad, también se eliminarían todas las recopilaciones de la entidad y la entidad dejaría de estar habilitada para las jerarquías explícitas y las recopilaciones.</span><span class="sxs-lookup"><span data-stu-id="0e969-105">If you delete all explicit hierarchies for an entity, all collections for the entity are also deleted and the entity is no longer enabled for explicit hierarchies and collections.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0e969-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0e969-106">Prerequisites</span></span>  
 <span data-ttu-id="0e969-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="0e969-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="0e969-108">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="0e969-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="0e969-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="0e969-109">You must be a model administrator.</span></span> <span data-ttu-id="0e969-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0e969-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-explicit-hierarchy"></a><span data-ttu-id="0e969-111">Eliminar una jerarquía explícita</span><span class="sxs-lookup"><span data-stu-id="0e969-111">To delete an explicit hierarchy</span></span>  
  
1.  <span data-ttu-id="0e969-112">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="0e969-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="0e969-113">En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="0e969-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="0e969-114">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="0e969-114">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="0e969-115">Seleccione la fila correspondiente a la entidad que contenga la jerarquía explícita que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="0e969-115">Select the row for the entity that contains the explicit hierarchy you want to delete.</span></span>  
  
5.  <span data-ttu-id="0e969-116">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="0e969-116">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="0e969-117">En la página **Editar entidad** , en el panel **jerarquías explícitas** , haga clic en la jerarquía explícita que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="0e969-117">On the **Edit Entity** page, in the **Explicit Hierarchies** pane, click the explicit hierarchy you want to delete.</span></span>  
  
7.  <span data-ttu-id="0e969-118">Haga clic en **eliminar jerarquía seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="0e969-118">Click **Delete selected hierarchy**.</span></span>  
  
8.  <span data-ttu-id="0e969-119">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e969-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="0e969-120">En el cuadro de diálogo de confirmación adicional, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e969-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e969-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e969-121">See Also</span></span>  
 <span data-ttu-id="0e969-122">[Cree una jerarquía explícita &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="0e969-122">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) </span></span>  
 [<span data-ttu-id="0e969-123">Jerarquías explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0e969-123">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
  
