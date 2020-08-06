---
title: 'Lección 6: crear y trabajar con predicciones (tutorial básico de minería de datos) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b213cb58-2c40-4c89-b08b-d3c36a4afad3
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d0a8bfdf83e96622a19ac72490e8602d12afc9df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670706"
---
# <a name="lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="2fa39-102">Lección 6: Crear y trabajar con predicciones (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="2fa39-102">Lesson 6: Creating and Working with Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="2fa39-103">Ha entrenado, probado y explorado los modelos de minería de datos que creó.</span><span class="sxs-lookup"><span data-stu-id="2fa39-103">You have trained, tested, and explored the data mining models you created.</span></span> <span data-ttu-id="2fa39-104">Ahora ya puede usar los modelos para identificar a las personas que es más probable que respondan a la nueva campaña de envío de correo directo.</span><span class="sxs-lookup"><span data-stu-id="2fa39-104">Now you are ready to use the models to identify the people most likely to respond to the new targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="2fa39-105">En esta lección creará una consulta para predecir qué clientes tienen más probabilidad de comprar una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="2fa39-105">In this lesson you will create a query to predict which customers are most likely to purchase a bike.</span></span> <span data-ttu-id="2fa39-106">También recuperará la *probabilidad* de que la predicción sea correcta, por lo que el Departamento de marketing puede decidir si desea decidir si usar o no la predicción.</span><span class="sxs-lookup"><span data-stu-id="2fa39-106">You will also retrieve the *probability* that the prediction is correct, so the marketing department can decide whether to you can decide whether to use the prediction or not.</span></span>  
  
 <span data-ttu-id="2fa39-107">Cuando haya identificado a los clientes con una probabilidad alta de comprar una bicicleta, obtendrá detalles de los casos del modelo de minería de datos para recuperar los nombres y la información de contacto correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2fa39-107">Once you have identified customers with a high probability of purchasing a bike, you will drill through to the details of the cases in the mining model to retrieve names and contact information for these customers.</span></span>  
  
 <span data-ttu-id="2fa39-108">En esta lección se incluyen los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2fa39-108">This lesson contains the following topics:</span></span>  
  
 [<span data-ttu-id="2fa39-109">Crear predicciones &#40;Tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2fa39-109">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="2fa39-110">Usar la obtención de detalles en datos de estructura &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2fa39-110">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="2fa39-111">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="2fa39-111">Next Lesson</span></span>  
 [<span data-ttu-id="2fa39-112">Tutorial intermedio de minería de datos &#40;Analysis Services:&#41;de minería de datos</span><span class="sxs-lookup"><span data-stu-id="2fa39-112">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="2fa39-113">Lección anterior</span><span class="sxs-lookup"><span data-stu-id="2fa39-113">Previous Lesson</span></span>  
 [<span data-ttu-id="2fa39-114">Lección 5: probar los modelos &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2fa39-114">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2fa39-115">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="2fa39-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2fa39-116">Crear predicciones &#40;Tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="2fa39-116">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="2fa39-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fa39-117">See Also</span></span>  
 <span data-ttu-id="2fa39-118">[Contenido del modelo de minería de datos para los modelos de árbol de decisión &#40;&#41;de minería de datos Analysis Services](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="2fa39-118">[Mining Model Content for Decision Tree Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="2fa39-119">Crear una consulta de predicción con el Generador de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="2fa39-119">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
