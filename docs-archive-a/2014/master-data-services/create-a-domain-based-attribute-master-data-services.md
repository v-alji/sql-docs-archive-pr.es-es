---
title: Crear un atributo basado en dominio (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], creating
- creating domain-based attributes [Master Data Services]
- attributes [Master Data Services], creating domain-based attributes
ms.assetid: 11c31c9f-e6cc-47b7-b76a-d691f84c93c6
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 51c0f44bb76ae2ad4c25987ed5e5ee144a18c739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669728"
---
# <a name="create-a-domain-based-attribute-master-data-services"></a><span data-ttu-id="715b6-102">Crear un atributo basado en dominio (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="715b6-102">Create a Domain-Based Attribute (Master Data Services)</span></span>
  <span data-ttu-id="715b6-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree un atributo basado en dominios para rellenar los valores de un atributo con los miembros de una entidad.</span><span class="sxs-lookup"><span data-stu-id="715b6-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a domain-based attribute to populate an attribute's values with members from an entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="715b6-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="715b6-104">Prerequisites</span></span>  
 <span data-ttu-id="715b6-105">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="715b6-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="715b6-106">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="715b6-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="715b6-107">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="715b6-107">You must be a model administrator.</span></span> <span data-ttu-id="715b6-108">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="715b6-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="715b6-109">Debe existir una entidad para utilizarse como origen de los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="715b6-109">An entity must exist to use as the source of the attribute values.</span></span> <span data-ttu-id="715b6-110">Por ejemplo, para crear un atributo basado en dominio en la entidad Color, primero debe crear esta.</span><span class="sxs-lookup"><span data-stu-id="715b6-110">For example, to create a domain-based attribute based on the Color entity, you must first create the Color entity.</span></span> <span data-ttu-id="715b6-111">Para obtener más información, vea [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="715b6-111">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="715b6-112">Debe existir una entidad para la que crear el atributo.</span><span class="sxs-lookup"><span data-stu-id="715b6-112">An entity must exist to create the attribute for.</span></span> <span data-ttu-id="715b6-113">Para obtener más información, vea [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="715b6-113">For more information, see [Create an Entity &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-entity-master-data-services.md).</span></span>  
  
### <a name="to-create-a-domain-based-attribute"></a><span data-ttu-id="715b6-114">Crear un atributo basado en dominio</span><span class="sxs-lookup"><span data-stu-id="715b6-114">To create a domain-based attribute</span></span>  
  
1.  <span data-ttu-id="715b6-115">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="715b6-115">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="715b6-116">En la página **Vista de modelo** , en la barra de menús, seleccione **Administrar** y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="715b6-116">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="715b6-117">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="715b6-117">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="715b6-118">Seleccione la fila para la entidad para la que desea crear un atributo.</span><span class="sxs-lookup"><span data-stu-id="715b6-118">Select the row for the entity that you want to create an attribute for.</span></span>  
  
5.  <span data-ttu-id="715b6-119">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="715b6-119">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="715b6-120">En la página **Editar entidad** :</span><span class="sxs-lookup"><span data-stu-id="715b6-120">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="715b6-121">Si el atributo es para miembros hoja, en el panel **Atributos de miembro hoja** , haga clic en **Agregar atributo hoja**.</span><span class="sxs-lookup"><span data-stu-id="715b6-121">If the attribute is for leaf members, in the **Leaf member attributes** pane, click **Add leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="715b6-122">Si el atributo es para miembros consolidados, en el panel **Atributos de miembro consolidados** , haga clic en **Agregar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="715b6-122">If the attribute is for consolidated members, in the **Consolidated member attributes** pane, click **Add consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="715b6-123">Si el atributo es para colecciones, en el panel **Atributos de colección** , haga clic en **Agregar atributo de colección**.</span><span class="sxs-lookup"><span data-stu-id="715b6-123">If the attribute is for collections, in the **Collection attributes** pane, click **Add collection attribute**.</span></span>  
  
7.  <span data-ttu-id="715b6-124">En la página **Agregar atributo** , seleccione la opción **basado en dominio** .</span><span class="sxs-lookup"><span data-stu-id="715b6-124">On the **Add Attribute** page, select the **Domain-based** option.</span></span>  
  
8.  <span data-ttu-id="715b6-125">En el cuadro **Nombre** , escriba un nombre para el atributo.</span><span class="sxs-lookup"><span data-stu-id="715b6-125">In the **Name** box, type a name for the attribute.</span></span> <span data-ttu-id="715b6-126">No tiene que ser el mismo nombre que la entidad que utiliza para el origen de los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="715b6-126">It does not have to be the same name as the entity that you use for the source of the attribute values.</span></span>  
  
9. <span data-ttu-id="715b6-127">En el cuadro **Ancho de píxel de la pantalla** , escriba el ancho de la columna de atributo que se va a mostrar en la cuadrícula del **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="715b6-127">In the **Display pixel width** box, type the width of the attribute column to be displayed in the **Explorer** grid.</span></span>  
  
10. <span data-ttu-id="715b6-128">En la lista **entidad** , elija la entidad que se va a usar para rellenar los valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="715b6-128">From the **Entity** list, choose the entity to be used to populate the attribute values.</span></span>  
  
11. <span data-ttu-id="715b6-129">Opcional.</span><span class="sxs-lookup"><span data-stu-id="715b6-129">Optional.</span></span> <span data-ttu-id="715b6-130">Seleccione **Enable change tracking** para realizar el seguimiento de los cambios en los grupos de atributos.</span><span class="sxs-lookup"><span data-stu-id="715b6-130">Select **Enable change tracking** to track changes to groups of attributes.</span></span> <span data-ttu-id="715b6-131">Para obtener más información, consulte [Agregar atributos a un grupo de seguimiento de cambios &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="715b6-131">For more information, see [Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;](../../2014/master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).</span></span>  
  
12. <span data-ttu-id="715b6-132">Haga clic en **Guardar atributo**.</span><span class="sxs-lookup"><span data-stu-id="715b6-132">Click **Save attribute**.</span></span>  
  
13. <span data-ttu-id="715b6-133">En la página **Mantenimiento de entidades** , haga clic en **Guardar entidad**.</span><span class="sxs-lookup"><span data-stu-id="715b6-133">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="715b6-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="715b6-134">See Also</span></span>  
 <span data-ttu-id="715b6-135">[Atributos basados en dominio &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="715b6-135">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="715b6-136">[Cree una jerarquía derivada &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="715b6-136">[Create a Derived Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md) </span></span>  
 <span data-ttu-id="715b6-137">[Cambiar el nombre de un atributo &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="715b6-137">[Change an Attribute Name &#40;Master Data Services&#41;](change-an-attribute-name-and-data-type-master-data-services.md) </span></span>  
 [<span data-ttu-id="715b6-138">Eliminar un atributo &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="715b6-138">Delete an Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-attribute-master-data-services.md)  
  
  
