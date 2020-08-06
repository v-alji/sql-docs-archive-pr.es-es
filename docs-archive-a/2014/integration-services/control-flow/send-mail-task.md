---
title: Tarea Enviar correo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.f1
helpviewer_keywords:
- mail [Integration Services]
- Send Mail task
- e-mail [Integration Services]
- messages [Integration Services]
- sending messages
ms.assetid: fe0b7cbc-fe8e-4fe2-95b4-2953efff5869
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c93723f3c443705acc14226ce07f456da4d5a884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669794"
---
# <a name="send-mail-task"></a><span data-ttu-id="c4ca8-102">Enviar correo, tarea</span><span class="sxs-lookup"><span data-stu-id="c4ca8-102">Send Mail Task</span></span>
  <span data-ttu-id="c4ca8-103">La tarea Enviar correo envía un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-103">The Send Mail task sends an e-mail message.</span></span> <span data-ttu-id="c4ca8-104">Un paquete puede utilizar la tarea Enviar correo para enviar mensajes si las tareas del paquete de flujo de trabajo finalizan correctamente o si se producen errores, o para enviar mensajes en respuesta a eventos provocados por el paquete en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-104">By using the Send Mail task, a package can send messages if tasks in the package workflow succeed or fail, or send messages in response to an event that the package raises at run time.</span></span> <span data-ttu-id="c4ca8-105">Por ejemplo, la tarea puede notificar a un administrador de base de datos si la tarea Copia de seguridad de la base de datos se realizó correctamente o no.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-105">For example, the task can notify a database administrator about the success or failure of the Backup Database task.</span></span>  
  
 <span data-ttu-id="c4ca8-106">Puede configurar la tarea Enviar correo de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="c4ca8-106">You can configure the Send Mail task in the following ways:</span></span>  
  
-   <span data-ttu-id="c4ca8-107">Proporcionar el texto del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-107">Provide the message text for the e-mail message.</span></span>  
  
-   <span data-ttu-id="c4ca8-108">Especificar el asunto del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-108">Provide a subject line for the e-mail message.</span></span>  
  
-   <span data-ttu-id="c4ca8-109">Establecer el nivel de prioridad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-109">Set the priority level of the message.</span></span> <span data-ttu-id="c4ca8-110">La tarea admite tres niveles de prioridad: normal, bajo y alto.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-110">The task supports three priority levels: normal, low, and high.</span></span>  
  
-   <span data-ttu-id="c4ca8-111">Especificar los destinatarios en las líneas Para, CC y CCO.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-111">Specify the recipients on the To, Cc, and Bcc lines.</span></span> <span data-ttu-id="c4ca8-112">Si la tarea especifica varios destinatarios, deben separarse mediante signos de punto y coma.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-112">If the task specifies multiple recipients, they are separated by semicolons.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4ca8-113">Las líneas Para, CC y CCO tienen un límite de 256 caracteres cada una, de acuerdo con los estándares de Internet.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-113">The To, Cc, and Bcc lines are limited to 256 characters each in accordance with Internet standards.</span></span>  
  
-   <span data-ttu-id="c4ca8-114">Incluir archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-114">Include attachments.</span></span> <span data-ttu-id="c4ca8-115">Si la tarea especifica varios archivos adjuntos, deben separarse mediante la barra vertical (|).</span><span class="sxs-lookup"><span data-stu-id="c4ca8-115">If the task specifies multiple attachments, they are separated by the pipe (|) character.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c4ca8-116">Si cuando se ejecuta el paquete no existe un archivo adjunto, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-116">If an attachment file does not exist when the package runs, an error occurs.</span></span>  
  
-   <span data-ttu-id="c4ca8-117">Especificar el administrador de conexiones SMTP que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-117">Specify the SMTP connection manager to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c4ca8-118">El administrador de conexiones SMTP solo es compatible con la autenticación anónima y la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-118">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="c4ca8-119">No admite la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-119">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="c4ca8-120">El texto del mensaje puede ser una cadena que especifique, una conexión a un archivo que contiene el texto o el nombre de una variable que contiene el texto que se va a enviar.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-120">The message text can be a string that you provide, a connection to a file that contains the text, or the name of a variable that contains the text.</span></span> <span data-ttu-id="c4ca8-121">La tarea usa el administrador de conexiones de archivos para conectar con un archivo.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-121">The task uses a File connection manager to connect to a file.</span></span> <span data-ttu-id="c4ca8-122">Para más información, consulte [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c4ca8-122">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="c4ca8-123">La tarea usa el administrador de conexiones SMTP para conectar con un servidor de correo.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-123">The task uses an SMTP connection manager to connect to a mail server.</span></span> <span data-ttu-id="c4ca8-124">Para más información, consulte [SMTP Connection Manager](../connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c4ca8-124">For more information, see [SMTP Connection Manager](../connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="custom-logging-messages-available-on-the-send-mail-task"></a><span data-ttu-id="c4ca8-125">Mensajes de registro personalizados disponibles en la tarea Enviar correo</span><span class="sxs-lookup"><span data-stu-id="c4ca8-125">Custom Logging Messages Available on the Send Mail Task</span></span>  
 <span data-ttu-id="c4ca8-126">La siguiente tabla contiene las entradas del registro personalizadas para la tarea Enviar correo.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-126">The following table lists the custom log entries for the Send Mail task.</span></span> <span data-ttu-id="c4ca8-127">Para obtener más información, vea [Registro de Integration Services &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) y [Mensajes personalizados para registro](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="c4ca8-127">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="c4ca8-128">Entrada del registro</span><span class="sxs-lookup"><span data-stu-id="c4ca8-128">Log entry</span></span>|<span data-ttu-id="c4ca8-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4ca8-129">Description</span></span>|  
|---------------|-----------------|  
|`SendMailTaskBegin`|<span data-ttu-id="c4ca8-130">Indica que la tarea comenzó a enviar un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-130">Indicates that the task began to send an e-mail message.</span></span>|  
|`SendMailTaskEnd`|<span data-ttu-id="c4ca8-131">Indica que la tarea finalizó el envío de un mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-131">Indicates that the task finished sending an e-mail message.</span></span>|  
|`SendMailTaskInfo`|<span data-ttu-id="c4ca8-132">Proporciona información descriptiva sobre la tarea.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-132">Provides descriptive information about the task.</span></span>|  
  
## <a name="configuring-the-send-mail-task"></a><span data-ttu-id="c4ca8-133">Configurar la tarea Enviar correo</span><span class="sxs-lookup"><span data-stu-id="c4ca8-133">Configuring the Send Mail Task</span></span>  
 <span data-ttu-id="c4ca8-134">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="c4ca8-134">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="c4ca8-135">Para obtener información acerca de las propiedades que puede establecer en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c4ca8-135">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="c4ca8-136">Editor de la tarea Enviar correo &#40;página General&#41;</span><span class="sxs-lookup"><span data-stu-id="c4ca8-136">Send Mail Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="c4ca8-137">Editor de la tarea Enviar correo &#40;página Correo&#41;</span><span class="sxs-lookup"><span data-stu-id="c4ca8-137">Send Mail Task Editor &#40;Mail Page&#41;</span></span>](../send-mail-task-editor-mail-page.md)  
  
-   [<span data-ttu-id="c4ca8-138">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="c4ca8-138">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="c4ca8-139">Para obtener información sobre cómo establecer estas propiedades mediante programación, haga clic en el tema siguiente:</span><span class="sxs-lookup"><span data-stu-id="c4ca8-139">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.SendMailTask.SendMailTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="c4ca8-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c4ca8-140">Related Tasks</span></span>  
 <span data-ttu-id="c4ca8-141">Para obtener información sobre cómo establecer estas propiedades en el Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] , haga clic en [Establecer las propiedades de tareas o contenedores](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="c4ca8-141">For information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="c4ca8-142">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="c4ca8-142">Related Content</span></span>  
  
-   <span data-ttu-id="c4ca8-143">Artículo técnico [How to send email with delivery notification in C#](https://go.microsoft.com/fwlink/?LinkId=237625)(Enviar un mensaje de correo electrónico con una notificación de entrega en C#) en shareourideas.com</span><span class="sxs-lookup"><span data-stu-id="c4ca8-143">Technical article, [How to send email with delivery notification in C#](https://go.microsoft.com/fwlink/?LinkId=237625), on shareourideas.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ca8-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4ca8-144">See Also</span></span>  
 <span data-ttu-id="c4ca8-145">[Tareas de Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="c4ca8-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="c4ca8-146">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="c4ca8-146">Control Flow</span></span>](control-flow.md)  
  
  
