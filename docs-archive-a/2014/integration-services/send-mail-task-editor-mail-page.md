---
title: Editor de la tarea enviar correo (página correo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.mail.f1
helpviewer_keywords:
- Send Mail Task Editor
ms.assetid: adb385d5-ef24-4d18-b9ea-b39e00a7075e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 52cab62f3c88ea248b76061664547fd8f1314099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751305"
---
# <a name="send-mail-task-editor-mail-page"></a><span data-ttu-id="5e798-102">Editor de la tarea Enviar correo (página Correo)</span><span class="sxs-lookup"><span data-stu-id="5e798-102">Send Mail Task Editor (Mail Page)</span></span>
  <span data-ttu-id="5e798-103">Use la página **Correo** del cuadro de diálogo **Editor de la tarea Enviar correo** para especificar los destinatarios, el tipo de mensaje y la prioridad de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="5e798-103">Use the **Mail** page of the **Send Mail Task Editor** dialog box to specify recipients, message type, and priority for a message.</span></span> <span data-ttu-id="5e798-104">También puede adjuntar archivos al mensaje.</span><span class="sxs-lookup"><span data-stu-id="5e798-104">You can also attach files to the message.</span></span> <span data-ttu-id="5e798-105">El texto del mensaje puede consistir en una cadena que proporcione, una conexión de archivo a un archivo con el texto o el nombre de una variable con el texto.</span><span class="sxs-lookup"><span data-stu-id="5e798-105">The message text can be a string you provide, a file connection to a file that contains the text, or the name of a variable that contains the text.</span></span>  
  
 <span data-ttu-id="5e798-106">Para obtener información acerca de esta tarea, vea [Send Mail Task](control-flow/send-mail-task.md).</span><span class="sxs-lookup"><span data-stu-id="5e798-106">To learn about this task, see [Send Mail Task](control-flow/send-mail-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5e798-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="5e798-107">Options</span></span>  
 <span data-ttu-id="5e798-108">**SMTPConnection**</span><span class="sxs-lookup"><span data-stu-id="5e798-108">**SMTPConnection**</span></span>  
 <span data-ttu-id="5e798-109">Seleccione un administrador de conexiones SMTP de la lista o haga clic en **\<New connection...>** para crear un nuevo administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="5e798-109">Select an SMTP connection manager in the list, or click **\<New connection...>** to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5e798-110">El administrador de conexiones SMTP solo es compatible con la autenticación anónima y la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="5e798-110">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="5e798-111">No admite la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="5e798-111">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="5e798-112">**Temas relacionados:** [Administrador de conexiones SMTP](connection-manager/smtp-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="5e798-112">**Related Topics:** [SMTP Connection Manager](connection-manager/smtp-connection-manager.md)</span></span>  
  
 <span data-ttu-id="5e798-113">**From**</span><span class="sxs-lookup"><span data-stu-id="5e798-113">**From**</span></span>  
 <span data-ttu-id="5e798-114">Especifique la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="5e798-114">Specify the e-mail address of the sender.</span></span>  
  
 <span data-ttu-id="5e798-115">**To**</span><span class="sxs-lookup"><span data-stu-id="5e798-115">**To**</span></span>  
 <span data-ttu-id="5e798-116">Escriba las direcciones de correo electrónico de los destinatarios, separadas con punto y coma.</span><span class="sxs-lookup"><span data-stu-id="5e798-116">Provide the e-mail addresses of the recipients, delimited by semicolons.</span></span>  
  
 <span data-ttu-id="5e798-117">**CC**</span><span class="sxs-lookup"><span data-stu-id="5e798-117">**Cc**</span></span>  
 <span data-ttu-id="5e798-118">Escriba las direcciones de correo electrónico de las personas que recibirán una copia del mensaje, separadas con punto y coma.</span><span class="sxs-lookup"><span data-stu-id="5e798-118">Specify the e-mail addresses, delimited by semicolons, of individuals who also receive copies of the message.</span></span>  
  
 <span data-ttu-id="5e798-119">**CCO**</span><span class="sxs-lookup"><span data-stu-id="5e798-119">**Bcc**</span></span>  
 <span data-ttu-id="5e798-120">Escriba las direcciones de correo electrónico de los destinatarios ocultos de copia del mensaje, separadas con punto y coma.</span><span class="sxs-lookup"><span data-stu-id="5e798-120">Specify the e-mail addresses, delimited by semicolons, of individuals who receive blind carbon copies (Bcc) copies of the message.</span></span>  
  
 <span data-ttu-id="5e798-121">**Subject**</span><span class="sxs-lookup"><span data-stu-id="5e798-121">**Subject**</span></span>  
 <span data-ttu-id="5e798-122">Escriba el asunto del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="5e798-122">Provide a subject for the e-mail message.</span></span>  
  
 <span data-ttu-id="5e798-123">**MessageSourceType**</span><span class="sxs-lookup"><span data-stu-id="5e798-123">**MessageSourceType**</span></span>  
 <span data-ttu-id="5e798-124">Permite seleccionar el tipo de origen del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5e798-124">Select the source type of the message.</span></span> <span data-ttu-id="5e798-125">Esta propiedad presenta las opciones indicadas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="5e798-125">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="5e798-126">Value</span><span class="sxs-lookup"><span data-stu-id="5e798-126">Value</span></span>|<span data-ttu-id="5e798-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e798-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5e798-128">**Entrada directa**</span><span class="sxs-lookup"><span data-stu-id="5e798-128">**Direct input**</span></span>|<span data-ttu-id="5e798-129">Establezca el origen para el texto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5e798-129">Set the source to the message text.</span></span> <span data-ttu-id="5e798-130">Si selecciona este valor, se mostrará la opción dinámica **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="5e798-130">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="5e798-131">**Conexión de archivos**</span><span class="sxs-lookup"><span data-stu-id="5e798-131">**File connection**</span></span>|<span data-ttu-id="5e798-132">Establezca el origen al archivo que incluye el texto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5e798-132">Set the source to the file that contains the message text.</span></span> <span data-ttu-id="5e798-133">Si selecciona este valor, se mostrará la opción dinámica **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="5e798-133">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="5e798-134">**Variable**</span><span class="sxs-lookup"><span data-stu-id="5e798-134">**Variable**</span></span>|<span data-ttu-id="5e798-135">Establezca el origen para la variable que incluye el texto del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5e798-135">Set the source to a variable that contains the message text.</span></span> <span data-ttu-id="5e798-136">Si selecciona este valor, se mostrará la opción dinámica **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="5e798-136">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
  
 <span data-ttu-id="5e798-137">**Prioridad**</span><span class="sxs-lookup"><span data-stu-id="5e798-137">**Priority**</span></span>  
 <span data-ttu-id="5e798-138">Establezca la prioridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5e798-138">Set the priority of the message.</span></span>  
  
 <span data-ttu-id="5e798-139">**Datos adjuntos**</span><span class="sxs-lookup"><span data-stu-id="5e798-139">**Attachments**</span></span>  
 <span data-ttu-id="5e798-140">Escriba los nombres de los archivos de datos adjuntos que desea adjuntar al mensaje de correo electrónico, separados por una barra vertical (|).</span><span class="sxs-lookup"><span data-stu-id="5e798-140">Provide the file names of attachments to the e-mail message, delimited by the pipe (|) character.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5e798-141">Las líneas Para, CC y CCO están limitadas a 256 caracteres según las normas de Internet.</span><span class="sxs-lookup"><span data-stu-id="5e798-141">The To, Cc, and Bcc lines are limited to 256 characters in accordance with Internet standards.</span></span>  
  
## <a name="messagesourcetype-dynamic-options"></a><span data-ttu-id="5e798-142">Opciones dinámicas de MessageSourceType</span><span class="sxs-lookup"><span data-stu-id="5e798-142">MessageSourceType Dynamic Options</span></span>  
  
### <a name="messagesourcetype--direct-input"></a><span data-ttu-id="5e798-143">MessageSourceType = Entrada directa</span><span class="sxs-lookup"><span data-stu-id="5e798-143">MessageSourceType = Direct Input</span></span>  
 <span data-ttu-id="5e798-144">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="5e798-144">**MessageSource**</span></span>  
 <span data-ttu-id="5e798-145">Escriba el texto del mensaje, o bien haga clic en el botón Examinar (…) y escriba el mensaje en el cuadro de diálogo **Origen del mensaje**.</span><span class="sxs-lookup"><span data-stu-id="5e798-145">Type the message text or click the browse button (...) and then type the message in the **Message source** dialog box.</span></span>  
  
### <a name="messagesourcetype--file-connection"></a><span data-ttu-id="5e798-146">MessageSourceType = Conexión de archivos</span><span class="sxs-lookup"><span data-stu-id="5e798-146">MessageSourceType = File connection</span></span>  
 <span data-ttu-id="5e798-147">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="5e798-147">**MessageSource**</span></span>  
 <span data-ttu-id="5e798-148">Seleccione un administrador de conexiones de archivos de la lista o haga clic en \<**New connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="5e798-148">Select a File connection manager in the list or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="5e798-149">**Temas relacionados:** [Administrador de conexiones de archivos](connection-manager/file-connection-manager.md), [Editor de administrador de conexiones de archivos](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="5e798-149">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="messagesourcetype--variable"></a><span data-ttu-id="5e798-150">MessageSourceType = Variable</span><span class="sxs-lookup"><span data-stu-id="5e798-150">MessageSourceType = Variable</span></span>  
 <span data-ttu-id="5e798-151">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="5e798-151">**MessageSource**</span></span>  
 <span data-ttu-id="5e798-152">Seleccione una variable de la lista o haga clic en \<**New variable...**> para crear una nueva variable.</span><span class="sxs-lookup"><span data-stu-id="5e798-152">Select a variable in the list or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="5e798-153">**Temas relacionados:** [Variables de Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Agregar variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="5e798-153">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e798-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5e798-154">See Also</span></span>  
 <span data-ttu-id="5e798-155">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5e798-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="5e798-156">[Editor de la tarea enviar correo &#40;página general&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="5e798-156">[Send Mail Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="5e798-157">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="5e798-157">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
