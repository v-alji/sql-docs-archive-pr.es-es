---
title: Name (DTA, elemento de index) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Name element
ms.assetid: 2300e9cf-f0a8-49e6-b1f5-45ffe03ccb5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: a878923a3d483fae5ad6b55421a2b286f15ceb29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749533"
---
# <a name="name-element-for-index-dta"></a><span data-ttu-id="503af-102">Name (DTA, elemento de Index)</span><span class="sxs-lookup"><span data-stu-id="503af-102">Name Element for Index (DTA)</span></span>
  <span data-ttu-id="503af-103">Establece un nombre para un índice en la configuración especificada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="503af-103">Specifies a name for an index in the user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="503af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="503af-104">Syntax</span></span>  
  
```  
  
<Create>  
    <Index>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="503af-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="503af-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="503af-106">Característica</span><span class="sxs-lookup"><span data-stu-id="503af-106">Characteristic</span></span>|<span data-ttu-id="503af-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="503af-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="503af-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="503af-108">**Data type and length**</span></span>|<span data-ttu-id="503af-109">`string`, longitud ilimitada.</span><span class="sxs-lookup"><span data-stu-id="503af-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="503af-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="503af-110">**Default value**</span></span>|<span data-ttu-id="503af-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="503af-111">None.</span></span>|  
|<span data-ttu-id="503af-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="503af-112">**Occurrence**</span></span>|<span data-ttu-id="503af-113">Una obligatoria por cada elemento `Index`.</span><span class="sxs-lookup"><span data-stu-id="503af-113">Required once for each `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="503af-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="503af-114">Element Relationships</span></span>  
  
|<span data-ttu-id="503af-115">Relación</span><span class="sxs-lookup"><span data-stu-id="503af-115">Relationship</span></span>|<span data-ttu-id="503af-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="503af-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="503af-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="503af-117">**Parent element**</span></span>|[<span data-ttu-id="503af-118">Index &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="503af-118">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="503af-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="503af-119">**Child elements**</span></span>|<span data-ttu-id="503af-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="503af-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="503af-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="503af-121">Example</span></span>  
 <span data-ttu-id="503af-122">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML con configuración especificada por el usuario &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="503af-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="503af-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="503af-123">See Also</span></span>  
 [<span data-ttu-id="503af-124">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="503af-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
