---
title: Editor de la tarea cola de mensajes (página general) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.general.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 09368b18-37a5-4321-a173-7cfe5d42d2a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dcec75f3a4dd85efb7c97226c592d6b1e1bb26ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677772"
---
# <a name="message-queue-task-editor-general-page"></a><span data-ttu-id="ea1cc-102">Editor de la tarea Cola de mensajes (página General)</span><span class="sxs-lookup"><span data-stu-id="ea1cc-102">Message Queue Task Editor (General Page)</span></span>
  <span data-ttu-id="ea1cc-103">Utilice la página **General** del cuadro de diálogo **Editor de la tarea Cola de mensajes** para asignar un nombre y describir la tarea Cola de mensajes, especificar el formato del mensaje e indicar si la tarea envía o recibe o mensajes.</span><span class="sxs-lookup"><span data-stu-id="ea1cc-103">Use the **General page** of the **Message Queue Task Editor** dialog box to name and describe the Message Queue task, to specify the message format, and to indicate whether the task sends or receives messages.</span></span>  
  
 <span data-ttu-id="ea1cc-104">Para obtener información acerca de esta tarea, vea [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="ea1cc-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ea1cc-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="ea1cc-105">Options</span></span>  
 <span data-ttu-id="ea1cc-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="ea1cc-106">**Name**</span></span>  
 <span data-ttu-id="ea1cc-107">Proporcione un nombre único para la tarea Cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ea1cc-107">Provide a unique name for the Message Queue task.</span></span> <span data-ttu-id="ea1cc-108">Este nombre se utiliza como etiqueta en el icono de tarea.</span><span class="sxs-lookup"><span data-stu-id="ea1cc-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea1cc-109">Los nombres de tarea deben ser únicos en un paquete.</span><span class="sxs-lookup"><span data-stu-id="ea1cc-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="ea1cc-110">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ea1cc-110">**Description**</span></span>  
 <span data-ttu-id="ea1cc-111">Escriba una descripción de la tarea Cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ea1cc-111">Type a description of the Message Queue task.</span></span>  
  
 <span data-ttu-id="ea1cc-112">**Use2000Format**</span><span class="sxs-lookup"><span data-stu-id="ea1cc-112">**Use2000Format**</span></span>  
 <span data-ttu-id="ea1cc-113">Indica si se va a utilizar el formato 2000 de Message Queue Server (que también recibe el nombre de MSMQ).</span><span class="sxs-lookup"><span data-stu-id="ea1cc-113">Indicate whether to use the 2000 format of Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="ea1cc-114">El valor predeterminado es `False`.</span><span class="sxs-lookup"><span data-stu-id="ea1cc-114">The default is `False`.</span></span>  
  
 <span data-ttu-id="ea1cc-115">**MSMQConnection**</span><span class="sxs-lookup"><span data-stu-id="ea1cc-115">**MSMQConnection**</span></span>  
 <span data-ttu-id="ea1cc-116">Seleccione un administrador de conexiones MSMQ existente o haga clic en \<**New connection...**> para crear uno.</span><span class="sxs-lookup"><span data-stu-id="ea1cc-116">Select an existing MSMQ connection manager or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="ea1cc-117">**Temas relacionados**: [Administrador de conexiones MSMQ](connection-manager/msmq-connection-manager.md), [Editor del administrador de conexiones MSMQ](../../2014/integration-services/msmq-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="ea1cc-117">**Related Topics**: [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md), [MSMQ Connection Manager Editor](../../2014/integration-services/msmq-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="ea1cc-118">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="ea1cc-118">**Message**</span></span>  
 <span data-ttu-id="ea1cc-119">Especifique si la tarea Cola de mensajes envía o recibe mensajes.</span><span class="sxs-lookup"><span data-stu-id="ea1cc-119">Specify whether the Message Queue task sends or receive messages.</span></span> <span data-ttu-id="ea1cc-120">Si selecciona **Enviar mensaje**, la página Enviar se agrega a la lista del panel izquierdo del cuadro de diálogo. Si selecciona **Recibir mensaje**, se agrega la página Recibir.</span><span class="sxs-lookup"><span data-stu-id="ea1cc-120">If you select **Send message**, the Send page is listed in the left pane of the dialog box; if you select **Receive message**, the Receive page is listed.</span></span> <span data-ttu-id="ea1cc-121">De forma predeterminada, este valor está establecido en **Enviar mensaje**.</span><span class="sxs-lookup"><span data-stu-id="ea1cc-121">By default, this value is set to **Send message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea1cc-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea1cc-122">See Also</span></span>  
 <span data-ttu-id="ea1cc-123">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ea1cc-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="ea1cc-124">[Editor de la tarea cola de mensajes &#40;página de recepción&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="ea1cc-124">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 <span data-ttu-id="ea1cc-125">[Editor de la tarea cola de mensajes &#40;página envío&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="ea1cc-125">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 [<span data-ttu-id="ea1cc-126">Página Expresiones</span><span class="sxs-lookup"><span data-stu-id="ea1cc-126">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
