---
title: Elemento DiagnosticInformation (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose], diagnosticinformation element
- diagnosticinformation element
- ssbdiagnose
ms.assetid: 0cfda544-542c-4cf4-86d2-8031c91b10f6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92d76a065c24ddc1fc8d85989ed3202308571951
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670248"
---
# <a name="diagnosticinformation-element-ssbdiagnose"></a><span data-ttu-id="3755c-102">Elemento DiagnosticInformation (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="3755c-102">DiagnosticInformation Element (ssbdiagnose)</span></span>
  <span data-ttu-id="3755c-103">El elemento **DiagnosticInformation** contiene todos los elementos que incluyen la información de diagnóstico generada por la utilidad.</span><span class="sxs-lookup"><span data-stu-id="3755c-103">The **DiagnosticInformation** element contains all elements that report the diagnostic information found by the utility.</span></span> <span data-ttu-id="3755c-104">**DiagnosticInformation** es el elemento raíz de un archivo de salida XML **ssbdiagnostic** .</span><span class="sxs-lookup"><span data-stu-id="3755c-104">**DiagnosticInformation** is the root element of a **ssbdiagnostic** XML output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3755c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3755c-105">Syntax</span></span>  
  
```  
  
<DiagnosticInformation>   
    ...   
</DiagnosticInformation>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="3755c-106">Atributos del elemento</span><span class="sxs-lookup"><span data-stu-id="3755c-106">Element Attributes</span></span>  
  
|<span data-ttu-id="3755c-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="3755c-107">Attribute</span></span>|<span data-ttu-id="3755c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3755c-108">Description</span></span>|  
|---------------|-----------------|  
|`None`|<span data-ttu-id="3755c-109">N/D</span><span class="sxs-lookup"><span data-stu-id="3755c-109">N/A</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="3755c-110">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="3755c-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="3755c-111">Característica</span><span class="sxs-lookup"><span data-stu-id="3755c-111">Characteristic</span></span>|<span data-ttu-id="3755c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3755c-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3755c-113">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="3755c-113">**Data type and length**</span></span>|<span data-ttu-id="3755c-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3755c-114">None.</span></span>|  
|<span data-ttu-id="3755c-115">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="3755c-115">**Default value**</span></span>|<span data-ttu-id="3755c-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3755c-116">None.</span></span>|  
|<span data-ttu-id="3755c-117">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="3755c-117">**Occurrence**</span></span>|<span data-ttu-id="3755c-118">Una vez por archivo de salida XML **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="3755c-118">Once per **ssbdiagnose** XML output file.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="3755c-119">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="3755c-119">Element Relationships</span></span>  
  
|<span data-ttu-id="3755c-120">Relación</span><span class="sxs-lookup"><span data-stu-id="3755c-120">Relationship</span></span>|<span data-ttu-id="3755c-121">Elementos</span><span class="sxs-lookup"><span data-stu-id="3755c-121">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="3755c-122">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="3755c-122">**Parent element**</span></span>|<span data-ttu-id="3755c-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3755c-123">None.</span></span>|  
|<span data-ttu-id="3755c-124">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="3755c-124">**Child elements**</span></span>|[<span data-ttu-id="3755c-125">Elemento Banner &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="3755c-125">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)<br /><br /> [<span data-ttu-id="3755c-126">Elemento Issue &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="3755c-126">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)|  
  
## <a name="remarks"></a><span data-ttu-id="3755c-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3755c-127">Remarks</span></span>  
 <span data-ttu-id="3755c-128">Para obtener más información acerca de los espacios de nombres XML, vea el artículo sobre [espacios de nombres en un documento XML](https://go.microsoft.com/fwlink/?LinkId=7341) en [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="3755c-128">For more information about XML namespaces, see [Namespaces in an XML Document](https://go.microsoft.com/fwlink/?LinkId=7341) in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] MSDN Library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3755c-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3755c-129">See Also</span></span>  
 [<span data-ttu-id="3755c-130">Utilidad ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="3755c-130">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
