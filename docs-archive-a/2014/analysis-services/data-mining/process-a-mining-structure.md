---
title: Procesar una estructura de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], processing
ms.assetid: 4162f33e-c23f-4293-8905-271781e45fa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d25a927ae61ee5ffadf4ca21073a1c04cdb542
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747265"
---
# <a name="process-a-mining-structure"></a><span data-ttu-id="e6e0d-102">Procesar una estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e6e0d-102">Process a Mining Structure</span></span>
  <span data-ttu-id="e6e0d-103">Para poder examinar o trabajar con los modelos de minería de datos asociados a una estructura de minería de datos, se debe implementar el proyecto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] y procesar la estructura y los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="e6e0d-103">Before you can browse or work with the mining models that are associated with a mining structure, you have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span> <span data-ttu-id="e6e0d-104">Además, si realiza un cambio en la estructura o los modelos de minería de datos, se le solicitará que vuelva a implementarlos y procesarlos.</span><span class="sxs-lookup"><span data-stu-id="e6e0d-104">Also, if you make a change to the mining structure or mining models, you will be prompted to redeploy and process them.</span></span> <span data-ttu-id="e6e0d-105">Al procesar la estructura en la pestaña **Estructura de minería de datos** del Diseñador de minería de datos en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] se procesan todos los modelos asociados.</span><span class="sxs-lookup"><span data-stu-id="e6e0d-105">Processing the structure in the **Mining Structure** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] processes all the associated models.</span></span>  
  
 <span data-ttu-id="e6e0d-106">Puede procesar una estructura de minería de datos mediante estas herramientas:</span><span class="sxs-lookup"><span data-stu-id="e6e0d-106">You can process a mining structure by using these tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
-   <span data-ttu-id="e6e0d-107">XMLA: comando Process</span><span class="sxs-lookup"><span data-stu-id="e6e0d-107">XMLA: Process command</span></span>  
  
 <span data-ttu-id="e6e0d-108">Para obtener información sobre cómo procesar modelos individuales, vea [Procesar un modelo de minería de datos](process-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="e6e0d-108">For information about how to process individual models, see [Process a Mining Model](process-a-mining-model.md).</span></span>  
  
### <a name="to-process-a-mining-structure-and-all-associated-mining-models-using-sql-server-data-tools"></a><span data-ttu-id="e6e0d-109">Para procesar una estructura de minería de datos y todos los modelos asociados a las herramientas de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6e0d-109">To process a mining structure and all associated mining models using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="e6e0d-110">Seleccione **Procesar estructura de minería de datos y todos los modelos** en la opción de menú **Modelo de minería de datos** en [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6e0d-110">Select **Process Mining Structure and All Models** from the **Mining Model** menu item in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
     <span data-ttu-id="e6e0d-111">Si ha realizado cambios en la estructura, se le pedirá que vuelva a implementar la estructure antes de procesar los modelos.</span><span class="sxs-lookup"><span data-stu-id="e6e0d-111">If you made changes to the structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="e6e0d-112">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e6e0d-112">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="e6e0d-113">Haga clic en **Ejecutar** en el cuadro de diálogo **procesando estructura de minería \<structure> de datos** .</span><span class="sxs-lookup"><span data-stu-id="e6e0d-113">Click **Run** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
     <span data-ttu-id="e6e0d-114">Se abre el cuadro de diálogo **Progreso del proceso** para mostrar los detalles del procesamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="e6e0d-114">The **Process Progress** dialog box opens to display the details of model processing.</span></span>  
  
3.  <span data-ttu-id="e6e0d-115">Haga clic en **Cerrar** en el cuadro de diálogo **Progreso del proceso** cuando el procesamiento de los modelos se haya completado.</span><span class="sxs-lookup"><span data-stu-id="e6e0d-115">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="e6e0d-116">Haga clic en **cerrar** en el cuadro de diálogo **procesando estructura de minería \<structure> de datos** .</span><span class="sxs-lookup"><span data-stu-id="e6e0d-116">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6e0d-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6e0d-117">See Also</span></span>  
 [<span data-ttu-id="e6e0d-118">Tareas y procedimientos de las estructuras de minería de datos</span><span class="sxs-lookup"><span data-stu-id="e6e0d-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
