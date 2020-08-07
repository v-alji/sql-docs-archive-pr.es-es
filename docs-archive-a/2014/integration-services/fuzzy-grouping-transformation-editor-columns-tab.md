---
title: Editor de transformación agrupación aproximada (pestaña columnas) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.columns.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 24f4539f-2a9f-4acd-acc7-06228a07f7df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9d3aef9c30a81760b7f09378a8ecd66fee0dac62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744772"
---
# <a name="fuzzy-grouping-transformation-editor-columns-tab"></a><span data-ttu-id="1fbd7-102">Editor de transformación Agrupación aproximada (pestaña Columnas)</span><span class="sxs-lookup"><span data-stu-id="1fbd7-102">Fuzzy Grouping Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="1fbd7-103">Use la pestaña **Columnas** del cuadro de diálogo **Editor de transformación Agrupación aproximada** para especificar las columnas utilizadas para agrupar filas con valores duplicados.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-103">Use the **Columns** tab of the **Fuzzy Grouping Transformation Editor** dialog box to specify the columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="1fbd7-104">Para obtener más información acerca de la transformación Agrupación aproximada, vea [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="1fbd7-104">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="1fbd7-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="1fbd7-105">Options</span></span>  
 <span data-ttu-id="1fbd7-106">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="1fbd7-107">Seleccione en esta lista las columnas de entrada utilizadas para agrupar filas con valores duplicados.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-107">Select from this list the input columns used to group rows with duplicate values.</span></span>  
  
 <span data-ttu-id="1fbd7-108">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-108">**Name**</span></span>  
 <span data-ttu-id="1fbd7-109">Muestra los nombres de las columnas de entrada disponibles.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-109">View the names of available input columns.</span></span>  
  
 <span data-ttu-id="1fbd7-110">**Paso a través**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-110">**Pass Through**</span></span>  
 <span data-ttu-id="1fbd7-111">Seleccione si la columna de entrada debe incluirse en la salida de transformación.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-111">Select whether to include the input column in the output of the transformation.</span></span> <span data-ttu-id="1fbd7-112">Todas las columnas utilizadas para la agrupación se copian automáticamente en la salida.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-112">All columns used for grouping are automatically copied to the output.</span></span> <span data-ttu-id="1fbd7-113">Si activa esta columna, puede incluir columnas adicionales.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-113">You can include additional columns by checking this column.</span></span>  
  
 <span data-ttu-id="1fbd7-114">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-114">**Input Column**</span></span>  
 <span data-ttu-id="1fbd7-115">Seleccione una de las columnas de entrada seleccionadas anteriormente en la lista **Columnas de entrada disponibles** .</span><span class="sxs-lookup"><span data-stu-id="1fbd7-115">Select one of the input columns selected earlier in the **Available Input Columns** list.</span></span>  
  
 <span data-ttu-id="1fbd7-116">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-116">**Output Alias**</span></span>  
 <span data-ttu-id="1fbd7-117">Escriba un nombre descriptivo para la columna de salida correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-117">Enter a descriptive name for the corresponding output column.</span></span> <span data-ttu-id="1fbd7-118">De forma predeterminada, el nombre de la columna de salida es el mismo que el nombre de la columna de entrada.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-118">By default, the output column name is the same as the input column name.</span></span>  
  
 <span data-ttu-id="1fbd7-119">**Alias de salida de grupo**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-119">**Group Output Alias**</span></span>  
 <span data-ttu-id="1fbd7-120">Escriba un nombre descriptivo para la columna que contendrá el valor canónico de los valores duplicados agrupados.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-120">Enter a descriptive name for the column that will contain the canonical value for the grouped duplicates.</span></span> <span data-ttu-id="1fbd7-121">El nombre predeterminado de esta columna de salida es el nombre de la columna de entrada con _clean anexado.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-121">The default name of this output column is the input column name with _clean appended.</span></span>  
  
 <span data-ttu-id="1fbd7-122">**Tipo de coincidencia**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-122">**Match Type**</span></span>  
 <span data-ttu-id="1fbd7-123">Seleccione coincidencia exacta o aproximada.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-123">Select fuzzy or exact matching.</span></span> <span data-ttu-id="1fbd7-124">Las filas se consideran duplicadas si existe un parecido suficiente entre todas las columnas con un tipo de coincidencia aproximada.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-124">Rows are considered duplicates if they are sufficiently similar across all columns with a fuzzy match type.</span></span> <span data-ttu-id="1fbd7-125">Si también especifica coincidencia exacta en determinadas columnas, solamente se consideran como posibles duplicados las filas que contienen valores idénticos en las columnas de coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-125">If you also specify exact matching on certain columns, only rows that contain identical values in the exact matching columns are considered as possible duplicates.</span></span> <span data-ttu-id="1fbd7-126">Por tanto, si sabe que una determinada columna no tiene errores o incoherencias, puede especificar coincidencia exacta en esa columna para aumentar la exactitud de la coincidencia aproximada en otras columnas.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-126">Therefore, if you know that a certain column contains no errors or inconsistencies, you can specify exact matching on that column to increase the accuracy of the fuzzy matching on other columns.</span></span>  
  
 <span data-ttu-id="1fbd7-127">**Similitud mínima**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-127">**Minimum Similarity**</span></span>  
 <span data-ttu-id="1fbd7-128">Establezca el umbral de similitud del nivel de combinación con el control deslizante.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-128">Set the similarity threshold at the join level by using the slider.</span></span> <span data-ttu-id="1fbd7-129">Cuanto más se acerque el valor a 1, más deberá parecerse el valor de búsqueda al valor de origen para que pueda calificarse como coincidencia.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-129">The closer the value is to 1, the closer the resemblance of the lookup value to the source value must be to qualify as a match.</span></span> <span data-ttu-id="1fbd7-130">Al aumentar el umbral se puede mejorar la velocidad de la coincidencia ya que se tendrán en cuanta menos registros candidatos.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-130">Increasing the threshold can improve the speed of matching since fewer candidate records need to be considered.</span></span>  
  
 <span data-ttu-id="1fbd7-131">**Alias de salida de similitud**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-131">**Similarity Output Alias**</span></span>  
 <span data-ttu-id="1fbd7-132">Especifique el nombre de una nueva columna de salida que contendrá los resultados de similitud de la combinación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-132">Specify the name for a new output column that contains the similarity scores for the selected join.</span></span> <span data-ttu-id="1fbd7-133">Si este valor se deja vacío, la columna de salida no se crea.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-133">If you leave this value empty, the output column is not created.</span></span>  
  
 <span data-ttu-id="1fbd7-134">**Números**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-134">**Numerals**</span></span>  
 <span data-ttu-id="1fbd7-135">Especifique la importancia de los números iniciales y finales en la comparación de los datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-135">Specify the significance of leading and trailing numerals in comparing the column data.</span></span> <span data-ttu-id="1fbd7-136">Por ejemplo, si los números iniciales son significativos, "123 Main Street" no se agrupará con "456 Main Street."</span><span class="sxs-lookup"><span data-stu-id="1fbd7-136">For example, if leading numerals are significant, "123 Main Street" will not be grouped with "456 Main Street."</span></span>  
  
|<span data-ttu-id="1fbd7-137">Value</span><span class="sxs-lookup"><span data-stu-id="1fbd7-137">Value</span></span>|<span data-ttu-id="1fbd7-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="1fbd7-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1fbd7-139">**Neither**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-139">**Neither**</span></span>|<span data-ttu-id="1fbd7-140">Los números iniciales y finales no son significativos.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-140">Leading and trailing numerals are not significant.</span></span>|  
|<span data-ttu-id="1fbd7-141">**Leading**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-141">**Leading**</span></span>|<span data-ttu-id="1fbd7-142">Solo son significativos los números iniciales.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-142">Only leading numerals are significant.</span></span>|  
|<span data-ttu-id="1fbd7-143">**Trailing**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-143">**Trailing**</span></span>|<span data-ttu-id="1fbd7-144">Solo son significativos los números finales.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-144">Only trailing numerals are significant.</span></span>|  
|<span data-ttu-id="1fbd7-145">**LeadingAndTrailing**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-145">**LeadingAndTrailing**</span></span>|<span data-ttu-id="1fbd7-146">Tanto los números iniciales como los finales son significativos.</span><span class="sxs-lookup"><span data-stu-id="1fbd7-146">Both leading and trailing numerals are significant.</span></span>|  
  
 <span data-ttu-id="1fbd7-147">**Marcas de comparación**</span><span class="sxs-lookup"><span data-stu-id="1fbd7-147">**Comparison Flags**</span></span>  
 <span data-ttu-id="1fbd7-148">Para más información sobre las opciones de comparación de cadenas, vea [Comparar datos de cadena](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="1fbd7-148">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fbd7-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1fbd7-149">See Also</span></span>  
 <span data-ttu-id="1fbd7-150">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="1fbd7-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="1fbd7-151">Identificar filas de datos similares mediante la transformación Agrupación aproximada</span><span class="sxs-lookup"><span data-stu-id="1fbd7-151">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
