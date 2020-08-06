---
title: Jerarquías derivadas con límites explícitos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Master Data Services], derived hierarchies with explicit caps
- explicit hierarchies, derived hierarchies with explicit caps
- derived hierarchies, derived hierarchies with explicit caps
ms.assetid: 6a82ff66-c137-4757-99bb-787d189b4295
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d2460ddf098f0547c2876dd9689f5d2bf9b461a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669718"
---
# <a name="derived-hierarchies-with-explicit-caps-master-data-services"></a><span data-ttu-id="9f1b1-102">Jerarquías derivadas con límites explícitos (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="9f1b1-102">Derived Hierarchies with Explicit Caps (Master Data Services)</span></span>
  <span data-ttu-id="9f1b1-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], el hecho de que los niveles de una jerarquía explícita se utilicen como niveles superiores de una jerarquía derivada, se denomina jerarquía derivada con límites explícitos.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when the levels from an explicit hierarchy are used as the top levels of a derived hierarchy, this is called a derived hierarchy with an explicit cap.</span></span>

 <span data-ttu-id="9f1b1-104">La jerarquía explícita debe estar basada en la misma entidad que la entidad del nivel superior de la jerarquía derivada.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-104">The explicit hierarchy must be based on the same entity as the entity at the top of the derived hierarchy.</span></span>

 <span data-ttu-id="9f1b1-105">En la interfaz de usuario de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , para crear este tipo de jerarquía, arrastre una jerarquía explícita hasta la parte superior de una jerarquía derivada.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-105">In the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface (UI), you create this type of hierarchy by dragging an explicit hierarchy to the top of a derived hierarchy.</span></span>

 <span data-ttu-id="9f1b1-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="9f1b1-106">![mds_conc_explicit_cap_UI_structure](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-structure.gif "mds_conc_explicit_cap_UI_structure")</span></span>

## <a name="derived-hierarchy-with-explicit-cap-example"></a><span data-ttu-id="9f1b1-107">Ejemplo de jerarquía derivada con límite explícito</span><span class="sxs-lookup"><span data-stu-id="9f1b1-107">Derived Hierarchy with Explicit Cap Example</span></span>
 <span data-ttu-id="9f1b1-108">En este ejemplo, los miembros de la jerarquía explícita son los de la entidad Subcategory.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-108">In this example, the members in the explicit hierarchy are from the Subcategory entity.</span></span> <span data-ttu-id="9f1b1-109">En la jerarquía derivada, los miembros de nivel superior también son los de la entidad Subcategory.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-109">In the derived hierarchy, the top-level members are also from the Subcategory entity.</span></span>

 <span data-ttu-id="9f1b1-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span><span class="sxs-lookup"><span data-stu-id="9f1b1-110">![mds_conc_explicit_cap_UI_example](../../2014/master-data-services/media/mds-conc-explicit-cap-ui-example.gif "mds_conc_explicit_cap_UI_example")</span></span>

 <span data-ttu-id="9f1b1-111">Al usar la jerarquía explícita en el nivel superior de una jerarquía derivada, la jerarquía derivada queda desigual.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-111">By using the explicit hierarchy at the top of a derived hierarchy, the derived hierarchy becomes ragged.</span></span>

## <a name="rules"></a><span data-ttu-id="9f1b1-112">Reglas</span><span class="sxs-lookup"><span data-stu-id="9f1b1-112">Rules</span></span>

-   <span data-ttu-id="9f1b1-113">No puede tener más de una jerarquía explícita en una jerarquía derivada con límites explícitos.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-113">You cannot have more than one explicit hierarchy in a derived hierarchy with explicit cap.</span></span>

-   <span data-ttu-id="9f1b1-114">Puede utilizar la misma jerarquía explícita como límite para varias jerarquías derivadas.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-114">You can use the same explicit hierarchy as a cap for multiple derived hierarchies.</span></span>

-   <span data-ttu-id="9f1b1-115">No puede asignar permisos a los miembros de jerarquías derivadas con límites explícitos.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-115">You cannot assign hierarchy member permissions to derived hierarchies with explicit caps.</span></span> <span data-ttu-id="9f1b1-116">Si asigna individualmente permisos a la jerarquía explícita o a la jerarquía derivada, los permisos afectan a ambas.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-116">If you assign permissions to either the explicit hierarchy or the derived hierarchy individually, the permissions affect both hierarchies.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="9f1b1-117">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="9f1b1-117">Related Tasks</span></span>

|<span data-ttu-id="9f1b1-118">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="9f1b1-118">Task Description</span></span>|<span data-ttu-id="9f1b1-119">Tema</span><span class="sxs-lookup"><span data-stu-id="9f1b1-119">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="9f1b1-120">Crear una jerarquía derivada.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-120">Create a derived hierarchy.</span></span>|[<span data-ttu-id="9f1b1-121">Crear una jerarquía derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9f1b1-121">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="9f1b1-122">Crear una jerarquía explícita.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-122">Create an explicit hierarchy.</span></span>|[<span data-ttu-id="9f1b1-123">Crear una jerarquía explícita &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9f1b1-123">Create an Explicit Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-explicit-hierarchy-master-data-services.md)|
|<span data-ttu-id="9f1b1-124">Eliminar una jerarquía derivada existente.</span><span class="sxs-lookup"><span data-stu-id="9f1b1-124">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="9f1b1-125">Eliminar una jerarquía derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9f1b1-125">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|
|||

## <a name="related-content"></a><span data-ttu-id="9f1b1-126">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="9f1b1-126">Related Content</span></span>

-   [<span data-ttu-id="9f1b1-127">Jerarquías derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9f1b1-127">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)

-   [<span data-ttu-id="9f1b1-128">Jerarquías explícitas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9f1b1-128">Explicit Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/explicit-hierarchies-master-data-services.md)


