---
title: Procesar un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], processing
ms.assetid: c2204472-c500-47a5-9afa-7ce2ca78b233
author: minewiskan
ms.author: owend
ms.openlocfilehash: c2fed5d72c677dc175f4c9681096d1859b30d829
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747262"
---
# <a name="process-a-mining-model"></a><span data-ttu-id="2ae15-102">Procesar un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="2ae15-102">Process a Mining Model</span></span>
  <span data-ttu-id="2ae15-103">En la pestaña Modelos de minería de datos del Diseñador de minería de datos en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], puede procesar un modelo de minería de datos específico que esté asociado a una estructura de minería de datos, o bien, procesar todos los modelos que estén asociados con la estructura.</span><span class="sxs-lookup"><span data-stu-id="2ae15-103">In the Mining Models tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can either process a specific mining model that is associated with a mining structure or you can process all the models that are associated with the structure.</span></span>  
  
 <span data-ttu-id="2ae15-104">Puede procesar un modelo de minería de datos utilizando las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="2ae15-104">You can process a mining model by using the following tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
 <span data-ttu-id="2ae15-105">También puede utilizar un comando XMLA Process.</span><span class="sxs-lookup"><span data-stu-id="2ae15-105">You can also use an XMLA Process command.</span></span> <span data-ttu-id="2ae15-106">Para obtener más información, vea [herramientas y enfoques para procesar &#40;Analysis Services&#41;](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="2ae15-106">For more information, see  [Tools and Approaches for Processing &#40;Analysis Services&#41;](../multidimensional-models/tools-and-approaches-for-processing-analysis-services.md).</span></span>  
  
### <a name="process-a-single-mining-model-using-sql-server-data-tools"></a><span data-ttu-id="2ae15-107">Procesar un modelo de minería de datos mediante las Herramientas de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="2ae15-107">Process a single mining model using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="2ae15-108">En la pestaña **Modelos de minería de datos** del Diseñador de minería de datos, seleccione un modelo en la columna o columnas de modelos de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="2ae15-108">On the **Mining Models** tab of Data Mining Designer, select a mining model from the one or more columns of models in the grid.</span></span>  
  
2.  <span data-ttu-id="2ae15-109">En el menú **Modelo de minería de datos** , seleccione **Procesar modelo**.</span><span class="sxs-lookup"><span data-stu-id="2ae15-109">On the **Mining Model** menu, select **Process Model**.</span></span>  
  
     <span data-ttu-id="2ae15-110">Si ha realizado cambios a la estructura de minería de datos, se le pedirá que vuelva a implementar la estructura antes de procesar el modelo.</span><span class="sxs-lookup"><span data-stu-id="2ae15-110">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the model.</span></span> <span data-ttu-id="2ae15-111">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2ae15-111">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="2ae15-112">En el cuadro de diálogo **procesando modelo de minería de \<model> datos** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2ae15-112">In the **Processing Mining Model - \<model>** dialog box, click **Run**.</span></span>  
  
     <span data-ttu-id="2ae15-113">Se abre el cuadro de diálogo **Progreso del proceso** para mostrar información acerca del procesamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="2ae15-113">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
4.  <span data-ttu-id="2ae15-114">Una vez que haya finalizado el procesamiento del modelo correctamente, haga clic en **Cerrar** en el cuadro de diálogo **Progreso del proceso** .</span><span class="sxs-lookup"><span data-stu-id="2ae15-114">After the model has successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
5.  <span data-ttu-id="2ae15-115">Haga clic en **cerrar** en el cuadro de diálogo **procesando modelo de minería \<model> de datos** .</span><span class="sxs-lookup"><span data-stu-id="2ae15-115">Click **Close** in the **Processing Mining Model - \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="2ae15-116">Solo se han procesado la estructura y el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2ae15-116">Only the mining structure and the selected mining model have been processed.</span></span>  
  
### <a name="process-all-mining-models-that-are-associated-with-a-mining-structure"></a><span data-ttu-id="2ae15-117">Procesar todos los modelos de minería de datos asociados a una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="2ae15-117">Process all mining models that are associated with a mining structure</span></span>  
  
1.  <span data-ttu-id="2ae15-118">En la pestaña **Modelos de minería de datos** del Diseñador de minería de datos, seleccione la opción **Procesar estructura de minería de datos y todos los modelos** en el menú **Modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="2ae15-118">On the **Mining Models** tab of Data Mining Designer, select **Process Mining Structure and All Models** from the **Mining Model** menu.</span></span>  
  
2.  <span data-ttu-id="2ae15-119">Si ha realizado cambios a la estructura de minería de datos, se le pedirá que vuelva a implementar la estructura antes de procesar los modelos.</span><span class="sxs-lookup"><span data-stu-id="2ae15-119">If you made changes to the mining structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="2ae15-120">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2ae15-120">Click **Yes**.</span></span>  
  
3.  <span data-ttu-id="2ae15-121">En el cuadro de diálogo **procesando estructura de minería de \<structure> datos** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="2ae15-121">In the **Processing Mining Structure - \<structure>** dialog box, click **Run**.</span></span>  
  
4.  <span data-ttu-id="2ae15-122">Se abre el cuadro de diálogo **Progreso del proceso** para mostrar información acerca del procesamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="2ae15-122">The **Process Progress** dialog box opens to show the details of model processing.</span></span>  
  
5.  <span data-ttu-id="2ae15-123">Una vez que haya finalizado el procesamiento de todos los modelos correctamente, haga clic en **Cerrar** en el cuadro de diálogo **Progreso del proceso** .</span><span class="sxs-lookup"><span data-stu-id="2ae15-123">After the models have successfully completed processing, click **Close** in the **Process Progress** dialog box.</span></span>  
  
6.  <span data-ttu-id="2ae15-124">Haga clic en **cerrar** en el cuadro de diálogo de \*\*procesamiento \<model> \*\* .</span><span class="sxs-lookup"><span data-stu-id="2ae15-124">Click **Close** in the **Processing \<model>** dialog box.</span></span>  
  
 <span data-ttu-id="2ae15-125">Se han procesado la estructura y todos los modelos de minería de datos asociados.</span><span class="sxs-lookup"><span data-stu-id="2ae15-125">The mining structure and all the associated mining models have been processed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae15-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ae15-126">See Also</span></span>  
 [<span data-ttu-id="2ae15-127">Tareas y procedimientos de los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="2ae15-127">Mining Model Tasks and How-tos</span></span>](mining-model-tasks-and-how-tos.md)  
  
  
