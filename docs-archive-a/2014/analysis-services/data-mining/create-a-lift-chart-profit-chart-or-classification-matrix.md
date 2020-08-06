---
title: Crear un gráfico de elevación, un gráfico de beneficios o una matriz de clasificación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], mining structures
ms.assetid: aa3d052f-58a9-4417-8e7a-5e6feb562af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 932138b37b36269bed86df42786bd5d684f75ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744444"
---
# <a name="create-a-lift-chart-profit-chart-or-classification-matrix"></a><span data-ttu-id="855ae-102">Crear un gráfico de mejora respecto al modelo predictivo, un gráfico de beneficios o una matriz de clasificación</span><span class="sxs-lookup"><span data-stu-id="855ae-102">Create a Lift Chart, Profit Chart, or Classification Matrix</span></span>
  <span data-ttu-id="855ae-103">Puede crear un gráfico de precisión para un modelo de minería de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] siguiendo cinco pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="855ae-103">You can create an accuracy chart for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data mining model in five basic steps:</span></span>  
  
-   <span data-ttu-id="855ae-104">Seleccione la estructura de minería de datos que contiene los modelos de minería de datos que desea comparar.</span><span class="sxs-lookup"><span data-stu-id="855ae-104">Select the mining structure that contains the mining models that you want to compare.</span></span>  
  
-   <span data-ttu-id="855ae-105">Seleccione los modelos de minería de datos que desea agregar al gráfico.</span><span class="sxs-lookup"><span data-stu-id="855ae-105">Select the mining models to add to the chart.</span></span>  
  
-   <span data-ttu-id="855ae-106">Especifique el origen de datos de pruebas que se ha de utilizar al generar el gráfico.</span><span class="sxs-lookup"><span data-stu-id="855ae-106">Specify a source of testing data to use in generating the chart.</span></span>  
  
-   <span data-ttu-id="855ae-107">Elija el tipo de gráfico.</span><span class="sxs-lookup"><span data-stu-id="855ae-107">Choose the chart type.</span></span>  
  
-   <span data-ttu-id="855ae-108">Configure las opciones de gráfico.</span><span class="sxs-lookup"><span data-stu-id="855ae-108">Configure the chart options.</span></span>  
  
 <span data-ttu-id="855ae-109">Estos pasos básicos son los mismos para el gráfico de elevación, el gráfico de beneficios y la matriz de clasificación.</span><span class="sxs-lookup"><span data-stu-id="855ae-109">These basic steps are the same for the lift chart, profit chart, and classification matrix.</span></span> <span data-ttu-id="855ae-110">Los procedimientos siguientes describen los pasos necesarios para configurar las opciones de gráfico básicas para estos tipos de gráfico.</span><span class="sxs-lookup"><span data-stu-id="855ae-110">The following procedures outline the steps to configure the basic chart options for these chart types.</span></span> <span data-ttu-id="855ae-111">Para obtener más información sobre cómo crear un informe de validación cruzada, vea [Medidas en el informe de validación cruzada](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="855ae-111">For information about how to create a cross-validation report, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
### <a name="open-the-mining-structure-in-the-accuracy-chart-designer"></a><span data-ttu-id="855ae-112">Abrir la estructura de minería de datos en el Diseñador de gráficos de precisión</span><span class="sxs-lookup"><span data-stu-id="855ae-112">Open the mining structure in the Accuracy Chart Designer</span></span>  
  
1.  <span data-ttu-id="855ae-113">Abra el Diseñador de minería de datos de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="855ae-113">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="855ae-114">En el Explorador de soluciones, haga doble clic en la estructura que contiene el modelo o los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="855ae-114">In Solution Explorer, double-click the structure that contains the mining model or models.</span></span>  
  
3.  <span data-ttu-id="855ae-115">Haga clic en la pestaña **Gráfico de precisión de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="855ae-115">Click the **Mining Accuracy Chart** tab.</span></span>  
  
### <a name="select-mining-models-for-inclusion-in-the-chart"></a><span data-ttu-id="855ae-116">Seleccionar los modelos de minería de datos para incluirlos en el gráfico</span><span class="sxs-lookup"><span data-stu-id="855ae-116">Select mining models for inclusion in the chart</span></span>  
  
1.  <span data-ttu-id="855ae-117">En la pestaña **Gráfico de precisión de minería de datos** del Diseñador de minería de datos de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga clic en la pestaña **Selección de entrada** .</span><span class="sxs-lookup"><span data-stu-id="855ae-117">On the **Mining Accuracy Chart** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Input Selection** tab.</span></span>  
  
     <span data-ttu-id="855ae-118">La lista muestra todos los modelos de la estructura actual que tienen el mismo atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="855ae-118">The list displays all models in the current structure that have the same predictable attribute.</span></span>  
  
2.  <span data-ttu-id="855ae-119">Seleccione el cuadro **Mostrar** para cada uno de los modelos que desea incluir en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="855ae-119">Select the **Show box** for each model that you want to include in the chart.</span></span>  
  
3.  <span data-ttu-id="855ae-120">Haga clic en el cuadro de texto **Nombre de columna de predicción** y seleccione el nombre de una columna de predicción en la lista.</span><span class="sxs-lookup"><span data-stu-id="855ae-120">Click the **Predictable Column Name** text box, and select the name of a predictable column from the list.</span></span> <span data-ttu-id="855ae-121">Todos los modelos que ponga en el gráfico deben tener la misma columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="855ae-121">All models that you put in one chart must have the same predictable column.</span></span>  
  
4.  <span data-ttu-id="855ae-122">Si compara dos modelos y las columnas de predicción tienen valores o tipos de datos diferentes, desactive la casilla **Sincronizar valores y columnas de predicción** para forzar la comparación.</span><span class="sxs-lookup"><span data-stu-id="855ae-122">If you compare two models and the predictable columns have different values or different data types, clear the **Synchonize prediction columns and values** box to force a comparison.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="855ae-123">Si está activada la casilla **Sincronizar valores y columnas de predicción** , Analysis Services analiza los datos de las columnas de predicción del modelo y los datos de pruebas, e intenta buscar la mejor coincidencia.</span><span class="sxs-lookup"><span data-stu-id="855ae-123">If the **Synchonize prediction columns and values** box is selected, Analysis Services analyzes the data in the predictable columns of the model and the test data, and attempts to find the best match.</span></span> <span data-ttu-id="855ae-124">Por consiguiente, no desactive la casilla a menos que sea absolutamente necesario forzar una comparación de las columnas.</span><span class="sxs-lookup"><span data-stu-id="855ae-124">Therefore, do not clear the box unless absolutely necessary to force a comparison of the columns.</span></span>  
  
5.  <span data-ttu-id="855ae-125">Haga clic en el cuadro de texto **Valor de predicción** y seleccione un valor en la lista.</span><span class="sxs-lookup"><span data-stu-id="855ae-125">Click the **Predict Value** text box, and select a value from the list.</span></span> <span data-ttu-id="855ae-126">Si la columna de predicción es un tipo de datos continuo, debe escribir un valor en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="855ae-126">If the predictable column is a continuous data type, you must type a value in the text box.</span></span>  
  
     <span data-ttu-id="855ae-127">Para obtener más información, vea [Elija la columna que se va a utilizar para probar un modelo de minería de datos](choose-the-column-to-use-for-testing-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="855ae-127">For more information, see [Choose the Column to Use for Testing a Mining Model](choose-the-column-to-use-for-testing-a-mining-model.md).</span></span>  
  
### <a name="select-testing-data"></a><span data-ttu-id="855ae-128">Seleccionar los datos de pruebas</span><span class="sxs-lookup"><span data-stu-id="855ae-128">Select testing data</span></span>  
  
1.  <span data-ttu-id="855ae-129">En la pestaña **Selección de entrada** de la pestaña **Gráfico de precisión de minería de datos** , especifique el origen de los datos que utilizará para generar el gráfico seleccionando una de las opciones del grupo **Seleccionar un conjunto de datos para usarlo en un gráfico de precisión**.</span><span class="sxs-lookup"><span data-stu-id="855ae-129">On the **Input Selection** tab of the **Mining Accuracy Chart** tab, specify the source of the data that you will use to generate the chart by selecting one of the options in the group, **Select data set to be used for accuracy chart**.</span></span>  
  
    -   <span data-ttu-id="855ae-130">Seleccione la opción **Usar casos de pruebas de modelo de minería de datos**si desea utilizar el subconjunto de casos definido por la intersección de los casos de prueba de la estructura de minería de datos y los filtros que se hayan aplicado durante la creación del modelo.</span><span class="sxs-lookup"><span data-stu-id="855ae-130">Select the option, **Use Mining Model test cases**, if you want to use the subset of cases that is defined by the intersection of the mining structure test cases and any filters that may have been applied during model creation.</span></span>  
  
    -   <span data-ttu-id="855ae-131">Seleccione la opción **Usar casos de pruebas de estructura de minería de datos**para utilizar el conjunto completo de casos de prueba que se definieron como parte del conjunto de datos de exclusión de las estructuras de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="855ae-131">Select the option, **Use mining structure test cases**, to use the full set of testing cases that were defined as part of the mining structures holdout data set.</span></span>  
  
    -   <span data-ttu-id="855ae-132">Seleccione la opción **Especificar otro conjunto de datos**si desea utilizar datos externos.</span><span class="sxs-lookup"><span data-stu-id="855ae-132">Select the option, **Specify a different data set**, if you want to use external data.</span></span>  <span data-ttu-id="855ae-133">El conjunto de datos debe estar disponible como vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="855ae-133">The data set must be available as a data source view.</span></span>   <span data-ttu-id="855ae-134">Haga clic en el botón Examinar (**...**) para elegir las tablas de datos que se van a usar para el gráfico de precisión.</span><span class="sxs-lookup"><span data-stu-id="855ae-134">Click the browse (**...**) button to choose the data tables to use for the accuracy chart.</span></span> <span data-ttu-id="855ae-135">Para más información, consulte [Choose and Map Model Testing Data](choose-and-map-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="855ae-135">For more information, see [Choose and Map Model Testing Data](choose-and-map-model-testing-data.md).</span></span>  
  
         <span data-ttu-id="855ae-136">Si está utilizando un conjunto de datos externos, opcionalmente puede filtrar el conjunto de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="855ae-136">If you are using an external data set, you can optionally filter the input data set.</span></span> <span data-ttu-id="855ae-137">Para obtener más información, vea [Aplicar filtros a los datos de prueba del modelo](apply-filters-to-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="855ae-137">For more information, see [Apply Filters to Model Testing Data](apply-filters-to-model-testing-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="855ae-138">No se puede crear un filtro en los casos de prueba del modelo ni en los casos de prueba de la estructura de minería de datos en la pestaña **selección de entrada** . Para crear un filtro en el modelo de minería de datos, modifique la propiedad Filter del modelo.</span><span class="sxs-lookup"><span data-stu-id="855ae-138">You cannot create a filter on the model test cases or the mining structure test cases on the **Input Selection** tab. To create a filter on the mining model, modify the Filter property of the model.</span></span> <span data-ttu-id="855ae-139">Para más información, vea [Aplicar un filtro a un modelo de minería de datos](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="855ae-139">For more information, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
### <a name="configure-chart-settings-and-generate-the-chart"></a><span data-ttu-id="855ae-140">Configurar los valores del gráfico y generarlo</span><span class="sxs-lookup"><span data-stu-id="855ae-140">Configure chart settings and generate the chart</span></span>  
  
1.  <span data-ttu-id="855ae-141">En la pestaña **Gráfico de precisión de minería de datos** , haga clic en la pestaña correspondiente al gráfico que desea crear.</span><span class="sxs-lookup"><span data-stu-id="855ae-141">In the **Mining Accuracy Chart** tab, click the tab for the chart you want to create.</span></span>  
  
2.  <span data-ttu-id="855ae-142">Para un **gráfico de elevación**, haga clic en la pestaña **gráfico de elevación** . El gráfico se genera automáticamente basándose en el modelo, los atributos de predicción y los datos de entrada que acaba de seleccionar.</span><span class="sxs-lookup"><span data-stu-id="855ae-142">For a **lift chart**, click the **Lift Chart** tab. The chart is automatically generated based on the model, predictable attributes, and input data that you just selected.</span></span>  
  
3.  <span data-ttu-id="855ae-143">Para una **matriz de clasificación**, haga clic en la pestaña **matriz de clasificación** . No es necesario realizar más configuraciones. el gráfico se genera automáticamente en función de los datos de entrada y del modelo que haya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="855ae-143">For a **classification matrix**, click the **Classification Matrix** tab. No further settings are needed; the chart is automatically generated based on the input data and model that you selected.</span></span>  
  
4.  <span data-ttu-id="855ae-144">Para un **gráfico de beneficios**, haga clic primero en la pestaña **gráfico de elevación** . A continuación, en la lista desplegable **tipo de gráfico** , seleccione **gráfico de beneficios**.</span><span class="sxs-lookup"><span data-stu-id="855ae-144">For a **profit chart**, first click the **Lift Chart** tab. Then, from the **Chart type** drop-down list, select **Profit chart**.</span></span>  
  
     <span data-ttu-id="855ae-145">Escriba los valores siguientes en el cuadro de diálogo **Configuración del gráfico de beneficios** .</span><span class="sxs-lookup"><span data-stu-id="855ae-145">Enter the following settings in the **Profit Chart Settings** dialog box.</span></span>  
  
     <span data-ttu-id="855ae-146">**Llenado**</span><span class="sxs-lookup"><span data-stu-id="855ae-146">**Population**</span></span>  
     <span data-ttu-id="855ae-147">El número de casos del conjunto de datos que desea utilizar al crear el gráfico de elevación.</span><span class="sxs-lookup"><span data-stu-id="855ae-147">The number of cases from the data set that you want to use when creating the lift chart.</span></span>  
  
     <span data-ttu-id="855ae-148">El modelo siempre elige los casos en orden de probabilidad decreciente; es decir, si se están evaluando clientes potenciales y elige un número que representa solo la mitad de los registros de la base de datos de clientes, el modelo medirá la exactitud en el subconjunto de casos que mejor se ajustan al modelo.</span><span class="sxs-lookup"><span data-stu-id="855ae-148">The model always chooses the cases in order of decreasing probability; that is, if you are assessing potential customers and you choose a number that represents only half the records in your customer database, the model will measure accuracy on the subset of cases that best fit your model.</span></span>  
  
     <span data-ttu-id="855ae-149">Esto se debe a que cuando use el modelo para generar un envío de correo directo o crear una campaña, utilizará la probabilidad de predicción asociada a cada caso para destinarlo solo a los clientes que tengan la mayor probabilidad de dar una respuesta favorable.</span><span class="sxs-lookup"><span data-stu-id="855ae-149">This is because when you use the model to generate a mailing or create a campaign, you will use the prediction probability associated with each case to target only the customers who have the highest probability of making a positive response.</span></span>  
  
     <span data-ttu-id="855ae-150">**Costo fijo**</span><span class="sxs-lookup"><span data-stu-id="855ae-150">**Fixed Cost**</span></span>  
     <span data-ttu-id="855ae-151">Costo fijo asociado con el problema de la empresa.</span><span class="sxs-lookup"><span data-stu-id="855ae-151">The fixed cost that is associated with the business problem.</span></span>  
  
     <span data-ttu-id="855ae-152">Si se tratara de una solución de envío de correo directo, el costo fijo podría representar una tarifa por la configuración de la impresora que abarcara el costo inicial de preparar el envío de correo promocional.</span><span class="sxs-lookup"><span data-stu-id="855ae-152">If this were for a targeted mailing solution, the fixed cost might represent a printer setup fee that covers the initial cost of preparing the promotional mailing.</span></span>  
  
     <span data-ttu-id="855ae-153">Este costo se aplica una vez a toda la población de destino.</span><span class="sxs-lookup"><span data-stu-id="855ae-153">This cost applies one time to the entire target population.</span></span>  
  
     <span data-ttu-id="855ae-154">**Costo individual**</span><span class="sxs-lookup"><span data-stu-id="855ae-154">**Individual Cost**</span></span>  
     <span data-ttu-id="855ae-155">Costos adicionales al costo fijo y que se pueden asociar con cada contacto con el cliente.</span><span class="sxs-lookup"><span data-stu-id="855ae-155">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="855ae-156">Por ejemplo, podría especificar el costo del franqueo para un envío de correo promocional o el costo de la realización de llamadas telefónicas.</span><span class="sxs-lookup"><span data-stu-id="855ae-156">For example, you might enter the postage cost for a promotional mailing or the cost of making telephone calls.</span></span>  
  
     <span data-ttu-id="855ae-157">Este costo debe ser el mismo para toda la población de destino.</span><span class="sxs-lookup"><span data-stu-id="855ae-157">This cost must be the same for the entire target population.</span></span> <span data-ttu-id="855ae-158">Cada valor se multiplica por el número de casos que constituyen el destino.</span><span class="sxs-lookup"><span data-stu-id="855ae-158">Each value is multiplied by the number of cases that are targeted.</span></span>  
  
     <span data-ttu-id="855ae-159">**Ingresos por individuo**</span><span class="sxs-lookup"><span data-stu-id="855ae-159">**Revenue Per Individual**</span></span>  
     <span data-ttu-id="855ae-160">Cantidad de ingresos asociados con cada venta realizada con éxito.</span><span class="sxs-lookup"><span data-stu-id="855ae-160">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="855ae-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="855ae-161">See Also</span></span>  
 <span data-ttu-id="855ae-162">[Gráfico de elevación &#40;Analysis Services:&#41;de minería de datos](lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="855ae-162">[Lift Chart &#40;Analysis Services - Data Mining&#41;](lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="855ae-163">Matriz de clasificación &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="855ae-163">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](classification-matrix-analysis-services-data-mining.md)  
  
  
