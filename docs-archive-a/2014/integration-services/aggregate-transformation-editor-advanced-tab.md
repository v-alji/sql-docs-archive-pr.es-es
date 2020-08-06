---
title: Editor de transformación agregado (pestaña avanzadas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.aggregationtransformation.advanced.f1
helpviewer_keywords:
- Aggregate Transformation Editor
ms.assetid: 186a9736-2554-40a0-9cb2-877a8db5fde8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb3742a83f363f74004a5aac0eefc589ee2a5be2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670525"
---
# <a name="aggregate-transformation-editor-advanced-tab"></a><span data-ttu-id="a2d2c-102">Editor de transformación Agregado (pestaña Avanzadas)</span><span class="sxs-lookup"><span data-stu-id="a2d2c-102">Aggregate Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="a2d2c-103">Utilice la pestaña **Avanzadas** del cuadro de diálogo **Editor de transformación Agregado** para establecer las propiedades del componente, especificar agregaciones y establecer las propiedades de las columnas de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-103">Use the **Advanced** tab of the **Aggregate Transformation Editor** dialog box to set component properties, specify aggregations, and set properties of input and output columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2d2c-104">Las opciones para el recuento de claves, la escala de claves, la clave Count Distinct y la escala de claves distintas estarán disponibles en el componente si se especifican en la pestaña **Avanzadas** , en la salida si se especifican en la pantalla avanzada de la pestaña **Agregaciones** y en la columna si se especifican en la lista de columnas en la parte inferior de la pestaña **Agregaciones** .</span><span class="sxs-lookup"><span data-stu-id="a2d2c-104">The options for key count, key scale, distinct key count, and distinct key scale apply at the component level when specified on the **Advanced** tab, at the output level when specified in the advanced display of the **Aggregations** tab, and at the column level when specified in the column list at the bottom of the **Aggregations** tab.</span></span>  
>   
>  <span data-ttu-id="a2d2c-105">En la transformación Agregado, **Claves** y **Escala de claves** hacen referencia al número de grupos que se esperan como resultado de una operación **Agrupar por** .</span><span class="sxs-lookup"><span data-stu-id="a2d2c-105">In the Aggregate transformation, **Keys** and **Keys scale** refer to the number of groups that are expected to result from a **Group by** operation.</span></span> <span data-ttu-id="a2d2c-106">**Claves Count Distinct** y **Escala Count Distinct** hacen referencia al número de valores distintos que se esperan como resultado de una operación **Recuento distinto** .</span><span class="sxs-lookup"><span data-stu-id="a2d2c-106">**Count distinct keys** and **Count distinct scale** refer to the number of distinct values that are expected to result from a **Distinct count** operation.</span></span>  
  
 <span data-ttu-id="a2d2c-107">Para obtener más información acerca de la transformación Agregado, vea [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a2d2c-107">To learn more about the Aggregate transformation, see [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a2d2c-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="a2d2c-108">Options</span></span>  
 <span data-ttu-id="a2d2c-109">**Escala de claves**</span><span class="sxs-lookup"><span data-stu-id="a2d2c-109">**Keys scale**</span></span>  
 <span data-ttu-id="a2d2c-110">Si lo desea, especifique el número aproximado de claves que espera la agregación.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-110">Optionally specify the approximate number of keys that the aggregation expects.</span></span> <span data-ttu-id="a2d2c-111">La transformación utiliza esta información para optimizar el tamaño de caché inicial.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-111">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="a2d2c-112">De forma predeterminada, el valor de esta opción es **No especificado**.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-112">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="a2d2c-113">Si se especifica tanto **Escala de claves** como **Número de claves** , prevalece la opción **Número de claves** .</span><span class="sxs-lookup"><span data-stu-id="a2d2c-113">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
|<span data-ttu-id="a2d2c-114">Value</span><span class="sxs-lookup"><span data-stu-id="a2d2c-114">Value</span></span>|<span data-ttu-id="a2d2c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2d2c-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a2d2c-116">Sin especificar</span><span class="sxs-lookup"><span data-stu-id="a2d2c-116">Unspecified</span></span>|<span data-ttu-id="a2d2c-117">No se utiliza la propiedad **Escala de claves** .</span><span class="sxs-lookup"><span data-stu-id="a2d2c-117">The **Keys scale** property is not used.</span></span>|  
|<span data-ttu-id="a2d2c-118">Bajo</span><span class="sxs-lookup"><span data-stu-id="a2d2c-118">Low</span></span>|<span data-ttu-id="a2d2c-119">La agregación podrá escribir aproximadamente 500 000 claves.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-119">Aggregation can write approximately 500,000 keys.</span></span>|  
|<span data-ttu-id="a2d2c-120">Media</span><span class="sxs-lookup"><span data-stu-id="a2d2c-120">Medium</span></span>|<span data-ttu-id="a2d2c-121">La agregación podrá escribir aproximadamente 5.000.000 claves.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-121">Aggregation can write approximately 5,000,000 keys.</span></span>|  
|<span data-ttu-id="a2d2c-122">Alto</span><span class="sxs-lookup"><span data-stu-id="a2d2c-122">High</span></span>|<span data-ttu-id="a2d2c-123">La agregación podrá escribir más de 25.000.000 claves.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-123">Aggregation can write more than 25,000,000 keys.</span></span>|  
  
 <span data-ttu-id="a2d2c-124">**Número de claves**</span><span class="sxs-lookup"><span data-stu-id="a2d2c-124">**Number of keys**</span></span>  
 <span data-ttu-id="a2d2c-125">Si lo desea, especifique el número exacto de claves que espera la agregación.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-125">Optionally specify the exact number of keys that the aggregation expects.</span></span> <span data-ttu-id="a2d2c-126">La transformación utiliza esta información para optimizar el tamaño de caché inicial.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-126">The transformation uses this information to optimize its initial cache size.</span></span> <span data-ttu-id="a2d2c-127">Si se especifica tanto **Escala de claves** como **Número de claves** , prevalece la opción **Número de claves** .</span><span class="sxs-lookup"><span data-stu-id="a2d2c-127">If both **Keys scale** and **Number of keys** are specified, **Number of keys** takes precedence.</span></span>  
  
 <span data-ttu-id="a2d2c-128">**Escala Count Distinct**</span><span class="sxs-lookup"><span data-stu-id="a2d2c-128">**Count distinct scale**</span></span>  
 <span data-ttu-id="a2d2c-129">Opcionalmente, puede especificar el número aproximado de valores DISTINCT que podrá escribir la agregación.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-129">Optionally specify the approximate number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="a2d2c-130">De forma predeterminada, el valor de esta opción es **No especificado**.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-130">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="a2d2c-131">Si se especifica tanto **Escala Count Distinct** como **Claves Count Distinct** , prevalece la opción **Claves Count Distinct** .</span><span class="sxs-lookup"><span data-stu-id="a2d2c-131">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
|<span data-ttu-id="a2d2c-132">Value</span><span class="sxs-lookup"><span data-stu-id="a2d2c-132">Value</span></span>|<span data-ttu-id="a2d2c-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2d2c-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a2d2c-134">Sin especificar</span><span class="sxs-lookup"><span data-stu-id="a2d2c-134">Unspecified</span></span>|<span data-ttu-id="a2d2c-135">No se utiliza la propiedad CountDistinctScale.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-135">The CountDistinctScale property is not used.</span></span>|  
|<span data-ttu-id="a2d2c-136">Bajo</span><span class="sxs-lookup"><span data-stu-id="a2d2c-136">Low</span></span>|<span data-ttu-id="a2d2c-137">La agregación podrá escribir aproximadamente 500.000 valores DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-137">Aggregation can write approximately 500,000 distinct values.</span></span>|  
|<span data-ttu-id="a2d2c-138">Media</span><span class="sxs-lookup"><span data-stu-id="a2d2c-138">Medium</span></span>|<span data-ttu-id="a2d2c-139">La agregación podrá escribir aproximadamente 5 000 000 valores DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-139">Aggregation can write approximately 5,000,000 distinct values.</span></span>|  
|<span data-ttu-id="a2d2c-140">Alto</span><span class="sxs-lookup"><span data-stu-id="a2d2c-140">High</span></span>|<span data-ttu-id="a2d2c-141">La agregación podrá escribir más de 25.000.000 valores DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-141">Aggregation can write more than 25,000,000 distinct values.</span></span>|  
  
 <span data-ttu-id="a2d2c-142">**Claves Count Distinct**</span><span class="sxs-lookup"><span data-stu-id="a2d2c-142">**Count distinct keys**</span></span>  
 <span data-ttu-id="a2d2c-143">Opcionalmente, puede especificar el número exacto de valores DISTINCT que podrá escribir la agregación.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-143">Optionally specify the exact number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="a2d2c-144">Si se especifica tanto **Escala Count Distinct** como **Claves Count Distinct** , prevalece la opción **Claves Count Distinct** .</span><span class="sxs-lookup"><span data-stu-id="a2d2c-144">If both **Count distinct scale** and **Count distinct keys** are specified, **Count distinct keys** takes precedence.</span></span>  
  
 <span data-ttu-id="a2d2c-145">**Factor de ampliación automática**</span><span class="sxs-lookup"><span data-stu-id="a2d2c-145">**Auto extend factor**</span></span>  
 <span data-ttu-id="a2d2c-146">Utilice un valor comprendido entre 1 y 100 para especificar el porcentaje en el que se puede ampliar la memoria durante la agregación.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-146">Use a value between 1 and 100 to specify the percentage by which memory can be extended during the aggregation.</span></span> <span data-ttu-id="a2d2c-147">De forma predeterminada, el valor de esta opción es **25%**.</span><span class="sxs-lookup"><span data-stu-id="a2d2c-147">By default, the value of this option is **25%**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d2c-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a2d2c-148">See Also</span></span>  
 <span data-ttu-id="a2d2c-149">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a2d2c-149">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a2d2c-150">[Editor de transformación agregado &#40;pestaña agregaciones&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span><span class="sxs-lookup"><span data-stu-id="a2d2c-150">[Aggregate Transformation Editor &#40;Aggregations Tab&#41;](../../2014/integration-services/aggregate-transformation-editor-aggregations-tab.md) </span></span>  
 [<span data-ttu-id="a2d2c-151">Agregar valores en un conjunto de datos mediante la transformación Agregado</span><span class="sxs-lookup"><span data-stu-id="a2d2c-151">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>](data-flow/transformations/aggregate-values-in-a-dataset-by-using-the-aggregate-transformation.md)  
  
  
