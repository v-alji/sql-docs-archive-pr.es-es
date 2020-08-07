---
title: Database (DTA, elemento de Configuration) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database element
ms.assetid: e91ba243-6cc9-457a-8f5a-134f3c71ae69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 69ce1a0ac9912907f6d22916dd6243621e0778db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743785"
---
# <a name="database-element-for-configuration-dta"></a><span data-ttu-id="608ae-102">Database (DTA, elemento de Configuration)</span><span class="sxs-lookup"><span data-stu-id="608ae-102">Database Element for Configuration (DTA)</span></span>
  <span data-ttu-id="608ae-103">Especifica la base de datos en la que desea que el Asistente para la optimización de motor de base de datos evalúe la configuración hipotética (especificada por el elemento `Configuration`).</span><span class="sxs-lookup"><span data-stu-id="608ae-103">Specifies the database against which you want the Database Engine Tuning Advisor to evaluate the hypothetical configuration (specified by the `Configuration` element).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="608ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="608ae-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="608ae-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="608ae-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="608ae-106">Característica</span><span class="sxs-lookup"><span data-stu-id="608ae-106">Characteristic</span></span>|<span data-ttu-id="608ae-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="608ae-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="608ae-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="608ae-108">**Data type and length**</span></span>|<span data-ttu-id="608ae-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="608ae-109">None.</span></span>|  
|<span data-ttu-id="608ae-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="608ae-110">**Default value**</span></span>|<span data-ttu-id="608ae-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="608ae-111">None.</span></span>|  
|<span data-ttu-id="608ae-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="608ae-112">**Occurrence**</span></span>|<span data-ttu-id="608ae-113">Obligatoria una o más veces por elemento `Server`.</span><span class="sxs-lookup"><span data-stu-id="608ae-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="608ae-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="608ae-114">Element Relationships</span></span>  
  
|<span data-ttu-id="608ae-115">Relación</span><span class="sxs-lookup"><span data-stu-id="608ae-115">Relationship</span></span>|<span data-ttu-id="608ae-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="608ae-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="608ae-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="608ae-117">**Parent element**</span></span>|[<span data-ttu-id="608ae-118">Server &#40;DTA, elemento de Configuration&#41;</span><span class="sxs-lookup"><span data-stu-id="608ae-118">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)|  
|<span data-ttu-id="608ae-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="608ae-119">**Child elements**</span></span>|[<span data-ttu-id="608ae-120">Name &#40;DTA, elemento de Database&#41;</span><span class="sxs-lookup"><span data-stu-id="608ae-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="608ae-121">Schema &#40;DTA, elemento de Database&#41;</span><span class="sxs-lookup"><span data-stu-id="608ae-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="608ae-122">Elemento Recommendation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="608ae-122">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="608ae-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="608ae-123">Remarks</span></span>  
 <span data-ttu-id="608ae-124">Este elemento tiene el nombre **DatabaseTypecomplexType** en el esquema XML del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="608ae-124">This element is of the **DatabaseTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="608ae-125">No confunda este elemento `Database` con el que tiene al elemento `Server` como raíz primaria, que se encuentra en la parte superior del archivo de entrada XML.</span><span class="sxs-lookup"><span data-stu-id="608ae-125">Do not confuse this `Database` element with the one whose root parent is the `Server` element, which occurs at the top of the XML input file.</span></span> <span data-ttu-id="608ae-126">Para obtener más información, vea [Elemento Database para servidor &#40;DTA&#41;](database-element-for-server-dta.md).</span><span class="sxs-lookup"><span data-stu-id="608ae-126">For more information, see [Database Element for Server &#40;DTA&#41;](database-element-for-server-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="608ae-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="608ae-127">Example</span></span>  
 <span data-ttu-id="608ae-128">Para obtener un ejemplo de uso de este `Database` elemento, vea el [ejemplo de archivo de entrada XML con configuración especificada por el usuario &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="608ae-128">For a usage example of this `Database` element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="608ae-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="608ae-129">See Also</span></span>  
 [<span data-ttu-id="608ae-130">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="608ae-130">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
