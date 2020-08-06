---
title: TuningTimeInMin (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TuningTimeInMin element
ms.assetid: 4973d9ac-20fd-4ac3-bc9f-5d60e39fdb7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4dae3fe4e9ac3126f43ec017c34d2bc548fda6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747819"
---
# <a name="tuningtimeinmin-element-dta"></a><span data-ttu-id="789e2-102">TuningTimeInMin (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="789e2-102">TuningTimeInMin Element (DTA)</span></span>
  <span data-ttu-id="789e2-103">Especifica la duración máxima de una sesión de optimización en minutos.</span><span class="sxs-lookup"><span data-stu-id="789e2-103">Specifies the maximum length of a tuning session in minutes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="789e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="789e2-104">Syntax</span></span>  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <TuningTimeInMin>...</TuningTimeInMin>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="789e2-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="789e2-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="789e2-106">Característica</span><span class="sxs-lookup"><span data-stu-id="789e2-106">Characteristic</span></span>|<span data-ttu-id="789e2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="789e2-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="789e2-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="789e2-108">**Data type and length**</span></span>|<span data-ttu-id="789e2-109">`unsignedInt`, longitud ilimitada.</span><span class="sxs-lookup"><span data-stu-id="789e2-109">`unsignedInt`, unlimited length.</span></span>|  
|<span data-ttu-id="789e2-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="789e2-110">**Default value**</span></span>|<span data-ttu-id="789e2-111">480 minutos (8 horas).</span><span class="sxs-lookup"><span data-stu-id="789e2-111">480 minutes (8 hours).</span></span>|  
|<span data-ttu-id="789e2-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="789e2-112">**Occurrence**</span></span>|<span data-ttu-id="789e2-113">Obligatoria a menos que se haya especificado un valor para el elemento `NumberOfEvents`.</span><span class="sxs-lookup"><span data-stu-id="789e2-113">Required unless a value has been specified for the `NumberOfEvents` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="789e2-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="789e2-114">Element Relationships</span></span>  
  
|<span data-ttu-id="789e2-115">Relación</span><span class="sxs-lookup"><span data-stu-id="789e2-115">Relationship</span></span>|<span data-ttu-id="789e2-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="789e2-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="789e2-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="789e2-117">**Parent element**</span></span>|[<span data-ttu-id="789e2-118">TuningOptions &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="789e2-118">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="789e2-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="789e2-119">**Child elements**</span></span>|<span data-ttu-id="789e2-120">None</span><span class="sxs-lookup"><span data-stu-id="789e2-120">None</span></span>|  
  
## <a name="example"></a><span data-ttu-id="789e2-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="789e2-121">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="789e2-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="789e2-122">Description</span></span>  
 <span data-ttu-id="789e2-123">En el siguiente ejemplo de código se muestra cómo establecer un tiempo de optimización máximo de 12 horas:</span><span class="sxs-lookup"><span data-stu-id="789e2-123">The following code example shows how to set 12 hours as the maximum tuning time:</span></span>  
  
## <a name="code"></a><span data-ttu-id="789e2-124">Código</span><span class="sxs-lookup"><span data-stu-id="789e2-124">Code</span></span>  
  
```  
<DTAInput>  
  <Server>...</Server>  
  <Workload>...</Workload>  
  <TuningOptions>  
    <TuningTimeInMin>720</TuningTimeInMin>  
...code removed here...  
</DTAInput>  
```  
  
## <a name="see-also"></a><span data-ttu-id="789e2-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="789e2-125">See Also</span></span>  
 [<span data-ttu-id="789e2-126">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="789e2-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
