---
title: Validar modelos y usar modelos para la predicción (complementos de minería de datos para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, validating
- mining models, charting
- validation [data mining]
- mining models, testing
ms.assetid: e245ac1f-1230-48e9-9091-e70b131aa2a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1dd4f9bab977a90579076b824d2c0aa525c84af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671200"
---
# <a name="validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel"></a><span data-ttu-id="a0c44-102">Validar modelos y usar modelos para la predicción (Complementos de minería de datos para Excel)</span><span class="sxs-lookup"><span data-stu-id="a0c44-102">Validating Models and Using Models for Prediction (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="a0c44-103">La prueba y validación de un modelo constituye un paso importante en el proceso de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="a0c44-103">Testing and validating your model is an important step in the data mining process.</span></span> <span data-ttu-id="a0c44-104">Antes de implementar los modelos de minería de datos en un entorno de producción, debe saber cómo se comportan con datos reales.</span><span class="sxs-lookup"><span data-stu-id="a0c44-104">You must know how well your mining models perform against real data before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="a0c44-105">Los Complementos de minería de datos incluyen herramientas que le ayudan a probar los modelos generados, así como a crear predicciones y recomendaciones utilizando estos.</span><span class="sxs-lookup"><span data-stu-id="a0c44-105">The Data Mining Add-ins include tools that help you test the models you built, and create predictions and recommendations using the models.</span></span>  
  
## <a name="accuracy-chart"></a><span data-ttu-id="a0c44-106">Gráfico de precisión</span><span class="sxs-lookup"><span data-stu-id="a0c44-106">Accuracy Chart</span></span>  
 <span data-ttu-id="a0c44-107">El Asistente para **gráfico de precisión** le ayuda a crear una consulta de predicción y evaluar el rendimiento de un modelo de minería de datos mediante la creación de un gráfico de elevación o de dispersión.</span><span class="sxs-lookup"><span data-stu-id="a0c44-107">The **Accuracy Chart** wizard helps you create a prediction query and assess the performance of a data mining model by creating a lift chart or scatter plot chart.</span></span> <span data-ttu-id="a0c44-108">El gráfico de elevación permite distinguir entre los modelos de una estructura que son prácticamente idénticos y determinar cuál ofrece las mejores predicciones.</span><span class="sxs-lookup"><span data-stu-id="a0c44-108">The lift chart helps distinguish between models in a structure that are almost the same, to help you determine which model provides the best predictions.</span></span>  
  
 [<span data-ttu-id="a0c44-109">Gráfico de precisión &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="a0c44-109">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
## <a name="classification-matrix"></a><span data-ttu-id="a0c44-110">Matriz de clasificación</span><span class="sxs-lookup"><span data-stu-id="a0c44-110">Classification Matrix</span></span>  
 <span data-ttu-id="a0c44-111">El Asistente para **matriz de clasificación** le ayuda a crear una consulta de predicción para evaluar el rendimiento de un modelo de clasificación.</span><span class="sxs-lookup"><span data-stu-id="a0c44-111">The **Classification Matrix** wizard helps you create a prediction query to assess the performance of a classification model.</span></span> <span data-ttu-id="a0c44-112">El resultado es un gráfico que resume las predicciones precisas e imprecisas realizadas por el modelo.</span><span class="sxs-lookup"><span data-stu-id="a0c44-112">The output is a chart that summarizes both accurate and inaccurate predictions made by the model.</span></span> <span data-ttu-id="a0c44-113">La matriz es una herramienta valiosa porque no sólo muestra la frecuencia con que el modelo predice un valor correctamente, sino que también muestra qué valores predice el modelo incorrectamente con más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="a0c44-113">The matrix is a valuable tool because it not only shows how frequently the model correctly predicted a value, but also shows which values the model most frequently predicted incorrectly.</span></span>  
  
 [<span data-ttu-id="a0c44-114">Matriz de clasificación &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="a0c44-114">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
## <a name="profit-chart"></a><span data-ttu-id="a0c44-115">Gráfico de beneficios</span><span class="sxs-lookup"><span data-stu-id="a0c44-115">Profit Chart</span></span>  
 <span data-ttu-id="a0c44-116">El Asistente para **gráfico de beneficios** le ayuda a sopesar las ventajas de usar un modelo de minería de datos y evaluar los costos de falsos positivos y falsos negativos.</span><span class="sxs-lookup"><span data-stu-id="a0c44-116">The **Profit Chart** wizard helps you weigh the benefits of using a data mining model and assess the costs of both false positives and false negatives</span></span>  
  
 <span data-ttu-id="a0c44-117">Este tipo de gráfico mide la precisión de la predicción del modelo e incorpora los costos unitarios y totales que especifique.</span><span class="sxs-lookup"><span data-stu-id="a0c44-117">This chart type measures the prediction accuracy of the model and incorporates unit and overall costs that you specify.</span></span>  
  
 <span data-ttu-id="a0c44-118">[Gráfico de beneficios &#40;SQL Server complementos de minería de datos&#41;](profit-chart-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="a0c44-118">[Profit Chart &#40;SQL Server Data Mining Add-ins&#41;](profit-chart-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="cross-validation"></a><span data-ttu-id="a0c44-119">Validación cruzada</span><span class="sxs-lookup"><span data-stu-id="a0c44-119">Cross-Validation</span></span>  
 <span data-ttu-id="a0c44-120">La validación cruzada es una técnica establecida en la comunidad de la minería de datos para evaluar la validez de un conjunto de datos y la precisión de un modelo de minería de datos en dicho conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a0c44-120">Cross-validation is an established technique in the data mining community for assessing the validity of a data set and the accuracy of a mining model on that data set.</span></span> <span data-ttu-id="a0c44-121">Divide un conjunto de datos en subconjuntos y, a continuación, va creando, entrenando y probando modelos de forma iterativa en cada subconjunto.</span><span class="sxs-lookup"><span data-stu-id="a0c44-121">It divides a set of data into subsets, and then iteratively creates, trains, and tests models on each subset.</span></span>  
  
 <span data-ttu-id="a0c44-122">El Asistente para la **validación cruzada** le permite especificar el número de plegamientos por los que dividir los datos y, a continuación, proporciona un informe de validación cruzada que describe estadísticamente las diferencias entre estas secciones transversales.</span><span class="sxs-lookup"><span data-stu-id="a0c44-122">The **Cross-Validation** wizard lets you specify the number of folds to divide your data by, and then provides a cross-validation report that statistically describes the differences among these cross-sections.</span></span> <span data-ttu-id="a0c44-123">Con esta información, puede determinar si el modelo funciona bien con todos los datos de entrenamiento, o si está sesgado hacia un subconjunto determinado.</span><span class="sxs-lookup"><span data-stu-id="a0c44-123">From this you can determine whether the model performs well on all training data, or might be skewed to a particular subset.</span></span>  
  
 [<span data-ttu-id="a0c44-124">&#40;de validación cruzada SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="a0c44-124">Cross-Validation &#40;SQL Server Data Mining Add-ins&#41;</span></span>](cross-validation-sql-server-data-mining-add-ins.md)  
  
## <a name="query-wizard"></a><span data-ttu-id="a0c44-125">Asistente para consultas</span><span class="sxs-lookup"><span data-stu-id="a0c44-125">Query Wizard</span></span>  
 <span data-ttu-id="a0c44-126">El Asistente para **consultas** es una herramienta interactiva que le ayuda a generar una consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="a0c44-126">The **Query** wizard is an interactive tool that helps you build a prediction query.</span></span> <span data-ttu-id="a0c44-127">Las consultas son la forma de generar recomendaciones, pronósticos futuros, etc.</span><span class="sxs-lookup"><span data-stu-id="a0c44-127">Queries are how you generate recommendations, future forecasts, and so forth.</span></span>  
  
 <span data-ttu-id="a0c44-128">En el Asistente para **consultas** , elija un modelo y, a continuación, proporcione datos de entrada, como valores únicos o desde una tabla o un rango, y el asistente le ayudará a seleccionar las columnas que se van a mostrar.</span><span class="sxs-lookup"><span data-stu-id="a0c44-128">In the **Query** wizard, you pick a model, and then provide input data, either as single values or from a table or range, and the wizard helps you select columns to output.</span></span> <span data-ttu-id="a0c44-129">También puede agregar funciones a la consulta para generar puntuaciones de probabilidad y otras estadísticas útiles.</span><span class="sxs-lookup"><span data-stu-id="a0c44-129">You can also add functions to your query to generate probability scores and other useful statistics.</span></span>  
  
 [<span data-ttu-id="a0c44-130">&#40;de consultas SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="a0c44-130">Query &#40;SQL Server Data Mining Add-ins&#41;</span></span>](query-sql-server-data-mining-add-ins.md)  
  
## <a name="advanced-query-editor"></a><span data-ttu-id="a0c44-131">Editor de consultas avanzadas</span><span class="sxs-lookup"><span data-stu-id="a0c44-131">Advanced Query Editor</span></span>  
 <span data-ttu-id="a0c44-132">El **Editor de consultas avanzadas** es un conjunto interactivo de cuadros de diálogo que le ayuda a crear todo tipo de instrucciones DMX, desde ejecutar consultas personalizadas hasta crear y entrenar nuevos modelos, eliminar modelos o crear nuevos conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="a0c44-132">The **Advanced Query Editor** is an interactive set of dialog boxes that helps you build all kinds of DMX statements, anything from running custom queries to creating and training new models, deleting models, or creating new data sets.</span></span>  
  
 [<span data-ttu-id="a0c44-133">Editor de consultas avanzadas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="a0c44-133">Advanced Data Mining Query Editor</span></span>](advanced-data-mining-query-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0c44-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0c44-134">See Also</span></span>  
 <span data-ttu-id="a0c44-135">[Explorar y limpiar datos](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="a0c44-135">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="a0c44-136">[Crear un modelo de minería de datos](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="a0c44-136">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="a0c44-137">Implementar y escalar modelos de minería de datos &#40;complementos de minería de datos para Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="a0c44-137">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
