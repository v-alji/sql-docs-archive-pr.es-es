---
title: DropOnlyMode (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DropOnlyMode element
ms.assetid: 80960676-7581-4074-889b-80ee665963dd
author: stevestein
ms.author: sstein
ms.openlocfilehash: b274dc394a933308cf2161cc271d09b8391900c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743780"
---
# <a name="droponlymode-element-dta"></a><span data-ttu-id="7a532-102">DropOnlyMode (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="7a532-102">DropOnlyMode Element (DTA)</span></span>
  <span data-ttu-id="7a532-103">Especifica que el Asistente para la optimización de motor de base de datos solo debe quitar índices, vistas indizadas o particiones ya existentes durante la sesión de optimización.</span><span class="sxs-lookup"><span data-stu-id="7a532-103">Specifies that Database Engine Tuning Advisor should only consider dropping existing indexes, indexed views, or partitions during the tuning session.</span></span> <span data-ttu-id="7a532-104">Cuando se especifica esta opción de optimización, no se consideran nuevas estructuras de diseño físico.</span><span class="sxs-lookup"><span data-stu-id="7a532-104">No new physical design structures are considered when this tuning option is specified.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a532-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a532-105">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <DropOnlyMode>...</DropOnlyMode>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="7a532-106">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="7a532-106">Element Characteristics</span></span>  
  
|<span data-ttu-id="7a532-107">Característica</span><span class="sxs-lookup"><span data-stu-id="7a532-107">Characteristic</span></span>|<span data-ttu-id="7a532-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a532-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7a532-109">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="7a532-109">**Data type and length**</span></span>|<span data-ttu-id="7a532-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7a532-110">None.</span></span>|  
|<span data-ttu-id="7a532-111">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="7a532-111">**Default value**</span></span>|<span data-ttu-id="7a532-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7a532-112">None.</span></span>|  
|<span data-ttu-id="7a532-113">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="7a532-113">**Occurrence**</span></span>|<span data-ttu-id="7a532-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="7a532-114">Optional.</span></span> <span data-ttu-id="7a532-115">Se puede utilizar una sola vez por cada elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="7a532-115">Can use only once for each `TuningOptions` element.</span></span> <span data-ttu-id="7a532-116">No se puede utilizar si se especifican los siguientes elementos en el elemento `TuningOptions`:</span><span class="sxs-lookup"><span data-stu-id="7a532-116">Cannot be used if the following elements are specified in the `TuningOptions` element:</span></span><br /><br /> [<span data-ttu-id="7a532-117">FeatureSet &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="7a532-117">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)<br /><br /> [<span data-ttu-id="7a532-118">Partitioning &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="7a532-118">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)<br /><br /> <span data-ttu-id="7a532-119">[KeepExisting &#40;DTA, elemento&#41;](keepexisting-element-dta.md) se establece en **ALL**</span><span class="sxs-lookup"><span data-stu-id="7a532-119">[KeepExisting Element &#40;DTA&#41;](keepexisting-element-dta.md) is set to **ALL**</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="7a532-120">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="7a532-120">Element Relationships</span></span>  
  
|<span data-ttu-id="7a532-121">Relación</span><span class="sxs-lookup"><span data-stu-id="7a532-121">Relationship</span></span>|<span data-ttu-id="7a532-122">Elementos</span><span class="sxs-lookup"><span data-stu-id="7a532-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="7a532-123">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="7a532-123">**Parent element**</span></span>|[<span data-ttu-id="7a532-124">TuningOptions &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="7a532-124">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="7a532-125">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="7a532-125">**Child elements**</span></span>|<span data-ttu-id="7a532-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7a532-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7a532-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7a532-127">Example</span></span>  
 <span data-ttu-id="7a532-128">El ejemplo siguiente muestra la sección `TuningOptions` de un archivo de entrada XML del Asistente para la optimización de motor de base de datos donde se especifica `DropOnlyMode`.</span><span class="sxs-lookup"><span data-stu-id="7a532-128">The following example shows the `TuningOptions` section of a Database Engine Tuning Advisor XML input file where the `DropOnlyMode` is specified.</span></span> <span data-ttu-id="7a532-129">En este ejemplo, la hora de optimización se limita a 24 horas (1440 minutos) y se considerará la eliminación de todos los clúster y no clúster existentes:</span><span class="sxs-lookup"><span data-stu-id="7a532-129">In this example the tuning time is limited to 24 hours (1440 minutes) and all existing clustered and nonclustered indexes will be considered for dropping:</span></span>  
  
```xml  
<TuningOptions  
  <TuningTimeInMin>1440</Name>  
  <KeepExisting>ALIGNED</KeepExisting>  
  <DropOnlyMode />  
</TuningOptions>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a532-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a532-130">See Also</span></span>  
 [<span data-ttu-id="7a532-131">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7a532-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
