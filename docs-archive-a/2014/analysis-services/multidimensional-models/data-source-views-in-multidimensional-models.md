---
title: Vistas del origen de datos en modelos multidimensionales | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data source views [Analysis Services]
- data source views [Analysis Services], about data source views
- SQL Server Analysis Services, data source views
- data source views [Analysis Services], multiple
- Analysis Services, data source views
- multiple data source views
- SSAS, data source views
ms.assetid: 4c12376f-4fc2-492b-9a00-93eec34571ed
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1aef6b6d716ec71ac082ca8b7c042492c1712b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750309"
---
# <a name="data-source-views-in-multidimensional-models"></a><span data-ttu-id="ba6bc-102">Vistas del origen de datos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="ba6bc-102">Data Source Views in Multidimensional Models</span></span>
  <span data-ttu-id="ba6bc-103">Una vista del origen de datos (DSV) es una abstracción de un origen de datos relacional que se convierte en la base de los cubos y dimensiones creadas en un proyecto multidimensional.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-103">A data source view (DSV) is an abstraction of a relational data source that becomes the basis of the cubes and dimensions you create in a multidimensional project.</span></span> <span data-ttu-id="ba6bc-104">La finalidad de una DSV es proporcionar el control sobre las estructuras de datos utilizadas en el proyecto, y trabajar independientemente de los orígenes de datos subyacentes (por ejemplo, la capacidad de cambiar de nombre o concatenar columnas sin modificar directamente el origen de datos original).</span><span class="sxs-lookup"><span data-stu-id="ba6bc-104">The purpose of a DSV is to give you control over the data structures used in your project, and to work independently of the underlying data sources (for example, the ability to rename or concatenate columns without directly modifying the original data source).</span></span>  
  
 <span data-ttu-id="ba6bc-105">Puede crear varias vistas del origen de datos en un proyecto o una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en uno o varios orígenes de datos y crear cada una de ellas de forma que cumpla los requisitos de una solución distinta.</span><span class="sxs-lookup"><span data-stu-id="ba6bc-105">You can build multiple data source views in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database on one or more data sources, and construct each one to satisfy the requirements for a different solution.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ba6bc-106">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="ba6bc-106">Related Tasks</span></span>  
 [<span data-ttu-id="ba6bc-107">Definir una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-107">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](defining-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="ba6bc-108">Agregar o quitar tablas o vistas en una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-108">Adding or Removing Tables or Views in a Data Source View &#40;Analysis Services&#41;</span></span>](adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="ba6bc-109">Cambiar las propiedades de una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-109">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](change-properties-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="ba6bc-110">Definir relaciones lógicas en una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-110">Define Logical Relationships in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-relationships-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="ba6bc-111">Definir claves principales lógicas en una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-111">Define Logical Primary Keys in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-primary-keys-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="ba6bc-112">Definir cálculos con nombre en una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-112">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="ba6bc-113">Definir consultas con nombre en una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-113">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="ba6bc-114">Reemplazar una tabla o una consulta con nombre en una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-114">Replace a Table or a Named Query in a Data Source View &#40;Analysis Services&#41;</span></span>](replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="ba6bc-115">Trabajar con diagramas en el Diseñador de vistas del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-115">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
 [<span data-ttu-id="ba6bc-116">Explorar datos en una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-116">Explore Data in a Data Source View &#40;Analysis Services&#41;</span></span>](explore-data-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="ba6bc-117">Eliminar una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-117">Delete a Data Source View &#40;Analysis Services&#41;</span></span>](delete-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="ba6bc-118">Actualizar el esquema de una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ba6bc-118">Refresh the Schema in a Data Source View &#40;Analysis Services&#41;</span></span>](refresh-the-schema-in-a-data-source-view-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="ba6bc-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba6bc-119">See Also</span></span>  
 <span data-ttu-id="ba6bc-120">[Asistente para generar esquemas &#40;Analysis Services&#41;](schema-generation-wizard-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="ba6bc-120">[Schema Generation Wizard &#40;Analysis Services&#41;](schema-generation-wizard-analysis-services.md) </span></span>  
 [<span data-ttu-id="ba6bc-121">Orígenes de datos admitidos &#40;&#41;de SSAS multidimensionales</span><span class="sxs-lookup"><span data-stu-id="ba6bc-121">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)  
  
  
