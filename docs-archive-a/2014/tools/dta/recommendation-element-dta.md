---
title: Recommendation (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Recommendation element
ms.assetid: 679ea535-865a-4633-a4d3-5b3090515158
author: stevestein
ms.author: sstein
ms.openlocfilehash: b4eb54a106d67f0217a2604b2d08754d0d2c0765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663879"
---
# <a name="recommendation-element-dta"></a><span data-ttu-id="3f534-102">Recommendation (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="3f534-102">Recommendation Element (DTA)</span></span>
  <span data-ttu-id="3f534-103">Contiene información sobre los índices hipotéticos que forman parte de una configuración especificada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3f534-103">Contains information about the hypothetical indexes that are part of a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f534-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f534-104">Syntax</span></span>  
  
```  
  
<Configuration>  
    ...code removed here...  
    <Table>  
      <Name>...</Name>  
      <Recommendation>  
      ...code removed here...  
      </Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="3f534-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="3f534-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="3f534-106">Característica</span><span class="sxs-lookup"><span data-stu-id="3f534-106">Characteristic</span></span>|<span data-ttu-id="3f534-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f534-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3f534-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="3f534-108">**Data type and length**</span></span>|<span data-ttu-id="3f534-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3f534-109">None.</span></span>|  
|<span data-ttu-id="3f534-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="3f534-110">**Default value**</span></span>|<span data-ttu-id="3f534-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3f534-111">None.</span></span>|  
|<span data-ttu-id="3f534-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="3f534-112">**Occurrence**</span></span>|<span data-ttu-id="3f534-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="3f534-113">Optional.</span></span> <span data-ttu-id="3f534-114">Se puede utilizar una vez por cada elemento `Table`.</span><span class="sxs-lookup"><span data-stu-id="3f534-114">Can use once for each `Table` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="3f534-115">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="3f534-115">Element Relationships</span></span>  
  
|<span data-ttu-id="3f534-116">Relación</span><span class="sxs-lookup"><span data-stu-id="3f534-116">Relationship</span></span>|<span data-ttu-id="3f534-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="3f534-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="3f534-118">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="3f534-118">**Parent element**</span></span>|[<span data-ttu-id="3f534-119">Table &#40;DTA, elemento de Schema&#41;</span><span class="sxs-lookup"><span data-stu-id="3f534-119">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)|  
|<span data-ttu-id="3f534-120">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="3f534-120">**Child elements**</span></span>|[<span data-ttu-id="3f534-121">Create &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="3f534-121">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)<br /><br /> <span data-ttu-id="3f534-122">Elemento `Drop`.</span><span class="sxs-lookup"><span data-stu-id="3f534-122">`Drop` element.</span></span> <span data-ttu-id="3f534-123">Para obtener más información, vea el [esquema XML del Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="3f534-123">For more information, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f534-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3f534-124">Remarks</span></span>  
 <span data-ttu-id="3f534-125">Este elemento tiene el nombre **RecommendationTypecomplexType** en el esquema XML del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="3f534-125">This element is of the **RecommendationTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="3f534-126">Se utiliza para especificar índices para una configuración hipotética.</span><span class="sxs-lookup"><span data-stu-id="3f534-126">It is used to specify indexes for a hypothetical configuration.</span></span> <span data-ttu-id="3f534-127">No confunda este elemento `Recommendation` con los otros tipos que se pueden utilizar para especificar particiones (`RecommendationPType`) o vistas (`RecommendationViewType`).</span><span class="sxs-lookup"><span data-stu-id="3f534-127">Do not confuse this `Recommendation` element with the other types that can be used to specify partitioning (`RecommendationPType`) or views (`RecommendationViewType`).</span></span> <span data-ttu-id="3f534-128">Para obtener información sobre estos otros `Recommendation` tipos de elementos, vea el [esquema XML de Asistente para la optimización de motor de base de datos](https://go.microsoft.com/fwlink/?linkid=43100).</span><span class="sxs-lookup"><span data-stu-id="3f534-128">For information about these other `Recommendation` element types, see the [Database Engine Tuning Advisor XML schema](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f534-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3f534-129">Example</span></span>  
 <span data-ttu-id="3f534-130">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML con configuración especificada por el usuario &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="3f534-130">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f534-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f534-131">See Also</span></span>  
 [<span data-ttu-id="3f534-132">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="3f534-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
