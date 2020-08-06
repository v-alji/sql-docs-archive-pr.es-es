---
title: Ver o cambiar los parámetros del algoritmo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- algorithms [data mining]
- mining models [Analysis Services], algorithms
ms.assetid: 151b899b-c27a-4a09-bcf5-5c9f0ec24168
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30719cd50e0c473cf2aab5d9689d27dff4f26343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671814"
---
# <a name="view-or-change-algorithm-parameters"></a><span data-ttu-id="98c71-102">Ver o cambiar parámetros del algoritmo</span><span class="sxs-lookup"><span data-stu-id="98c71-102">View or Change Algorithm Parameters</span></span>
  <span data-ttu-id="98c71-103">Puede cambiar los parámetros proporcionados con los algoritmos que se utilizan para crear modelos de minería de datos para personalizar los resultados del modelo.</span><span class="sxs-lookup"><span data-stu-id="98c71-103">You can change the parameters provided with the algorithms that you use to build data mining models to customize the results of the model.</span></span>  
  
 <span data-ttu-id="98c71-104">Los parámetros de algoritmo que se proporcionan en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cambian mucho más que las propiedades del modelo: se pueden usar para modificar fundamentalmente la manera en que se procesan, agrupan y muestran los datos.</span><span class="sxs-lookup"><span data-stu-id="98c71-104">The algorithm parameters provided in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] change much more than just properties on the model: they can be used to fundamentally alter the way that data is processed, grouped, and displayed.</span></span> <span data-ttu-id="98c71-105">Por ejemplo, puede usar parámetros de algoritmo para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="98c71-105">For example, you can use algorithm parameters to do the following:</span></span>  
  
-   <span data-ttu-id="98c71-106">Cambiar el método de análisis, como el método de clústeres.</span><span class="sxs-lookup"><span data-stu-id="98c71-106">Change the method of analysis, such as the clustering method.</span></span>  
  
-   <span data-ttu-id="98c71-107">Controlar el comportamiento de la selección de características.</span><span class="sxs-lookup"><span data-stu-id="98c71-107">Control feature selection behavior.</span></span>  
  
-   <span data-ttu-id="98c71-108">Especificar el tamaño de los conjuntos de elementos o la probabilidad de las reglas.</span><span class="sxs-lookup"><span data-stu-id="98c71-108">Specify the size of itemsets or the probability of rules.</span></span>  
  
-   <span data-ttu-id="98c71-109">Controlar la bifurcación y la profundidad de los árboles de decisión.</span><span class="sxs-lookup"><span data-stu-id="98c71-109">Control branching and depth of decision trees.</span></span>  
  
-   <span data-ttu-id="98c71-110">Especificar un valor de inicialización o el tamaño del conjunto interno de exclusión que se utiliza para la creación del modelo.</span><span class="sxs-lookup"><span data-stu-id="98c71-110">Specify a seed value or the size of the internal holdout set used for model creation.</span></span>  
  
 <span data-ttu-id="98c71-111">Los parámetros proporcionados para cada algoritmo varían en gran medida. Para obtener una lista de los parámetros que se pueden establecer para cada algoritmo, vea los temas de referencia técnica de esta sección: [Algoritmos de minería de datos &#40;Analysis Services - Minería de datos&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="98c71-111">The parameters provided for each algorithm vary greatly; for a list of the parameters that you can set for each algorithm, see the technical reference topics in this section: [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
### <a name="change-an-algorithm-parameter"></a><span data-ttu-id="98c71-112">Cambiar un parámetro de algoritmo</span><span class="sxs-lookup"><span data-stu-id="98c71-112">Change an algorithm parameter</span></span>  
  
1.  <span data-ttu-id="98c71-113">En la pestaña **Modelos de minería de datos** del Diseñador de minería de datos en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga clic con el botón derecho en el tipo de algoritmo del modelo de minería de datos para el que quiera ajustar el algoritmo y, después, seleccione **Establecer parámetros de algoritmo**.</span><span class="sxs-lookup"><span data-stu-id="98c71-113">On the **Mining Models** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], right-click the algorithm type of the mining model for which you want to tune the algorithm, and select **Set Algorithm Parameters**.</span></span>  
  
     <span data-ttu-id="98c71-114">Se abrirá la ventana **Parámetros de algoritmo** .</span><span class="sxs-lookup"><span data-stu-id="98c71-114">The **Algorithm Parameters** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="98c71-115">En la columna **Valor** , ajuste un nuevo valor para el algoritmo que desee cambiar.</span><span class="sxs-lookup"><span data-stu-id="98c71-115">In the **Value** column, set a new value for the algorithm that you want to change.</span></span>  
  
     <span data-ttu-id="98c71-116">Si no especifica un valor en la columna **Valor** , [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utiliza el valor de parámetro predeterminado.</span><span class="sxs-lookup"><span data-stu-id="98c71-116">If you do not enter a value in the **Value** column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] uses the default parameter value.</span></span> <span data-ttu-id="98c71-117">La columna **Intervalo** describe los posibles valores que se pueden especificar.</span><span class="sxs-lookup"><span data-stu-id="98c71-117">The **Range** column describes the possible values that you can enter.</span></span>  
  
3.  <span data-ttu-id="98c71-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="98c71-118">Click **OK**.</span></span>  
  
     <span data-ttu-id="98c71-119">El parámetro de algoritmo se establece con el nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="98c71-119">The algorithm parameter is set with the new value.</span></span> <span data-ttu-id="98c71-120">El cambio de parámetro no se reflejará en el modelo de minería de datos hasta que vuelva a procesar el modelo.</span><span class="sxs-lookup"><span data-stu-id="98c71-120">The parameter change will not be reflected in the mining model until you reprocess the model.</span></span>  
  
### <a name="view-the-parameters-used-in-an-existing-model"></a><span data-ttu-id="98c71-121">Vea los parámetros utilizados en un modelo existente</span><span class="sxs-lookup"><span data-stu-id="98c71-121">View the parameters used in an existing model</span></span>  
  
1.  <span data-ttu-id="98c71-122">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], abra una ventana Consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="98c71-122">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], open a DMX Query window.</span></span>  
  
2.  <span data-ttu-id="98c71-123">Escriba una consulta como esta:</span><span class="sxs-lookup"><span data-stu-id="98c71-123">Type a query like this one:</span></span>  
  
    ```  
    select MINING_PARAMETERS   
    from $system.DMSCHEMA_MINING_MODELS  
    WHERE MODEL_NAME = '<model name>'  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="98c71-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98c71-124">See Also</span></span>  
 [<span data-ttu-id="98c71-125">Tareas y procedimientos de los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="98c71-125">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
