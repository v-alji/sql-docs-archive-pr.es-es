---
title: 'Lección 5: definir relaciones entre dimensiones y grupos de medida | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 31aeb271-47a1-433b-a8a5-120bcb4584d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6dbdf20e64e3cd8adc751b69122a380d7b3b3648
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671787"
---
# <a name="lesson-5-defining-relationships-between-dimensions-and-measure-groups"></a><span data-ttu-id="85311-102">Lección 5: definir relaciones entre dimensiones y grupos de medida</span><span class="sxs-lookup"><span data-stu-id="85311-102">Lesson 5: Defining Relationships Between Dimensions and Measure Groups</span></span>
  <span data-ttu-id="85311-103">En las lecciones anteriores de este tutorial, ha aprendido que las dimensiones de base de datos que se agregan a un cubo pueden utilizarse como base para una o más dimensiones de cubo.</span><span class="sxs-lookup"><span data-stu-id="85311-103">In the previous lessons in this tutorial, you learned that database dimensions added to a cube can be used as the basis for one or more cube dimensions.</span></span> <span data-ttu-id="85311-104">En esta lección, aprenderá a definir distintos tipos de relaciones entre dimensiones de cubo y grupos de medida, así como a especificar las propiedades de estas relaciones.</span><span class="sxs-lookup"><span data-stu-id="85311-104">In this lesson, you learn to define different types of relationships between cube dimensions and measure groups, and to specify the properties of these relationships.</span></span>  
  
 <span data-ttu-id="85311-105">Para obtener más información, consulte [Relaciones de dimensiones](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="85311-105">For more information, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85311-106">Los proyectos completos para todas las lecciones de este tutorial están disponibles en línea.</span><span class="sxs-lookup"><span data-stu-id="85311-106">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="85311-107">Puede saltar a continuación a cualquier lección con el proyecto completado de la lección anterior como punto de partida.</span><span class="sxs-lookup"><span data-stu-id="85311-107">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="85311-108">[Haga clic aquí](https://go.microsoft.com/fwlink/?LinkID=221866) para descargar los proyectos de ejemplo que tienen que ver con este tutorial.</span><span class="sxs-lookup"><span data-stu-id="85311-108">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="85311-109">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="85311-109">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="85311-110">Definir una relación referenciada</span><span class="sxs-lookup"><span data-stu-id="85311-110">Defining a Referenced Relationship</span></span>](lesson-5-1-defining-a-referenced-relationship.md)  
 <span data-ttu-id="85311-111">En esta tarea, aprenderá a vincular una dimensión a una tabla de hechos de forma indirecta a través de una dimensión que está vinculada directamente a través de una relación de clave principal y clave externa.</span><span class="sxs-lookup"><span data-stu-id="85311-111">In this task, you learn to link a dimension to a fact table indirectly through a dimension that is linked directly through a primary key-foreign key relationship.</span></span>  
  
 [<span data-ttu-id="85311-112">Definir una relación de hechos</span><span class="sxs-lookup"><span data-stu-id="85311-112">Defining a Fact Relationship</span></span>](lesson-5-2-defining-a-fact-relationship.md)  
 <span data-ttu-id="85311-113">En esta tarea, aprende a definir una dimensión basada en datos de la tabla de hechos, y a definir la relación de la dimensión como una relación de hechos.</span><span class="sxs-lookup"><span data-stu-id="85311-113">In this task, you learn to define a dimension based on data in the fact table, and to define the dimension relationship as a fact relationship.</span></span>  
  
 [<span data-ttu-id="85311-114">Definir una relación de varios a varios</span><span class="sxs-lookup"><span data-stu-id="85311-114">Defining a Many-to-Many Relationship</span></span>](lesson-5-3-defining-a-many-to-many-relationship.md)  
 <span data-ttu-id="85311-115">En esta tarea, aprende a relacionar un hecho con varios miembros de dirección a través de la definición de una relación de varios a varios entre tablas de dimensiones y tablas de hechos.</span><span class="sxs-lookup"><span data-stu-id="85311-115">In this task, you learn to relate a fact to multiple dimension members through the definition of a many-to-many relationship between dimension tables and fact tables.</span></span>  
  
 [<span data-ttu-id="85311-116">Definir la granularidad de las dimensiones en un grupo de medida</span><span class="sxs-lookup"><span data-stu-id="85311-116">Defining Dimension Granularity within a Measure Group</span></span>](lesson-5-4-defining-dimension-granularity-within-a-measure-group.md)  
 <span data-ttu-id="85311-117">En esta tarea, aprende a modificar la granularidad de una dimensión para un grupo de medida específico.</span><span class="sxs-lookup"><span data-stu-id="85311-117">In this task, you learn to modify the granularity of a dimension for a specific measure group.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="85311-118">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="85311-118">Next Lesson</span></span>  
 [<span data-ttu-id="85311-119">Lección 6: definir cálculos</span><span class="sxs-lookup"><span data-stu-id="85311-119">Lesson 6: Defining Calculations</span></span>](lesson-6-defining-calculations.md)  
  
## <a name="see-also"></a><span data-ttu-id="85311-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85311-120">See Also</span></span>  
 <span data-ttu-id="85311-121">[Escenario de Analysis Services tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="85311-121">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="85311-122">[Modelo multidimensional &#40;tutorial de Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="85311-122">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 [<span data-ttu-id="85311-123">Relaciones de dimensión</span><span class="sxs-lookup"><span data-stu-id="85311-123">Dimension Relationships</span></span>](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md)  
  
  
