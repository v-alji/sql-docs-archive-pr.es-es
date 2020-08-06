---
title: 'Lección 2: definir e implementar un cubo | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: bb62e3c9-462f-4ad2-ac8e-92e2f9e9cc28
author: minewiskan
ms.author: owend
ms.openlocfilehash: a2c043920ac646ec4da9eaa2aace4bf6f48e694c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675635"
---
# <a name="lesson-2-defining-and-deploying-a-cube"></a><span data-ttu-id="86842-102">Lección 2: Definir e implementar un cubo</span><span class="sxs-lookup"><span data-stu-id="86842-102">Lesson 2: Defining and Deploying a Cube</span></span>
  <span data-ttu-id="86842-103">Después de definir una vista del origen de datos en el [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] proyecto, está listo para definir un [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubo inicial.</span><span class="sxs-lookup"><span data-stu-id="86842-103">After you define a data source view in your [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you are ready to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 <span data-ttu-id="86842-104">Puede definir un cubo y sus dimensiones en un solo paso mediante el Asistente para cubos.</span><span class="sxs-lookup"><span data-stu-id="86842-104">You can define a cube and its dimensions in a single pass using the Cube Wizard.</span></span> <span data-ttu-id="86842-105">También puede definir una o más dimensiones y usar el Asistente para cubos con objeto de definir un cubo que use dichas dimensiones.</span><span class="sxs-lookup"><span data-stu-id="86842-105">Alternatively, you can define one or more dimensions and then use the Cube Wizard to define a cube that uses those dimensions.</span></span> <span data-ttu-id="86842-106">Si está diseñando una solución compleja, generalmente empezará definiendo las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="86842-106">If you are designing a complex solution, you generally start by defining the dimensions.</span></span> <span data-ttu-id="86842-107">Para obtener más información, consulte [Dimensiones en modelos multidimensionales](multidimensional-models/dimensions-in-multidimensional-models.md) o [Cubos en modelos multidimensionales](multidimensional-models/cubes-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="86842-107">For more information, see [Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) or [Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86842-108">Los proyectos completos para todas las lecciones de este tutorial están disponibles en línea.</span><span class="sxs-lookup"><span data-stu-id="86842-108">Completed projects for all of the lessons in this tutorial are available online.</span></span> <span data-ttu-id="86842-109">Puede saltar a continuación a cualquier lección con el proyecto completado de la lección anterior como punto de partida.</span><span class="sxs-lookup"><span data-stu-id="86842-109">You can jump ahead to any lesson by using the completed project from the previous lesson as a starting point.</span></span> <span data-ttu-id="86842-110">[Haga clic aquí](https://go.microsoft.com/fwlink/?LinkID=221866) para descargar los proyectos de ejemplo que tienen que ver con este tutorial.</span><span class="sxs-lookup"><span data-stu-id="86842-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to download the sample projects that go with this tutorial.</span></span>  
  
 <span data-ttu-id="86842-111">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="86842-111">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="86842-112">Definir una dimensión</span><span class="sxs-lookup"><span data-stu-id="86842-112">Defining a Dimension</span></span>](lesson-2-1-defining-a-dimension.md)  
 <span data-ttu-id="86842-113">En esta tarea, debe usar el Asistente para dimensiones con objeto de definir una dimensión.</span><span class="sxs-lookup"><span data-stu-id="86842-113">In this task, you use the Dimension Wizard to define a dimension.</span></span>  
  
 [<span data-ttu-id="86842-114">Definir un cubo</span><span class="sxs-lookup"><span data-stu-id="86842-114">Defining a Cube</span></span>](lesson-2-2-defining-a-cube.md)  
 <span data-ttu-id="86842-115">En esta tarea, debe usar el Asistente para cubos con objeto de definir un cubo de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] inicial.</span><span class="sxs-lookup"><span data-stu-id="86842-115">In this task, you use the Cube Wizard to define an initial [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube.</span></span>  
  
 [<span data-ttu-id="86842-116">Agregar atributos a dimensiones</span><span class="sxs-lookup"><span data-stu-id="86842-116">Adding Attributes to Dimensions</span></span>](lesson-2-3-adding-attributes-to-dimensions.md)  
 <span data-ttu-id="86842-117">En esta tarea, debe agregar atributos a las dimensiones que creó.</span><span class="sxs-lookup"><span data-stu-id="86842-117">In this task, you add attributes to the dimensions that you created.</span></span>  
  
 [<span data-ttu-id="86842-118">Revisar las propiedades de cubo y dimensión</span><span class="sxs-lookup"><span data-stu-id="86842-118">Reviewing Cube and Dimension Properties</span></span>](lesson-2-4-reviewing-cube-and-dimension-properties.md)  
 <span data-ttu-id="86842-119">En esta tarea, debe revisar la estructura del cubo que definió utilizando el Asistente para cubos.</span><span class="sxs-lookup"><span data-stu-id="86842-119">In this task, you review the structure of the cube that you defined by using the Cube Wizard.</span></span>  
  
 [<span data-ttu-id="86842-120">Implementar un proyecto de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="86842-120">Deploying an Analysis Services Project</span></span>](lesson-2-5-deploying-an-analysis-services-project.md)  
 <span data-ttu-id="86842-121">En esta tarea, debe implementar el proyecto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en la instancia local de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], y obtendrá información sobre algunas propiedades de implementación.</span><span class="sxs-lookup"><span data-stu-id="86842-121">In this task, you deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project to your local instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], and learn about certain deployment properties.</span></span>  
  
 [<span data-ttu-id="86842-122">Examinar el cubo</span><span class="sxs-lookup"><span data-stu-id="86842-122">Browsing the Cube</span></span>](lesson-2-6-browsing-the-cube.md)  
 <span data-ttu-id="86842-123">En esta tarea, examinará los datos de cubo y de dimensión usando Excel o el diseñador de consultas MDX.</span><span class="sxs-lookup"><span data-stu-id="86842-123">In this task, you browse the cube and dimension data by using Excel or the MDX query designer.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="86842-124">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="86842-124">Next Lesson</span></span>  
 [<span data-ttu-id="86842-125">Lección 3: modificar medidas, atributos y jerarquías</span><span class="sxs-lookup"><span data-stu-id="86842-125">Lesson 3: Modifying Measures, Attributes and Hierarchies</span></span>](lesson-3-modifying-measures-attributes-and-hierarchies.md)  
  
## <a name="see-also"></a><span data-ttu-id="86842-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86842-126">See Also</span></span>  
 <span data-ttu-id="86842-127">[Escenario de Analysis Services tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="86842-127">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 <span data-ttu-id="86842-128">[Modelo multidimensional &#40;tutorial de Adventure Works&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="86842-128">[Multidimensional Modeling &#40;Adventure Works Tutorial&#41;](multidimensional-modeling-adventure-works-tutorial.md) </span></span>  
 <span data-ttu-id="86842-129">[Dimensiones en modelos multidimensionales](multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="86842-129">[Dimensions in Multidimensional Models](multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="86842-130">[Cubos en modelos multidimensionales](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="86842-130">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="86842-131">[Configurar las propiedades del proyecto Analysis Services &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="86842-131">[Configure Analysis Services Project Properties &#40;SSDT&#41;](multidimensional-models/configure-analysis-services-project-properties-ssdt.md) </span></span>  
 <span data-ttu-id="86842-132">[Compilar proyectos de Analysis Services &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="86842-132">[Build Analysis Services Projects &#40;SSDT&#41;](multidimensional-models/build-analysis-services-projects-ssdt.md) </span></span>  
 [<span data-ttu-id="86842-133">Implementar proyectos de Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="86842-133">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
  
