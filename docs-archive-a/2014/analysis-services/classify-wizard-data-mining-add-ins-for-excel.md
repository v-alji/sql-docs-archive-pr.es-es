---
title: Asistente para clasificar (complementos de minería de datos para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- classification [data mining]
ms.assetid: 409c5076-c4c3-4f09-8f30-d3297df45f13
author: minewiskan
ms.author: owend
ms.openlocfilehash: b82fc98df10ae2e6754a378dacea108f9f3379ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670065"
---
# <a name="classify-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="bae30-102">Asistente para clasificación (Complementos de minería de datos para Excel)</span><span class="sxs-lookup"><span data-stu-id="bae30-102">Classify Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="bae30-103">![Asistente para clasificación, cinta de opciones Minería de datos](media/dmc-classify.gif "Asistente para clasificación, cinta de opciones Minería de datos")</span><span class="sxs-lookup"><span data-stu-id="bae30-103">![Classify wizard in Data Mining ribbon](media/dmc-classify.gif "Classify wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="bae30-104">El Asistente para **clasificar** le ayuda a generar un modelo de clasificación basado en los datos existentes en una tabla de Excel, un intervalo de Excel o un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="bae30-104">The **Classify** wizard helps you build a classification model based on existing data in an Excel table, an Excel range, or an external data source.</span></span>  
  
 <span data-ttu-id="bae30-105">Un modelo de clasificación extrae patrones de los datos que indican similitudes y permiten realizar predicciones basadas en las agrupaciones de valores.</span><span class="sxs-lookup"><span data-stu-id="bae30-105">A classification model extracts patterns in your data that indicate similarities and helps you make predictions based on groupings of values.</span></span> <span data-ttu-id="bae30-106">Por ejemplo, un modelo de clasificación podría utilizarse para predecir el riesgo en función de los patrones de ingresos o gastos.</span><span class="sxs-lookup"><span data-stu-id="bae30-106">For example, a classification model might be used to predict risk based on income or spending patterns.</span></span>  
  
## <a name="using-the-classify-wizard"></a><span data-ttu-id="bae30-107">Usar el Asistente para clasificar</span><span class="sxs-lookup"><span data-stu-id="bae30-107">Using the Classify Wizard</span></span>  
  
1.  <span data-ttu-id="bae30-108">En la cinta de opciones **minería de datos** , haga clic en **clasificar**y, a continuación, en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bae30-108">In the **Data Mining** ribbon, click **Classify**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="bae30-109">En la página **seleccionar datos de origen** , elija los datos que desea analizar.</span><span class="sxs-lookup"><span data-stu-id="bae30-109">In the **Select Source Data** page, choose the data to analyze.</span></span>  
  
     <span data-ttu-id="bae30-110">Este asistente admite varios tipos de datos: tablas de Excel, rangos de Excel y orígenes de datos externos.</span><span class="sxs-lookup"><span data-stu-id="bae30-110">This wizard supports multiple kinds of data: Excel tables, Excel ranges, and external data sources.</span></span> <span data-ttu-id="bae30-111">Con datos externos, puede agregarlos a Excel o elegir un conjunto de tablas o vistas de un origen de datos de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="bae30-111">With external data, you can either add it into Excel, or choose a set of tables or views in an Analysis Services data source.</span></span> <span data-ttu-id="bae30-112">También puede agregar tablas y cambiar columnas para crear orígenes de datos ad hoc.</span><span class="sxs-lookup"><span data-stu-id="bae30-112">You can also add tables and change columns to create ad hoc data sources.</span></span>  
  
3.  <span data-ttu-id="bae30-113">En la página **clasificación** , elija la columna que desea clasificar.</span><span class="sxs-lookup"><span data-stu-id="bae30-113">On the **Classification** page, choose the column that you want to classify.</span></span>  
  
     <span data-ttu-id="bae30-114">Revise las columnas de la lista, **las columnas de entrada**y anule la selección de las columnas que tengan valores únicos y, por tanto, no resulten útiles para crear patrones, como números de identificación, nombres de clientes, etc.</span><span class="sxs-lookup"><span data-stu-id="bae30-114">Review the columns in the list, **Input columns**, and deselect any columns that have unique values and thus aren't useful for creating patterns, such as ID numbers, customer names, and so on.</span></span> <span data-ttu-id="bae30-115">También debe quitar las columnas que básicamente dupliquen la columna clasificable.</span><span class="sxs-lookup"><span data-stu-id="bae30-115">You should also remove columns that essentially duplicate the classifiable column.</span></span>  
  
     <span data-ttu-id="bae30-116">Por ejemplo, si está clasificando la predicción de la categoría de un producto, debe excluir el campo de subcategoría si hay una regla de negocios conocida o la fortaleza de esa regla podría impedir que se detectaran otras correlaciones.</span><span class="sxs-lookup"><span data-stu-id="bae30-116">For example, if you are classifying predicting the category of a product, you should exclude the subcategory field if there is a known business rule, or else the strength of that rule might prevent you from discovering other correlations.</span></span>  
  
4.  <span data-ttu-id="bae30-117">Opcionalmente, haga clic en **parámetros** para cambiar los parámetros del algoritmo y personalizar el comportamiento del modelo de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="bae30-117">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="bae30-118">En la página **dividir datos en conjuntos de entrenamiento y de prueba** , especifique la cantidad de datos que se van a conservar para las pruebas.</span><span class="sxs-lookup"><span data-stu-id="bae30-118">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="bae30-119">El resto se utiliza siempre para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="bae30-119">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="bae30-120">La configuración predeterminada es tener un 30 % de datos de prueba y un 70 % de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="bae30-120">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="bae30-121">En la página **Finalizar** , proporcione un nombre descriptivo para el conjunto de datos y el modelo, y establezca las siguientes opciones que controlan cómo se trabaja con el modelo terminado:</span><span class="sxs-lookup"><span data-stu-id="bae30-121">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="bae30-122">**Examinar modelo**.</span><span class="sxs-lookup"><span data-stu-id="bae30-122">**Browse model**.</span></span> <span data-ttu-id="bae30-123">Cuando se selecciona esta opción, en cuanto el asistente finaliza el procesamiento del modelo, se abre una ventana **examinar** para ayudarle a explorar los resultados.</span><span class="sxs-lookup"><span data-stu-id="bae30-123">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="bae30-124">El contenido del visor depende del tipo de modelo que creó.</span><span class="sxs-lookup"><span data-stu-id="bae30-124">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="bae30-125">Para obtener más información, vea [examinar un modelo de árboles de decisión](browsing-a-decision-trees-model.md) y [examinar un modelo de red neuronal](browsing-a-neural-network-model.md).</span><span class="sxs-lookup"><span data-stu-id="bae30-125">For more information, see [Browsing a Decision Trees Model](browsing-a-decision-trees-model.md) and [Browsing a Neural Network Model](browsing-a-neural-network-model.md).</span></span>  
  
    -   <span data-ttu-id="bae30-126">**Habilitar la obtención de detalles**.</span><span class="sxs-lookup"><span data-stu-id="bae30-126">**Enable drillthrough**.</span></span> <span data-ttu-id="bae30-127">Seleccione esta opción para ver los datos subyacentes desde el modelo terminado.</span><span class="sxs-lookup"><span data-stu-id="bae30-127">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="bae30-128">Esta opción solo está disponible si se crea un modelo de árbol de decisión.</span><span class="sxs-lookup"><span data-stu-id="bae30-128">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="bae30-129">**Usar modelo temporal**.</span><span class="sxs-lookup"><span data-stu-id="bae30-129">**Use temporary model**.</span></span> <span data-ttu-id="bae30-130">Si selecciona esta opción, el modelo no se guardará en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bae30-130">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="bae30-131">Se eliminan los modelos temporales al cerrar Excel.</span><span class="sxs-lookup"><span data-stu-id="bae30-131">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-classification-models"></a><span data-ttu-id="bae30-132">Más información sobre los modelos de clasificación</span><span class="sxs-lookup"><span data-stu-id="bae30-132">More About Classification Models</span></span>  
 <span data-ttu-id="bae30-133">En el cuadro de diálogo **parámetros de algoritmo** , también puede elegir el método de clasificación entre estos algoritmos que se proporcionan en Analysis Services:</span><span class="sxs-lookup"><span data-stu-id="bae30-133">In the **Algorithm Parameters** dialog box, you can also choose the classification method from among these algorithms provided in Analysis Services:</span></span>  
  
-   <span data-ttu-id="bae30-134">Árbol de decisión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bae30-134">Microsoft Decision Tree</span></span>  
  
-   <span data-ttu-id="bae30-135">Regresión logística de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bae30-135">Microsoft Logistic Regression</span></span>  
  
-   <span data-ttu-id="bae30-136">Bayes naive de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bae30-136">Microsoft Naïve Bayes</span></span>  
  
-   <span data-ttu-id="bae30-137">Red neuronal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bae30-137">Microsoft Neural Network</span></span>  
  
 <span data-ttu-id="bae30-138">Aunque los algoritmos podrían producir resultados similares, analizan los datos de forma diferente, por lo que recomendamos probar varios y comparar los resultados.</span><span class="sxs-lookup"><span data-stu-id="bae30-138">Although the algorithms might yield similar results, they analyze the data differently, so we recommend trying several algorithms and comparing the results.</span></span> <span data-ttu-id="bae30-139">El método predeterminado es Árboles de decisión de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bae30-139">The default method is Microsoft Decision Trees.</span></span>  
  
 <span data-ttu-id="bae30-140">En la lista de **parámetros** , puede cambiar las opciones avanzadas, que dependen del tipo de algoritmo que elija.</span><span class="sxs-lookup"><span data-stu-id="bae30-140">In the **Parameters** list, you can change advanced options, which depend on the type of algorithm you choose.</span></span> <span data-ttu-id="bae30-141">Los parámetros de cada algoritmo se describen con más detalle en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bae30-141">The parameters for each algorithm are described in more detail in SQL Server Books Online.</span></span>  
  
 [<span data-ttu-id="bae30-142">Referencia técnica del algoritmo de árboles de decisión de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bae30-142">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="bae30-143">Referencia técnica del algoritmo de regresión logística de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bae30-143">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="bae30-144">Referencia técnica del algoritmo Bayes naive de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bae30-144">Microsoft Naive Bayes Algorithm Technical Reference</span></span>](data-mining/microsoft-naive-bayes-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="bae30-145">Referencia técnica del algoritmo de red neuronal de Microsoft</span><span class="sxs-lookup"><span data-stu-id="bae30-145">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="bae30-146">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bae30-146">Requirements</span></span>  
 <span data-ttu-id="bae30-147">Para usar el Asistente para **clasificar** , debe estar conectado a una [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] base de datos de.</span><span class="sxs-lookup"><span data-stu-id="bae30-147">To use the **Classify** wizard, you must be connected to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="bae30-148">Para obtener información sobre cómo crear una conexión, vea [conectarse a los datos de origen &#40;cliente de minería de datos para Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="bae30-148">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae30-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bae30-149">See Also</span></span>  
 [<span data-ttu-id="bae30-150">Crear un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="bae30-150">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
