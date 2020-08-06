---
title: Asistente para pronóstico (complementos de minería de datos para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- forecasting [data mining]
- time series [data mining]
ms.assetid: c5b33f75-42d4-4598-89e7-94815c142ce6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c3fae97bf1c36154d8ae378840014f2fb997afd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669967"
---
# <a name="forecast-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="c53e1-102">Asistente para pronóstico (Complementos de minería de datos para Excel)</span><span class="sxs-lookup"><span data-stu-id="c53e1-102">Forecast Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="c53e1-103">![Asistente para asociación, cinta de opciones Minería de datos](media/dmc-forecast.gif "Asistente para asociación, cinta de opciones Minería de datos")</span><span class="sxs-lookup"><span data-stu-id="c53e1-103">![Associate wizard in Data Mining ribbon](media/dmc-forecast.gif "Associate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="c53e1-104">El Asistente para pronóstico le permite predecir valores en una serie temporal.</span><span class="sxs-lookup"><span data-stu-id="c53e1-104">The Forecast wizard helps you predict values in a time series.</span></span> <span data-ttu-id="c53e1-105">El Asistente para pronóstico usa el algoritmo de serie temporal de [!INCLUDE[msCoName](../includes/msconame-md.md)], que es un algoritmo de regresión que se usa para predecir columnas continuas, como ventas de productos.</span><span class="sxs-lookup"><span data-stu-id="c53e1-105">The Forecast wizard uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm, which is a regression algorithm for use in predicting continuous columns, such as product sales.</span></span>  
  
 <span data-ttu-id="c53e1-106">Cada modelo de pronóstico debe contener una serie de casos, que es la columna que distingue entre los puntos de una secuencia.</span><span class="sxs-lookup"><span data-stu-id="c53e1-106">Each forecasting model must contain a case series, which is the column that distinguishes between points in a sequence.</span></span> <span data-ttu-id="c53e1-107">Por ejemplo, si va a usar datos históricos para pronosticar las ventas durante un período de varios meses, debería usar una columna que contenga una serie de fechas como la serie de casos.</span><span class="sxs-lookup"><span data-stu-id="c53e1-107">For example, if you are using historical data to forecast sales over a period of several months, you would use a column containing a series of dates as the case series.</span></span>  
  
 <span data-ttu-id="c53e1-108">Puede crear predicciones a partir de un modelo de predicción sin proporcionar nuevos datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="c53e1-108">You can create predictions from a forecasting model without providing new input data.</span></span>  
  
 <span data-ttu-id="c53e1-109">El [pronóstico &#40;herramienta de&#41;herramientas de análisis de tabla para Excel](forecast-table-analysis-tools-for-excel.md) , en la cinta de opciones **analizar** también le permite crear modelos de predicción, pero es menos personalizable y solo puede usar datos en tablas de Excel.</span><span class="sxs-lookup"><span data-stu-id="c53e1-109">The [Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) tool, in the **Analyze** ribbon, also lets you create forecasting models, but it is less customizable and can only use data in Excel tables.</span></span>  
  
## <a name="using-the-forecast-wizard"></a><span data-ttu-id="c53e1-110">Usar el Asistente para pronóstico</span><span class="sxs-lookup"><span data-stu-id="c53e1-110">Using the Forecast Wizard</span></span>  
  
1.  <span data-ttu-id="c53e1-111">En la cinta de opciones **minería de datos** , haga clic en **previsión**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-111">In the **Data Mining** ribbon, click **Forecast**.</span></span>  
  
2.  <span data-ttu-id="c53e1-112">En **seleccionar datos de origen**, elija la tabla, el intervalo o el origen de datos externo de Excel que se usarán como entradas.</span><span class="sxs-lookup"><span data-stu-id="c53e1-112">In the **Select Source Data**, choose the Excel table, range, or external data source to use as inputs.</span></span>  
  
     <span data-ttu-id="c53e1-113">Si utiliza un origen de datos externo, puede definir consultas o vistas personalizadas y guardarlas como un origen de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c53e1-113">If you use an external data source, you can define custom view or queries and save it as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="c53e1-114">En la página **previsión** , en **marca de tiempo**, seleccione una columna que contenga el valor numérico único (esto incluye los valores de fecha y hora) que se puede utilizar como serie de casos.</span><span class="sxs-lookup"><span data-stu-id="c53e1-114">On the **Forecasting** page, for **Time stamp**, select a column that contains unique numeric value (this includes date and time values) that can be used as the case series.</span></span> <span data-ttu-id="c53e1-115">El origen de datos se debe ordenar de forma ascendente según esta columna.</span><span class="sxs-lookup"><span data-stu-id="c53e1-115">The data source must be sorted in ascending order by this column.</span></span>  
  
     <span data-ttu-id="c53e1-116">Si los datos no tienen este tipo de columna, puede usar la opción \<no time stamp> .</span><span class="sxs-lookup"><span data-stu-id="c53e1-116">If your data does not have such a column, you can use the option \<no time stamp>.</span></span> <span data-ttu-id="c53e1-117">El asistente agregará una columna de orden única para los datos de entrada; por consiguiente, debe asegurarse de que los datos están ordenados de la manera que desea antes de ejecutar el asistente y elegir esta opción.</span><span class="sxs-lookup"><span data-stu-id="c53e1-117">The wizard will add a unique order column for the input data; therefore, you must make sure that the data is sorted the way you want before running the wizard and choosing this option.</span></span>  
  
4.  <span data-ttu-id="c53e1-118">Opcionalmente, puede hacer clic en **parámetros** y personalizar el comportamiento del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="c53e1-118">Optionally, you can click **Parameters** and customize the behavior of the mining model.</span></span>  
  
     <span data-ttu-id="c53e1-119">Los modelos de predicción admiten varios algoritmos:</span><span class="sxs-lookup"><span data-stu-id="c53e1-119">Forecasting models support several different algorithms:</span></span>  
  
    -   <span data-ttu-id="c53e1-120">ARIMA</span><span class="sxs-lookup"><span data-stu-id="c53e1-120">ARIMA</span></span>  
  
    -   <span data-ttu-id="c53e1-121">ARTXP (un tipo de modelo de regresión)</span><span class="sxs-lookup"><span data-stu-id="c53e1-121">ARTXP (a type of regression model)</span></span>  
  
    -   <span data-ttu-id="c53e1-122">ARTXP y ARIMA combinados</span><span class="sxs-lookup"><span data-stu-id="c53e1-122">ARTXP and ARIMA combined</span></span>  
  
     <span data-ttu-id="c53e1-123">Para obtener información acerca de las diferencias, vea [referencia técnica del algoritmo de serie temporal de Microsoft](data-mining/microsoft-time-series-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c53e1-123">For information about the differences, see [Microsoft Time Series Algorithm Technical Reference](data-mining/microsoft-time-series-algorithm-technical-reference.md).</span></span>  
  
     <span data-ttu-id="c53e1-124">También puede agregar sugerencias de periodicidad, especificar opciones de suavizado y personalizar las opciones de regresión para el modelo.</span><span class="sxs-lookup"><span data-stu-id="c53e1-124">You can also add periodicity hints, specify smoothing options, and customize regression options for the model.</span></span>  
  
5.  <span data-ttu-id="c53e1-125">En la página **Finalizar** , proporcione un nombre descriptivo para el conjunto de datos y el modelo, y establezca las siguientes opciones que controlan cómo se trabaja con el modelo terminado:</span><span class="sxs-lookup"><span data-stu-id="c53e1-125">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="c53e1-126">**Examinar modelo**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-126">**Browse model**.</span></span> <span data-ttu-id="c53e1-127">Cuando se selecciona esta opción, en cuanto el asistente finaliza el procesamiento del modelo, se abre una ventana **examinar** para ayudarle a explorar los resultados.</span><span class="sxs-lookup"><span data-stu-id="c53e1-127">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="c53e1-128">El contenido del visor depende del tipo de modelo que creó.</span><span class="sxs-lookup"><span data-stu-id="c53e1-128">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="c53e1-129">Para obtener más información, vea [examinar un modelo de previsión](browsing-a-forecasting-model.md).</span><span class="sxs-lookup"><span data-stu-id="c53e1-129">For more information, see [Browsing a Forecasting Model](browsing-a-forecasting-model.md).</span></span>  
  
    -   <span data-ttu-id="c53e1-130">**Habilitar la obtención de detalles**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-130">**Enable drillthrough**.</span></span> <span data-ttu-id="c53e1-131">Seleccione esta opción para ver los datos subyacentes desde el modelo terminado.</span><span class="sxs-lookup"><span data-stu-id="c53e1-131">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="c53e1-132">Esta opción solo está disponible si se crea un modelo de árbol de decisión.</span><span class="sxs-lookup"><span data-stu-id="c53e1-132">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="c53e1-133">**Usar modelo temporal**.</span><span class="sxs-lookup"><span data-stu-id="c53e1-133">**Use temporary model**.</span></span> <span data-ttu-id="c53e1-134">Si selecciona esta opción, el modelo no se guardará en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c53e1-134">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="c53e1-135">Se eliminan los modelos temporales al cerrar Excel.</span><span class="sxs-lookup"><span data-stu-id="c53e1-135">Temporary models are deleted when you close Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="c53e1-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c53e1-136">Requirements</span></span>  
 <span data-ttu-id="c53e1-137">Los datos deben incluir al menos una columna que se pueda utilizar como serie temporal.</span><span class="sxs-lookup"><span data-stu-id="c53e1-137">Your data should include at least one column that can be used as the time series.</span></span> <span data-ttu-id="c53e1-138">Los valores de esta columna deben ser únicos y continuos; es decir, no debería haber ningún hueco.</span><span class="sxs-lookup"><span data-stu-id="c53e1-138">The values in this column should be unique and continuous - that is, there should be no gaps.</span></span> <span data-ttu-id="c53e1-139">Antes de ejecutar el asistente, ordene los datos según la columna de serie temporal en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="c53e1-139">Before running the wizard, sort the data by the time series column in ascending order.</span></span>  
  
 <span data-ttu-id="c53e1-140">Si los datos no incluyen una columna de hora o de fecha, puede asignar una serie numérica arbitraria o permitir al asistente crearla.</span><span class="sxs-lookup"><span data-stu-id="c53e1-140">If your data does not include a time or date column, you can assign an arbitrary numeric series, or let the wizard create one.</span></span> <span data-ttu-id="c53e1-141">Si permite al asistente crear la columna de orden de la serie, asegúrese de que las otras columnas están ordenadas en el orden que desea antes de iniciar el asistente.</span><span class="sxs-lookup"><span data-stu-id="c53e1-141">F you let the wizard create the series order column, make sure the other columns are sorted in the worder you want them before starting the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c53e1-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c53e1-142">See Also</span></span>  
 <span data-ttu-id="c53e1-143">[Crear un modelo de minería de datos](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="c53e1-143">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 <span data-ttu-id="c53e1-144">[Previsión &#40;herramientas de análisis de tabla para Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="c53e1-144">[Forecast &#40;Table Analysis Tools for Excel&#41;](forecast-table-analysis-tools-for-excel.md) </span></span>  
 [<span data-ttu-id="c53e1-145">Examinar un modelo de pronóstico</span><span class="sxs-lookup"><span data-stu-id="c53e1-145">Browsing a Forecasting Model</span></span>](browsing-a-forecasting-model.md)  
  
  
