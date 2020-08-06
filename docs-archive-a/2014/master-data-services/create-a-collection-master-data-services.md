---
title: Crear una colección (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating collections [Master Data Services]
- collections [Master Data Services], creating
ms.assetid: 3d4f152c-863c-4385-bca9-a9fcd0402e1f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f76171b4fd9b07f751d4f919011a443253fbe31b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747067"
---
# <a name="create-a-collection-master-data-services"></a><span data-ttu-id="ac18a-102">Crear una colección (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ac18a-102">Create a Collection (Master Data Services)</span></span>
  <span data-ttu-id="ac18a-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cree una colección cuando desee crear listas planas de miembros hoja y consolidados.</span><span class="sxs-lookup"><span data-stu-id="ac18a-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a collection when you want to create flat lists of leaf and consolidated members.</span></span> <span data-ttu-id="ac18a-104">Las colecciones no tienen que incluir todos los miembros de la entidad.</span><span class="sxs-lookup"><span data-stu-id="ac18a-104">Collections do not need to include all members from the entity.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ac18a-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ac18a-105">Prerequisites</span></span>  
 <span data-ttu-id="ac18a-106">Para realizar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="ac18a-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ac18a-107">Debe disponer de permiso de acceso al área funcional **Explorador** .</span><span class="sxs-lookup"><span data-stu-id="ac18a-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="ac18a-108">Como mínimo debe tener el permiso **Actualizar** para el objeto de modelo de colección de la entidad.</span><span class="sxs-lookup"><span data-stu-id="ac18a-108">You must have a minimum of **Update** permission to the collection model object for the entity.</span></span>  
  
-   <span data-ttu-id="ac18a-109">La entidad debe habilitarse para las jerarquías explícitas y las colecciones.</span><span class="sxs-lookup"><span data-stu-id="ac18a-109">The entity must be enabled for explicit hierarchies and collections.</span></span> <span data-ttu-id="ac18a-110">Para obtener más información, vea [habilitar una entidad para jerarquías explícitas y colecciones &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ac18a-110">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
### <a name="to-create-a-collection"></a><span data-ttu-id="ac18a-111">Crear una colección</span><span class="sxs-lookup"><span data-stu-id="ac18a-111">To create a collection</span></span>  
  
1.  <span data-ttu-id="ac18a-112">En la página principal de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , en la lista **Modelo** , seleccione un modelo.</span><span class="sxs-lookup"><span data-stu-id="ac18a-112">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="ac18a-113">En la lista **Versión** , seleccione una versión.</span><span class="sxs-lookup"><span data-stu-id="ac18a-113">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="ac18a-114">Haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="ac18a-114">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="ac18a-115">En la barra de menús, seleccione **Colecciones** y haga clic en *entity_name*.</span><span class="sxs-lookup"><span data-stu-id="ac18a-115">From the menu bar, point to **Collections** and click *entity_name*.</span></span>  
  
5.  <span data-ttu-id="ac18a-116">Haga clic en **Agregar colección**.</span><span class="sxs-lookup"><span data-stu-id="ac18a-116">Click **Add collection**.</span></span>  
  
6.  <span data-ttu-id="ac18a-117">En la pestaña **Detalles** , en el cuadro **Nombre** , escriba un nombre para la colección.</span><span class="sxs-lookup"><span data-stu-id="ac18a-117">On the **Details** tab, in the **Name** box, type a name for the collection.</span></span>  
  
7.  <span data-ttu-id="ac18a-118">En el cuadro **Código** , escriba un código único para la colección.</span><span class="sxs-lookup"><span data-stu-id="ac18a-118">In the **Code** box, type a unique code for the collection.</span></span>  
  
8.  <span data-ttu-id="ac18a-119">Si lo desea, en el cuadro de texto **Descripción** , escriba una descripción de la colección.</span><span class="sxs-lookup"><span data-stu-id="ac18a-119">Optionally, in the **Description** box, type a description for the collection.</span></span>  
  
9. <span data-ttu-id="ac18a-120">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac18a-120">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ac18a-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ac18a-121">Next Steps</span></span>  
  
-   [<span data-ttu-id="ac18a-122">Agregar miembros a una colección &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ac18a-122">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="ac18a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac18a-123">See Also</span></span>  
 <span data-ttu-id="ac18a-124">[Colecciones &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ac18a-124">[Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md) </span></span>  
 <span data-ttu-id="ac18a-125">[Eliminar un miembro o una colección &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ac18a-125">[Delete a Member or Collection &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md) </span></span>  
 [<span data-ttu-id="ac18a-126">Crear una jerarquía explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ac18a-126">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)  
  
  
