---
title: OnlineIndexOperation (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- OnlineIndexOperation element
ms.assetid: 7c5614cd-09aa-4a59-9591-347aa7d36473
author: stevestein
ms.author: sstein
ms.openlocfilehash: 48943c1b31d7a0a24ae939050d44494476e50034
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675092"
---
# <a name="onlineindexoperation-element-dta"></a><span data-ttu-id="09d38-102">OnlineIndexOperation (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="09d38-102">OnlineIndexOperation Element (DTA)</span></span>
  <span data-ttu-id="09d38-103">Especifica si los índices, las vistas indizadas o las particiones recomendados por el Asistente para la optimización de motor de base de datos se pueden crear en línea.</span><span class="sxs-lookup"><span data-stu-id="09d38-103">Specifies whether the indexes, indexed views, or partitions that Database Engine Tuning Advisor recommends can be created online.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09d38-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <OnlineIndexOperation>...</OnlineIndexOperation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="09d38-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="09d38-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="09d38-106">Característica</span><span class="sxs-lookup"><span data-stu-id="09d38-106">Characteristic</span></span>|<span data-ttu-id="09d38-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="09d38-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="09d38-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="09d38-108">**Data type and length**</span></span>|<span data-ttu-id="09d38-109">`string`, sin longitud máxima.</span><span class="sxs-lookup"><span data-stu-id="09d38-109">`string`, no maximum length.</span></span>|  
|<span data-ttu-id="09d38-110">**Valores permitidos**</span><span class="sxs-lookup"><span data-stu-id="09d38-110">**Allowed values**</span></span>|<span data-ttu-id="09d38-111">**OFF**</span><span class="sxs-lookup"><span data-stu-id="09d38-111">**OFF**</span></span><br /> <span data-ttu-id="09d38-112">No se pueden crear en línea las estructuras recomendadas de diseño físico.</span><span class="sxs-lookup"><span data-stu-id="09d38-112">No recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="09d38-113">**ON**</span><span class="sxs-lookup"><span data-stu-id="09d38-113">**ON**</span></span><br /> <span data-ttu-id="09d38-114">Se pueden crear en línea todas las estructuras recomendadas de diseño físico.</span><span class="sxs-lookup"><span data-stu-id="09d38-114">All recommended physical design structures can be created online.</span></span><br /><br /> <span data-ttu-id="09d38-115">**COMBINACIÓN**</span><span class="sxs-lookup"><span data-stu-id="09d38-115">**MIXED**</span></span><br /> <span data-ttu-id="09d38-116">Siempre que es posible, el Asistente para la optimización de motor de base de datos intenta recomendar las estructuras de diseño físico que se pueden crear en línea.</span><span class="sxs-lookup"><span data-stu-id="09d38-116">Database Engine Tuning Advisor attempts to recommend physical design structures that can be created online when possible.</span></span><br /><br /> <span data-ttu-id="09d38-117">Utilice uno de estos valores con este elemento.</span><span class="sxs-lookup"><span data-stu-id="09d38-117">Use one of these values with this element.</span></span> <span data-ttu-id="09d38-118">Si los índices se crean en línea, se anexa la palabra clave **ONLINE = ON** a la definición del objeto.</span><span class="sxs-lookup"><span data-stu-id="09d38-118">If indexes are created online, the keyword **ONLINE = ON** is appended to its object definition.</span></span>|  
|<span data-ttu-id="09d38-119">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="09d38-119">**Default value**</span></span>|<span data-ttu-id="09d38-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="09d38-120">None.</span></span>|  
|<span data-ttu-id="09d38-121">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="09d38-121">**Occurrence**</span></span>|<span data-ttu-id="09d38-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="09d38-122">Optional.</span></span> <span data-ttu-id="09d38-123">Si se utiliza, solo puede hacerse una vez para el elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="09d38-123">If used, can only be used once for the `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="09d38-124">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="09d38-124">Element Relationships</span></span>  
  
|<span data-ttu-id="09d38-125">Relación</span><span class="sxs-lookup"><span data-stu-id="09d38-125">Relationship</span></span>|<span data-ttu-id="09d38-126">Elementos</span><span class="sxs-lookup"><span data-stu-id="09d38-126">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="09d38-127">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="09d38-127">**Parent element**</span></span>|[<span data-ttu-id="09d38-128">TuningOptions &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="09d38-128">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="09d38-129">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="09d38-129">**Child elements**</span></span>|<span data-ttu-id="09d38-130">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="09d38-130">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="09d38-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09d38-131">Example</span></span>  
 <span data-ttu-id="09d38-132">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML simple &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="09d38-132">For a usage example of this element, see the [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09d38-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09d38-133">See Also</span></span>  
 [<span data-ttu-id="09d38-134">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="09d38-134">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
