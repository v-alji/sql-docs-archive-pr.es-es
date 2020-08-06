---
title: TuningOptions (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningOptions element
ms.assetid: 58a22ba1-8e03-411f-bd46-85e4540f217a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2fab1c55c9d036424142b2692e8335ea65c22340
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747820"
---
# <a name="tuningoptions-element-dta"></a><span data-ttu-id="89189-102">TuningOptions (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="89189-102">TuningOptions Element (DTA)</span></span>
  <span data-ttu-id="89189-103">Contiene las opciones de optimización de una sesión de optimización concreta.</span><span class="sxs-lookup"><span data-stu-id="89189-103">Contains the tuning options for a specific tuning session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89189-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89189-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
    <Server>  
...code removed...  
    <Workload>...</Workload>  
    <TuningOptions>...</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="89189-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="89189-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="89189-106">Característica</span><span class="sxs-lookup"><span data-stu-id="89189-106">Characteristic</span></span>|<span data-ttu-id="89189-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="89189-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="89189-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="89189-108">**Data type and length**</span></span>|<span data-ttu-id="89189-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="89189-109">None.</span></span>|  
|<span data-ttu-id="89189-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="89189-110">**Default value**</span></span>|<span data-ttu-id="89189-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="89189-111">None.</span></span>|  
|<span data-ttu-id="89189-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="89189-112">**Occurrence**</span></span>|<span data-ttu-id="89189-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="89189-113">Optional.</span></span> <span data-ttu-id="89189-114">Si se utiliza, solo puede hacerse una vez para cada elemento `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="89189-114">If used, can only be used once for each `DTAInput` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="89189-115">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="89189-115">Element Relationships</span></span>  
  
|<span data-ttu-id="89189-116">Relación</span><span class="sxs-lookup"><span data-stu-id="89189-116">Relationship</span></span>|<span data-ttu-id="89189-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="89189-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="89189-118">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="89189-118">**Parent element**</span></span>|[<span data-ttu-id="89189-119">Elemento DTAInput &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="89189-119">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)|  
|<span data-ttu-id="89189-120">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="89189-120">**Child elements**</span></span>|<span data-ttu-id="89189-121">Elemento `ReportSet`.</span><span class="sxs-lookup"><span data-stu-id="89189-121">`ReportSet` element.</span></span> <span data-ttu-id="89189-122">Para obtener más información, vea el [esquema XML del Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="89189-122">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="89189-123">Elemento `TuningLogTable`.</span><span class="sxs-lookup"><span data-stu-id="89189-123">`TuningLogTable` element.</span></span> <span data-ttu-id="89189-124">Para obtener más información, vea el [esquema XML del Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="89189-124">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="89189-125">Elemento `NumberOfEvents`.</span><span class="sxs-lookup"><span data-stu-id="89189-125">`NumberOfEvents` element.</span></span> <span data-ttu-id="89189-126">Para obtener más información, vea el [esquema XML del Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="89189-126">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> [<span data-ttu-id="89189-127">TuningTimeInMin &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="89189-127">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)<br /><br /> [<span data-ttu-id="89189-128">StorageBoundInMB &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="89189-128">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)<br /><br /> <span data-ttu-id="89189-129">Elemento `MaxKeyColumnsInIndex`.</span><span class="sxs-lookup"><span data-stu-id="89189-129">`MaxKeyColumnsInIndex` element.</span></span> <span data-ttu-id="89189-130">Para obtener más información, vea el [esquema XML del Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="89189-130">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="89189-131">Elemento `MaxColumnsInIndex`.</span><span class="sxs-lookup"><span data-stu-id="89189-131">`MaxColumnsInIndex` element.</span></span> <span data-ttu-id="89189-132">Para obtener más información, vea el [esquema XML del Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="89189-132">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="89189-133">Elemento `MinPercentageImprovement`.</span><span class="sxs-lookup"><span data-stu-id="89189-133">`MinPercentageImprovement` element.</span></span> <span data-ttu-id="89189-134">Para obtener más información, vea el [esquema XML del Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?linkid=43100)</span><span class="sxs-lookup"><span data-stu-id="89189-134">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100)</span></span><br /><br /> [<span data-ttu-id="89189-135">TestServer &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="89189-135">TestServer Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="89189-136">FeatureSet &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="89189-136">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="89189-137">Partitioning &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="89189-137">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> [<span data-ttu-id="89189-138">DropOnlyMode &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="89189-138">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)<br /><br /> [<span data-ttu-id="89189-139">KeepExisting &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="89189-139">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)<br /><br /> [<span data-ttu-id="89189-140">OnlineIndexOperation &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="89189-140">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)<br /><br /> [<span data-ttu-id="89189-141">DatabaseToConnect &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="89189-141">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)<br /><br /> <span data-ttu-id="89189-142">Elemento `IgnoreConstantsInWorkload`.</span><span class="sxs-lookup"><span data-stu-id="89189-142">`IgnoreConstantsInWorkload` element.</span></span> <span data-ttu-id="89189-143">Para obtener más información, vea el [esquema XML del Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="89189-143">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span><br /><br /> <span data-ttu-id="89189-144">Elemento `RetainShellDB`.</span><span class="sxs-lookup"><span data-stu-id="89189-144">`RetainShellDB` element.</span></span> <span data-ttu-id="89189-145">Para obtener más información, vea el [esquema XML del Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="89189-145">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="89189-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="89189-146">Example</span></span>  
 <span data-ttu-id="89189-147">Para obtener ejemplos del `TuningOptions` elemento, vea los [ejemplos de archivos de entrada XML &#40;DTA&#41;](xml-input-file-samples-dta.md).</span><span class="sxs-lookup"><span data-stu-id="89189-147">For examples of the `TuningOptions` element, see the [XML Input File Samples &#40;DTA&#41;](xml-input-file-samples-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89189-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89189-148">See Also</span></span>  
 [<span data-ttu-id="89189-149">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="89189-149">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
