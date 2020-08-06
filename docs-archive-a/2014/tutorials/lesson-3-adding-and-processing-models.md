---
title: 'Lección 3: agregar y procesar modelos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: cc29927a-c368-4b8a-bbd0-af89a9f54dc9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 5da034089d8bbe7f1a967258d195a56ddbf13c03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663213"
---
# <a name="lesson-3-adding-and-processing-models"></a><span data-ttu-id="7da16-102">Lección 3: Adición y procesamiento de modelos</span><span class="sxs-lookup"><span data-stu-id="7da16-102">Lesson 3: Adding and Processing Models</span></span>
  <span data-ttu-id="7da16-103">La estructura de minería de datos que creó en la lección anterior contiene un modelo de minería de datos individual que se basa en el algoritmo de árboles de decisión de [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7da16-103">The mining structure that you created in the previous lesson contains a single mining model that is based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span> <span data-ttu-id="7da16-104">Puede usar este modelo para identificar clientes para la campaña de envío de correo directo.</span><span class="sxs-lookup"><span data-stu-id="7da16-104">You can use this model to identify customers for the targeted mailing campaign.</span></span> <span data-ttu-id="7da16-105">Sin embargo, para asegurarse de que el análisis es detallado, se suelen crear modelos relacionados usando algoritmos diferentes y comparar sus resultados.</span><span class="sxs-lookup"><span data-stu-id="7da16-105">However, to ensure that your analysis is thorough, it is a common practice to create related models using different algorithms and compare their results.</span></span> <span data-ttu-id="7da16-106">De esta manera, puede obtener diferentes puntos de vista.</span><span class="sxs-lookup"><span data-stu-id="7da16-106">That way you can get different insights as well.</span></span> <span data-ttu-id="7da16-107">Por consiguiente, creará dos modelos adicionales y luego los procesará e implementará.</span><span class="sxs-lookup"><span data-stu-id="7da16-107">Therefore, you will create two additional models, then process and deploy the models.</span></span>  
  
 <span data-ttu-id="7da16-108">En esta lección, creará un conjunto de modelos de minería de datos que sugerirá los clientes que tienen una mayor probabilidad de serlo entre una lista de clientes potenciales.</span><span class="sxs-lookup"><span data-stu-id="7da16-108">In this lesson, you will create a set of mining models that will suggest the most likely customers from a list of potential customers.</span></span>  
  
 <span data-ttu-id="7da16-109">Para completar las tareas de esta lección, usará el algoritmo de [clústeres de Microsoft](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) y el [algoritmo Bayes Naive de Microsoft](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="7da16-109">To complete the tasks in this lesson, you will use the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md) and the [Microsoft Naive Bayes Algorithm](../../2014/analysis-services/data-mining/microsoft-naive-bayes-algorithm.md).</span></span>  
  
 <span data-ttu-id="7da16-110">Esta lección contiene las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="7da16-110">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="7da16-111">Agregar nuevos modelos a la estructura de distribución de correo directo &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7da16-111">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="7da16-112">Procesar modelos en la estructura de distribución de correo directo &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7da16-112">Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="7da16-113">Primera tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="7da16-113">First Task in Lesson</span></span>  
 [<span data-ttu-id="7da16-114">Agregar nuevos modelos a la estructura de distribución de correo directo &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7da16-114">Adding New Models to the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-new-models-to-the-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="7da16-115">Lección anterior</span><span class="sxs-lookup"><span data-stu-id="7da16-115">Previous Lesson</span></span>  
 [<span data-ttu-id="7da16-116">Lección 2: crear una estructura de distribución de correo directo &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7da16-116">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="7da16-117">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="7da16-117">Next Lesson</span></span>  
 [<span data-ttu-id="7da16-118">Lección 4: explorar los modelos de correo directo &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7da16-118">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="7da16-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7da16-119">See Also</span></span>  
 [<span data-ttu-id="7da16-120">Agregar modelos de minería de datos a una estructura &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="7da16-120">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/add-mining-models-to-a-structure-analysis-services-data-mining.md)  
  
  
