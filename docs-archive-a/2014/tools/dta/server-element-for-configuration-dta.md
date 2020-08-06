---
title: Server (DTA, elemento de Configuration) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Server element
ms.assetid: da9ff870-9cfd-42fe-994b-7b9292681f7d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88182cdad2e7313f0910a106ee37d727d840bfed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675085"
---
# <a name="server-element-for-configuration-dta"></a><span data-ttu-id="2cfe6-102">Server (DTA, elemento de Configuration)</span><span class="sxs-lookup"><span data-stu-id="2cfe6-102">Server Element for Configuration (DTA)</span></span>
  <span data-ttu-id="2cfe6-103">Contiene la información de identificación del servidor en el que desea que el Asistente para la optimización de motor de base de datos evalúe la configuración hipotética (especificada por el elemento `Configuration`).</span><span class="sxs-lookup"><span data-stu-id="2cfe6-103">Contains the identifying information for the server where you want Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cfe6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2cfe6-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    <Server>  
...code removed here...  
    </Server>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="2cfe6-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="2cfe6-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="2cfe6-106">Característica</span><span class="sxs-lookup"><span data-stu-id="2cfe6-106">Characteristic</span></span>|<span data-ttu-id="2cfe6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2cfe6-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2cfe6-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="2cfe6-108">**Data type and length**</span></span>|<span data-ttu-id="2cfe6-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2cfe6-109">None.</span></span>|  
|<span data-ttu-id="2cfe6-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="2cfe6-110">**Default value**</span></span>|<span data-ttu-id="2cfe6-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2cfe6-111">None.</span></span>|  
|<span data-ttu-id="2cfe6-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="2cfe6-112">**Occurrence**</span></span>|<span data-ttu-id="2cfe6-113">Se requiere una vez por elemento `Configuration`.</span><span class="sxs-lookup"><span data-stu-id="2cfe6-113">Required once per `Configuration` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="2cfe6-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="2cfe6-114">Element Relationships</span></span>  
  
|<span data-ttu-id="2cfe6-115">Relación</span><span class="sxs-lookup"><span data-stu-id="2cfe6-115">Relationship</span></span>|<span data-ttu-id="2cfe6-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="2cfe6-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="2cfe6-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="2cfe6-117">**Parent element**</span></span>|[<span data-ttu-id="2cfe6-118">Elemento Configuration &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="2cfe6-118">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)|  
|<span data-ttu-id="2cfe6-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="2cfe6-119">**Child elements**</span></span>|[<span data-ttu-id="2cfe6-120">Name &#40;DTA, elemento de Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2cfe6-120">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)<br /><br /> [<span data-ttu-id="2cfe6-121">Database &#40;DTA, elemento de Configuration&#41;</span><span class="sxs-lookup"><span data-stu-id="2cfe6-121">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="2cfe6-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2cfe6-122">Remarks</span></span>  
 <span data-ttu-id="2cfe6-123">Solo puede especificar un `Server` elemento para el `Configuration` elemento.</span><span class="sxs-lookup"><span data-stu-id="2cfe6-123">You can specify only one `Server` element for the `Configuration` element.</span></span> <span data-ttu-id="2cfe6-124">Este elemento tiene el nombre **ServerTypecomplexType** en el [esquema XML del Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="2cfe6-124">This element is of the **ServerTypecomplexType** name in the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span> <span data-ttu-id="2cfe6-125">No confunda este elemento `Server` con el elemento secundario de `DTAInput`.</span><span class="sxs-lookup"><span data-stu-id="2cfe6-125">Do not confuse this `Server` element with the one that is the child of the `DTAInput` element.</span></span> <span data-ttu-id="2cfe6-126">Para obtener más información, vea [Server &#40;DTA, elemento&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="2cfe6-126">For more information, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cfe6-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2cfe6-127">Example</span></span>  
 <span data-ttu-id="2cfe6-128">Para obtener un ejemplo de uso, vea [Ejemplo de archivo de entrada XML con configuración especificada por el usuario &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="2cfe6-128">For a usage example, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cfe6-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2cfe6-129">See Also</span></span>  
 [<span data-ttu-id="2cfe6-130">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2cfe6-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
