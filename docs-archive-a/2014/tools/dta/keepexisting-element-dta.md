---
title: KeepExisting (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- KeepExisting element
ms.assetid: e67aae61-d06d-4a03-85ba-6516c3502dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: cde9b3091b75f55e4b9c79137853fbd7d4e0daf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747356"
---
# <a name="keepexisting-element-dta"></a><span data-ttu-id="c734f-102">KeepExisting (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="c734f-102">KeepExisting Element (DTA)</span></span>
  <span data-ttu-id="c734f-103">Especifica las estructuras de diseño físico (índices, vistas indizadas o particiones) que el Asistente para la optimización de motor de base de datos debe conservar al generar su recomendación.</span><span class="sxs-lookup"><span data-stu-id="c734f-103">Specifies the physical design structures (indexes, indexed views, or partitioning) that Database Engine Tuning Advisor must retain when generating its recommendation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c734f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c734f-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <KeepExisting>...</KeepExisting>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="c734f-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="c734f-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="c734f-106">Característica</span><span class="sxs-lookup"><span data-stu-id="c734f-106">Characteristic</span></span>|<span data-ttu-id="c734f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c734f-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c734f-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="c734f-108">**Data type and length**</span></span>|<span data-ttu-id="c734f-109">`string`, límite de longitud aplicado por el servidor.</span><span class="sxs-lookup"><span data-stu-id="c734f-109">`string`, length limit enforced by the server.</span></span>|  
|<span data-ttu-id="c734f-110">**Valores permitidos**</span><span class="sxs-lookup"><span data-stu-id="c734f-110">**Allowed values**</span></span>|<span data-ttu-id="c734f-111">**NONE**</span><span class="sxs-lookup"><span data-stu-id="c734f-111">**NONE**</span></span><br /> <span data-ttu-id="c734f-112">Ninguna estructura existente.</span><span class="sxs-lookup"><span data-stu-id="c734f-112">No existing structures.</span></span><br /><br /> <span data-ttu-id="c734f-113">**ALL**</span><span class="sxs-lookup"><span data-stu-id="c734f-113">**ALL**</span></span><br /> <span data-ttu-id="c734f-114">Todas las estructuras existentes.</span><span class="sxs-lookup"><span data-stu-id="c734f-114">All existing structures.</span></span><br /><br /> <span data-ttu-id="c734f-115">**ALIGNED**</span><span class="sxs-lookup"><span data-stu-id="c734f-115">**ALIGNED**</span></span><br /> <span data-ttu-id="c734f-116">Todas las estructuras alineadas de partición.</span><span class="sxs-lookup"><span data-stu-id="c734f-116">All partition-aligned structures.</span></span><br /><br /> <span data-ttu-id="c734f-117">**CL_IDX**</span><span class="sxs-lookup"><span data-stu-id="c734f-117">**CL_IDX**</span></span><br /> <span data-ttu-id="c734f-118">Todos los clúster de las tablas.</span><span class="sxs-lookup"><span data-stu-id="c734f-118">All clustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="c734f-119">**IDX**</span><span class="sxs-lookup"><span data-stu-id="c734f-119">**IDX**</span></span><br /> <span data-ttu-id="c734f-120">Todos los índices clúster y no clúster de las tablas.</span><span class="sxs-lookup"><span data-stu-id="c734f-120">All clustered and nonclustered indexes on tables.</span></span><br /><br /> <span data-ttu-id="c734f-121">Utilice solo uno de estos valores con este elemento.</span><span class="sxs-lookup"><span data-stu-id="c734f-121">Use only one of these values with this element.</span></span>|  
|<span data-ttu-id="c734f-122">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="c734f-122">**Default value**</span></span>|<span data-ttu-id="c734f-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c734f-123">None.</span></span>|  
|<span data-ttu-id="c734f-124">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="c734f-124">**Occurrence**</span></span>|<span data-ttu-id="c734f-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="c734f-125">Optional.</span></span> <span data-ttu-id="c734f-126">Se puede utilizar una sola vez por cada elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="c734f-126">Can use only once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="c734f-127">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="c734f-127">Element Relationships</span></span>  
  
|<span data-ttu-id="c734f-128">Relación</span><span class="sxs-lookup"><span data-stu-id="c734f-128">Relationship</span></span>|<span data-ttu-id="c734f-129">Elementos</span><span class="sxs-lookup"><span data-stu-id="c734f-129">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="c734f-130">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="c734f-130">**Parent element**</span></span>|[<span data-ttu-id="c734f-131">TuningOptions &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="c734f-131">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="c734f-132">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="c734f-132">**Child elements**</span></span>|<span data-ttu-id="c734f-133">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c734f-133">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c734f-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c734f-134">Example</span></span>  
 <span data-ttu-id="c734f-135">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML simple &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="c734f-135">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c734f-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c734f-136">See Also</span></span>  
 [<span data-ttu-id="c734f-137">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c734f-137">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
