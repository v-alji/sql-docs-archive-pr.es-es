---
title: StorageBoundInMB (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- StorageBoundInMB element
ms.assetid: a8374910-bf68-4edb-b464-53a3a705e7f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea49b0af981b8f8d96efb087033d8f1466364c76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747834"
---
# <a name="storageboundinmb-element-dta"></a><span data-ttu-id="02113-102">StorageBoundInMB (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="02113-102">StorageBoundInMB Element (DTA)</span></span>
  <span data-ttu-id="02113-103">Especifica el espacio máximo en megabytes que puede consumir la recomendación de optimización del Asistente para la optimización de motor de base de datos (conjunto de índices y particiones).</span><span class="sxs-lookup"><span data-stu-id="02113-103">Specifies the maximum space in megabytes that can be consumed by the Database Engine Tuning Advisor tuning recommendation (index and partitioning set).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02113-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02113-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <StorageBoundInMB>...</ StorageBoundInMB >  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="02113-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="02113-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="02113-106">Característica</span><span class="sxs-lookup"><span data-stu-id="02113-106">Characteristic</span></span>|<span data-ttu-id="02113-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="02113-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="02113-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="02113-108">**Data type and length**</span></span>|<span data-ttu-id="02113-109">`unsignedInt`, longitud ilimitada.</span><span class="sxs-lookup"><span data-stu-id="02113-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="02113-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="02113-110">**Default value**</span></span>|<span data-ttu-id="02113-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="02113-111">None.</span></span>|  
|<span data-ttu-id="02113-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="02113-112">**Occurrence**</span></span>|<span data-ttu-id="02113-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="02113-113">Optional.</span></span> <span data-ttu-id="02113-114">Solo puede utilizarse una vez para el elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="02113-114">Can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="02113-115">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="02113-115">Element Relationships</span></span>  
  
|<span data-ttu-id="02113-116">Relación</span><span class="sxs-lookup"><span data-stu-id="02113-116">Relationship</span></span>|<span data-ttu-id="02113-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="02113-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="02113-118">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="02113-118">**Parent element**</span></span>|[<span data-ttu-id="02113-119">TuningOptions &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="02113-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="02113-120">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="02113-120">**Child elements**</span></span>|<span data-ttu-id="02113-121">None</span><span class="sxs-lookup"><span data-stu-id="02113-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02113-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="02113-122">Remarks</span></span>  
 <span data-ttu-id="02113-123">Cuando se optimizan varias bases de datos, se tienen en cuenta las recomendaciones para todas las bases de datos sobre el cálculo del espacio.</span><span class="sxs-lookup"><span data-stu-id="02113-123">When multiple databases are tuned, recommendations for all databases are considered for the space calculation.</span></span> <span data-ttu-id="02113-124">De forma predeterminada, el Asistente para la optimización de motor de base de datos asume el menor de los siguientes tamaños de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="02113-124">By default, Database Engine Tuning Advisor assumes the smaller of the following storage sizes:</span></span>  
  
-   <span data-ttu-id="02113-125">Tres veces el tamaño actual de los datos sin procesar, lo que incluye el tamaño total de los montones y los clúster de las tablas.</span><span class="sxs-lookup"><span data-stu-id="02113-125">Three times the current raw data size, which includes the total size of heaps and clustered indexes on tables.</span></span>  
  
-   <span data-ttu-id="02113-126">El espacio disponible en todas las unidades de disco adjuntas más el tamaño de los datos sin procesar.</span><span class="sxs-lookup"><span data-stu-id="02113-126">The free space on all attached disk drives plus the raw data size.</span></span>  
  
 <span data-ttu-id="02113-127">El tamaño de almacenamiento predeterminado no incluye los índices no clúster ni las vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="02113-127">The default storage size does not include nonclustered indexes and indexed views.</span></span>  
  
 <span data-ttu-id="02113-128">Si el valor especificado para el elemento `StorageBoundInMB` supera el espacio en disco real, el Asistente para la optimización de motor de base de datos devuelve un error, aunque continúa optimizando.</span><span class="sxs-lookup"><span data-stu-id="02113-128">If the value specified for the `StorageBoundInMB` element exceeds the actual disk space, Database Engine Tuning Advisor returns an error, but continues tuning.</span></span> <span data-ttu-id="02113-129">Una vez finalizada la optimización, puede agregar espacio en disco si decide seguir la recomendación.</span><span class="sxs-lookup"><span data-stu-id="02113-129">After tuning is complete, you can add disk space if you decide to implement the recommendation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02113-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02113-130">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="02113-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="02113-131">Description</span></span>  
 <span data-ttu-id="02113-132">El siguiente ejemplo de código muestra cómo establecer un límite de 1500 megabytes como el máximo espacio en disco que una recomendación de optimización puede utilizar:</span><span class="sxs-lookup"><span data-stu-id="02113-132">The following code example shows how to set a limit of 1500 megabytes as the maximum disk space that a tuning recommendation can consume:</span></span>  
  
## <a name="code"></a><span data-ttu-id="02113-133">Código</span><span class="sxs-lookup"><span data-stu-id="02113-133">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <StorageBoundInMB>1500</StorageBoundInMB>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02113-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02113-134">See Also</span></span>  
 [<span data-ttu-id="02113-135">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="02113-135">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
