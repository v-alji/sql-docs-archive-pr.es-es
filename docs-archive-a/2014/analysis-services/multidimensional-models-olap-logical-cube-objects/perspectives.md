---
title: Perspectivas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- ready-only cube view
- OLAP objects [Analysis Services], perspectives
- storing data [Analysis Services], perspectives
- perspectives [Analysis Services]
- cubes [Analysis Services], perspectives
- visibility [Analysis Services]
- storage [Analysis Services], perspectives
ms.assetid: b064171e-b1b4-4f32-95e5-59e1b831c4c9
author: minewiskan
ms.author: owend
ms.openlocfilehash: f385fd078500739d97394cd8856fc8bd6a3b87e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746573"
---
# <a name="perspectives"></a><span data-ttu-id="8ebd1-102">Perspectivas</span><span class="sxs-lookup"><span data-stu-id="8ebd1-102">Perspectives</span></span>
  <span data-ttu-id="8ebd1-103">Una perspectiva es una definición que permite a los usuarios ver un cubo de una manera más fácil.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-103">A perspective is a definition that allows users to see a cube in a simpler way.</span></span> <span data-ttu-id="8ebd1-104">Una perspectiva es un subconjunto de las características de un cubo.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-104">A perspective is a subset of the features of a cube.</span></span> <span data-ttu-id="8ebd1-105">La perspectiva permite a los administradores crear vistas de un cubo, lo que ayuda a los usuarios a centrarse en los datos más pertinentes para ellos.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-105">A perspective enables administrators to create views of a cube, helping users to focus on the most relevant data for them.</span></span> <span data-ttu-id="8ebd1-106">Una perspectiva contiene subconjuntos de todos los objetos de un cubo.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-106">A perspective contains subsets of all objects from a cube.</span></span> <span data-ttu-id="8ebd1-107">No puede incluir elementos que no están definidos en el cubo primario.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-107">A perspective cannot include elements that are not defined in the parent cube.</span></span>  
  
 <span data-ttu-id="8ebd1-108">Un objeto <xref:Microsoft.AnalysisServices.Perspective> simple se compone de la información básica, dimensiones, grupos de medida, cálculos, KPI y acciones.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-108">A simple <xref:Microsoft.AnalysisServices.Perspective> object is composed of: basic information, dimensions, measure groups, calculations, KPIs, and actions.</span></span> <span data-ttu-id="8ebd1-109">La información básica incluye el nombre y la medida predeterminada de la perspectiva.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-109">Basic information includes the name and the default measure of the perspective.</span></span> <span data-ttu-id="8ebd1-110">Las dimensiones son un conjunto de las dimensiones del cubo.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-110">The dimensions are a subset of the cube dimensions.</span></span> <span data-ttu-id="8ebd1-111">Los grupos de medida son un subconjunto de los grupos de medida del cubo.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-111">The measure groups are a subset of the cube measure groups.</span></span> <span data-ttu-id="8ebd1-112">Los cálculos son un subconjunto de los cálculos del cubo.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-112">The calculations are a subset of the cube calculations.</span></span> <span data-ttu-id="8ebd1-113">Los KPI son un subconjunto de los KPI del cubo.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-113">The KPIs are a subset of the cube KPIs.</span></span> <span data-ttu-id="8ebd1-114">Las acciones son un subconjunto de las acciones del cubo.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-114">The actions are a subset of the cube actions.</span></span>  
  
 <span data-ttu-id="8ebd1-115">Para usar la perspectiva, el cubo debe estar actualizado y haberse procesado.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-115">A cube has to be updated and processed before the perspective can be used.</span></span>  
  
 <span data-ttu-id="8ebd1-116">Los cubos pueden ser objetos muy complejos para que los usuarios los exploren [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ebd1-116">Cubes can be very complex objects for users to explore in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="8ebd1-117">Un solo cubo puede representar el contenido de un almacenamiento de datos completo, con varios grupos de medida en un cubo que representan varias tablas de hechos y varias dimensiones basadas en varias tablas de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-117">A single cube can represent the contents of a complete data warehouse, with multiple measure groups in a cube representing multiple fact tables, and multiple dimensions based on multiple dimension tables.</span></span> <span data-ttu-id="8ebd1-118">Un cubo así puede ser muy complejo y eficaz, pero resultar desalentador para los usuarios que solo necesitan interactuar con una pequeña parte del cubo para satisfacer sus requisitos de informes y de Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-118">Such a cube can be very complex and powerful, but daunting to users who may only need to interact with a small part of the cube in order to satisfy their business intelligence and reporting requirements.</span></span>  
  
 <span data-ttu-id="8ebd1-119">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , puede utilizar una perspectiva para reducir la complejidad percibida de un cubo en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ebd1-119">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use a perspective to reduce the perceived complexity of a cube in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="8ebd1-120">Una perspectiva define un subconjunto visible de un cubo que ofrece puntos de vista centrados en el cubo, específicos del negocio o la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-120">A perspective defines a viewable subset of a cube that provides focused, business-specific or application-specific viewpoints on the cube.</span></span> <span data-ttu-id="8ebd1-121">La perspectiva controla la visibilidad de los objetos que contiene un cubo.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-121">The perspective controls the visibility of objects that are contained by a cube.</span></span> <span data-ttu-id="8ebd1-122">Los siguientes objetos pueden mostrarse u ocultarse en una perspectiva:</span><span class="sxs-lookup"><span data-stu-id="8ebd1-122">The following objects can be displayed or hidden in a perspective:</span></span>  
  
-   <span data-ttu-id="8ebd1-123">Dimensions</span><span class="sxs-lookup"><span data-stu-id="8ebd1-123">Dimensions</span></span>  
  
-   <span data-ttu-id="8ebd1-124">Atributos</span><span class="sxs-lookup"><span data-stu-id="8ebd1-124">Attributes</span></span>  
  
-   <span data-ttu-id="8ebd1-125">Jerarquías</span><span class="sxs-lookup"><span data-stu-id="8ebd1-125">Hierarchies</span></span>  
  
-   <span data-ttu-id="8ebd1-126">Grupos de medida</span><span class="sxs-lookup"><span data-stu-id="8ebd1-126">Measure groups</span></span>  
  
-   <span data-ttu-id="8ebd1-127">Medidas</span><span class="sxs-lookup"><span data-stu-id="8ebd1-127">Measures</span></span>  
  
-   <span data-ttu-id="8ebd1-128">Indicadores clave de rendimiento (KPI)</span><span class="sxs-lookup"><span data-stu-id="8ebd1-128">Key Performance Indicators (KPIs)</span></span>  
  
-   <span data-ttu-id="8ebd1-129">Cálculos (miembros calculados, conjuntos con nombre y comandos de script)</span><span class="sxs-lookup"><span data-stu-id="8ebd1-129">Calculations (calculated members, named sets, and script commands)</span></span>  
  
-   <span data-ttu-id="8ebd1-130">Acciones</span><span class="sxs-lookup"><span data-stu-id="8ebd1-130">Actions</span></span>  
  
 <span data-ttu-id="8ebd1-131">Por ejemplo, el cubo **Adventure Works** de la [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] base de datos de ejemplo [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contiene once grupos de medida y veinte dimensiones de cubo diferentes, que representan ventas, previsiones de ventas y datos financieros.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-131">For example, the **Adventure Works** cube in the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database contains eleven measure groups and twenty-one different cube dimensions, representing sales, sales forecasting, and financial data.</span></span> <span data-ttu-id="8ebd1-132">Una aplicación cliente puede hacer referencia directa al cubo completo, pero esto puede resultar abrumador para un usuario que intenta extraer información básica de previsiones de ventas.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-132">A client application can directly reference the complete cube, but this viewpoint may be overwhelming to a user trying to extract basic sales forecasting information.</span></span> <span data-ttu-id="8ebd1-133">En su lugar, el mismo usuario puede utilizar la perspectiva de **destinos de ventas** para limitar la vista del cubo de **Adventure Works** a solo los objetos relevantes para la previsión de ventas.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-133">Instead, the same user can use the **Sales Targets** perspective to limit the view of the **Adventure Works** cube to only those objects relevant to sales forecasting.</span></span>  
  
 <span data-ttu-id="8ebd1-134">Se puede hacer referencia directa a los objetos de un cubo que no son visibles para el usuario en una perspectiva y recuperarlos mediante XML for Analysis (XMLA), MDX (Expresiones multidimensionales) o instrucciones de Extensiones de minería de datos (DMX).</span><span class="sxs-lookup"><span data-stu-id="8ebd1-134">Objects in a cube that are not visible to the user through a perspective can still be directly referenced and retrieved using XML for Analysis (XMLA), Multidimensional Expressions (MDX), or Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="8ebd1-135">Las perspectivas no restringen el acceso a los objetos de un cubo y no deben usarse con este fin; en lugar de ello, se usan para proporcionar una mejor experiencia para el usuario al obtener acceso a un cubo.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-135">Perspectives do not restrict access to objects in a cube and should not be used as such; instead, perspectives are used to provide a better user experience while accessing a cube.</span></span>  
  
 <span data-ttu-id="8ebd1-136">Una perspectiva es una vista de solo lectura del cubo; no se pueden cambiar los nombres de los objetos ni los objetos del cubo en una perspectiva.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-136">A perspective is a read-only view of the cube; objects in the cube cannot be renamed or changed by using a perspective.</span></span> <span data-ttu-id="8ebd1-137">De forma similar, el comportamiento o las características de un cubo, como el uso de totales visuales, no se puede cambiar en una perspectiva.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-137">Similarly, the behavior or features of a cube, such as the use of visual totals, cannot be changed by using a perspective.</span></span>  
  
## <a name="security"></a><span data-ttu-id="8ebd1-138">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8ebd1-138">Security</span></span>  
 <span data-ttu-id="8ebd1-139">Las perspectivas no están diseñadas para usarse como mecanismo de seguridad, sino como una herramienta para proporcionar una mejor experiencia para el usuario en las aplicaciones de Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-139">Perspectives are not meant to be used as a security mechanism, but as a tool for providing a better user experience in business intelligence applications.</span></span> <span data-ttu-id="8ebd1-140">Toda la seguridad de una determinada perspectiva se hereda del cubo subyacente.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-140">All security for a particular perspective is inherited from the underlying cube.</span></span> <span data-ttu-id="8ebd1-141">Por ejemplo, las perspectivas no pueden proporcionar acceso a objetos de un cubo al que el usuario no tiene acceso.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-141">For example, perspectives cannot provide access to objects in a cube to which a user does not already have access.</span></span> <span data-ttu-id="8ebd1-142">- La seguridad del cubo se debe resolver para tener acceso a objetos del cubo mediante una perspectiva.</span><span class="sxs-lookup"><span data-stu-id="8ebd1-142">- Security for the cube must be resolved before access to objects in the cube can be provided through a perspective.</span></span>  
  
  