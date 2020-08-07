---
title: Configuration (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Configuration element
ms.assetid: 1478e56f-57c4-4441-bac9-1ac91453839b
author: stevestein
ms.author: sstein
ms.openlocfilehash: d11938d9a9a694f994a3ea977022a393cbae23d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743797"
---
# <a name="configuration-element-dta"></a><span data-ttu-id="fcc78-102">Configuration (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="fcc78-102">Configuration Element (DTA)</span></span>
  <span data-ttu-id="fcc78-103">Establece una configuración especificada por el usuario compuesta por estructuras de diseño físico existentes e hipotéticas para que el Asistente para la optimización de motor de base de datos la analice al optimizar una carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fcc78-103">Specifies a user-specified configuration consisting of existing and hypothetical physical design structures for the Database Engine Tuning Advisor to analyze when tuning a workload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc78-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcc78-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>...</Server>  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions  
    <Configuration [SpecificationMode="Relative" | "Absolute"]>  
    ...code removed here...  
    </Configuration>  
</DTAInput>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="fcc78-105">Atributos del elemento</span><span class="sxs-lookup"><span data-stu-id="fcc78-105">Element Attributes</span></span>  
  
|<span data-ttu-id="fcc78-106">Atributo Configuration</span><span class="sxs-lookup"><span data-stu-id="fcc78-106">Configuration Attribute</span></span>|<span data-ttu-id="fcc78-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcc78-107">Description</span></span>|  
|-----------------------------|-----------------|  
|`SpecificationMode`|<span data-ttu-id="fcc78-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fcc78-108">Optional.</span></span> <span data-ttu-id="fcc78-109">Especifica si el Asistente para la optimización de motor de base de datos debe analizar la configuración especificada con respecto a la configuración actual existente o como una independiente totalmente nueva.</span><span class="sxs-lookup"><span data-stu-id="fcc78-109">Specifies whether Database Engine Tuning Advisor should analyze the specified configuration in relation to the current existing configuration, or as a completely new, standalone one.</span></span> <span data-ttu-id="fcc78-110">Utilice un tipo de datos **string** para especificar este atributo mediante uno de los siguientes valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="fcc78-110">Use a **string** data type to specify this attribute with one of the following allowed values:</span></span><br /><br /> <span data-ttu-id="fcc78-111">`Relative`:</span><span class="sxs-lookup"><span data-stu-id="fcc78-111">`Relative`:</span></span> <br />                  <span data-ttu-id="fcc78-112">Evalúa la configuración especificada con respecto a la configuración actual existente de las estructuras de diseño físico (índices, vistas indizadas, particiones) de la base de datos que se está optimizando.</span><span class="sxs-lookup"><span data-stu-id="fcc78-112">Evaluates the specified configuration in relation to the current existing configuration of physical design structures (indexes, indexed views, partitioning) in the database that is being tuned.</span></span> <span data-ttu-id="fcc78-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fcc78-113">For example:</span></span> <br />`<Configuration SpecificationMode="Relative">`<br /><br /> <span data-ttu-id="fcc78-114">`Absolute`:</span><span class="sxs-lookup"><span data-stu-id="fcc78-114">`Absolute`:</span></span> <br />                  <span data-ttu-id="fcc78-115">Evalúa la configuración especificada como una configuración independiente.</span><span class="sxs-lookup"><span data-stu-id="fcc78-115">Evaluates the specified configuration as a standalone configuration.</span></span> <span data-ttu-id="fcc78-116">Cuando se especifica Absolute, el Asistente para la optimización de motor de base de datos no tiene en cuenta la configuración existente.</span><span class="sxs-lookup"><span data-stu-id="fcc78-116">When Absolute is specified, Database Engine Tuning Advisor does not consider the existing configuration.</span></span> <span data-ttu-id="fcc78-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fcc78-117">For example:</span></span><br />`<Configuration SpecificationMode="Absolute">`|  
  
## <a name="element-characteristics"></a><span data-ttu-id="fcc78-118">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="fcc78-118">Element Characteristics</span></span>  
  
|<span data-ttu-id="fcc78-119">Característica</span><span class="sxs-lookup"><span data-stu-id="fcc78-119">Characteristic</span></span>|<span data-ttu-id="fcc78-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcc78-120">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="fcc78-121">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="fcc78-121">**Data type and length**</span></span>|<span data-ttu-id="fcc78-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fcc78-122">None.</span></span>|  
|<span data-ttu-id="fcc78-123">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="fcc78-123">**Default value**</span></span>|<span data-ttu-id="fcc78-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fcc78-124">None.</span></span>|  
|<span data-ttu-id="fcc78-125">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="fcc78-125">**Occurrence**</span></span>|<span data-ttu-id="fcc78-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="fcc78-126">Optional.</span></span> <span data-ttu-id="fcc78-127">Se puede utilizar una vez por cada elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="fcc78-127">Can use once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="fcc78-128">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="fcc78-128">Element Relationships</span></span>  
  
|<span data-ttu-id="fcc78-129">Relación</span><span class="sxs-lookup"><span data-stu-id="fcc78-129">Relationship</span></span>|<span data-ttu-id="fcc78-130">Elementos</span><span class="sxs-lookup"><span data-stu-id="fcc78-130">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="fcc78-131">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="fcc78-131">**Parent element**</span></span>|[<span data-ttu-id="fcc78-132">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="fcc78-132">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="fcc78-133">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="fcc78-133">**Child elements**</span></span>|[<span data-ttu-id="fcc78-134">Server &#40;DTA, elemento de Configuration&#41;</span><span class="sxs-lookup"><span data-stu-id="fcc78-134">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)|  
  
## <a name="example"></a><span data-ttu-id="fcc78-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fcc78-135">Example</span></span>  
 <span data-ttu-id="fcc78-136">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML con configuración especificada por el usuario &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="fcc78-136">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc78-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcc78-137">See Also</span></span>  
 [<span data-ttu-id="fcc78-138">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="fcc78-138">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
