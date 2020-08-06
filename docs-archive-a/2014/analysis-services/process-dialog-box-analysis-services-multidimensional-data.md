---
title: Cuadro de diálogo procesar (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.processdialog.f1
ms.assetid: c065248c-9001-4f0c-928f-9c59eccb618b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 369c121713894bba9b2ce6c40aa2869de49eaa72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750258"
---
# <a name="process-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="bd175-102">Cuadro de diálogo Procesar (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="bd175-102">Process Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="bd175-103">Use el cuadro de diálogo **Proceso** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] y [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] para procesar objetos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd175-103">Use the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to process [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects.</span></span> <span data-ttu-id="bd175-104">Para mostrar el cuadro de diálogo **Procesar** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="bd175-104">You can display the **Process** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] by:</span></span>  
  
-   <span data-ttu-id="bd175-105">Haga clic con el botón derecho en un proyecto, cubo, dimensión o estructura de minería de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en el **Explorador de soluciones** y seleccione **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="bd175-105">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, cube, dimension, or mining structure in **Solution Explorer** and selecting **Process**.</span></span>  
  
-   <span data-ttu-id="bd175-106">Seleccione **Procesar** en la barra de herramientas en todas las páginas del **Diseñador de cubos**, en todas las páginas del **Diseñador de dimensiones**o en las páginas de la **Estructura de minería de datos** y **Modelos de minería de datos** del **Diseñador de modelos de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="bd175-106">Selecting **Process** from the toolbar on every page of **Cube Designer**, every page of **Dimension Designer**, or the **Mining Structure** and **Mining Models** pages of **Data Mining Model Designer**.</span></span>  
  
-   <span data-ttu-id="bd175-107">Haga clic con el botón derecho en un modelo de minería de datos de la página **Modelos de minería de datos** del **Diseñador de modelos de minería de datos** y seleccione **Procesar estructura de minería de datos y todos los modelos** o **Procesar modelo**.</span><span class="sxs-lookup"><span data-stu-id="bd175-107">Right-clicking a mining model in the **Mining Models** page of **Data Mining Model Designer** and selecting **Process Mining Structure and All Models** or **Process Model**.</span></span>  
  
 <span data-ttu-id="bd175-108">Para mostrar el cuadro de diálogo **Procesar** de **SQL Server Management Studio** :</span><span class="sxs-lookup"><span data-stu-id="bd175-108">You can display the **Process** dialog box in **SQL Server Management Studio** by:</span></span>  
  
-   <span data-ttu-id="bd175-109">Haga clic con el botón derecho en una base de datos, cubo, grupo de medida, partición, dimensión, estructura de minería de datos o modelo de minería de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en el **Explorador de objetos** y seleccione **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="bd175-109">Right-clicking an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, cube, measure group, partition, dimension, mining structure, or mining model in **Object Explorer** and selecting **Process**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bd175-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="bd175-110">Options</span></span>  
 <span data-ttu-id="bd175-111">**Lista de objetos**</span><span class="sxs-lookup"><span data-stu-id="bd175-111">**Object list**</span></span>  
 <span data-ttu-id="bd175-112">Seleccione los objetos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que desea procesar, así como las opciones de proceso y la configuración que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="bd175-112">Select the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects to be processed and the processing options and settings to be applied.</span></span> <span data-ttu-id="bd175-113">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="bd175-113">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="bd175-114">**Nombre de objeto**</span><span class="sxs-lookup"><span data-stu-id="bd175-114">**Object Name**</span></span>  
 <span data-ttu-id="bd175-115">Muestra el nombre del objeto que se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="bd175-115">Displays the name of the object to be processed.</span></span> <span data-ttu-id="bd175-116">El icono que se muestra a la izquierda del nombre indica el tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="bd175-116">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="bd175-117">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="bd175-117">**Type**</span></span>  
 <span data-ttu-id="bd175-118">Muestra el tipo de objeto que se va a procesar.</span><span class="sxs-lookup"><span data-stu-id="bd175-118">Displays the type of the object to be processed.</span></span>  
  
 <span data-ttu-id="bd175-119">**Opciones de proceso**</span><span class="sxs-lookup"><span data-stu-id="bd175-119">**Process Options**</span></span>  
 <span data-ttu-id="bd175-120">Seleccione el tipo de procesamiento que desea realizar para el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bd175-120">Select the type of processing to perform on the selected object.</span></span> <span data-ttu-id="bd175-121">Para obtener más información sobre las opciones de procesamiento disponibles, vea [procesamiento de objetos de modelo multidimensional](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="bd175-121">For more information about available processing options, see [Multidimensional Model Object Processing](multidimensional-models/processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
 <span data-ttu-id="bd175-122">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="bd175-122">**Settings**</span></span>  
 <span data-ttu-id="bd175-123">Muestra el hipervínculo **Configurar** si elige **Procesar incremental** en **Opciones de proceso** para cubos, grupos de medida o particiones.</span><span class="sxs-lookup"><span data-stu-id="bd175-123">Displays the **Configure** hyperlink when you choose **Process Incremental** in **Process Options** for cubes, measure groups, or partitions.</span></span> <span data-ttu-id="bd175-124">Haga clic en **Configurar** para abrir el cuadro de diálogo **Actualización incremental** .</span><span class="sxs-lookup"><span data-stu-id="bd175-124">Click **Configure** to launch the **Incremental Update** dialog box.</span></span> <span data-ttu-id="bd175-125">Para obtener más información sobre el cuadro de diálogo **Actualización incremental**, vea [Cuadro de diálogo Actualización incremental &#40;Analysis Services - Datos multidimensionales&#41;](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="bd175-125">For more information about the **Incremental Update** dialog box, see [Incremental Update Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](incremental-update-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="bd175-126">**Remove**</span><span class="sxs-lookup"><span data-stu-id="bd175-126">**Remove**</span></span>  
 <span data-ttu-id="bd175-127">Haga clic para quitar los elementos seleccionados de la **Lista de objetos**.</span><span class="sxs-lookup"><span data-stu-id="bd175-127">Click to remove the selected items from **Object list**.</span></span>  
  
 <span data-ttu-id="bd175-128">**Análisis de impacto**</span><span class="sxs-lookup"><span data-stu-id="bd175-128">**Impact Analysis**</span></span>  
 <span data-ttu-id="bd175-129">Haga clic para abrir el cuadro de diálogo **Análisis de impacto** y mostrar los objetos a los que afectará la tarea de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="bd175-129">Click to open the **Impact Analysis** dialog box and display the objects that will be affected by the processing task.</span></span> <span data-ttu-id="bd175-130">Para obtener más información sobre el cuadro de diálogo **Análisis de impacto**, vea [Cuadro de diálogo Análisis de impacto &#40;Analysis Services - Datos multidimensionales&#41;](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="bd175-130">For more information about the **Impact Analysis** dialog box, see [Impact Analysis Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](impact-analysis-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bd175-131"> Esta opción se deshabilitará si se selecciona la opción **Objetos afectados por el proceso** en el cuadro de diálogo **Cambiar configuración** .</span><span class="sxs-lookup"><span data-stu-id="bd175-131">This option is disabled when the **Process affected objects** option is selected in the **Change Settings** dialog box.</span></span>  
  
 <span data-ttu-id="bd175-132">**Cambiar configuración**</span><span class="sxs-lookup"><span data-stu-id="bd175-132">**Change Settings**</span></span>  
 <span data-ttu-id="bd175-133">Haga clic para abrir el cuadro de diálogo **Cambiar configuración** y cambiar la configuración que regirá el procesamiento de los objetos seleccionados, incluida la configuración de procesamiento por lotes, la configuración de reescritura y la configuración de errores de claves de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="bd175-133">Click to open the **Change Settings** dialog box and change the settings that govern processing of the selected objects, including batch processing settings, writeback settings, and dimension key error settings.</span></span> <span data-ttu-id="bd175-134">Para obtener más información sobre el cuadro de diálogo **Cambiar configuración**, vea [Cuadro de diálogo Cambiar configuración &#40;Analysis Services - Datos multidimensionales&#41;](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="bd175-134">For more information about the **Change Settings** dialog box, see [Change Settings Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](change-settings-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="bd175-135">**Ejecutar**</span><span class="sxs-lookup"><span data-stu-id="bd175-135">**Run**</span></span>  
 <span data-ttu-id="bd175-136">Haga clic para procesar los objetos.</span><span class="sxs-lookup"><span data-stu-id="bd175-136">Click to process the objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd175-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd175-137">See Also</span></span>  
 <span data-ttu-id="bd175-138">[Analysis Services diseñadores y cuadros de diálogo &#40;datos multidimensionales&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="bd175-138">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="bd175-139">Cuadro de diálogo progreso del proceso &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="bd175-139">Process Progress Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-progress-dialog-box-analysis-services-multidimensional-data.md)  
  
  
