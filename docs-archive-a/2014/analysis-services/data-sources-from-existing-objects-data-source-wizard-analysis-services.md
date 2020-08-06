---
title: Orígenes de datos de objetos existentes (Asistente para orígenes de datos) (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourcewizard.specifyobject.f1
ms.assetid: e6ef6dea-9db8-45c4-8959-f9febd7caf7b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 621c938f4902c95dee1e2fcccb0f292597a565f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746599"
---
# <a name="data-sources-from-existing-objects-data-source-wizard-analysis-services"></a><span data-ttu-id="57e02-102">Orígenes de datos basados en objetos existentes (Asistente para orígenes de datos) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="57e02-102">Data sources from existing objects (Data Source Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="57e02-103">Utilice la página **Orígenes de datos basados en objetos existentes** para especificar un origen de datos o un proyecto existente en el que basar el nuevo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="57e02-103">Use the **Data sources from existing objects** page to specify an existing data source or project on which to base the new data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="57e02-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="57e02-104">Options</span></span>  
 <span data-ttu-id="57e02-105">**Crear un origen de datos basándose en un origen de datos existente en su solución**</span><span class="sxs-lookup"><span data-stu-id="57e02-105">**Create a data source based on an existing data source in your solution**</span></span>  
 <span data-ttu-id="57e02-106">Seleccione esta opción para basar el origen de datos nuevo en un origen de datos existente de la solución.</span><span class="sxs-lookup"><span data-stu-id="57e02-106">Select to base the new data source on an existing data source in the solution.</span></span> <span data-ttu-id="57e02-107">Cuando se genera, actualiza o implementa un proyecto que utiliza el origen de datos nuevo, este origen de datos adquiere los valores del origen de datos especificado al seleccionar esta opción.</span><span class="sxs-lookup"><span data-stu-id="57e02-107">When a project that uses the new data source is built, refreshed, or deployed, the new data source acquires the settings from the data source you specify when you select this option.</span></span>  
  
 <span data-ttu-id="57e02-108">**Origen de datos**</span><span class="sxs-lookup"><span data-stu-id="57e02-108">**Data source**</span></span>  
 <span data-ttu-id="57e02-109">Seleccione en la lista de orígenes de datos agrupada por proyectos el origen de datos en el que desea basar el origen de datos nuevo.</span><span class="sxs-lookup"><span data-stu-id="57e02-109">Select a data source on which you want to base the new data source from the list of data sources, which is grouped by project.</span></span>  
  
 <span data-ttu-id="57e02-110">**Crear un origen de datos basándose en un proyecto de Analysis Services**</span><span class="sxs-lookup"><span data-stu-id="57e02-110">**Create a data source based on an Analysis Services project**</span></span>  
 <span data-ttu-id="57e02-111">Seleccione esta información para crear un nuevo origen de datos que haga referencia a otro [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] proyecto de la solución actual.</span><span class="sxs-lookup"><span data-stu-id="57e02-111">Select to create a new data source that references another [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project in the current solution.</span></span> <span data-ttu-id="57e02-112">El origen de datos nuevo adquiere los valores de las propiedades `TargetServer` y `TargetDatabase` del proyecto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="57e02-112">The new data source acquires settings from the `TargetServer` and `TargetDatabase` properties of the selected project.</span></span> <span data-ttu-id="57e02-113">Cuando se genera, actualiza o implementa un proyecto que utiliza el origen de datos nuevo, este origen de datos adquiere los valores del origen de datos especificado al seleccionar esta opción.</span><span class="sxs-lookup"><span data-stu-id="57e02-113">When a project that uses the new data source is built, refreshed, or deployed, the new data source acquires settings from the data source you specify when you select this option.</span></span>  
  
 <span data-ttu-id="57e02-114">**Proyecto**</span><span class="sxs-lookup"><span data-stu-id="57e02-114">**Project**</span></span>  
 <span data-ttu-id="57e02-115">Seleccione el proyecto al que desea hacer referencia en el origen de datos nuevo.</span><span class="sxs-lookup"><span data-stu-id="57e02-115">Select the project that you want to reference in the new data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57e02-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57e02-116">See Also</span></span>  
 <span data-ttu-id="57e02-117">[Asistente para orígenes de datos &#40;de ayuda F1 Analysis Services&#41;](data-source-wizard-f1-help-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="57e02-117">[Data Source Wizard F1 Help &#40;Analysis Services&#41;](data-source-wizard-f1-help-analysis-services.md) </span></span>  
 <span data-ttu-id="57e02-118">[Orígenes de datos en modelos multidimensionales](multidimensional-models/data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="57e02-118">[Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="57e02-119">Orígenes de datos admitidos &#40;&#41;de SSAS multidimensionales</span><span class="sxs-lookup"><span data-stu-id="57e02-119">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
