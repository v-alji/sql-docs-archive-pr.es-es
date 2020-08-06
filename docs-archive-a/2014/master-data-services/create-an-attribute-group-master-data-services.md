---
title: Crear un grupo de atributos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attribute groups [Master Data Services], creating
- creating attribute groups [Master Data Services]
ms.assetid: 798c325e-e8d8-412a-b02e-118f2741d1c7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fbd95869082ea0a73f3abea092163c4705e4da5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748153"
---
# <a name="create-an-attribute-group-master-data-services"></a><span data-ttu-id="5579e-102">Crear un grupo de atributos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5579e-102">Create an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="5579e-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree grupos de atributos cuando desee mostrar los atributos en pestañas individuales en la cuadrícula **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="5579e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create attribute groups when you want to display attributes on individual tabs in the **Explorer** grid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5579e-104">Cuando se crea un grupo de atributos, se oculta automáticamente para todos los usuarios excepto para la persona que lo creó.</span><span class="sxs-lookup"><span data-stu-id="5579e-104">When you create an attribute group, it is automatically hidden from all users except the one who created it.</span></span> <span data-ttu-id="5579e-105">Para obtener más información sobre cómo hacer visible el grupo, consulte [Hacer que un grupo de atributos sea visible para los usuarios &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5579e-105">For more information about making the group visible, see [Make an Attribute Group Visible to Users &#40;Master Data Services&#41;](make-an-attribute-group-visible-to-users-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5579e-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5579e-106">Prerequisites</span></span>  
 <span data-ttu-id="5579e-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="5579e-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5579e-108">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="5579e-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="5579e-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="5579e-109">You must be a model administrator.</span></span> <span data-ttu-id="5579e-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5579e-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="5579e-111">Por lo menos debe existir un atributo.</span><span class="sxs-lookup"><span data-stu-id="5579e-111">At least one attribute must exist.</span></span> <span data-ttu-id="5579e-112">Para obtener más información, vea [Crear un atributo de texto &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5579e-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-create-an-attribute-group"></a><span data-ttu-id="5579e-113">Para crear un grupo de atributos</span><span class="sxs-lookup"><span data-stu-id="5579e-113">To create an attribute group</span></span>  
  
1.  <span data-ttu-id="5579e-114">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="5579e-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="5579e-115">En la página **vista de modelo** , en la barra de menús, seleccione **administrar** y haga clic en grupos de **atributos**.</span><span class="sxs-lookup"><span data-stu-id="5579e-115">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="5579e-116">En la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="5579e-116">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="5579e-117">En la lista **Entidad** , seleccione una entidad.</span><span class="sxs-lookup"><span data-stu-id="5579e-117">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="5579e-118">Haga clic en **Grupos hoja**, **Grupos consolidados**o **Grupos de colecciones** para crear un grupo de atributos para los miembros hoja, los miembros consolidados o las colecciones, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5579e-118">Click **Leaf Groups**, **Consolidated Groups**, or **Collection Groups** to create an attribute group of leaf members, consolidated members, or collections respectively.</span></span>  
  
6.  <span data-ttu-id="5579e-119">Haga clic en **Agregar grupo de atributos**.</span><span class="sxs-lookup"><span data-stu-id="5579e-119">Click **Add attribute group**.</span></span>  
  
7.  <span data-ttu-id="5579e-120">En el cuadro **nombre de grupo hoja** , escriba un nombre para el grupo.</span><span class="sxs-lookup"><span data-stu-id="5579e-120">In the **Leaf group name** box, type a name for the group.</span></span> <span data-ttu-id="5579e-121">Este es el nombre que se muestra en la pestaña en el **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="5579e-121">This is the name displayed on the tab in **Explorer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5579e-122">Si seleccionó grupos **consolidados** o **grupos de recopilación** en el paso 5, este cuadro es el nombre del **grupo consolidado** o el nombre del grupo de **recopilación**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5579e-122">If you selected **Consolidated Groups** or **Collection Groups** in step 5, this box is **Consolidated group name** or **Collection group name**, respectively.</span></span>  
  
8.  <span data-ttu-id="5579e-123">Haga clic en **Guardar grupo**.</span><span class="sxs-lookup"><span data-stu-id="5579e-123">Click **Save group**.</span></span>  
  
9. <span data-ttu-id="5579e-124">Expanda la carpeta del grupo.</span><span class="sxs-lookup"><span data-stu-id="5579e-124">Expand the folder for the group.</span></span>  
  
10. <span data-ttu-id="5579e-125">Haga clic en **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="5579e-125">Click **Attributes**.</span></span>  
  
11. <span data-ttu-id="5579e-126">Haga clic en **Editar elemento seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="5579e-126">Click **Edit selected item**.</span></span>  
  
12. <span data-ttu-id="5579e-127">Haga clic en atributos en el cuadro **disponible** y haga clic en la flecha **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="5579e-127">Click attributes in the **Available** box and click the **Add** arrow.</span></span> <span data-ttu-id="5579e-128">Para agregarlos todos, haga clic en la flecha **Agregar todo** .</span><span class="sxs-lookup"><span data-stu-id="5579e-128">To add all, click the **Add All** arrow.</span></span>  
  
13. <span data-ttu-id="5579e-129">Opcionalmente, haga clic en las flechas **arriba** y **abajo** para cambiar el orden de izquierda a derecha de los atributos.</span><span class="sxs-lookup"><span data-stu-id="5579e-129">Optionally, click the **Up** and **Down** arrows to change the left-to-right order of the attributes.</span></span>  
  
14. <span data-ttu-id="5579e-130">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="5579e-130">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5579e-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5579e-131">Next Steps</span></span>  
  
-   [<span data-ttu-id="5579e-132">Hacer que un grupo de atributos sea visible para los usuarios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5579e-132">Make an Attribute Group Visible to Users &#40;Master Data Services&#41;</span></span>](make-an-attribute-group-visible-to-users-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="5579e-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5579e-133">See Also</span></span>  
 <span data-ttu-id="5579e-134">[Grupos de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5579e-134">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 <span data-ttu-id="5579e-135">[Atributos &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5579e-135">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="5579e-136">[Cambiar el nombre de un grupo de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5579e-136">[Change an Attribute Group Name &#40;Master Data Services&#41;](../../2014/master-data-services/change-an-attribute-group-name-master-data-services.md) </span></span>  
 <span data-ttu-id="5579e-137">[Eliminar un grupo de atributos &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5579e-137">[Delete an Attribute Group &#40;Master Data Services&#41;](../../2014/master-data-services/delete-an-attribute-group-master-data-services.md) </span></span>  
 <span data-ttu-id="5579e-138">[Permisos de hoja &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5579e-138">[Leaf Permissions &#40;Master Data Services&#41;](../../2014/master-data-services/leaf-permissions-master-data-services.md) </span></span>  
 [<span data-ttu-id="5579e-139">Permisos consolidados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5579e-139">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)  
  
  
