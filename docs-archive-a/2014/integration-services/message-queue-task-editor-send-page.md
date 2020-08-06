---
title: Editor de la tarea cola de mensajes (página enviar) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.send.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 565aa079-ac44-4407-8efc-cddab839de30
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3534e1a8b475f22064ef7f2283c2e70eb561294f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752253"
---
# <a name="message-queue-task-editor-send-page"></a><span data-ttu-id="11621-102">Editor de la tarea Cola de mensajes (página Enviar)</span><span class="sxs-lookup"><span data-stu-id="11621-102">Message Queue Task Editor (Send Page)</span></span>
  <span data-ttu-id="11621-103">Utilice la página **Enviar** del cuadro de diálogo **Editor de la tarea Cola de mensajes** para configurar una tarea Cola de mensajes para enviar mensajes desde un paquete de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11621-103">Use the **Send** page of the **Message Queue Task Editor** dialog box to configure a Message Queue task to send messages from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="11621-104">Para obtener información acerca de esta tarea, vea [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="11621-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="11621-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="11621-105">Options</span></span>  
 <span data-ttu-id="11621-106">**UseEncryption**</span><span class="sxs-lookup"><span data-stu-id="11621-106">**UseEncryption**</span></span>  
 <span data-ttu-id="11621-107">Indica si se debe cifrar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="11621-107">Indicate whether to encrypt the message.</span></span> <span data-ttu-id="11621-108">El valor predeterminado es `False`.</span><span class="sxs-lookup"><span data-stu-id="11621-108">The default is `False`.</span></span>  
  
 <span data-ttu-id="11621-109">**EncryptionAlgorithm**</span><span class="sxs-lookup"><span data-stu-id="11621-109">**EncryptionAlgorithm**</span></span>  
 <span data-ttu-id="11621-110">Si opta por usar cifrado, especifique el nombre del algoritmo de cifrado que debe utilizarse.</span><span class="sxs-lookup"><span data-stu-id="11621-110">If you choose to use encryption, specify the name of the encryption algorithm to use.</span></span> <span data-ttu-id="11621-111">La tarea Cola de mensajes puede utilizar los algoritmos RC2 y RC4.</span><span class="sxs-lookup"><span data-stu-id="11621-111">The Message Queue task can use the RC2 and RC4 algorithms.</span></span> <span data-ttu-id="11621-112">El valor predeterminado es **RC2**.</span><span class="sxs-lookup"><span data-stu-id="11621-112">The default is **RC2**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11621-113">El algoritmo RC4 se admite únicamente por razones de compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="11621-113">The RC4 algorithm is only supported for backward compatibility.</span></span> <span data-ttu-id="11621-114">El material nuevo solo se puede cifrar con RC4 o RC4_128 cuando la base de datos tenga el nivel de compatibilidad 90 o 100.</span><span class="sxs-lookup"><span data-stu-id="11621-114">New material can only be encrypted using RC4 or RC4_128 when the database is in compatibility level 90 or 100.</span></span> <span data-ttu-id="11621-115">(No se recomienda). Use un algoritmo más reciente como uno de los algoritmos AES en su lugar.</span><span class="sxs-lookup"><span data-stu-id="11621-115">(Not recommended.) Use a newer algorithm such as one of the AES algorithms instead.</span></span> <span data-ttu-id="11621-116">En la versión actual de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], el material cifrado con RC4 o RC4_128 se puede descifrar en cualquier nivel de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="11621-116">In the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], material encrypted using RC4 or RC4_128 can be decrypted in any compatibility level.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="11621-117">Éstos son los algoritmos de cifrado que admite la tecnología de Message Queue Server (que también recibe el nombre de MSMQ).</span><span class="sxs-lookup"><span data-stu-id="11621-117">These are the encryption algorithms that the Message Queuing (also known as MSMQ) technology supports.</span></span> <span data-ttu-id="11621-118">Ambos algoritmos de cifrado se consideran en estos momentos criptográficamente menos seguros que otros algoritmos más recientes con los que Message Queue Server aún no es compatible.</span><span class="sxs-lookup"><span data-stu-id="11621-118">Both of these encryption algorithms are now considered cryptographically weak compared to newer algorithms, which Message Queuing does not yet support.</span></span> <span data-ttu-id="11621-119">Por tanto, debe considerar con detenimiento sus necesidades criptográficas a la hora de enviar mensajes con la tarea Cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="11621-119">Therefore, you should consider your cryptography needs carefully when sending messages using the Message Queue task.</span></span>  
  
 <span data-ttu-id="11621-120">**MessageType**</span><span class="sxs-lookup"><span data-stu-id="11621-120">**MessageType**</span></span>  
 <span data-ttu-id="11621-121">Seleccione el tipo de mensaje.</span><span class="sxs-lookup"><span data-stu-id="11621-121">Select the message type.</span></span> <span data-ttu-id="11621-122">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="11621-122">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="11621-123">Value</span><span class="sxs-lookup"><span data-stu-id="11621-123">Value</span></span>|<span data-ttu-id="11621-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="11621-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="11621-125">**Mensaje de archivo de datos**</span><span class="sxs-lookup"><span data-stu-id="11621-125">**Data file message**</span></span>|<span data-ttu-id="11621-126">El mensaje se almacena en un archivo.</span><span class="sxs-lookup"><span data-stu-id="11621-126">The message is stored in a file.</span></span> <span data-ttu-id="11621-127">Al seleccionar este valor se muestra la opción dinámica **DataFileMessage**.</span><span class="sxs-lookup"><span data-stu-id="11621-127">Selecting the value displays the dynamic option, **DataFileMessage**.</span></span>|  
|<span data-ttu-id="11621-128">**Mensaje de variable**</span><span class="sxs-lookup"><span data-stu-id="11621-128">**Variable message**</span></span>|<span data-ttu-id="11621-129">El mensaje se almacena en una variable.</span><span class="sxs-lookup"><span data-stu-id="11621-129">The message is stored in a variable.</span></span> <span data-ttu-id="11621-130">Al seleccionar este valor se muestra la opción dinámica **VariableMessage**.</span><span class="sxs-lookup"><span data-stu-id="11621-130">Selecting the value displays the dynamic option, **VariableMessage**.</span></span>|  
|<span data-ttu-id="11621-131">**Mensaje de cadena**</span><span class="sxs-lookup"><span data-stu-id="11621-131">**String message**</span></span>|<span data-ttu-id="11621-132">El mensaje se almacena en la tarea Cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="11621-132">The message is stored in the Message Queue task.</span></span> <span data-ttu-id="11621-133">Al seleccionar este valor se muestra la opción dinámica **StringMessage**.</span><span class="sxs-lookup"><span data-stu-id="11621-133">Selecting the value displays the dynamic option, **StringMessage**.</span></span>|  
  
## <a name="messagetype-dynamic-options"></a><span data-ttu-id="11621-134">Opciones dinámicas de MessageType</span><span class="sxs-lookup"><span data-stu-id="11621-134">MessageType Dynamic Options</span></span>  
  
### <a name="messagetype--data-file-message"></a><span data-ttu-id="11621-135">MessageType = Mensaje de archivo de datos</span><span class="sxs-lookup"><span data-stu-id="11621-135">MessageType = Data file message</span></span>  
 <span data-ttu-id="11621-136">**DataFileMessage**</span><span class="sxs-lookup"><span data-stu-id="11621-136">**DataFileMessage**</span></span>  
 <span data-ttu-id="11621-137">Escriba la ruta de acceso del archivo de datos, o bien haga clic en el botón de puntos suspensivos **(…)** y busque el archivo.</span><span class="sxs-lookup"><span data-stu-id="11621-137">Type the path of the data file, or click the ellipsis **(...)** and then locate the file.</span></span>  
  
### <a name="messagetype--variable-message"></a><span data-ttu-id="11621-138">MessageType = Mensaje de variable</span><span class="sxs-lookup"><span data-stu-id="11621-138">MessageType = Variable message</span></span>  
 <span data-ttu-id="11621-139">**VariableMessage**</span><span class="sxs-lookup"><span data-stu-id="11621-139">**VariableMessage**</span></span>  
 <span data-ttu-id="11621-140">Escriba los nombres de variable, o bien haga clic en el botón de puntos suspensivos **(…)** y seleccione las variables.</span><span class="sxs-lookup"><span data-stu-id="11621-140">Type the variable names, or click the ellipsis **(...)** and then select the variables.</span></span> <span data-ttu-id="11621-141">Las variables se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="11621-141">Variables are separated by commas.</span></span>  
  
 <span data-ttu-id="11621-142">**Temas relacionados:** Seleccionar variables</span><span class="sxs-lookup"><span data-stu-id="11621-142">**Related Topics:** Select Variables</span></span>  
  
### <a name="messagetype--string-message"></a><span data-ttu-id="11621-143">MessageType = Mensaje de cadena</span><span class="sxs-lookup"><span data-stu-id="11621-143">MessageType = String message</span></span>  
 <span data-ttu-id="11621-144">**StringMessage**</span><span class="sxs-lookup"><span data-stu-id="11621-144">**StringMessage**</span></span>  
 <span data-ttu-id="11621-145">Escriba el mensaje de cadena, o bien haga clic en el botón de puntos suspensivos **(…)** y escriba el mensaje en el cuadro de diálogo **Escribir mensaje de cadena**.</span><span class="sxs-lookup"><span data-stu-id="11621-145">Type the string message, or click the ellipsis **(...)** and then type the message in the **Enter String Message** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11621-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11621-146">See Also</span></span>  
 <span data-ttu-id="11621-147">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="11621-147">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="11621-148">[Editor de la tarea cola de mensajes &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="11621-148">[Message Queue Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="11621-149">[Editor de la tarea cola de mensajes &#40;página de recepción&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="11621-149">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 [<span data-ttu-id="11621-150">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="11621-150">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
