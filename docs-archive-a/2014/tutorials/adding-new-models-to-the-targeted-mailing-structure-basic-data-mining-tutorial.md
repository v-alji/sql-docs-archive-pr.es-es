---
title: Agregar nuevos modelos a la estructura de distribución de correo directo (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 512c6888-60f1-46e4-9639-bc448395b8d7
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b83dfc6c9e218eecf3f2abe636b8c24d69d1b507
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747793"
---
# <a name="adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial"></a><span data-ttu-id="66d29-102">Agregar modelos nuevos a la estructura de correo de destino (tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="66d29-102">Adding New Models to the Targeted Mailing Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="66d29-103">En esta tarea, definirá dos modelos adicionales mediante la pestaña **modelos de minería** de datos del diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="66d29-103">In this task, you will define two additional models by using the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="66d29-104">Para crear los modelos, se usarán el algoritmo Bayes naive y el algoritmo de clústeres de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66d29-104">You will use the Microsoft Clustering and Microsoft Naive Bayes algorithms to create the models.</span></span> <span data-ttu-id="66d29-105">Estos dos algoritmos se han seleccionado debido a su capacidad de predecir un valor discreto (por ejemplo, la compra de una bicicleta).</span><span class="sxs-lookup"><span data-stu-id="66d29-105">These two algorithms are selected because of their ability to predict a discrete value (i.e., bike purchase).</span></span> <span data-ttu-id="66d29-106">Para obtener más información sobre estos algoritmos, vea [algoritmo de clústeres de Microsoft](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) y [algoritmo Bayes Naive de Microsoft](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md) .</span><span class="sxs-lookup"><span data-stu-id="66d29-106">For more information about these algorithms, see [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md)</span></span>  
  
### <a name="to-create-a-clustering-mining-model"></a><span data-ttu-id="66d29-107">Para crear un modelo de minería de datos de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="66d29-107">To create a clustering mining model</span></span>  
  
1.  <span data-ttu-id="66d29-108">Cambie a la pestaña **modelos de minería** de datos del diseñador de minería de datos en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="66d29-108">Switch to the **Mining Models** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="66d29-109">Observe que el diseñador muestra dos columnas, una para la estructura de minería de datos y otra para el `TM_Decision_Tree` modelo de minería de datos, que creó en la lección anterior.</span><span class="sxs-lookup"><span data-stu-id="66d29-109">Notice that the designer displays two columns, one for the mining structure and one for the `TM_Decision_Tree` mining model, which you created in the previous lesson.</span></span>  
  
2.  <span data-ttu-id="66d29-110">Haga clic con el botón secundario en la columna **estructura** y seleccione **nuevo modelo de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="66d29-110">Right-click the **Structure** column and select **New Mining Model**.</span></span>  
  
3.  <span data-ttu-id="66d29-111">En el cuadro de diálogo **nuevo modelo de minería de datos** , en **nombre del modelo**, escriba `TM_Clustering` .</span><span class="sxs-lookup"><span data-stu-id="66d29-111">In the **New Mining Model** dialog box, in **Model name**, type `TM_Clustering`.</span></span>  
  
4.  <span data-ttu-id="66d29-112">En **nombre del algoritmo**, seleccione **agrupación en clústeres de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="66d29-112">In **Algorithm name**, select **Microsoft Clustering**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="66d29-113">El nuevo modelo aparece ahora en la pestaña **modelos de minería** de datos del diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="66d29-113">The new model now appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="66d29-114">Este modelo, creado con el [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo de clústeres, agrupa a los clientes con características similares en los clústeres y predice la compra de bicicletas para cada clúster.</span><span class="sxs-lookup"><span data-stu-id="66d29-114">This model, built with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm, groups customers with similar characteristics into clusters and predicts bike buying for each cluster.</span></span> <span data-ttu-id="66d29-115">Aunque puede modificar el uso de las columnas y las propiedades del nuevo modelo, no es necesario realizar ningún cambio en el `TM_Clustering` modelo para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="66d29-115">Although you can modify the column usage and properties for the new model, no changes to the `TM_Clustering` model are necessary for this tutorial.</span></span>  
  
### <a name="to-create-a-naive-bayes-mining-model"></a><span data-ttu-id="66d29-116">Para crear un modelo de minería de datos Bayes naive</span><span class="sxs-lookup"><span data-stu-id="66d29-116">To create a Naive Bayes mining model</span></span>  
  
1.  <span data-ttu-id="66d29-117">En la pestaña **modelos de minería** de datos del diseñador de minería de datos, haga clic con el botón derecho en la columna de **estructura** Clickthe y seleccione **nuevo modelo de minería**de datos.</span><span class="sxs-lookup"><span data-stu-id="66d29-117">In the **Mining Models** tab of Data Mining Designer, right-clickthe **Structure** column, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="66d29-118">En el cuadro de diálogo **nuevo modelo de minería de datos** , en **nombre del modelo**, escriba `TM_NaiveBayes` .</span><span class="sxs-lookup"><span data-stu-id="66d29-118">In the **New Mining Model** dialog box, under **Model name**, type `TM_NaiveBayes`.</span></span>  
  
3.  <span data-ttu-id="66d29-119">En **nombre del algoritmo**, seleccione **Bayes Naive de Microsoft**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="66d29-119">In **Algorithm name**, select **Microsoft Naive Bayes**, then click **OK**.</span></span>  
  
     <span data-ttu-id="66d29-120">Aparece un mensaje que indica que el [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo Bayes Naive de no admite las columnas **Age** y **yearly Income** , que son continuas.</span><span class="sxs-lookup"><span data-stu-id="66d29-120">A message appears stating that the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes algorithm does not support the **Age** and **Yearly Income** columns, which are continuous.</span></span>  
  
4.  <span data-ttu-id="66d29-121">Haga clic en **sí** para confirmar el mensaje y continuar.</span><span class="sxs-lookup"><span data-stu-id="66d29-121">Click **Yes** to acknowledge the message and continue.</span></span>  
  
 <span data-ttu-id="66d29-122">Aparece un nuevo modelo en la pestaña **modelos de minería** de datos del diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="66d29-122">A new model appears in the **Mining Models** tab of Data Mining Designer.</span></span> <span data-ttu-id="66d29-123">Aunque puede modificar el uso de las columnas y las propiedades de todos los modelos de esta pestaña, no es necesario realizar ningún cambio en el `TM_NaiveBayes` modelo para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="66d29-123">Although you can modify the column usage and properties for all the models in this tab, no changes to the `TM_NaiveBayes` model are necessary for this tutorial.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="66d29-124">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="66d29-124">Next Task in Lesson</span></span>  
 [<span data-ttu-id="66d29-125">Procesar modelos en la estructura de distribución de correo directo &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="66d29-125">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="66d29-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66d29-126">See Also</span></span>  
 <span data-ttu-id="66d29-127">[Agregar modelos de minería de datos a una estructura &#40;&#41;de minería de datos Analysis Services](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="66d29-127">[Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="66d29-128">[Diseñador de minería de datos](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="66d29-128">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="66d29-129">Mover objetos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="66d29-129">Moving Data Mining Objects</span></span>](../../2014/analysis-services/data-mining/moving-data-mining-objects.md)  
  
  
