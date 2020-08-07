---
title: Name (DTA, elemento de Column) | Microsoft Docs
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
ms.assetid: f93b61de-01fe-4237-ada4-f1e481550564
author: stevestein
ms.author: sstein
ms.openlocfilehash: fad3d9a86a7c5db6b6a7503dc90b5a1540e3618b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743773"
---
# <a name="name-element-for-column-dta"></a><span data-ttu-id="46a3f-102">Name (DTA, elemento de Column)</span><span class="sxs-lookup"><span data-stu-id="46a3f-102">Name Element for Column (DTA)</span></span>
  <span data-ttu-id="46a3f-103">Especifica el nombre de una columna de índice en una configuración especificada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="46a3f-103">Specifies the name for an index column in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46a3f-104">Syntax</span></span>  
  
```  
  
<Index>  
    <Column>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="46a3f-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="46a3f-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="46a3f-106">Característica</span><span class="sxs-lookup"><span data-stu-id="46a3f-106">Characteristic</span></span>|<span data-ttu-id="46a3f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="46a3f-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="46a3f-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="46a3f-108">**Data type and length**</span></span>|<span data-ttu-id="46a3f-109">`string`, longitud ilimitada.</span><span class="sxs-lookup"><span data-stu-id="46a3f-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="46a3f-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="46a3f-110">**Default value**</span></span>|<span data-ttu-id="46a3f-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="46a3f-111">None.</span></span>|  
|<span data-ttu-id="46a3f-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="46a3f-112">**Occurrence**</span></span>|<span data-ttu-id="46a3f-113">Una obligatoria por cada elemento `Column`.</span><span class="sxs-lookup"><span data-stu-id="46a3f-113">Required once for each `Column` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="46a3f-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="46a3f-114">Element Relationships</span></span>  
  
|<span data-ttu-id="46a3f-115">Relación</span><span class="sxs-lookup"><span data-stu-id="46a3f-115">Relationship</span></span>|<span data-ttu-id="46a3f-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="46a3f-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="46a3f-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="46a3f-117">**Parent element**</span></span>|[<span data-ttu-id="46a3f-118">Column &#40;DTA, elemento de Index&#41;</span><span class="sxs-lookup"><span data-stu-id="46a3f-118">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)|  
|<span data-ttu-id="46a3f-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="46a3f-119">**Child elements**</span></span>|<span data-ttu-id="46a3f-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="46a3f-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="46a3f-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46a3f-121">Example</span></span>  
 <span data-ttu-id="46a3f-122">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML con configuración especificada por el usuario &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="46a3f-122">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46a3f-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46a3f-123">See Also</span></span>  
 [<span data-ttu-id="46a3f-124">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="46a3f-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
