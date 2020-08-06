---
title: Crear un miembro consolidado (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating consolidated members [Master Data Services]
- members [Master Data Services], creating consolidated members
- consolidated members [Master Data Services], creating
ms.assetid: 431ab2d2-5517-4372-9980-142b05427c08
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c41673f6f3bf1f4de2a831ecd659321b273b6af9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747062"
---
# <a name="create-a-consolidated-member-master-data-services"></a><span data-ttu-id="7d428-102">Crear un miembro consolidado (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="7d428-102">Create a Consolidated Member (Master Data Services)</span></span>
  <span data-ttu-id="7d428-103">En [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cree un miembro consolidado si desea un nodo primario para una jerarquía explícita.</span><span class="sxs-lookup"><span data-stu-id="7d428-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a consolidated member when you want a parent node for an explicit hierarchy.</span></span> <span data-ttu-id="7d428-104">Los miembros consolidados pueden tener sus propios atributos.</span><span class="sxs-lookup"><span data-stu-id="7d428-104">Consolidated members can have their own attributes.</span></span> <span data-ttu-id="7d428-105">Se utilizan para la agrupación.</span><span class="sxs-lookup"><span data-stu-id="7d428-105">They are used for grouping.</span></span> <span data-ttu-id="7d428-106">Tal y como se muestra en el ejemplo siguiente, los miembros consolidados pueden usarse para grupos de cuentas que tienen cuentas en ellos.</span><span class="sxs-lookup"><span data-stu-id="7d428-106">As shown in the following example, consolidated members can be used for account groups that have accounts under them.</span></span>

 <span data-ttu-id="7d428-107">![Miembros consolidados de MDS](../../2014/master-data-services/media/mds-consolidated-members.png "Miembros consolidados de MDS")</span><span class="sxs-lookup"><span data-stu-id="7d428-107">![MDS Consolidated Members](../../2014/master-data-services/media/mds-consolidated-members.png "MDS Consolidated Members")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7d428-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7d428-108">Prerequisites</span></span>
 <span data-ttu-id="7d428-109">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="7d428-109">To perform this procedure:</span></span>

-   <span data-ttu-id="7d428-110">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="7d428-110">You must have permission to access the **Explorer** functional area.</span></span>

-   <span data-ttu-id="7d428-111">Como mínimo, debe tener el permiso **Actualizar** para el objeto de modelo consolidado en la entidad a la que vaya a agregar un miembro.</span><span class="sxs-lookup"><span data-stu-id="7d428-111">You must have a minimum of **Update** permission to the consolidated model object for the entity you are adding a member to.</span></span>

### <a name="to-create-a-consolidated-member"></a><span data-ttu-id="7d428-112">Crear un miembro consolidado</span><span class="sxs-lookup"><span data-stu-id="7d428-112">To create a consolidated member</span></span>

1.  <span data-ttu-id="7d428-113">En la página principal de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="7d428-113">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>

2.  <span data-ttu-id="7d428-114">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="7d428-114">From the **Version** list, select a version.</span></span>

3.  <span data-ttu-id="7d428-115">Haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="7d428-115">Click **Explorer**.</span></span>

4.  <span data-ttu-id="7d428-116">En la barra de menús, seleccione **Jerarquías** y haga clic en el nombre de la jerarquía a la que desee agregar un miembro consolidado.</span><span class="sxs-lookup"><span data-stu-id="7d428-116">From the menu bar, point to **Hierarchies** and click the name of the hierarchy you want to add a consolidated member to.</span></span>

5.  <span data-ttu-id="7d428-117">Encima de la cuadrícula, seleccione **Miembros consolidados** o **Todos los miembros consolidados de esta jerarquía** .</span><span class="sxs-lookup"><span data-stu-id="7d428-117">Above the grid, select either the **Consolidated members** or the **All consolidated members in hierarchy** option.</span></span>

6.  <span data-ttu-id="7d428-118">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7d428-118">Click **Add**.</span></span>

7.  <span data-ttu-id="7d428-119">En el panel de la derecha, cumplimente los campos.</span><span class="sxs-lookup"><span data-stu-id="7d428-119">In the pane on the right, complete the fields.</span></span>

8.  <span data-ttu-id="7d428-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7d428-120">Optional.</span></span> <span data-ttu-id="7d428-121">En el cuadro **Anotaciones** , escriba un comentario sobre los motivos por los que se agregó el miembro.</span><span class="sxs-lookup"><span data-stu-id="7d428-121">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="7d428-122">Todos los usuarios que tienen acceso al miembro pueden ver la anotación.</span><span class="sxs-lookup"><span data-stu-id="7d428-122">All users who have access to the member can view the annotation.</span></span>

9. <span data-ttu-id="7d428-123">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d428-123">Click **OK**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d428-124">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7d428-124">Next Steps</span></span>

-   [<span data-ttu-id="7d428-125">Movimiento de miembros dentro de una jerarquía &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7d428-125">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](move-members-within-a-hierarchy-master-data-services.md)

## <a name="see-also"></a><span data-ttu-id="7d428-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d428-126">See Also</span></span>
 <span data-ttu-id="7d428-127">[Cree una jerarquía explícita &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [crear un miembro hoja &#40;Master Data Services](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)&#41;[cargar o actualizar miembros en Master Data Services mediante el uso de los miembros del proceso de almacenamiento provisional](add-update-and-delete-data-master-data-services.md) [Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) &#40;Master Data Services&#41;las [jerarquías explícitas](../../2014/master-data-services/explicit-hierarchies-master-data-services.md) &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="7d428-127">[Create an Explicit Hierarchy &#40;Master Data Services&#41;](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md) [Create a Leaf Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-leaf-member-master-data-services.md) [Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) [Members &#40;Master Data Services&#41;](../../2014/master-data-services/members-master-data-services.md) [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)</span></span>


