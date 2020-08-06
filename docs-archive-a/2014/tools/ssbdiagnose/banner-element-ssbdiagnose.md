---
title: Elemento banner (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- banner element
- XML output file format [ssbdiagnose], banner element
- ssbdiagnose
ms.assetid: cc6cd49a-acf0-4cfb-8c6a-554692b89de2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13238ac4ef1745dea4fbf3392484ac6137c09df1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751622"
---
# <a name="banner-element-ssbdiagnose"></a><span data-ttu-id="2c66e-102">Elemento Banner (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="2c66e-102">Banner Element (ssbdiagnose)</span></span>
  <span data-ttu-id="2c66e-103">Identifica la utilidad que generó el archivo de salida XML de **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="2c66e-103">Identifies which utility generated the **ssbdiagnose** output XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c66e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c66e-104">Syntax</span></span>  
  
```  
  
<Banner  
    title="..."   
    product="..."   
    version="..." />  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="2c66e-105">Atributos del elemento</span><span class="sxs-lookup"><span data-stu-id="2c66e-105">Element Attributes</span></span>  
  
|<span data-ttu-id="2c66e-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="2c66e-106">Attribute</span></span>|<span data-ttu-id="2c66e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c66e-107">Description</span></span>|  
|---------------|-----------------|  
|`title`|<span data-ttu-id="2c66e-108">Identifica la utilidad que generó el archivo de salida XML de **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="2c66e-108">Identifies the utility that generated the **ssbdiagnose** XML output file.</span></span>|  
|`product`|<span data-ttu-id="2c66e-109">Identifica el producto que generó el archivo de salida XML de **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="2c66e-109">Identifies the product that generated the **ssbdiagnose** XML output file.</span></span>|  
|`version`|<span data-ttu-id="2c66e-110">Identifica la versión de la utilidad que generó el archivo de salida XML.</span><span class="sxs-lookup"><span data-stu-id="2c66e-110">Identifies which version of the utility generated the XML output file.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="2c66e-111">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="2c66e-111">Element Characteristics</span></span>  
  
|<span data-ttu-id="2c66e-112">Característica</span><span class="sxs-lookup"><span data-stu-id="2c66e-112">Characteristic</span></span>|<span data-ttu-id="2c66e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c66e-113">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2c66e-114">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="2c66e-114">**Data type and length**</span></span>|<span data-ttu-id="2c66e-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2c66e-115">None.</span></span>|  
|<span data-ttu-id="2c66e-116">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="2c66e-116">**Default value**</span></span>|<span data-ttu-id="2c66e-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2c66e-117">None.</span></span>|  
|<span data-ttu-id="2c66e-118">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="2c66e-118">**Occurrence**</span></span>|<span data-ttu-id="2c66e-119">Se produce una vez por archivo de salida XML de **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="2c66e-119">Occurs once per **ssbdiagnose** output XML file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="2c66e-120">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="2c66e-120">Element Relationships</span></span>  
  
|<span data-ttu-id="2c66e-121">Relación</span><span class="sxs-lookup"><span data-stu-id="2c66e-121">Relationship</span></span>|<span data-ttu-id="2c66e-122">Elementos</span><span class="sxs-lookup"><span data-stu-id="2c66e-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="2c66e-123">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="2c66e-123">**Parent element**</span></span>|[<span data-ttu-id="2c66e-124">Elemento DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="2c66e-124">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)|  
|<span data-ttu-id="2c66e-125">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="2c66e-125">**Child elements**</span></span>|<span data-ttu-id="2c66e-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2c66e-126">None.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2c66e-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c66e-127">Example</span></span>  
 <span data-ttu-id="2c66e-128">Este es un ejemplo de un elemento banner.</span><span class="sxs-lookup"><span data-stu-id="2c66e-128">This is an example of a banner element.</span></span>  
  
```  
<Banner title="Service Broker Diagnostics Utility" product="Microsoft SQL Server" version="10.0.1073.0" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c66e-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2c66e-129">See Also</span></span>  
 [<span data-ttu-id="2c66e-130">Utilidad ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="2c66e-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
