---
title: Jerarquías (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services]
- hierarchies [Master Data Services], about hierarchies
ms.assetid: 70dbb1fc-ead7-45be-9552-a45e3ccd8d21
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 126a01c03134c6859426c09fda398408694795f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674177"
---
# <a name="hierarchies-master-data-services"></a><span data-ttu-id="c535d-102">Jerarquías (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="c535d-102">Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="c535d-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], una jerarquía es una estructura en forma de árbol que se puede usar para:</span><span class="sxs-lookup"><span data-stu-id="c535d-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a hierarchy is a tree structure that you can use to:</span></span>

-   <span data-ttu-id="c535d-104">Agrupar miembros similares con fines organizativos.</span><span class="sxs-lookup"><span data-stu-id="c535d-104">Group similar members for organizational purposes.</span></span>

-   <span data-ttu-id="c535d-105">Consolidar y resumir miembros para la elaboración de informes y análisis.</span><span class="sxs-lookup"><span data-stu-id="c535d-105">Consolidate and summarize members for reporting and analysis.</span></span>

## <a name="what-hierarchies-contain"></a><span data-ttu-id="c535d-106">Qué contienen las jerarquías</span><span class="sxs-lookup"><span data-stu-id="c535d-106">What Hierarchies Contain</span></span>
 <span data-ttu-id="c535d-107">Cada jerarquía contiene todos los miembros de una o más entidades.</span><span class="sxs-lookup"><span data-stu-id="c535d-107">Each hierarchy contains members from one or more entities.</span></span> <span data-ttu-id="c535d-108">Cuando un miembro se agrega, cambia o elimina, todas las jerarquías se actualizan.</span><span class="sxs-lookup"><span data-stu-id="c535d-108">When a member is added, changed, or deleted, all hierarchies are updated.</span></span> <span data-ttu-id="c535d-109">Esto garantiza que los datos sean exactos en todas las jerarquías.</span><span class="sxs-lookup"><span data-stu-id="c535d-109">This ensures that the data is accurate in all hierarchies.</span></span> <span data-ttu-id="c535d-110">Las jerarquías también ayudan a asegurarse de que cada miembro se cuenta solamente una vez.</span><span class="sxs-lookup"><span data-stu-id="c535d-110">Hierarchies also help ensure that each member is counted once and only once.</span></span>

 <span data-ttu-id="c535d-111">Si desea crear una agrupación de un subconjunto de miembros, considere la posibilidad de usar una colección.</span><span class="sxs-lookup"><span data-stu-id="c535d-111">If you want to create a grouping of a subset of members, consider using a collection.</span></span> <span data-ttu-id="c535d-112">Para obtener más información, consulte [Colecciones &#40;Master Data Services&#41;](collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c535d-112">For more information, see [Collections &#40;Master Data Services&#41;](collections-master-data-services.md).</span></span>

## <a name="kinds-of-hierarchies"></a><span data-ttu-id="c535d-113">Tipos de jerarquías</span><span class="sxs-lookup"><span data-stu-id="c535d-113">Kinds of Hierarchies</span></span>
 <span data-ttu-id="c535d-114">Puede crear varias jerarquías para ver y organizar los miembros de diferentes maneras.</span><span class="sxs-lookup"><span data-stu-id="c535d-114">You can create multiple hierarchies to view and organize your members in different ways.</span></span> <span data-ttu-id="c535d-115">Puede crear:</span><span class="sxs-lookup"><span data-stu-id="c535d-115">You can create:</span></span>

-   <span data-ttu-id="c535d-116">Jerarquías irregulares a partir de una entidad única, que se denominan jerarquías explícitas.</span><span class="sxs-lookup"><span data-stu-id="c535d-116">Ragged hierarchies from a single entity, which are called explicit hierarchies.</span></span> <span data-ttu-id="c535d-117">Para obtener más información, consulte [Jerarquías explícitas &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c535d-117">For more information, see [Explicit Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/explicit-hierarchies-master-data-services.md).</span></span>

-   <span data-ttu-id="c535d-118">Jerarquías basadas en el nivel a partir de varias entidades, basándose en las relaciones existentes entre las entidades y sus atributos, que se denominan jerarquías derivadas.</span><span class="sxs-lookup"><span data-stu-id="c535d-118">Level-based hierarchies from multiple entities, based on the existing relationships between entities and their attributes, which are called derived hierarchies.</span></span> <span data-ttu-id="c535d-119">Para obtener más información, consulte [Jerarquías derivadas &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c535d-119">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="c535d-120">Todos los miembros de una jerarquía deben estar dentro del mismo modelo.</span><span class="sxs-lookup"><span data-stu-id="c535d-120">All members in a hierarchy must be within the same model.</span></span>

## <a name="hierarchies-are-not-taxonomies"></a><span data-ttu-id="c535d-121">Las jerarquías no son taxonomías</span><span class="sxs-lookup"><span data-stu-id="c535d-121">Hierarchies Are Not Taxonomies</span></span>
 <span data-ttu-id="c535d-122">Las jerarquías son distintas a las taxonomías.</span><span class="sxs-lookup"><span data-stu-id="c535d-122">A hierarchy is different from a taxonomy.</span></span> <span data-ttu-id="c535d-123">Una taxonomía organiza los miembros según diversos atributos al mismo tiempo, mientras que una jerarquía organiza los miembros según un atributo cada vez.</span><span class="sxs-lookup"><span data-stu-id="c535d-123">A taxonomy organizes members by multiple attributes at the same time, while a hierarchy organizes members by one attribute at a time.</span></span> <span data-ttu-id="c535d-124">Una taxonomía puede incluir al mismo miembro varias veces, mientras que una jerarquía solo incluye un miembro una vez.</span><span class="sxs-lookup"><span data-stu-id="c535d-124">A taxonomy can include the same member multiple times, while a hierarchy includes a member only once.</span></span>

 <span data-ttu-id="c535d-125">Por ejemplo, la misma bicicleta se puede incluir dos veces en una taxonomía: una vez porque sea roja y otra porque sea de la talla 38.</span><span class="sxs-lookup"><span data-stu-id="c535d-125">For example, the same bike can be included in a taxonomy twice: once because it's red, and once because it's a size 38.</span></span> <span data-ttu-id="c535d-126">En una jerarquía, la bicicleta solo se incluye una vez, por lo que debe decidir si mostrarla en relación con su color o su tamaño.</span><span class="sxs-lookup"><span data-stu-id="c535d-126">In a hierarchy, the bike is included only once, so you must decide whether to show it in relation to its color or its size.</span></span>

## <a name="hierarchy-example"></a><span data-ttu-id="c535d-127">Ejemplo de jerarquía</span><span class="sxs-lookup"><span data-stu-id="c535d-127">Hierarchy Example</span></span>
 <span data-ttu-id="c535d-128">En el ejemplo siguiente, los miembros de Product se agrupan según los miembros de la subcategoría.</span><span class="sxs-lookup"><span data-stu-id="c535d-128">In the following example, product members are grouped by subcategory members.</span></span>

 <span data-ttu-id="c535d-129">![Ejemplo de jerarquía agrupada por subcategoría](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Ejemplo de jerarquía agrupada por subcategoría")</span><span class="sxs-lookup"><span data-stu-id="c535d-129">![Hierarchy Grouped by Subcategory Example](../../2014/master-data-services/media/mds-conc-hierarchy.gif "Hierarchy Grouped by Subcategory Example")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="c535d-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c535d-130">Related Tasks</span></span>

|<span data-ttu-id="c535d-131">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="c535d-131">Task Description</span></span>|<span data-ttu-id="c535d-132">Tema</span><span class="sxs-lookup"><span data-stu-id="c535d-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="c535d-133">Habilitar una entidad para colecciones y jerarquías explícitas.</span><span class="sxs-lookup"><span data-stu-id="c535d-133">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="c535d-134">Habilitar una entidad para colecciones y jerarquías explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c535d-134">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|
|<span data-ttu-id="c535d-135">Crear una jerarquía explícita.</span><span class="sxs-lookup"><span data-stu-id="c535d-135">Create a explicit hierarchy.</span></span>|[<span data-ttu-id="c535d-136">Crear una jerarquía explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c535d-136">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="c535d-137">Crear una jerarquía derivada.</span><span class="sxs-lookup"><span data-stu-id="c535d-137">Create a derived hierarchy.</span></span>|[<span data-ttu-id="c535d-138">Crear una jerarquía derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c535d-138">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="c535d-139">Ocultar o eliminar niveles en una jerarquía derivada existente.</span><span class="sxs-lookup"><span data-stu-id="c535d-139">Hide or delete levels in an existing derived hierarchy.</span></span>|[<span data-ttu-id="c535d-140">Ocultar o eliminar niveles en una jerarquía derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c535d-140">Hide or Delete Levels in a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/hide-or-delete-levels-in-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="c535d-141">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="c535d-141">Related Content</span></span>

-   [<span data-ttu-id="c535d-142">Jerarquías explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c535d-142">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)

-   [<span data-ttu-id="c535d-143">Jerarquías derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c535d-143">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="c535d-144">Jerarquías recursivas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c535d-144">Recursive Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/recursive-hierarchies-master-data-services.md)

-   [<span data-ttu-id="c535d-145">Jerarquías derivadas con límites explícitos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c535d-145">Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md)

-   [<span data-ttu-id="c535d-146">Colecciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c535d-146">Collections &#40;Master Data Services&#41;</span></span>](collections-master-data-services.md)


