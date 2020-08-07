---
title: Colecciones (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- collections [Master Data Services]
- collections [Master Data Services], about collections
ms.assetid: 5aa1d1e0-b4e5-4897-8e74-01dcf418df73
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ce49c57aad5da52dabba32a0f3fb9b6f4f45b209
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745894"
---
# <a name="collections-master-data-services"></a><span data-ttu-id="adbd9-102">Colecciones (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="adbd9-102">Collections (Master Data Services)</span></span>
  <span data-ttu-id="adbd9-103">Una colección es un grupo de miembros hoja y consolidados de una única entidad.</span><span class="sxs-lookup"><span data-stu-id="adbd9-103">A collection is a group of leaf and consolidated members from a single entity.</span></span> <span data-ttu-id="adbd9-104">Use colecciones cuando no necesite una jerarquía completa y desee ver agrupaciones diferentes de los miembros para elaborar informes o análisis o cuando necesite crear una taxonomía.</span><span class="sxs-lookup"><span data-stu-id="adbd9-104">Use collections when you do not need a complete hierarchy and you want to view different groupings of members for reporting or analysis, or when you need to create a taxonomy.</span></span>  
  
## <a name="what-collections-contain"></a><span data-ttu-id="adbd9-105">Qué contienen las colecciones</span><span class="sxs-lookup"><span data-stu-id="adbd9-105">What Collections Contain</span></span>  
 <span data-ttu-id="adbd9-106">Las colecciones no limitan el número o el tipo de miembros que puede incluir, siempre y cuando los miembros pertenezcan a la misma entidad.</span><span class="sxs-lookup"><span data-stu-id="adbd9-106">Collections do not limit the number or type of members you can include, as long as the members are within the same entity.</span></span> <span data-ttu-id="adbd9-107">Una colección puede contener miembros hoja y consolidados de varias jerarquías explícitas obligatorias y no obligatorias.</span><span class="sxs-lookup"><span data-stu-id="adbd9-107">A collection can contain leaf and consolidated members from multiple mandatory and non-mandatory explicit hierarchies.</span></span>  
  
 <span data-ttu-id="adbd9-108">Al crear una colección, no está creando una estructura jerárquica; crea una lista plana de miembros.</span><span class="sxs-lookup"><span data-stu-id="adbd9-108">When you create a collection, you are not creating a hierarchical structure; you are creating a flat list of members.</span></span> <span data-ttu-id="adbd9-109">Al seleccionar un nodo de una jerarquía y agregarlo a la colección, el miembro consolidado seleccionado es el único miembro que se agregará a la colección.</span><span class="sxs-lookup"><span data-stu-id="adbd9-109">When you select a node from a hierarchy and add it to the collection, the consolidated member you selected is the only member added to the collection.</span></span>  
  
 <span data-ttu-id="adbd9-110">Una colección también puede contener otras colecciones.</span><span class="sxs-lookup"><span data-stu-id="adbd9-110">A collection can also contain other collections.</span></span> <span data-ttu-id="adbd9-111">Puede usar colecciones de colecciones para crear taxonomías.</span><span class="sxs-lookup"><span data-stu-id="adbd9-111">You can use collections of collections to create taxonomies.</span></span>  
  
 <span data-ttu-id="adbd9-112">Al crear una colección, aparecerá automáticamente como el propietario.</span><span class="sxs-lookup"><span data-stu-id="adbd9-112">When you create a collection you are automatically listed as the owner.</span></span> <span data-ttu-id="adbd9-113">Si es administrador, puede crear otros atributos para la colección según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="adbd9-113">If you are an administrator, you can create other attributes for your collection as needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="adbd9-114">Antes de poder crear una colección, la entidad debe estar habilitada para las jerarquías explícitas.</span><span class="sxs-lookup"><span data-stu-id="adbd9-114">Before you can create a collection, the entity must be enabled for explicit hierarchies.</span></span> <span data-ttu-id="adbd9-115">Para obtener más información, vea [habilitar una entidad para jerarquías explícitas y colecciones &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="adbd9-115">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>  
  
## <a name="subscription-views-for-collections"></a><span data-ttu-id="adbd9-116">Vistas de suscripciones para colecciones</span><span class="sxs-lookup"><span data-stu-id="adbd9-116">Subscription Views for Collections</span></span>  
 <span data-ttu-id="adbd9-117">Hay dos tipos de vistas de suscripciones que muestran colecciones.</span><span class="sxs-lookup"><span data-stu-id="adbd9-117">There are two types of subscription views that show collections.</span></span> <span data-ttu-id="adbd9-118">El formato **Atributos de colección** muestra una lista de colecciones y todos los atributos relacionados con las colecciones (como la descripción o el propietario).</span><span class="sxs-lookup"><span data-stu-id="adbd9-118">The **Collection attributes** format shows a list of collections and any attributes related to the collections (like description or owner).</span></span> <span data-ttu-id="adbd9-119">El formato **Colecciones** muestra todos los miembros en todas las colecciones, junto con cada ponderación y criterio de ordenación de los miembros.</span><span class="sxs-lookup"><span data-stu-id="adbd9-119">The **Collections** format shows all members in all collections, as well as each members weight and sort order.</span></span> <span data-ttu-id="adbd9-120">Para obtener más información, vea [exportar datos &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="adbd9-120">For more information, see [Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md).</span></span>  
  
 <span data-ttu-id="adbd9-121">Si establece valores de ponderación para los miembros específicos de una colección, estos valores estarán disponibles en las vistas de suscripción relacionadas.</span><span class="sxs-lookup"><span data-stu-id="adbd9-121">If you set weight values for specific members in a collection, these values are available in related subscription views.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="adbd9-122">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="adbd9-122">Related Tasks</span></span>  
  
|<span data-ttu-id="adbd9-123">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="adbd9-123">Task Description</span></span>|<span data-ttu-id="adbd9-124">Tema</span><span class="sxs-lookup"><span data-stu-id="adbd9-124">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="adbd9-125">Habilitar una entidad para colecciones y jerarquías explícitas.</span><span class="sxs-lookup"><span data-stu-id="adbd9-125">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="adbd9-126">Habilitar una entidad para colecciones y jerarquías explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="adbd9-126">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|  
|<span data-ttu-id="adbd9-127">Crear una nueva colección.</span><span class="sxs-lookup"><span data-stu-id="adbd9-127">Create a new collection.</span></span>|[<span data-ttu-id="adbd9-128">Crear una colección &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="adbd9-128">Create a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-collection-master-data-services.md)|  
|<span data-ttu-id="adbd9-129">Agregar miembros a una colección existente.</span><span class="sxs-lookup"><span data-stu-id="adbd9-129">Add members to an existing collection.</span></span>|[<span data-ttu-id="adbd9-130">Agregar miembros a una colección &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="adbd9-130">Add Members to a Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/add-members-to-a-collection-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="adbd9-131">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="adbd9-131">Related Content</span></span>  
  
-   [<span data-ttu-id="adbd9-132">Jerarquías explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="adbd9-132">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)  
  
-   [<span data-ttu-id="adbd9-133">Exportar datos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="adbd9-133">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
