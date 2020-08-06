---
title: Programación de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- data mining [Analysis Services], developer's guide
ms.assetid: 9fd77b16-0b89-44ce-bcf1-7c04b62499da
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd4bd48b5914d5fda89f94c0a959e670ffec3321
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744423"
---
# <a name="data-mining-programming"></a><span data-ttu-id="139e4-102">Programación de minería de datos</span><span class="sxs-lookup"><span data-stu-id="139e4-102">Data Mining Programming</span></span>
  <span data-ttu-id="139e4-103">Si los visores y las herramientas integrados en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no cumplen sus requisitos, puede extender la capacidad de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] codificando sus propias extensiones.</span><span class="sxs-lookup"><span data-stu-id="139e4-103">If you find that the built-in tools and viewers in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] do not meet your requirements, you can extend the power of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by coding your own extensions.</span></span> <span data-ttu-id="139e4-104">En este enfoque, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="139e4-104">In this approach, you have two options:</span></span>  
  
-   <span data-ttu-id="139e4-105">**XMLA**</span><span class="sxs-lookup"><span data-stu-id="139e4-105">**XMLA**</span></span>  
  
     [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="139e4-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)]admite XML for Analysis (XMLA) como protocolo para la comunicación con aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="139e4-106">[!INCLUDE[ssASCurrent](../../includes/ssascurrent-md.md)] supports XML for Analysis (XMLA) as a protocol for communication with client applications.</span></span> <span data-ttu-id="139e4-107">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] admite comandos adicionales que amplían la especificación XML for Analysis.</span><span class="sxs-lookup"><span data-stu-id="139e4-107">Additional commands are supported by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that extend the XML for Analysis specification.</span></span>  
  
     <span data-ttu-id="139e4-108">Dado que [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utiliza XMLA para la compatibilidad con la definición, la manipulación y el control de los datos, puede crear estructuras y modelos de minería de datos mediante las herramientas visuales proporcionadas por [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] y extender, a continuación, los objetos de minería de datos que haya creado mediante scripts DMX (Extensiones de minería de datos) y ASSL (Analysis Services Scripting Language).</span><span class="sxs-lookup"><span data-stu-id="139e4-108">Because [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses XMLA for data definition, data manipulation, and data control support, you can create mining structures and mining models by using the visual tools provided by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], and then extend the data mining objects that you have created by using Data Mining Extensions (DMX) and Analysis Services Scripting Language (ASSL) scripts.</span></span>  
  
     <span data-ttu-id="139e4-109">Puede crear y modificar objetos de minería de datos íntegramente en scripts XMLA, además de ejecutar mediante programación consultas de predicción en los modelos desde sus propias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="139e4-109">You can create and modify data mining objects entirely in XMLA scripts, and run prediction queries against the models programmatically from your own applications.</span></span>  
  
-   <span data-ttu-id="139e4-110">**Objetos de administración de análisis (AMO)**</span><span class="sxs-lookup"><span data-stu-id="139e4-110">**Analysis Management Objects (AMO)**</span></span>  
  
     [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="139e4-111">también proporciona un marco completo que permite a los demás proveedores de minería de datos integrar los objetos de minería de datos en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="139e4-111">also provides a complete framework that enables third-party data mining providers to integrate the data mining objects into [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="139e4-112">Es posible crear estructuras y modelos de minería de datos mediante AMO.</span><span class="sxs-lookup"><span data-stu-id="139e4-112">You can create mining structures and mining models by using AMO.</span></span> <span data-ttu-id="139e4-113">Vea los ejemplos siguientes de CodePlex:</span><span class="sxs-lookup"><span data-stu-id="139e4-113">See the following samples in CodePlex:</span></span>  
  
    -   <span data-ttu-id="139e4-114">Explorador de AMO</span><span class="sxs-lookup"><span data-stu-id="139e4-114">AMO Browser</span></span>  
  
         <span data-ttu-id="139e4-115">Se conecta a la instancia de SSAS especificada y muestra todos los objetos de servidor y sus propiedades, incluidos la estructura y los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="139e4-115">Connects to the SSAS instance you specify and lists all server objects and their properties, including mining structure and mining models.</span></span>  
  
    -   <span data-ttu-id="139e4-116">Ejemplo simple de AMO</span><span class="sxs-lookup"><span data-stu-id="139e4-116">AMO Simple Sample</span></span>  
  
         <span data-ttu-id="139e4-117">El ejemplo simple de AS abarca el acceso mediante programación a la mayoría de los objetos principales, y muestra la exploración de los metadatos y el acceso a los valores de los objetos.</span><span class="sxs-lookup"><span data-stu-id="139e4-117">The AS Simple Sample covers programmatic access to most major objects, and demonstrates metadata browsing, and access to the values in objects.</span></span>  
  
         <span data-ttu-id="139e4-118">En el ejemplo también se muestra cómo crear y procesar una estructura y un modelo de minería de datos, y cómo examinar un modelo de minería de datos existente.</span><span class="sxs-lookup"><span data-stu-id="139e4-118">The sample also demonstrates how to create and process a data mining structure and model, as well as browse an existing data mining model.</span></span>  
  
-   <span data-ttu-id="139e4-119">**DMX**</span><span class="sxs-lookup"><span data-stu-id="139e4-119">**DMX**</span></span>  
  
     <span data-ttu-id="139e4-120">Puede usar DMX para encapsular instrucciones de comandos, consultas de predicción y consultas de metadatos, y devolver resultados en formato tabular, suponiendo que se haya creado una conexión con un servidor de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="139e4-120">You can use DMX to encapsulate command statements, prediction queries, and metadata queries and return results in a tabular format, assuming you have created a connection to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="139e4-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="139e4-121">In This Section</span></span>  
 [<span data-ttu-id="139e4-122">OLE DB para minería de datos</span><span class="sxs-lookup"><span data-stu-id="139e4-122">OLE DB for Data Mining</span></span>](../../../2014/analysis-services/dev-guide/ole-db-for-data-mining.md)  
 <span data-ttu-id="139e4-123">Describe las adiciones realizadas en la especificación para admitir la minería de datos y los datos multidimensionales: nuevas columnas y nuevos conjuntos de filas de esquema y el lenguaje DMX (Extensiones de minería de datos) para crear y administrar las estructuras de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="139e4-123">Describes additions to the specification to support data mining and multidimensional data: new schema rowsets and columns, Data Mining Extensions (DMX) language for creating and managing mining structures.</span></span>  
  
## <a name="related-reference"></a><span data-ttu-id="139e4-124">Referencia relacionada</span><span class="sxs-lookup"><span data-stu-id="139e4-124">Related Reference</span></span>  
 [<span data-ttu-id="139e4-125">Desarrollar con ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="139e4-125">Developing with ADOMD.NET</span></span>](https://docs.microsoft.com/bi-reference/adomd/developing-with-adomd-net)  
 <span data-ttu-id="139e4-126">Presenta los objetos de programación de cliente y servidor de ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="139e4-126">Introduces ADOMD.NET client and server programming objects.</span></span>  
  
 [<span data-ttu-id="139e4-127">Desarrollar con Objetos de administración de análisis &#40;AMO&#41;</span><span class="sxs-lookup"><span data-stu-id="139e4-127">Developing with Analysis Management Objects &#40;AMO&#41;</span></span>](https://docs.microsoft.com/bi-reference/amo/developing-with-analysis-management-objects-amo)  
 <span data-ttu-id="139e4-128">Presenta la biblioteca de programación de AMO.</span><span class="sxs-lookup"><span data-stu-id="139e4-128">Introduces the AMO programming library.</span></span>  
  
 [<span data-ttu-id="139e4-129">Desarrollar aplicaciones con Analysis Services Scripting Language &#40;ASSL&#41;</span><span class="sxs-lookup"><span data-stu-id="139e4-129">Developing with Analysis Services Scripting Language &#40;ASSL&#41;</span></span>](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)  
 <span data-ttu-id="139e4-130">Presenta XML for Analysis (XMLA) y sus extensiones.</span><span class="sxs-lookup"><span data-stu-id="139e4-130">Introduces XML for Analysis (XMLA) and its extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="139e4-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="139e4-131">See Also</span></span>  
 <span data-ttu-id="139e4-132">[Guía del desarrollador &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md) </span><span class="sxs-lookup"><span data-stu-id="139e4-132">[Developer's Guide &#40;Analysis Services&#41;](../analysis-services-developer-documentation.md) </span></span>  
 [<span data-ttu-id="139e4-133">Referencia de Extensiones de minería de datos &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="139e4-133">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
