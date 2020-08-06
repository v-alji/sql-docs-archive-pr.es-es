---
title: Agregar atributos a un grupo de seguimiento de cambios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking groups [Master Data Services]
- attributes [Master Data Services], change tracking groups
- change tracking groups [Master Data Services], adding attributes
ms.assetid: e153eb5f-70ca-4c6f-89d8-1f937ed3917d
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c8a13dad3ca886668c96c1886f8cd238d9adad9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677191"
---
# <a name="add-attributes-to-a-change-tracking-group-master-data-services"></a><span data-ttu-id="25a2f-102">Agregar atributos a un grupo de seguimiento de cambios (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="25a2f-102">Add Attributes to a Change Tracking Group (Master Data Services)</span></span>
  <span data-ttu-id="25a2f-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], agregue los atributos a un grupo de seguimiento de cambios cuando desee realizar el seguimiento de los cambios de los valores de atributos.</span><span class="sxs-lookup"><span data-stu-id="25a2f-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], add attributes to a change tracking group when you want to track changes to the attribute's values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="25a2f-104">Después de agregar un atributo a un grupo de seguimiento de cambios, cuando los valores del atributo cambian, el atributo se marca como que ha cambiado en la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="25a2f-104">After you add an attribute to a change tracking group, when values for the attribute change, the attribute is flagged as changed in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="25a2f-105">Cree una regla de negocios para realizar una acción según el cambio.</span><span class="sxs-lookup"><span data-stu-id="25a2f-105">Create a business rule to take action based on the change.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="25a2f-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="25a2f-106">Prerequisites</span></span>  
 <span data-ttu-id="25a2f-107">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="25a2f-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="25a2f-108">Debe disponer de permiso para tener acceso al área funcional de **Administración del sistema** .</span><span class="sxs-lookup"><span data-stu-id="25a2f-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="25a2f-109">Debe ser administrador de modelo.</span><span class="sxs-lookup"><span data-stu-id="25a2f-109">You must be a model administrator.</span></span> <span data-ttu-id="25a2f-110">Para obtener más información, vea [administradores &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="25a2f-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="25a2f-111">Los atributos deben existir para agregarlos al grupo de seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="25a2f-111">Attributes must exist to add to the change tracking group.</span></span> <span data-ttu-id="25a2f-112">Para obtener más información, vea [Crear un atributo de texto &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="25a2f-112">For more information, see [Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md).</span></span>  
  
### <a name="to-add-attributes-to-a-change-tracking-group"></a><span data-ttu-id="25a2f-113">Agregar atributos a un grupo de seguimiento de cambios</span><span class="sxs-lookup"><span data-stu-id="25a2f-113">To add attributes to a change tracking group</span></span>  
  
1.  <span data-ttu-id="25a2f-114">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], haga clic en **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="25a2f-115">En la página **Explorador de modelos** , en la barra de menús, seleccione **administrar** y haga clic en **entidades**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-115">On the **Model Explorer** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="25a2f-116">En la página **Mantenimiento de entidades** , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="25a2f-116">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="25a2f-117">Seleccione la fila correspondiente a la entidad para la que desea realizar el seguimiento de los valores de atributos.</span><span class="sxs-lookup"><span data-stu-id="25a2f-117">Select the row for the entity that you want to track attribute values for.</span></span>  
  
5.  <span data-ttu-id="25a2f-118">Haga clic en **Editar entidad seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-118">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="25a2f-119">En la página **Editar entidad** :</span><span class="sxs-lookup"><span data-stu-id="25a2f-119">On the **Edit Entity** page:</span></span>  
  
    -   <span data-ttu-id="25a2f-120">Si el atributo es para los miembros hoja, en el panel **atributos hoja** , seleccione el atributo y haga clic en **Editar atributo hoja**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-120">If the attribute is for leaf members, in the **Leaf attributes** pane, select the attribute and click **Edit leaf attribute**.</span></span>  
  
    -   <span data-ttu-id="25a2f-121">Si el atributo es para miembros consolidados, en el panel **atributos consolidados** , seleccione el atributo y haga clic en **Editar atributo consolidado**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-121">If the attribute is for consolidated members, in the **Consolidated attributes** pane, select the attribute and click **Edit consolidated attribute**.</span></span>  
  
    -   <span data-ttu-id="25a2f-122">Si el atributo es para colecciones, en el panel **atributos de colección** , seleccione el atributo y haga clic en **Editar atributo de colección**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-122">If the attribute is for collections, in the **Collection attributes** pane, select the attribute and click **Edit collection attribute**.</span></span>  
  
7.  <span data-ttu-id="25a2f-123">Active la casilla **Habilitar seguimiento de cambios** .</span><span class="sxs-lookup"><span data-stu-id="25a2f-123">Select the **Enable change tracking** check box.</span></span>  
  
8.  <span data-ttu-id="25a2f-124">En el cuadro **Grupo de seguimiento de cambios** , escriba un número para el grupo.</span><span class="sxs-lookup"><span data-stu-id="25a2f-124">In the **Change tracking group** box, type a number for the group.</span></span>  
  
9. <span data-ttu-id="25a2f-125">Haga clic en **Guardar atributo**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-125">Click **Save attribute**.</span></span>  
  
10. <span data-ttu-id="25a2f-126">En la página **Mantenimiento de entidades** , haga clic en **Guardar entidad**.</span><span class="sxs-lookup"><span data-stu-id="25a2f-126">On the **Entity Maintenance** page, click **Save entity**.</span></span>  
  
11. <span data-ttu-id="25a2f-127">Repita este procedimiento para todos los atributos que desea incluir en el grupo.</span><span class="sxs-lookup"><span data-stu-id="25a2f-127">Repeat this procedure for all attributes you want to include in the group.</span></span> <span data-ttu-id="25a2f-128">Utilice el mismo número de grupo de seguimiento de cambios para cada atributo del grupo.</span><span class="sxs-lookup"><span data-stu-id="25a2f-128">Use the same change tracking group number for each attribute in the group.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="25a2f-129">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="25a2f-129">Next Steps</span></span>  
  
-   [<span data-ttu-id="25a2f-130">Iniciar acciones según los cambios de valores de atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="25a2f-130">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="25a2f-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25a2f-131">See Also</span></span>  
 <span data-ttu-id="25a2f-132">[Cree un atributo de texto &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="25a2f-132">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="25a2f-133">Crear un atributo basado en dominio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="25a2f-133">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
