---
title: TestServer (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- TestServer element
ms.assetid: caa3547a-2cd5-47ad-ace2-a36752835cfe
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d1f1fadf76a43caca262652254e8a778602183c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747831"
---
# <a name="testserver-element-dta"></a><span data-ttu-id="0b26d-102">TestServer (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="0b26d-102">TestServer Element (DTA)</span></span>
  <span data-ttu-id="0b26d-103">Especifica el servidor de prueba que se va a utilizar al optimizar un servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="0b26d-103">Specifies the test server to use when tuning a production server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b26d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b26d-104">Syntax</span></span>  
  
```  
  
<TuningOptions>  
  <TestServer>...</TestServer>  
   ...code removed here...  
</TuningOptions>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="0b26d-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="0b26d-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="0b26d-106">Característica</span><span class="sxs-lookup"><span data-stu-id="0b26d-106">Characteristic</span></span>|<span data-ttu-id="0b26d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b26d-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0b26d-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="0b26d-108">**Data type and length**</span></span>|<span data-ttu-id="0b26d-109">**string**, longitud ilimitada.</span><span class="sxs-lookup"><span data-stu-id="0b26d-109">**string**, unlimited length.</span></span>|  
|<span data-ttu-id="0b26d-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="0b26d-110">**Default value**</span></span>|<span data-ttu-id="0b26d-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0b26d-111">None.</span></span>|  
|<span data-ttu-id="0b26d-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="0b26d-112">**Occurrence**</span></span>|<span data-ttu-id="0b26d-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="0b26d-113">Optional.</span></span> <span data-ttu-id="0b26d-114">Se puede utilizar una vez por cada elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="0b26d-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="0b26d-115">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="0b26d-115">Element Relationships</span></span>  
  
|<span data-ttu-id="0b26d-116">Relación</span><span class="sxs-lookup"><span data-stu-id="0b26d-116">Relationship</span></span>|<span data-ttu-id="0b26d-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="0b26d-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="0b26d-118">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="0b26d-118">**Parent element**</span></span>|[<span data-ttu-id="0b26d-119">TuningOptions &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="0b26d-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="0b26d-120">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="0b26d-120">**Child elements**</span></span>|<span data-ttu-id="0b26d-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0b26d-121">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0b26d-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b26d-122">Example</span></span>  
 <span data-ttu-id="0b26d-123">Para obtener un ejemplo de uso de este elemento, vea [Reducir la carga de optimización del servidor de producción](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span><span class="sxs-lookup"><span data-stu-id="0b26d-123">For a usage example of this element, see [Reduce the Production Server Tuning Load](../../relational-databases/performance/reduce-the-production-server-tuning-load.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b26d-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b26d-124">See Also</span></span>  
 [<span data-ttu-id="0b26d-125">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="0b26d-125">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
