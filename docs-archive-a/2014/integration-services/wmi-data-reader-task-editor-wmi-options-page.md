---
title: Editor de la tarea lector de datos WMI (Página opciones WMI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.wmidatareadertask.wmiquery.f1
helpviewer_keywords:
- WMI Data Reader Task Editor
ms.assetid: 4b8d4716-882d-41b0-b77e-e0e2741a2cd5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfb28e7f8f352f708085bf664757391a05869752
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676546"
---
# <a name="wmi-data-reader-task-editor-wmi-options-page"></a><span data-ttu-id="bb575-102">Editor de la tarea Lector de datos WMI (página Opciones WMI)</span><span class="sxs-lookup"><span data-stu-id="bb575-102">WMI Data Reader Task Editor (WMI Options Page)</span></span>
  <span data-ttu-id="bb575-103">Use la página **Opciones WMI** del cuadro de diálogo **Editor de la tarea Lector de datos WMI** para especificar el origen de la consulta WQL (Lenguaje de consulta de Instrumental de administración de Windows) y el destino del resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="bb575-103">Use the **WMI Options** page of the **WMI Data Reader Task Editor** dialog box to specify the source of the Windows Management Instrumentation Query Language (WQL) query and the destination of the query result.</span></span>  
  
 <span data-ttu-id="bb575-104">Para obtener información acerca de esta tarea, vea [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span><span class="sxs-lookup"><span data-stu-id="bb575-104">To learn about this task, see [WMI Data Reader Task](control-flow/wmi-data-reader-task.md).</span></span> <span data-ttu-id="bb575-105">Para más información sobre el lenguaje de consulta de WMI (WQL), vea el tema sobre Instrumental de administración de Windows, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045)(Realizar consultas con WQL), en MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="bb575-105">For more information about WMI Query Language (WQL), see the Windows Management Instrumentation topic, [Querying with WQL](https://go.microsoft.com/fwlink/?LinkId=79045), in the MSDN Library.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="bb575-106">Opciones estáticas</span><span class="sxs-lookup"><span data-stu-id="bb575-106">Static Options</span></span>  
 <span data-ttu-id="bb575-107">**WMIConnectionName**</span><span class="sxs-lookup"><span data-stu-id="bb575-107">**WMIConnectionName**</span></span>  
 <span data-ttu-id="bb575-108">Seleccione un administrador de conexiones de WMI de la lista o haga clic en \<**New WMI Connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="bb575-108">Select a WMI connection manager in the list, or click \<**New WMI Connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="bb575-109">**Temas relacionados:** [Administrador de conexiones WMI](connection-manager/wmi-connection-manager.md), [Editor del administrador de conexiones WMI](../../2014/integration-services/wmi-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="bb575-109">**Related Topics:** [WMI Connection Manager](connection-manager/wmi-connection-manager.md), [WMI Connection Manager Editor](../../2014/integration-services/wmi-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="bb575-110">**WQLQuerySourceType**</span><span class="sxs-lookup"><span data-stu-id="bb575-110">**WQLQuerySourceType**</span></span>  
 <span data-ttu-id="bb575-111">Seleccione el tipo de origen de la consulta WQL que ejecuta la tarea.</span><span class="sxs-lookup"><span data-stu-id="bb575-111">Select the source type of the WQL query that the task runs.</span></span> <span data-ttu-id="bb575-112">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="bb575-112">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="bb575-113">Value</span><span class="sxs-lookup"><span data-stu-id="bb575-113">Value</span></span>|<span data-ttu-id="bb575-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb575-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bb575-115">**Entrada directa**</span><span class="sxs-lookup"><span data-stu-id="bb575-115">**Direct input**</span></span>|<span data-ttu-id="bb575-116">Establezca el origen en una consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="bb575-116">Set the source to a WQL query.</span></span> <span data-ttu-id="bb575-117">Al seleccionar este valor se muestra la opción dinámica **WQLQuerySourceType**.</span><span class="sxs-lookup"><span data-stu-id="bb575-117">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="bb575-118">**Conexión de archivos**</span><span class="sxs-lookup"><span data-stu-id="bb575-118">**File connection**</span></span>|<span data-ttu-id="bb575-119">Seleccione el archivo que contiene la consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="bb575-119">Select a file that contains the WQL query.</span></span> <span data-ttu-id="bb575-120">Al seleccionar este valor se muestra la opción dinámica **WQLQuerySourceType**.</span><span class="sxs-lookup"><span data-stu-id="bb575-120">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
|<span data-ttu-id="bb575-121">**Variable**</span><span class="sxs-lookup"><span data-stu-id="bb575-121">**Variable**</span></span>|<span data-ttu-id="bb575-122">Establezca el origen en una variable que defina la consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="bb575-122">Set the source to a variable that defines the WQL query.</span></span> <span data-ttu-id="bb575-123">Al seleccionar este valor se muestra la opción dinámica **WQLQuerySourceType**.</span><span class="sxs-lookup"><span data-stu-id="bb575-123">Selecting this value displays the dynamic option **WQLQuerySourceType**.</span></span>|  
  
 <span data-ttu-id="bb575-124">**OutputType**</span><span class="sxs-lookup"><span data-stu-id="bb575-124">**OutputType**</span></span>  
 <span data-ttu-id="bb575-125">Especifique si la salida debe ser una tabla de datos, un valor de propiedad o un valor y nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="bb575-125">Specify whether the output should be a data table, property value, or property name and value.</span></span>  
  
 <span data-ttu-id="bb575-126">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="bb575-126">**OverwriteDestination**</span></span>  
 <span data-ttu-id="bb575-127">Especifica si mantener, sobrescribir o anexar a los datos originales en el archivo de destino o variable.</span><span class="sxs-lookup"><span data-stu-id="bb575-127">Specifies whether to keep, overwrite, or append to the original data in the destination file or variable.</span></span>  
  
 <span data-ttu-id="bb575-128">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="bb575-128">**DestinationType**</span></span>  
 <span data-ttu-id="bb575-129">Seleccione el tipo de destino de la consulta WQL que ejecuta la tarea.</span><span class="sxs-lookup"><span data-stu-id="bb575-129">Select the destination type of the WQL query that the task runs.</span></span> <span data-ttu-id="bb575-130">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="bb575-130">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="bb575-131">Value</span><span class="sxs-lookup"><span data-stu-id="bb575-131">Value</span></span>|<span data-ttu-id="bb575-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="bb575-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bb575-133">**Conexión de archivos**</span><span class="sxs-lookup"><span data-stu-id="bb575-133">**File connection**</span></span>|<span data-ttu-id="bb575-134">Seleccione un archivo donde guardar los resultados de la consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="bb575-134">Select a file to save the results of the WQL query in.</span></span> <span data-ttu-id="bb575-135">Al seleccionar este valor se muestra la opción dinámica **DestinationType**.</span><span class="sxs-lookup"><span data-stu-id="bb575-135">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
|<span data-ttu-id="bb575-136">**Variable**</span><span class="sxs-lookup"><span data-stu-id="bb575-136">**Variable**</span></span>|<span data-ttu-id="bb575-137">Establezca la variable donde almacenar los resultados de la consulta WQL.</span><span class="sxs-lookup"><span data-stu-id="bb575-137">Set the variable to store the results of the WQL query in.</span></span> <span data-ttu-id="bb575-138">Al seleccionar este valor se muestra la opción dinámica **DestinationType**.</span><span class="sxs-lookup"><span data-stu-id="bb575-138">Selecting this value displays the dynamic option, **DestinationType**.</span></span>|  
  
## <a name="wqlquerysourcetype-dynamic-options"></a><span data-ttu-id="bb575-139">Opciones dinámicas WQLQuerySourceType</span><span class="sxs-lookup"><span data-stu-id="bb575-139">WQLQuerySourceType Dynamic Options</span></span>  
  
### <a name="wqlquerysourcetype--direct-input"></a><span data-ttu-id="bb575-140">WQLQuerySourceType = Entrada directa</span><span class="sxs-lookup"><span data-stu-id="bb575-140">WQLQuerySourceType = Direct input</span></span>  
 <span data-ttu-id="bb575-141">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="bb575-141">**WQLQuerySource**</span></span>  
 <span data-ttu-id="bb575-142">Proporcione una consulta, o bien haga clic en los puntos suspensivos (…) y escriba una consulta con el cuadro de diálogo **Consulta WQL**.</span><span class="sxs-lookup"><span data-stu-id="bb575-142">Provide a query, or click the ellipsis (...) and enter a query using the **WQL Query** dialog box.</span></span>  
  
### <a name="wqlquerysourcetype--file-connection"></a><span data-ttu-id="bb575-143">WQLQuerySourceType = Conexión de archivos</span><span class="sxs-lookup"><span data-stu-id="bb575-143">WQLQuerySourceType = File connection</span></span>  
 <span data-ttu-id="bb575-144">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="bb575-144">**WQLQuerySource**</span></span>  
 <span data-ttu-id="bb575-145">Seleccione un administrador de conexiones de archivos de la lista o haga clic en \<**New connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="bb575-145">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="bb575-146">**Temas relacionados:** [Administrador de conexiones de archivos](connection-manager/file-connection-manager.md), [Editor de administrador de conexiones de archivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="bb575-146">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="wqlquerysourcetype--variable"></a><span data-ttu-id="bb575-147">WQLQuerySourceType = Variable</span><span class="sxs-lookup"><span data-stu-id="bb575-147">WQLQuerySourceType = Variable</span></span>  
 <span data-ttu-id="bb575-148">**WQLQuerySource**</span><span class="sxs-lookup"><span data-stu-id="bb575-148">**WQLQuerySource**</span></span>  
 <span data-ttu-id="bb575-149">Seleccione una variable de la lista o haga clic en \<**New variable...**> para crear una.</span><span class="sxs-lookup"><span data-stu-id="bb575-149">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="bb575-150">**Temas relacionados:** [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="bb575-150">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="destinationtype-dynamic-options"></a><span data-ttu-id="bb575-151">Opciones dinámicas DestinationType</span><span class="sxs-lookup"><span data-stu-id="bb575-151">DestinationType Dynamic Options</span></span>  
  
### <a name="destinationtype--file-connection"></a><span data-ttu-id="bb575-152">DestinationType = Conexión de archivos</span><span class="sxs-lookup"><span data-stu-id="bb575-152">DestinationType = File connection</span></span>  
 <span data-ttu-id="bb575-153">**Destino**</span><span class="sxs-lookup"><span data-stu-id="bb575-153">**Destination**</span></span>  
 <span data-ttu-id="bb575-154">Seleccione un administrador de conexiones de archivos de la lista o haga clic en \<**New connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="bb575-154">Select a File connection manager in the list, or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="bb575-155">**Temas relacionados:** [Administrador de conexiones de archivos](connection-manager/file-connection-manager.md), [Editor de administrador de conexiones de archivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="bb575-155">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="destinationtype--variable"></a><span data-ttu-id="bb575-156">DestinationType = Variable</span><span class="sxs-lookup"><span data-stu-id="bb575-156">DestinationType = Variable</span></span>  
 <span data-ttu-id="bb575-157">**Destino**</span><span class="sxs-lookup"><span data-stu-id="bb575-157">**Destination**</span></span>  
 <span data-ttu-id="bb575-158">Seleccione una variable de la lista o haga clic en \<**New variable...**> para crear una.</span><span class="sxs-lookup"><span data-stu-id="bb575-158">Select a variable in the list, or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="bb575-159">**Temas relacionados:** [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="bb575-159">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb575-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb575-160">See Also</span></span>  
 <span data-ttu-id="bb575-161">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bb575-161">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="bb575-162">[Editor de la tarea lector de datos WMI &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="bb575-162">[WMI Data Reader Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="bb575-163">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="bb575-163">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="bb575-164">Tarea Monitor de eventos WMI</span><span class="sxs-lookup"><span data-stu-id="bb575-164">WMI Event Watcher Task</span></span>](control-flow/wmi-event-watcher-task.md)  
  
  
