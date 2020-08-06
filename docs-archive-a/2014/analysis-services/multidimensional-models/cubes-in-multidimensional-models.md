---
title: Cubos en modelos multidimensionales | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OLAP objects [Analysis Services], cubes
- cubes [Analysis Services], about cubes
- cubes [Analysis Services]
- OLAP [Analysis Services], cubes
ms.assetid: e0f7acf3-4b07-41fc-a5fc-ac30b4a56c54
author: minewiskan
ms.author: owend
ms.openlocfilehash: 372bb8075b232ff8fbf8a54facf9bc065e6763a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750317"
---
# <a name="cubes-in-multidimensional-models"></a><span data-ttu-id="dd00a-102">Cubos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-102">Cubes in Multidimensional Models</span></span>
  <span data-ttu-id="dd00a-103">Un cubo es una estructura multidimensional que contiene información con fines analíticos; sus componentes principales son las dimensiones y las medidas.</span><span class="sxs-lookup"><span data-stu-id="dd00a-103">A cube is a multidimensional structure that contains information for analytical purposes; the main constituents of a cube are dimensions and measures.</span></span> <span data-ttu-id="dd00a-104">Las dimensiones definen la estructura del cubo que se utiliza para segmentar y dividir los datos, y las medidas proporcionan valores numéricos agregados importantes para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="dd00a-104">Dimensions define the structure of the cube that you use to slice and dice over, and measures provide aggregated numerical values of interest to the end user.</span></span> <span data-ttu-id="dd00a-105">Como estructura lógica, un cubo permite a una aplicación cliente recuperar valores, de medidas, como si estuvieran almacenados en las celdas del cubo; las celdas se definen para cada posible valor resumido.</span><span class="sxs-lookup"><span data-stu-id="dd00a-105">As a logical structure, a cube allows a client application to retrieve values, of measures, as if they were contained in cells in the cube; cells are defined for every possible summarized value.</span></span> <span data-ttu-id="dd00a-106">Las celdas del cubo se definen por la intersección de miembros de dimensión y contienen los valores agregados de las medidas en esa intersección concreta.</span><span class="sxs-lookup"><span data-stu-id="dd00a-106">A cell, in the cube, is defined by the intersection of dimension members and contains the aggregated values of the measures at that specific intersection.</span></span>  
  
## <a name="benefits-of-using-cubes"></a><span data-ttu-id="dd00a-107">Ventajas del uso de cubos</span><span class="sxs-lookup"><span data-stu-id="dd00a-107">Benefits of Using Cubes</span></span>  
 <span data-ttu-id="dd00a-108">Un cubo proporciona un único lugar en el que se almacenan todos los datos relacionados con fines analíticos.</span><span class="sxs-lookup"><span data-stu-id="dd00a-108">A cube provides a single place where all related data, for analysis, is stored.</span></span>  
  
## <a name="components-of-cubes"></a><span data-ttu-id="dd00a-109">Componentes de los cubos</span><span class="sxs-lookup"><span data-stu-id="dd00a-109">Components of Cubes</span></span>  
 <span data-ttu-id="dd00a-110">Un cubo consta de:</span><span class="sxs-lookup"><span data-stu-id="dd00a-110">A cube is composed of:</span></span>  
  
|<span data-ttu-id="dd00a-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="dd00a-111">Element</span></span>|<span data-ttu-id="dd00a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd00a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd00a-113">Dimensions</span><span class="sxs-lookup"><span data-stu-id="dd00a-113">Dimensions</span></span>|[<span data-ttu-id="dd00a-114">Dimensiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-114">Dimensions in Multidimensional Models</span></span>](dimensions-in-multidimensional-models.md)|  
|<span data-ttu-id="dd00a-115">Medidas y grupos de medida</span><span class="sxs-lookup"><span data-stu-id="dd00a-115">Measures and Measure Groups</span></span>|[<span data-ttu-id="dd00a-116">Crear medidas y grupos de medida en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-116">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|  
|<span data-ttu-id="dd00a-117">Particiones</span><span class="sxs-lookup"><span data-stu-id="dd00a-117">Partitions</span></span>|[<span data-ttu-id="dd00a-118">Particiones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-118">Partitions in Multidimensional Models</span></span>](partitions-in-multidimensional-models.md)|  
|<span data-ttu-id="dd00a-119">Perspectivas</span><span class="sxs-lookup"><span data-stu-id="dd00a-119">Perspectives</span></span>|[<span data-ttu-id="dd00a-120">Perspectivas de modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-120">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|  
|<span data-ttu-id="dd00a-121">Jerarquías</span><span class="sxs-lookup"><span data-stu-id="dd00a-121">Hierarchies</span></span>|[<span data-ttu-id="dd00a-122">Crear jerarquías definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="dd00a-122">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)|  
|<span data-ttu-id="dd00a-123">Acciones</span><span class="sxs-lookup"><span data-stu-id="dd00a-123">Actions</span></span>|[<span data-ttu-id="dd00a-124">Acciones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-124">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|  
|<span data-ttu-id="dd00a-125">Indicadores clave de rendimiento (KPI)</span><span class="sxs-lookup"><span data-stu-id="dd00a-125">Key Performance Indicators (KPI)</span></span>|[<span data-ttu-id="dd00a-126">Indicadores clave de rendimiento &#40;KPI&#41; en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-126">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](key-performance-indicators-kpis-in-multidimensional-models.md)|  
|<span data-ttu-id="dd00a-127">Cálculos</span><span class="sxs-lookup"><span data-stu-id="dd00a-127">Calculations</span></span>|[<span data-ttu-id="dd00a-128">Cálculos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-128">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|  
|<span data-ttu-id="dd00a-129">Translations</span><span class="sxs-lookup"><span data-stu-id="dd00a-129">Translations</span></span>|[<span data-ttu-id="dd00a-130">Traducciones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-130">Translations in Multidimensional Models</span></span>](translations-in-multidimensional-models-analysis-services.md)|  
  
## <a name="related-tasks"></a><span data-ttu-id="dd00a-131">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="dd00a-131">Related Tasks</span></span>  
  
|<span data-ttu-id="dd00a-132">Tema</span><span class="sxs-lookup"><span data-stu-id="dd00a-132">Topic</span></span>|<span data-ttu-id="dd00a-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd00a-133">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="dd00a-134">Crear un cubo con el Asistente para cubos</span><span class="sxs-lookup"><span data-stu-id="dd00a-134">Create a Cube Using the Cube Wizard</span></span>](create-a-cube-using-the-cube-wizard.md)|<span data-ttu-id="dd00a-135">Describe la utilización del Asistente para cubos para definir un cubo, dimensiones, atributos de dimensión y jerarquías definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="dd00a-135">Describes how to use the Cube Wizard to define a cube, dimensions, dimension attributes, and user-defined hierarchies.</span></span>|  
|[<span data-ttu-id="dd00a-136">Crear medidas y grupos de medida en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-136">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|<span data-ttu-id="dd00a-137">Describe cómo definir los grupos de medida.</span><span class="sxs-lookup"><span data-stu-id="dd00a-137">Describes how to define measure groups.</span></span>|  
|[<span data-ttu-id="dd00a-138">Cálculos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-138">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|<span data-ttu-id="dd00a-139">Describe cómo definir y configurar un cálculo en un script MDX.</span><span class="sxs-lookup"><span data-stu-id="dd00a-139">Describes how to define and configure a calculation in an MDX script.</span></span>|  
|[<span data-ttu-id="dd00a-140">Acciones en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-140">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|<span data-ttu-id="dd00a-141">Describe cómo definir y configurar una acción.</span><span class="sxs-lookup"><span data-stu-id="dd00a-141">Describes how to define and configure an action.</span></span>|  
|[<span data-ttu-id="dd00a-142">Perspectivas de modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="dd00a-142">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|<span data-ttu-id="dd00a-143">Describe cómo definir y configurar una perspectiva.</span><span class="sxs-lookup"><span data-stu-id="dd00a-143">Describes how to define and configure a perspective.</span></span>|  
|[<span data-ttu-id="dd00a-144">Definir procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="dd00a-144">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)|<span data-ttu-id="dd00a-145">Describe cómo trabajar con los procedimientos almacenados.</span><span class="sxs-lookup"><span data-stu-id="dd00a-145">Describes how to work with stored procedures.</span></span>|  
  
  
