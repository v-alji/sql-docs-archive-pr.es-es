---
title: Agregar un modelo de regresión logística a la estructura del centro de llamadas (tutorial intermedio de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 97abb77a-346c-44fa-8959-688dee1af6a8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7d0100313d1ea5a1af5f729249bc2d743a730222
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747799"
---
# <a name="adding-a-logistic-regression-model-to-the-call-center-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="da48e-102">Agregar un modelo de regresión logística a la estructura de centro de llamadas (Tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="da48e-102">Adding a Logistic Regression Model to the Call Center Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="da48e-103">Además de analizar los factores que pueden influir en las operaciones del centro de llamadas, se le pidió que proporcionara recomendaciones concretas sobre la manera en que el personal puede mejorar la calidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="da48e-103">In addition to analyzing the factors that might affect call center operations, you were also asked to provide some specific recommendations on how the staff can improve service quality.</span></span> <span data-ttu-id="da48e-104">En esta tarea usará la misma estructura de minería de datos con la que creó el modelo de exploración y agregará un modelo de minería de datos que después se usará para crear predicciones.</span><span class="sxs-lookup"><span data-stu-id="da48e-104">In this task, you will use the same mining structure that you used to build the exploratory model and add a mining model that will be used for creating predictions.</span></span>  
  
 <span data-ttu-id="da48e-105">En [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], un modelo de regresión logística se basa en el algoritmo de redes neuronales, lo que ofrece la misma flexibilidad y eficacia que un modelo de red neuronal.</span><span class="sxs-lookup"><span data-stu-id="da48e-105">In [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], a logistic regression model is based on the neural networks algorithm, and therefore provides the same flexibility and power as a neural network model.</span></span> <span data-ttu-id="da48e-106">Sin embargo, la regresión logística es especialmente adecuada para predecir resultados binarios.</span><span class="sxs-lookup"><span data-stu-id="da48e-106">However, logistic regression is particularly well-suited for predicting binary outcomes.</span></span>  
  
 <span data-ttu-id="da48e-107">En este escenario, usará la misma estructura de minería de datos que utilizó para el modelo de red neuronal.</span><span class="sxs-lookup"><span data-stu-id="da48e-107">For this scenario, you will use the same mining structure that you used for the neural network model.</span></span> <span data-ttu-id="da48e-108">Sin embargo, personalizará el nuevo modelo para abordar las cuestiones empresariales.</span><span class="sxs-lookup"><span data-stu-id="da48e-108">However, you will customize the new model to target your business questions.</span></span> <span data-ttu-id="da48e-109">Le interesa la mejora de la calidad de servicio y determinar cuántos operadores experimentados necesita; para ello, configurará el modelo para predecir esos valores.</span><span class="sxs-lookup"><span data-stu-id="da48e-109">You are interested in improving service quality and determining how many experienced operators you need, so you will set up your model to predict those values.</span></span>  
  
 <span data-ttu-id="da48e-110">Para asegurarse de que todos los modelos basados en los datos del centro de llamadas se parecen lo más posible, usará el mismo valor de inicialización que antes.</span><span class="sxs-lookup"><span data-stu-id="da48e-110">To ensure that all the models based on the call center data are as similar as possible, you will use the same seed value as before.</span></span> <span data-ttu-id="da48e-111">Al establecer el parámetro de inicialización se garantiza que el modelo procesa los datos a partir del mismo punto inicial, y se minimizan las variaciones causadas por las anomalías en los datos.</span><span class="sxs-lookup"><span data-stu-id="da48e-111">Setting the seed parameter ensures that the model processes the data from the same starting point, and minimizes variations caused by artifacts in the data.</span></span>  
  
### <a name="to-add-a-new-mining-model-to-the-call-center-mining-structure"></a><span data-ttu-id="da48e-112">Para agregar un nuevo modelo de minería de datos a la estructura de minería de datos del centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="da48e-112">To add a new mining model to the call center mining structure</span></span>  
  
1.  <span data-ttu-id="da48e-113">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , en explorador de soluciones, haga clic con el botón secundario en la estructura de minería de datos **Call Center discretizan**y seleccione **abrir diseñador**.</span><span class="sxs-lookup"><span data-stu-id="da48e-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, right-click the mining structure, **Call Center Binned**, and select **Open Designer**.</span></span>  
  
2.  <span data-ttu-id="da48e-114">En el diseñador de minería de datos, haga clic en la pestaña **modelos de minería** de datos.</span><span class="sxs-lookup"><span data-stu-id="da48e-114">In Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="da48e-115">Haga clic en **crear un modelo de minería de datos relacionado**.</span><span class="sxs-lookup"><span data-stu-id="da48e-115">Click **Create a related mining model**.</span></span>  
  
4.  <span data-ttu-id="da48e-116">En el cuadro de diálogo **nuevo modelo de minería de datos** , en **nombre del modelo**, escriba `Call Center - LR` .</span><span class="sxs-lookup"><span data-stu-id="da48e-116">In the **New Mining Model** dialog box, for **Model name**, type `Call Center - LR`.</span></span>  <span data-ttu-id="da48e-117">En **nombre del algoritmo**, seleccione **regresión logística de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="da48e-117">For **Algorithm name**, select **Microsoft Logistic Regression**.</span></span>  
  
5.  <span data-ttu-id="da48e-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="da48e-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="da48e-119">El nuevo modelo de minería de datos se muestra en la pestaña **modelos de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="da48e-119">The new mining model is displayed in the **Mining Models** tab.</span></span>  
  
### <a name="to-customize-the-logistic-regression-model"></a><span data-ttu-id="da48e-120">Para personalizar el modelo de regresión logística</span><span class="sxs-lookup"><span data-stu-id="da48e-120">To customize the logistic regression model</span></span>  
  
1.  <span data-ttu-id="da48e-121">En la columna del nuevo modelo de minería de datos, `Call Center - LR` deje Fact CALLCENTER ID como la clave.</span><span class="sxs-lookup"><span data-stu-id="da48e-121">In the column for the new mining model, `Call Center - LR`, leave Fact CallCenter ID as the key.</span></span>  
  
2.  <span data-ttu-id="da48e-122">Cambie el valor de ServiceGrade y el nivel dos operadores a **PREDICT**.</span><span class="sxs-lookup"><span data-stu-id="da48e-122">Change the value of ServiceGrade and Level Two Operators to **Predict**.</span></span>  
  
     <span data-ttu-id="da48e-123">Ambas columnas se usarán como entrada y para la predicción.</span><span class="sxs-lookup"><span data-stu-id="da48e-123">These columns will be used both as input and for prediction.</span></span> <span data-ttu-id="da48e-124">Básicamente, crea dos modelos independientes en los mismos datos: uno que predice el número de operadores y otro que predice la calificación del servicio.</span><span class="sxs-lookup"><span data-stu-id="da48e-124">In essence, you are creating two separate models on the same data: one that predicts the number of operators, and one that predicts the service grade.</span></span>  
  
3.  <span data-ttu-id="da48e-125">Cambie todas las demás columnas a **Input**.</span><span class="sxs-lookup"><span data-stu-id="da48e-125">Change all other columns to **Input**.</span></span>  
  
### <a name="to-specify-the-seed-and-process-the-models"></a><span data-ttu-id="da48e-126">Para especificar el valor de inicialización y procesar los modelos</span><span class="sxs-lookup"><span data-stu-id="da48e-126">To specify the seed and process the models</span></span>  
  
1.  <span data-ttu-id="da48e-127">En la pestaña **modelo de minería de datos** , haga clic con el botón secundario en la columna del modelo denominado Call Center-LR y seleccione **establecer parámetros de algoritmo**.</span><span class="sxs-lookup"><span data-stu-id="da48e-127">In the **Mining Model** tab, right-click the column for the model named Call Center - LR, and select **Set Algorithm Parameters**.</span></span>  
  
2.  <span data-ttu-id="da48e-128">En la fila del parámetro HOLDOUT_SEED, haga clic en la celda vacía situada debajo de **valor**y escriba `1` .</span><span class="sxs-lookup"><span data-stu-id="da48e-128">In the row for the HOLDOUT_SEED parameter, click the empty cell under **Value**, and type `1`.</span></span> <span data-ttu-id="da48e-129">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="da48e-129">Click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="da48e-130">El valor de inicialización que elija no es importante siempre y cuando use el mismo para todos los modelos relacionados.</span><span class="sxs-lookup"><span data-stu-id="da48e-130">The value that you choose as the seed does not matter, as long as you use the same seed for all related models.</span></span>  
  
3.  <span data-ttu-id="da48e-131">En el menú **modelos de minería de datos** , seleccione **procesar estructura de minería de datos y todos los modelos**.</span><span class="sxs-lookup"><span data-stu-id="da48e-131">In the **Mining Models** menu, select **Process Mining Structure and All Models**.</span></span> <span data-ttu-id="da48e-132">Haga clic en **sí** para implementar el proyecto de minería de datos actualizado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="da48e-132">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
4.  <span data-ttu-id="da48e-133">En el cuadro de diálogo **procesar modelo de minería de datos** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="da48e-133">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
5.  <span data-ttu-id="da48e-134">Haga clic en **cerrar** para cerrar el cuadro de diálogo **progreso del proceso** y, a continuación, haga clic de nuevo en **cerrar** en el cuadro de diálogo **procesar modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="da48e-134">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="da48e-135">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="da48e-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="da48e-136">Crear predicciones para los modelos del centro de llamadas &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="da48e-136">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="da48e-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da48e-137">See Also</span></span>  
 [<span data-ttu-id="da48e-138">Requisitos y consideraciones de procesamiento &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="da48e-138">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
