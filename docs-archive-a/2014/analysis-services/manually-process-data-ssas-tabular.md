---
title: Procesar manualmente los datos (SSAS tabular) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.datarefreshprogressdb.f1
ms.assetid: 0918c04c-c1e6-45b4-acfa-96fa578e684b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 51bdb1b9535685db4fc35dbdd791e6b4d9bed1b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675621"
---
# <a name="manually-process-data-ssas-tabular"></a><span data-ttu-id="22818-102">Procesar manualmente los datos (SSAS tabular)</span><span class="sxs-lookup"><span data-stu-id="22818-102">Manually Process Data (SSAS Tabular)</span></span>
  <span data-ttu-id="22818-103">En este tema se describe cómo procesar manualmente los datos del área de trabajo en [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="22818-103">This topic describes how to manually process workspace data in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="22818-104">Si crea un modelo tabular que use datos externos, podrá actualizar manualmente los datos mediante el comando Procesar.</span><span class="sxs-lookup"><span data-stu-id="22818-104">When you author a tabular model that uses external data, you can manually refresh the data by using the Process command.</span></span> <span data-ttu-id="22818-105">Puede procesar una única tabla, todas las tablas del modelo o una o más particiones.</span><span class="sxs-lookup"><span data-stu-id="22818-105">You can process a single table, all tables in the model, or one or more partitions.</span></span> <span data-ttu-id="22818-106">Siempre que procese datos, puede que también tenga que volver a calcularlos.</span><span class="sxs-lookup"><span data-stu-id="22818-106">Whenever you process data, you may also need to recalculate data.</span></span>  <span data-ttu-id="22818-107">Procesar los datos significa obtener los datos más recientes de los orígenes externos.</span><span class="sxs-lookup"><span data-stu-id="22818-107">Processing data means getting the latest data from external sources.</span></span> <span data-ttu-id="22818-108">Recalcular significa actualizar el resultado de cualquier fórmula que use los datos.</span><span class="sxs-lookup"><span data-stu-id="22818-108">Recalculating means updating the result of any formula that uses the data.</span></span>  
  
 <span data-ttu-id="22818-109">Secciones de este tema:</span><span class="sxs-lookup"><span data-stu-id="22818-109">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="22818-110">Procesar manualmente los datos</span><span class="sxs-lookup"><span data-stu-id="22818-110">Manually Process Data</span></span>](#bkmk_mahually_process)  
  
-   [<span data-ttu-id="22818-111">Progreso del proceso de datos</span><span class="sxs-lookup"><span data-stu-id="22818-111">Data Process Progress</span></span>](#bkmk_data_process_progress)  
  
##  <a name="manually-process-data"></a><a name="bkmk_mahually_process"></a><span data-ttu-id="22818-112">Procesar manualmente los datos</span><span class="sxs-lookup"><span data-stu-id="22818-112">Manually Process Data</span></span>  
  
#### <a name="to-process-data-for-a-single-table-or-all-tables-in-a-model"></a><span data-ttu-id="22818-113">Para procesar los datos de una sola tabla o todas las tablas de un modelo</span><span class="sxs-lookup"><span data-stu-id="22818-113">To process data for a single table or all tables in a model</span></span>  
  
1.  <span data-ttu-id="22818-114">En el diseñador de modelos, haga clic en la tabla que desea procesar.</span><span class="sxs-lookup"><span data-stu-id="22818-114">In the model designer, click the table you want to process.</span></span>  
  
2.  <span data-ttu-id="22818-115">En el menú **Modelo** , haga clic en **Procesar**y, a continuación, haga clic en **Procesar** o en **Procesar todo**.</span><span class="sxs-lookup"><span data-stu-id="22818-115">Click on the **Model** menu, then click **Process**, and then click **Process** or **Process All**.</span></span>  
  
#### <a name="to-process-data-for-all-tables-using-the-same-connection"></a><span data-ttu-id="22818-116">Para procesar los datos de todas las tablas utilizando la misma conexión</span><span class="sxs-lookup"><span data-stu-id="22818-116">To process data for all tables using the same connection</span></span>  
  
1.  <span data-ttu-id="22818-117">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** y, a continuación, en **Conexiones existentes**.</span><span class="sxs-lookup"><span data-stu-id="22818-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="22818-118">En el cuadro de diálogo **Conexiones existentes** , seleccione una conexión y, a continuación, haga clic en **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="22818-118">In the **Existing Connections** dialog box, select a connection, and then click **Process**.</span></span>  
  
#### <a name="to-process-data-for-one-or-more-partitions"></a><span data-ttu-id="22818-119">Para procesar los datos de una o más particiones</span><span class="sxs-lookup"><span data-stu-id="22818-119">To process data for one or more partitions</span></span>  
  
1.  <span data-ttu-id="22818-120">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** , seleccione **Procesar**y, a continuación, haga clic en **Procesar particiones**.</span><span class="sxs-lookup"><span data-stu-id="22818-120">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model** menu, then point to **Process**, and then click **Process Partitions**.</span></span>  
  
2.  <span data-ttu-id="22818-121">En el cuadro de diálogo **Procesar particiones** , en **Modo**, seleccione uno de los siguientes modos de procesamiento:</span><span class="sxs-lookup"><span data-stu-id="22818-121">In the **Process Partitions** dialog box, in **Mode**, select one of the following process modes:</span></span>  
  
    |<span data-ttu-id="22818-122">Mode</span><span class="sxs-lookup"><span data-stu-id="22818-122">Mode</span></span>|<span data-ttu-id="22818-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="22818-123">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="22818-124">**Proceso predeterminado**</span><span class="sxs-lookup"><span data-stu-id="22818-124">**Process Default**</span></span>|<span data-ttu-id="22818-125">Detecta el estado de proceso de un objeto de partición y realiza el procesamiento necesario para devolver objetos de partición sin procesar o procesados parcialmente a un estado de procesamiento completo.</span><span class="sxs-lookup"><span data-stu-id="22818-125">Detects the process state of a partition object, and performs processing necessary to deliver unprocessed or partially processed partition objects to a fully processed state.</span></span> <span data-ttu-id="22818-126">Se cargan los datos de las tablas vacías y las particiones; se generan o se vuelven a generar las jerarquías, las columnas calculadas y las relaciones.</span><span class="sxs-lookup"><span data-stu-id="22818-126">Data for empty tables and partitions is loaded; hierarchies, calculated columns, and relationships are built or rebuilt.</span></span>|  
    |<span data-ttu-id="22818-127">**Proceso completo**</span><span class="sxs-lookup"><span data-stu-id="22818-127">**Process Full**</span></span>|<span data-ttu-id="22818-128">Procesa un objeto de partición y todos los objetos que contiene.</span><span class="sxs-lookup"><span data-stu-id="22818-128">Processes a partition object and all the objects that it contains.</span></span> <span data-ttu-id="22818-129">Cuando se ejecuta Proceso completo en un objeto que ya se ha procesado, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] quita todos los datos del objeto y, a continuación, lo procesa.</span><span class="sxs-lookup"><span data-stu-id="22818-129">When Process Full is run for an object that has already been processed, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] drops all data in the object, and then processes the object.</span></span> <span data-ttu-id="22818-130">Este tipo de procesamiento es necesario cuando se ha realizado un cambio estructural en un objeto.</span><span class="sxs-lookup"><span data-stu-id="22818-130">This kind of processing is required when a structural change has been made to an object.</span></span>|  
    |<span data-ttu-id="22818-131">**Procesar datos**</span><span class="sxs-lookup"><span data-stu-id="22818-131">**Process Data**</span></span>|<span data-ttu-id="22818-132">Carga datos en una partición o en una tabla sin volver a generar las jerarquías o las relaciones, ni volver a calcular las columnas calculadas y las medidas.</span><span class="sxs-lookup"><span data-stu-id="22818-132">Load data into a partition or a table without rebuilding hierarchies or relationships or recalculating calculated columns and measures.</span></span>|  
    |<span data-ttu-id="22818-133">**Procesar borrado**</span><span class="sxs-lookup"><span data-stu-id="22818-133">**Process Clear**</span></span>|<span data-ttu-id="22818-134">Quita todos los datos de una partición.</span><span class="sxs-lookup"><span data-stu-id="22818-134">Removes all data from a partition.</span></span>|  
    |<span data-ttu-id="22818-135">**Procesar adición**</span><span class="sxs-lookup"><span data-stu-id="22818-135">**Process Add**</span></span>|<span data-ttu-id="22818-136">Actualiza la partición con nuevos datos de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="22818-136">Incrementally update partition with new data.</span></span>|  
  
3.  <span data-ttu-id="22818-137">En la lista Particiones, seleccione las particiones que desee procesar y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="22818-137">In the partitions list, select the partitions you want to process, and then click **OK**.</span></span>  
  
##  <a name="data-process-progress"></a><a name="bkmk_data_process_progress"></a> <span data-ttu-id="22818-138">Progreso de procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="22818-138">Data Process Progress</span></span>  
 <span data-ttu-id="22818-139">El cuadro de diálogo **Progreso de procesamiento de datos** le permite supervisar el procesamiento de los datos que ha importado en el modelo desde un origen externo.</span><span class="sxs-lookup"><span data-stu-id="22818-139">The **Data Process Progress** dialog box enables you to monitor the processing of data that you have imported into the model from an external source.</span></span> <span data-ttu-id="22818-140">Para obtener acceso a este cuadro de diálogo, haga clic en el menú **Modelo** y, a continuación, en **Procesar particiones**, **Procesar tabla** o **Procesar todo**.</span><span class="sxs-lookup"><span data-stu-id="22818-140">To access this dialog box, click on the **Model** menu, and then click **Process Partitions**, **Process Table** or **Process All**.</span></span>  
  
 <span data-ttu-id="22818-141">**Estado**</span><span class="sxs-lookup"><span data-stu-id="22818-141">**Status**</span></span>  
 <span data-ttu-id="22818-142">Indica si la operación de procesamiento fue correcta o no.</span><span class="sxs-lookup"><span data-stu-id="22818-142">Indicates whether the process operation was successful or not.</span></span>  
  
 <span data-ttu-id="22818-143">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="22818-143">**Details**</span></span>  
 <span data-ttu-id="22818-144">Enumera las tablas y vistas que se importaron, el número de filas que se importaron y proporciona un vínculo a un informe de los problemas que se hayan producido.</span><span class="sxs-lookup"><span data-stu-id="22818-144">Lists the tables and views that were imported, the number of rows that were imported, and provides a link to a report of any issues.</span></span>  
  
 <span data-ttu-id="22818-145">**Detener actualización**</span><span class="sxs-lookup"><span data-stu-id="22818-145">**Stop Refresh**</span></span>  
 <span data-ttu-id="22818-146">Haga clic aquí para detener la operación de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="22818-146">Click to halt the process operation.</span></span> <span data-ttu-id="22818-147">Esta opción resulta útil si la operación tarda demasiado o hay demasiados errores.</span><span class="sxs-lookup"><span data-stu-id="22818-147">This option is useful if the operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22818-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="22818-148">See Also</span></span>  
 <span data-ttu-id="22818-149">[Procesar datos &#40;SSAS tabular&#41;](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="22818-149">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="22818-150">Solucionar problemas del procesamiento de datos &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="22818-150">Troubleshoot Process Data &#40;SSAS Tabular&#41;</span></span>](troubleshoot-process-data-ssas-tabular.md)  
  
  
