---
title: Especificar un conjunto de datos de prueba para la estructura (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 75cd508f-b126-418b-848d-3c4c3e6c303f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c1430706a0ec2cd3ddc0eaee18d7001d05fefae1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662420"
---
# <a name="specifying-a-testing-data-set-for-the-structure-basic-data-mining-tutorial"></a><span data-ttu-id="ab966-102">Especificar un conjunto de datos de pruebas para la estructura (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="ab966-102">Specifying a Testing Data Set for the Structure (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="ab966-103">En las pantallas finales del Asistente para minería de datos dividirá los datos en un conjunto de pruebas y en un conjunto de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="ab966-103">In the final few screens of the Data Mining Wizard you will split your data into a testing set and a training set.</span></span> <span data-ttu-id="ab966-104">Después, asignará nombre a la estructura y habilitará la obtención de detalles en el modelo.</span><span class="sxs-lookup"><span data-stu-id="ab966-104">You will then name your structure and enable drillthrough on the model.</span></span>  
  
## <a name="specifying-a-testing-set"></a><span data-ttu-id="ab966-105">Especificar un conjunto de pruebas</span><span class="sxs-lookup"><span data-stu-id="ab966-105">Specifying a Testing Set</span></span>  
 <span data-ttu-id="ab966-106">Al separar los datos en conjuntos de entrenamiento y de pruebas cuando se crea una estructura de minería de datos, es posible evaluar fácilmente la precisión de los modelos de minería de datos que se crean después.</span><span class="sxs-lookup"><span data-stu-id="ab966-106">Separating data into training and testing sets when you create a mining structure makes it possible to easily assess the accuracy of the mining models that you create later.</span></span> <span data-ttu-id="ab966-107">Para obtener más información sobre los conjuntos de pruebas, consulte [conjuntos de datos de entrenamiento y de prueba](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span><span class="sxs-lookup"><span data-stu-id="ab966-107">For more information on testing sets, see [Training and Testing Data Sets](../../2014/analysis-services/data-mining/training-and-testing-data-sets.md).</span></span>  
  
#### <a name="to-specify-the-testing-set"></a><span data-ttu-id="ab966-108">Para especificar el conjunto de pruebas</span><span class="sxs-lookup"><span data-stu-id="ab966-108">To specify the testing set</span></span>  
  
1.  <span data-ttu-id="ab966-109">En la página **crear conjunto de pruebas** , en **porcentaje de datos para pruebas**, deje el valor predeterminado de `30` .</span><span class="sxs-lookup"><span data-stu-id="ab966-109">On the **Create Testing Set** page, for **Percentage of data for testing**, leave the default value of `30`.</span></span>  
  
2.  <span data-ttu-id="ab966-110">**En número máximo de casos en el conjunto de datos de prueba**, escriba `1000` .</span><span class="sxs-lookup"><span data-stu-id="ab966-110">For **Maximum number of cases in testing data set**, type `1000`.</span></span>  
  
3.  <span data-ttu-id="ab966-111">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="ab966-111">Click **Next**.</span></span>  
  
## <a name="specifying-drillthrough"></a><span data-ttu-id="ab966-112">Especificar la obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="ab966-112">Specifying Drillthrough</span></span>  
 <span data-ttu-id="ab966-113">La obtención de detalles puede habilitarse en los modelos y en las estructuras.</span><span class="sxs-lookup"><span data-stu-id="ab966-113">Drillthrough can be enabled on models and on structures.</span></span> <span data-ttu-id="ab966-114">La casilla de este cuadro de diálogo habilita la obtención de detalles en el modelo con nombre.</span><span class="sxs-lookup"><span data-stu-id="ab966-114">The checkbox in this dialog box enables drillthrough on the named model.</span></span> <span data-ttu-id="ab966-115">Una vez procesado el modelo, podrá recuperar información detallada de los datos de entrenamiento usados para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="ab966-115">After the model has been processed,  you will be able to retrieve detailed information from the training data that were used to create the model.</span></span>  
  
 <span data-ttu-id="ab966-116">Si la estructura de minería de datos subyacente también se ha configurado para permitir la obtención de detalles, puede recuperar información detallada tanto de los casos de modelos como de la estructura, incluidas las columnas que no estaban incluidas en el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="ab966-116">If the underlying mining structure has also been configured to allow drillthrough, you can retrieve detailed information from both the model cases and the mining structure, including columns that were not included in the mining model.</span></span> <span data-ttu-id="ab966-117">Para obtener más información, vea [Consultas de obtención de detalles &#40;minería de datos&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="ab966-117">For more information, see [Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md).</span></span>  
  
#### <a name="to-name-the-model-and-structure-and-specify-drillthrough"></a><span data-ttu-id="ab966-118">Para denominar el modelo y la estructura, y especificar la obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="ab966-118">To name the model and structure and specify drillthrough</span></span>  
  
1.  <span data-ttu-id="ab966-119">En la página **finalización del asistente** , en nombre de la **estructura de minería de datos**, escriba `Targeted Mailing` .</span><span class="sxs-lookup"><span data-stu-id="ab966-119">On the **Completing the Wizard** page, in **Mining structure name**, type `Targeted Mailing`.</span></span>  
  
2.  <span data-ttu-id="ab966-120">En **nombre del modelo de minería de datos**, escriba `TM_Decision_Tree` .</span><span class="sxs-lookup"><span data-stu-id="ab966-120">In **Mining model name**, type `TM_Decision_Tree`.</span></span>  
  
3.  <span data-ttu-id="ab966-121">Active la casilla **permitir obtención de detalles** .</span><span class="sxs-lookup"><span data-stu-id="ab966-121">Select the **Allow drill through** check box.</span></span>  
  
4.  <span data-ttu-id="ab966-122">Revise el panel de **vista previa** .</span><span class="sxs-lookup"><span data-stu-id="ab966-122">Review the **Preview** pane.</span></span> <span data-ttu-id="ab966-123">Observe que solo se muestran las columnas seleccionadas como **clave**, **entrada** o **predicción** .</span><span class="sxs-lookup"><span data-stu-id="ab966-123">Notice that only those columns selected as **Key**, **Input** or **Predictable** are shown.</span></span> <span data-ttu-id="ab966-124">Las otras columnas que seleccionó (por ejemplo, AddressLine1) no se usan para generar el modelo, pero estarán disponibles en la estructura subyacente y se pueden consultar una vez procesado e implementado el modelo.</span><span class="sxs-lookup"><span data-stu-id="ab966-124">The other columns you selected (e.g., AddressLine1) are not used for building the model but will be available in the underlying structure, and can be queried after the model is processed and deployed.</span></span>  
  
5.  <span data-ttu-id="ab966-125">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="ab966-125">Click **Finish**.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="ab966-126">Tarea anterior de la lección</span><span class="sxs-lookup"><span data-stu-id="ab966-126">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="ab966-127">Especificar el tipo de datos y el tipo de contenido &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="ab966-127">Specifying the Data Type and Content Type &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/specifying-the-data-type-and-content-type-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="ab966-128">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="ab966-128">Next Lesson</span></span>  
 [<span data-ttu-id="ab966-129">Lección 3: Adición y procesamiento de modelos</span><span class="sxs-lookup"><span data-stu-id="ab966-129">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="see-also"></a><span data-ttu-id="ab966-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab966-130">See Also</span></span>  
 <span data-ttu-id="ab966-131">[Habilitar la obtención de detalles para un modelo de minería de datos](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="ab966-131">[Enable Drillthrough for a Mining Model](../../2014/analysis-services/data-mining/enable-drillthrough-for-a-mining-model.md) </span></span>  
 <span data-ttu-id="ab966-132">[Consultas de obtención de detalles &#40;&#41;de minería de datos](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ab966-132">[Drillthrough Queries &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/drillthrough-queries-data-mining.md) </span></span>  
 [<span data-ttu-id="ab966-133">Especificar los datos de entrenamiento &#40;Asistente para minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="ab966-133">Specify the Training Data &#40;Data Mining Wizard&#41;</span></span>](../../2014/analysis-services/specify-the-training-data-data-mining-wizard.md)  
  
  
