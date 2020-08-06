---
title: Modificar y procesar el modelo de cesta de la compra (tutorial intermedio de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b6019413-aebd-4ff7-831a-644572ad88b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 369de98e944c5ccf5d06ef61eaa16c06bb864e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662429"
---
# <a name="modifying-and-processing-the-market-basket-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="c865c-102">Modificar y procesar el modelo de cesta de la compra (Tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="c865c-102">Modifying and Processing the Market Basket Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="c865c-103">Antes de procesar el modelo de minería de datos de asociación que creó, debe cambiar los valores predeterminados de dos de los parámetros: *compatibilidad* y *probabilidad*.</span><span class="sxs-lookup"><span data-stu-id="c865c-103">Before you process the association mining model that you created, you must change the default values of two of the parameters: *Support* and *Probability*.</span></span>  
  
-   <span data-ttu-id="c865c-104">La *compatibilidad* define el porcentaje de casos en los que debe existir una regla antes de que se considere válida.</span><span class="sxs-lookup"><span data-stu-id="c865c-104">*Support* defines the percentage of cases in which a rule must exist before it is considered valid.</span></span> <span data-ttu-id="c865c-105">Especificará que una regla se debe encontrar en un uno por ciento de casos al menos.</span><span class="sxs-lookup"><span data-stu-id="c865c-105">You will specify that a rule must be found in at least 1 percent of cases.</span></span>  
  
-   <span data-ttu-id="c865c-106">La *probabilidad* define la probabilidad de que una asociación sea antes de que se considere válida.</span><span class="sxs-lookup"><span data-stu-id="c865c-106">*Probability* defines how likely an association must be before it is considered valid.</span></span> <span data-ttu-id="c865c-107">Considerará cualquier asociación con una probabilidad de al menos el 10 por ciento.</span><span class="sxs-lookup"><span data-stu-id="c865c-107">You will consider any association with a probability of at least 10 percent.</span></span>  
  
 <span data-ttu-id="c865c-108">Para obtener más información sobre los efectos de aumentar o reducir la compatibilidad y la probabilidad, consulte [referencia técnica del algoritmo de Asociación de Microsoft](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c865c-108">For more information about the effects of increasing or decreasing support and probability, see [Microsoft Association Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-association-algorithm-technical-reference.md).</span></span>  
  
 <span data-ttu-id="c865c-109">Después de definir la estructura y los parámetros para el modelo de minería de datos **Association** , procesará el modelo.</span><span class="sxs-lookup"><span data-stu-id="c865c-109">After you have defined the structure and parameters for the **Association** mining model, you will process the model.</span></span>  
  
### <a name="to-adjust-the-parameters-of-the-association-model"></a><span data-ttu-id="c865c-110">Para ajustar los parámetros del modelo Association</span><span class="sxs-lookup"><span data-stu-id="c865c-110">To adjust the parameters of the Association model</span></span>  
  
1.  <span data-ttu-id="c865c-111">Abra la pestaña **modelos de minería** de datos del diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="c865c-111">Open the **Mining Models** tab of Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="c865c-112">Haga clic con el botón secundario en la columna **Asociación** de la cuadrícula en el diseñador y seleccione **establecer parámetros de algoritmo para abrir el cuadro de diálogo parámetros de algoritmo** .</span><span class="sxs-lookup"><span data-stu-id="c865c-112">Right-click the **Association** column in the grid in the designer and select **Set Algorithm Parameters to open the Algorithm Parameters** dialog box.</span></span>  
  
3.  <span data-ttu-id="c865c-113">En la columna **valor** del cuadro de diálogo **parámetros de algoritmo** , establezca los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="c865c-113">In the **Value** column of the **Algorithm Parameters** dialog box, set the following parameters:</span></span>  
  
     <span data-ttu-id="c865c-114">MINIMUM_PROBABILITY = 0,1</span><span class="sxs-lookup"><span data-stu-id="c865c-114">MINIMUM_PROBABILITY = 0.1</span></span>  
  
     <span data-ttu-id="c865c-115">MINIMUM_SUPPORT = 0,01</span><span class="sxs-lookup"><span data-stu-id="c865c-115">MINIMUM_SUPPORT = 0.01</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-process-the-mining-model"></a><span data-ttu-id="c865c-116">Para procesar el modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c865c-116">To process the mining model</span></span>  
  
1.  <span data-ttu-id="c865c-117">En el menú **modelo de minería de datos** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , seleccione **procesar estructura de minería de datos y todos los modelos.**</span><span class="sxs-lookup"><span data-stu-id="c865c-117">On the **Mining Model** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], select **Process Mining Structure and All Models.**</span></span>  
  
2.  <span data-ttu-id="c865c-118">En la advertencia en la que se pregunta si desea generar e implementar el proyecto, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="c865c-118">At the warning asking whether you want to build and deploy the project, click **Yes**.</span></span>  
  
     <span data-ttu-id="c865c-119">Se abrirá el cuadro **de diálogo procesar estructura de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="c865c-119">The **Process Mining Structure - Association** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c865c-120">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c865c-120">Click **Run**.</span></span>  
  
     <span data-ttu-id="c865c-121">Se abre el cuadro de diálogo **Progreso del proceso** para mostrar información acerca del procesamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="c865c-121">The **Process Progress** dialog box opens to display information about model processing.</span></span> <span data-ttu-id="c865c-122">El procesamiento de la nueva estructura y del nuevo modelo puede tardar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="c865c-122">Processing of the new structure and model might take some time.</span></span>  
  
4.  <span data-ttu-id="c865c-123">Cuando se complete el proceso, haga clic en **Cerrar** para salir del cuadro de diálogo **Progreso del proceso** .</span><span class="sxs-lookup"><span data-stu-id="c865c-123">After processing is complete, click **Close** to exit the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="c865c-124">Vuelva a hacer clic en **cerrar** para salir del cuadro **de diálogo procesar estructura de minería de datos-Asociación** .</span><span class="sxs-lookup"><span data-stu-id="c865c-124">Click **Close** again to exit the **Process Mining Structure - Association** dialog box.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c865c-125">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="c865c-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c865c-126">Explorar los modelos de cesta de la compra &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c865c-126">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="c865c-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c865c-127">See Also</span></span>  
 [<span data-ttu-id="c865c-128">Requisitos y consideraciones de procesamiento &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="c865c-128">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md)  
  
  
