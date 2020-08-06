---
title: Editor de transformación agregado (pestaña agregaciones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.aggregationtransformation.aggregations.f1
helpviewer_keywords:
- Aggregate Transformation Editor
ms.assetid: a01cb124-ec79-4673-b1a1-bf4d60ee1b45
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 30cafb68a69a061fe4b79e832f356b82926c9761
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670522"
---
# <a name="aggregate-transformation-editor-aggregations-tab"></a><span data-ttu-id="047a2-102">Editor de transformación Agregado (pestaña Agregaciones)</span><span class="sxs-lookup"><span data-stu-id="047a2-102">Aggregate Transformation Editor (Aggregations Tab)</span></span>
  <span data-ttu-id="047a2-103">Use la pestaña **Agregaciones** del cuadro de diálogo **Editor de transformación Agregado** para especificar las columnas que desea agregar y las propiedades de agregación.</span><span class="sxs-lookup"><span data-stu-id="047a2-103">Use the **Aggregations** tab of the **Aggregate Transformation Editor** dialog box to specify columns for aggregation and aggregation properties.</span></span> <span data-ttu-id="047a2-104">Puede aplicar diversas agregaciones.</span><span class="sxs-lookup"><span data-stu-id="047a2-104">You can apply multiple aggregations.</span></span> <span data-ttu-id="047a2-105">Esta transformación no genera una salida de errores.</span><span class="sxs-lookup"><span data-stu-id="047a2-105">This transformation does not generate an error output.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="047a2-106">Las opciones para el recuento de claves, la escala de claves, la clave Count Distinct y la escala de claves distintas estarán disponibles en el componente si se especifican en la pestaña **Avanzadas** , en la salida si se especifican en la pantalla avanzada de la pestaña **Agregaciones** y en la columna si se especifican en la lista de columnas en la parte inferior de la pestaña **Agregaciones** .</span><span class="sxs-lookup"><span data-stu-id="047a2-106">The options for key count, key scale, distinct key count, and distinct key scale apply at the component level when specified on the **Advanced** tab, at the output level when specified in the advanced display of the **Aggregations** tab, and at the column level when specified in the column list at the bottom of the **Aggregations** tab.</span></span>  
>   
>  <span data-ttu-id="047a2-107">En la transformación Agregado, **Claves** y **Escala de claves** hacen referencia al número de grupos que se esperan como resultado de una operación **Agrupar por** .</span><span class="sxs-lookup"><span data-stu-id="047a2-107">In the Aggregate transformation, **Keys** and **Keys scale** refer to the number of groups that are expected to result from a **Group by** operation.</span></span> <span data-ttu-id="047a2-108">**Claves Count Distinct** y **Escala Count Distinct** hacen referencia al número de valores distintos que se esperan como resultado de una operación **Recuento distinto** .</span><span class="sxs-lookup"><span data-stu-id="047a2-108">**Count distinct keys** and **Count distinct scale** refer to the number of distinct values that are expected to result from a **Distinct count** operation.</span></span>  
  
 <span data-ttu-id="047a2-109">Para obtener más información acerca de la transformación Agregado, vea [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="047a2-109">To learn more about the Aggregate transformation, see [Aggregate Transformation](data-flow/transformations/aggregate-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="047a2-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="047a2-110">Options</span></span>  
 <span data-ttu-id="047a2-111">**Avanzadas/Básicas**</span><span class="sxs-lookup"><span data-stu-id="047a2-111">**Advanced / Basic**</span></span>  
 <span data-ttu-id="047a2-112">Muestra u oculta opciones para configurar diversas agregaciones para varias salidas.</span><span class="sxs-lookup"><span data-stu-id="047a2-112">Display or hide options to configure multiple aggregations for multiple outputs.</span></span> <span data-ttu-id="047a2-113">De forma predeterminada, las opciones Avanzadas aparecen ocultas.</span><span class="sxs-lookup"><span data-stu-id="047a2-113">By default, the Advanced options are hidden.</span></span>  
  
 <span data-ttu-id="047a2-114">**Nombre de agregación**</span><span class="sxs-lookup"><span data-stu-id="047a2-114">**Aggregation Name**</span></span>  
 <span data-ttu-id="047a2-115">En la pantalla Avanzadas, escriba un nombre descriptivo para la agregación.</span><span class="sxs-lookup"><span data-stu-id="047a2-115">In the Advanced display, type a friendly name for the aggregation.</span></span>  
  
 <span data-ttu-id="047a2-116">**Agrupar por columnas**</span><span class="sxs-lookup"><span data-stu-id="047a2-116">**Group By Columns**</span></span>  
 <span data-ttu-id="047a2-117">En la pantalla Avanzadas, seleccione las columnas que quiere agrupar en la lista **Columnas de entrada disponibles** como se explica a continuación.</span><span class="sxs-lookup"><span data-stu-id="047a2-117">In the Advanced display, select columns for grouping by using the **Available Input Columns** list as described below.</span></span>  
  
 <span data-ttu-id="047a2-118">**Escala de claves**</span><span class="sxs-lookup"><span data-stu-id="047a2-118">**Key Scale**</span></span>  
 <span data-ttu-id="047a2-119">En la pantalla Avanzadas, especifique opcionalmente el número aproximado de claves que podrá escribir la agregación.</span><span class="sxs-lookup"><span data-stu-id="047a2-119">In the Advanced display, optionally specify the approximate number of keys that the aggregation can write.</span></span> <span data-ttu-id="047a2-120">De forma predeterminada, el valor de esta opción es **No especificado**.</span><span class="sxs-lookup"><span data-stu-id="047a2-120">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="047a2-121">Si se seleccionan las propiedades **Escala de claves** y **Claves** , tendrá prioridad el valor de **Claves** .</span><span class="sxs-lookup"><span data-stu-id="047a2-121">If both the **Key Scale** and **Keys** properties are set, the value of **Keys** takes precedence.</span></span>  
  
|<span data-ttu-id="047a2-122">Value</span><span class="sxs-lookup"><span data-stu-id="047a2-122">Value</span></span>|<span data-ttu-id="047a2-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="047a2-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="047a2-124">Sin especificar</span><span class="sxs-lookup"><span data-stu-id="047a2-124">Unspecified</span></span>|<span data-ttu-id="047a2-125">No se utiliza la propiedad Escala de claves.</span><span class="sxs-lookup"><span data-stu-id="047a2-125">The Key Scale property is not used.</span></span>|  
|<span data-ttu-id="047a2-126">Bajo</span><span class="sxs-lookup"><span data-stu-id="047a2-126">Low</span></span>|<span data-ttu-id="047a2-127">La agregación podrá escribir aproximadamente 500 000 claves.</span><span class="sxs-lookup"><span data-stu-id="047a2-127">Aggregation can write approximately 500,000 keys.</span></span>|  
|<span data-ttu-id="047a2-128">Media</span><span class="sxs-lookup"><span data-stu-id="047a2-128">Medium</span></span>|<span data-ttu-id="047a2-129">La agregación podrá escribir aproximadamente 5.000.000 claves.</span><span class="sxs-lookup"><span data-stu-id="047a2-129">Aggregation can write approximately 5,000,000 keys.</span></span>|  
|<span data-ttu-id="047a2-130">Alto</span><span class="sxs-lookup"><span data-stu-id="047a2-130">High</span></span>|<span data-ttu-id="047a2-131">La agregación podrá escribir más de 25.000.000 claves.</span><span class="sxs-lookup"><span data-stu-id="047a2-131">Aggregation can write more than 25,000,000 keys.</span></span>|  
  
 <span data-ttu-id="047a2-132">**Claves**</span><span class="sxs-lookup"><span data-stu-id="047a2-132">**Keys**</span></span>  
 <span data-ttu-id="047a2-133">En la pantalla Avanzadas, especifique opcionalmente el número exacto de claves que podrá escribir la agregación.</span><span class="sxs-lookup"><span data-stu-id="047a2-133">In the Advanced display, optionally specify the exact number of keys that the aggregation can write.</span></span> <span data-ttu-id="047a2-134">Si se especifican **Escala de claves** y **Claves** , tendrá prioridad **Claves** .</span><span class="sxs-lookup"><span data-stu-id="047a2-134">If both **Key Scale** and **Keys** are specified, **Keys** takes precedence.</span></span>  
  
 <span data-ttu-id="047a2-135">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="047a2-135">**Available Input Columns**</span></span>  
 <span data-ttu-id="047a2-136">Seleccione una columna en la lista de columnas de entrada disponibles con las casillas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="047a2-136">Select from the list of available input columns by using the check boxes in this table.</span></span>  
  
 <span data-ttu-id="047a2-137">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="047a2-137">**Input Column**</span></span>  
 <span data-ttu-id="047a2-138">Seleccione las columnas de entrada disponibles de la lista.</span><span class="sxs-lookup"><span data-stu-id="047a2-138">Select from the list of available input columns.</span></span>  
  
 <span data-ttu-id="047a2-139">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="047a2-139">**Output Alias**</span></span>  
 <span data-ttu-id="047a2-140">Escriba un alias para cada columna.</span><span class="sxs-lookup"><span data-stu-id="047a2-140">Type an alias for each column.</span></span> <span data-ttu-id="047a2-141">El nombre predeterminado es el de la columna de entrada, pero puede elegir cualquier nombre descriptivo único.</span><span class="sxs-lookup"><span data-stu-id="047a2-141">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="047a2-142">**operación**</span><span class="sxs-lookup"><span data-stu-id="047a2-142">**Operation**</span></span>  
 <span data-ttu-id="047a2-143">Elija una operación de la lista de operaciones disponibles con la siguiente tabla como guía.</span><span class="sxs-lookup"><span data-stu-id="047a2-143">Choose from the list of available operations, using the following table as a guide.</span></span>  
  
|<span data-ttu-id="047a2-144">Operación</span><span class="sxs-lookup"><span data-stu-id="047a2-144">Operation</span></span>|<span data-ttu-id="047a2-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="047a2-145">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="047a2-146">**GroupBy**</span><span class="sxs-lookup"><span data-stu-id="047a2-146">**GroupBy**</span></span>|<span data-ttu-id="047a2-147">Divide los conjuntos de datos en grupos.</span><span class="sxs-lookup"><span data-stu-id="047a2-147">Divides datasets into groups.</span></span> <span data-ttu-id="047a2-148">Podrán agruparse columnas con cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="047a2-148">Columns with any data type can be used for grouping.</span></span> <span data-ttu-id="047a2-149">Para obtener más información, vea GROUP BY.</span><span class="sxs-lookup"><span data-stu-id="047a2-149">For more information, see GROUP BY.</span></span>|  
|<span data-ttu-id="047a2-150">**Sum**</span><span class="sxs-lookup"><span data-stu-id="047a2-150">**Sum**</span></span>|<span data-ttu-id="047a2-151">Suma los valores de una columna.</span><span class="sxs-lookup"><span data-stu-id="047a2-151">Sums the values in a column.</span></span> <span data-ttu-id="047a2-152">Solo podrán sumarse las columnas con tipos de datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="047a2-152">Only columns with numeric data types can be summed.</span></span> <span data-ttu-id="047a2-153">Para obtener más información, vea SUM.</span><span class="sxs-lookup"><span data-stu-id="047a2-153">For more information, see SUM.</span></span>|  
|<span data-ttu-id="047a2-154">**Average**</span><span class="sxs-lookup"><span data-stu-id="047a2-154">**Average**</span></span>|<span data-ttu-id="047a2-155">Devuelve la media de los valores de columna de una columna.</span><span class="sxs-lookup"><span data-stu-id="047a2-155">Returns the average of the column values in a column.</span></span> <span data-ttu-id="047a2-156">Solo podrá calcularse la media de las columnas con tipos de datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="047a2-156">Only columns with numeric data types can be averaged.</span></span> <span data-ttu-id="047a2-157">Para obtener más información, vea AVG.</span><span class="sxs-lookup"><span data-stu-id="047a2-157">For more information, see AVG.</span></span>|  
|<span data-ttu-id="047a2-158">**Recuento**</span><span class="sxs-lookup"><span data-stu-id="047a2-158">**Count**</span></span>|<span data-ttu-id="047a2-159">Devuelve el número de elementos de un grupo.</span><span class="sxs-lookup"><span data-stu-id="047a2-159">Returns the number of items in a group.</span></span> <span data-ttu-id="047a2-160">Para obtener más información, vea COUNT.</span><span class="sxs-lookup"><span data-stu-id="047a2-160">For more information, see COUNT.</span></span>|  
|<span data-ttu-id="047a2-161">**CountDistinct**</span><span class="sxs-lookup"><span data-stu-id="047a2-161">**CountDistinct**</span></span>|<span data-ttu-id="047a2-162">Devuelve el número de valores únicos distintos de NULL de un grupo.</span><span class="sxs-lookup"><span data-stu-id="047a2-162">Returns the number of unique nonnull values in a group.</span></span> <span data-ttu-id="047a2-163">Para obtener más información, vea COUNT y Distinct.</span><span class="sxs-lookup"><span data-stu-id="047a2-163">For more information, see COUNT and Distinct.</span></span>|  
|<span data-ttu-id="047a2-164">**Mínimo**</span><span class="sxs-lookup"><span data-stu-id="047a2-164">**Minimum**</span></span>|<span data-ttu-id="047a2-165">Devuelve el valor mínimo en un grupo.</span><span class="sxs-lookup"><span data-stu-id="047a2-165">Returns the minimum value in a group.</span></span> <span data-ttu-id="047a2-166">Está restringido a los tipos de datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="047a2-166">Restricted to numeric data types.</span></span>|  
|<span data-ttu-id="047a2-167">**Máximo**</span><span class="sxs-lookup"><span data-stu-id="047a2-167">**Maximum**</span></span>|<span data-ttu-id="047a2-168">Devuelve el valor máximo en un grupo.</span><span class="sxs-lookup"><span data-stu-id="047a2-168">Returns the maximum value in a group.</span></span> <span data-ttu-id="047a2-169">Está restringido a los tipos de datos numéricos.</span><span class="sxs-lookup"><span data-stu-id="047a2-169">Restricted to numeric data types.</span></span>|  
  
 <span data-ttu-id="047a2-170">**Marcas de comparación**</span><span class="sxs-lookup"><span data-stu-id="047a2-170">**Comparison Flags**</span></span>  
 <span data-ttu-id="047a2-171">Si selecciona **Agrupar por**, use las casillas para controlar cómo realiza la transformación la comparación.</span><span class="sxs-lookup"><span data-stu-id="047a2-171">If you choose **Group By**, use the check boxes to control how the transformation performs the comparison.</span></span> <span data-ttu-id="047a2-172">Para obtener más información acerca de las opciones de comparación de cadenas, vea [Comparing String Data](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="047a2-172">For information on the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="047a2-173">**Escala Count DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="047a2-173">**Count Distinct Scale**</span></span>  
 <span data-ttu-id="047a2-174">Opcionalmente, puede especificar el número aproximado de valores DISTINCT que podrá escribir la agregación.</span><span class="sxs-lookup"><span data-stu-id="047a2-174">Optionally specify the approximate number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="047a2-175">De forma predeterminada, el valor de esta opción es **No especificado**.</span><span class="sxs-lookup"><span data-stu-id="047a2-175">By default, the value of this option is **Unspecified**.</span></span> <span data-ttu-id="047a2-176">Si `CountDistinctScale` se especifican y **CountDistinctKeys** , **CountDistinctKeys** tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="047a2-176">If both `CountDistinctScale` and **CountDistinctKeys** are specified, **CountDistinctKeys** takes precedence.</span></span>  
  
|<span data-ttu-id="047a2-177">Value</span><span class="sxs-lookup"><span data-stu-id="047a2-177">Value</span></span>|<span data-ttu-id="047a2-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="047a2-178">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="047a2-179">Sin especificar</span><span class="sxs-lookup"><span data-stu-id="047a2-179">Unspecified</span></span>|<span data-ttu-id="047a2-180">No se utiliza la propiedad `CountDistinctScale`.</span><span class="sxs-lookup"><span data-stu-id="047a2-180">The `CountDistinctScale` property is not used.</span></span>|  
|<span data-ttu-id="047a2-181">Bajo</span><span class="sxs-lookup"><span data-stu-id="047a2-181">Low</span></span>|<span data-ttu-id="047a2-182">La agregación podrá escribir aproximadamente 500.000 valores DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="047a2-182">Aggregation can write approximately 500,000 distinct values.</span></span>|  
|<span data-ttu-id="047a2-183">Media</span><span class="sxs-lookup"><span data-stu-id="047a2-183">Medium</span></span>|<span data-ttu-id="047a2-184">La agregación podrá escribir aproximadamente 5 000 000 valores DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="047a2-184">Aggregation can write approximately 5,000,000 distinct values.</span></span>|  
|<span data-ttu-id="047a2-185">Alto</span><span class="sxs-lookup"><span data-stu-id="047a2-185">High</span></span>|<span data-ttu-id="047a2-186">La agregación podrá escribir más de 25.000.000 valores DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="047a2-186">Aggregation can write more than 25,000,000 distinct values.</span></span>|  
  
 <span data-ttu-id="047a2-187">**Claves Count DISTINCT**</span><span class="sxs-lookup"><span data-stu-id="047a2-187">**Count Distinct Keys**</span></span>  
 <span data-ttu-id="047a2-188">Opcionalmente, puede especificar el número exacto de valores DISTINCT que podrá escribir la agregación.</span><span class="sxs-lookup"><span data-stu-id="047a2-188">Optionally specify the exact number of distinct values that the aggregation can write.</span></span> <span data-ttu-id="047a2-189">Si `CountDistinctScale` se especifican y **CountDistinctKeys** , **CountDistinctKeys** tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="047a2-189">If both `CountDistinctScale` and **CountDistinctKeys** are specified, **CountDistinctKeys** takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047a2-190">Consulte también</span><span class="sxs-lookup"><span data-stu-id="047a2-190">See Also</span></span>  
 <span data-ttu-id="047a2-191">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="047a2-191">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="047a2-192">[Editor de transformación agregado &#40;pestaña avanzadas&#41;](../../2014/integration-services/aggregate-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="047a2-192">[Aggregate Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/aggregate-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="047a2-193">Agregar valores en un conjunto de datos mediante la transformación Agregado</span><span class="sxs-lookup"><span data-stu-id="047a2-193">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>](data-flow/transformations/aggregate-values-in-a-dataset-by-using-the-aggregate-transformation.md)  
  
  