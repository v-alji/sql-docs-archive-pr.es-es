---
title: 'Lección 5: probar los modelos (tutorial básico de minería de datos) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9a7ddcf-2b01-485f-bbb5-62638b303bc6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: fcfd9a9e90d9c6800af4dfd1599bbdd62d9520ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747301"
---
# <a name="lesson-5-testing-models-basic-data-mining-tutorial"></a><span data-ttu-id="140d0-102">Lección 5: Probar los modelos (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="140d0-102">Lesson 5: Testing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="140d0-103">Ahora que ha procesado el modelo utilizando el conjunto de entrenamiento del escenario de distribución de correo directo, probará sus modelos con el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="140d0-103">Now that you have processed the model by using the targeted mailing scenario training set, you will test your models against the testing set.</span></span> <span data-ttu-id="140d0-104">La validación es un paso importante del proceso de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="140d0-104">Validation is an important step in the data mining process.</span></span> <span data-ttu-id="140d0-105">Es importante conocer cómo se comportan con datos reales los modelos de minería de datos de distribución de correo directo antes de implementarlos en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="140d0-105">Knowing how well your targeted mailing mining models perform against real data is important before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="140d0-106">Dado que los datos del conjunto de pruebas ya contienen valores conocidos para la compra de bicicletas, es fácil determinar si las predicciones del modelo son correctas.</span><span class="sxs-lookup"><span data-stu-id="140d0-106">Because the data in the testing set already contains known values for bike buying, it is easy to determine whether the model's predictions are correct.</span></span> <span data-ttu-id="140d0-107">El Departamento de marketing usará el modelo que mejor se adapte [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] a los clientes de su campaña de distribución de correo directo.</span><span class="sxs-lookup"><span data-stu-id="140d0-107">The model that performs the best will be used by the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department to identify the customers for their targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="140d0-108">En esta lección, validará los modelos utilizando varios métodos:</span><span class="sxs-lookup"><span data-stu-id="140d0-108">In this lesson you will validate your models using multiple methods:</span></span>  
  
1.  <span data-ttu-id="140d0-109">Realizará predicciones en el conjunto de pruebas para ver el grado de precisión del modelo en los resultados conocidos.</span><span class="sxs-lookup"><span data-stu-id="140d0-109">You'll make predictions against the testing set to see how accurate the model is on known results.</span></span> <span data-ttu-id="140d0-110">Usará un gráfico de *elevación* para medir su eficacia.</span><span class="sxs-lookup"><span data-stu-id="140d0-110">You'll use a *lift chart* to measure its effectiveness.</span></span>  
  
     [<span data-ttu-id="140d0-111">Probar la exactitud con gráficos de mejora respecto al modelo predictivo &#40;Tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="140d0-111">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
2.  <span data-ttu-id="140d0-112">Probará los modelos en un subconjunto filtrado de los datos.</span><span class="sxs-lookup"><span data-stu-id="140d0-112">You will test your models on a filtered subset of the data.</span></span> <span data-ttu-id="140d0-113">Puede comparar varios modelos en el mismo gráfico de elevación.</span><span class="sxs-lookup"><span data-stu-id="140d0-113">You can compare multiple models in the same lift chart.</span></span>  
  
     [<span data-ttu-id="140d0-114">Probar un modelo filtrado &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="140d0-114">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="140d0-115">Para obtener más información sobre la validación de modelos en general, vea [conceptos de minería de datos](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="140d0-115">For more information about how model validation in general, see [Data Mining Concepts](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="140d0-116">Primera tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="140d0-116">First Task in Lesson</span></span>  
 [<span data-ttu-id="140d0-117">Probar la exactitud con gráficos de mejora respecto al modelo predictivo &#40;Tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="140d0-117">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="140d0-118">Lección anterior</span><span class="sxs-lookup"><span data-stu-id="140d0-118">Previous Lesson</span></span>  
 [<span data-ttu-id="140d0-119">Lección 4: explorar los modelos de correo directo &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="140d0-119">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="140d0-120">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="140d0-120">Next Lesson</span></span>  
 [<span data-ttu-id="140d0-121">Lección 6: Crear y trabajar con predicciones &#40;Tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="140d0-121">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="140d0-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="140d0-122">See Also</span></span>  
 <span data-ttu-id="140d0-123">[Pestaña gráfico de elevación &#40;vista gráfico de precisión de minería de datos&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="140d0-123">[Lift Chart Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span></span>  
 <span data-ttu-id="140d0-124">[Gráfico de elevación &#40;Analysis Services:&#41;de minería de datos](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="140d0-124">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="140d0-125">[Pruebas y validación &#40;&#41;de minería de datos](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="140d0-125">[Testing and Validation &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span></span>  
 <span data-ttu-id="140d0-126">[Pestaña matriz de clasificación &#40;vista gráfico de precisión de minería de datos&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="140d0-126">[Classification Matrix Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span></span>  
 [<span data-ttu-id="140d0-127">Matriz de clasificación &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="140d0-127">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/classification-matrix-analysis-services-data-mining.md)  
  
  
