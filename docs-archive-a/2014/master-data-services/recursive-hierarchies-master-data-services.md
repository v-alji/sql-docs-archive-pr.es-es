---
title: Jerarquías recursivas (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- recursive hierarchies [Master Data Services]
- hierarchies [Master Data Services], recursive hierarchies
ms.assetid: 9408c6ea-d9c4-4a0b-8a1b-1457fb6944af
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 3c149d500ce1499ad36247d5e32bb6f2d55b4250
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676532"
---
# <a name="recursive-hierarchies-master-data-services"></a><span data-ttu-id="96678-102">Jerarquías recursivas (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="96678-102">Recursive Hierarchies (Master Data Services)</span></span>
  <span data-ttu-id="96678-103">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], una jerarquía recursiva es una jerarquía derivada que incluye una relación recursiva.</span><span class="sxs-lookup"><span data-stu-id="96678-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], a recursive hierarchy is a derived hierarchy that includes a recursive relationship.</span></span> <span data-ttu-id="96678-104">Una relación recursiva existe cuando una entidad tiene un atributo basado en dominio en la propia entidad.</span><span class="sxs-lookup"><span data-stu-id="96678-104">A recursive relationship exists when an entity has a domain-based attribute based on the entity itself.</span></span>

## <a name="recursive-hierarchy-example"></a><span data-ttu-id="96678-105">Ejemplo de jerarquía recursiva</span><span class="sxs-lookup"><span data-stu-id="96678-105">Recursive Hierarchy Example</span></span>
 <span data-ttu-id="96678-106">Un ejemplo de jerarquía recursiva típica es una estructura organizativa.</span><span class="sxs-lookup"><span data-stu-id="96678-106">A typical recursive hierarchy example is an organizational structure.</span></span> <span data-ttu-id="96678-107">En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], esto se haría creando una entidad Empleado con un atributo basado en dominio llamado Administrador.</span><span class="sxs-lookup"><span data-stu-id="96678-107">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you would do this by creating an Employee entity with a domain-based attribute called Manager.</span></span> <span data-ttu-id="96678-108">El atributo Administrador se rellena a partir de la lista de empleados.</span><span class="sxs-lookup"><span data-stu-id="96678-108">The Manager attribute is populated from the list of employees.</span></span> <span data-ttu-id="96678-109">En esta organización de ejemplo, todos los empleados pueden ser administradores.</span><span class="sxs-lookup"><span data-stu-id="96678-109">In this sample organization, all employees can be managers.</span></span>

 <span data-ttu-id="96678-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span><span class="sxs-lookup"><span data-stu-id="96678-110">![mds_conc_recursive_table_w_data](../../2014/master-data-services/media/mds-conc-recursive-table-w-data.gif "mds_conc_recursive_table_w_data")</span></span>

 <span data-ttu-id="96678-111">Puede crear una jerarquía derivada que resalte la relación entre la entidad Empleado y el atributo basado en dominio Administrador.</span><span class="sxs-lookup"><span data-stu-id="96678-111">You can create a derived hierarchy that highlights the relationship between the Employee entity and the Manager domain-based attribute.</span></span>

 <span data-ttu-id="96678-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span><span class="sxs-lookup"><span data-stu-id="96678-112">![mds_conc_recursive_UI_structure](../../2014/master-data-services/media/mds-conc-recursive-ui-structure.gif "mds_conc_recursive_UI_structure")</span></span>

 <span data-ttu-id="96678-113">Para incluir cada miembro en la jerarquía solo una vez, puede delimitar las relaciones nulas.</span><span class="sxs-lookup"><span data-stu-id="96678-113">To include each member in the hierarchy only once, you can anchor null relationships.</span></span> <span data-ttu-id="96678-114">Cuando se hace esto, los miembros con los valores de atributo basado en dominio en blanco se muestran en el nivel superior de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="96678-114">When you do, members with blank domain-based attribute values are displayed at the top level of the hierarchy.</span></span>

 <span data-ttu-id="96678-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span><span class="sxs-lookup"><span data-stu-id="96678-115">![mds_conc_recursive_UI_example_anchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-anchored.gif "mds_conc_recursive_UI_example_anchored")</span></span>

 <span data-ttu-id="96678-116">Si no delimita las relaciones nulas, los miembros se incluyen varias veces.</span><span class="sxs-lookup"><span data-stu-id="96678-116">If you do not anchor null relationships, members are included multiple times.</span></span> <span data-ttu-id="96678-117">Todos los miembros se muestran en el nivel superior.</span><span class="sxs-lookup"><span data-stu-id="96678-117">All members are displayed at the top level.</span></span> <span data-ttu-id="96678-118">También se muestran bajo los miembros de los que son atributos.</span><span class="sxs-lookup"><span data-stu-id="96678-118">They are also displayed under members of which they are attributes.</span></span>

 <span data-ttu-id="96678-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span><span class="sxs-lookup"><span data-stu-id="96678-119">![mds_conc_recursive_UI_example_nonanchored](../../2014/master-data-services/media/mds-conc-recursive-ui-example-nonanchored.gif "mds_conc_recursive_UI_example_nonanchored")</span></span>

 <span data-ttu-id="96678-120">En este ejemplo, Marcia está en el nivel superior.</span><span class="sxs-lookup"><span data-stu-id="96678-120">In this example, Marcia is at the top level.</span></span> <span data-ttu-id="96678-121">No es la administradora de ningún empleado porque no se utiliza como valor de atributo basado en dominio para ningún otro miembro Empleado.</span><span class="sxs-lookup"><span data-stu-id="96678-121">She is not the manager of any employees because she is not used as a domain-based attribute value for any other Employee members.</span></span> <span data-ttu-id="96678-122">Robert, por el contrario, tiene un nivel por debajo porque Marcia tiene a Robert como valor de su atributo Administrador.</span><span class="sxs-lookup"><span data-stu-id="96678-122">Robert, in contrast, has a level beneath him because Marcia has Robert as her Manager attribute value.</span></span>

## <a name="rules"></a><span data-ttu-id="96678-123">Reglas</span><span class="sxs-lookup"><span data-stu-id="96678-123">Rules</span></span>

-   <span data-ttu-id="96678-124">Una jerarquía derivada no puede contener más de una relación recursiva.</span><span class="sxs-lookup"><span data-stu-id="96678-124">A derived hierarchy cannot contain more than one recursive relationship.</span></span> <span data-ttu-id="96678-125">Sin embargo, puede tener otras relaciones derivadas (por ejemplo, una jerarquía derivada que contenga una relación recursiva entre administrador y empleado también puede tener relaciones entre país y administrador y entre empleado y almacén).</span><span class="sxs-lookup"><span data-stu-id="96678-125">It can, however, have other derived relationships (for example, a derived hierarchy that contains a recursive Manager to Employee relationship can also have Country to Manager and Employee to Store relationships).</span></span>

-   <span data-ttu-id="96678-126">No puede asignar permisos de miembro (en la pestaña **Miembros de la jerarquía** ) a los miembros de una jerarquía recursiva.</span><span class="sxs-lookup"><span data-stu-id="96678-126">You cannot assign member permissions (on the **Hierarchy Members** tab) to members in a recursive hierarchy.</span></span>

-   <span data-ttu-id="96678-127">Las jerarquías recursivas no pueden incluir relaciones circulares.</span><span class="sxs-lookup"><span data-stu-id="96678-127">Recursive hierarchies cannot include circular relationships.</span></span> <span data-ttu-id="96678-128">Por ejemplo, Katherine no puede ser administradora de Sandeep si este es su administrador.</span><span class="sxs-lookup"><span data-stu-id="96678-128">For example, Katherine cannot be Sandeep's manager if Sandeep is her manager.</span></span> <span data-ttu-id="96678-129">Asimismo, Katherine no se puede administrar así misma.</span><span class="sxs-lookup"><span data-stu-id="96678-129">Also, Katherine cannot manage herself.</span></span>

## <a name="related-tasks"></a><span data-ttu-id="96678-130">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="96678-130">Related Tasks</span></span>

|<span data-ttu-id="96678-131">Descripción de la tarea</span><span class="sxs-lookup"><span data-stu-id="96678-131">Task Description</span></span>|<span data-ttu-id="96678-132">Tema</span><span class="sxs-lookup"><span data-stu-id="96678-132">Topic</span></span>|
|----------------------|-----------|
|<span data-ttu-id="96678-133">Crear una jerarquía derivada.</span><span class="sxs-lookup"><span data-stu-id="96678-133">Create a derived hierarchy.</span></span>|[<span data-ttu-id="96678-134">Crear una jerarquía derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="96678-134">Create a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](create-a-derived-hierarchy-master-data-services.md)|
|<span data-ttu-id="96678-135">Cambiar el nombre de una jerarquía derivada existente.</span><span class="sxs-lookup"><span data-stu-id="96678-135">Change the name of an existing derived hierarchy.</span></span>|[<span data-ttu-id="96678-136">Cambiar el nombre de una jerarquía derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="96678-136">Change a Derived Hierarchy Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-derived-hierarchy-name-master-data-services.md)|
|<span data-ttu-id="96678-137">Eliminar una jerarquía derivada existente.</span><span class="sxs-lookup"><span data-stu-id="96678-137">Delete an existing derived hierarchy.</span></span>|[<span data-ttu-id="96678-138">Eliminar una jerarquía derivada &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="96678-138">Delete a Derived Hierarchy &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-derived-hierarchy-master-data-services.md)|

## <a name="related-content"></a><span data-ttu-id="96678-139">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="96678-139">Related Content</span></span>

-   [<span data-ttu-id="96678-140">Atributos basados en dominios &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="96678-140">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)

-   [<span data-ttu-id="96678-141">Jerarquías derivadas &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="96678-141">Derived Hierarchies &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/derived-hierarchies-master-data-services.md)


