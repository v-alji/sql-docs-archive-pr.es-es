---
title: 'Lección 4: definir propiedades de dimensiones y atributos avanzados | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0e86b9be-e47d-4bb4-87eb-136ff3a61aef
author: minewiskan
ms.author: owend
ms.openlocfilehash: deb2d9c40ad5024f6cc4ba6e9148df41a168c6e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747235"
---
# <a name="lesson-4-defining-advanced-attribute-and-dimension-properties"></a><span data-ttu-id="30723-102">Lección 4: Definir propiedades de dimensiones y de atributos avanzados</span><span class="sxs-lookup"><span data-stu-id="30723-102">Lesson 4: Defining Advanced Attribute and Dimension Properties</span></span>
  <span data-ttu-id="30723-103">En esta lección, aprenderá a utilizar algunas de las propiedades avanzadas de atributos, jerarquías de atributos y propiedades de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="30723-103">In this lesson, you will learn how to use some of the advanced properties of attributes, attribute hierarchies, and dimension properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30723-104">Esta lección se basa en una versión mejorada del proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que completó en las tres primeras lecciones de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="30723-104">This lesson is based on an enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons of this tutorial.</span></span> <span data-ttu-id="30723-105">En la primera tarea de esta lección se describe dónde buscar el proyecto de ejemplo adecuado que debe utilizar para la lección, así como la diferencia existente entre este proyecto y el proyecto que ha creado en las tres primeras lecciones.</span><span class="sxs-lookup"><span data-stu-id="30723-105">The first task in this lesson describes where to locate the appropriate sample project to use for the lesson, and the difference between this project and the project that you created in the first three lessons.</span></span>  
  
 <span data-ttu-id="30723-106">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="30723-106">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="30723-107">Usar una versión modificada del proyecto Tutorial de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="30723-107">Using a Modified Version of the Analysis Services Tutorial Project</span></span>](lesson-4-1-using-a-modified-version-of-the-analysis-services-tutorial-project.md)  
 <span data-ttu-id="30723-108">En esta tarea, abrirá, revisará e implementará una versión modificada del proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , que tiene varios grupos de medidas y dimensiones adicionales.</span><span class="sxs-lookup"><span data-stu-id="30723-108">In this task, you open, review, and deploy a modified version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, which has multiple measure groups and additional dimensions.</span></span>  
  
 [<span data-ttu-id="30723-109">Definir propiedades de atributo primario en una jerarquía de elementos primarios y secundarios</span><span class="sxs-lookup"><span data-stu-id="30723-109">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>](lesson-4-2-defining-parent-attribute-properties-in-a-parent-child-hierarchy.md)  
 <span data-ttu-id="30723-110">En esta tarea, definirá los nombres de nivel de una dimensión primaria-secundaria y especificará si deben mostrarse los datos relacionados con los miembros primarios.</span><span class="sxs-lookup"><span data-stu-id="30723-110">In this task, you define level names in a parent-child dimension and specify whether data related to parent members is displayed.</span></span> <span data-ttu-id="30723-111">Para obtener más información, vea jerarquía de elementos [primarios y secundarios](multidimensional-models/parent-child-dimension.md) en jerarquías de elementos [primarios y secundarios](multidimensional-models/parent-child-dimension-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="30723-111">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) and [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md).</span></span>  
  
 [<span data-ttu-id="30723-112">Agrupar miembros de atributo automáticamente</span><span class="sxs-lookup"><span data-stu-id="30723-112">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)  
 <span data-ttu-id="30723-113">En esta tarea, debe crear automáticamente agrupaciones de miembros de atributos basadas en la distribución de miembros de la jerarquía de atributo.</span><span class="sxs-lookup"><span data-stu-id="30723-113">In this task, you automatically create groupings of attribute members based on the distribution of the members within the attribute hierarchy.</span></span> <span data-ttu-id="30723-114">Para más información, vea [Agrupar miembros de atributos &#40;Discretización&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="30723-114">For more information, see [Group Attribute Members &#40;Discretization&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span></span>  
  
 [<span data-ttu-id="30723-115">Ocultar y deshabilitar jerarquías de atributo</span><span class="sxs-lookup"><span data-stu-id="30723-115">Hiding and Disabling Attribute Hierarchies</span></span>](lesson-4-4-hiding-and-disabling-attribute-hierarchies.md)  
 <span data-ttu-id="30723-116">En esta tarea, se muestra cómo y cuándo deshabilitar u ocultar jerarquías de atributo.</span><span class="sxs-lookup"><span data-stu-id="30723-116">In this task, you learn how and when to disable or hide attribute hierarchies.</span></span>  
  
 [<span data-ttu-id="30723-117">Ordenar los miembros de atributo en función de un atributo secundario</span><span class="sxs-lookup"><span data-stu-id="30723-117">Sorting Attribute Members Based on a Secondary Attribute</span></span>](lesson-4-5-sorting-attribute-members-based-on-a-secondary-attribute.md)  
 <span data-ttu-id="30723-118">En esta tarea, se muestra cómo ordenar los miembros de dimensión en función de un atributo secundario para obtener el criterio de ordenación que se desee.</span><span class="sxs-lookup"><span data-stu-id="30723-118">In this task, you learn how to sort dimension members based on a secondary attribute, to achieve the sort order that you want.</span></span>  
  
 [<span data-ttu-id="30723-119">Especificar relaciones de atributo entre los atributos de una jerarquía definida por el usuario</span><span class="sxs-lookup"><span data-stu-id="30723-119">Specifying Attribute Relationships Between Attributes in a User-Defined Hierarchy</span></span>](4-6-specifying-attribute-relationships-in-user-defined-hierarchy.md)  
 <span data-ttu-id="30723-120">En esta tarea, aprenderá a definir las propiedades de miembro de los atributos y a especificar relaciones de agregación entre ellos.</span><span class="sxs-lookup"><span data-stu-id="30723-120">In this task, you learn how to define member properties for attributes and to specify aggregation relationships between them.</span></span> <span data-ttu-id="30723-121">Para obtener más información, vea [definir relaciones de atributo](multidimensional-models/attribute-relationships-define.md) y [propiedades de jerarquía de usuario](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span><span class="sxs-lookup"><span data-stu-id="30723-121">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [User Hierarchy Properties](multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md).</span></span>  
  
 [<span data-ttu-id="30723-122">Definir las propiedades de miembro desconocido y de procesamiento de valores NULL</span><span class="sxs-lookup"><span data-stu-id="30723-122">Defining the Unknown Member and Null Processing Properties</span></span>](lesson-4-7-defining-the-unknown-member-and-null-processing-properties.md)  
 <span data-ttu-id="30723-123">En esta tarea, debe configurar las propiedades UnknownMember y UnknownMemberName para controlar las condiciones de error causadas por los miembros de dimensión con valor NULL.</span><span class="sxs-lookup"><span data-stu-id="30723-123">In this task, you configure the UnknownMember and UnknownMemberName properties to handle error conditions caused by null dimension members.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="30723-124">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="30723-124">Next Lesson</span></span>  
 [<span data-ttu-id="30723-125">Lección 5: definir relaciones entre dimensiones y grupos de medida</span><span class="sxs-lookup"><span data-stu-id="30723-125">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>](lesson-5-defining-relationships-between-dimensions-and-measure-groups.md)  
  
## <a name="see-also"></a><span data-ttu-id="30723-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30723-126">See Also</span></span>  
 <span data-ttu-id="30723-127">[Escenario de Analysis Services tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="30723-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="30723-128">[Modelo multidimensional &#40;tutorial de Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="30723-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="30723-129">Dimensiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="30723-129">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
