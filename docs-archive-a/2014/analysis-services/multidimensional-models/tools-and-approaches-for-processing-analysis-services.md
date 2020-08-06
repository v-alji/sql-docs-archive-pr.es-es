---
title: Herramientas y enfoques para el procesamiento (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- process [Analysis Services]
- processing [Analysis Services]
ms.assetid: 82347a16-4145-4655-8adf-2a300f1fdf99
author: minewiskan
ms.author: owend
ms.openlocfilehash: d2b28ecf29adc8240f76ec9888f9d4cb06dda887
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673346"
---
# <a name="tools-and-approaches-for-processing-analysis-services"></a><span data-ttu-id="ef249-102">Herramientas y enfoques de procesamiento (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="ef249-102">Tools and Approaches for Processing (Analysis Services)</span></span>
  <span data-ttu-id="ef249-103">El procesamiento es una operación en la que Analysis Services consulta un origen de datos relacional y rellena objetos de Analysis Services utilizando esos datos.</span><span class="sxs-lookup"><span data-stu-id="ef249-103">Processing is an operation in which Analysis Services queries a relational data source and populates Analysis Services objects using that data.</span></span>  
  
 <span data-ttu-id="ef249-104">Como administrador del sistema de Analysis Services, puede ejecutar y supervisar el procesamiento de objetos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilizando estos enfoques:</span><span class="sxs-lookup"><span data-stu-id="ef249-104">As an Analysis Services system administrator, you can execute and monitor the processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects using these approaches:</span></span>  
  
-   <span data-ttu-id="ef249-105">Ejecutar el análisis de impacto para conocer las dependencias del objeto y el ámbito de las operaciones</span><span class="sxs-lookup"><span data-stu-id="ef249-105">Run Impact Analysis to understand object dependencies and scope of operations</span></span>  
  
-   <span data-ttu-id="ef249-106">Procesar objetos individuales en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef249-106">Process individual objects in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="ef249-107">Procesar objetos individuales o varios objetos en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef249-107">Process individual or multiple objects in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="ef249-108">Ejecutar el análisis de impacto para revisar una lista de objetos relacionados que estarán en estado no procesado como resultado de la acción actual</span><span class="sxs-lookup"><span data-stu-id="ef249-108">Run Impact Analysis to review a list of related objects that will be unprocessed as result of the current action.</span></span>  
  
-   <span data-ttu-id="ef249-109">Generar y ejecutar un script en una ventana Consulta XMLA de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para procesar objetos individuales o varios objetos</span><span class="sxs-lookup"><span data-stu-id="ef249-109">Generate and run a script in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to process individual or multiple objects</span></span>  
  
-   <span data-ttu-id="ef249-110">Utilizar cmdlets de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef249-110">Use [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] PowerShell cmdlets</span></span>  
  
-   <span data-ttu-id="ef249-111">Usar flujos de control y tareas en paquetes de [!INCLUDE[ssIS](../../includes/ssis-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef249-111">Use control flows and tasks in [!INCLUDE[ssIS](../../includes/ssis-md.md)] packages</span></span>  
  
-   <span data-ttu-id="ef249-112">Supervisar el procesamiento con SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="ef249-112">Monitor processing with SQL Server Profiler</span></span>  
  
-   <span data-ttu-id="ef249-113">Programar una solución personalizada mediante AMO</span><span class="sxs-lookup"><span data-stu-id="ef249-113">Program a custom solution using AMO.</span></span> <span data-ttu-id="ef249-114">Para más información, consulte [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span><span class="sxs-lookup"><span data-stu-id="ef249-114">For more information, see [Programming AMO OLAP Basic Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-basic-objects).</span></span>  
  
 <span data-ttu-id="ef249-115">El procesamiento es una operación altamente configurable, controlada por un conjunto de opciones de procesamiento que determinan si se produce un procesamiento completo o incremental en el nivel de objeto.</span><span class="sxs-lookup"><span data-stu-id="ef249-115">Processing is a highly configurable operation, controlled by a set of processing options that determine whether full or incremental processing occurs at the object level.</span></span> <span data-ttu-id="ef249-116">Para más información sobre las opciones de procesamiento, vea [Opciones y valores de procesamiento &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md) y [Procesar objetos de Analysis Services](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="ef249-116">For more information about processing options and objects, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md) and [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef249-117">En este tema se describen las herramientas y los enfoques para procesar modelos multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="ef249-117">This topic describes the tools and approaches for processing multidimensional models.</span></span> <span data-ttu-id="ef249-118">Para obtener más información sobre el procesamiento de modelos tabulares, vea [procesar base de datos, tabla o partición](../tabular-models/process-database-table-or-partition-analysis-services.md) y [procesar datos &#40;&#41;tabular de SSAS ](../process-data-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="ef249-118">For more information about processing tabular models, see [Process Database, Table, or Partition](../tabular-models/process-database-table-or-partition-analysis-services.md) and [Process Data &#40;SSAS Tabular&#41;](../process-data-ssas-tabular.md).</span></span>  
  
### <a name="processing-objects-in-sql-server-management-studio"></a><span data-ttu-id="ef249-119">Procesar objetos en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ef249-119">Processing objects in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="ef249-120">Inicie [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y conéctese a Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ef249-120">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="ef249-121">Haga clic con el botón derecho en el objeto de Analysis Services que quiera procesar y haga clic en **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="ef249-121">Right-click the Analysis Services object you want to process and then click **Process**.</span></span> <span data-ttu-id="ef249-122">Puede procesar datos en cualquiera de estos niveles:</span><span class="sxs-lookup"><span data-stu-id="ef249-122">You can process data at any of these levels:</span></span>  
  
    -   <span data-ttu-id="ef249-123">Bases de datos</span><span class="sxs-lookup"><span data-stu-id="ef249-123">Databases</span></span>  
  
    -   <span data-ttu-id="ef249-124">Cubos</span><span class="sxs-lookup"><span data-stu-id="ef249-124">Cubes</span></span>  
  
    -   <span data-ttu-id="ef249-125">Grupos de medida o particiones individuales en el grupo de medida</span><span class="sxs-lookup"><span data-stu-id="ef249-125">Measure Groups or individual partitions in the measure group</span></span>  
  
    -   <span data-ttu-id="ef249-126">Dimensions</span><span class="sxs-lookup"><span data-stu-id="ef249-126">Dimensions</span></span>  
  
    -   <span data-ttu-id="ef249-127">Modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="ef249-127">Mining Models</span></span>  
  
    -   <span data-ttu-id="ef249-128">Estructuras de minería de datos</span><span class="sxs-lookup"><span data-stu-id="ef249-128">Mining Structures</span></span>  
  
     <span data-ttu-id="ef249-129">Los objetos de Analysis Services son jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="ef249-129">Analysis Services objects are hierarchical.</span></span> <span data-ttu-id="ef249-130">Si elige una base de datos, el procesamiento puede producirse para todos los objetos contenidos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ef249-130">If you choose database, processing can occur for all of the objects contained in the database.</span></span> <span data-ttu-id="ef249-131">El hecho de que el procesamiento se produzca realmente variará en función de la opción de proceso que se seleccione y del estado del objeto.</span><span class="sxs-lookup"><span data-stu-id="ef249-131">Whether processing actually occurs will vary depending on the process option you select and the state of the object.</span></span> <span data-ttu-id="ef249-132">Concretamente, si un objeto no está procesado, el procesamiento de su objeto primario dará lugar al procesamiento de dicho objeto.</span><span class="sxs-lookup"><span data-stu-id="ef249-132">Specifically, if an object is unprocessed, processing its parent will result in that object getting processed.</span></span> <span data-ttu-id="ef249-133">Para obtener más información sobre las dependencias de objetos, vea [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span><span class="sxs-lookup"><span data-stu-id="ef249-133">For more information about object dependencies, see [Processing Analysis Services Objects](processing-analysis-services-objects.md).</span></span>  
  
3.  <span data-ttu-id="ef249-134">En el cuadro de diálogo **Procesar** , en **Opciones de proceso**, use el valor predeterminado proporcionado o seleccione una opción diferente de la lista.</span><span class="sxs-lookup"><span data-stu-id="ef249-134">In the **Process** dialog box, in **Process Options**, use the default value provided or select a different option from the list.</span></span> <span data-ttu-id="ef249-135">Para más información sobre cada opción, vea [Opciones y valores de procesamiento &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ef249-135">For more information about each option, see [Processing Options and Settings &#40;Analysis Services&#41;](processing-options-and-settings-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="ef249-136">Haga clic en **Análisis de impacto** para identificar y, opcionalmente, procesar objetos dependientes que se ven afectados si se procesan los objetos enumerados en el cuadro de diálogo Procesar.</span><span class="sxs-lookup"><span data-stu-id="ef249-136">Click **Impact Analysis** to identify and optionally process dependent objects that are affected if the objects listed in the Process dialog box are processed.</span></span>  
  
5.  <span data-ttu-id="ef249-137">Opcionalmente, haga clic en **Cambiar configuración** para modificar el orden de procesamiento, el comportamiento de procesamiento relativo a tipos de errores concretos y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="ef249-137">Optionally, click **Change Settings** to modify the processing order, processing behavior relative to specific types of errors, and other settings.</span></span>  
  
6.  <span data-ttu-id="ef249-138">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef249-138">Click **OK**.</span></span>  
  
     <span data-ttu-id="ef249-139">El cuadro de diálogo Progreso del proceso proporciona el estado actual de cada comando.</span><span class="sxs-lookup"><span data-stu-id="ef249-139">The Process Progress dialog box provides ongoing status for each command.</span></span> <span data-ttu-id="ef249-140">Si un mensaje de estado aparece truncado, puede hacer clic en **Ver detalles** para leer la totalidad del mismo.</span><span class="sxs-lookup"><span data-stu-id="ef249-140">If a status message is truncated, you can click **View Details** to read the entire message.</span></span>  
  
### <a name="processing-objects-in-sql-server-data-tools"></a><span data-ttu-id="ef249-141">Procesar objetos en Herramientas de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ef249-141">Processing Objects in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="ef249-142">Inicie [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] y abra un proyecto que se haya implementado.</span><span class="sxs-lookup"><span data-stu-id="ef249-142">Start [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open a project that has been deployed.</span></span>  
  
2.  <span data-ttu-id="ef249-143">En el Explorador de soluciones, debajo del proyecto implementado, expanda la carpeta **Dimensiones** .</span><span class="sxs-lookup"><span data-stu-id="ef249-143">In Solution Explorer, under the deployed project, expand the **Dimensions** folder.</span></span>  
  
3.  <span data-ttu-id="ef249-144">Haga clic con el botón derecho en una dimensión y, después, haga clic en **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="ef249-144">Right-click a dimension, and then click **Process**.</span></span> <span data-ttu-id="ef249-145">Puede hacer clic con el botón secundario en varias dimensiones para procesar varios objetos de una vez.</span><span class="sxs-lookup"><span data-stu-id="ef249-145">You can right-click multiple dimensions to process multiple objects at once.</span></span> <span data-ttu-id="ef249-146">Para más información, vea [Procesamiento por lotes &#40;Analysis Services&#41;](batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="ef249-146">For more information, see [Batch Processing &#40;Analysis Services&#41;](batch-processing-analysis-services.md).</span></span>  
  
4.  <span data-ttu-id="ef249-147">En el cuadro de diálogo **Procesar dimensión** , en la columna **Opciones de proceso** debajo de **Lista de objetos**, compruebe que la opción en esta columna sea **Procesar completo**.</span><span class="sxs-lookup"><span data-stu-id="ef249-147">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="ef249-148">En caso contrario, en **Opciones de proceso**, haga clic en la opción y seleccione **Proceso completo** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="ef249-148">If it is not, under **Process Options**, click the option, and select **Process Full** from the drop-down list.</span></span>  
  
5.  <span data-ttu-id="ef249-149">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ef249-149">Click **Run**.</span></span>  
  
6.  <span data-ttu-id="ef249-150">Cuando el procesamiento haya finalizado, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ef249-150">When processing is finished, click **Close**.</span></span>  
  
##  <a name="run-impact-analysis-to-identify-object-dependencies-and-scope-of-operations"></a><a name="bkmk_impactanalysis"></a><span data-ttu-id="ef249-151">Ejecutar el análisis de impacto para identificar las dependencias de objetos y el ámbito de las operaciones</span><span class="sxs-lookup"><span data-stu-id="ef249-151">Run Impact Analysis to identify object dependencies and scope of operations</span></span>  
  
1.  <span data-ttu-id="ef249-152">Antes de procesar un objeto de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], puede analizar el efecto sobre los objetos relacionados haciendo clic en **Análisis de impacto** en uno de los cuadros de diálogo **Procesar objetos** .</span><span class="sxs-lookup"><span data-stu-id="ef249-152">Before you process an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object in either [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], you can analyze the effect on related objects by clicking **Impact Analysis** in one of the **Process Objects** dialog boxes.</span></span>  
  
2.  <span data-ttu-id="ef249-153">Haga clic con el botón derecho en una dimensión, cubo, grupo de medida o partición para abrir un cuadro de diálogo **Procesar objetos** .</span><span class="sxs-lookup"><span data-stu-id="ef249-153">Right-click a dimension, cube, measure group, or partition to open a **Process Objects** dialog box.</span></span>  
  
3.  <span data-ttu-id="ef249-154">Haga clic en **Análisis de impacto**</span><span class="sxs-lookup"><span data-stu-id="ef249-154">Click **Impact Analysis**.</span></span> [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="ef249-155">examina el modelo e informa de los requisitos de nuevo procesamiento de los objetos relacionados con el objeto seleccionado para procesar.</span><span class="sxs-lookup"><span data-stu-id="ef249-155">scans the model and reports on reprocessing requirements for objects that are related to the one you selected for processing.</span></span>  
  
### <a name="processing-objects-using-xmla"></a><span data-ttu-id="ef249-156">Procesar objetos utilizando XMLA</span><span class="sxs-lookup"><span data-stu-id="ef249-156">Processing objects using XMLA</span></span>  
  
1.  <span data-ttu-id="ef249-157">Inicie [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y conéctese a Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="ef249-157">Start [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to Analysis Services.</span></span>  
  
2.  <span data-ttu-id="ef249-158">Haga clic con el botón derecho en el objeto que quiera procesar y, después, haga clic en **Procesar**.</span><span class="sxs-lookup"><span data-stu-id="ef249-158">Right-click the object to be processed and then click **Process**.</span></span>  
  
3.  <span data-ttu-id="ef249-159">En el cuadro de diálogo **Procesar** , seleccione la opción de proceso que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="ef249-159">In the **Process** dialog box, select the process option you want to use.</span></span> <span data-ttu-id="ef249-160">Modifique las opciones de configuración que desee.</span><span class="sxs-lookup"><span data-stu-id="ef249-160">Modify any other settings.</span></span> <span data-ttu-id="ef249-161">Ejecute el análisis de impacto para identificar los cambios que pueda necesitar realizar.</span><span class="sxs-lookup"><span data-stu-id="ef249-161">Run Impact Analysis to identify any changes you might need to make.</span></span>  
  
4.  <span data-ttu-id="ef249-162">Haga clic en **Script** en la pantalla **Procesar objetos** .</span><span class="sxs-lookup"><span data-stu-id="ef249-162">Click **Script** on the **Process Objects** screen.</span></span>  
  
     <span data-ttu-id="ef249-163">Este paso genera un script XMLA y abre una ventana Consulta XMLA de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ef249-163">This generates an XMLA script and opens an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] XMLA Query window.</span></span>  
  
5.  <span data-ttu-id="ef249-164">Cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ef249-164">Close the dialog box.</span></span> <span data-ttu-id="ef249-165">El script contiene el comando y las opciones de procesamiento que se especificaron en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ef249-165">The script contains the processing command and options that were specified in the dialog box.</span></span>  
  
6.  <span data-ttu-id="ef249-166">Opcionalmente, puede continuar agregando al script si desea procesar objetos adicionales en el mismo lote.</span><span class="sxs-lookup"><span data-stu-id="ef249-166">Optionally, you can continue adding to the script if you want to process additional objects in the same batch.</span></span> <span data-ttu-id="ef249-167">Para continuar, repita los pasos anteriores, anexando el script generado de forma que tenga un script único para todas las operaciones de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ef249-167">To continue, repeat the previous steps, appending the generated script so that you have a single script for all processing operations.</span></span> <span data-ttu-id="ef249-168">Para obtener un ejemplo, vea [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span><span class="sxs-lookup"><span data-stu-id="ef249-168">To view an example, see [Schedule SSAS Administrative Tasks with SQL Server Agent](../instances/schedule-ssas-administrative-tasks-with-sql-server-agent.md).</span></span>  
  
7.  <span data-ttu-id="ef249-169">En la barra de menús, haga clic en **Consulta**y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ef249-169">From the menu bar, click **Query**, and then click **Execute**.</span></span>  
  
### <a name="processing-objects-using-powershell"></a><span data-ttu-id="ef249-170">Procesar objetos utilizando PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef249-170">Processing objects using PowerShell</span></span>  
  
1.  <span data-ttu-id="ef249-171">A partir de esta versión de SQL Server, puede utilizar los cmdlets de Analysis Services PowerShell para procesar objetos.</span><span class="sxs-lookup"><span data-stu-id="ef249-171">Starting in this release of SQL Server, you can use Analysis Services PowerShell cmdlets to process objects.</span></span> <span data-ttu-id="ef249-172">Los cmdlets siguientes pueden ejecutarse de forma interactiva o en un script:</span><span class="sxs-lookup"><span data-stu-id="ef249-172">The following cmdlets can be run interactively or in script:</span></span>  
  
    -   [<span data-ttu-id="ef249-173">Cmdlet Invoke-ProcessCube</span><span class="sxs-lookup"><span data-stu-id="ef249-173">Invoke-ProcessCube cmdlet</span></span>](/powershell/module/sqlserver/invoke-processcube)  
  
    -   [<span data-ttu-id="ef249-174">Cmdlet Invoke-ProcessDimension</span><span class="sxs-lookup"><span data-stu-id="ef249-174">Invoke-ProcessDimension cmdlet</span></span>](/powershell/module/sqlserver/invoke-processdimension)  
  
    -   [<span data-ttu-id="ef249-175">Cmdlet Invoke-ProcessPartition</span><span class="sxs-lookup"><span data-stu-id="ef249-175">Invoke-ProcessPartition cmdlet</span></span>](/powershell/module/sqlserver/invoke-processpartition)  
  
    -   <span data-ttu-id="ef249-176">El[cmdlet Invoke-ASCmd](/powershell/module/sqlserver/invoke-ascmd), que se puede usar para ejecutar un script XMLA, MDX o DMX que incluya comandos de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ef249-176">[Invoke-ASCmd cmdlet](/powershell/module/sqlserver/invoke-ascmd), which can be used to execute XMLA, MDX, or DMX script that includes processing commands.</span></span>  
  
### <a name="monitoring-object-processing-using-sql-server-profiler"></a><span data-ttu-id="ef249-177">Supervisar el procesamiento de objetos mediante SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="ef249-177">Monitoring object processing using SQL Server Profiler</span></span>  
  
1.  <span data-ttu-id="ef249-178">Conéctese a una instancia de Analysis Services en SQL Server Profiler.</span><span class="sxs-lookup"><span data-stu-id="ef249-178">Connect to an Analysis Services instance in SQL Server Profiler.</span></span>  
  
2.  <span data-ttu-id="ef249-179">En Selección de eventos, haga clic en **Mostrar todos los eventos** para agregar todos los eventos a la lista.</span><span class="sxs-lookup"><span data-stu-id="ef249-179">In Events Selection, click **Show all events** to add all events to the list.</span></span>  
  
3.  <span data-ttu-id="ef249-180">Elija los siguientes eventos:</span><span class="sxs-lookup"><span data-stu-id="ef249-180">Choose the following events:</span></span>  
  
    -   <span data-ttu-id="ef249-181">**Inicio del comando** y **Fin del comando** para mostrar cuándo se inicia y se detiene el procesamiento</span><span class="sxs-lookup"><span data-stu-id="ef249-181">**Command Begin** and **Command End** to show when processing starts and stops</span></span>  
  
    -   <span data-ttu-id="ef249-182">**Error** para capturar errores</span><span class="sxs-lookup"><span data-stu-id="ef249-182">**Error** to capture any errors</span></span>  
  
    -   <span data-ttu-id="ef249-183">**Informe de progreso Inicio**, **Informe de progreso Actual**y **Fin del informe de progreso** para informar del estado del proceso y mostrar las consultas SQL usadas para recuperar los datos</span><span class="sxs-lookup"><span data-stu-id="ef249-183">**Progress Report Begin**, **Progress Report Current**, and **Progress Report End** to report on process status and show the SQL queries used to retrieve the data</span></span>  
  
    -   <span data-ttu-id="ef249-184">**Ejecutar script MDX Inicio** y **Ejecutar script MDX Final** para mostrar los cálculos del cubo</span><span class="sxs-lookup"><span data-stu-id="ef249-184">**Execute MDX Script Begin** and **Execute MDX Script End** to show the cube calculations</span></span>  
  
    -   <span data-ttu-id="ef249-185">Opcionalmente, agregue eventos de bloqueo si está diagnosticando problemas de rendimiento relacionados con el procesamiento</span><span class="sxs-lookup"><span data-stu-id="ef249-185">Optionally, add lock events if you are diagnosing performance problems related to processing</span></span>  
  
### <a name="process-analysis-services-objects-using-integration-services"></a><span data-ttu-id="ef249-186">Procesar objetos de Analysis Services mediante Integration Services</span><span class="sxs-lookup"><span data-stu-id="ef249-186">Process Analysis Services objects using Integration Services</span></span>  
  
1.  <span data-ttu-id="ef249-187">En [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], cree un paquete que use la tarea Procesamiento de Analysis Services para rellenar automáticamente objetos con datos nuevos cuando realice actualizaciones periódicas de la base de datos relacional de origen.</span><span class="sxs-lookup"><span data-stu-id="ef249-187">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], create a package that uses the Analysis Services Processing Task to automatically populate objects with new data when you make regular updates to your source relational database.</span></span>  
  
2.  <span data-ttu-id="ef249-188">En **Cuadro de herramientas de SSIS**, haga doble clic en **Procesamiento de Analysis Services** para agregarlo al paquete.</span><span class="sxs-lookup"><span data-stu-id="ef249-188">In the **SSIS Toolbox**, double-click **Analysis Services Processing** to add it to the package.</span></span>  
  
3.  <span data-ttu-id="ef249-189">Edite la tarea para especificar una conexión con la base de datos, qué objetos se van a procesar y la opción de proceso.</span><span class="sxs-lookup"><span data-stu-id="ef249-189">Edit the task to specify a connection to the database, which objects to process, and the process option.</span></span> <span data-ttu-id="ef249-190">Para obtener más información acerca de cómo implementar esta tarea, vea [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span><span class="sxs-lookup"><span data-stu-id="ef249-190">For more information about how to implement this task, see [Analysis Services Processing Task](../../integration-services/control-flow/analysis-services-processing-task.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef249-191">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef249-191">See Also</span></span>  
 [<span data-ttu-id="ef249-192">Procesamiento de objetos del modelo multidimensional</span><span class="sxs-lookup"><span data-stu-id="ef249-192">Multidimensional Model Object Processing</span></span>](processing-a-multidimensional-model-analysis-services.md)  
  
  
