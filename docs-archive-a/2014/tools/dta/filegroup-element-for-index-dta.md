---
title: Filegroup (DTA, elemento de index) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Filegroup element [DTA]
ms.assetid: 7078d2fb-fa77-44fc-beb3-c095088fcb85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5ed8ea723d6c0798b93e16411ee47d6e956c6c22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747832"
---
# <a name="filegroup-element-for-index-dta"></a><span data-ttu-id="67ff7-102">Filegroup (DTA, elemento de Index)</span><span class="sxs-lookup"><span data-stu-id="67ff7-102">Filegroup Element for Index (DTA)</span></span>
  <span data-ttu-id="67ff7-103">Especifica el grupo de archivos de una configuración especificada por el usuario en que se va a crear el índice.</span><span class="sxs-lookup"><span data-stu-id="67ff7-103">Specifies the filegroup on which the index is to be created for a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67ff7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67ff7-104">Syntax</span></span>  
  
```  
  
<Index>  
  <Name>...</Name>  
  <Column>  
    <Name>...</Name>  
  <Filegroup>...</Filegroup>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="67ff7-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="67ff7-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="67ff7-106">Característica</span><span class="sxs-lookup"><span data-stu-id="67ff7-106">Characteristic</span></span>|<span data-ttu-id="67ff7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="67ff7-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="67ff7-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="67ff7-108">**Data type and length**</span></span>|<span data-ttu-id="67ff7-109">`string`, longitud ilimitada.</span><span class="sxs-lookup"><span data-stu-id="67ff7-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="67ff7-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="67ff7-110">**Default value**</span></span>|<span data-ttu-id="67ff7-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="67ff7-111">None.</span></span>|  
|<span data-ttu-id="67ff7-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="67ff7-112">**Occurrence**</span></span>|<span data-ttu-id="67ff7-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="67ff7-113">Optional.</span></span> <span data-ttu-id="67ff7-114">Se puede utilizar una vez por cada elemento `Index`.</span><span class="sxs-lookup"><span data-stu-id="67ff7-114">Can use once for each `Index` element.</span></span> <span data-ttu-id="67ff7-115">Este elemento no se puede utilizar si se han especificado los elementos `PartitionScheme` y `PartitionColumn` para el elemento `Index`.</span><span class="sxs-lookup"><span data-stu-id="67ff7-115">This element cannot be used if the `PartitionScheme` and `PartitionColumn` elements are specified for the `Index` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="67ff7-116">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="67ff7-116">Element Relationships</span></span>  
  
|<span data-ttu-id="67ff7-117">Relación</span><span class="sxs-lookup"><span data-stu-id="67ff7-117">Relationship</span></span>|<span data-ttu-id="67ff7-118">Elementos</span><span class="sxs-lookup"><span data-stu-id="67ff7-118">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="67ff7-119">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="67ff7-119">**Parent element**</span></span>|[<span data-ttu-id="67ff7-120">Index &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="67ff7-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)|  
|<span data-ttu-id="67ff7-121">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="67ff7-121">**Child elements**</span></span>|<span data-ttu-id="67ff7-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="67ff7-122">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="67ff7-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67ff7-123">Example</span></span>  
 <span data-ttu-id="67ff7-124">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML con configuración especificada por el usuario &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="67ff7-124">For a usage example of this element, see [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ff7-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67ff7-125">See Also</span></span>  
 [<span data-ttu-id="67ff7-126">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="67ff7-126">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
