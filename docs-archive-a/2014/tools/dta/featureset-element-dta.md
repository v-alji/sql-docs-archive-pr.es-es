---
title: FeatureSet (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- FeatureSet element
ms.assetid: f2070c53-4a5c-4c11-ac38-96ee200c84f0
author: stevestein
ms.author: sstein
ms.openlocfilehash: d36c28b24a56ef2dcdf69578fb7e8c196306a416
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748425"
---
# <a name="featureset-element-dta"></a><span data-ttu-id="85c05-102">FeatureSet (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="85c05-102">FeatureSet Element (DTA)</span></span>
  <span data-ttu-id="85c05-103">Contiene las estructuras de diseño físico (índices o vistas indizadas) que desea que utilice el Asistente para la optimización de motor de base de datos durante el análisis.</span><span class="sxs-lookup"><span data-stu-id="85c05-103">Contains the physical design structures (indexes or indexed views) that you would like Database Engine Tuning Advisor to use during analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85c05-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <FeatureSet>...</FeatureSet>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="85c05-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="85c05-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="85c05-106">Característica</span><span class="sxs-lookup"><span data-stu-id="85c05-106">Characteristic</span></span>|<span data-ttu-id="85c05-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="85c05-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="85c05-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="85c05-108">**Data type and length**</span></span>|<span data-ttu-id="85c05-109">`string`, sin longitud máxima.</span><span class="sxs-lookup"><span data-stu-id="85c05-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="85c05-110">**Valores permitidos**</span><span class="sxs-lookup"><span data-stu-id="85c05-110">**Allowed values**</span></span>|<span data-ttu-id="85c05-111">**IDX_IV**</span><span class="sxs-lookup"><span data-stu-id="85c05-111">**IDX_IV**</span></span><br /> <span data-ttu-id="85c05-112">Índices y vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="85c05-112">Indexes and indexed views.</span></span><br /><br /> <span data-ttu-id="85c05-113">**IDX**</span><span class="sxs-lookup"><span data-stu-id="85c05-113">**IDX**</span></span><br /> <span data-ttu-id="85c05-114">Solo índices.</span><span class="sxs-lookup"><span data-stu-id="85c05-114">Indexes only.</span></span><br /><br /> <span data-ttu-id="85c05-115">**IV**</span><span class="sxs-lookup"><span data-stu-id="85c05-115">**IV**</span></span><br /> <span data-ttu-id="85c05-116">Solo vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="85c05-116">Indexed views only.</span></span><br /><br /> <span data-ttu-id="85c05-117">**NCL_IDX**</span><span class="sxs-lookup"><span data-stu-id="85c05-117">**NCL_IDX**</span></span><br /> <span data-ttu-id="85c05-118">Solo índices no clúster.</span><span class="sxs-lookup"><span data-stu-id="85c05-118">Nonclustered indexes only.</span></span><br /><br /> <span data-ttu-id="85c05-119">Utilice uno de estos valores con este elemento.</span><span class="sxs-lookup"><span data-stu-id="85c05-119">Use one of these values with this element.</span></span>|  
|<span data-ttu-id="85c05-120">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="85c05-120">**Default value**</span></span>|<span data-ttu-id="85c05-121">**IDX**</span><span class="sxs-lookup"><span data-stu-id="85c05-121">**IDX**</span></span>|  
|<span data-ttu-id="85c05-122">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="85c05-122">**Occurrence**</span></span>|<span data-ttu-id="85c05-123">Una obligatoria para cada elemento `TuningOptions`, a menos que se utilice el elemento `DropOnlyMode`.</span><span class="sxs-lookup"><span data-stu-id="85c05-123">Required once for each `TuningOptions` element, unless the `DropOnlyMode` element is used.</span></span> <span data-ttu-id="85c05-124">Si se utiliza `DropOnlyMode`, no es posible utilizar `FeatureSet`.</span><span class="sxs-lookup"><span data-stu-id="85c05-124">If `DropOnlyMode` is used, you cannot use `FeatureSet`.</span></span> <span data-ttu-id="85c05-125">Estos elementos son mutuamente exclusivos.</span><span class="sxs-lookup"><span data-stu-id="85c05-125">These elements are mutually exclusive.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="85c05-126">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="85c05-126">Element Relationships</span></span>  
  
|<span data-ttu-id="85c05-127">Relación</span><span class="sxs-lookup"><span data-stu-id="85c05-127">Relationship</span></span>|<span data-ttu-id="85c05-128">Elementos</span><span class="sxs-lookup"><span data-stu-id="85c05-128">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="85c05-129">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="85c05-129">**Parent element**</span></span>|[<span data-ttu-id="85c05-130">TuningOptions &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="85c05-130">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="85c05-131">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="85c05-131">**Child elements**</span></span>|<span data-ttu-id="85c05-132">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="85c05-132">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="85c05-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="85c05-133">Example</span></span>  
 <span data-ttu-id="85c05-134">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML simple &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="85c05-134">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c05-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85c05-135">See Also</span></span>  
 [<span data-ttu-id="85c05-136">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="85c05-136">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
