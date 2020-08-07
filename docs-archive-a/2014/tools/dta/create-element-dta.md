---
title: Create (DTA, elemento) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Create element (DTA)
ms.assetid: 9d076c90-f933-45f4-b6d9-447793f6528b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 407f16c3898e56cd393e36c39ed799b83e0092ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743787"
---
# <a name="create-element-dta"></a><span data-ttu-id="74eb3-102">Create (DTA, elemento)</span><span class="sxs-lookup"><span data-stu-id="74eb3-102">Create Element (DTA)</span></span>
  <span data-ttu-id="74eb3-103">Contiene información sobre los índices, las estadísticas o las estructuras de montones de una configuración especificada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="74eb3-103">Contains information about the indexes, statistics, or heap structures in a user-specified configuration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74eb3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74eb3-104">Syntax</span></span>  
  
```  
  
<Recommendation>  
    <Create>  
    ...code removed here...  
    </Create>  
</Recommendation>  
```  
  
## <a name="element-characteristics"></a><span data-ttu-id="74eb3-105">Características de los elementos</span><span class="sxs-lookup"><span data-stu-id="74eb3-105">Element Characteristics</span></span>  
  
|<span data-ttu-id="74eb3-106">Característica</span><span class="sxs-lookup"><span data-stu-id="74eb3-106">Characteristic</span></span>|<span data-ttu-id="74eb3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="74eb3-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="74eb3-108">**Tipo y longitud de los datos**</span><span class="sxs-lookup"><span data-stu-id="74eb3-108">**Data type and length**</span></span>|<span data-ttu-id="74eb3-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="74eb3-109">None.</span></span>|  
|<span data-ttu-id="74eb3-110">**Valor predeterminado**</span><span class="sxs-lookup"><span data-stu-id="74eb3-110">**Default value**</span></span>|<span data-ttu-id="74eb3-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="74eb3-111">None.</span></span>|  
|<span data-ttu-id="74eb3-112">**Repetición**</span><span class="sxs-lookup"><span data-stu-id="74eb3-112">**Occurrence**</span></span>|<span data-ttu-id="74eb3-113">Una obligatoria por cada tipo de estructura de diseño físico (índices, estadísticas o estructuras de montones).</span><span class="sxs-lookup"><span data-stu-id="74eb3-113">Required once for each physical design structure type (indexes, statistics, or heap structures).</span></span>|  
  
## <a name="element-relationships"></a><span data-ttu-id="74eb3-114">Relaciones del elemento</span><span class="sxs-lookup"><span data-stu-id="74eb3-114">Element Relationships</span></span>  
  
|<span data-ttu-id="74eb3-115">Relación</span><span class="sxs-lookup"><span data-stu-id="74eb3-115">Relationship</span></span>|<span data-ttu-id="74eb3-116">Elementos</span><span class="sxs-lookup"><span data-stu-id="74eb3-116">Elements</span></span>|  
|------------------|--------------|  
|<span data-ttu-id="74eb3-117">**Elemento primario**</span><span class="sxs-lookup"><span data-stu-id="74eb3-117">**Parent element**</span></span>|[<span data-ttu-id="74eb3-118">Elemento Recommendation &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="74eb3-118">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)|  
|<span data-ttu-id="74eb3-119">**Elementos secundarios**</span><span class="sxs-lookup"><span data-stu-id="74eb3-119">**Child elements**</span></span>|[<span data-ttu-id="74eb3-120">Index &#40;DTA, elemento&#41;</span><span class="sxs-lookup"><span data-stu-id="74eb3-120">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)<br /><br /> <span data-ttu-id="74eb3-121">`Statistics`Elemento (vea [Asistente para la optimización de motor de base de datos esquema XML](https://schemas.microsoft.com/sqlserver/) para obtener información)</span><span class="sxs-lookup"><span data-stu-id="74eb3-121">`Statistics` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span><br /><br /> <span data-ttu-id="74eb3-122">`Heap`Elemento (vea [Asistente para la optimización de motor de base de datos esquema XML](https://schemas.microsoft.com/sqlserver/) para obtener información)</span><span class="sxs-lookup"><span data-stu-id="74eb3-122">`Heap` Element (see [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74eb3-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="74eb3-123">Remarks</span></span>  
 <span data-ttu-id="74eb3-124">Este elemento tiene el nombre **CreateTypecomplexType** en el esquema XML del Asistente para la optimización de motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="74eb3-124">This element is of the **CreateTypecomplexType** name in the Database Engine Tuning Advisor XML schema.</span></span> <span data-ttu-id="74eb3-125">Se utiliza para crear los índices, las estadísticas y las estructuras de montones de una configuración especificada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="74eb3-125">It is used to create indexes, statistics, and heap structures for a user-specified configuration.</span></span> <span data-ttu-id="74eb3-126">No confunda este elemento `Create` con los otros tipos que se pueden utilizar para crear vistas (`CreateViewType`) o particiones (`CreatePType`).</span><span class="sxs-lookup"><span data-stu-id="74eb3-126">Do not confuse this `Create` element with the other types that can be used to create views (`CreateViewType`) or partitioning (`CreatePType`).</span></span> <span data-ttu-id="74eb3-127">Consulte el [esquema XML de Asistente para la optimización de motor de base de datos](https://schemas.microsoft.com/sqlserver/) para obtener información sobre estos otros `Create` tipos de elemento.</span><span class="sxs-lookup"><span data-stu-id="74eb3-127">Refer to the [Database Engine Tuning Advisor XML schema](https://schemas.microsoft.com/sqlserver/) for information about these other `Create` element types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74eb3-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74eb3-128">Example</span></span>  
 <span data-ttu-id="74eb3-129">Para obtener un ejemplo de uso de este elemento, vea [Ejemplo de archivo de entrada XML con configuración especificada por el usuario &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span><span class="sxs-lookup"><span data-stu-id="74eb3-129">For a usage example of this element, see the [XML Input File Sample with User-specified Configuration &#40;DTA&#41;](xml-input-file-sample-with-user-specified-configuration-dta.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74eb3-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74eb3-130">See Also</span></span>  
 [<span data-ttu-id="74eb3-131">Referencia del archivo de entrada XML &#40;Asistente para la optimización de motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="74eb3-131">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
