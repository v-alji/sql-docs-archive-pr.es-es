---
title: Procesamiento por lotes (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- batches [Analysis Services]
ms.assetid: ba4dcf72-0667-41d0-816b-ab8ff9a7d9cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: c777339f41f5f9029e4d03d47cc7f682e00032b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663167"
---
# <a name="batch-processing-analysis-services"></a><span data-ttu-id="b7bfe-102">Procesamiento por lotes (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="b7bfe-102">Batch Processing (Analysis Services)</span></span>
  <span data-ttu-id="b7bfe-103">En [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], puede usar el comando Batch para enviar varios comandos de procesamiento al servidor en una única solicitud.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-103">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you can use the Batch command to send multiple processing commands to the server in a single request.</span></span> <span data-ttu-id="b7bfe-104">El procesamiento por lotes ofrece una forma de controlar qué objetos se deben procesar y en qué orden.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-104">Batch processing gives you a way to control which objects are to be processed, and in what order.</span></span> <span data-ttu-id="b7bfe-105">Además, un lote se puede ejecutar como una serie de trabajos independientes o como una transacción en la que un error en un proceso causa la reversión del lote completo.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-105">Also, a batch can run as a series of stand-alone jobs, or as a transaction in which the failure of one process causes a rollback of the complete batch.</span></span>  
  
 <span data-ttu-id="b7bfe-106">El procesamiento por lotes maximiza la disponibilidad de datos consolidando y reduciendo el tiempo empleado en confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-106">Batch processing maximizes data availability by consolidating and reducing the amount of time taken to commit changes.</span></span> <span data-ttu-id="b7bfe-107">Cuando se procesa totalmente una dimensión, cualquier partición que usa dicha dimensión se marca como sin procesar.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-107">When you fully process a dimension, any partition using that dimension is marked as unprocessed.</span></span> <span data-ttu-id="b7bfe-108">Como resultado, los cubos que contienen las particiones sin procesar no están disponibles para búsquedas.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-108">As a result, cubes that contain the unprocessed partitions are unavailable for browsing.</span></span> <span data-ttu-id="b7bfe-109">Puede solucionar esto con un trabajo de procesamiento por lotes mediante el procesamiento de las dimensiones junto con las particiones afectadas.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-109">You can address this with a batch processing job by processing the dimensions together with the affected partitions.</span></span> <span data-ttu-id="b7bfe-110">La ejecución del trabajo de procesamiento por lotes como una transacción asegura que todos los objetos incluidos en la transacción permanezcan disponibles para consultas hasta que se complete todo el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-110">Running the batch processing job as a transaction makes sure that all objects included in the transaction remain available for queries until all processing is completed.</span></span> <span data-ttu-id="b7bfe-111">Mientras la transacción confirma los cambios, se aplican bloqueos en los objetos afectados, por lo que estos no están disponibles temporalmente, pero en general la cantidad de tiempo empleado para confirmar los cambios es inferior a la que se emplearía procesando los objetos individualmente.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-111">As the transaction commits the changes, locks are put on the affected objects, making the objects temporarily unavailable, but overall the amount of time used to commit the changes is less than if you processed objects individually.</span></span>  
  
 <span data-ttu-id="b7bfe-112">Los procedimientos de este tema muestran los pasos para procesar completamente dimensiones y particiones.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-112">The procedures in this topic show the steps for fully processing dimensions and partitions.</span></span> <span data-ttu-id="b7bfe-113">El procesamiento por lotes también puede incluir otras opciones de procesamiento, como el procesamiento incremental.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-113">Batch processing can also include other processing options, such as incremental processing.</span></span> <span data-ttu-id="b7bfe-114">Para que estos procedimientos funcionen correctamente, debe usar una base de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] existente que contenga al menos dos dimensiones y una partición.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-114">For these procedures to work correctly, you should use an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that contains at least two dimensions and one partition.</span></span>  
  
 <span data-ttu-id="b7bfe-115">Este tema incluye las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="b7bfe-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="b7bfe-116">Procesamiento por lotes en SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="b7bfe-116">Batch Processing in SQL Server Data Tools</span></span>](#bkmk_ssdt)  
  
 [<span data-ttu-id="b7bfe-117">Procesamiento por lotes con XMLA en Management Studio</span><span class="sxs-lookup"><span data-stu-id="b7bfe-117">Batch Processing using XMLA in Management Studio</span></span>](#bkmk_xmla)  
  
##  <a name="batch-processing-in-sql-server-data-tools"></a><a name="bkmk_ssdt"></a> <span data-ttu-id="b7bfe-118">Procesamiento por lotes en SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="b7bfe-118">Batch Processing in SQL Server Data Tools</span></span>  
 <span data-ttu-id="b7bfe-119">Para poder procesar objetos en [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], se debe implementar el proyecto que contiene los objetos.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-119">Before objects can be processed in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], the project that contains the objects must be deployed.</span></span> <span data-ttu-id="b7bfe-120">Para más información, vea [Implementar proyectos de Analysis Services &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="b7bfe-120">For more information, see [Deploy Analysis Services Projects &#40;SSDT&#41;](deploy-analysis-services-projects-ssdt.md).</span></span>  
  
1.  <span data-ttu-id="b7bfe-121">Abra [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7bfe-121">Open [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="b7bfe-122">Abra un proyecto que se haya implementado.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-122">Open a project that has been deployed.</span></span>  
  
3.  <span data-ttu-id="b7bfe-123">En el Explorador de soluciones, debajo del proyecto implementado, expanda la carpeta **Dimensiones** .</span><span class="sxs-lookup"><span data-stu-id="b7bfe-123">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
4.  <span data-ttu-id="b7bfe-124">Manteniendo presionada la tecla Ctrl, haga clic en todas las dimensiones que aparecen en la carpeta **Dimensiones** .</span><span class="sxs-lookup"><span data-stu-id="b7bfe-124">Holding the Ctrl key, click each dimension listed in the **Dimensions** folder.</span></span>  
  
5.  <span data-ttu-id="b7bfe-125">Haga clic con el botón derecho en las dimensiones seleccionadas y luego haga clic en **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-125">Right-click the selected dimensions, and then click **Process**.</span></span>  
  
6.  <span data-ttu-id="b7bfe-126">Manteniendo presionada la tecla Ctrl, haga clic en todas las dimensiones que aparecen en la **lista de objetos**.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-126">Holding the Ctrl key, click each dimension listed in the **Object list**.</span></span>  
  
7.  <span data-ttu-id="b7bfe-127">Haga clic con el botón derecho en las dimensiones seleccionadas y seleccione **Proceso completo**.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-127">Right-click the selected dimensions and select **Process Full**.</span></span>  
  
8.  <span data-ttu-id="b7bfe-128">Para personalizar el trabajo de proceso por lotes, haga clic en **Cambiar configuración**.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-128">To customize the batch process job, click **Change Settings.**</span></span>  
  
9. <span data-ttu-id="b7bfe-129">En **Opciones de procesamiento**, marque la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="b7bfe-129">Under **Processing options**, mark the following settings:</span></span>  
  
    -   <span data-ttu-id="b7bfe-130">La opción**Orden de procesamiento** establecida en **Secuenciales**y la opción **Modo de transacción** establecida en **Una transacción**.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-130">**Processing Order** is set to **Sequential**, and **Transaction mode** is set to **One Transaction**.</span></span>  
  
    -   <span data-ttu-id="b7bfe-131">La opción**Opción de tabla de reescritura** establecida en **Utilizar existente**.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-131">**Writeback Table Option** is set to **Use existing**.</span></span>  
  
    -   <span data-ttu-id="b7bfe-132">En **Objetos afectados**, active la casilla **Procesar objetos afectados** .</span><span class="sxs-lookup"><span data-stu-id="b7bfe-132">Under **Affected Objects**, select the **Process affected objects** check box.</span></span>  
  
10. <span data-ttu-id="b7bfe-133">Haga clic en la pestaña **errores de clave de dimensión** . Compruebe que esté seleccionada la **opción usar configuración de error predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="b7bfe-133">Click the **Dimension key errors** tab. Verify that **Use default error configuration** is selected.</span></span>  
  
11. <span data-ttu-id="b7bfe-134">Haga clic en **Aceptar** para cerrar la pantalla **Cambiar configuración** .</span><span class="sxs-lookup"><span data-stu-id="b7bfe-134">Click **OK** to close the **Change Settings** screen.</span></span>  
  
12. <span data-ttu-id="b7bfe-135">Haga clic en **Ejecutar** en la pantalla **Procesar objetos** para iniciar el trabajo de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-135">Click **Run** in the **Process Objects** screen to start the processing job.</span></span>  
  
13. <span data-ttu-id="b7bfe-136">Cuando en el cuadro **Estado** se muestre **Proceso finalizado correctamente**, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-136">When the **Status** box shows **Process succeeded**, click **Close**.</span></span>  
  
14. <span data-ttu-id="b7bfe-137">Haga clic en **Cerrar** en la pantalla **Procesar objetos** .</span><span class="sxs-lookup"><span data-stu-id="b7bfe-137">Click **Close** on the **Process Objects** screen.</span></span>  
  
##  <a name="batch-processing-using-xmla-in-management-studio"></a><a name="bkmk_xmla"></a><span data-ttu-id="b7bfe-138">Procesamiento por lotes mediante XMLA en Management Studio</span><span class="sxs-lookup"><span data-stu-id="b7bfe-138">Batch Processing using XMLA in Management Studio</span></span>  
 <span data-ttu-id="b7bfe-139">Puede crear un script XMLA que realice el procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-139">You can create an XMLA script that performs batch processing.</span></span> <span data-ttu-id="b7bfe-140">Comience por generar un script XMLA en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para cada objeto y, a continuación combínelos en una única consulta XMLA que puede ejecutar interactivamente o en una tarea programada.</span><span class="sxs-lookup"><span data-stu-id="b7bfe-140">Start by generating an XMLA script in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] for each object, and then combine them into a single XMLA Query that you run interactively or inside a scheduled task.</span></span>  
  
 <span data-ttu-id="b7bfe-141">Para obtener instrucciones paso a paso, consulte el **ejemplo 2** en [programación de tareas administrativas de SSAS con Agente SQL Server](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md)</span><span class="sxs-lookup"><span data-stu-id="b7bfe-141">For step by step instructions, see **Example 2** in [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bfe-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7bfe-142">See Also</span></span>  
 [<span data-ttu-id="b7bfe-143">Procesamiento de objetos del modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="b7bfe-143">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
