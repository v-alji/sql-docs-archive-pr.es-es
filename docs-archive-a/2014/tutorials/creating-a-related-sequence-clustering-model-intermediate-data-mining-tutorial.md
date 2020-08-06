---
title: Crear un modelo de agrupación en clústeres de secuencia relacionado (tutorial intermedio de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1fb4f5bc-1756-45ca-9cd7-411a8c5992a9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d015ed8a9887cb6164020806bf4136f58629ad11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747325"
---
# <a name="creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="64cb3-102">Crear un modelo de agrupación en clústeres de secuencia relacionado (tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="64cb3-102">Creating a Related Sequence Clustering Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="64cb3-103">En el modelo de agrupación en clústeres de secuencia aprendió que otros atributos como Region o Income influyen considerablemente en los modelos; por tanto, para ampliar sus conocimientos sobre las secuencias, creará un modelo de agrupación en clústeres de secuencia relacionado y quitará los atributos relacionados con los datos demográficos de los clientes.</span><span class="sxs-lookup"><span data-stu-id="64cb3-103">Through your exploration of the sequence clustering model, you learned that other attributes such as Region or Income have a strong effect on the models; therefore, to understand the sequences better, you will create a related sequence clustering model and remove the attributes related to customer demographics.</span></span>  
  
 <span data-ttu-id="64cb3-104">En esta tarea, creará una copia del modelo de agrupación en clústeres de secuencia de región y, a continuación, quitará del modelo todas las columnas que no estén relacionadas directamente con las secuencias.</span><span class="sxs-lookup"><span data-stu-id="64cb3-104">In this task, you will create a copy of the regional sequence clustering model, and then remove from the model any columns that are not directly related to the sequences.</span></span>  
  
 <span data-ttu-id="64cb3-105">El nuevo modelo contendrá las mismas columnas que el modelo de minería de datos en el que se basa.</span><span class="sxs-lookup"><span data-stu-id="64cb3-105">The new model will contain all the same columns as the mining model on which it is based.</span></span> <span data-ttu-id="64cb3-106">Sin embargo, no necesita quitar las columnas de la estructura de minería de datos; solo tendrá que especificar que el nuevo modelo de minería omitirá las columnas.</span><span class="sxs-lookup"><span data-stu-id="64cb3-106">However, you do not need to remove the columns from the mining structure, only specify that the new mining model ignore the columns.</span></span>  
  
### <a name="to-make-a-copy-of-the-sequence-clustering-model"></a><span data-ttu-id="64cb3-107">Para realizar una copia del modelo de agrupación en clústeres de secuencia</span><span class="sxs-lookup"><span data-stu-id="64cb3-107">To make a copy of the sequence clustering model</span></span>  
  
1.  <span data-ttu-id="64cb3-108">En [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , en el diseñador de minería de datos, haga clic en la pestaña **modelos de minería** de datos.</span><span class="sxs-lookup"><span data-stu-id="64cb3-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in the Data Mining Designer, click the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="64cb3-109">Haga clic con el botón secundario en el modelo que desea copiar y seleccione **nuevo modelo de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="64cb3-109">Right-click the model you want to copy, and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="64cb3-110">En el cuadro de diálogo **nuevo modelo de minería de datos** , escriba un nombre de modelo y seleccione Microsoft `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="64cb3-110">In the **New Mining Model** dialog box, type a model name, and select Microsoft `Sequence Clustering`.</span></span>  
  
     <span data-ttu-id="64cb3-111">Para este tutorial, escriba el nombre `Sequence Clustering` .</span><span class="sxs-lookup"><span data-stu-id="64cb3-111">For this tutorial, type the name `Sequence Clustering`.</span></span>  
  
4.  <span data-ttu-id="64cb3-112">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="64cb3-112">Click **OK**.</span></span>  
  
### <a name="to-remove-columns-from-the-mining-model"></a><span data-ttu-id="64cb3-113">Para quitar columnas del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="64cb3-113">To remove columns from the mining model</span></span>  
  
1.  <span data-ttu-id="64cb3-114">En la pestaña **modelo de minería de datos** , en la columna del nuevo modelo denominado agrupación en clústeres de secuencia, haga clic en la fila del atributo de grupo de **ingresos** y seleccione **omitir**.</span><span class="sxs-lookup"><span data-stu-id="64cb3-114">In the **Mining Model** tab, in the column for the new model named Sequence Clustering, click the row for the **Income Group** attribute, and select **Ignore**.</span></span>  
  
2.  <span data-ttu-id="64cb3-115">Repita este paso para la **región**de atributo.</span><span class="sxs-lookup"><span data-stu-id="64cb3-115">Repeat this step for the attribute **Region**.</span></span>  
  
3.  <span data-ttu-id="64cb3-116">Haga clic en el signo más situado junto al nombre de la tabla, **v Assoc SEQ line items**, para expandir la tabla y ver las columnas de la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="64cb3-116">Click the plus sign next to the table name, **v Assoc Seq Line Items**, to expand the table and view the columns from the nested table.</span></span>  
  
     <span data-ttu-id="64cb3-117">El nuevo modelo debe contener solamente las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="64cb3-117">The new model should have only the following columns:</span></span>  
  
     <span data-ttu-id="64cb3-118">**Orden NumberKey**</span><span class="sxs-lookup"><span data-stu-id="64cb3-118">**Order NumberKey**</span></span>  
  
     <span data-ttu-id="64cb3-119">**Clave de número de línea**</span><span class="sxs-lookup"><span data-stu-id="64cb3-119">**Line Number Key**</span></span>  
  
     <span data-ttu-id="64cb3-120">**Predicción de modelo**</span><span class="sxs-lookup"><span data-stu-id="64cb3-120">**Model Predict**</span></span>  
  
### <a name="to-process-the-new-sequence-clustering-model"></a><span data-ttu-id="64cb3-121">Para procesar el nuevo modelo de agrupación en clústeres de secuencia</span><span class="sxs-lookup"><span data-stu-id="64cb3-121">To process the new sequence clustering model</span></span>  
  
1.  <span data-ttu-id="64cb3-122">En la pestaña **modelo de minería de datos** , haga clic con el botón secundario en el nuevo modelo denominado `Sequence Clustering` y seleccione **procesar modelo**.</span><span class="sxs-lookup"><span data-stu-id="64cb3-122">In the **Mining Model** tab, right-click the new model named `Sequence Clustering`, and select **Process Model**.</span></span>  
  
     <span data-ttu-id="64cb3-123">Como el nuevo modelo de minería de datos simplificado se basa en una estructura que ya se ha procesado, no es necesario volver a procesar la estructura.</span><span class="sxs-lookup"><span data-stu-id="64cb3-123">Because the new simplified mining model is based on a structure that has already been processed, you do not need to reprocess the structure.</span></span> <span data-ttu-id="64cb3-124">Simplemente puede procesar el nuevo modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="64cb3-124">You can process just the new mining model.</span></span>  
  
2.  <span data-ttu-id="64cb3-125">Haga clic en **sí** para implementar el proyecto de minería de datos actualizado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="64cb3-125">Click **Yes** to deploy the updated data mining project to the server.</span></span>  
  
3.  <span data-ttu-id="64cb3-126">En el cuadro de diálogo **procesar modelo de minería de datos** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="64cb3-126">In the **Process Mining Model** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="64cb3-127">Haga clic en **cerrar** para cerrar el cuadro de diálogo **progreso del proceso** y, a continuación, haga clic de nuevo en **cerrar** en el cuadro de diálogo **procesar modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="64cb3-127">Click **Close** to close the **Process Progress** dialog box, and then click **Close** again in the **Process Mining Model** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="64cb3-128">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="64cb3-128">Next Task in Lesson</span></span>  
 [<span data-ttu-id="64cb3-129">Crear predicciones en un modelo de agrupación en clústeres de secuencia &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="64cb3-129">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="64cb3-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64cb3-130">See Also</span></span>  
 [<span data-ttu-id="64cb3-131">Requisitos y consideraciones de procesamiento &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="64cb3-131">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
