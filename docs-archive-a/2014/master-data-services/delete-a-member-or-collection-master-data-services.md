---
title: Eliminar un miembro o una colección (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services], deleting
- leaf members [Master Data Services], deleting
- deleting members [Master Data Services]
- members [Master Data Services], deleting
- consolidated members [Master Data Services], deleting
ms.assetid: 519130a7-4226-4d71-9124-d2ee0ce7e5bd
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9b248750c0e755c3fc9e32d45068c754e64957b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744168"
---
# <a name="delete-a-member-or-collection-master-data-services"></a><span data-ttu-id="d60c6-102">Eliminar un miembro o una colección (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d60c6-102">Delete a Member or Collection (Master Data Services)</span></span>
  <span data-ttu-id="d60c6-103">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], elimine un miembro o recopilación cuando ya no lo necesite.</span><span class="sxs-lookup"><span data-stu-id="d60c6-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], delete a member or collection when you no longer need it.</span></span> <span data-ttu-id="d60c6-104">Si desea eliminar miembros de forma masiva, utilice el proceso de almacenamiento provisional en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d60c6-104">If you want to delete members in bulk, use the staging process instead.</span></span> <span data-ttu-id="d60c6-105">Para obtener más información, consulte [desactivación o eliminación de miembros mediante el proceso de almacenamiento provisional &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d60c6-105">For more information, see [Deactivate or Delete Members by Using the Staging Process &#40;Master Data Services&#41;](add-update-and-delete-data-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d60c6-106">No puede eliminar un miembro si se utiliza como un valor de atributo basado en dominio para otro miembro.</span><span class="sxs-lookup"><span data-stu-id="d60c6-106">You cannot delete a member if it is used as a domain-based attribute value for another member.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d60c6-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d60c6-107">Prerequisites</span></span>  
 <span data-ttu-id="d60c6-108">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="d60c6-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d60c6-109">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="d60c6-109">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="d60c6-110">Para los miembros, debe tener como mínimo el permiso **Actualizar** para el objeto de modelo hoja del que va a eliminar un miembro.</span><span class="sxs-lookup"><span data-stu-id="d60c6-110">For members, you must have a minimum of **Update** permission to the leaf model object you are deleting a member from.</span></span>  
  
-   <span data-ttu-id="d60c6-111">Para las colecciones, debe tener como mínimo el permiso **Actualizar** en el objeto de colección hoja que vaya a eliminar.</span><span class="sxs-lookup"><span data-stu-id="d60c6-111">For collections, you must have a minimum of **Update** permission to the leaf collection object you are deleting.</span></span>  
  
### <a name="to-delete-a-member-or-collection"></a><span data-ttu-id="d60c6-112">Para eliminar un miembro o colección</span><span class="sxs-lookup"><span data-stu-id="d60c6-112">To delete a member or collection</span></span>  
  
1.  <span data-ttu-id="d60c6-113">En la página principal de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="d60c6-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="d60c6-114">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="d60c6-114">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="d60c6-115">Haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="d60c6-115">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="d60c6-116">Para eliminar:</span><span class="sxs-lookup"><span data-stu-id="d60c6-116">To delete:</span></span>  
  
    -   <span data-ttu-id="d60c6-117">Un miembro hoja, en la barra de menús, seleccione **Entidades** y haga clic en el nombre de la entidad que contenga el miembro.</span><span class="sxs-lookup"><span data-stu-id="d60c6-117">A leaf member, from the menu bar, point to **Entities** and click the name of the entity that contains the member.</span></span>  
  
    -   <span data-ttu-id="d60c6-118">Un miembro consolidado, en la barra de menús, seleccione **Jerarquías** y haga clic en el nombre de la entidad que contenga el miembro.</span><span class="sxs-lookup"><span data-stu-id="d60c6-118">A consolidated member, from the menu bar, point to **Hierarchies** and click the name of the hierarchy that contains the member.</span></span> <span data-ttu-id="d60c6-119">Después, haga clic en el nodo de la jerarquía que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="d60c6-119">Then click the node in the hierarchy that contains the member.</span></span>  
  
    -   <span data-ttu-id="d60c6-120">Una colección, en la barra de menús, elija **Colecciones** y haga clic en el nombre de la entidad que contenga la colección.</span><span class="sxs-lookup"><span data-stu-id="d60c6-120">A collection, from the menu bar, point to **Collections** and click the name of the entity that contains the collection.</span></span>  
  
5.  <span data-ttu-id="d60c6-121">En la cuadrícula, haga clic en la fila correspondiente al miembro o colección que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="d60c6-121">In the grid, click the row of the member or collection you want to delete.</span></span>  
  
6.  <span data-ttu-id="d60c6-122">Haga clic en **Eliminar miembro**, en **Eliminar**o en **Eliminar colección**.</span><span class="sxs-lookup"><span data-stu-id="d60c6-122">Click **Delete Member**, **Delete**, or **Delete Collection**.</span></span>  
  
7.  <span data-ttu-id="d60c6-123">En el cuadro de diálogo de confirmación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d60c6-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60c6-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d60c6-124">See Also</span></span>  
 <span data-ttu-id="d60c6-125">[Reactivar un miembro o colección &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d60c6-125">[Reactivate a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md) </span></span>  
 <span data-ttu-id="d60c6-126">[Miembros &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d60c6-126">[Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) </span></span>  
 [<span data-ttu-id="d60c6-127">Colecciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d60c6-127">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)  
  
  
