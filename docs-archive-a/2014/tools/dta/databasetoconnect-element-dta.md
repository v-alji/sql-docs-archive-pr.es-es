---
title: DatabaseToConnect (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- DatabaseToConnect element
ms.assetid: 65153a66-3aee-4429-99b7-0816ac23c285
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c21b36319e4007264677d499b84964c7cb5ea7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743782"
---
# <a name="databasetoconnect-element-dta"></a><span data-ttu-id="4ee0b-102">DatabaseToConnect (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="4ee0b-102">DatabaseToConnect Element (DTA)</span></span>
  <span data-ttu-id="4ee0b-103">Especifica la primera base de datos a la que se conecta el Asistente para la optimización de motor de base de datos al optimizar una carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4ee0b-103">Specifies the first database to which Database Engine Tuning Advisor connects when tuning a workload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ee0b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ee0b-104">Syntax</span></span>  
  
```  
  
    <TuningOptions>  
...code removed here...  
      <DatabaseToConnect>...</DatabaseToConnect>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="4ee0b-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="4ee0b-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="4ee0b-106">Característica</span><span class="sxs-lookup"><span data-stu-id="4ee0b-106">Characteristic</span></span>|<span data-ttu-id="4ee0b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ee0b-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4ee0b-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="4ee0b-108">**Data type and length**</span></span>|<span data-ttu-id="4ee0b-109">`string`, longitud ilimitada.</span><span class="sxs-lookup"><span data-stu-id="4ee0b-109">`string`, unlimited length.</span></span>|  
|<span data-ttu-id="4ee0b-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="4ee0b-110">**Default value**</span></span>|<span data-ttu-id="4ee0b-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4ee0b-111">None.</span></span>|  
|<span data-ttu-id="4ee0b-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="4ee0b-112">**Occurrence**</span></span>|<span data-ttu-id="4ee0b-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="4ee0b-113">Optional.</span></span> <span data-ttu-id="4ee0b-114">Se puede utilizar una vez por cada elemento `TuningOptions`.</span><span class="sxs-lookup"><span data-stu-id="4ee0b-114">Can use once for each `TuningOptions` element.</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="4ee0b-115">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="4ee0b-115">Element Relationships</span></span>  
  
|<span data-ttu-id="4ee0b-116">Relación</span><span class="sxs-lookup"><span data-stu-id="4ee0b-116">Relationship</span></span>|<span data-ttu-id="4ee0b-117">Elementos</span><span class="sxs-lookup"><span data-stu-id="4ee0b-117">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="4ee0b-118">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="4ee0b-118">**Parent element**</span></span>|[<span data-ttu-id="4ee0b-119">TuningOptions &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="4ee0b-119">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)|  
|<span data-ttu-id="4ee0b-120">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="4ee0b-120">**Child elements**</span></span>|<span data-ttu-id="4ee0b-121">None</span><span class="sxs-lookup"><span data-stu-id="4ee0b-121">None</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ee0b-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4ee0b-122">Remarks</span></span>  
 <span data-ttu-id="4ee0b-123">Utilice `DatabaseToConnect` para especificar el nombre de la primera base de datos a la que desea que se conecte el Asistente para la optimización de motor de base de datos cuando inicie la sesión de optimización.</span><span class="sxs-lookup"><span data-stu-id="4ee0b-123">Use `DatabaseToConnect` to specify the name of the first database to which you want Database Engine Tuning Advisor to connect when it starts the tuning session.</span></span> <span data-ttu-id="4ee0b-124">Con este elemento, solo es posible especificar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="4ee0b-124">You can specify only one database with this element.</span></span> <span data-ttu-id="4ee0b-125">Si se especifican varias bases de datos, el Asistente para la optimización de motor de base de datos devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="4ee0b-125">If multiple database names are specified, Database Engine Tuning Advisor returns an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ee0b-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4ee0b-126">Example</span></span>  
 <span data-ttu-id="4ee0b-127">Para obtener un ejemplo de uso, vea [Ejemplo de archivo de entrada XML con carga de trabajo insertada &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span><span class="sxs-lookup"><span data-stu-id="4ee0b-127">For a usage example, see the [XML Input File Sample with Inline Workload &#40;DTA&#41;](xml-input-file-sample-with-inline-workload-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ee0b-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ee0b-128">See Also</span></span>  
 [<span data-ttu-id="4ee0b-129">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="4ee0b-129">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
