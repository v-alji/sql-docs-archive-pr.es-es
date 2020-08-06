---
title: Explorar y limpiar datos | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7c888c95-8986-461e-9f11-2395044b9d97
author: minewiskan
ms.author: owend
ms.openlocfilehash: 154c711f735bcbb472e49654139fd16a036a0dd5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662329"
---
# <a name="exploring-and-cleaning-data"></a><span data-ttu-id="7d13a-102">Explorar y limpiar datos</span><span class="sxs-lookup"><span data-stu-id="7d13a-102">Exploring and Cleaning Data</span></span>
  <span data-ttu-id="7d13a-103">La preparación de los datos es mucho más que limpiarlos.</span><span class="sxs-lookup"><span data-stu-id="7d13a-103">Data preparation is much more than data cleansing.</span></span> <span data-ttu-id="7d13a-104">Recuerde que el modo en que los datos se preparan también afecta al modo en que los resultados se interpretan en el extremo.</span><span class="sxs-lookup"><span data-stu-id="7d13a-104">Remember that how data is prepared also affects how results are interpreted in the end.</span></span> <span data-ttu-id="7d13a-105">La preparación de los datos implica estas tareas:</span><span class="sxs-lookup"><span data-stu-id="7d13a-105">Data preparation involves these tasks:</span></span>  
  
-   <span data-ttu-id="7d13a-106">Explorar y comprobar la distribución de los datos.</span><span class="sxs-lookup"><span data-stu-id="7d13a-106">Exploring and checking the distribution of data.</span></span>  
  
-   <span data-ttu-id="7d13a-107">Limpiar los registros no válidos y elegir las columnas para la minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7d13a-107">Cleaning bad records, and choosing columns for data mining.</span></span>  
  
-   <span data-ttu-id="7d13a-108">Controlar los valores NULL correctamente.</span><span class="sxs-lookup"><span data-stu-id="7d13a-108">Handling nulls appropriately.</span></span>  
  
-   <span data-ttu-id="7d13a-109">Discretizar los valores o agregar valores en distintos fragmentos de tiempo.</span><span class="sxs-lookup"><span data-stu-id="7d13a-109">Binning values, or aggregating values by different chunks of time.</span></span>  
  
-   <span data-ttu-id="7d13a-110">Agregar etiquetas para mejorar la utilidad de los resultados.</span><span class="sxs-lookup"><span data-stu-id="7d13a-110">Adding labels to improve the usability of the results.</span></span>  
  
-   <span data-ttu-id="7d13a-111">Convertir los tipos de datos o categorizar los valores en caso necesario para el análisis.</span><span class="sxs-lookup"><span data-stu-id="7d13a-111">Converting data types or categorizing values where necessary for analysis.</span></span>  
  
 <span data-ttu-id="7d13a-112">Si no está familiarizado con el modelado de datos, se recomienda leer el tema relacionado, [lista de comprobación de preparación para la minería de datos](checklist-of-preparation-for-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="7d13a-112">If you are new to data modeling, we recommend that you read the related topic, [Checklist of Preparation for Data Mining](checklist-of-preparation-for-data-mining.md).</span></span>  
  
## <a name="data-preparation-tools"></a><span data-ttu-id="7d13a-113">Herramientas de preparación de datos</span><span class="sxs-lookup"><span data-stu-id="7d13a-113">Data Preparation Tools</span></span>  
 <span data-ttu-id="7d13a-114">Complementos de minería de datos para Office incluye las herramientas siguientes para la limpieza y preparación de los datos:</span><span class="sxs-lookup"><span data-stu-id="7d13a-114">The Data Mining Add-ins for Office includes the following tools for data cleansing and preparation:</span></span>  
  
### <a name="explore-data"></a><span data-ttu-id="7d13a-115">Explorar datos</span><span class="sxs-lookup"><span data-stu-id="7d13a-115">Explore Data</span></span>  
 <span data-ttu-id="7d13a-116">Use el Asistente para **explorar datos** para estas tareas de preparación de datos:</span><span class="sxs-lookup"><span data-stu-id="7d13a-116">Use the **Explore Data** wizard for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="7d13a-117">Obtener una vista previa de los datos e identificar errores que se deben corregir antes del análisis.</span><span class="sxs-lookup"><span data-stu-id="7d13a-117">Preview your data and identify errors that must be fixed prior to analysis.</span></span>  
  
-   <span data-ttu-id="7d13a-118">Recopile información estadística que sea útil para comprender el equilibrio de los datos y las tareas necesarias de limpieza.</span><span class="sxs-lookup"><span data-stu-id="7d13a-118">Gather statistical information that is useful for understanding the balance of data and the required clean-up tasks.</span></span>  
  
-   <span data-ttu-id="7d13a-119">Identificar columnas que son útiles para el análisis y planear la fase de modelado de datos.</span><span class="sxs-lookup"><span data-stu-id="7d13a-119">Identify columns that are useful for analysis, and plan the data modeling phase.</span></span>  
  
 <span data-ttu-id="7d13a-120">[Explore los datos &#40;SQL Server complementos de minería de datos&#41;](explore-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="7d13a-120">[Explore Data &#40;SQL Server Data Mining Add-ins&#41;](explore-data-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="detect-and-handle-outliers"></a><span data-ttu-id="7d13a-121">Detectar y administrar valores atípicos</span><span class="sxs-lookup"><span data-stu-id="7d13a-121">Detect and Handle Outliers</span></span>  
 <span data-ttu-id="7d13a-122">El asistente valores **atípicos** representa gráficamente la distribución de los valores de los datos y ayuda a quitar los valores extremos.</span><span class="sxs-lookup"><span data-stu-id="7d13a-122">The **Outliers** wizard graphs the distribution of values in your data and helps you remove extreme values.</span></span> <span data-ttu-id="7d13a-123">Use la herramienta **valores atípicos** para las siguientes tareas de preparación de datos:</span><span class="sxs-lookup"><span data-stu-id="7d13a-123">Use the **Outliers** tool for the following data preparation tasks:</span></span>  
  
-   <span data-ttu-id="7d13a-124">Determinar si los distintos valores son confiables, basándose en los patrones encontrados en los datos.</span><span class="sxs-lookup"><span data-stu-id="7d13a-124">Determine whether individual values are reliable, based on patterns found in the data.</span></span>  
  
-   <span data-ttu-id="7d13a-125">Revisar valores inusuales y eliminarlos o reemplazarlos.</span><span class="sxs-lookup"><span data-stu-id="7d13a-125">Review unusual values and take action by deleting or replacing them.</span></span>  
  
-   <span data-ttu-id="7d13a-126">Definir el ámbito de un modelo a un intervalo de valores específico.</span><span class="sxs-lookup"><span data-stu-id="7d13a-126">Scope a model to a specific range of values.</span></span> <span data-ttu-id="7d13a-127">Por ejemplo, si sabe que tiene valores atípicos en un almacén determinado, puede eliminar ese valor y obtener un modelo que obtenga mejores predicciones en otros almacenes.</span><span class="sxs-lookup"><span data-stu-id="7d13a-127">For example, if you know that you have outliers at a particular store, you can eliminate that value and get a model that better predicts other stores.</span></span>  
  
 <span data-ttu-id="7d13a-128">[Valores atípicos &#40;SQL Server complementos de minería de datos&#41;](outliers-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="7d13a-128">[Outliers &#40;SQL Server Data Mining Add-ins&#41;](outliers-sql-server-data-mining-add-ins.md).</span></span>  
  
### <a name="relabel-and-bin-data"></a><span data-ttu-id="7d13a-129">Cambiar etiquetas y discretizar datos</span><span class="sxs-lookup"><span data-stu-id="7d13a-129">Relabel and Bin Data</span></span>  
 <span data-ttu-id="7d13a-130">El Asistente para cambiar **etiquetas** agrupa los datos por valores para que pueda cambiar las etiquetas de los datos.</span><span class="sxs-lookup"><span data-stu-id="7d13a-130">The **Relabel** wizard groups data by values so that you can change the labels on the data.</span></span> <span data-ttu-id="7d13a-131">Utilice la herramienta Cambiar etiquetas para estas tareas de preparación de datos:</span><span class="sxs-lookup"><span data-stu-id="7d13a-131">Use the Relabel tool for these data preparation tasks:</span></span>  
  
-   <span data-ttu-id="7d13a-132">Cambiar los códigos numéricos utilizados en los resultados de una encuesta por una descripción de texto con el significado de los códigos numéricos.</span><span class="sxs-lookup"><span data-stu-id="7d13a-132">Change numeric codes used in survey results to a text description of what the numeric code means.</span></span>  
  
     <span data-ttu-id="7d13a-133">Por ejemplo, puede reemplazar entradas de datos como Sexo = 1 por Sexo = Mujer.</span><span class="sxs-lookup"><span data-stu-id="7d13a-133">For example, you might replace data entries such as Gender = 1 with Gender = Female.</span></span>  
  
-   <span data-ttu-id="7d13a-134">Discretizar datos mediante la creación de grupos que representen intervalos de números.</span><span class="sxs-lookup"><span data-stu-id="7d13a-134">Bin data, by creating groups to represents number ranges.</span></span>  
  
     <span data-ttu-id="7d13a-135">Por ejemplo, puede que desee reemplazar una columna ingresos de números por etiquetas como **ingresos-moderado** e **ingresos-alto**.</span><span class="sxs-lookup"><span data-stu-id="7d13a-135">For example, you might want to replace an Income column of numbers with labels such as **Income - Moderate** and **Income - High**.</span></span>  
  
-   <span data-ttu-id="7d13a-136">Contraer valores discretos en categorías.</span><span class="sxs-lookup"><span data-stu-id="7d13a-136">Collapse discrete values into categories.</span></span>  
  
     <span data-ttu-id="7d13a-137">Por ejemplo, si tiene demasiados productos individuales que le imposibilitan detectar un patrón de compras, puede intentar reagrupar los productos en categorías.</span><span class="sxs-lookup"><span data-stu-id="7d13a-137">For example, if you have too many individual products to detect a pattern among purchases, you could try assigning products into broader categories.</span></span>  
  
 [<span data-ttu-id="7d13a-138">Cambiar la etiqueta de &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7d13a-138">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
### <a name="cleanse-data"></a><span data-ttu-id="7d13a-139">Limpiar datos</span><span class="sxs-lookup"><span data-stu-id="7d13a-139">Cleanse Data</span></span>  
 <span data-ttu-id="7d13a-140">La limpieza de datos abarca una amplia variedad de actividades, la mayoría de las cuales se realizan mediante los complementos</span><span class="sxs-lookup"><span data-stu-id="7d13a-140">Data cleansing encompasses a wide range of activities, most of which are supported by the add-ins</span></span>  
  
-   <span data-ttu-id="7d13a-141">Identificar valores NULL y determinar si se deben cambiar por valores reales o se deben considerar valores `Missing`.</span><span class="sxs-lookup"><span data-stu-id="7d13a-141">Identify nulls and determine whether they should be changed to a real value or handled as `Missing` values.</span></span>  
  
-   <span data-ttu-id="7d13a-142">Detectar valores ausentes y quitarlos o imputarles un valor adecuado, como una media, un valor NULL u otro valor.</span><span class="sxs-lookup"><span data-stu-id="7d13a-142">Detect missing values, and then remove them, or impute an appropriate value, such as a mean, null, or other value.</span></span>  
  
 [<span data-ttu-id="7d13a-143">Explorar datos &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7d13a-143">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="7d13a-144">Cambiar la etiqueta de &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7d13a-144">Relabel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](relabel-sql-server-data-mining-add-ins.md)  
  
 [<span data-ttu-id="7d13a-145">Rellenar desde ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d13a-145">Fill From Example</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
### <a name="sample-data"></a><span data-ttu-id="7d13a-146">Datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d13a-146">Sample Data</span></span>  
 <span data-ttu-id="7d13a-147">El Asistente para datos de muestra proporciona dos métodos para crear conjuntos de datos equilibrados para entrenar y probar modelos.</span><span class="sxs-lookup"><span data-stu-id="7d13a-147">The Sample Data wizard provides two methods for creating balanced data sets for training and testing models.</span></span>  
  
-   <span data-ttu-id="7d13a-148">**Muestreo aleatorio.**</span><span class="sxs-lookup"><span data-stu-id="7d13a-148">**Random sampling.**</span></span> <span data-ttu-id="7d13a-149">Utilice esta opción para extraer un conjunto de datos representativo de un conjunto de datos más grande y usarlos como datos de entrenamiento o de prueba.</span><span class="sxs-lookup"><span data-stu-id="7d13a-149">Use this option to extract a representative set of data from a larger data set, for use in either training or testing.</span></span> <span data-ttu-id="7d13a-150">Los complementos de minería de datos usan el *muestreo estratificado* para asegurarse de que se obtiene un conjunto equilibrado de valores para cada variable muestreada.</span><span class="sxs-lookup"><span data-stu-id="7d13a-150">The Data Mining Add-ins use *stratified sampling* to ensure that a balanced set of values is obtained for each variable sampled.</span></span>  
  
-   <span data-ttu-id="7d13a-151">**Sobremuestreo.**</span><span class="sxs-lookup"><span data-stu-id="7d13a-151">**Oversampling.**</span></span> <span data-ttu-id="7d13a-152">Utilice esta opción cuando disponga de menos datos de los que le gustaría para un resultado de destino, y necesite dar a dichos datos un peso mayor.</span><span class="sxs-lookup"><span data-stu-id="7d13a-152">Use this option when you have less data than you would like for a target outcome, and need to weight that data more heavily.</span></span> <span data-ttu-id="7d13a-153">Por ejemplo, el fraude puede ser relativamente poco frecuente, pero puede sobremuestrear los casos que implican fraude para obtener datos apropiados para el modelado.</span><span class="sxs-lookup"><span data-stu-id="7d13a-153">For example, fraud might be relatively rare, but you can oversample cases involving fraud to get adequate data for modeling.</span></span>  
  
 <span data-ttu-id="7d13a-154">[&#40;de datos de ejemplo SQL Server complementos de minería de datos&#41;](sample-data-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="7d13a-154">[Sample Data &#40;SQL Server Data Mining Add-ins&#41;](sample-data-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d13a-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d13a-155">See Also</span></span>  
 <span data-ttu-id="7d13a-156">[Crear un modelo de minería de datos](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="7d13a-156">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="7d13a-157">[Validar modelos y usar modelos para la predicción &#40;complementos de minería de datos para Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="7d13a-157">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="7d13a-158">Implementar y escalar modelos de minería de datos &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="7d13a-158">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
