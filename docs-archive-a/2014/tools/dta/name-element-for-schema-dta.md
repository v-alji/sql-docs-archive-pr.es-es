---
title: Name (DTA, elemento de Schema) | Microsoft Docs
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
ms.assetid: 014e4854-fed2-454b-8557-5f7c5bb6b17a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 678a6d58b35b25be2aed6d91fcae7ceb2640bdcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747341"
---
# <a name="name-element-for-schema-dta"></a><span data-ttu-id="1f772-102">Name (DTA, elemento de Schema)</span><span class="sxs-lookup"><span data-stu-id="1f772-102">Name Element for Schema (DTA)</span></span>
  <span data-ttu-id="1f772-103">Contiene el nombre del esquema.</span><span class="sxs-lookup"><span data-stu-id="1f772-103">Contains name of the schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f772-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f772-104">Syntax</span></span>  
  
```  
  
<Database>  
...code removed here  
    <Schema>  
        <Name>...</Name>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="1f772-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="1f772-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="1f772-106">Característica</span><span class="sxs-lookup"><span data-stu-id="1f772-106">Characteristic</span></span>|<span data-ttu-id="1f772-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f772-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1f772-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="1f772-108">**Data type and length**</span></span>|<span data-ttu-id="1f772-109">`string`, entre 1 y 255 caracteres</span><span class="sxs-lookup"><span data-stu-id="1f772-109">`string`, between 1 and 255 characters</span></span>|  
|<span data-ttu-id="1f772-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="1f772-110">**Default value**</span></span>|<span data-ttu-id="1f772-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1f772-111">None.</span></span>|  
|<span data-ttu-id="1f772-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="1f772-112">**Occurrence**</span></span>|<span data-ttu-id="1f772-113">Una obligatoria por elemento **Schema** .</span><span class="sxs-lookup"><span data-stu-id="1f772-113">Required once per **Schema** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="1f772-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="1f772-114">Element Relationships</span></span>  
  
|<span data-ttu-id="1f772-115">Relación</span><span class="sxs-lookup"><span data-stu-id="1f772-115">Relationship</span></span>|<span data-ttu-id="1f772-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="1f772-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="1f772-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="1f772-117">**Parent element**</span></span>|[<span data-ttu-id="1f772-118">Schema &#40;DTA, elemento de Database&#41;</span><span class="sxs-lookup"><span data-stu-id="1f772-118">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="1f772-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="1f772-119">**Child elements**</span></span>|<span data-ttu-id="1f772-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1f772-120">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1f772-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f772-121">Example</span></span>  
 <span data-ttu-id="1f772-122">Para obtener un ejemplo del uso de este elemento, vea [Elemento Server &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="1f772-122">For a usage example of this element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f772-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f772-123">See Also</span></span>  
 [<span data-ttu-id="1f772-124">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="1f772-124">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
