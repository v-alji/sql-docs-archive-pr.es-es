---
title: Objetos de base de datos (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], about objects
- SQL Server Analysis Services, objects
- Analysis Services objects, about Analysis Services objects
- SSAS, objects
- Analysis Services objects
- objects [Analysis Services]
ms.assetid: f76d869b-fc1d-4807-9f28-da09c7be382d
author: minewiskan
ms.author: owend
ms.openlocfilehash: d61e3213356146e1cf9e452e0b62e02c96bd4902
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752465"
---
# <a name="database-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="7dd3b-102">Objetos de base de datos (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="7dd3b-102">Database Objects (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="7dd3b-103">Una [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instancia de contiene objetos y ensamblados de base de datos para su uso con el procesamiento analítico en línea (OLAP) y la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-103">A [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance contains database objects and assemblies for use with online analytical processing (OLAP) and data mining.</span></span>  
  
-   <span data-ttu-id="7dd3b-104">Las bases de datos contienen objetos OLAP y de minería de datos como orígenes de datos, vistas del origen de datos, cubos, medidas, grupos de medida, dimensiones, atributos, jerarquías, estructuras de minería de datos, modelos de minería de datos y roles.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-104">Databases contain OLAP and data mining objects, such as data sources, data source views, cubes, measures, measure groups, dimensions, attributes, hierarchies, mining structures, mining models and roles.</span></span>  
  
-   <span data-ttu-id="7dd3b-105">Los ensamblados contienen funciones definidas por el usuario que amplían la funcionalidad de las funciones intrínsecas suministradas por los lenguajes Expresiones multidimensionales (MDX) y Extensiones de minería de datos (DMX).</span><span class="sxs-lookup"><span data-stu-id="7dd3b-105">Assemblies contain user-defined functions that extend the functionality of the intrinsic functions provided with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span>  
  
 <span data-ttu-id="7dd3b-106">El objeto <xref:Microsoft.AnalysisServices.Database> es el contenedor para todos los objetos de datos que se necesitan para un proyecto de Business Intelligence (como cubos OLAP, dimensiones y estructuras de minería de datos) y sus objetos de ayuda (como <xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account> y <xref:Microsoft.AnalysisServices.Role>).</span><span class="sxs-lookup"><span data-stu-id="7dd3b-106">The <xref:Microsoft.AnalysisServices.Database> object is the container for all data objects that are needed for a business intelligence project (such as OLAP cubes, dimensions, and data mining structures), and their supporting objects (such as <xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account>, and <xref:Microsoft.AnalysisServices.Role>).</span></span>  
  
 <span data-ttu-id="7dd3b-107">Un objeto <xref:Microsoft.AnalysisServices.Database> proporciona acceso a los objetos y atributos que incluyen lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7dd3b-107">A <xref:Microsoft.AnalysisServices.Database> object provides access to objects and attributes that include the following:</span></span>  
  
-   <span data-ttu-id="7dd3b-108">Todos los cubos a los que puede tener acceso, como una colección.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-108">All cubes that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="7dd3b-109">Todas las dimensiones a las que puede tener acceso, como una colección.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-109">All dimensions that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="7dd3b-110">Todas las estructuras de minería de datos a las que puede tener acceso, como una colección.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-110">All mining structures that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="7dd3b-111">Todos los orígenes de datos y vistas del origen de datos, como dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-111">All data sources and data source views, as two collections.</span></span>  
  
-   <span data-ttu-id="7dd3b-112">Todos los roles y permisos de base de datos, como dos colecciones.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-112">All roles and database permissions, as two collections.</span></span>  
  
-   <span data-ttu-id="7dd3b-113">El valor de intercalación para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-113">The collation value for the database.</span></span>  
  
-   <span data-ttu-id="7dd3b-114">El tamaño estimado de la base de datos</span><span class="sxs-lookup"><span data-stu-id="7dd3b-114">The estimated size of the database.</span></span>  
  
-   <span data-ttu-id="7dd3b-115">El valor de lenguaje de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-115">The language value of the database.</span></span>  
  
-   <span data-ttu-id="7dd3b-116">El valor visible para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-116">The visible setting for the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7dd3b-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7dd3b-117">In This Section</span></span>  
 <span data-ttu-id="7dd3b-118">En los siguientes temas se describen los objetos compartidos por características de OLAP y de minería de datos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dd3b-118">The following topics describe objects shared by both OLAP and data mining features in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="7dd3b-119">Tema</span><span class="sxs-lookup"><span data-stu-id="7dd3b-119">Topic</span></span>|<span data-ttu-id="7dd3b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="7dd3b-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7dd3b-121">Orígenes de datos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="7dd3b-121">Data Sources in Multidimensional Models</span></span>](../data-sources-in-multidimensional-models.md)|<span data-ttu-id="7dd3b-122">Describe un origen de datos en [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dd3b-122">Describes a data source in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="7dd3b-123">Vistas del origen de datos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="7dd3b-123">Data Source Views in Multidimensional Models</span></span>](../data-source-views-in-multidimensional-models.md)|<span data-ttu-id="7dd3b-124">Describe un modelo de datos lógico basado en uno o varios orígenes de datos, en [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dd3b-124">Describes a logical data model based on one or more data sources, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="7dd3b-125">Cubos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="7dd3b-125">Cubes in Multidimensional Models</span></span>](../cubes-in-multidimensional-models.md)|<span data-ttu-id="7dd3b-126">Describe cubos y objetos de cubo, lo que incluye medidas, grupos de medida, relaciones de uso de dimensiones, cálculos, indicadores clave de rendimiento, acciones, traducciones, particiones y perspectivas.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-126">Describes cubes and cube objects, including measures, measure groups, dimension usage relationships, calculations, key performance indicators, actions, translations, partitions, and perspectives.</span></span>|  
|[<span data-ttu-id="7dd3b-127">Dimensiones &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="7dd3b-127">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="7dd3b-128">Describe dimensiones y objetos de dimensiones, incluidos atributos, relaciones de atributo, jerarquías, niveles y miembros.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-128">Describes dimensions and dimension objects, including attributes, attribute relationships, hierarchies, levels, and members.</span></span>|  
|[<span data-ttu-id="7dd3b-129">Estructuras de minería de datos &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7dd3b-129">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](../../data-mining/mining-structures-analysis-services-data-mining.md)|<span data-ttu-id="7dd3b-130">Describe estructuras y objetos de minería de datos, incluidos modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7dd3b-130">Describes mining structures and mining objects, including mining models.</span></span>|  
|[<span data-ttu-id="7dd3b-131">Roles de seguridad &#40;Analysis Services - Datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="7dd3b-131">Security Roles  &#40;Analysis Services - Multidimensional Data&#41;</span></span>](security-roles-analysis-services-multidimensional-data.md)|<span data-ttu-id="7dd3b-132">Describe un rol, el mecanismo de seguridad utilizado para controlar el acceso a objetos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dd3b-132">Describes a role, the security mechanism used to control access to objects in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="7dd3b-133">Administración de ensamblados de modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="7dd3b-133">Multidimensional Model Assemblies Management</span></span>](../multidimensional-model-assemblies-management.md)|<span data-ttu-id="7dd3b-134">Describe un ensamblado, una colección de funciones definidas por el usuario utilizadas para ampliar los lenguajes MDX y DMX, en [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dd3b-134">Describes an assembly, a collection of user-defined functions used to extend the MDX and DMX languages, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7dd3b-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7dd3b-135">See Also</span></span>  
 <span data-ttu-id="7dd3b-136">[Orígenes de datos admitidos &#40;&#41;de SSAS multidimensionales](../supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="7dd3b-136">[Data Sources Supported &#40;SSAS Multidimensional&#41;](../supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="7dd3b-137">[Soluciones de modelos multidimensionales &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="7dd3b-137">[Multidimensional Model Solutions &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span></span>  
 [<span data-ttu-id="7dd3b-138">Soluciones de minería de datos</span><span class="sxs-lookup"><span data-stu-id="7dd3b-138">Data Mining Solutions</span></span>](../../data-mining/data-mining-solutions.md)  
  
  
