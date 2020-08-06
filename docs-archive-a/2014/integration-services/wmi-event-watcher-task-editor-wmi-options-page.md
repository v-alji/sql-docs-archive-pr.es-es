---
title: Editor de la tarea monitor de eventos WMI (Página opciones WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmieventwatcher.wmiquery.f1
helpviewer_keywords:
- WMI Event Watcher Task Editor
ms.assetid: 525f3de7-a021-4e52-9939-3a83c88f131a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d7d95501f6442df3723261c970c7a90f48cbdc87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747082"
---
# <a name="wmi-event-watcher-task-editor-wmi-options-page"></a><span data-ttu-id="2afea-102">Editor de la tarea Monitor de eventos WMI (página Opciones WMI)</span><span class="sxs-lookup"><span data-stu-id="2afea-102">WMI Event Watcher Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="2afea-103">Use la página **Opciones WMI** del cuadro de diálogo **Editor de la tarea Monitor de eventos WMI** para especificar el origen de la consulta WQL (Lenguaje de consulta de Instrumental de administración de Windows) y la manera en que la tarea Monitor de eventos WMI responde a los eventos WMI (Instrumentación de Microsoft Windows).</span><span class="sxs-lookup"><span data-stu-id="2afea-103">Use the **WMI Options** page of the **WMI Event Watcher Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and how the WMI Event Watcher task responds to Microsoft Windows Instrumentation (WMI) events.</span></span>  
  
 <span data-ttu-id="2afea-104">Para obtener información acerca de esta tarea, vea [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span><span class="sxs-lookup"><span data-stu-id="2afea-104">To learn about this task, see [WMI Event Watcher Task](control-flow/wmi-event-watcher-task.md).</span></span> <span data-ttu-id="2afea-105">Para más información sobre el lenguaje de consulta de WMI (WQL), vea el tema sobre Instrumental de administración de Windows, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045)(Realizar consultas con WQL), en MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="2afea-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="2afea-106">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="2afea-106">Static Options</span></span>  
 <span data-ttu-id="2afea-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="2afea-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="2afea-108">Seleccione un administrador de conexiones de WMI de la lista o haga clic en \<**New WMI Connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="2afea-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="2afea-109">**Temas relacionados:** [Administrador de conexiones WMI](connection-manager/wmi-connection-manager.md), [Editor del administrador de conexiones WMI](../../2014/integration-services/wmi-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="2afea-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="2afea-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="2afea-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="2afea-111">Seleccione el tipo de origen de la consulta WQL que ejecuta la tarea.</span><span class="sxs-lookup"><span data-stu-id="2afea-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="2afea-112">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="2afea-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="2afea-113">Value</span><span class="sxs-lookup"><span data-stu-id="2afea-113">Value</span></span>|<span data-ttu-id="2afea-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2afea-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2afea-115">**Entrada directa**</span><span class="sxs-lookup"><span data-stu-id="2afea-115">**Direct input**</span></span>|<span data-ttu-id="2afea-116">Establezca el origen en una consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="2afea-116">Set the source to a WQL query.</span></span> <span data-ttu-id="2afea-117">Al seleccionar este valor se muestra la opción dinámica **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="2afea-117">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="2afea-118">**Conexión de archivos**</span><span class="sxs-lookup"><span data-stu-id="2afea-118">**File connection**</span></span>|<span data-ttu-id="2afea-119">Seleccione el archivo que contiene la consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="2afea-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="2afea-120">Al seleccionar este valor se muestra la opción dinámica **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="2afea-120">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
|<span data-ttu-id="2afea-121">**Variable**</span><span class="sxs-lookup"><span data-stu-id="2afea-121">**Variable**</span></span>|<span data-ttu-id="2afea-122">Establezca el origen en una variable que defina la consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="2afea-122">Set the source to a variable that defines WQL query.</span></span> <span data-ttu-id="2afea-123">Al seleccionar este valor se muestra la opción dinámica **WQLQuerySource**.</span><span class="sxs-lookup"><span data-stu-id="2afea-123">Selecting this value displays the dynamic option, **WQLQuerySource**.</span></span>|  
  
 <span data-ttu-id="2afea-124">**ActionAtEvent**</span><span class="sxs-lookup"><span data-stu-id="2afea-124">**ActionAtEvent**</span></span>  
 <span data-ttu-id="2afea-125">Especifique si el evento WMI registra el evento e inicia una acción de [!INCLUDE[ssIS](../includes/ssis-md.md)] o si solamente registra el evento.</span><span class="sxs-lookup"><span data-stu-id="2afea-125">Specify whether the WMI event logs the event and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] action, or only logs the event.</span></span>  
  
 <span data-ttu-id="2afea-126">**AfterEvent**</span><span class="sxs-lookup"><span data-stu-id="2afea-126">**AfterEvent**</span></span>  
 <span data-ttu-id="2afea-127">Especifique si la tarea se realiza correctamente o se produce un error después de recibir el evento WMI, o si la tarea continúa inspeccionando si el evento se vuelve a producir.</span><span class="sxs-lookup"><span data-stu-id="2afea-127">Specify whether the task succeeds or fails after it receives the WMI event, or if the task continues watching for the event to occur again.</span></span>  
  
 <span data-ttu-id="2afea-128">**ActionAtTimeout**</span><span class="sxs-lookup"><span data-stu-id="2afea-128">**ActionAtTimeout**</span></span>  
 <span data-ttu-id="2afea-129">Especifique si la tarea registra un tiempo de espera de consulta WMI e inicia un evento de [!INCLUDE[ssIS](../includes/ssis-md.md)] como respuesta o si solamente registra el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2afea-129">Specify whether the task logs a WMI query time-out and initiates an [!INCLUDE[ssIS](../includes/ssis-md.md)] event in response, or only logs the time-out.</span></span>  
  
 <span data-ttu-id="2afea-130">**AfterTimeout**</span><span class="sxs-lookup"><span data-stu-id="2afea-130">**AfterTimeout**</span></span>  
 <span data-ttu-id="2afea-131">Especifique si la tarea se realiza correctamente o se produce un error en respuesta a un tiempo de espera, o si la tarea continúa inspeccionando si se vuelve a producir otro tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2afea-131">Specify whether the task succeeds or fails in response to a time-out, or if the task continues watching for another time-out to recur.</span></span>  
  
 <span data-ttu-id="2afea-132">**NumberOfEvents**</span><span class="sxs-lookup"><span data-stu-id="2afea-132">**NumberOfEvents**</span></span>  
 <span data-ttu-id="2afea-133">Especifique el número de eventos a inspeccionar.</span><span class="sxs-lookup"><span data-stu-id="2afea-133">Specify the number of events to watch for.</span></span>  
  
 <span data-ttu-id="2afea-134">**Tiempo de espera**</span><span class="sxs-lookup"><span data-stu-id="2afea-134">**Timeout**</span></span>  
 <span data-ttu-id="2afea-135">Especifique el número de segundos que se debe esperar a que el evento ocurra.</span><span class="sxs-lookup"><span data-stu-id="2afea-135">Specify the number of seconds to wait for the event to occur.</span></span> <span data-ttu-id="2afea-136">Un valor de 0 significa que no rige ningún tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2afea-136">A value of 0 means that no time-out is in effect.</span></span>  
  
## <a name="wqlquerysource-dynamic-options"></a><span data-ttu-id="2afea-137">Opciones dinámicas de WQLQuerySource</span><span class="sxs-lookup"><span data-stu-id="2afea-137">WQLQuerySource Dynamic Options</span></span>  
  
### <a name="wqlquerysource--direct-input"></a><span data-ttu-id="2afea-138">WQLQuerySource = Entrada directa</span><span class="sxs-lookup"><span data-stu-id="2afea-138">WQLQuerySource = Direct input</span></span>  
 <span data-ttu-id="2afea-139">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="2afea-139">**WQLQuerySource**</span></span>  
 <span data-ttu-id="2afea-140">Proporcione una consulta, o bien haga clic en el botón de puntos suspensivos (…) y escriba una consulta con el cuadro de diálogo **Consulta WQL**.</span><span class="sxs-lookup"><span data-stu-id="2afea-140">Provide a query, or click the ellipsis button (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysource--file-connection"></a><span data-ttu-id="2afea-141">WQLQuerySource = Conexión de archivos</span><span class="sxs-lookup"><span data-stu-id="2afea-141">WQLQuerySource = File connection</span></span>  
 <span data-ttu-id="2afea-142">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="2afea-142">**WQLQuerySource**</span></span>  
 <span data-ttu-id="2afea-143">Seleccione un administrador de conexiones de archivos de la lista o haga clic en \<**New connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="2afea-143">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="2afea-144">**Temas relacionados:** [Administrador de conexiones de archivos](connection-manager/file-connection-manager.md), [Editor de administrador de conexiones de archivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="2afea-144">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysource--variable"></a><span data-ttu-id="2afea-145">WQLQuerySource = Variable</span><span class="sxs-lookup"><span data-stu-id="2afea-145">WQLQuerySource = Variable</span></span>  
 <span data-ttu-id="2afea-146">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="2afea-146">**WQLQuerySource**</span></span>  
 <span data-ttu-id="2afea-147">Seleccione una variable de la lista o haga clic en \<**New variable...**> para crear una.</span><span class="sxs-lookup"><span data-stu-id="2afea-147">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="2afea-148">**Temas relacionados:** [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="2afea-148">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2afea-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2afea-149">See Also</span></span>  
 <span data-ttu-id="2afea-150">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2afea-150">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2afea-151">[Editor de la tarea monitor de eventos WMI &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="2afea-151">[WMI Event Watcher Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="2afea-152">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="2afea-152">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="2afea-153">Tarea Lector de datos WMI</span><span class="sxs-lookup"><span data-stu-id="2afea-153">WMI Data Reader Task</span></span>](control-flow/wmi-data-reader-task.md)  
  
  
