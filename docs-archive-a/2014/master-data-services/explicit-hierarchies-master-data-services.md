---
title: Jerarquías explícitas (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- explicit hierarchies, about explicit hierarchies
- hierarchies [Master Data Services], explicit hierarchies
- explicit hierarchies
ms.assetid: e6f44e37-e1f0-4c38-a816-1935a856d5a4
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f37f341dc2c003683e696f2767a6b644047d5a0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745875"
---
# <a name="explicit-hierarchies-master-data-services"></a><span data-ttu-id="64d34-102">Jerarquías explícitas (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="64d34-102">Explicit Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="64d34-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], una jerarquía explícita organiza los miembros de una sola entidad de la forma que se especifique.</span><span class="sxs-lookup"><span data-stu-id="64d34-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], an explicit hierarchy organizes members from a single entity in any way you specify.</span></span> <span data-ttu-id="64d34-104">La estructura puede ser irregular y, a diferencia de las jerarquías derivadas, las jerarquías explícitas no se basan en relaciones de atributo basadas en dominio.</span><span class="sxs-lookup"><span data-stu-id="64d34-104">The structure can be ragged and unlike derived hierarchies, explicit hierarchies are not based on domain-based attribute relationships.</span></span>

## <a name="consolidated-members-group-other-members"></a><span data-ttu-id="64d34-105">Los miembros consolidados agrupan a otros miembros</span><span class="sxs-lookup"><span data-stu-id="64d34-105">Consolidated Members Group Other Members</span></span>
 <span data-ttu-id="64d34-106">Una jerarquía explícita usa los miembros consolidados que se crean con el propósito de agrupar a otros miembros.</span><span class="sxs-lookup"><span data-stu-id="64d34-106">An explicit hierarchy uses consolidated members that you create for the purpose of grouping other members.</span></span> <span data-ttu-id="64d34-107">Estos miembros consolidados pueden pertenecer a una sola jerarquía explícita cada vez.</span><span class="sxs-lookup"><span data-stu-id="64d34-107">These consolidated members can belong to only one explicit hierarchy at a time.</span></span> <span data-ttu-id="64d34-108">Una jerarquía explícita también incluye todos los miembros hoja de la entidad asociada.</span><span class="sxs-lookup"><span data-stu-id="64d34-108">An explicit hierarchy also includes all of the leaf members from the associated entity.</span></span>

 <span data-ttu-id="64d34-109">Una jerarquía explícita puede ser desigual, lo que significa que puede terminar simultáneamente en niveles diferentes.</span><span class="sxs-lookup"><span data-stu-id="64d34-109">An explicit hierarchy can be ragged, which means that the hierarchy can end at different levels simultaneously.</span></span> <span data-ttu-id="64d34-110">Cada miembro consolidado puede tener un número ilimitado de miembros consolidados y miembros hoja subordinados, o bien es posible que no tenga ninguno.</span><span class="sxs-lookup"><span data-stu-id="64d34-110">Each consolidated member can have an unlimited number of consolidated and leaf members underneath, or can have none.</span></span> <span data-ttu-id="64d34-111">Los miembros hoja pueden estar subordinados a un solo miembro consolidado o a varios niveles de miembros consolidados.</span><span class="sxs-lookup"><span data-stu-id="64d34-111">The leaf members can be under a single consolidated member or under multiple levels of consolidated members.</span></span>

> [!NOTE]
>  <span data-ttu-id="64d34-112">Antes de poder crear una jerarquía explícita, la entidad debe estar habilitar para jerarquías explícitas.</span><span class="sxs-lookup"><span data-stu-id="64d34-112">Before you can create an explicit hierarchy, the entity must be enabled for explicit hierarchies.</span></span> <span data-ttu-id="64d34-113">Para obtener más información, vea [habilitar una entidad para jerarquías explícitas y colecciones &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="64d34-113">For more information, see [Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md).</span></span>

## <a name="types-of-explicit-hierarchies"></a><span data-ttu-id="64d34-114">Tipos de jerarquías explícitas</span><span class="sxs-lookup"><span data-stu-id="64d34-114">Types of Explicit Hierarchies</span></span>
 <span data-ttu-id="64d34-115">Existen dos tipos de jerarquías explícitas: obligatoria y no obligatoria.</span><span class="sxs-lookup"><span data-stu-id="64d34-115">There are two types of explicit hierarchies: mandatory and non-mandatory.</span></span>

### <a name="mandatory-explicit-hierarchy"></a><span data-ttu-id="64d34-116">Jerarquías explícitas obligatorias</span><span class="sxs-lookup"><span data-stu-id="64d34-116">Mandatory Explicit Hierarchy</span></span>
 <span data-ttu-id="64d34-117">Una jerarquía explícita obligatoria es una jerarquía en la que todos los miembros hoja deben estar incluidos en el árbol de jerarquía.</span><span class="sxs-lookup"><span data-stu-id="64d34-117">A mandatory explicit hierarchy is a hierarchy in which all leaf members must be included in the hierarchy tree.</span></span> <span data-ttu-id="64d34-118">De forma predeterminada, todos los miembros están incluidos en la raíz del árbol.</span><span class="sxs-lookup"><span data-stu-id="64d34-118">By default, all members are included at the root of the tree.</span></span> <span data-ttu-id="64d34-119">Puede reorganizar los miembros según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="64d34-119">You can rearrange the members as needed.</span></span>

### <a name="non-mandatory-explicit-hierarchy"></a><span data-ttu-id="64d34-120">Jerarquías explícitas no obligatorias</span><span class="sxs-lookup"><span data-stu-id="64d34-120">Non-Mandatory Explicit Hierarchy</span></span>
 <span data-ttu-id="64d34-121">Una jerarquía explícita no obligatoria es una jerarquía en la que todos los miembros hoja están en un nodo **No utilizado** creado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="64d34-121">A non-mandatory explicit hierarchy is a hierarchy in which all leaf members are in a system-created **Unused** node.</span></span> <span data-ttu-id="64d34-122">Puede sacar los miembros del nodo según los vaya necesitando.</span><span class="sxs-lookup"><span data-stu-id="64d34-122">You can move members out of this node as you need them.</span></span> <span data-ttu-id="64d34-123">El resto de los miembros puede permanecer en el nodo **No utilizado** .</span><span class="sxs-lookup"><span data-stu-id="64d34-123">The rest of the members can remain in the **Unused** node.</span></span>

 <span data-ttu-id="64d34-124">Cuando utilice jerarquías explícitas no obligatorias, recuerde que cualquier informe o análisis que se realice en la jerarquía no puede coincidir con los informes o análisis realizados en las jerarquías obligatorias.</span><span class="sxs-lookup"><span data-stu-id="64d34-124">When you use non-mandatory explicit hierarchies, any reporting or analysis done on the hierarchy may not match reporting or analysis done on mandatory hierarchies.</span></span>

## <a name="rules"></a><span data-ttu-id="64d34-125">Reglas</span><span class="sxs-lookup"><span data-stu-id="64d34-125">Rules</span></span>
 <span data-ttu-id="64d34-126">Las siguientes reglas se aplican a las jerarquías explícitas (tanto las obligatorias como las no obligatorias).</span><span class="sxs-lookup"><span data-stu-id="64d34-126">The following rules apply to explicit hierarchies (both mandatory and non-mandatory).</span></span>

-   <span data-ttu-id="64d34-127">Cada miembro hoja solo puede estar incluido una vez en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="64d34-127">Each leaf member can be included in the hierarchy only once.</span></span>

-   <span data-ttu-id="64d34-128">Es preciso que todos los miembros consolidados estén incluidos en una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="64d34-128">All consolidated members must be included in a hierarchy.</span></span>

-   <span data-ttu-id="64d34-129">Los miembros consolidados no pueden estar en más de una jerarquía explícita.</span><span class="sxs-lookup"><span data-stu-id="64d34-129">Consolidated members cannot be in more than one explicit hierarchy.</span></span>

-   <span data-ttu-id="64d34-130">Los miembros consolidados en el árbol de jerarquía no tienen que tener miembros hoja subordinados.</span><span class="sxs-lookup"><span data-stu-id="64d34-130">Consolidated members in the hierarchy tree do not have to contain leaf members underneath them.</span></span>

-   <span data-ttu-id="64d34-131">Si elimina una jerarquía explícita, se eliminarán todos los miembros consolidados que hayan utilizado en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="64d34-131">If you delete an explicit hierarchy, all consolidated members that were used in the hierarchy are deleted.</span></span>

-   <span data-ttu-id="64d34-132">Si elimina un miembro consolidado que estaba en una jerarquía explícita, todos los miembros hoja que estaban agrupados por ese miembro consolidado se mueven a la raíz.</span><span class="sxs-lookup"><span data-stu-id="64d34-132">If you delete a consolidated member that was in an explicit hierarchy, all leaf members that were grouped by that consolidated member are moved to the root.</span></span>

## <a name="explicit-hierarchies-versus-derived-hierarchies"></a><span data-ttu-id="64d34-133">Jerarquías explícitas frente a jerarquías derivadas</span><span class="sxs-lookup"><span data-stu-id="64d34-133">Explicit Hierarchies versus Derived Hierarchies</span></span>
 <span data-ttu-id="64d34-134">En la tabla siguiente se muestran algunas de las diferencias existentes entre las jerarquías explícitas y las jerarquías derivadas.</span><span class="sxs-lookup"><span data-stu-id="64d34-134">The following table shows some of the differences between explicit and derived hierarchies.</span></span>

|<span data-ttu-id="64d34-135">Jerarquías explícitas</span><span class="sxs-lookup"><span data-stu-id="64d34-135">Explicit Hierarchies</span></span>|<span data-ttu-id="64d34-136">Jerarquías derivadas</span><span class="sxs-lookup"><span data-stu-id="64d34-136">Derived Hierarchies</span></span>|
|--------------------------|-------------------------|
|<span data-ttu-id="64d34-137">La estructura la define el usuario</span><span class="sxs-lookup"><span data-stu-id="64d34-137">Structure is defined by the user</span></span>|<span data-ttu-id="64d34-138">La estructura se deriva de las relaciones entre los atributos basados en dominio</span><span class="sxs-lookup"><span data-stu-id="64d34-138">Structure is derived from the relationships between domain-based attributes</span></span>|
|<span data-ttu-id="64d34-139">Contiene miembros de una sola entidad</span><span class="sxs-lookup"><span data-stu-id="64d34-139">Contains members from a single entity</span></span>|<span data-ttu-id="64d34-140">Contiene miembros de varias entidades</span><span class="sxs-lookup"><span data-stu-id="64d34-140">Contains members from multiple entities</span></span>|
|<span data-ttu-id="64d34-141">Usa miembros consolidados para agrupar a otros miembros</span><span class="sxs-lookup"><span data-stu-id="64d34-141">Uses consolidated members to group other members</span></span>|<span data-ttu-id="64d34-142">Usa miembros hoja de una entidad para agrupar miembros hoja de otra entidad</span><span class="sxs-lookup"><span data-stu-id="64d34-142">Uses leaf members from one entity to group leaf members from another entity</span></span>|
|<span data-ttu-id="64d34-143">Puede ser desigual</span><span class="sxs-lookup"><span data-stu-id="64d34-143">Can be ragged</span></span>|<span data-ttu-id="64d34-144">Siempre contiene un número coherente de niveles</span><span class="sxs-lookup"><span data-stu-id="64d34-144">Always contains a consistent number of levels</span></span>|

## <a name="explicit-hierarchy-example"></a><span data-ttu-id="64d34-145">Ejemplo de jerarquía explícita</span><span class="sxs-lookup"><span data-stu-id="64d34-145">Explicit Hierarchy Example</span></span>
 <span data-ttu-id="64d34-146">En el ejemplo siguiente, la entidad Product contiene estos miembros hoja: BK-M101 {Mountain-100}, BK-M201 {Mountain-200}, BK-M301 {Mountain-300}, BK-R150 {Road-150}, BK-R450 {Road-450} y BK-R650 {Road-650}.</span><span class="sxs-lookup"><span data-stu-id="64d34-146">In the following example, the Product entity contains these leaf members: BK-M101 {Mountain-100}, BK-M201 {Mountain-200}, BK-M301 {Mountain-300}, BK-R150 {Road-150}, BK-R450 {Road-450}, and BK-R650 {Road-650}.</span></span>

 <span data-ttu-id="64d34-147">Para resumir estos miembros hoja en puntos específicos de consolidación, puede crear miembros consolidados en la entidad Product.</span><span class="sxs-lookup"><span data-stu-id="64d34-147">To summarize these leaf members at specific consolidation points, you can create consolidated members in the Product entity.</span></span> <span data-ttu-id="64d34-148">Inserte los miembros consolidados en los niveles del árbol de jerarquía donde desea resumir los miembros hoja.</span><span class="sxs-lookup"><span data-stu-id="64d34-148">Insert the consolidated members at levels in the hierarchy tree where you want to summarize the leaf members.</span></span> <span data-ttu-id="64d34-149">No existe limitación alguna con respecto al lugar donde insertar los miembros consolidados; sin embargo, solo puede utilizar cada miembro (hoja o consolidado) una vez.</span><span class="sxs-lookup"><span data-stu-id="64d34-149">There is no limitation on where you insert your consolidated members; however, each member (leaf or consolidated) can be used only once.</span></span>

 <span data-ttu-id="64d34-150">![Ejemplo de jerarquía explícita de bicicleta de montaña](../../2014/master-data-services/media/mds-conc-explicit-hierarchy.gif "Ejemplo de jerarquía explícita de bicicleta de montaña")</span><span class="sxs-lookup"><span data-stu-id="64d34-150">![Mountain Bike Explicit Hierarchy Example](../../2014/master-data-services/media/mds-conc-explicit-hierarchy.gif "Mountain Bike Explicit Hierarchy Example")</span></span>

 <span data-ttu-id="64d34-151">Los miembros consolidados se pueden usar para agrupar miembros en cualquier nivel, y los miembros hoja y consolidados se ordenan según se determine.</span><span class="sxs-lookup"><span data-stu-id="64d34-151">Consolidated members can be used to group members at any level, and leaf and consolidated members are sorted in the order you determine.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="64d34-152">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="64d34-152">Related Tasks</span></span>

|<span data-ttu-id="64d34-153">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="64d34-153">Task Description</span></span>|<span data-ttu-id="64d34-154">Tema</span><span class="sxs-lookup"><span data-stu-id="64d34-154">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="64d34-155">Habilitar una entidad para colecciones y jerarquías explícitas.</span><span class="sxs-lookup"><span data-stu-id="64d34-155">Enable an entity for explicit hierarchies and collections.</span></span>|[<span data-ttu-id="64d34-156">Habilitar una entidad para colecciones y jerarquías explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="64d34-156">Enable an Entity for Explicit Hierarchies and Collections &#40;Master Data Services&#41;</span></span>](enable-an-entity-for-explicit-hierarchies-and-collections-master-data-services.md)|
|<span data-ttu-id="64d34-157">Crear una nueva jerarquía explícita.</span><span class="sxs-lookup"><span data-stu-id="64d34-157">Create a new explicit hierarchy.</span></span>|[<span data-ttu-id="64d34-158">Crear una jerarquía explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="64d34-158">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="64d34-159">Cambiar el nombre de una jerarquía explícita existente.</span><span class="sxs-lookup"><span data-stu-id="64d34-159">Change the name of an existing explicity hierarchy.</span></span>|[<span data-ttu-id="64d34-160">Crear un nombre de jerarquía explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="64d34-160">Change an Explicit Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-an-explicit-hierarchy-name-master-data-services.md)|
|<span data-ttu-id="64d34-161">Eliminar una jerarquía explícita existente.</span><span class="sxs-lookup"><span data-stu-id="64d34-161">Delete an existing explicit hierarchy.</span></span>|[<span data-ttu-id="64d34-162">Eliminar una jerarquía explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="64d34-162">Delete an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-an-explicit-hierarchy-master-data-services.md)|
|||

## <a name="related-content"></a><span data-ttu-id="64d34-163">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="64d34-163">Related Content</span></span>

-   [<span data-ttu-id="64d34-164">Jerarquías derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="64d34-164">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="64d34-165">Colecciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="64d34-165">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)


