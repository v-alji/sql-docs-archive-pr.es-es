---
title: Elegir la columna que se va a utilizar para probar un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], predictable mining columns
- Mining Accuracy Chart [Analysis Services], columns
- predictable mining columns [Analysis Services]
ms.assetid: c6a8f23a-da21-4f31-9521-99460d624649
author: minewiskan
ms.author: owend
ms.openlocfilehash: 326a7084600695d95d3a132f633041e9abad045b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674453"
---
# <a name="choose-the-column-to-use-for-testing-a-mining-model"></a><span data-ttu-id="9149a-102">Elija la columna que se va a utilizar para probar un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="9149a-102">Choose the Column to Use for Testing a Mining Model</span></span>
  <span data-ttu-id="9149a-103">Para poder medir la exactitud de un modelo de minería de datos, debe decidir qué resultado desea devolver.</span><span class="sxs-lookup"><span data-stu-id="9149a-103">Before you can measure the accuracy of a mining model, you must decide which outcome it is that you want to assess.</span></span> <span data-ttu-id="9149a-104">La mayoría de los modelos de minería de datos requieren que seleccione al menos una columna para utilizarla como atributo de predicción al crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="9149a-104">Most data mining models require that you choose at least one column to use as the predictable attribute when you create the model.</span></span> <span data-ttu-id="9149a-105">Por consiguiente, al probar la precisión del modelo, normalmente debe seleccionar ese atributo para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="9149a-105">Therefore, when you test the accuracy of the model, you generally must select that attribute to test.</span></span>  
  
 <span data-ttu-id="9149a-106">En la siguiente lista se describen algunas consideraciones adicionales para elegir el atributo de predicción para utilizarlo en las pruebas:</span><span class="sxs-lookup"><span data-stu-id="9149a-106">The following list describes some additional considerations for choosing the predictable attribute to use in testing:</span></span>  
  
-   <span data-ttu-id="9149a-107">Algunos tipos de modelos de minería de datos pueden predecir varios atributos, como redes neuronal, que pueden explorar las relaciones entre muchos atributos.</span><span class="sxs-lookup"><span data-stu-id="9149a-107">Some types of data mining models can predict multiple attributes-such as neural networks, which can explore the relationships between many attributes.</span></span>  
  
-   <span data-ttu-id="9149a-108">Otros tipos de modelos de minería de datos, como los modelos de agrupación en clústeres, no tienen necesariamente un atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="9149a-108">Other types of mining models-such as clustering models-do not necessarily have a predictable attribute.</span></span> <span data-ttu-id="9149a-109">Los modelos de clústeres no se pueden probar a menos que tengan un atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="9149a-109">Clustering models cannot be tested unless they have a predictable attribute.</span></span>  
  
-   <span data-ttu-id="9149a-110">Para crear un gráfico de dispersión o medir la exactitud de un modelo de regresión es necesario que elija un atributo de predicción continuo como resultado.</span><span class="sxs-lookup"><span data-stu-id="9149a-110">To create a scatter plot or measure the accuracy of a regression model requires that you choose a continuous predictable attribute as the outcome.</span></span> <span data-ttu-id="9149a-111">En ese caso, no puede especificar un valor de destino.</span><span class="sxs-lookup"><span data-stu-id="9149a-111">In that case, you cannot specify a target value.</span></span> <span data-ttu-id="9149a-112">Si va a crear algo distinto de un gráfico de dispersión, la columna de la estructura de minería de datos subyacente también debe tener un tipo de contenido **Discreto** o **Discretizado**.</span><span class="sxs-lookup"><span data-stu-id="9149a-112">If you are creating anything other than a scatter plot, the underlying mining structure column must also have a content type of **Discrete** or **Discretized**.</span></span>  
  
-   <span data-ttu-id="9149a-113">Si elige un atributo discreto como resultado de predicción, puede especificar un valor de destino o puede dejar en blanco el campo **Valor de predicción** .</span><span class="sxs-lookup"><span data-stu-id="9149a-113">If you choose a discrete attribute as the predictable outcome, you can also specify a target value, or you can leave the **Predict Value** field blank.</span></span> <span data-ttu-id="9149a-114">Si incluye un **valor de predicción**, el gráfico medirá solo la eficacia del modelo al predecir el valor de destino.</span><span class="sxs-lookup"><span data-stu-id="9149a-114">If you include a **Predict Value**, the chart will measure only the model's effectiveness at predicting the target value.</span></span> <span data-ttu-id="9149a-115">Si no especifica un resultado de destino, se mide la precisión del modelo al predecir los resultados.</span><span class="sxs-lookup"><span data-stu-id="9149a-115">If you do not specify a target outcome, the model is measured for its accuracy in predicting all outcomes.</span></span>  
  
-   <span data-ttu-id="9149a-116">Si desea incluir varios modelos y compararlos en un único gráfico de precisión, todos los modelos deben usar la misma columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="9149a-116">If you want to include multiple models and compare them in a single accuracy chart, all models must use the same predictable column.</span></span>  
  
-   <span data-ttu-id="9149a-117">Al crear un informe de validación cruzada, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] analizará de modo automático todos los modelos que tengan el mismo atributo de predicción.</span><span class="sxs-lookup"><span data-stu-id="9149a-117">When you create a cross-validation report, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will automatically analyze all models that have the same predictable attribute.</span></span>  
  
-   <span data-ttu-id="9149a-118">Cuando la opción **Sincronizar valores y columnas de predicción**está seleccionado, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] elige automáticamente las columnas de predicción que tienen los mismos nombres y tipos de datos coincidentes.</span><span class="sxs-lookup"><span data-stu-id="9149a-118">When the option, **Synchronize Prediction columns and Values**, is selected, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] automatically chooses predictable columns that have the same names and matching data types.</span></span> <span data-ttu-id="9149a-119">Si las columnas no cumplen estos criterios, puede desactivar esta opción y elegir manualmente una columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="9149a-119">If your columns do not meet these criteria, you can turn off this option and manually choose a predictable column.</span></span> <span data-ttu-id="9149a-120">Puede que tenga que hacer esto si va a probar el modelo con un conjunto de datos externo que tenga columnas distintas a las del modelo.</span><span class="sxs-lookup"><span data-stu-id="9149a-120">You might need to do this if you are testing the model with an external data set that has different columns than the model.</span></span> <span data-ttu-id="9149a-121">Sin embargo, si elige una columna con el del tipo de datos incorrecto, obtendrá un error o resultados erróneos.</span><span class="sxs-lookup"><span data-stu-id="9149a-121">However, if you choose a column with the wrong the type of data you will either get an error or bad results.</span></span>  
  
### <a name="specify-the-outcome-to-predict"></a><span data-ttu-id="9149a-122">Especifique el resultado de la predicción</span><span class="sxs-lookup"><span data-stu-id="9149a-122">Specify the outcome to predict</span></span>  
  
1.  <span data-ttu-id="9149a-123">Haga doble clic en la estructura de minería de datos para abrirla en el Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="9149a-123">Double-click the mining structure to open it in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="9149a-124">Seleccione la pestaña **Gráfico de precisión de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="9149a-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="9149a-125">Seleccione la pestaña **Selección de entrada** .</span><span class="sxs-lookup"><span data-stu-id="9149a-125">Select the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="9149a-126">En la pestaña **Selección de entrada** , en **Nombre de columna de predicción**, seleccione una columna de predicción para cada modelo que vaya a incluir en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="9149a-126">On the **Input Selection** tab, under **Predictable Column Name**, select a predictable column for each model that you include in the chart.</span></span>  
  
     <span data-ttu-id="9149a-127">Las columnas del modelo de minería de datos que están disponibles en el cuadro **Nombre de columna de predicción** solo son aquellas cuyo tipo de uso se ha establecido en **Predicción** o **Solo predicción**.</span><span class="sxs-lookup"><span data-stu-id="9149a-127">The mining model columns that are available in the **Predictable Column Name** box are only those with the usage type set to **Predict** or **Predict Only**.</span></span>  
  
5.  <span data-ttu-id="9149a-128">Si desea determinar la elevación de un modelo, debe seleccionar un valor específico del resultado para la medición, eligiéndolo en la lista **Valor de predicción** .</span><span class="sxs-lookup"><span data-stu-id="9149a-128">If you want to determine the lift for a model, you must select a specific outcome value to measure, for by choosing from the **Predict Value** list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9149a-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9149a-129">See Also</span></span>  
 <span data-ttu-id="9149a-130">[Elegir y asignar los datos de prueba del modelo](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="9149a-130">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 [<span data-ttu-id="9149a-131">Elegir un tipo de gráfico de precisión y establecer las opciones del gráfico</span><span class="sxs-lookup"><span data-stu-id="9149a-131">Choose an Accuracy Chart Type and Set Chart Options</span></span>](choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  
