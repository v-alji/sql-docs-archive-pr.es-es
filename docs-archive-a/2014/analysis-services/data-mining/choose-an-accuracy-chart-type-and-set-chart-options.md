---
title: Elegir un tipo de gráfico de precisión y establecer las opciones del gráfico | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services]
- mining models [Analysis Services], validating
- classification accuracy [data mining]
- accuracy testing [data mining]
ms.assetid: bd24dd4a-624f-478a-9c94-b1361e857680
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33c2b5e8a1e228a86328ef6df1b636742d3614ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671847"
---
# <a name="choose-an-accuracy-chart-type-and-set-chart-options"></a><span data-ttu-id="2cd35-102">Elegir un tipo de gráfico de precisión y establecer las opciones del gráfico</span><span class="sxs-lookup"><span data-stu-id="2cd35-102">Choose an Accuracy Chart Type and Set Chart Options</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="2cd35-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]proporciona varios métodos para determinar la validez de los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="2cd35-103">[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] provides multiple methods for determining the validity of your mining models.</span></span> <span data-ttu-id="2cd35-104">El tipo de gráfico de precisión que puede crear para cada modelo o estructura depende de estos factores:</span><span class="sxs-lookup"><span data-stu-id="2cd35-104">The type of accuracy chart that you can create for each model or structure depends on these factors:</span></span>  
  
-   <span data-ttu-id="2cd35-105">El tipo de algoritmo utilizado para crear el modelo</span><span class="sxs-lookup"><span data-stu-id="2cd35-105">The type of algorithm that was used to create the model</span></span>  
  
-   <span data-ttu-id="2cd35-106">El tipo de datos del atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="2cd35-106">The data type of the predictable attribute</span></span>  
  
-   <span data-ttu-id="2cd35-107">El número de atributos de predicción que medir</span><span class="sxs-lookup"><span data-stu-id="2cd35-107">The number of predictable attributes to measure</span></span>  
  
 <span data-ttu-id="2cd35-108">En este tema se proporciona información general de los diferentes gráficos de precisión.</span><span class="sxs-lookup"><span data-stu-id="2cd35-108">This topic provides an overview of the different accuracy charts.</span></span>  
  
 <span data-ttu-id="2cd35-109">**Nota** Los gráficos y sus definiciones no se guardan.</span><span class="sxs-lookup"><span data-stu-id="2cd35-109">**Note** Charts and their definitions are not saved.</span></span> <span data-ttu-id="2cd35-110">Si cierra la ventana que contiene un gráfico, debe volverlo a crear.</span><span class="sxs-lookup"><span data-stu-id="2cd35-110">If you close the window that contains a chart, you must create the chart again.</span></span>  
  
## <a name="accuracy-chart-types"></a><span data-ttu-id="2cd35-111">Tipos de gráficos de precisión</span><span class="sxs-lookup"><span data-stu-id="2cd35-111">Accuracy Chart Types</span></span>  
 <span data-ttu-id="2cd35-112">Según el tipo de gráfico que elija, puede seguir configurando las opciones, examinar el gráfico o copiarlo en el Portapapeles y trabajar con los datos en Excel.</span><span class="sxs-lookup"><span data-stu-id="2cd35-112">Depending on the chart type that you choose, you have the ability to further configure options, to browse the chart, or copy the chart to the Clipboard and work with the data in Excel.</span></span>  
  
#### <a name="lift-chart"></a><span data-ttu-id="2cd35-113">Gráfico de elevación</span><span class="sxs-lookup"><span data-stu-id="2cd35-113">Lift chart</span></span>  
 <span data-ttu-id="2cd35-114">Después de configurar las opciones para los modelos y los datos de prueba, haga clic en la pestaña **Gráfico de elevación** para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="2cd35-114">After you have configured the options for the models and the testing data, click the **Lift Chart** tab to view the results.</span></span> <span data-ttu-id="2cd35-115">También puede copiar el gráfico en el Portapapeles o ver detalles de puntos de datos o líneas de tendencia individuales en la Leyenda de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="2cd35-115">You can also copy the chart to the Clipboard, or view details of individual trend lines or data points in the Mining Legend.</span></span>  
  
#### <a name="profit-chart"></a><span data-ttu-id="2cd35-116">Gráfico de beneficios</span><span class="sxs-lookup"><span data-stu-id="2cd35-116">Profit Chart</span></span>  
 <span data-ttu-id="2cd35-117">Después de configurar las opciones de los modelos y los datos de prueba, haga clic en la pestaña **Gráfico de elevación** , seleccione **Gráfico de beneficios** en la lista **Tipo de gráfico** para establecer las opciones del gráfico de beneficios y, a continuación, haga clic en **Aceptar** para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="2cd35-117">After you have configured the options for the models and the testing data, click the **Lift Chart** tab, select **Profit Chart** from the **Chart Type** list to set profit chart options, and then click **OK** to view the results.</span></span>  
  
 <span data-ttu-id="2cd35-118">Puede utilizar el cuadro de diálogo **Configuración del gráfico de beneficios** tantas veces como desee para probar opciones de costo diferentes y volver a mostrar el gráfico.</span><span class="sxs-lookup"><span data-stu-id="2cd35-118">You can use the **Profit Chart Settings** dialog box as many times as you want to try different cost options and redisplay the chart.</span></span> <span data-ttu-id="2cd35-119">La Leyenda de minería de datos contiene información detallada sobre las ventajas estimadas de cada modelo.</span><span class="sxs-lookup"><span data-stu-id="2cd35-119">The Mining Legend contains detailed information about the estimated profit for each model.</span></span> <span data-ttu-id="2cd35-120">También puede copiar el gráfico y el contenido de la Leyenda de minería de datos en el Portapapeles para trabajar con ellos en Excel.</span><span class="sxs-lookup"><span data-stu-id="2cd35-120">You can also copy the chart and the contents of the Mining Legend to the Clipboard to work with it in Excel.</span></span>  
  
#### <a name="scatter-plot"></a><span data-ttu-id="2cd35-121">Gráfico de dispersión</span><span class="sxs-lookup"><span data-stu-id="2cd35-121">Scatter Plot</span></span>  
 <span data-ttu-id="2cd35-122">Si ha seleccionado el tipo adecuado de modelo, al hacer clic en la pestaña **Gráfico de elevación** , el tipo de gráfico se establece automáticamente en **Gráfico de dispersión** y se muestra un gráfico de dispersión.</span><span class="sxs-lookup"><span data-stu-id="2cd35-122">If you have selected the appropriate type of model, when you click the **Lift Chart** tab, the chart type is automatically set to **Scatter Plot** and a scatter plot is displayed.</span></span> <span data-ttu-id="2cd35-123">No se puede realizar ninguna otra configuración.</span><span class="sxs-lookup"><span data-stu-id="2cd35-123">No further configuration is possible.</span></span> <span data-ttu-id="2cd35-124">También puede copiar el gráfico en el Portapapeles y pegarlo como un gráfico en Excel u otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="2cd35-124">You can also copy the chart to the Clipboard and paste the chart as a graphic into Excel or another application.</span></span>  
  
#### <a name="classification-matrix"></a><span data-ttu-id="2cd35-125">Matriz de clasificación</span><span class="sxs-lookup"><span data-stu-id="2cd35-125">Classification Matrix</span></span>  
 <span data-ttu-id="2cd35-126">En una matriz de clasificación, utilice la pestaña **Selección de entrada** para elegir los modelos y los datos de prueba y, a continuación, haga clic en la pestaña **Matriz de clasificación** para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="2cd35-126">For a classification matrix, use the **Input Selection** tab to choose the models and the testing data, and then click the **Classification Matrix** tab to view the results.</span></span>  
  
 <span data-ttu-id="2cd35-127">El contenido de una matriz de clasificación es el mismo para todos los tipos de modelo y no se puede configurar.</span><span class="sxs-lookup"><span data-stu-id="2cd35-127">The contents of a classification matrix are the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="2cd35-128">Puede copiar los datos del gráfico en el Portapapeles y, a continuación, trabajar con ellos en Excel.</span><span class="sxs-lookup"><span data-stu-id="2cd35-128">You can copy the data in the chart to the Clipboard and then work with it in Excel.</span></span>  
  
#### <a name="cross-validation-report"></a><span data-ttu-id="2cd35-129">Informe de validación cruzada</span><span class="sxs-lookup"><span data-stu-id="2cd35-129">Cross-Validation Report</span></span>  
 <span data-ttu-id="2cd35-130">En un informe de validación cruzada, después de seleccionar una estructura o un modelo de minería de datos en el Explorador de soluciones, haga clic en la pestaña **Validación cruzada** , configure todas las opciones correspondientes y, después, haga clic **Obtener resultados** para generar el informe.</span><span class="sxs-lookup"><span data-stu-id="2cd35-130">For a cross-validation report, after you have selected a mining structure or mining model in Solution Explorer, click the **Cross Validation** tab, configure all relevant options, and then click **Get Results** to generate the report.</span></span> <span data-ttu-id="2cd35-131">No se puede realizar ninguna otra configuración.</span><span class="sxs-lookup"><span data-stu-id="2cd35-131">No further configuration is possible.</span></span>  
  
 <span data-ttu-id="2cd35-132">El formato del informe de validación cruzada es el mismo para todos los tipos de modelo y no se puede configurar.</span><span class="sxs-lookup"><span data-stu-id="2cd35-132">The format of the cross-validation report is the same for all model types, and cannot be configured.</span></span> <span data-ttu-id="2cd35-133">Sin embargo, el contenido del informe difiere según sea el tipo de modelo que se esté analizando y el tipo de datos del atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="2cd35-133">However, the content of the report differs depending on the type of model that you are analyzing, and the data type of the predictable attribute.</span></span> <span data-ttu-id="2cd35-134">También puede copiar los resultados del informe en el Portapapeles y trabajar con ellos en Excel.</span><span class="sxs-lookup"><span data-stu-id="2cd35-134">You can also copy the results of the report to the Clipboard and work with the data in Excel.</span></span>  
  
  
