---
title: Tarea Lector de datos WMI | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.f1
helpviewer_keywords:
- WQL [Integration Services]
- WMI Data Reader task [Integration Services]
ms.assetid: dae57067-0275-4ac3-8f34-1b9d169f1112
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1d2f16a28e8b6c94c7275468dedb6d2dfec76d8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669790"
---
# <a name="wmi-data-reader-task"></a><span data-ttu-id="965b1-102">Tarea Lector de datos WMI</span><span class="sxs-lookup"><span data-stu-id="965b1-102">WMI Data Reader Task</span></span>
  <span data-ttu-id="965b1-103">La tarea Lector de datos WMI ejecuta consultas mediante el Lenguaje de consulta del Instrumental de administración de Windows (WMI), que devuelve información de WMI sobre un sistema informático.</span><span class="sxs-lookup"><span data-stu-id="965b1-103">The WMI Data Reader task runs queries using the Windows Management Instrumentation (WMI) Query Language that returns information from WMI about a computer system.</span></span> <span data-ttu-id="965b1-104">Puede usar la tarea Lector de datos WMI para los siguientes fines:</span><span class="sxs-lookup"><span data-stu-id="965b1-104">You can use the WMI Data Reader task for the following purposes:</span></span>  
  
-   <span data-ttu-id="965b1-105">Realizar consultas de los registros de eventos de Windows en un equipo local o remoto y escribir la información en un archivo o variable.</span><span class="sxs-lookup"><span data-stu-id="965b1-105">Query the Windows event logs on a local or remote computer and write the information to a file or variable.</span></span>  
  
-   <span data-ttu-id="965b1-106">Obtener información sobre la presencia, estado o propiedades de componentes del hardware y usar posteriormente esta información para determinar si se deben ejecutar otras tareas en el flujo de control.</span><span class="sxs-lookup"><span data-stu-id="965b1-106">Obtain information about the presence, state, or properties of hardware components, and then use this information to determine whether other tasks in the control flow should run.</span></span>  
  
-   <span data-ttu-id="965b1-107">Obtener una lista de las aplicaciones y determinar qué versión de cada aplicación está instalada.</span><span class="sxs-lookup"><span data-stu-id="965b1-107">Get a list of applications and determine what version of each application is installed.</span></span>  
  
 <span data-ttu-id="965b1-108">Puede configurar la tarea Lector de datos WMI de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="965b1-108">You can configure the WMI Data Reader task in the following ways:</span></span>  
  
-   <span data-ttu-id="965b1-109">Especificar el administrador de conexiones WMI que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="965b1-109">Specify the WMI connection manager to use.</span></span>  
  
-   <span data-ttu-id="965b1-110">Especificar el origen de la consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="965b1-110">Specify the source of the WQL query.</span></span> <span data-ttu-id="965b1-111">La consulta se puede almacenar en una propiedad de tarea, o bien fuera de la tarea, en una variable o archivo.</span><span class="sxs-lookup"><span data-stu-id="965b1-111">The query can be stored in a task property, or the query can be stored outside the task, in a variable or a file.</span></span>  
  
-   <span data-ttu-id="965b1-112">Definir el formato de los resultados de la consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="965b1-112">Define the format of the WQL query results.</span></span> <span data-ttu-id="965b1-113">La tarea admite una tabla, par de nombre/valor de la propiedad o formato de valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="965b1-113">The task supports a table, property name/value pair, or property value format.</span></span>  
  
-   <span data-ttu-id="965b1-114">Especificar el destino de la consulta.</span><span class="sxs-lookup"><span data-stu-id="965b1-114">Specify the destination of the query.</span></span> <span data-ttu-id="965b1-115">El destino puede ser una variable o un archivo.</span><span class="sxs-lookup"><span data-stu-id="965b1-115">The destination can be a variable or a file.</span></span>  
  
-   <span data-ttu-id="965b1-116">Indicar si el destino de la consulta se sobrescribe, se conserva o anexa.</span><span class="sxs-lookup"><span data-stu-id="965b1-116">Indicate whether the query destination is overwritten, kept, or appended.</span></span>  
  
 <span data-ttu-id="965b1-117">Si el origen o destino es un archivo, la tarea Lector de datos WMI usa un administrador de conexiones de archivo para conectarse al archivo.</span><span class="sxs-lookup"><span data-stu-id="965b1-117">If the source or destination is a file, the WMI Data Reader task uses a File connection manager to connect to the file.</span></span> <span data-ttu-id="965b1-118">Para más información, consulte [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="965b1-118">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="965b1-119">La tarea Lector de datos WMI usa un administrador de conexiones WMI para conectarse al servidor desde el cual lee la información de WMI.</span><span class="sxs-lookup"><span data-stu-id="965b1-119">The WMI Data Reader task uses a WMI connection manager to connect to the server from which it reads WMI information.</span></span> <span data-ttu-id="965b1-120">Para más información, consulte [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="965b1-120">For more information, see [WMI Connection Manager](../connection-manager/wmi-connection-manager.md).</span></span>  
  
## <a name="wql-query"></a><span data-ttu-id="965b1-121">WQL Query</span><span class="sxs-lookup"><span data-stu-id="965b1-121">WQL Query</span></span>  
 <span data-ttu-id="965b1-122">WQL es un dialecto de SQL con extensiones para admitir la notificación de eventos de WMI y otras características específicas de WMI.</span><span class="sxs-lookup"><span data-stu-id="965b1-122">WQL is a dialect of SQL with extensions to support WMI event notification and other WMI-specific features.</span></span> <span data-ttu-id="965b1-123">Para obtener más información sobre WQL, vea la documentación sobre Instrumental de administración de Windows en [MSDN Library](https://go.microsoft.com/fwlink/?linkid=7022).</span><span class="sxs-lookup"><span data-stu-id="965b1-123">For more information about WQL, see the Windows Management Instrumentation documentation in the [MSDN Library](https://go.microsoft.com/fwlink/?linkid=7022).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="965b1-124">Las clases de WMI varían en las diferentes versiones de Windows.</span><span class="sxs-lookup"><span data-stu-id="965b1-124">WMI classes vary between versions of Windows.</span></span>  
  
 <span data-ttu-id="965b1-125">La siguiente consulta WQL devuelve entradas en el evento de registro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="965b1-125">The following WQL query returns entries in the Application log event.</span></span>  
  
```  
SELECT * FROM Win32_NTLogEvent WHERE LogFile = 'Application' AND (SourceName='SQLISService' OR SourceName='SQLISPackage') AND TimeGenerated > '20050117'  
```  
  
 <span data-ttu-id="965b1-126">La siguiente consulta WQL devuelve información de disco lógica.</span><span class="sxs-lookup"><span data-stu-id="965b1-126">The following WQL query returns logical disk information.</span></span>  
  
```  
SELECT FreeSpace, DeviceId, Size, SystemName, Description FROM Win32_LlogicalDisk  
```  
  
 <span data-ttu-id="965b1-127">La siguiente consulta WQL devuelve una lista de las actualizaciones de Ingeniería de corrección rápida (QFE) al sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="965b1-127">The following WQL query returns a list of the quick fix engineering (QFE) updates to the operating system.</span></span>  
  
```  
Select * FROM Win32_QuickFixEngineering  
```  
  
## <a name="custom-logging-messages-available-on-the-wmi-data-reader-task"></a><span data-ttu-id="965b1-128">Mensajes de registro personalizados disponibles en la tarea Lector de datos WMI</span><span class="sxs-lookup"><span data-stu-id="965b1-128">Custom Logging Messages Available on the WMI Data Reader Task</span></span>  
 <span data-ttu-id="965b1-129">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Lector de datos WMI.</span><span class="sxs-lookup"><span data-stu-id="965b1-129">The following table lists the custom log entries for the WMI Data Reader task.</span></span> <span data-ttu-id="965b1-130">Para obtener más información, vea [Registro de Integration Services &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) y [Mensajes personalizados para registro](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="965b1-130">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="965b1-131">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="965b1-131">Log entry</span></span>|<span data-ttu-id="965b1-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="965b1-132">Description</span></span>|  
|---------------|-----------------|  
|`WMIDataReaderGettingWMIData`|<span data-ttu-id="965b1-133">Indica que la tarea inició la lectura de datos WMI.</span><span class="sxs-lookup"><span data-stu-id="965b1-133">Indicates that the task began to read WMI data.</span></span>|  
|`WMIDataReaderOperation`|<span data-ttu-id="965b1-134">Informa de la consulta WQL que ejecutó la tarea.</span><span class="sxs-lookup"><span data-stu-id="965b1-134">Reports the WQL query that the task ran.</span></span>|  
  
## <a name="configuration-of-the-wmi-data-reader-task"></a><span data-ttu-id="965b1-135">Configuración de la tarea Lector de datos WMI</span><span class="sxs-lookup"><span data-stu-id="965b1-135">Configuration of the WMI Data Reader Task</span></span>  
 <span data-ttu-id="965b1-136">Puede establecer propiedades mediante programación o a través del Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="965b1-136">You can set properties programmatically or through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="965b1-137">Para obtener información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="965b1-137">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="965b1-138">Editor de la tarea Lector de datos WMI &#40;página Opciones WMI&#41;</span><span class="sxs-lookup"><span data-stu-id="965b1-138">WMI Data Reader Task Editor &#40;WMI Options Page&#41;</span></span>](../wmi-data-reader-task-editor-wmi-options-page.md)  
  
-   [<span data-ttu-id="965b1-139">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="965b1-139">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="965b1-140">Para obtener información sobre cómo establecer estas propiedades mediante programación, haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="965b1-140">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.WmiDataReaderTask.WmiDataReaderTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="965b1-141">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="965b1-141">Related Tasks</span></span>  
 <span data-ttu-id="965b1-142">Para obtener más información sobre cómo establecer estas propiedades en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en el siguiente tema:</span><span class="sxs-lookup"><span data-stu-id="965b1-142">For more information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="965b1-143">Establecer las propiedades de tareas o contenedores</span><span class="sxs-lookup"><span data-stu-id="965b1-143">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="965b1-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="965b1-144">See Also</span></span>  
 <span data-ttu-id="965b1-145">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="965b1-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="965b1-146">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="965b1-146">Control Flow</span></span>](control-flow.md)  
  
  
