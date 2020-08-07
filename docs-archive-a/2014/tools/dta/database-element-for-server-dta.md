---
title: Database (DTA, elemento de Server) | Microsoft Docs
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
ms.assetid: 5cd9a87a-af4b-45f3-8c18-f7fd7e7d3064
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9a48d255898eff6bd780f8edf2c8d2da7229b0ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743784"
---
# <a name="database-element-for-server-dta"></a><span data-ttu-id="560a4-102">Elemento Database para servidor (DTA)</span><span class="sxs-lookup"><span data-stu-id="560a4-102">Database Element for Server (DTA)</span></span>
  <span data-ttu-id="560a4-103">Especifica la base de datos que se desea optimizar en un servidor concreto.</span><span class="sxs-lookup"><span data-stu-id="560a4-103">Specifies the database you want to tune on a specific server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="560a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="560a4-104">Syntax</span></span>  
  
```  
  
<Server>  
...code removed here...  
    <Database>...</Database>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="560a4-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="560a4-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="560a4-106">Característica</span><span class="sxs-lookup"><span data-stu-id="560a4-106">Characteristic</span></span>|<span data-ttu-id="560a4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="560a4-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="560a4-108">Tipo y longitud de los datos</span><span class="sxs-lookup"><span data-stu-id="560a4-108">Data type and length</span></span>|<span data-ttu-id="560a4-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="560a4-109">None.</span></span>|  
|<span data-ttu-id="560a4-110">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="560a4-110">Default value</span></span>|<span data-ttu-id="560a4-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="560a4-111">None.</span></span>|  
|<span data-ttu-id="560a4-112">Repetición</span><span class="sxs-lookup"><span data-stu-id="560a4-112">Occurrence</span></span>|<span data-ttu-id="560a4-113">Obligatoria una o más veces por elemento `Server`.</span><span class="sxs-lookup"><span data-stu-id="560a4-113">Required one or more times per `Server` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="560a4-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="560a4-114">Element Relationships</span></span>  
  
|<span data-ttu-id="560a4-115">Relación</span><span class="sxs-lookup"><span data-stu-id="560a4-115">Relationship</span></span>|<span data-ttu-id="560a4-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="560a4-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="560a4-117">Elemento primario</span><span class="sxs-lookup"><span data-stu-id="560a4-117">Parent element</span></span>|[<span data-ttu-id="560a4-118">Server &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="560a4-118">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)|  
|<span data-ttu-id="560a4-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="560a4-119">Child elements</span></span>|[<span data-ttu-id="560a4-120">Name &#40;DTA, elemento de Database&#41;</span><span class="sxs-lookup"><span data-stu-id="560a4-120">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)<br /><br /> [<span data-ttu-id="560a4-121">Schema &#40;DTA, elemento de Database&#41;</span><span class="sxs-lookup"><span data-stu-id="560a4-121">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="560a4-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="560a4-122">Remarks</span></span>  
 <span data-ttu-id="560a4-123">Este elemento tiene el nombre **DatabaseDetailsTypecomplexType** en el esquema XML del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="560a4-123">This element is of the **DatabaseDetailsTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="560a4-124">No confunda este elemento `Database` con el que tiene al elemento `Configuration` como raíz primaria.</span><span class="sxs-lookup"><span data-stu-id="560a4-124">Do not confuse this `Database` element with the one whose root parent is the `Configuration` element.</span></span> <span data-ttu-id="560a4-125">Para obtener más información, vea [Database &#40;DTA, elemento de Configuration&#41;](database-element-for-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="560a4-125">For more information, see [Database Element for Configuration &#40;DTA&#41;](database-element-for-configuration-dta.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="560a4-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="560a4-126">Example</span></span>  
 <span data-ttu-id="560a4-127">Para obtener un ejemplo de uso del `Database` elemento, vea [Server Element &#40;DTA&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="560a4-127">For a usage example of the `Database` element, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="560a4-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="560a4-128">See Also</span></span>  
 [<span data-ttu-id="560a4-129">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="560a4-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
