---
title: Table (DTA, elemento de Schema) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Table element [DTA]
ms.assetid: a59e8319-05d1-47f3-af39-7d970ab8e7dc
author: stevestein
ms.author: sstein
ms.openlocfilehash: dd444b1da99b22e0259dc1f50818c1763b7052ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747830"
---
# <a name="table-element-for-schema-dta"></a><span data-ttu-id="f1821-102">Table (DTA, elemento de Schema)</span><span class="sxs-lookup"><span data-stu-id="f1821-102">Table Element for Schema (DTA)</span></span>
  <span data-ttu-id="f1821-103">Especifica la tabla que se va a optimizar.</span><span class="sxs-lookup"><span data-stu-id="f1821-103">Specifies the table for tuning.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1821-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1821-104">Syntax</span></span>  
  
```  
  
<Schema>  
...code removed here...  
    <Table>...</Table>  
```  
  
## <a name="element-attributes"></a><span data-ttu-id="f1821-105">Atributos del elemento</span><span class="sxs-lookup"><span data-stu-id="f1821-105">Element Attributes</span></span>  
  
|<span data-ttu-id="f1821-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="f1821-106">Attribute</span></span>|<span data-ttu-id="f1821-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1821-107">Description</span></span>|  
|---------------|-----------------|  
|`NumberOfRows`|<span data-ttu-id="f1821-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f1821-108">Optional.</span></span> <span data-ttu-id="f1821-109">Entero que permite simular tablas de diferentes tamaños.</span><span class="sxs-lookup"><span data-stu-id="f1821-109">Integer that allows you to simulate tables of different sizes.</span></span>|  
  
## <a name="element-characteristics"></a><span data-ttu-id="f1821-110">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="f1821-110">Element Characteristics</span></span>  
  
|<span data-ttu-id="f1821-111">Característica</span><span class="sxs-lookup"><span data-stu-id="f1821-111">Characteristic</span></span>|<span data-ttu-id="f1821-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1821-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f1821-113">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="f1821-113">**Data type and length**</span></span>|<span data-ttu-id="f1821-114">**string**, entre 1 y 255 caracteres.</span><span class="sxs-lookup"><span data-stu-id="f1821-114">**string**, between 1 and 255 characters.</span></span>|  
|<span data-ttu-id="f1821-115">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="f1821-115">**Default value**</span></span>|<span data-ttu-id="f1821-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f1821-116">None.</span></span>|  
|<span data-ttu-id="f1821-117">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="f1821-117">**Occurrence**</span></span>|<span data-ttu-id="f1821-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f1821-118">Optional.</span></span> <span data-ttu-id="f1821-119">Presenta tantas tablas como sea necesario para la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f1821-119">List as many tables as appropriate for your workload.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="f1821-120">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="f1821-120">Element Relationships</span></span>  
  
|<span data-ttu-id="f1821-121">Relación</span><span class="sxs-lookup"><span data-stu-id="f1821-121">Relationship</span></span>|<span data-ttu-id="f1821-122">Elementos</span><span class="sxs-lookup"><span data-stu-id="f1821-122">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="f1821-123">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="f1821-123">**Parent element**</span></span>|[<span data-ttu-id="f1821-124">Schema &#40;DTA, elemento de Database&#41;</span><span class="sxs-lookup"><span data-stu-id="f1821-124">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)|  
|<span data-ttu-id="f1821-125">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="f1821-125">**Child elements**</span></span>|[<span data-ttu-id="f1821-126">Elemento Name de Table &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="f1821-126">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)|  
  
## <a name="remarks"></a><span data-ttu-id="f1821-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f1821-127">Remarks</span></span>  
 <span data-ttu-id="f1821-128">Si no se especifica un elemento `Table`, el Asistente para la optimización de motor de base de datos asumirá que todas las tablas de la base de datos especificada se pueden optimizar.</span><span class="sxs-lookup"><span data-stu-id="f1821-128">If you do not specify a `Table` element, Database Engine Tuning Advisor will assume all tables on the specified database can be tuned.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1821-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1821-129">Example</span></span>  
 <span data-ttu-id="f1821-130">Para obtener un ejemplo de uso, vea [Server &#40;DTA, elemento&#41;](server-element-dta.md).</span><span class="sxs-lookup"><span data-stu-id="f1821-130">For a usage example, see [Server Element &#40;DTA&#41;](server-element-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1821-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1821-131">See Also</span></span>  
 [<span data-ttu-id="f1821-132">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="f1821-132">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
