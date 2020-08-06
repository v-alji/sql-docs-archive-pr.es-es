---
title: Mensajes personalizados para el registro | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], custom
- writing log entries
- SSIS packages, logs
- custom messages for logging [Integration Services]
ms.assetid: 3c74bba9-02b7-4bf5-bad5-19278b680730
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2b9f450c74ef6d46876adfde45729c71b3262449
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673205"
---
# <a name="custom-messages-for-logging"></a><span data-ttu-id="18223-102">Mensajes personalizados para registro</span><span class="sxs-lookup"><span data-stu-id="18223-102">Custom Messages for Logging</span></span>
  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="18223-103">proporciona a un amplio conjunto de eventos personalizados para escribir entradas del registro para paquetes y muchas tareas.</span><span class="sxs-lookup"><span data-stu-id="18223-103">provides a rich set of custom events for writing log entries for packages and many tasks.</span></span> <span data-ttu-id="18223-104">Puede utilizar estas entradas para guardar información detallada sobre el progreso, resultados y problemas de ejecución al registrar eventos predefinidos o mensajes definidos por el usuario para su análisis posterior.</span><span class="sxs-lookup"><span data-stu-id="18223-104">You can use these entries to save detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="18223-105">Por ejemplo, puede registrar cuando se inicia y finaliza la inserción masiva para identificar los problemas de rendimiento en la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="18223-105">For example, you can record when a bulk insert begins and ends to identify performance issues when the package runs.</span></span>  
  
 <span data-ttu-id="18223-106">Las entradas del registro personalizadas pertenecen a un conjunto de entradas diferente de los eventos estándar de registro que están disponibles para los paquetes y todos los contenedores y tareas.</span><span class="sxs-lookup"><span data-stu-id="18223-106">The custom log entries are a different set of entries than the set of standard logging events that are available for packages and all containers and tasks.</span></span> <span data-ttu-id="18223-107">Las entradas del registro personalizadas se han adaptado para capturar información de utilidad sobre una tarea específica de un paquete.</span><span class="sxs-lookup"><span data-stu-id="18223-107">The custom log entries are tailored to capture useful information about a specific task in a package.</span></span> <span data-ttu-id="18223-108">Por ejemplo, una de las entradas de registro personalizadas para la tarea Ejecutar SQL registra la instrucción SQL que ejecuta la tarea en el registro.</span><span class="sxs-lookup"><span data-stu-id="18223-108">For example, one of the custom log entries for the Execute SQL task records the SQL statement that the task executes in the log.</span></span>  
  
 <span data-ttu-id="18223-109">Todas las entradas del registro incluyen información de fecha y hora, incluidas las entradas del registro que se escriben automáticamente cuando se inicia o finaliza un paquete.</span><span class="sxs-lookup"><span data-stu-id="18223-109">All log entries include date and time information, including the log entries that are automatically written when a package begins and finishes.</span></span> <span data-ttu-id="18223-110">Muchos de los eventos de registro escriben varias entradas en el registro.</span><span class="sxs-lookup"><span data-stu-id="18223-110">Many of the log events write multiple entries to the log.</span></span> <span data-ttu-id="18223-111">Esto ocurre generalmente cuando los eventos tienen diferentes fases.</span><span class="sxs-lookup"><span data-stu-id="18223-111">This typically occurs when the event has different phases.</span></span> <span data-ttu-id="18223-112">Por ejemplo, el evento de registro `ExecuteSQLExecutingQuery` escribe tres entradas: una entrada después de que la tarea adquiere una conexión con la base de datos, otra después de que la tarea comienza a preparar la instrucción SQL y otra más una vez que se completa la ejecución de la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="18223-112">For example, the `ExecuteSQLExecutingQuery` log event writes three entries: one entry after the task acquires a connection to the database, another after the task starts to prepare the SQL statement, and one more after the execution of the SQL statement is completed.</span></span>  
  
 <span data-ttu-id="18223-113">Los siguientes objetos [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] poseen entradas del registro personalizadas:</span><span class="sxs-lookup"><span data-stu-id="18223-113">The following [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects have custom log entries:</span></span>  
  
 [<span data-ttu-id="18223-114">Package</span><span class="sxs-lookup"><span data-stu-id="18223-114">Package</span></span>](#Package)  
  
 [<span data-ttu-id="18223-115">Tarea Inserción masiva</span><span class="sxs-lookup"><span data-stu-id="18223-115">Bulk Insert Task</span></span>](#BulkInsert)  
  
 [<span data-ttu-id="18223-116">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="18223-116">Data Flow Task</span></span>](#DataFlow)  
  
 [<span data-ttu-id="18223-117">Tarea Ejecutar DTS 2000</span><span class="sxs-lookup"><span data-stu-id="18223-117">Execute DTS 2000 Task</span></span>](#ExecuteDTS200)  
  
 [<span data-ttu-id="18223-118">Tarea Ejecutar proceso</span><span class="sxs-lookup"><span data-stu-id="18223-118">Execute Process Task</span></span>](#ExecuteProcess)  
  
 [<span data-ttu-id="18223-119">Tarea Ejecutar SQL</span><span class="sxs-lookup"><span data-stu-id="18223-119">Execute SQL Task</span></span>](#ExecuteSQL)  
  
 [<span data-ttu-id="18223-120">Tarea Sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="18223-120">File System Task</span></span>](#FileSystem)  
  
 [<span data-ttu-id="18223-121">Tarea FTP</span><span class="sxs-lookup"><span data-stu-id="18223-121">FTP Task</span></span>](#FTP)  
  
 [<span data-ttu-id="18223-122">Tarea Cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="18223-122">Message Queue Task</span></span>](#MessageQueue)  
  
 [<span data-ttu-id="18223-123">Tarea Script</span><span class="sxs-lookup"><span data-stu-id="18223-123">Script Task</span></span>](#Script)  
  
 [<span data-ttu-id="18223-124">Tarea Enviar correo</span><span class="sxs-lookup"><span data-stu-id="18223-124">Send Mail Task</span></span>](#SendMail)  
  
 [<span data-ttu-id="18223-125">Tarea Transferir bases de datos</span><span class="sxs-lookup"><span data-stu-id="18223-125">Transfer Database Task</span></span>](#TransferDatabase)  
  
 [<span data-ttu-id="18223-126">Tarea Transferir mensajes de error</span><span class="sxs-lookup"><span data-stu-id="18223-126">Transfer Error Messages Task</span></span>](#TransferErrorMessages)  
  
 [<span data-ttu-id="18223-127">Tarea Transferir trabajos</span><span class="sxs-lookup"><span data-stu-id="18223-127">Transfer Jobs Task</span></span>](#TransferJobs)  
  
 [<span data-ttu-id="18223-128">Tarea Transferir inicios de sesión</span><span class="sxs-lookup"><span data-stu-id="18223-128">Transfer Logins Task</span></span>](#TransferLogins)  
  
 [<span data-ttu-id="18223-129">Tarea Transferir procedimientos almacenados principales</span><span class="sxs-lookup"><span data-stu-id="18223-129">Transfer Master Stored Procedures Task</span></span>](#TransferMasterStoredProcedures)  
  
 [<span data-ttu-id="18223-130">Tarea Transferir objetos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="18223-130">Transfer SQL Server Objects Task</span></span>](#TransferSQLServerObjects)  
  
 [<span data-ttu-id="18223-131">Tarea Servicios web</span><span class="sxs-lookup"><span data-stu-id="18223-131">Web Services Task</span></span>](#WebServices)  
  
 [<span data-ttu-id="18223-132">Tarea Lector de datos WMI</span><span class="sxs-lookup"><span data-stu-id="18223-132">WMI Data Reader Task</span></span>](#WMIDataReader)  
  
 [<span data-ttu-id="18223-133">Tarea Monitor de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="18223-133">WMI Event Watcher Task</span></span>](#WMIEventWatcher)  
  
 [<span data-ttu-id="18223-134">Tarea XML</span><span class="sxs-lookup"><span data-stu-id="18223-134">XML Task</span></span>](#XML)  
  
## <a name="log-entries"></a><span data-ttu-id="18223-135">Entradas del registro</span><span class="sxs-lookup"><span data-stu-id="18223-135">Log Entries</span></span>  
  
###  <a name="package"></a><a name="Package"></a> <span data-ttu-id="18223-136">Paquete</span><span class="sxs-lookup"><span data-stu-id="18223-136">Package</span></span>  
 <span data-ttu-id="18223-137">La siguiente tabla contiene las entradas del registro personalizadas para paquetes.</span><span class="sxs-lookup"><span data-stu-id="18223-137">The following table lists the custom log entries for packages.</span></span>  
  
|<span data-ttu-id="18223-138">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-138">Log entry</span></span>|<span data-ttu-id="18223-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-139">Description</span></span>|  
|---------------|-----------------|  
|`PackageStart`|<span data-ttu-id="18223-140">Indica que se inició la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="18223-140">Indicates that the package began to run.</span></span><br /><br /> <span data-ttu-id="18223-141">Nota: Esta entrada del registro se escribe automáticamente en el registro.</span><span class="sxs-lookup"><span data-stu-id="18223-141">Note: This log entry is automatically written to the log.</span></span> <span data-ttu-id="18223-142">No se puede excluir.</span><span class="sxs-lookup"><span data-stu-id="18223-142">You cannot exclude it.</span></span>|  
|`PackageEnd`|<span data-ttu-id="18223-143">Indica que finalizó la ejecución del paquete.</span><span class="sxs-lookup"><span data-stu-id="18223-143">Indicates that the package completed.</span></span><br /><br /> <span data-ttu-id="18223-144">Nota: Esta entrada del registro se escribe automáticamente en el registro.</span><span class="sxs-lookup"><span data-stu-id="18223-144">Note: This log entry is automatically written to the log.</span></span> <span data-ttu-id="18223-145">No se puede excluir.</span><span class="sxs-lookup"><span data-stu-id="18223-145">You cannot exclude it.</span></span>|  
|`Diagnostic`|<span data-ttu-id="18223-146">Proporciona información sobre la configuración del sistema que afecta a la ejecución de paquetes, como el número de ejecutables que se pueden ejecutar simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="18223-146">Provides information about the system configuration that affects package execution such as the number executables that can be run concurrently.</span></span><br /><br /> <span data-ttu-id="18223-147">La entrada del registro `Diagnostic` también incluye entradas por delante y por detrás relativas a las llamadas a proveedores de datos externos.</span><span class="sxs-lookup"><span data-stu-id="18223-147">The `Diagnostic` log entry also includes before and after entries for calls to external data providers.</span></span> <span data-ttu-id="18223-148">Para obtener más información, consulte [Troubleshooting Tools Package Connectivity](troubleshooting/troubleshooting-tools-for-package-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="18223-148">For more information, see [Troubleshooting Tools Package Connectivity](troubleshooting/troubleshooting-tools-for-package-connectivity.md).</span></span>|  
  
###  <a name="bulk-insert-task"></a><a name="BulkInsert"></a> <span data-ttu-id="18223-149">Tarea Inserción masiva</span><span class="sxs-lookup"><span data-stu-id="18223-149">Bulk Insert Task</span></span>  
 <span data-ttu-id="18223-150">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="18223-150">The following table lists the custom log entries for the Bulk Insert task.</span></span>  
  
|<span data-ttu-id="18223-151">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-151">Log entry</span></span>|<span data-ttu-id="18223-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-152">Description</span></span>|  
|---------------|-----------------|  
|`DTSBulkInsertTaskBegin`|<span data-ttu-id="18223-153">Indica que se inició la inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="18223-153">Indicates that the bulk insert began.</span></span>|  
|`DTSBulkInsertTaskEnd`|<span data-ttu-id="18223-154">Indica que finalizó la inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="18223-154">Indicates that the bulk insert finished.</span></span>|  
|`DTSBulkInsertTaskInfos`|<span data-ttu-id="18223-155">Proporciona información descriptiva sobre la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-155">Provides descriptive information about the task.</span></span>|  
  
###  <a name="data-flow-task"></a><a name="DataFlow"></a> <span data-ttu-id="18223-156">Data Flow Task</span><span class="sxs-lookup"><span data-stu-id="18223-156">Data Flow Task</span></span>  
 <span data-ttu-id="18223-157">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="18223-157">The following table lists the custom log entries for the Data Flow task.</span></span>  
  
|<span data-ttu-id="18223-158">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-158">Log entry</span></span>|<span data-ttu-id="18223-159">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-159">Description</span></span>|  
|---------------|-----------------|  
|`BufferSizeTuning`|<span data-ttu-id="18223-160">Indica que la tarea Flujo de datos cambió el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="18223-160">Indicates that the Data Flow task changed the size of the buffer.</span></span> <span data-ttu-id="18223-161">En la entrada del registro se describen las razones del cambio de tamaño y se indica el nuevo tamaño temporal del búfer.</span><span class="sxs-lookup"><span data-stu-id="18223-161">The log entry describes the reasons for the size change and lists the temporary new buffer size.</span></span>|  
|`OnPipelinePostEndOfRowset`|<span data-ttu-id="18223-162">Indica que se ha dado la señal de fin del conjunto de filas a un componente, la cual se establece a través de la última llamada del método `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="18223-162">Denotes that a component has been given its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="18223-163">Se escribe una entrada por cada componente del flujo de datos que procesa la entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="18223-163">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="18223-164">La entrada incluye el nombre del componente.</span><span class="sxs-lookup"><span data-stu-id="18223-164">The entry includes the name of the component.</span></span>|  
|`OnPipelinePostPrimeOutput`|<span data-ttu-id="18223-165">Indica que el componente ha completado su última llamada al método `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="18223-165">Indicates that the component has completed its last call to the `PrimeOutput` method.</span></span> <span data-ttu-id="18223-166">En función del flujo de datos, es posible que se escriban varias entradas.</span><span class="sxs-lookup"><span data-stu-id="18223-166">Depending on the data flow, multiple log entries may be written.</span></span> <span data-ttu-id="18223-167">Si el componente es un origen, esto significa que el componente ha terminado de procesar filas.</span><span class="sxs-lookup"><span data-stu-id="18223-167">If the component is a source, this means that the component has finished processing rows.</span></span>|  
|`OnPipelinePreEndOfRowset`|<span data-ttu-id="18223-168">Indica que un componente está a punto de recibir la señal de fin del conjunto de filas, la cual se establece a través de la última llamada del método `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="18223-168">Indicates that a component is about to receive its end-of-rowset signal, which is set by the last call of the `ProcessInput` method.</span></span> <span data-ttu-id="18223-169">Se escribe una entrada por cada componente del flujo de datos que procesa la entrada de datos.</span><span class="sxs-lookup"><span data-stu-id="18223-169">An entry is written for each component in the data flow that processes input.</span></span> <span data-ttu-id="18223-170">La entrada incluye el nombre del componente.</span><span class="sxs-lookup"><span data-stu-id="18223-170">The entry includes the name of the component.</span></span>|  
|`OnPipelinePrePrimeOutput`|<span data-ttu-id="18223-171">Indica que el componente está a punto de recibir su última llamada del método `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="18223-171">Indicates that the component is about to receive its call from the `PrimeOutput` method.</span></span> <span data-ttu-id="18223-172">En función del flujo de datos, es posible que se escriban varias entradas.</span><span class="sxs-lookup"><span data-stu-id="18223-172">Depending on the data flow, multiple log entries may be written.</span></span>|  
|`OnPipelineRowsSent`|<span data-ttu-id="18223-173">Informa del número de filas que se proporciona a una entrada de componentes a través de una llamada al método `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="18223-173">Reports the number of rows provided to a component input by a call to the `ProcessInput` method.</span></span> <span data-ttu-id="18223-174">La entrada del registro incluye el nombre del componente.</span><span class="sxs-lookup"><span data-stu-id="18223-174">The log entry includes the component name.</span></span>|  
|`PipelineBufferLeak`|<span data-ttu-id="18223-175">Proporciona información sobre cualquier componente que mantuvo la conexión de los búferes después de que desapareciera el administrador de búferes.</span><span class="sxs-lookup"><span data-stu-id="18223-175">Provides information about any component that kept buffers alive after the buffer manager goes away.</span></span> <span data-ttu-id="18223-176">Esto significa que no se liberaron los recursos de los búferes y podría ocasionar pérdidas de memoria.</span><span class="sxs-lookup"><span data-stu-id="18223-176">This means that buffers resources were not released and may cause memory leaks.</span></span> <span data-ttu-id="18223-177">La entrada del registro proporciona el nombre del componente y el Id. del búfer.</span><span class="sxs-lookup"><span data-stu-id="18223-177">The log entry provides the name of the component and the ID of the buffer.</span></span>|  
|`PipelineExecutionPlan`|<span data-ttu-id="18223-178">Informa del plan de ejecución del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="18223-178">Reports the execution plan of the data flow.</span></span> <span data-ttu-id="18223-179">Proporciona información sobre cómo se van a enviar los búferes a los componentes.</span><span class="sxs-lookup"><span data-stu-id="18223-179">It provides information about how buffers will be sent to components.</span></span> <span data-ttu-id="18223-180">Esta información, junto con la entrada PipelineExecutionTrees, explica lo que ocurre en la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-180">This information, in combination with the PipelineExecutionTrees entry, describes what is occurring in the task.</span></span>|  
|`PipelineExecutionTrees`|<span data-ttu-id="18223-181">Informa sobre los árboles de ejecución del diseño del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="18223-181">Reports the execution trees of the layout in the data flow.</span></span> <span data-ttu-id="18223-182">El programador del motor de flujo de datos utiliza los árboles para generar el plan de ejecución del flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="18223-182">The scheduler of the data flow engine use the trees to build the execution plan of the data flow.</span></span>|  
|`PipelineInitialization`|<span data-ttu-id="18223-183">Proporciona información de inicialización sobre la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-183">Provides initialization information about the task.</span></span> <span data-ttu-id="18223-184">Esta información incluye los directorios que se utilizan para el almacenamiento temporal de datos BLOB, el tamaño predeterminado del búfer y la cantidad de filas de un búfer.</span><span class="sxs-lookup"><span data-stu-id="18223-184">This information includes the directories to use for temporary storage of BLOB data, the default buffer size, and the number of rows in a buffer.</span></span> <span data-ttu-id="18223-185">En función de la configuración de la tarea Flujo de datos, es posible que se escriban varias entradas.</span><span class="sxs-lookup"><span data-stu-id="18223-185">Depending on the configuration of the Data Flow task, multiple log entries may be written.</span></span>|  
  
###  <a name="execute-dts-2000-task"></a><a name="ExecuteDTS200"></a> <span data-ttu-id="18223-186">Tarea Ejecutar DTS 2000</span><span class="sxs-lookup"><span data-stu-id="18223-186">Execute DTS 2000 Task</span></span>  
 <span data-ttu-id="18223-187">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Ejecutar DTS 2000.</span><span class="sxs-lookup"><span data-stu-id="18223-187">The following table lists the custom log entries for the Execute DTS 2000 task.</span></span>  
  
|<span data-ttu-id="18223-188">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-188">Log entry</span></span>|<span data-ttu-id="18223-189">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-189">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteDTS80PackageTaskBegin`|<span data-ttu-id="18223-190">Indica que la tarea inició la ejecución del paquete DTS 2000.</span><span class="sxs-lookup"><span data-stu-id="18223-190">Indicates that the task began to run a DTS 2000 package.</span></span>|  
|`ExecuteDTS80PackageTaskEnd`|<span data-ttu-id="18223-191">Indica que finalizó la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-191">Indicates that the task finished.</span></span><br /><br /> <span data-ttu-id="18223-192">Nota: Es posible que el paquete DTS 2000 continúe ejecutándose una vez finalizada la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-192">Note: The DTS 2000 package may continue to run after the task ends.</span></span>|  
|`ExecuteDTS80PackageTaskTaskInfo`|<span data-ttu-id="18223-193">Proporciona información descriptiva sobre la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-193">Provides descriptive information about the task.</span></span>|  
|`ExecuteDTS80PackageTaskTaskResult`|<span data-ttu-id="18223-194">Informa del resultado de la ejecución del paquete DTS 2000 que ejecutó la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-194">Reports the execution result of the DTS 2000 package that the task ran.</span></span>|  
  
###  <a name="execute-process-task"></a><a name="ExecuteProcess"></a> <span data-ttu-id="18223-195">Tarea Ejecutar proceso</span><span class="sxs-lookup"><span data-stu-id="18223-195">Execute Process Task</span></span>  
 <span data-ttu-id="18223-196">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Ejecutar proceso.</span><span class="sxs-lookup"><span data-stu-id="18223-196">The following table lists the custom log entries for the Execute Process task.</span></span>  
  
|<span data-ttu-id="18223-197">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-197">Log entry</span></span>|<span data-ttu-id="18223-198">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-198">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteProcessExecutingProcess`|<span data-ttu-id="18223-199">Proporciona información sobre el proceso de ejecución del ejecutable que se configuró para que ejecute la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-199">Provides information about the process of running the executable that the task is configured to run.</span></span><br /><br /> <span data-ttu-id="18223-200">Se escriben dos entradas del registro.</span><span class="sxs-lookup"><span data-stu-id="18223-200">Two log entries are written.</span></span> <span data-ttu-id="18223-201">Una entrada contiene información sobre el nombre y la ubicación del ejecutable que ejecuta la tarea y la otra entrada registra la salida del ejecutable.</span><span class="sxs-lookup"><span data-stu-id="18223-201">One contains information about the name and location of the executable that the task runs, and the other records the exit from the executable.</span></span>|  
|`ExecuteProcessVariableRouting`|<span data-ttu-id="18223-202">Proporciona información acerca de las variables que se enrutan a la entrada y las salidas del ejecutable.</span><span class="sxs-lookup"><span data-stu-id="18223-202">Provides information about which variables are routed to the input and outputs of the executable.</span></span> <span data-ttu-id="18223-203">Se escriben entradas del registro para stdin (la entrada), stdout (la salida) y stderr (la salida de errores).</span><span class="sxs-lookup"><span data-stu-id="18223-203">Log entries are written for stdin (the input), stdout (the output), and stderr (the error output).</span></span>|  
  
###  <a name="execute-sql-task"></a><a name="ExecuteSQL"></a> <span data-ttu-id="18223-204">Tarea Ejecutar SQL</span><span class="sxs-lookup"><span data-stu-id="18223-204">Execute SQL Task</span></span>  
 <span data-ttu-id="18223-205">La siguiente tabla contiene la entrada del registro personalizada para la tarea Ejecutar SQL.</span><span class="sxs-lookup"><span data-stu-id="18223-205">The following table describes the custom log entry for the Execute SQL task.</span></span>  
  
|<span data-ttu-id="18223-206">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-206">Log entry</span></span>|<span data-ttu-id="18223-207">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-207">Description</span></span>|  
|---------------|-----------------|  
|`ExecuteSQLExecutingQuery`|<span data-ttu-id="18223-208">Proporciona información sobre las fases de ejecución de la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="18223-208">Provides information about the execution phases of the SQL statement.</span></span> <span data-ttu-id="18223-209">Las entradas de registro se escriben cuando la tarea adquiere una conexión con la base de datos, cuando la tarea comienza a preparar la instrucción SQL y una vez que se completa la ejecución de la instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="18223-209">Log entries are written when the task acquires connection to the database, when the task starts to prepare the SQL statement, and after the execution of the SQL statement is completed.</span></span> <span data-ttu-id="18223-210">La entrada del registro para la fase de preparación incluye la instrucción SQL que utiliza la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-210">The log entry for the prepare phase includes the SQL statement that the task uses.</span></span>|  
  
###  <a name="file-system-task"></a><a name="FileSystem"></a> <span data-ttu-id="18223-211">Tarea Sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="18223-211">File System Task</span></span>  
 <span data-ttu-id="18223-212">La siguiente tabla contiene las entradas de registro personalizadas para la tarea Sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="18223-212">The following table describes the custom log entry for the File System task.</span></span>  
  
|<span data-ttu-id="18223-213">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-213">Log entry</span></span>|<span data-ttu-id="18223-214">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-214">Description</span></span>|  
|---------------|-----------------|  
|`FileSystemOperation`|<span data-ttu-id="18223-215">Informa sobre la operación que realiza la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-215">Reports the operation that the task performs.</span></span> <span data-ttu-id="18223-216">La entrada del registro se escribe cuando se inicia la operación del sistema de archivos e incluye información sobre el origen y el destino.</span><span class="sxs-lookup"><span data-stu-id="18223-216">The log entry is written when the file system operation starts and includes information about the source and destination.</span></span>|  
  
###  <a name="ftp-task"></a><a name="FTP"></a> <span data-ttu-id="18223-217">Tarea FTP</span><span class="sxs-lookup"><span data-stu-id="18223-217">FTP Task</span></span>  
 <span data-ttu-id="18223-218">La siguiente tabla contiene las entradas del registro personalizadas para la tarea FTP.</span><span class="sxs-lookup"><span data-stu-id="18223-218">The following table lists the custom log entries for the FTP task.</span></span>  
  
|<span data-ttu-id="18223-219">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-219">Log entry</span></span>|<span data-ttu-id="18223-220">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-220">Description</span></span>|  
|---------------|-----------------|  
|`FTPConnectingToServer`|<span data-ttu-id="18223-221">Indica que la tarea inició una conexión con el servidor FTP.</span><span class="sxs-lookup"><span data-stu-id="18223-221">Indicates that the task initiated a connection to the FTP server.</span></span>|  
|`FTPOperation`|<span data-ttu-id="18223-222">Informa del comienzo y del tipo de operación de FTP que realiza la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-222">Reports the beginning of and the type of FTP operation that the task performs.</span></span>|  
  
###  <a name="message-queue-task"></a><a name="MessageQueue"></a> <span data-ttu-id="18223-223">Tarea Cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="18223-223">Message Queue Task</span></span>  
 <span data-ttu-id="18223-224">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="18223-224">The following table lists the custom log entries for the Message Queue task.</span></span>  
  
|<span data-ttu-id="18223-225">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-225">Log entry</span></span>|<span data-ttu-id="18223-226">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-226">Description</span></span>|  
|---------------|-----------------|  
|`MSMQAfterOpen`|<span data-ttu-id="18223-227">Indica que la tarea finalizó la apertura de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="18223-227">Indicates that the task finished opening the message queue.</span></span>|  
|`MSMQBeforeOpen`|<span data-ttu-id="18223-228">Indica que la tarea inició la apertura de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="18223-228">Indicates that the task began to open the message queue.</span></span>|  
|`MSMQBeginReceive`|<span data-ttu-id="18223-229">Indica que la tarea comenzó a recibir un mensaje.</span><span class="sxs-lookup"><span data-stu-id="18223-229">Indicates that the task began to receive a message.</span></span>|  
|`MSMQBeginSend`|<span data-ttu-id="18223-230">Indica que la tarea comenzó a enviar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="18223-230">Indicates that the task began to send a message.</span></span>|  
|`MSMQEndReceive`|<span data-ttu-id="18223-231">Indica que la tarea finalizó la recepción de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="18223-231">Indicates that the task finished receiving a message.</span></span>|  
|`MSMQEndSend`|<span data-ttu-id="18223-232">Indica que la tarea finalizó el envío de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="18223-232">Indicates that the task finished sending a message</span></span>|  
|`MSMQTaskInfo`|<span data-ttu-id="18223-233">Proporciona información descriptiva sobre la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-233">Provides descriptive information about the task.</span></span>|  
|`MSMQTaskTimeOut`|<span data-ttu-id="18223-234">Indica que se superó el tiempo de espera de la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-234">Indicates that the task timed out.</span></span>|  
  
###  <a name="script-task"></a><a name="Script"></a> <span data-ttu-id="18223-235">Tarea Script</span><span class="sxs-lookup"><span data-stu-id="18223-235">Script Task</span></span>  
 <span data-ttu-id="18223-236">La siguiente tabla contiene la entrada personalizada de registro para la tarea Script.</span><span class="sxs-lookup"><span data-stu-id="18223-236">The following table describes the custom log entry for the Script task.</span></span>  
  
|<span data-ttu-id="18223-237">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-237">Log entry</span></span>|<span data-ttu-id="18223-238">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-238">Description</span></span>|  
|---------------|-----------------|  
|`ScriptTaskLogEntry`|<span data-ttu-id="18223-239">Informa sobre los resultados de la implementación del registro en el script.</span><span class="sxs-lookup"><span data-stu-id="18223-239">Reports the results of implementing logging in the script.</span></span> <span data-ttu-id="18223-240">Se escribe una entrada de registro para cada llamada al método `Log` del objeto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="18223-240">A log entry is written for each call to the `Log` method of the `Dts` object.</span></span> <span data-ttu-id="18223-241">La entrada se escribe cuando se ejecuta el código.</span><span class="sxs-lookup"><span data-stu-id="18223-241">The entry is written when the code is run.</span></span> <span data-ttu-id="18223-242">Para más información, consulte [Logging in the Script Task](extending-packages-scripting/task/logging-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="18223-242">For more information, see [Logging in the Script Task](extending-packages-scripting/task/logging-in-the-script-task.md).</span></span>|  
  
###  <a name="send-mail-task"></a><a name="SendMail"></a> <span data-ttu-id="18223-243">Tarea Enviar correo</span><span class="sxs-lookup"><span data-stu-id="18223-243">Send Mail Task</span></span>  
 <span data-ttu-id="18223-244">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Enviar correo.</span><span class="sxs-lookup"><span data-stu-id="18223-244">The following table lists the custom log entries for the Send Mail task.</span></span>  
  
|<span data-ttu-id="18223-245">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-245">Log entry</span></span>|<span data-ttu-id="18223-246">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-246">Description</span></span>|  
|---------------|-----------------|  
|`SendMailTaskBegin`|<span data-ttu-id="18223-247">Indica que la tarea comenzó a enviar un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="18223-247">Indicates that the task began to send an e-mail message.</span></span>|  
|`SendMailTaskEnd`|<span data-ttu-id="18223-248">Indica que la tarea finalizó el envío de un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="18223-248">Indicates that the task finished sending an e-mail message.</span></span>|  
|`SendMailTaskInfo`|<span data-ttu-id="18223-249">Proporciona información descriptiva sobre la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-249">Provides descriptive information about the task.</span></span>|  
  
###  <a name="transfer-database-task"></a><a name="TransferDatabase"></a> <span data-ttu-id="18223-250">Tarea Transferir bases de datos</span><span class="sxs-lookup"><span data-stu-id="18223-250">Transfer Database Task</span></span>  
 <span data-ttu-id="18223-251">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Transferir bases de datos.</span><span class="sxs-lookup"><span data-stu-id="18223-251">The following table lists the custom log entries for the Transfer Database task.</span></span>  
  
|<span data-ttu-id="18223-252">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-252">Log entry</span></span>|<span data-ttu-id="18223-253">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-253">Description</span></span>|  
|---------------|-----------------|  
|`SourceDB`|<span data-ttu-id="18223-254">Especifica la base de datos que copió la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-254">Specifies the database that the task copied.</span></span>|  
|`SourceSQLServer`|<span data-ttu-id="18223-255">Especifica el equipo desde el que se copió la base de datos.</span><span class="sxs-lookup"><span data-stu-id="18223-255">Specifies the computer from which the database was copied.</span></span>|  
  
###  <a name="transfer-error-messages-task"></a><a name="TransferErrorMessages"></a> <span data-ttu-id="18223-256">Tarea Transferir mensajes de error</span><span class="sxs-lookup"><span data-stu-id="18223-256">Transfer Error Messages Task</span></span>  
 <span data-ttu-id="18223-257">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Transferir mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="18223-257">The following table lists the custom log entries for the Transfer Error Messages task.</span></span>  
  
|<span data-ttu-id="18223-258">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-258">Log entry</span></span>|<span data-ttu-id="18223-259">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-259">Description</span></span>|  
|---------------|-----------------|  
|`TransferErrorMessagesTaskFinishedTransferringObjects`|<span data-ttu-id="18223-260">Indica que la tarea finalizó la transferencia de los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="18223-260">Indicates that the task finished transferring error messages.</span></span>|  
|`TransferErrorMessagesTaskStartTransferringObjects`|<span data-ttu-id="18223-261">Indica que la tarea inició la transferencia de los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="18223-261">Indicates that the task started to transfer error messages.</span></span>|  
  
###  <a name="transfer-jobs-task"></a><a name="TransferJobs"></a> <span data-ttu-id="18223-262">Tarea Transferir trabajos</span><span class="sxs-lookup"><span data-stu-id="18223-262">Transfer Jobs Task</span></span>  
 <span data-ttu-id="18223-263">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Transferir trabajos.</span><span class="sxs-lookup"><span data-stu-id="18223-263">The following table lists the custom log entries for the Transfer Jobs task.</span></span>  
  
|<span data-ttu-id="18223-264">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-264">Log entry</span></span>|<span data-ttu-id="18223-265">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-265">Description</span></span>|  
|---------------|-----------------|  
|`TransferJobsTaskFinishedTransferringObjects`|<span data-ttu-id="18223-266">Indica que la tarea finalizó la transferencia de los trabajos del Agente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18223-266">Indicates that the task finished transferring [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs.</span></span>|  
|`TransferJobsTaskStartTransferringObjects`|<span data-ttu-id="18223-267">Indica que la tarea inició la transferencia de los trabajos del Agente de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18223-267">Indicates that the task started to transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent jobs.</span></span>|  
  
###  <a name="transfer-logins-task"></a><a name="TransferLogins"></a> <span data-ttu-id="18223-268">Tarea Transferir inicios de sesión</span><span class="sxs-lookup"><span data-stu-id="18223-268">Transfer Logins Task</span></span>  
 <span data-ttu-id="18223-269">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Transferir inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="18223-269">The following table lists the custom log entries for the Transfer Logins task.</span></span>  
  
|<span data-ttu-id="18223-270">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-270">Log entry</span></span>|<span data-ttu-id="18223-271">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-271">Description</span></span>|  
|---------------|-----------------|  
|`TransferLoginsTaskFinishedTransferringObjects`|<span data-ttu-id="18223-272">Indica que la tarea finalizó la transferencia de inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="18223-272">Indicates that the task finished transferring logins.</span></span>|  
|`TransferLoginsTaskStartTransferringObjects`|<span data-ttu-id="18223-273">Indica que la tarea inició la transferencia de los inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="18223-273">Indicates that the task started to transfer logins.</span></span>|  
  
###  <a name="transfer-master-stored-procedures-task"></a><a name="TransferMasterStoredProcedures"></a> <span data-ttu-id="18223-274">Tarea Transferir procedimientos almacenados principales</span><span class="sxs-lookup"><span data-stu-id="18223-274">Transfer Master Stored Procedures Task</span></span>  
 <span data-ttu-id="18223-275">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Transferir procedimientos almacenados principales.</span><span class="sxs-lookup"><span data-stu-id="18223-275">The following table lists the custom log entries for the Transfer Master Stored Procedures task.</span></span>  
  
|<span data-ttu-id="18223-276">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-276">Log entry</span></span>|<span data-ttu-id="18223-277">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-277">Description</span></span>|  
|---------------|-----------------|  
|`TransferStoredProceduresTaskFinishedTransferringObjects`|<span data-ttu-id="18223-278">Indica que la tarea finalizó la transferencia de los procedimientos almacenados definidos por el usuario que están almacenados en la base de datos **maestra** .</span><span class="sxs-lookup"><span data-stu-id="18223-278">Indicates that the task finished transferring user-defined stored procedures that are stored in the **master** database.</span></span>|  
|`TransferStoredProceduresTaskStartTransferringObjects`|<span data-ttu-id="18223-279">Indica que la tarea inició la transferencia de los procedimientos almacenados definidos por el usuario que están almacenados en la base de datos **maestra** .</span><span class="sxs-lookup"><span data-stu-id="18223-279">Indicates that the task started to transfer user-defined stored procedures that are stored in the **master** database.</span></span>|  
  
###  <a name="transfer-sql-server-objects-task"></a><a name="TransferSQLServerObjects"></a> <span data-ttu-id="18223-280">Tarea Transferir objetos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="18223-280">Transfer SQL Server Objects Task</span></span>  
 <span data-ttu-id="18223-281">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Transferir objetos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18223-281">The following table lists the custom log entries for the Transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Objects task.</span></span>  
  
|<span data-ttu-id="18223-282">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-282">Log entry</span></span>|<span data-ttu-id="18223-283">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-283">Description</span></span>|  
|---------------|-----------------|  
|`TransferSqlServerObjectsTaskFinishedTransferringObjects`|<span data-ttu-id="18223-284">Indica que la tarea finalizó la transferencia de los objetos de base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18223-284">Indicates that the task finished transferring [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database objects.</span></span>|  
|`TransferSqlServerObjectsTaskStartTransferringObjects`|<span data-ttu-id="18223-285">Indica que la tarea inició la transferencia de los objetos de base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="18223-285">Indicates that the task started to transfer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database objects.</span></span>|  
  
###  <a name="web-services-task"></a><a name="WebServices"></a> <span data-ttu-id="18223-286">Tarea Servicios web</span><span class="sxs-lookup"><span data-stu-id="18223-286">Web Services Task</span></span>  
 <span data-ttu-id="18223-287">La siguiente tabla contiene las entradas del registro personalizadas que puede habilitar para la tarea Servicios web.</span><span class="sxs-lookup"><span data-stu-id="18223-287">The following table lists the custom log entries that you can enable for the Web Services task.</span></span>  
  
|<span data-ttu-id="18223-288">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-288">Log entry</span></span>|<span data-ttu-id="18223-289">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-289">Description</span></span>|  
|---------------|-----------------|  
|`WSTaskBegin`|<span data-ttu-id="18223-290">La tarea inició el acceso a un servicio web.</span><span class="sxs-lookup"><span data-stu-id="18223-290">The task began to access a Web service.</span></span>|  
|`WSTaskEnd`|<span data-ttu-id="18223-291">La tarea completó un método de servicio web.</span><span class="sxs-lookup"><span data-stu-id="18223-291">The task completed a Web service method.</span></span>|  
|`WSTaskInfo`|<span data-ttu-id="18223-292">Información descriptiva acerca de la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-292">Descriptive information about the task.</span></span>|  
  
###  <a name="wmi-data-reader-task"></a><a name="WMIDataReader"></a> <span data-ttu-id="18223-293">Tarea Lector de datos WMI</span><span class="sxs-lookup"><span data-stu-id="18223-293">WMI Data Reader Task</span></span>  
 <span data-ttu-id="18223-294">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Lector de datos WMI.</span><span class="sxs-lookup"><span data-stu-id="18223-294">The following table lists the custom log entries for the WMI Data Reader task.</span></span>  
  
|<span data-ttu-id="18223-295">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-295">Log entry</span></span>|<span data-ttu-id="18223-296">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-296">Description</span></span>|  
|---------------|-----------------|  
|`WMIDataReaderGettingWMIData`|<span data-ttu-id="18223-297">Indica que la tarea inició la lectura de datos WMI.</span><span class="sxs-lookup"><span data-stu-id="18223-297">Indicates that the task began to read WMI data.</span></span>|  
|`WMIDataReaderOperation`|<span data-ttu-id="18223-298">Informa de la consulta WQL que ejecutó la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-298">Reports the WQL query that the task ran.</span></span>|  
  
###  <a name="wmi-event-watcher-task"></a><a name="WMIEventWatcher"></a> <span data-ttu-id="18223-299">Tarea Monitor de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="18223-299">WMI Event Watcher Task</span></span>  
 <span data-ttu-id="18223-300">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Monitor de eventos WMI.</span><span class="sxs-lookup"><span data-stu-id="18223-300">The following table lists the custom log entries for the WMI Event Watcher task.</span></span>  
  
|<span data-ttu-id="18223-301">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-301">Log entry</span></span>|<span data-ttu-id="18223-302">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-302">Description</span></span>|  
|---------------|-----------------|  
|`WMIEventWatcherEventOccurred`|<span data-ttu-id="18223-303">Indica que ocurrió el evento que supervisaba la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-303">Denotes that the event occurred that the task was monitoring.</span></span>|  
|`WMIEventWatcherTimedout`|<span data-ttu-id="18223-304">Indica que se superó el tiempo de espera de la tarea.</span><span class="sxs-lookup"><span data-stu-id="18223-304">Indicates that the task timed out.</span></span>|  
|`WMIEventWatcherWatchingForWMIEvents`|<span data-ttu-id="18223-305">Indica que la tarea inició la ejecución de la consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="18223-305">Indicates that the task began to execute the WQL query.</span></span> <span data-ttu-id="18223-306">La entrada incluye la consulta.</span><span class="sxs-lookup"><span data-stu-id="18223-306">The entry includes the query.</span></span>|  
  
###  <a name="xml-task"></a><a name="XML"></a> <span data-ttu-id="18223-307">Tarea XML</span><span class="sxs-lookup"><span data-stu-id="18223-307">XML Task</span></span>  
 <span data-ttu-id="18223-308">La siguiente tabla contiene las entradas del registro personalizadas para la tarea XML.</span><span class="sxs-lookup"><span data-stu-id="18223-308">The following table describes the custom log entry for the XML task.</span></span>  
  
|<span data-ttu-id="18223-309">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="18223-309">Log entry</span></span>|<span data-ttu-id="18223-310">Descripción</span><span class="sxs-lookup"><span data-stu-id="18223-310">Description</span></span>|  
|---------------|-----------------|  
|`XMLOperation`|<span data-ttu-id="18223-311">Proporciona información sobre la operación que la tarea realiza.</span><span class="sxs-lookup"><span data-stu-id="18223-311">Provides information about the operation that the task performs</span></span>|   
  
## <a name="see-also"></a><span data-ttu-id="18223-312">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18223-312">See Also</span></span>  
 [<span data-ttu-id="18223-313">Registro de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="18223-313">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
