---
title: Tarea Monitor de eventos WMI | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatchertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Event Watcher task [Integration Services]
ms.assetid: b5bb52e9-a77e-41e1-93f9-d4c3bc6b2c9a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: be20624e5ccdf665e6274f647c342498e9c0f0a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750053"
---
# <a name="wmi-event-watcher-task"></a><span data-ttu-id="cf1fb-102">Tarea Monitor de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="cf1fb-102">WMI Event Watcher Task</span></span>
  <span data-ttu-id="cf1fb-103">La tarea Monitor de eventos WMI supervisa un evento de Instrumental de administración de Windows (WMI) mediante una consulta de evento de Lenguaje de consulta de Instrumental de administración (WQL) para especificar los eventos de interés.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-103">The WMI Event Watcher task watches for a Windows Management Instrumentation (WMI) event using a Management Instrumentation Query Language (WQL) event query to specify events of interest.</span></span> <span data-ttu-id="cf1fb-104">Puede usar la tarea Monitor de eventos WMI para los siguientes fines:</span><span class="sxs-lookup"><span data-stu-id="cf1fb-104">You can use the WMI Event Watcher task for the following purposes:</span></span>  
  
-   <span data-ttu-id="cf1fb-105">Esperar la notificación de que se han agregado archivos a una carpeta y luego iniciar el procesamiento del archivo.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-105">Wait for notification that files have been added to a folder and then initiate the processing of the file.</span></span>  
  
-   <span data-ttu-id="cf1fb-106">Ejecutar un paquete que elimine archivos cuando la memoria disponible en un servidor alcance un porcentaje inferior al especificado.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-106">Run a package that deletes files when the available memory on a server drops lower than a specified percentage.</span></span>  
  
-   <span data-ttu-id="cf1fb-107">Controlar la instalación de una aplicación y luego ejecutar un paquete que usa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-107">Watch for installation of an application, and then run a package that uses the application.</span></span>  
  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="cf1fb-108">incluye una tarea que lee información de WMI.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-108">includes a task that reads WMI information.</span></span>  
  
 <span data-ttu-id="cf1fb-109">Para obtener más información sobre esta tarea, haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf1fb-109">For more information about this task, click the following topic:</span></span>  
  
-   [<span data-ttu-id="cf1fb-110">Tarea Lector de datos WMI</span><span class="sxs-lookup"><span data-stu-id="cf1fb-110">WMI Data Reader Task</span></span>](wmi-data-reader-task.md)  
  
## <a name="wql-queries"></a><span data-ttu-id="cf1fb-111">Consultas WQL</span><span class="sxs-lookup"><span data-stu-id="cf1fb-111">WQL Queries</span></span>  
 <span data-ttu-id="cf1fb-112">WQL es un dialecto de SQL con extensiones para admitir la notificación de eventos de WMI y otras características específicas de WMI.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-112">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="cf1fb-113">Para obtener más información sobre WQL, vea la documentación sobre Instrumental de administración de Windows en [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span><span class="sxs-lookup"><span data-stu-id="cf1fb-113">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=62553).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cf1fb-114">Las clases de WMI varían en las diferentes versiones de Windows.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-114">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="cf1fb-115">La siguiente consulta supervisa la notificación de que el uso de la CPU supera el 40 por ciento.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-115">The following query watches for notification that the CPU use is more than 40 percent.</span></span>  
  
```  
SELECT * from __InstanceModificationEvent WITHIN 2 WHERE TargetInstance ISA 'Win32_Processor' and TargetInstance.LoadPercentage > 40  
```  
  
 <span data-ttu-id="cf1fb-116">La siguiente consulta detecta la notificación de que se ha agregado un archivo a una carpeta.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-116">The following query watches for notification that a file has been added to a folder.</span></span>  
  
```  
SELECT * FROM __InstanceCreationEvent WITHIN 10 WHERE TargetInstance ISA "CIM_DirectoryContainsFile" and TargetInstance.GroupComponent= "Win32_Directory.Name=\"c:\\\\WMIFileWatcher\""   
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-event-watcher-task"></a><span data-ttu-id="cf1fb-117">Mensajes de registro personalizados disponibles en la tarea Monitor de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="cf1fb-117">Custom Logging Messages Available on the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="cf1fb-118">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Monitor de eventos WMI.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-118">The following table lists the custom log entries for the WMI Event Watcher task.</span></span> <span data-ttu-id="cf1fb-119">Para obtener más información, vea [Registro de Integration Services &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) y [Mensajes personalizados para registro](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="cf1fb-119">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="cf1fb-120">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="cf1fb-120">Log entry</span></span>|<span data-ttu-id="cf1fb-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf1fb-121">Description</span></span>|  
|---------------|-----------------|  
|`WMIEventWatcherEventOccurred`|<span data-ttu-id="cf1fb-122">Indica que ocurrió un evento que supervisaba la tarea.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-122">Indicates that an event occurred that the task was monitoring.</span></span>|  
|`WMIEventWatcherTimedout`|<span data-ttu-id="cf1fb-123">Indica que se superó el tiempo de espera de la tarea.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-123">Indicates that the task timed out.</span></span>|  
|`WMIEventWatcherWatchingForWMIEvents`|<span data-ttu-id="cf1fb-124">Indica que la tarea inició la ejecución de la consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-124">Indicates that the task began to execute the WQL query.</span></span> <span data-ttu-id="cf1fb-125">La entrada incluye la consulta.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-125">The entry includes the query.</span></span>|  
  
## <a name="configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="cf1fb-126">Configuración de la tarea Monitor de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="cf1fb-126">Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="cf1fb-127">Puede configurar la tarea Lector de datos WMI de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf1fb-127">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="cf1fb-128">Especificar el administrador de conexiones WMI que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-128">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="cf1fb-129">Especificar el origen de la consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-129">Specify the source of the WQL query.</span></span> <span data-ttu-id="cf1fb-130">El origen puede ser externo con respecto a la tarea, una variable o un archivo, o la consulta se puede almacenar en una propiedad de tarea.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-130">The source can be external to the task, a variable or a file, or the query can be stored in a task property.</span></span>  
  
-   <span data-ttu-id="cf1fb-131">Especificar la acción realizada por la tarea cuando se produce el evento WMI.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-131">Specify the action that the task takes when the WMI event occurs.</span></span> <span data-ttu-id="cf1fb-132">Puede registrar la notificación de eventos y el estado después del evento, o activar eventos personalizados de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que proporcionen información asociada con el evento WMI, la notificación y el estado después del evento.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-132">You can log the event notification and the status after the event, or raise custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] events that provide information associated with the WMI event, the notification, and the status after the event.</span></span>  
  
-   <span data-ttu-id="cf1fb-133">Definir de qué manera la tarea responde ante el evento.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-133">Define how the task responds to the event.</span></span> <span data-ttu-id="cf1fb-134">La tarea se puede configurar para realizarse correctamente o generar un error, según el evento, o la tarea puede supervisar el evento nuevamente.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-134">The task can be configured to succeed or fail, depending on the event, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="cf1fb-135">Especificar la acción realizada por la tarea cuando se agota el tiempo de espera de la consulta WMI. Puede registrar el tiempo de espera y el estado después del tiempo de espera, o activar un evento personalizado de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , que indique que se agotó el tiempo de espera del evento WMI y que registre el tiempo de espera y el estado del tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-135">Specify the action the task takes when the WMI query times out. You can log the time-out and the status after time-out, or raise a custom [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] event, indicating that the WMI event timed out and logging the time-out and time-out status.</span></span>  
  
-   <span data-ttu-id="cf1fb-136">Definir de qué manera la tarea responde ante el tiempo de espera. La tarea se puede configurar para realizarse correctamente o presentar un error, o la tarea puede detectar el evento nuevamente.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-136">Define how the task responds to the time-out. The task can be configured to succeed or fail, or the task can just watch for the event again.</span></span>  
  
-   <span data-ttu-id="cf1fb-137">Especificar la cantidad de veces que la tarea supervisa el evento.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-137">Specify the number of times the task watches for the event.</span></span>  
  
-   <span data-ttu-id="cf1fb-138">Especificar el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-138">Specify the time-out.</span></span>  
  
 <span data-ttu-id="cf1fb-139">Si el origen es un archivo, la tarea Monitor de eventos WMI usa un administrador de conexiones de archivos para conectarse al archivo.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-139">If the source is a file, the WMI Event Watcher task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="cf1fb-140">Para más información, consulte [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cf1fb-140">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="cf1fb-141">La tarea Monitor de eventos WMI usa un administrador de conexiones WMI para conectarse al servidor desde el cual lee la información de WMI.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-141">The WMI Event Watcher task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="cf1fb-142">Para más información, consulte [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cf1fb-142">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
 <span data-ttu-id="cf1fb-143">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="cf1fb-143">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="cf1fb-144">Para obtener más información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cf1fb-144">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="cf1fb-145">Editor de la tarea Monitor de eventos WMI &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="cf1fb-145">WMI Event Watcher Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="cf1fb-146">Editor de la tarea Monitor de eventos WMI &#40;página Opciones WMI&#41;</span><span class="sxs-lookup"><span data-stu-id="cf1fb-146">WMI Event Watcher Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-event-watcher-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="cf1fb-147">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="cf1fb-147">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="cf1fb-148">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="cf1fb-148">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="cf1fb-149">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="cf1fb-149">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="programmatic-configuration-of-the-wmi-event-watcher-task"></a><span data-ttu-id="cf1fb-150">Configuración mediante programación de la tarea Monitor de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="cf1fb-150">Programmatic Configuration of the WMI Event Watcher Task</span></span>  
 <span data-ttu-id="cf1fb-151">Para obtener más información sobre cómo establecer estas propiedades mediante programación, haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf1fb-151">For more information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiEventWatcherTask.WmiEventWatcherTask>  
  
  
