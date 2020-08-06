---
title: Crear una vista del origen de datos (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1e68a88-0f82-415d-becc-78d180d4f845
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 4582845c905ef95601cbff2c810633f0cc901e3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671281"
---
# <a name="creating-a-data-source-view-basic-data-mining-tutorial"></a><span data-ttu-id="87275-102">Crear una vista del origen de datos (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="87275-102">Creating a Data Source View (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="87275-103">Una vista del origen de datos se genera en un origen de datos y define un subconjunto de los datos, que puede usar en las estructuras de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="87275-103">A data source view is built on a data source and defines a subset of the data, which you can then use in your mining structures.</span></span> <span data-ttu-id="87275-104">También puede usar la vista del origen de datos para agregar columnas, crear columnas calculadas y agregados, y agregar vistas con nombre.</span><span class="sxs-lookup"><span data-stu-id="87275-104">You can also use the data source view to add columns, create calculated columns and aggregates, and add named views.</span></span> <span data-ttu-id="87275-105">Mediante el uso de vistas del origen de datos, puede seleccionar los datos relacionados con un proyecto, establecer relaciones entre tablas y modificar la estructura de los datos sin modificar el origen de datos original.</span><span class="sxs-lookup"><span data-stu-id="87275-105">By using data source views, you can select the data that relates to your project, establish relationships between tables, and modify the structure of the data, without modifying the original data source.</span></span> <span data-ttu-id="87275-106">Para más información, vea [Vistas del origen de datos en modelos multidimensionales](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span><span class="sxs-lookup"><span data-stu-id="87275-106">For more information, see [Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span></span>  
  
### <a name="to-create-a-data-source-view"></a><span data-ttu-id="87275-107">Para crear una vista del origen de datos</span><span class="sxs-lookup"><span data-stu-id="87275-107">To create a data source view</span></span>  
  
1.  <span data-ttu-id="87275-108">En **Explorador de soluciones**, haga clic con el botón secundario en **vistas del origen de datos**y seleccione **nueva vista del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="87275-108">In **Solution Explorer**, right-click **Data Source Views**, and select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="87275-109">En la página inicial del **Asistente para orígenes de datos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="87275-109">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="87275-110">En la página **seleccionar un origen de datos** , en **orígenes de datos relacionales**, seleccione el origen de datos Adventure Works DW 2012 que creó en la última tarea.</span><span class="sxs-lookup"><span data-stu-id="87275-110">On the **Select a Data Source** page, under **Relational data sources**, select the Adventure Works DW 2012 data source that you created in the last task.</span></span> <span data-ttu-id="87275-111">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="87275-111">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="87275-112">Si desea crear un origen de datos, haga clic con el botón secundario en **orígenes de datos** y, a continuación, haga clic en **nuevo origen de datos** para iniciar el Asistente para orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="87275-112">If you want to create a data source, right-click **Data Sources** and then click **New Data Source** to start the Data Source Wizard.</span></span>  
  
4.  <span data-ttu-id="87275-113">En la página **seleccionar tablas y vistas** , seleccione los objetos siguientes y, a continuación, haga clic en la flecha derecha para incluirlos en la nueva vista del origen de datos:</span><span class="sxs-lookup"><span data-stu-id="87275-113">On the **Select Tables and Views** page, select the following objects, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   <span data-ttu-id="87275-114">**ProspectiveBuyer (DBO)** : tabla de compradores de bicicletas posibles</span><span class="sxs-lookup"><span data-stu-id="87275-114">**ProspectiveBuyer (dbo)** - table of prospective bike buyers</span></span>  
  
    -   <span data-ttu-id="87275-115">**vTargetMail (DBO)** : vista de los datos históricos sobre los compradores de bicicletas anteriores</span><span class="sxs-lookup"><span data-stu-id="87275-115">**vTargetMail (dbo)** - view of historical data about past bike buyers</span></span>  
  
5.  <span data-ttu-id="87275-116">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="87275-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="87275-117">En la página **finalización del asistente** , de forma predeterminada, la vista del origen de datos se denomina Adventure Works DW 2012.</span><span class="sxs-lookup"><span data-stu-id="87275-117">On the **Completing the Wizard** page, by default the data source view is named Adventure Works DW 2012.</span></span> <span data-ttu-id="87275-118">Cambie el nombre a `Targeted Mailing` y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="87275-118">Change the name to `Targeted Mailing`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="87275-119">La nueva vista del origen de datos se abre en la pestaña **Targeted mailing. DSV [Design]** .</span><span class="sxs-lookup"><span data-stu-id="87275-119">The new data source view opens in the **Targeted Mailing.dsv [Design]** tab.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="87275-120">Tarea anterior de la lección</span><span class="sxs-lookup"><span data-stu-id="87275-120">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="87275-121">Crear un origen de datos &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="87275-121">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="87275-122">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="87275-122">Next Lesson</span></span>  
 [<span data-ttu-id="87275-123">Lección 2: crear una estructura de distribución de correo directo &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="87275-123">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="87275-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87275-124">See Also</span></span>  
 [<span data-ttu-id="87275-125">Definir una vista del origen de datos &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="87275-125">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/defining-a-data-source-view-analysis-services)  
  
  
