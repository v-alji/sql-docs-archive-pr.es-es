---
title: Procesar modelos en la estructura de distribución de correo directo (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9d8233bb-117e-4563-9302-8a5a8ad1fae2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b8fb7b9f601f351520c3f611cc3c520614ed8ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745580"
---
# <a name="processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="4d267-102">Procesar los modelos de la estructura de distribución de correo directo (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="4d267-102">Processing Models in the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="4d267-103">Para poder examinar o trabajar con los modelos de minería de datos que ha creado, se debe implementar el proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y procesar la estructura y los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="4d267-103">Before you can browse or work with the mining models that you have created, you must deploy the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span>  
  
-   <span data-ttu-id="4d267-104">La *implementación* envía el proyecto a un servidor y crea los objetos en ese proyecto en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4d267-104">*Deploying* sends the project to a server and creates any objects in that project on the server.</span></span>  
  
-   <span data-ttu-id="4d267-105">El *procesamiento* rellena los [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objetos con datos de orígenes de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="4d267-105">*Processing* populates [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects with data from relational data sources.</span></span>  
  
 <span data-ttu-id="4d267-106">Los modelos no se pueden utilizar hasta que se hayan implementado y procesado.</span><span class="sxs-lookup"><span data-stu-id="4d267-106">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="4d267-107">Además, cuando se realiza cualquier cambio en el modelo, como agregar datos nuevos, se debe volver a implementar y procesar los modelos.</span><span class="sxs-lookup"><span data-stu-id="4d267-107">Also, when you make any changes to the model, such as adding new data, you must redeploy and reprocess the models.</span></span>  
  
## <a name="ensuring-consistency-with-holdoutseed"></a><span data-ttu-id="4d267-108">Asegurarse de la coherencia con HoldoutSeed</span><span class="sxs-lookup"><span data-stu-id="4d267-108">Ensuring Consistency with HoldoutSeed</span></span>  
 <span data-ttu-id="4d267-109">Al implementar un proyecto y procesar la estructura y los modelos, a las filas individuales de la estructura de datos se les asigna el conjunto de entrenamiento o el conjunto de pruebas según un valor de inicialización numérico.</span><span class="sxs-lookup"><span data-stu-id="4d267-109">When you deploy a project and process the structure and models, individual rows in your data structure are assigned to either the training set or testing set based on a numerical seed value.</span></span> <span data-ttu-id="4d267-110">De forma predeterminada, el valor de inicialización numérico se calcula en función de los atributos de la estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="4d267-110">By default, the numerical seed value is computed based on attributes of the data structure.</span></span> <span data-ttu-id="4d267-111">Sin embargo, si alguna vez cambia algunos aspectos del modelo, el valor de inicialización cambiaría, lo que produciría resultados ligeramente diferentes.</span><span class="sxs-lookup"><span data-stu-id="4d267-111">However, if you ever change some aspects of your model, the seed value would change, leading to subtly different results.</span></span> <span data-ttu-id="4d267-112">Por lo tanto, para asegurarse de que los resultados son los mismos que los descritos aquí, asignaremos arbitrariamente una *inicialización de exclusión* fija de `12` .</span><span class="sxs-lookup"><span data-stu-id="4d267-112">Therefore, in order to ensure that your results are the same as described here, we will arbitrarily assign a fixed *holdout seed* of `12`.</span></span> <span data-ttu-id="4d267-113">El valor de inicialización de exclusión se utiliza para inicializar el algoritmo de muestreo y garantiza que los datos se reparten aproximadamente de la misma manera para todas las estructuras de minería de datos y sus modelos.</span><span class="sxs-lookup"><span data-stu-id="4d267-113">The holdout seed is used to initialize the sampling algorithm, and ensures that the data is partitioned in roughly the same way for all mining structures and their models.</span></span>  
  
 <span data-ttu-id="4d267-114">Este valor no afecta al número de casos del conjunto de entrenamiento; simplemente garantiza que se usará el mismo método de partición siempre que se genere el modelo.</span><span class="sxs-lookup"><span data-stu-id="4d267-114">This value does not affect the number of cases in the training set; it simply ensures that the same partitioning method will be used each time you build the model.</span></span>  
  
 <span data-ttu-id="4d267-115">Para obtener más información sobre los valores de inicialización de exclusión, vea [conjuntos de datos de entrenamiento y de prueba](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="4d267-115">For more information on holdout seed, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-set-the-holdout-seed"></a><span data-ttu-id="4d267-116">Para establecer el valor de inicialización de exclusión</span><span class="sxs-lookup"><span data-stu-id="4d267-116">To set the Holdout Seed</span></span>  
  
1.  <span data-ttu-id="4d267-117">Haga clic en la pestaña **estructura de minería** de datos o en la pestaña **modelos de minería** de datos del diseñador de minería de datos en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d267-117">Click on the **Mining Structure** tab or the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="4d267-118">**MiningStructure de correo** directo se muestra en el panel de **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="4d267-118">**Targeted Mailing MiningStructure** displays in the **Properties** pane.</span></span>  
  
2.  <span data-ttu-id="4d267-119">Para asegurarse de que el panel **propiedades** está abierto, presione **F4**.</span><span class="sxs-lookup"><span data-stu-id="4d267-119">Ensure that the **Properties** pane is open by pressing **F4**.</span></span>  
  
3.  <span data-ttu-id="4d267-120">Asegúrese de que **CacheMode** está establecido en **KeepTrainingCases**.</span><span class="sxs-lookup"><span data-stu-id="4d267-120">Ensure that **CacheMode** is set to **KeepTrainingCases**.</span></span>  
  
4.  <span data-ttu-id="4d267-121">Escriba `12` para **HoldoutSeed**.</span><span class="sxs-lookup"><span data-stu-id="4d267-121">Enter `12` for **HoldoutSeed**.</span></span>  
  
## <a name="deploying-and-processing-the-models"></a><span data-ttu-id="4d267-122">Implementar y procesar los modelos</span><span class="sxs-lookup"><span data-stu-id="4d267-122">Deploying and Processing the Models</span></span>  
 <span data-ttu-id="4d267-123">En el diseñador de minería de datos, puede decidir qué objetos se van a procesar, dependiendo del ámbito de los cambios que haya realizado en el modelo o en los datos subyacentes:</span><span class="sxs-lookup"><span data-stu-id="4d267-123">In Data Mining Designer, you can decide which objects to process, depending on the scope of changes you've made to your model or the underlying data:</span></span>  
  
 <span data-ttu-id="4d267-124">En esta tarea, puesto que los datos y los modelos son nuevos, procesará la estructura y todos los modelos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="4d267-124">For this task, because the data and the models are new, you will process the structure and all the models at the same time.</span></span>  
  
#### <a name="to-deploy-the-project-and-process-all-the-mining-models"></a><span data-ttu-id="4d267-125">Para implementar el proyecto y procesar todos los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="4d267-125">To deploy the project and process all the mining models</span></span>  
  
1.  <span data-ttu-id="4d267-126">En el menú **modelo de minería de datos** , seleccione **procesar estructura de minería de datos y todos los modelos**.</span><span class="sxs-lookup"><span data-stu-id="4d267-126">In the **Mining Model** menu, select **Process Mining Structure and All Models**.</span></span>  
  
     <span data-ttu-id="4d267-127">Si ha realizado cambios en la estructura, se le pedirá que genere e implemente el proyecto antes de procesar los modelos.</span><span class="sxs-lookup"><span data-stu-id="4d267-127">If you made changes to the structure, you will be prompted to build and deploy the project before processing the models.</span></span> <span data-ttu-id="4d267-128">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="4d267-128">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="4d267-129">Haga clic en **Ejecutar** en el cuadro de diálogo **procesando el correo electrónico de estructura de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="4d267-129">Click **Run** in the **Processing Mining Structure - Targeted Mailing** dialog box.</span></span>  
  
     <span data-ttu-id="4d267-130">Se abre el cuadro de diálogo **Progreso del proceso** para mostrar los detalles del procesamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="4d267-130">The **Process Progress** dialog box opens to display the details of model processing.</span></span> <span data-ttu-id="4d267-131">El procesamiento del modelo podría tardar algún tiempo, según el equipo.</span><span class="sxs-lookup"><span data-stu-id="4d267-131">Model processing might take some time, depending on your computer.</span></span>  
  
3.  <span data-ttu-id="4d267-132">Haga clic en **Cerrar** en el cuadro de diálogo **Progreso del proceso** cuando el procesamiento de los modelos se haya completado.</span><span class="sxs-lookup"><span data-stu-id="4d267-132">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="4d267-133">Haga clic en **cerrar** en el cuadro de diálogo **procesando estructura de minería \<structure> de datos** .</span><span class="sxs-lookup"><span data-stu-id="4d267-133">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="4d267-134">Tarea anterior de la lección</span><span class="sxs-lookup"><span data-stu-id="4d267-134">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="4d267-135">Agregar nuevos modelos a la estructura de distribución de correo directo &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="4d267-135">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="4d267-136">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="4d267-136">Next Lesson</span></span>  
 [<span data-ttu-id="4d267-137">Lección 4: explorar los modelos de correo directo &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="4d267-137">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="4d267-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d267-138">See Also</span></span>  
 [<span data-ttu-id="4d267-139">Requisitos y consideraciones de procesamiento &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="4d267-139">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
