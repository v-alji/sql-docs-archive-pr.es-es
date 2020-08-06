---
title: 'Lección 1: definir una vista del origen de datos dentro de un proyecto de Analysis Services | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7d3ffabd-78ae-4204-8323-29949d030c16
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a3d69225217154e5072d0cd34349a247730ddaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749525"
---
# <a name="lesson-1-defining-a-data-source-view-within-an-analysis-services-project"></a><span data-ttu-id="6dfe1-102">Lección 1: definir una vista del origen de datos en un proyecto de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6dfe1-102">Lesson 1: Defining a Data Source View within an Analysis Services Project</span></span>
  <span data-ttu-id="6dfe1-103">Para diseñar una aplicación de Business Intelligence en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , primero debe crear un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6dfe1-103">Designing a business intelligence application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with creating an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="6dfe1-104">En este proyecto, debe definir todos los elementos de la solución, empezando por una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-104">Within this project, you define all the elements of your solution, starting with a data source view.</span></span>  
  
 <span data-ttu-id="6dfe1-105">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="6dfe1-105">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="6dfe1-106">Crear un proyecto de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6dfe1-106">Creating an Analysis Services Project</span></span>](lesson-1-1-creating-an-analysis-services-project.md)  
 <span data-ttu-id="6dfe1-107">En esta tarea, creará el proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] basándose en una plantilla de modelo multidimensional de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6dfe1-107">In this task, you create the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, based on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional model template.</span></span>  
  
 [<span data-ttu-id="6dfe1-108">Definir un origen de datos</span><span class="sxs-lookup"><span data-stu-id="6dfe1-108">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
 <span data-ttu-id="6dfe1-109">En esta tarea, especificará la base de datos \*\*AdventureWorksDW2012[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] como origen de datos para las dimensiones y los cubos de \*\* que definirá en lecciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-109">In this task, you specify the **AdventureWorksDW2012** database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dimensions and cubes that you will define in subsequent lessons.</span></span>  
  
 [<span data-ttu-id="6dfe1-110">Definir una vista del origen de datos</span><span class="sxs-lookup"><span data-stu-id="6dfe1-110">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
 <span data-ttu-id="6dfe1-111">En esta tarea, definirá una única vista unificada de los metadatos de tablas seleccionadas en la base de datos **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="6dfe1-111">In this task, you define a single unified view of the metadata from selected tables in the **AdventureWorksDW2012** database.</span></span>  
  
 [<span data-ttu-id="6dfe1-112">Modificar los nombres de tabla predeterminados</span><span class="sxs-lookup"><span data-stu-id="6dfe1-112">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
 <span data-ttu-id="6dfe1-113">En esta tarea, modificará los nombres de tabla de la vista del origen de datos, de modo que los nombres de los objetos subsiguientes de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que definirá sean más descriptivos.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-113">In this task, you modify table names in the data source view, so that the names of subsequent [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects that you define will be more user-friendly.</span></span>  
  
 <span data-ttu-id="6dfe1-114">Compare sus resultados en un archivo de proyecto de ejemplo que se creó para esta lección.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-114">Compare your results against a sample project file that was built for this lesson.</span></span> <span data-ttu-id="6dfe1-115">Para obtener más información sobre cómo descargar los proyectos de ejemplo relacionados con este tutorial, consulte [SSAS Multidimensional Model Projects for SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) (Proyectos de modelo multidimensional de SSAS para SQL Server 2012) en la página de ejemplos del producto de codeplex.</span><span class="sxs-lookup"><span data-stu-id="6dfe1-115">For more information about downloading the sample projects that go with this tutorial, see [SSAS Multidimensional Model Projects for SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) on the product samples page on codeplex.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="6dfe1-116">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="6dfe1-116">Next Lesson</span></span>  
 [<span data-ttu-id="6dfe1-117">Lección 2: definir e implementar un cubo</span><span class="sxs-lookup"><span data-stu-id="6dfe1-117">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="6dfe1-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6dfe1-118">See Also</span></span>  
 <span data-ttu-id="6dfe1-119">[Cree un proyecto de Analysis Services &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="6dfe1-119">[Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span></span>  
 <span data-ttu-id="6dfe1-120">[Orígenes de datos admitidos &#40;&#41;de SSAS multidimensionales](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="6dfe1-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="6dfe1-121">[Vistas del origen de datos en modelos multidimensionales](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="6dfe1-121">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="6dfe1-122">[Escenario de Analysis Services tutorial](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6dfe1-122">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="6dfe1-123">Creación de modelos multidimensionales &#40;tutorial de Adventure Works&#41;</span><span class="sxs-lookup"><span data-stu-id="6dfe1-123">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
