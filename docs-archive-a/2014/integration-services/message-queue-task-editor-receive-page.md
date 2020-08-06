---
title: Editor de la tarea cola de mensajes (página recibir) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.receive.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 7028756d-1dcc-480c-bbcd-e9654f0772a0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f45aa579d37d1fdd3a3124eea972014ce839fdc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752254"
---
# <a name="message-queue-task-editor-receive-page"></a><span data-ttu-id="bdf59-102">Editor de la tarea Cola de mensajes (página Recibir)</span><span class="sxs-lookup"><span data-stu-id="bdf59-102">Message Queue Task Editor (Receive Page)</span></span>
  <span data-ttu-id="bdf59-103">Use la página **Recibir** del cuadro de diálogo **Editor de la tarea Cola de mensajes** para configurar una tarea de la cola de mensajes para recibir mensajes de [!INCLUDE[msCoName](../includes/msconame-md.md)] Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="bdf59-103">Use the **Receive** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to receive [!INCLUDE[msCoName](../includes/msconame-md.md)] Message Queuing (MSMQ) messages.</span></span>  
  
 <span data-ttu-id="bdf59-104">Para obtener información acerca de esta tarea, vea [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="bdf59-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="bdf59-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="bdf59-105">Options</span></span>  
 <span data-ttu-id="bdf59-106">**RemoveFromMessageQueue**</span><span class="sxs-lookup"><span data-stu-id="bdf59-106">**RemoveFromMessageQueue**</span></span>  
 <span data-ttu-id="bdf59-107">Indique si desea eliminar el mensaje de la cola una vez recibido.</span><span class="sxs-lookup"><span data-stu-id="bdf59-107">Indicate whether to remove the message from the queue after it is received.</span></span> <span data-ttu-id="bdf59-108">De forma predeterminada, este valor está establecido en `False`.</span><span class="sxs-lookup"><span data-stu-id="bdf59-108">By default, this value is set to `False`.</span></span>  
  
 <span data-ttu-id="bdf59-109">**ErrorIfMessageTimeOut**</span><span class="sxs-lookup"><span data-stu-id="bdf59-109">**ErrorIfMessageTimeOut**</span></span>  
 <span data-ttu-id="bdf59-110">Indique si desea mostrar un mensaje de error si se produce un error en la tarea al exceder el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="bdf59-110">Indicate whether the task fails when the message times out, displaying an error message.</span></span> <span data-ttu-id="bdf59-111">El valor predeterminado es `False`.</span><span class="sxs-lookup"><span data-stu-id="bdf59-111">The default is `False`.</span></span>  
  
 <span data-ttu-id="bdf59-112">**TimeoutAfter**</span><span class="sxs-lookup"><span data-stu-id="bdf59-112">**TimeoutAfter**</span></span>  
 <span data-ttu-id="bdf59-113">Si elige mostrar un mensaje de error al producirse errores en la tarea, indique el número de segundos que deben transcurrir antes de mostrar el mensaje de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="bdf59-113">If you choose to display an error message on task failure, specify the number of seconds to wait before displaying the time-out message.</span></span>  
  
 <span data-ttu-id="bdf59-114">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="bdf59-114">**MessageType**</span></span>  
 <span data-ttu-id="bdf59-115">Seleccione el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="bdf59-115">Select the message type.</span></span> <span data-ttu-id="bdf59-116">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="bdf59-116">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="bdf59-117">Value</span><span class="sxs-lookup"><span data-stu-id="bdf59-117">Value</span></span>|<span data-ttu-id="bdf59-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdf59-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bdf59-119">**Mensaje de archivo de datos**</span><span class="sxs-lookup"><span data-stu-id="bdf59-119">**Data file message**</span></span>|<span data-ttu-id="bdf59-120">El mensaje se almacena en un archivo.</span><span class="sxs-lookup"><span data-stu-id="bdf59-120">The message is stored in a file.</span></span> <span data-ttu-id="bdf59-121">Al seleccionar este valor se muestra la opción dinámica **DataFileMessage**.</span><span class="sxs-lookup"><span data-stu-id="bdf59-121">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="bdf59-122">**Mensaje de variable**</span><span class="sxs-lookup"><span data-stu-id="bdf59-122">**Variable message**</span></span>|<span data-ttu-id="bdf59-123">El mensaje se almacena en una variable.</span><span class="sxs-lookup"><span data-stu-id="bdf59-123">The message is stored in a variable.</span></span> <span data-ttu-id="bdf59-124">Al seleccionar este valor se muestra la opción dinámica **VariableMessage**.</span><span class="sxs-lookup"><span data-stu-id="bdf59-124">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="bdf59-125">**Mensaje de cadena**</span><span class="sxs-lookup"><span data-stu-id="bdf59-125">**String message**</span></span>|<span data-ttu-id="bdf59-126">El mensaje se almacena en la tarea Cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="bdf59-126">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="bdf59-127">Al seleccionar este valor se muestra la opción dinámica **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="bdf59-127">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
|<span data-ttu-id="bdf59-128">**Mensaje de cadena para variable**</span><span class="sxs-lookup"><span data-stu-id="bdf59-128">**String message to variable**</span></span>|<span data-ttu-id="bdf59-129">El mensaje.</span><span class="sxs-lookup"><span data-stu-id="bdf59-129">The message</span></span><br /><br /> <span data-ttu-id="bdf59-130">Al seleccionar este valor se muestra la opción dinámica **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="bdf59-130">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="bdf59-131">Opciones dinámicas de MessageType</span><span class="sxs-lookup"><span data-stu-id="bdf59-131">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="bdf59-132">MessageType = Mensaje de archivo de datos</span><span class="sxs-lookup"><span data-stu-id="bdf59-132">MessageType = Data file message</span></span>  
 <span data-ttu-id="bdf59-133">**SaveFileAs**</span><span class="sxs-lookup"><span data-stu-id="bdf59-133">**SaveFileAs**</span></span>  
 <span data-ttu-id="bdf59-134">Escriba la ruta del archivo que quiere usar, o bien haga clic en el botón de puntos suspensivos **(…)** para buscar el archivo.</span><span class="sxs-lookup"><span data-stu-id="bdf59-134">Type the path of the file to use, or click the ellipsis button **(...)** and then locate the file.</span></span>  
  
 <span data-ttu-id="bdf59-135">**Sobrescribir**</span><span class="sxs-lookup"><span data-stu-id="bdf59-135">**Overwrite**</span></span>  
 <span data-ttu-id="bdf59-136">Indique si desea sobrescribir los datos de un archivo existente al guardar el contenido del mensaje de archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="bdf59-136">Indicate whether to overwrite the data in an existing file when saving the contents of a data file message.</span></span> <span data-ttu-id="bdf59-137">El valor predeterminado es `False`.</span><span class="sxs-lookup"><span data-stu-id="bdf59-137">The default is `False`.</span></span>  
  
 <span data-ttu-id="bdf59-138">**Filter**</span><span class="sxs-lookup"><span data-stu-id="bdf59-138">**Filter**</span></span>  
 <span data-ttu-id="bdf59-139">Indique si desea aplicar un filtro al mensaje.</span><span class="sxs-lookup"><span data-stu-id="bdf59-139">Specify whether to apply a filter to the message.</span></span> <span data-ttu-id="bdf59-140">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="bdf59-140">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="bdf59-141">Value</span><span class="sxs-lookup"><span data-stu-id="bdf59-141">Value</span></span>|<span data-ttu-id="bdf59-142">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdf59-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bdf59-143">**Sin filtro**</span><span class="sxs-lookup"><span data-stu-id="bdf59-143">**No filter**</span></span>|<span data-ttu-id="bdf59-144">La tarea no filtra mensajes.</span><span class="sxs-lookup"><span data-stu-id="bdf59-144">The task does not filter messages.</span></span> <span data-ttu-id="bdf59-145">Al seleccionar este valor se muestra la opción dinámica **IdentifierReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="bdf59-145">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="bdf59-146">**De paquete**</span><span class="sxs-lookup"><span data-stu-id="bdf59-146">**From package**</span></span>|<span data-ttu-id="bdf59-147">El mensaje solo recibe mensajes del paquete seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bdf59-147">The message receives only messages from the specified package.</span></span> <span data-ttu-id="bdf59-148">Al seleccionar este valor se muestra la opción dinámica **Identifier**.</span><span class="sxs-lookup"><span data-stu-id="bdf59-148">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="bdf59-149">Opciones dinámicas de Filtro</span><span class="sxs-lookup"><span data-stu-id="bdf59-149">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="bdf59-150">Filtro = Sin filtro</span><span class="sxs-lookup"><span data-stu-id="bdf59-150">Filter = No filter</span></span>  
 <span data-ttu-id="bdf59-151">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="bdf59-151">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="bdf59-152">Esta opción es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="bdf59-152">This option is read-only.</span></span> <span data-ttu-id="bdf59-153">Podría estar en blanco o contener el GUID de un paquete si se ha establecido anteriormente la propiedad Filtro.</span><span class="sxs-lookup"><span data-stu-id="bdf59-153">It may be blank or contain the GUID of a package when the Filter property was previously set.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="bdf59-154">Filtro = De paquete</span><span class="sxs-lookup"><span data-stu-id="bdf59-154">Filter = From package</span></span>  
 <span data-ttu-id="bdf59-155">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="bdf59-155">**Identifier**</span></span>  
 <span data-ttu-id="bdf59-156">Si decide aplicar un filtro, escriba el identificador único del paquete del que se recibirán los mensajes, o bien haga clic en el botón de puntos suspensivos **(…)** y, después, especifique el paquete.</span><span class="sxs-lookup"><span data-stu-id="bdf59-156">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="bdf59-157">**Temas relacionados:** [Seleccionar un paquete](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="bdf59-157">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="bdf59-158">MessageType = Mensaje de variable</span><span class="sxs-lookup"><span data-stu-id="bdf59-158">MessageType = Variable message</span></span>  
 <span data-ttu-id="bdf59-159">**Filter**</span><span class="sxs-lookup"><span data-stu-id="bdf59-159">**Filter**</span></span>  
 <span data-ttu-id="bdf59-160">Especifica si se desea aplicar un filtro a los mensajes.</span><span class="sxs-lookup"><span data-stu-id="bdf59-160">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="bdf59-161">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="bdf59-161">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="bdf59-162">Value</span><span class="sxs-lookup"><span data-stu-id="bdf59-162">Value</span></span>|<span data-ttu-id="bdf59-163">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdf59-163">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bdf59-164">**Sin filtro**</span><span class="sxs-lookup"><span data-stu-id="bdf59-164">**No filter**</span></span>|<span data-ttu-id="bdf59-165">La tarea no filtra mensajes.</span><span class="sxs-lookup"><span data-stu-id="bdf59-165">The task does not filter messages.</span></span> <span data-ttu-id="bdf59-166">Al seleccionar este valor se muestra la opción dinámica **IdentifierReadOnly**.</span><span class="sxs-lookup"><span data-stu-id="bdf59-166">Selecting the value displays the dynamic option, **IdentifierReadOnly**.</span></span>|  
|<span data-ttu-id="bdf59-167">**De paquete**</span><span class="sxs-lookup"><span data-stu-id="bdf59-167">**From package**</span></span>|<span data-ttu-id="bdf59-168">El mensaje solo recibe mensajes del paquete seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bdf59-168">The message receives only messages from the specified package.</span></span> <span data-ttu-id="bdf59-169">Al seleccionar este valor se muestra la opción dinámica **Identifier**.</span><span class="sxs-lookup"><span data-stu-id="bdf59-169">Selecting the value displays the dynamic option, **Identifier**.</span></span>|  
  
 <span data-ttu-id="bdf59-170">**Variable**</span><span class="sxs-lookup"><span data-stu-id="bdf59-170">**Variable**</span></span>  
 <span data-ttu-id="bdf59-171">Escriba el nombre de la variable o haga clic en \<**New variable...**> para configurar una nueva variable.</span><span class="sxs-lookup"><span data-stu-id="bdf59-171">Type the variable name, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="bdf59-172">**Temas relacionados:** [Agregar variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="bdf59-172">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
### <a name="filter-dynamic-options"></a><span data-ttu-id="bdf59-173">Opciones dinámicas de Filtro</span><span class="sxs-lookup"><span data-stu-id="bdf59-173">Filter Dynamic Options</span></span>  
  
#### <a name="filter--no-filter"></a><span data-ttu-id="bdf59-174">Filtro = Sin filtro</span><span class="sxs-lookup"><span data-stu-id="bdf59-174">Filter = No filter</span></span>  
 <span data-ttu-id="bdf59-175">**IdentifierReadOnly**</span><span class="sxs-lookup"><span data-stu-id="bdf59-175">**IdentifierReadOnly**</span></span>  
 <span data-ttu-id="bdf59-176">Esta opción está en blanco.</span><span class="sxs-lookup"><span data-stu-id="bdf59-176">This option is blank.</span></span>  
  
#### <a name="filter--from-package"></a><span data-ttu-id="bdf59-177">Filtro = De paquete</span><span class="sxs-lookup"><span data-stu-id="bdf59-177">Filter = From package</span></span>  
 <span data-ttu-id="bdf59-178">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="bdf59-178">**Identifier**</span></span>  
 <span data-ttu-id="bdf59-179">Si decide aplicar un filtro, escriba el identificador único del paquete del que se recibirán los mensajes, o bien haga clic en el botón de puntos suspensivos **(…)** y, después, especifique el paquete.</span><span class="sxs-lookup"><span data-stu-id="bdf59-179">If you choose to apply a filter, type the unique identifier of the package from which messages can be received, or click the ellipsis button **(...)** and then specify the package.</span></span>  
  
 <span data-ttu-id="bdf59-180">**Temas relacionados:** [Seleccionar un paquete](control-flow/select-a-package.md)</span><span class="sxs-lookup"><span data-stu-id="bdf59-180">**Related Topics:** [Select a Package](control-flow/select-a-package.md)</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="bdf59-181">MessageType = Mensaje de cadena</span><span class="sxs-lookup"><span data-stu-id="bdf59-181">MessageType = String message</span></span>  
 <span data-ttu-id="bdf59-182">**Comparar**</span><span class="sxs-lookup"><span data-stu-id="bdf59-182">**Compare**</span></span>  
 <span data-ttu-id="bdf59-183">Especifica si se desea aplicar un filtro a los mensajes.</span><span class="sxs-lookup"><span data-stu-id="bdf59-183">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="bdf59-184">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="bdf59-184">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="bdf59-185">Value</span><span class="sxs-lookup"><span data-stu-id="bdf59-185">Value</span></span>|<span data-ttu-id="bdf59-186">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdf59-186">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bdf59-187">**None**</span><span class="sxs-lookup"><span data-stu-id="bdf59-187">**None**</span></span>|<span data-ttu-id="bdf59-188">Los mensajes no se comparan.</span><span class="sxs-lookup"><span data-stu-id="bdf59-188">Messages are not compared.</span></span>|  
|<span data-ttu-id="bdf59-189">**Coincidencia exacta**</span><span class="sxs-lookup"><span data-stu-id="bdf59-189">**Exact match**</span></span>|<span data-ttu-id="bdf59-190">Los mensajes deben coincidir exactamente con la cadena de la opción **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="bdf59-190">Messages must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="bdf59-191">**Omitir mayúsculas y minúsculas**</span><span class="sxs-lookup"><span data-stu-id="bdf59-191">**Ignore case**</span></span>|<span data-ttu-id="bdf59-192">El mensaje debe coincidir con la cadena de la opción **CompareString** , pero la comparación no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bdf59-192">Message must match the string in the **CompareString** option, but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="bdf59-193">**Que contenga**</span><span class="sxs-lookup"><span data-stu-id="bdf59-193">**Containing**</span></span>|<span data-ttu-id="bdf59-194">El mensaje debe contener la cadena de la opción **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="bdf59-194">Message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="bdf59-195">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="bdf59-195">**CompareString**</span></span>  
 <span data-ttu-id="bdf59-196">A menos que la opción **Comparar** se haya establecido en **Ninguno**, deberá indicar la cadena con la que se comparará el mensaje.</span><span class="sxs-lookup"><span data-stu-id="bdf59-196">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
### <a name="messagetype--string-message-to-variable"></a><span data-ttu-id="bdf59-197">MessageType = Mensaje de cadena para variable</span><span class="sxs-lookup"><span data-stu-id="bdf59-197">MessageType = String message to variable</span></span>  
 <span data-ttu-id="bdf59-198">**Comparar**</span><span class="sxs-lookup"><span data-stu-id="bdf59-198">**Compare**</span></span>  
 <span data-ttu-id="bdf59-199">Especifica si se desea aplicar un filtro a los mensajes.</span><span class="sxs-lookup"><span data-stu-id="bdf59-199">Specify whether to apply a filter to messages.</span></span> <span data-ttu-id="bdf59-200">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="bdf59-200">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="bdf59-201">Value</span><span class="sxs-lookup"><span data-stu-id="bdf59-201">Value</span></span>|<span data-ttu-id="bdf59-202">Descripción</span><span class="sxs-lookup"><span data-stu-id="bdf59-202">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bdf59-203">**None**</span><span class="sxs-lookup"><span data-stu-id="bdf59-203">**None**</span></span>|<span data-ttu-id="bdf59-204">Los mensajes no se comparan.</span><span class="sxs-lookup"><span data-stu-id="bdf59-204">Messages are not compared.</span></span>|  
|<span data-ttu-id="bdf59-205">**Coincidencia exacta**</span><span class="sxs-lookup"><span data-stu-id="bdf59-205">**Exact match**</span></span>|<span data-ttu-id="bdf59-206">Los mensajes deben coincidir exactamente con la cadena de la opción **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="bdf59-206">The message must match exactly the string in the **CompareString** option.</span></span>|  
|<span data-ttu-id="bdf59-207">**Omitir mayúsculas y minúsculas**</span><span class="sxs-lookup"><span data-stu-id="bdf59-207">**Ignore case**</span></span>|<span data-ttu-id="bdf59-208">El mensaje debe coincidir con la cadena de la opción **CompareString** , pero la comparación no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bdf59-208">The message must match the string in the **CompareString** option but the comparison is not case sensitive.</span></span>|  
|<span data-ttu-id="bdf59-209">**Que contenga**</span><span class="sxs-lookup"><span data-stu-id="bdf59-209">**Containing**</span></span>|<span data-ttu-id="bdf59-210">El mensaje debe contener la cadena de la opción **CompareString** .</span><span class="sxs-lookup"><span data-stu-id="bdf59-210">The message must contain the string in the **CompareString** option.</span></span>|  
  
 <span data-ttu-id="bdf59-211">**CompareString**</span><span class="sxs-lookup"><span data-stu-id="bdf59-211">**CompareString**</span></span>  
 <span data-ttu-id="bdf59-212">A menos que la opción **Comparar** se haya establecido en **Ninguno**, deberá indicar la cadena con la que se comparará el mensaje.</span><span class="sxs-lookup"><span data-stu-id="bdf59-212">Unless the **Compare** option is set to **None**, provide the string to which the message is compared.</span></span>  
  
 <span data-ttu-id="bdf59-213">**Variable**</span><span class="sxs-lookup"><span data-stu-id="bdf59-213">**Variable**</span></span>  
 <span data-ttu-id="bdf59-214">Escriba el nombre de la variable para conservar el mensaje recibido, o haga clic en \<**New variable...**> y, después, configure una nueva variable.</span><span class="sxs-lookup"><span data-stu-id="bdf59-214">Type the name of the variable to hold the received message, or click \<**New variable...**> and then configure a new variable.</span></span>  
  
 <span data-ttu-id="bdf59-215">**Temas relacionados:** [Agregar variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="bdf59-215">**Related Topics:** [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf59-216">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bdf59-216">See Also</span></span>  
 <span data-ttu-id="bdf59-217">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="bdf59-217">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="bdf59-218">[Editor de la tarea cola de mensajes &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="bdf59-218">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="bdf59-219">[Editor de la tarea cola de mensajes &#40;página envío&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="bdf59-219">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 <span data-ttu-id="bdf59-220">[Página Expresiones](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="bdf59-220">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="bdf59-221">Tarea Cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="bdf59-221">Message Queue Task</span></span>](control-flow/message-queue-task.md)  
  
  
