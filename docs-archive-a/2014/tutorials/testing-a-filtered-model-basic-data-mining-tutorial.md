---
title: Probar un modelo filtrado (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0d74f8c-600d-4df5-a742-695e6947a071
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a97b5ca3523d1fc73405baba52b179a9bef04767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662394"
---
# <a name="testing-a-filtered-model-basic-data-mining-tutorial"></a><span data-ttu-id="8d805-102">Probar un modelo filtrado (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="8d805-102">Testing a Filtered Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="8d805-103">Ahora que ha determinado que el `TM_Decision_Tree` modelo es el más preciso, personalizará el modelo para satisfacer mejor las necesidades de la campaña de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] correo directo.</span><span class="sxs-lookup"><span data-stu-id="8d805-103">Now that you have determined that the `TM_Decision_Tree` model is the most accurate, you will customize the model to better suit the needs of the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] targeted mailing campaign.</span></span> <span data-ttu-id="8d805-104">Concretamente, el departamento de marketing desea saber si hay alguna diferencia entre los clientes masculinos y femeninos.</span><span class="sxs-lookup"><span data-stu-id="8d805-104">Specifically, the Marketing department would like to know if there are any differences between male and female customers.</span></span> <span data-ttu-id="8d805-105">Esta información puede ayudarles a decidir qué revistas utilizar para los anuncios y qué productos ofrecer en sus campañas.</span><span class="sxs-lookup"><span data-stu-id="8d805-105">The information could help them decide which magazines to use for advertising and which products to feature in their mailings.</span></span>  
  
## <a name="using-filters"></a><span data-ttu-id="8d805-106">Usar filtros</span><span class="sxs-lookup"><span data-stu-id="8d805-106">Using Filters</span></span>  
 <span data-ttu-id="8d805-107">El filtrado permite crear con facilidad modelos basados en subconjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="8d805-107">Filtering enables you to easily create models built on subsets of your data.</span></span> <span data-ttu-id="8d805-108">El filtro se aplica solo al modelo y no cambia el origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="8d805-108">The filter is applied only to the model and does not change the underlying data source.</span></span>  
  
 <span data-ttu-id="8d805-109">En esta lección, creará un modelo filtrado por género para predecir las características que más influyen en el comportamiento de compra de los hombres y las mujeres.</span><span class="sxs-lookup"><span data-stu-id="8d805-109">In this lesson, you will create a model that is filtered on gender, to predict the characteristics that most influence buying behavior in males and female.</span></span>  
  
 <span data-ttu-id="8d805-110">En primer lugar, realizará una copia del `TM_Decision_Tree` modelo.</span><span class="sxs-lookup"><span data-stu-id="8d805-110">First you will make a copy of the `TM_Decision_Tree` model.</span></span>  
  
#### <a name="to-copy-the-decision-tree-model"></a><span data-ttu-id="8d805-111">Para copiar el modelo del árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="8d805-111">To copy the Decision Tree Model</span></span>  
  
1.  <span data-ttu-id="8d805-112">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], en el Explorador de soluciones, seleccione **BasicDataMining**.</span><span class="sxs-lookup"><span data-stu-id="8d805-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, select **BasicDataMining**.</span></span>  
  
2.  <span data-ttu-id="8d805-113">Haga clic en la pestaña **Modelos de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="8d805-113">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="8d805-114">Haga clic con el botón secundario en el `TM_Decision_Tree` modelo y seleccione **nuevo modelo de minería de datos.**</span><span class="sxs-lookup"><span data-stu-id="8d805-114">Right click the `TM_Decision_Tree` model, and select **New Mining Model.**</span></span>  
  
4.  <span data-ttu-id="8d805-115">En el campo **nombre del modelo** , escriba `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="8d805-115">In the **Model name** field, type `TM_Decision_Tree_Male`.</span></span>  
  
5.  <span data-ttu-id="8d805-116">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d805-116">Click **OK**.</span></span>  
  
 <span data-ttu-id="8d805-117">Luego, cree un filtro para seleccionar los clientes para el modelo basados en su género.</span><span class="sxs-lookup"><span data-stu-id="8d805-117">Next, create a filter to select customers for the model based on their gender.</span></span>  
  
#### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="8d805-118">Para crear un filtro de casos en un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="8d805-118">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="8d805-119">Haga clic con el botón secundario en el `TM_Decision_Tree_Male` modelo de minería de datos para abrir el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="8d805-119">Right-click the `TM_Decision_Tree_Male` mining model to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="8d805-120">-- o --</span><span class="sxs-lookup"><span data-stu-id="8d805-120">-- or --</span></span>  
  
     <span data-ttu-id="8d805-121">Seleccione el modelo.</span><span class="sxs-lookup"><span data-stu-id="8d805-121">Select the model.</span></span> <span data-ttu-id="8d805-122">En el menú **Minería de datos** , seleccione **Establecer filtro de modelos**.</span><span class="sxs-lookup"><span data-stu-id="8d805-122">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="8d805-123">En el cuadro de diálogo **Filtro del modelo** , haga clic en la fila superior de la cuadrícula en el cuadro de texto **Columna de la estructura de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="8d805-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
     <span data-ttu-id="8d805-124">La lista desplegable muestra solo los nombres de las columnas de esa tabla.</span><span class="sxs-lookup"><span data-stu-id="8d805-124">The drop-down list displays only the names of the columns in that table.</span></span>  
  
3.  <span data-ttu-id="8d805-125">En el cuadro de texto Columna de la estructura de minería de datos, seleccione **Gender**.</span><span class="sxs-lookup"><span data-stu-id="8d805-125">In the Mining Structure Column text box, select **Gender**.</span></span>  
  
     <span data-ttu-id="8d805-126">El icono en la parte izquierda del cuadro de texto cambia para indicar que el elemento seleccionado es una tabla o una columna.</span><span class="sxs-lookup"><span data-stu-id="8d805-126">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
4.  <span data-ttu-id="8d805-127">Haga clic en el cuadro de texto **Operador** y seleccione el operador igual (=) en la lista.</span><span class="sxs-lookup"><span data-stu-id="8d805-127">Click the **Operator** text box and select the equal (=) operator from the list.</span></span>  
  
5.  <span data-ttu-id="8d805-128">Haga clic en el cuadro de texto **Valor** y escriba **M**.</span><span class="sxs-lookup"><span data-stu-id="8d805-128">Click the **Value** text box, and type **M**.</span></span>  
  
6.  <span data-ttu-id="8d805-129">Haga clic en la siguiente fila de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8d805-129">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="8d805-130">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Filtro del modelo** .</span><span class="sxs-lookup"><span data-stu-id="8d805-130">Click **OK** to close the **Model Filter** dialog box.</span></span>  
  
     <span data-ttu-id="8d805-131">El filtro se muestra en la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="8d805-131">The filter displays in the **Properties** window.</span></span> <span data-ttu-id="8d805-132">Como alternativa, puede iniciar el cuadro de diálogo **Filtro del modelo** en la ventana **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="8d805-132">Alternately, you can launch the **Model Filter** dialog from the **Properties** window.</span></span>  
  
8.  <span data-ttu-id="8d805-133">Repita los pasos anteriores, pero esta vez asigne un nombre al modelo `TM_Decision_Tree_Female` y escriba **F** en el cuadro de texto **valor** .</span><span class="sxs-lookup"><span data-stu-id="8d805-133">Repeat the above steps, but this time name the model `TM_Decision_Tree_Female` and type **F** in the **Value** text box.</span></span>  
  
## <a name="process-the-filtered-models"></a><span data-ttu-id="8d805-134">Procesar los modelos filtrados</span><span class="sxs-lookup"><span data-stu-id="8d805-134">Process the Filtered Models</span></span>  
 <span data-ttu-id="8d805-135">Los modelos no se pueden utilizar hasta que se hayan implementado y procesado.</span><span class="sxs-lookup"><span data-stu-id="8d805-135">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="8d805-136">Para obtener más información sobre los modelos de procesamiento, vea [procesar modelos en la estructura de distribución de correo directo &#40;tutorial básico de minería de datos&#41;](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="8d805-136">For more information on processing models, see [Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md).</span></span>  
  
#### <a name="to-process-the-filtered-model"></a><span data-ttu-id="8d805-137">Para procesar el modelo filtrado</span><span class="sxs-lookup"><span data-stu-id="8d805-137">To process the filtered model</span></span>  
  
1.  <span data-ttu-id="8d805-138">Haga clic con el botón secundario en el `TM_Decision_Tree_Male` modelo y seleccione **procesar estructura de minería de datos y todos los modelos**.</span><span class="sxs-lookup"><span data-stu-id="8d805-138">Right-click the `TM_Decision_Tree_Male` model and select **Process Mining Structure and all Model**s</span></span>  
  
2.  <span data-ttu-id="8d805-139">Haga clic en **Ejecutar** para procesar los nuevos modelos.</span><span class="sxs-lookup"><span data-stu-id="8d805-139">Click **Run** to process the new models.</span></span>  
  
3.  <span data-ttu-id="8d805-140">Una vez completado el procesamiento, haga clic en **Cerrar** en ambas ventanas de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="8d805-140">After processing is complete, click **Close** on both processing windows.</span></span>  
  
     <span data-ttu-id="8d805-141">Ahora tiene dos modelos nuevos que se muestran en la pestaña **Modelos de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="8d805-141">You now have two new models displayed in the **Mining Models** tab.</span></span>  
  
## <a name="evaluate-the-results"></a><span data-ttu-id="8d805-142">Evaluar los resultados</span><span class="sxs-lookup"><span data-stu-id="8d805-142">Evaluate the Results</span></span>  
 <span data-ttu-id="8d805-143">Vea los resultados y evalúe la exactitud de los modelos filtrados de la misma manera que hizo con los tres modelos anteriores.</span><span class="sxs-lookup"><span data-stu-id="8d805-143">View the results and assess the accuracy of the filtered models in much the same way as you did for the previous three models.</span></span> <span data-ttu-id="8d805-144">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="8d805-144">For more information, see:</span></span>  
  
 [<span data-ttu-id="8d805-145">Explorar el modelo de árbol de decisión &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="8d805-145">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="8d805-146">Probar la exactitud con gráficos de mejora respecto al modelo predictivo &#40;Tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="8d805-146">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
#### <a name="to-explore-the-filtered-models"></a><span data-ttu-id="8d805-147">Para explorar los modelos filtrados</span><span class="sxs-lookup"><span data-stu-id="8d805-147">To explore the filtered models</span></span>  
  
1.  <span data-ttu-id="8d805-148">Seleccione la pestaña **Visor de modelo de minería de datos** en **Diseñador de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="8d805-148">Select the **Mining Model Viewer** tab in **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="8d805-149">En el cuadro modelo de minería de datos, seleccione `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="8d805-149">In the Mining Model box, select `TM_Decision_Tree_Male`.</span></span>  
  
3.  <span data-ttu-id="8d805-150">**Nivel** de presentación en `3` .</span><span class="sxs-lookup"><span data-stu-id="8d805-150">Slide **Show Level** to `3`.</span></span>  
  
4.  <span data-ttu-id="8d805-151">Cambie el valor de **fondo** a `1` .</span><span class="sxs-lookup"><span data-stu-id="8d805-151">Change the **Background** value to `1`.</span></span>  
  
5.  <span data-ttu-id="8d805-152">Coloque el cursor sobre el nodo con la etiqueta **Todos** para ver el número de compradores de bicicleta con respecto a los no compradores.</span><span class="sxs-lookup"><span data-stu-id="8d805-152">Place your cursor over the node labeled **All** to see the number of bike buyers versus non-bike buyers.</span></span>  
  
6.  <span data-ttu-id="8d805-153">Repita los pasos 1-5 para `TM_Decision_Tree_Female` .</span><span class="sxs-lookup"><span data-stu-id="8d805-153">Repeat steps 1 - 5 for `TM_Decision_Tree_Female`.</span></span>  
  
7.  <span data-ttu-id="8d805-154">Explore los resultados de `TM_Decision_Tree` y los modelos filtrados por sexo.</span><span class="sxs-lookup"><span data-stu-id="8d805-154">Explore the results for the `TM_Decision_Tree` and the models filtered for gender.</span></span> <span data-ttu-id="8d805-155">Si se comparan todos los compradores de bicicletas, los compradores masculinos y femeninos comparten algunas de las mismas características de los compradores de bicicletas sin filtrar, pero los tres también presentan diferencias interesantes.</span><span class="sxs-lookup"><span data-stu-id="8d805-155">Compared to all bike buyers, male and female bike buyers share some of the same characteristics as the unfiltered bike buyers but all three have interesting differences as well.</span></span> <span data-ttu-id="8d805-156">Ésta es información útil que [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] puede utilizar para desarrollar su campaña de marketing.</span><span class="sxs-lookup"><span data-stu-id="8d805-156">This is useful information that [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] can use to develop their marketing campaign.</span></span>  
  
#### <a name="to-test-the-lift-of-the-filtered-models"></a><span data-ttu-id="8d805-157">Para probar la mejora en la predicción de los modelos filtrados</span><span class="sxs-lookup"><span data-stu-id="8d805-157">To test the lift of the filtered models</span></span>  
  
1.  <span data-ttu-id="8d805-158">Cambie a la pestaña **Gráfico de precisión de minería de datos** del Diseñador de minería de datos de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] y seleccione la pestaña **Selección de entrada** .</span><span class="sxs-lookup"><span data-stu-id="8d805-158">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="8d805-159">En el cuadro de grupo **Seleccionar un conjunto de datos para usarlo en un gráfico de precisión** , seleccione **Usar casos de prueba de estructura de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="8d805-159">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span>  
  
3.  <span data-ttu-id="8d805-160">En la pestaña **Selección de entrada** del Diseñador de minería de datos, en **Seleccione las columnas del modelo de minería de datos de predicción que se mostrarán en el gráfico de elevación**, active la casilla correspondiente a **Sincronizar valores y columnas de predicción**.</span><span class="sxs-lookup"><span data-stu-id="8d805-160">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
4.  <span data-ttu-id="8d805-161">En la columna **Nombre de columna de predicción** , compruebe que **Bike Buyer** está seleccionado para cada modelo.</span><span class="sxs-lookup"><span data-stu-id="8d805-161">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
5.  <span data-ttu-id="8d805-162">En la columna **Mostrar** , seleccione cada uno de los modelos.</span><span class="sxs-lookup"><span data-stu-id="8d805-162">In the **Show** column, select each of the models.</span></span>  
  
6.  <span data-ttu-id="8d805-163">En la columna **valor de predicción** , seleccione `1` .</span><span class="sxs-lookup"><span data-stu-id="8d805-163">In the **Predict Value** column, select `1`.</span></span>  
  
7.  <span data-ttu-id="8d805-164">Seleccione la pestaña **Gráfico de mejora respecto al modelo predictivo** para mostrar el gráfico de mejora.</span><span class="sxs-lookup"><span data-stu-id="8d805-164">Select the **Lift Chart** tab to display the lift chart.</span></span>  
  
     <span data-ttu-id="8d805-165">Observará ahora que los tres modelos de Árbol de decisión proporcionan una mejora significativa con respecto al modelo de estimación aleatoria, además de superar a los modelos de agrupación en clústeres y Bayes naive.</span><span class="sxs-lookup"><span data-stu-id="8d805-165">You will now notice that all three Decision Tree models provide significant lift compared to the random guess model, and also outperform the Clustering and Naive-Bayes models.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8d805-166">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8d805-166">Related Tasks</span></span>  
 <span data-ttu-id="8d805-167">Para obtener más información sobre los filtros, vea [filtros para modelos de minería de datos &#40;Analysis Services-Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="8d805-167">For more information on filters, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="8d805-168">Para obtener un ejemplo de cómo aplicar filtros a tablas anidadas, vea [tutorial intermedio de minería de datos &#40;Analysis Services-&#41;de minería de datos ](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="8d805-168">For an example of how to apply filters to nested tables, see [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="8d805-169">Tarea anterior de la lección</span><span class="sxs-lookup"><span data-stu-id="8d805-169">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="8d805-170">Probar la exactitud con gráficos de mejora respecto al modelo predictivo &#40;Tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="8d805-170">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="8d805-171">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="8d805-171">Next Lesson</span></span>  
 [<span data-ttu-id="8d805-172">Lección 6: Crear y trabajar con predicciones &#40;Tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="8d805-172">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="8d805-173">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d805-173">See Also</span></span>  
 <span data-ttu-id="8d805-174">[Tutorial intermedio de minería de datos &#40;Analysis Services:&#41;de minería de datos](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="8d805-174">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="8d805-175">[Tareas y procedimientos del modelo de minería de datos](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="8d805-175">[Mining Model Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="8d805-176">[Eliminar un filtro de un modelo de minería de datos](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="8d805-176">[Delete a Filter from a Mining Model](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="8d805-177">Filtros para modelos de minería &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="8d805-177">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
