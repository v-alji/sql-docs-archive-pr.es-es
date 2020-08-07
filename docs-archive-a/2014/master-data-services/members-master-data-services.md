---
title: Miembros (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services]
- consolidated members [Master Data Services]
- consolidated members [Master Data Services], about consolidated members
- members [Master Data Services], about members
- leaf members [Master Data Services], about leaf members
- members [Master Data Services]
ms.assetid: 0fda32b9-677d-4ba2-bb28-f76f2383a30f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 89d2edb21b58575dffc21d9a6470171251889cc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745366"
---
# <a name="members-master-data-services"></a><span data-ttu-id="745d0-102">Miembros (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="745d0-102">Members (Master Data Services)</span></span>
  <span data-ttu-id="745d0-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], los miembros son los datos maestros físicos.</span><span class="sxs-lookup"><span data-stu-id="745d0-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], members are the physical master data.</span></span> <span data-ttu-id="745d0-104">Por ejemplo, un miembro puede ser una bicicleta Road-150 de una entidad Product o un cliente específico de una entidad Customer.</span><span class="sxs-lookup"><span data-stu-id="745d0-104">For example, a member can be a Road-150 bike in a Product entity or a specific customer in a Customer entity.</span></span>

## <a name="how-members-relate-to-other-model-objects"></a><span data-ttu-id="745d0-105">Cómo se relacionan los miembros con otros objetos del modelo</span><span class="sxs-lookup"><span data-stu-id="745d0-105">How Members Relate to Other Model Objects</span></span>
 <span data-ttu-id="745d0-106">Se puede considerar que los miembros son como filas de una tabla.</span><span class="sxs-lookup"><span data-stu-id="745d0-106">You can think of members as rows in a table.</span></span> <span data-ttu-id="745d0-107">Los miembros relacionados están contenidos en una entidad y cada miembro se define mediante valores de atributo.</span><span class="sxs-lookup"><span data-stu-id="745d0-107">Related members are contained in an entity, and each member is defined by attribute values.</span></span>

 <span data-ttu-id="745d0-108">En este ejemplo, la tabla representa una entidad, las filas serían los miembros y las columnas, los atributos.</span><span class="sxs-lookup"><span data-stu-id="745d0-108">In this example, the table represents an entity, the rows in the table represent members, and the columns in the table represent attributes.</span></span> <span data-ttu-id="745d0-109">Cada celda representa un valor de atributo de un miembro concreto.</span><span class="sxs-lookup"><span data-stu-id="745d0-109">Each cell represents an attribute value for a specific member.</span></span>

 <span data-ttu-id="745d0-110">![Entidad de Master Data Services representada como una tabla](../../2014/master-data-services/media/mds-conc-entity-table.gif "Entidad de Master Data Services representada como una tabla")</span><span class="sxs-lookup"><span data-stu-id="745d0-110">![Master Data Services Entity Represented as Table](../../2014/master-data-services/media/mds-conc-entity-table.gif "Master Data Services Entity Represented as Table")</span></span>

## <a name="member-types"></a><span data-ttu-id="745d0-111">Tipos de miembro</span><span class="sxs-lookup"><span data-stu-id="745d0-111">Member Types</span></span>
 <span data-ttu-id="745d0-112">Existen tres tipos de miembros: hoja, consolidados y de colección.</span><span class="sxs-lookup"><span data-stu-id="745d0-112">There are three types of members: leaf members, consolidated members, and collection members.</span></span>

 <span data-ttu-id="745d0-113">Los miembros hoja son los miembros predeterminados en una entidad.</span><span class="sxs-lookup"><span data-stu-id="745d0-113">Leaf members are the default members in an entity.</span></span>

-   <span data-ttu-id="745d0-114">En las jerarquías derivadas, los miembros hoja son el único tipo de miembro.</span><span class="sxs-lookup"><span data-stu-id="745d0-114">In derived hierarchies, leaf members are the only type of member.</span></span> <span data-ttu-id="745d0-115">Los miembros hoja de una entidad se usan como elementos primarios de los miembros hoja de otra entidad.</span><span class="sxs-lookup"><span data-stu-id="745d0-115">Leaf members from one entity are used as parents of leaf members from another entity.</span></span>

-   <span data-ttu-id="745d0-116">En las jerarquías explícitas, los miembros hoja son el nivel más bajo y no pueden tener elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="745d0-116">In explicit hierarchies, leaf members are the lowest level and cannot have children.</span></span>

 <span data-ttu-id="745d0-117">Los miembros consolidados solo existen cuando se habilitan jerarquías explícitas y colecciones para la entidad.</span><span class="sxs-lookup"><span data-stu-id="745d0-117">Consolidated members exist only when explicit hierarchies and collections are enabled for the entity.</span></span>

-   <span data-ttu-id="745d0-118">Las jerarquías derivadas no contienen miembros consolidados.</span><span class="sxs-lookup"><span data-stu-id="745d0-118">Derived hierarchies do not contain consolidated members.</span></span>

-   <span data-ttu-id="745d0-119">En las jerarquías explícitas, los miembros consolidados pueden ser elementos primarios de otros miembros de la jerarquía o pueden ser elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="745d0-119">In explicit hierarchies, consolidated members can be parents of other members within the hierarchy, or they can be children.</span></span>

## <a name="use-hierarchies-and-collections-to-organize-members"></a><span data-ttu-id="745d0-120">Usar jerarquías y colecciones para organizar los miembros</span><span class="sxs-lookup"><span data-stu-id="745d0-120">Use Hierarchies and Collections to Organize Members</span></span>
 <span data-ttu-id="745d0-121">Las jerarquías y las colecciones se pueden usar para agrupar miembros con fines de informes o análisis.</span><span class="sxs-lookup"><span data-stu-id="745d0-121">Hierarchies and collections can be used to group members for reporting or analysis.</span></span> <span data-ttu-id="745d0-122">Para obtener más información, consulte [Jerarquías &#40;Master Data Services&#41;](hierarchies-master-data-services.md) y [Colecciones &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="745d0-122">For more information, see [Hierarchies &#40;Master Data Services&#41;](hierarchies-master-data-services.md) and [Collections &#40;Master Data Services&#41;](../../2014/master-data-services/collections-master-data-services.md).</span></span>

## <a name="member-example"></a><span data-ttu-id="745d0-123">Ejemplo de miembro</span><span class="sxs-lookup"><span data-stu-id="745d0-123">Member Example</span></span>
 <span data-ttu-id="745d0-124">En el ejemplo siguiente, cada miembro se compone de los valores de atributo Name, Code, Subcategory, StandardCost, ListPrice y FilePhoto.</span><span class="sxs-lookup"><span data-stu-id="745d0-124">In the following example, each member is made up of a Name, Code, Subcategory, StandardCost, ListPrice, and FilePhoto attribute value.</span></span>

 <span data-ttu-id="745d0-125">![Tabla de entidades de producto de bicicleta](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Tabla de entidades de producto de bicicleta")</span><span class="sxs-lookup"><span data-stu-id="745d0-125">![Bike Product Entity Table](../../2014/master-data-services/media/mds-conc-entity-table-w-data.gif "Bike Product Entity Table")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="745d0-126">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="745d0-126">Related Tasks</span></span>

|<span data-ttu-id="745d0-127">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="745d0-127">Task Description</span></span>|<span data-ttu-id="745d0-128">Tema</span><span class="sxs-lookup"><span data-stu-id="745d0-128">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="745d0-129">Crear un nuevo miembro hoja.</span><span class="sxs-lookup"><span data-stu-id="745d0-129">Create a new leaf member.</span></span>|[<span data-ttu-id="745d0-130">Crear un miembro hoja &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-130">Create a Leaf Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-leaf-member-master-data-services.md)|
|<span data-ttu-id="745d0-131">Crear un nuevo miembro consolidado.</span><span class="sxs-lookup"><span data-stu-id="745d0-131">Create a new consolidated member.</span></span>|[<span data-ttu-id="745d0-132">Crear un miembro consolidado &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-132">Create a Consolidated Member &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md)|
|<span data-ttu-id="745d0-133">Eliminar un miembro o colección existente.</span><span class="sxs-lookup"><span data-stu-id="745d0-133">Delete an existing member or collection.</span></span>|[<span data-ttu-id="745d0-134">Eliminar un miembro o una colección &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-134">Delete a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="745d0-135">Reactivar un miembro o una colección eliminados.</span><span class="sxs-lookup"><span data-stu-id="745d0-135">Reactivate a deleted member or collection.</span></span>|[<span data-ttu-id="745d0-136">Reactivar un miembro o una colección &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-136">Reactivate a Member or Collection &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/reactivate-a-member-or-collection-master-data-services.md)|
|<span data-ttu-id="745d0-137">Actualizar los valores de atributo de un miembro.</span><span class="sxs-lookup"><span data-stu-id="745d0-137">Update the attribute values of a member.</span></span>|[<span data-ttu-id="745d0-138">Cambar el tipo de atributo &#40;complemento MDS para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-138">Change the Attribute Type &#40;MDS Add-in for Excel&#41;</span></span>](microsoft-excel-add-in/change-the-attribute-type-mds-add-in-for-excel.md)|
|<span data-ttu-id="745d0-139">Mover miembros dentro de una jerarquía.</span><span class="sxs-lookup"><span data-stu-id="745d0-139">Move members within a hierarchy.</span></span>|[<span data-ttu-id="745d0-140">Movimiento de miembros dentro de una jerarquía &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-140">Move Members within a Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/move-members-within-a-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="745d0-141">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="745d0-141">Related Content</span></span>

-   [<span data-ttu-id="745d0-142">Introducción a Master Data Services</span><span class="sxs-lookup"><span data-stu-id="745d0-142">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)

-   [<span data-ttu-id="745d0-143">Entidades &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-143">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)

-   [<span data-ttu-id="745d0-144">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-144">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="745d0-145">Jerarquías &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-145">Hierarchies &#40;Master Data Services&#41;</span></span>](hierarchies-master-data-services.md)

-   [<span data-ttu-id="745d0-146">Colecciones &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-146">Collections &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/collections-master-data-services.md)

-   [<span data-ttu-id="745d0-147">Permisos de hoja &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-147">Leaf Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/leaf-permissions-master-data-services.md)

-   [<span data-ttu-id="745d0-148">Permisos consolidados &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-148">Consolidated Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/consolidated-permissions-master-data-services.md)

-   [<span data-ttu-id="745d0-149">Operadores de filtro &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="745d0-149">Filter Operators &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/filter-operators-master-data-services.md)


