---
title: DTAInput (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DTAInput element
ms.assetid: 40c19abf-ded5-43de-be96-5b43b1b81b03
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7d2ff380a4ae1595e50aae472efc5fb4ac72efe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744456"
---
# <a name="dtainput-element-dta"></a><span data-ttu-id="938f1-102">DTAInput (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="938f1-102">DTAInput Element (DTA)</span></span>
  <span data-ttu-id="938f1-103">Contiene la definición de la entrada XML del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="938f1-103">Contains the definition of XML input for Database Engine Tuning Advisor.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="938f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="938f1-104">Syntax</span></span>  
  
```  
  
<DTAXML>  
    <DTAInput>  
    ...code removed here...  
    </DTAInput>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="938f1-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="938f1-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="938f1-106">Características</span><span class="sxs-lookup"><span data-stu-id="938f1-106">Characteristics</span></span>|<span data-ttu-id="938f1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="938f1-107">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="938f1-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="938f1-108">**Data type and length**</span></span>|<span data-ttu-id="938f1-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="938f1-109">None.</span></span>|  
|<span data-ttu-id="938f1-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="938f1-110">**Default value**</span></span>|<span data-ttu-id="938f1-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="938f1-111">None.</span></span>|  
|<span data-ttu-id="938f1-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="938f1-112">**Occurrence**</span></span>|<span data-ttu-id="938f1-113">Una opcional por elemento **DTAXML** .</span><span class="sxs-lookup"><span data-stu-id="938f1-113">Optional once per **DTAXML** element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="938f1-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="938f1-114">Element Relationships</span></span>  
  
|<span data-ttu-id="938f1-115">Relación</span><span class="sxs-lookup"><span data-stu-id="938f1-115">Relationship</span></span>|<span data-ttu-id="938f1-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="938f1-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="938f1-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="938f1-117">**Parent element**</span></span>|[<span data-ttu-id="938f1-118">Elemento DTAXML &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="938f1-118">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)|  
|<span data-ttu-id="938f1-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="938f1-119">**Child elements**</span></span>|[<span data-ttu-id="938f1-120">Server &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="938f1-120">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)<br /><br /> [<span data-ttu-id="938f1-121">Workload &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="938f1-121">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)<br /><br /> [<span data-ttu-id="938f1-122">TuningOptions &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="938f1-122">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)<br /><br /> [<span data-ttu-id="938f1-123">Elemento Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="938f1-123">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="938f1-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="938f1-124">Remarks</span></span>  
 <span data-ttu-id="938f1-125">Este elemento es la raíz de la jerarquía del esquema de entrada del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="938f1-125">This element is the root of the Database Engine Tuning Advisor input schema hierarchy.</span></span> <span data-ttu-id="938f1-126">La entrada del Asistente para la optimización de motor de base de datos pueden ser argumentos que especifiquen los servidores cuyas bases de datos se desean optimizar, cargas de trabajo, opciones de optimización o una configuración especificada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="938f1-126">Input to Database Engine Tuning Advisor can be arguments that specify the servers whose databases you want to tune, workloads, tuning options, or a user-specified configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="938f1-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="938f1-127">Example</span></span>  
 <span data-ttu-id="938f1-128">Para obtener un ejemplo de uso del elemento **DTAInput**, vea [Ejemplo de archivo de entrada XML simple &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span><span class="sxs-lookup"><span data-stu-id="938f1-128">For a usage example of the **DTAInput** element, see [Simple XML Input File Sample &#40;DTA&#41;](simple-xml-input-file-sample-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="938f1-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="938f1-129">See Also</span></span>  
 [<span data-ttu-id="938f1-130">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="938f1-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
