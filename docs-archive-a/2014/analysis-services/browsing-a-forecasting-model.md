---
title: Examinar un modelo de previsión | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- forecasting [data mining]
- mining models, viewing
- mining model, time series
- time series [data mining]
ms.assetid: ad35a528-1949-4048-8678-3b9760c1c88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d0b188c4ed6fba9bc5b1082725b17c99081c1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670108"
---
# <a name="browsing-a-forecasting-model"></a><span data-ttu-id="74844-102">Examinar un modelo de pronóstico</span><span class="sxs-lookup"><span data-stu-id="74844-102">Browsing a Forecasting Model</span></span>
  <span data-ttu-id="74844-103">Al abrir un modelo de previsión mediante **examinar**, el modelo se muestra en un visor interactivo, similar al visor de modelos de serie temporal de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="74844-103">When you open a forecasting model using **Browse**, the model is displayed in an interactive viewer, similar to the time series model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="74844-104">El visor sirve para explorar las tendencias, comparar series, crear predicciones y obtener información sobre el modelo y los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="74844-104">The viewer helps you explore trends, compare series, create predictions, and get information about the model and the underlying data.</span></span>  
  
##  <a name="explore-the-model"></a><a name="bkmk_Top"></a><span data-ttu-id="74844-105">Explorar el modelo</span><span class="sxs-lookup"><span data-stu-id="74844-105">Explore the Model</span></span>  
 <span data-ttu-id="74844-106">El visor de **búsqueda** de modelos de predicción proporciona una vista de gráfico, que muestra las tendencias a lo largo del tiempo y permite crear predicciones, y una vista de modelo, que representa la serie temporal como un árbol de decisión o un árbol de regresión.</span><span class="sxs-lookup"><span data-stu-id="74844-106">The **Browse** viewer for forecasting models provides a chart view, which shows the trends over time and lets you create predictions, and a model view, which represents the time series as a decision tree or a regression tree.</span></span>  
  
-   [<span data-ttu-id="74844-107">Vista de gráfico</span><span class="sxs-lookup"><span data-stu-id="74844-107">Chart view</span></span>](#bkmk_charts)  
  
-   [<span data-ttu-id="74844-108">Vista Modelo</span><span class="sxs-lookup"><span data-stu-id="74844-108">Model view</span></span>](#bkmk_Model)  
  
 <span data-ttu-id="74844-109">Para experimentar con un modelo de predicción, puede utilizar los datos de ejemplo de la pestaña Previsión del libro de datos de ejemplo y generar un modelo de serie temporal mediante el [Asistente para previsión &#40;complementos de minería de datos para excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) en la cinta de opciones **minería de datos** o [previsión &#40;herramientas de análisis de tabla para Excel&#41;](forecast-table-analysis-tools-for-excel.md) en la cinta de opciones **analizar** .</span><span class="sxs-lookup"><span data-stu-id="74844-109">To experiment with a forecasting model, you can use the sample data on the Forecast tab of the sample data workbook, and build a time series model using the [Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;](forecast-wizard-data-mining-add-ins-for-excel.md) in the **Data Mining** ribbon, or [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) in the **Analyze** ribbon.</span></span>  
  
###  <a name="chart"></a><a name="bkmk_charts"></a><span data-ttu-id="74844-110">Gráfica</span><span class="sxs-lookup"><span data-stu-id="74844-110">Chart</span></span>  
 <span data-ttu-id="74844-111">La pestaña **gráfico** muestra la tendencia de la serie de datos a lo largo del tiempo, junto con los valores de predicción.</span><span class="sxs-lookup"><span data-stu-id="74844-111">The **Chart** tab displays the trend in your data series over time, together with the predicted values.</span></span> <span data-ttu-id="74844-112">El eje vertical del gráfico representa los valores de la serie y el eje horizontal representa el tiempo.</span><span class="sxs-lookup"><span data-stu-id="74844-112">The vertical axis of the chart represents the values of the series, and the horizontal axis represents time.</span></span>  
  
##### <a name="explore-the-forecasting-chart"></a><span data-ttu-id="74844-113">Explorar el gráfico de predicción</span><span class="sxs-lookup"><span data-stu-id="74844-113">Explore the forecasting chart</span></span>  
  
1.  <span data-ttu-id="74844-114">Este modelo contiene varias series temporales pero, para simplificar el gráfico, puede mostrar una sola serie o algunas series relacionadas.</span><span class="sxs-lookup"><span data-stu-id="74844-114">This model contains multiple time series, but to simplify the chart, you can display a single series, or just a few related series.</span></span>  
  
     <span data-ttu-id="74844-115">![predicciones históricas en el modelo de predicción](media/dm13-forecast-chart-historicpredictions.gif "predicciones históricas en el modelo de predicción")</span><span class="sxs-lookup"><span data-stu-id="74844-115">![historical predictions in the forecasting model](media/dm13-forecast-chart-historicpredictions.gif "historical predictions in the forecasting model")</span></span>  
  
     <span data-ttu-id="74844-116">Utilice las casillas para seleccionar la predicción solo para Norteamérica y solo para la cantidad de ventas.</span><span class="sxs-lookup"><span data-stu-id="74844-116">Use the check boxes to select the forecast for just North America, and just for sales Amount.</span></span>  
  
2.  <span data-ttu-id="74844-117">Haga clic en **pasos de predicción** y escriba un nuevo valor para controlar cuántos valores de hora futuros desea ver en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="74844-117">Click **Prediction Steps** and type a new value to control how many future time values you want to see in the chart.</span></span>  
  
     <span data-ttu-id="74844-118">El valor predeterminado es 5.</span><span class="sxs-lookup"><span data-stu-id="74844-118">The default is 5.</span></span>  
  
3.  <span data-ttu-id="74844-119">Haga clic en cualquier punto de la línea, ya sea historial o futuro, para ver los valores exactos de ese momento en el tiempo, que se muestra en la **leyenda de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="74844-119">Click any point in the line, either historical or future, to see the exact values for that point in time, displayed in the **Mining Legend**.</span></span>  
  
4.  <span data-ttu-id="74844-120">El gráfico muestra tanto los datos históricos como los futuros.</span><span class="sxs-lookup"><span data-stu-id="74844-120">The chart displays both historical and future data.</span></span> <span data-ttu-id="74844-121">Observe la línea de puntos con un fondo sombreado.</span><span class="sxs-lookup"><span data-stu-id="74844-121">Note the dotted line, with a shaded background.</span></span> <span data-ttu-id="74844-122">Estos valores son las predicciones futuras, según el modelo.</span><span class="sxs-lookup"><span data-stu-id="74844-122">These values are the future predictions, based on the model.</span></span>  
  
     <span data-ttu-id="74844-123">Los datos históricos (que usó para generar el modelo) se muestran en el lado izquierdo del gráfico.</span><span class="sxs-lookup"><span data-stu-id="74844-123">The historical data (which you used to build the model) is shown in the left side of the chart.</span></span>  
  
5.  <span data-ttu-id="74844-124">Seleccione la opción **Mostrar predicciones históricas** para tener una idea de la estabilidad de la serie temporal.</span><span class="sxs-lookup"><span data-stu-id="74844-124">Select the **Show historic predictions** option to get a sense for the stability of the time series.</span></span>  
  
     <span data-ttu-id="74844-125">![predicciones para una única serie del modelo](media/dm13-forecast-chart-singleseries.gif "predicciones para una única serie del modelo")</span><span class="sxs-lookup"><span data-stu-id="74844-125">![forecasts for a single series in the model](media/dm13-forecast-chart-singleseries.gif "forecasts for a single series in the model")</span></span>  
  
     <span data-ttu-id="74844-126">Las predicciones históricas son los valores previstos en función de las series hasta ese punto, que se comparan con los valores históricos reales.</span><span class="sxs-lookup"><span data-stu-id="74844-126">Historical predictions are values predicted based on the series to that point, which are compared to actual historical values.</span></span> <span data-ttu-id="74844-127">Si la línea de puntos (con los valores previstos) se aparta de la línea continua (los valores reales), significa que la primera parte de la serie quizás no predice con precisión los valores posteriores.</span><span class="sxs-lookup"><span data-stu-id="74844-127">If the dotted line (with the predicted values) is far apart from the solid line (the actual values), it means the first part of the series perhaps does not accurately predict the later values.</span></span> <span data-ttu-id="74844-128">Podría necesitar más datos o podría ser simplemente un indicador de la volatilidad en el ciclo.</span><span class="sxs-lookup"><span data-stu-id="74844-128">You might need more data, or it might simply be an indicator of volatility in the cycle.</span></span>  
  
6.  <span data-ttu-id="74844-129">Seleccione la opción **Mostrar desviaciones** para mostrar las barras de error en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="74844-129">Select the **Show Deviations** option to display error bars in the chart.</span></span>  
  
     <span data-ttu-id="74844-130">Las barras de error permiten evaluar visualmente la variabilidad de las predicciones.</span><span class="sxs-lookup"><span data-stu-id="74844-130">The error bars let you visually assess the variability of the predictions.</span></span> <span data-ttu-id="74844-131">La calidad de las predicciones varía en función de los datos de origen pero a medida que aumenta el número de pasos de predicción, debería ver las desviaciones en constante aumento.</span><span class="sxs-lookup"><span data-stu-id="74844-131">The quality of predictions varies depending on your source data, but as you increase the number of prediction steps, you should see the deviations steadily increase.</span></span>  
  
 <span data-ttu-id="74844-132">**Sugerencias**</span><span class="sxs-lookup"><span data-stu-id="74844-132">**Tips**</span></span>  
  
-   <span data-ttu-id="74844-133">Para alternar la presentación de la **leyenda de minería de datos**, haga clic con el botón secundario en cualquier punto del gráfico.</span><span class="sxs-lookup"><span data-stu-id="74844-133">To toggle display of the **Mining Legend**, right-click any point in the chart.</span></span>  
  
     <span data-ttu-id="74844-134">Puede ver un intervalo específico de tiempo; para ello, haga clic en el gráfico, arrastre una selección temporal sobre el gráfico y, a continuación, haga clic de nuevo para acercarse al intervalo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="74844-134">You can view a specific time range by clicking the chart, dragging a time selection across the chart, and then clicking again to zoom in on the selected range.</span></span>  
  
-   <span data-ttu-id="74844-135">Para obtener una copia del gráfico actual, haga clic en **copiar a Excel**y, a continuación, haga clic en una hoja de cálculo en Excel.</span><span class="sxs-lookup"><span data-stu-id="74844-135">To get a copy of the current chart, click **Copy to Excel**, then click a worksheet in Excel.</span></span> <span data-ttu-id="74844-136">Un gráfico se inserta en la hoja con todas las opciones que hubiera establecido, incluida una leyenda.</span><span class="sxs-lookup"><span data-stu-id="74844-136">A graphic is inserted in the sheet using all the options you had set, including a legend.</span></span>  
  
     <span data-ttu-id="74844-137">Sin embargo, este gráfico es estático, por lo que no se puede editar la leyenda ni ver los datos subyacentes. Si necesita una vista de gráfico más interactiva, use los [visores de Visio](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="74844-137">However, this graphic is static so you cannot edit the legend or view the underlying data; if you need a more interactive chart view, use the [Visio viewers](viewing-data-mining-models-in-visio-data-mining-add-ins.md).</span></span>  
  
-   <span data-ttu-id="74844-138">Haga clic en **ABS** en la barra de menús del visor para alternar entre las curvas absolutas y relativas.</span><span class="sxs-lookup"><span data-stu-id="74844-138">Click **Abs** in the viewer menu bar to toggle between absolute and relative curves.</span></span>  
  
     <span data-ttu-id="74844-139">Esta opción es útil si el gráfico contiene varios modelos pero la escala de los datos de cada modelo es muy distinta.</span><span class="sxs-lookup"><span data-stu-id="74844-139">This option is useful if your chart contains multiple models, but the scale of the data for each model is very different.</span></span>  
  
     <span data-ttu-id="74844-140">Por ejemplo, si los almacenes de la región del Pacífico eran nuevos y las ventas eran bajas, y se utilizan valores absolutos, la línea que muestra las ventas del Pacífico podría parecer plana, dificultando la visualización de los cambios reales, mientras que los otros modelos se muestran en una escala más normal.</span><span class="sxs-lookup"><span data-stu-id="74844-140">For example, if the Pacific region stores were new and sales were low, and if absolute values are used, the line showing Pacific sales might appear flat, making it difficult to see actual changes, whereas the other models would be displayed at a more normal scale.</span></span>  
  
     <span data-ttu-id="74844-141">Al cambiar la vista para usar valores relativos, puede normalizar la escala de modelos diferentes y mostrar las diferencias como un porcentaje de cambio.</span><span class="sxs-lookup"><span data-stu-id="74844-141">By switching the view to use relative values, you can normalize the scale of different models, and display differences as a percent of change.</span></span> <span data-ttu-id="74844-142">Cuando el cambio es relativo a cada modelo, puede mostrarse en el mismo gráfico sin una distorsión significativa.</span><span class="sxs-lookup"><span data-stu-id="74844-142">When change is relative to each model, they can be displayed in the same graph without significant distortion.</span></span>  
  
 [<span data-ttu-id="74844-143">Explorar el modelo</span><span class="sxs-lookup"><span data-stu-id="74844-143">Explore the Model</span></span>](#bkmk_Top)  
  
###  <a name="model"></a><a name="bkmk_Model"></a><span data-ttu-id="74844-144">Modela</span><span class="sxs-lookup"><span data-stu-id="74844-144">Model</span></span>  
 <span data-ttu-id="74844-145">Un modelo de predicción también se puede representar como un árbol de decisión o bien, si la serie es básicamente lineal, un modelo de regresión.</span><span class="sxs-lookup"><span data-stu-id="74844-145">A forecasting model can also be represented as a decision tree, or, if the series is mostly linear, a regression model.</span></span>  
  
 <span data-ttu-id="74844-146">Por ejemplo, en este modelo hay una diferencia en la fórmula de regresión según cierta condición, por lo que el árbol se divide en dos bifurcaciones, cada una con una fórmula de regresión distinta.</span><span class="sxs-lookup"><span data-stu-id="74844-146">For example, in this model, there is a difference in the regression formula based on a certain condition, so the tree splits into two branches, each with a different regression formula.</span></span>  
  
 <span data-ttu-id="74844-147">![Filtrar una única serie del modelo de predicción](media/dm13-forecast-model-northamerica.gif "Filtrar una única serie del modelo de predicción")</span><span class="sxs-lookup"><span data-stu-id="74844-147">![Filter single series in the forecasting model](media/dm13-forecast-model-northamerica.gif "Filter single series in the forecasting model")</span></span>  
  
##### <a name="explore-the-forecasting-model-as-a-tree"></a><span data-ttu-id="74844-148">Explorar el modelo de predicción como un árbol</span><span class="sxs-lookup"><span data-stu-id="74844-148">Explore the forecasting model as a tree</span></span>  
  
1.  <span data-ttu-id="74844-149">Haga clic en la lista desplegable **árbol** y elija el modelo que desea mostrar.</span><span class="sxs-lookup"><span data-stu-id="74844-149">Click the **Tree** dropdown list and choose a model to display.</span></span>  
  
     <span data-ttu-id="74844-150">Se muestra un árbol independiente o un nodo de regresión para cada atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="74844-150">A separate tree or regression node is displayed for each predictable attribute.</span></span> <span data-ttu-id="74844-151">Por ejemplo, si los datos contienen las ventas para Europa, Norteamérica y el Pacífico, habría tres modelos distintos, uno para cada serie de datos.</span><span class="sxs-lookup"><span data-stu-id="74844-151">For example, if your data contains sales for Europe, North America, and the Pacific, there would three different models, one for each data series.</span></span>  
  
2.  <span data-ttu-id="74844-152">Arrastre el control deslizante **Mostrar nivel** para filtrar los niveles inferiores del árbol y céntrese en las divisiones más importantes.</span><span class="sxs-lookup"><span data-stu-id="74844-152">Drag the **Show Level** slider to filter out lower levels of the tree, and focus on the most important splits.</span></span>  
  
3.  <span data-ttu-id="74844-153">Haga clic en cada nodo para ver algunas estadísticas descriptivas en la **leyenda de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="74844-153">Click each node to view some descriptive statistics in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="74844-154">A medida que pausa el mouse sobre un nodo con el mouse, la información sobre herramientas también muestra las mismas estadísticas, así como la fórmula completa que describe el nodo.</span><span class="sxs-lookup"><span data-stu-id="74844-154">As you pause over a node with the mouse, a ToolTip also displays the same statistics, as well as the full formula describing that node.</span></span>  
  
4.  <span data-ttu-id="74844-155">Si desea copiar la información de la leyenda de **minería de datos**, haga clic con el botón secundario en la **leyenda de minería de datos**, seleccione **copiar**y haga clic dentro de la hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="74844-155">If you want to copy the information in the **Mining Legend**, right-click the **Mining Legend**, select **Copy**, and click inside your Excel worksheet.</span></span> <span data-ttu-id="74844-156">La opción **Copiar en Excel** copia el gráfico, no las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="74844-156">The **Copy to Excel** option copies the graph, not the statistics.</span></span>  
  
 [<span data-ttu-id="74844-157">Explorar el modelo</span><span class="sxs-lookup"><span data-stu-id="74844-157">Explore the Model</span></span>](#bkmk_Top)  
  
## <a name="see-also"></a><span data-ttu-id="74844-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74844-158">See Also</span></span>  
 [<span data-ttu-id="74844-159">Examinar modelos en Excel &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="74844-159">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
