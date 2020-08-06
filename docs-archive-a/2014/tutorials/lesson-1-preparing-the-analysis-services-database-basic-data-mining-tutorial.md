---
title: 'Lección 1: preparar la base de datos de Analysis Services (tutorial básico de minería de datos) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a796977-6568-4705-9d27-86a9b36658c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 07647a940851fbdbdc65357e168747662dc88380
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751614"
---
# <a name="lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial"></a><span data-ttu-id="aaebe-102">Lección 1: Preparar la base de datos de Analysis Services (tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="aaebe-102">Lesson 1: Preparing the Analysis Services Database (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="aaebe-103">Es un nuevo empleado de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] que se le ha encargado la tarea de diseñar una aplicación de Business Intelligence en [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aaebe-103">You are a new employee of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] who has been tasked with designing a business intelligence application in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)]<span data-ttu-id="aaebe-104">tiene la intención de aprovechar la [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] experiencia de minería de datos para detectar información interesante y procesable sobre las personas que han comprado bicicletas.</span><span class="sxs-lookup"><span data-stu-id="aaebe-104">hopes to leverage your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data mining experience to discover interesting and actionable information about people who have purchased bicycles.</span></span> <span data-ttu-id="aaebe-105">Quieren que prevea qué clientes tienen más probabilidad de comprar una bicicleta en el futuro.</span><span class="sxs-lookup"><span data-stu-id="aaebe-105">They then want you to predict which prospective customers are most likely to purchase a bicycle in the future.</span></span>  
  
 <span data-ttu-id="aaebe-106">El diseño de esta aplicación en [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] comienza con la creación en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] de un [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] proyecto basado en la [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] plantilla de proyecto para el modelado multidimensional y la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="aaebe-106">Designing this application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with the creation in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project template for multidimensional modeling and data mining.</span></span> <span data-ttu-id="aaebe-107">Después de crear un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], tiene que definir uno o varios orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="aaebe-107">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you define one or more data sources.</span></span> <span data-ttu-id="aaebe-108">A continuación, se define una vista de los metadatos, denominada *vista del origen de datos*, de las tablas y vistas seleccionadas de los orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="aaebe-108">Then, you define a view of the metadata, called a *data source view*, from selected tables and views from the data sources.</span></span>  
  
 <span data-ttu-id="aaebe-109">En esta lección, creará un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], definirá un solo origen de datos y agregará un subconjunto de tablas a una vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="aaebe-109">In this lesson, you will create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, define a single data source, and add a subset of tables to a data source view.</span></span> <span data-ttu-id="aaebe-110">Esta lección incluye las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="aaebe-110">This lesson includes the following tasks:</span></span>  
  
 [<span data-ttu-id="aaebe-111">Crear un proyecto de Analysis Services &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="aaebe-111">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="aaebe-112">Crear un origen de datos &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="aaebe-112">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="aaebe-113">Crear una vista del origen de datos &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="aaebe-113">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="aaebe-114">Primera tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="aaebe-114">First Task in Lesson</span></span>  
 [<span data-ttu-id="aaebe-115">Crear un proyecto de Analysis Services &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="aaebe-115">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="aaebe-116">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="aaebe-116">Next Lesson</span></span>  
 [<span data-ttu-id="aaebe-117">Lección 2: crear una estructura de distribución de correo directo &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="aaebe-117">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="aaebe-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aaebe-118">See Also</span></span>  
 <span data-ttu-id="aaebe-119">[Vistas del origen de datos en modelos multidimensionales](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span><span class="sxs-lookup"><span data-stu-id="aaebe-119">[Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span></span>  
 <span data-ttu-id="aaebe-120">[Orígenes de datos admitidos &#40;&#41;de SSAS multidimensionales](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="aaebe-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span></span>  
 <span data-ttu-id="aaebe-121">[Compilar proyectos de Analysis Services &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="aaebe-121">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="aaebe-122">Crear un proyecto de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="aaebe-122">Creating an Analysis Services Project</span></span>](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md)  
  
  
