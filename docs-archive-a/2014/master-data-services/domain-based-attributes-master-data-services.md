---
title: Atributos basados en dominios (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- domain-based attributes [Master Data Services], about domain-based attributes
- domain-based attributes [Master Data Services]
- attributes [Master Data Services], domain-based attributes
ms.assetid: df6f33ff-97f6-466c-af74-9780b2247473
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9182974923848d49ed3e9ecfb58a14949784a2c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678210"
---
# <a name="domain-based-attributes-master-data-services"></a><span data-ttu-id="0bf66-102">Atributos basados en dominios (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="0bf66-102">Domain-Based Attributes (Master Data Services)</span></span>
  <span data-ttu-id="0bf66-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], un atributo basado en dominio es un atributo con valores rellenados por miembros de otra entidad.</span><span class="sxs-lookup"><span data-stu-id="0bf66-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a domain-based attribute is an attribute with values that are populated by members from another entity.</span></span> <span data-ttu-id="0bf66-104">Se podría considerar que un atributo basado en dominio es una lista restringida; los atributos basados en dominios evitan que los usuarios puede especificar valores de atributo no válidos.</span><span class="sxs-lookup"><span data-stu-id="0bf66-104">You can think of a domain-based attribute as a constrained list; domain-based attributes prevent users from entering attribute values that are not valid.</span></span> <span data-ttu-id="0bf66-105">Para seleccionar un valor de atributo, el usuario debe elegir en una lista.</span><span class="sxs-lookup"><span data-stu-id="0bf66-105">To select an attribute value, the user must pick from a list.</span></span>

## <a name="domain-based-attribute-example"></a><span data-ttu-id="0bf66-106">Ejemplo de atributo basado en dominio</span><span class="sxs-lookup"><span data-stu-id="0bf66-106">Domain-Based Attribute Example</span></span>
 <span data-ttu-id="0bf66-107">En la imagen siguiente, la entidad Product tiene un atributo basado en dominio denominado Subcategory.</span><span class="sxs-lookup"><span data-stu-id="0bf66-107">In the following image, the Product entity has a domain-based attribute called Subcategory.</span></span> <span data-ttu-id="0bf66-108">El atributo Subcategory se rellena con los valores de la entidad Subcategory.</span><span class="sxs-lookup"><span data-stu-id="0bf66-108">The Subcategory attribute is populated by values from the Subcategory entity.</span></span>

 <span data-ttu-id="0bf66-109">La entidad Category tiene un atributo basado en domino denominado Subcategory.</span><span class="sxs-lookup"><span data-stu-id="0bf66-109">The Subcategory entity has a domain-based attribute called Category.</span></span> <span data-ttu-id="0bf66-110">El atributo Category se rellena con los valores de la entidad Category.</span><span class="sxs-lookup"><span data-stu-id="0bf66-110">The Category attribute is populated by values from the Category entity.</span></span>

 <span data-ttu-id="0bf66-111">![Atributos basados en dominio en una entidad](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Atributos basados en dominio en una entidad")</span><span class="sxs-lookup"><span data-stu-id="0bf66-111">![Domain-Based Attributes in an Entity](../../2014/master-data-services/media/mds-conc-domain-based-attribute-conceptual.gif "Domain-Based Attributes in an Entity")</span></span>

## <a name="use-same-entity-for-multiple-domain-based-attributes"></a><span data-ttu-id="0bf66-112">Usar la misma entidad para varios atributos basados en dominios</span><span class="sxs-lookup"><span data-stu-id="0bf66-112">Use Same Entity for Multiple Domain-Based Attributes</span></span>
 <span data-ttu-id="0bf66-113">Puede usar la misma entidad que un atributo basado en dominio de varias entidades.</span><span class="sxs-lookup"><span data-stu-id="0bf66-113">You can use the same entity as a domain-based attribute of multiple entities.</span></span> <span data-ttu-id="0bf66-114">Por ejemplo, puede crear una entidad denominada YesNoIndicator con los miembros Yes, No y Maybe.</span><span class="sxs-lookup"><span data-stu-id="0bf66-114">For example, you can create an entity called YesNoIndicator with the members: Yes, No, and Maybe.</span></span> <span data-ttu-id="0bf66-115">Puede crear un atributo basado en dominio denominado InStock y usar la entidad YesNoIndicator como origen.</span><span class="sxs-lookup"><span data-stu-id="0bf66-115">You can create a domain-based attribute named InStock and use the YesNoIndicator entity as the source.</span></span> <span data-ttu-id="0bf66-116">También puede crear otro atributo basado en dominio denominado Approved y usar la entidad YesNoIndicator como origen.</span><span class="sxs-lookup"><span data-stu-id="0bf66-116">You can also create another domain-based attribute named Approved and use the YesNoIndicator entity as a source.</span></span> <span data-ttu-id="0bf66-117">Siempre que desee que los usuarios elijan en una lista de los miembros de la entidad YesNoIndicator, puede usar la entidad como atributo basado en dominio.</span><span class="sxs-lookup"><span data-stu-id="0bf66-117">Any time you want users to choose from a list of the YesNoIndicator entity's members, you can use the entity as a domain-based attribute.</span></span>

## <a name="domain-based-attributes-form-derived-hierarchies"></a><span data-ttu-id="0bf66-118">Los atributos basados en dominio forman jerarquías derivadas</span><span class="sxs-lookup"><span data-stu-id="0bf66-118">Domain-Based Attributes Form Derived Hierarchies</span></span>
 <span data-ttu-id="0bf66-119">Las relaciones de atributo basados en dominio son la base de las jerarquías derivadas.</span><span class="sxs-lookup"><span data-stu-id="0bf66-119">Domain-based attribute relationships are the basis for derived hierarchies.</span></span> <span data-ttu-id="0bf66-120">Para obtener más información, consulte [Jerarquías derivadas &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0bf66-120">For more information, see [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span></span>

## <a name="related-tasks"></a><span data-ttu-id="0bf66-121">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="0bf66-121">Related Tasks</span></span>

|<span data-ttu-id="0bf66-122">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="0bf66-122">Task Description</span></span>|<span data-ttu-id="0bf66-123">Tema</span><span class="sxs-lookup"><span data-stu-id="0bf66-123">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="0bf66-124">Crear un nuevo atributo basado en dominio originado en una entidad existente.</span><span class="sxs-lookup"><span data-stu-id="0bf66-124">Create a new domain-based attribute that is sourced from an existing entity.</span></span>|[<span data-ttu-id="0bf66-125">Crear un atributo basado en dominio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0bf66-125">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)|
|<span data-ttu-id="0bf66-126">Crear una entidad nueva.</span><span class="sxs-lookup"><span data-stu-id="0bf66-126">Create a new entity.</span></span>|[<span data-ttu-id="0bf66-127">Crear una entidad &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0bf66-127">Create an Entity &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-entity-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="0bf66-128">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="0bf66-128">Related Content</span></span>

-   [<span data-ttu-id="0bf66-129">Jerarquías derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0bf66-129">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="0bf66-130">Atributos &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0bf66-130">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)

-   [<span data-ttu-id="0bf66-131">Entidades &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="0bf66-131">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)


