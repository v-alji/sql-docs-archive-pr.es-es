---
title: Editor del administrador de conexiones MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msmqconnectionmanager.f1
helpviewer_keywords:
- MSMQ Connection Manager Editor
ms.assetid: ef842cb4-82da-4550-85fe-9bedbc1e77c7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41d4231ce121d596c8d818485eccf5ddf6127470
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663574"
---
# <a name="msmq-connection-manager-editor"></a><span data-ttu-id="b703e-102">administrador de conexiones MSMQ, editor del</span><span class="sxs-lookup"><span data-stu-id="b703e-102">MSMQ Connection Manager Editor</span></span>
  <span data-ttu-id="b703e-103">Use el cuadro de diálogo **Administrador de conexiones MSMQ** para especificar la ruta de acceso a una cola de mensajes de Message Queuing (que también recibe el nombre de MSMQ).</span><span class="sxs-lookup"><span data-stu-id="b703e-103">Use the **MSMQ Connection Manager** dialog box to specify the path to a Message Queuing (also known as MSMQ) message queue.</span></span>  
  
 <span data-ttu-id="b703e-104">Para obtener más información acerca del administrador de conexiones MSMQ, vea [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="b703e-104">To learn more about the MSMQ connection manager, see [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b703e-105">El administrador de conexiones MSMQ admite colas públicas y privadas locales, además de colas públicas remotas.</span><span class="sxs-lookup"><span data-stu-id="b703e-105">The MSMQ connection manager supports local public and private queues and remote public queues.</span></span> <span data-ttu-id="b703e-106">No admite colas privadas remotas.</span><span class="sxs-lookup"><span data-stu-id="b703e-106">It does not support remote private queues.</span></span> <span data-ttu-id="b703e-107">Para obtener una solución que utilice la tarea Script, vea [Enviar a una cola de mensajes privada remota con la tarea Script](control-flow/script-task.md).</span><span class="sxs-lookup"><span data-stu-id="b703e-107">For a workaround that uses the Script Task, see [Sending to a Remote Private Message Queue with the Script Task](control-flow/script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b703e-108">Opciones</span><span class="sxs-lookup"><span data-stu-id="b703e-108">Options</span></span>  
 <span data-ttu-id="b703e-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="b703e-109">**Name**</span></span>  
 <span data-ttu-id="b703e-110">Proporcione un nombre único para el administrador de conexiones MSMQ en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b703e-110">Provide a unique name for the MSMQ connection manager in the workflow.</span></span> <span data-ttu-id="b703e-111">El nombre que indique se mostrará en el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b703e-111">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="b703e-112">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b703e-112">**Description**</span></span>  
 <span data-ttu-id="b703e-113">Describa el administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="b703e-113">Describe the connection manager.</span></span> <span data-ttu-id="b703e-114">Como método recomendado, describa el administrador de conexiones desde el punto de vista de su propósito, para que los paquetes estén autodocumentados y sean más fáciles de mantener.</span><span class="sxs-lookup"><span data-stu-id="b703e-114">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="b703e-115">**Path**</span><span class="sxs-lookup"><span data-stu-id="b703e-115">**Path**</span></span>  
 <span data-ttu-id="b703e-116">Escriba la ruta de acceso completa de la cola de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b703e-116">Type the complete path of the message queue.</span></span> <span data-ttu-id="b703e-117">El formato de la ruta de acceso depende del tipo de cola.</span><span class="sxs-lookup"><span data-stu-id="b703e-117">The format of the path depends on the type of queue.</span></span>  
  
|<span data-ttu-id="b703e-118">Tipo de cola</span><span class="sxs-lookup"><span data-stu-id="b703e-118">Queue type</span></span>|<span data-ttu-id="b703e-119">Ruta de acceso de ejemplo</span><span class="sxs-lookup"><span data-stu-id="b703e-119">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="b703e-120">Público</span><span class="sxs-lookup"><span data-stu-id="b703e-120">Public</span></span>|<span data-ttu-id="b703e-121">\<computer name>\\<queue name\></span><span class="sxs-lookup"><span data-stu-id="b703e-121">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="b703e-122">Privada</span><span class="sxs-lookup"><span data-stu-id="b703e-122">Private</span></span>|<span data-ttu-id="b703e-123">\<computer name>\Private$\\<queue name\></span><span class="sxs-lookup"><span data-stu-id="b703e-123">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="b703e-124">Puede utilizar "." para representar el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b703e-124">You can use "." to represent the local computer.</span></span>  
  
 <span data-ttu-id="b703e-125">**Test**</span><span class="sxs-lookup"><span data-stu-id="b703e-125">**Test**</span></span>  
 <span data-ttu-id="b703e-126">Después de configurar el Administrador de conexiones MSMQ, confirme que la conexión es viable haciendo clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="b703e-126">After configuring the MSMQ connection manager, confirm that the connection is viable by clicking **Test**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b703e-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b703e-127">See Also</span></span>  
 [<span data-ttu-id="b703e-128">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="b703e-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
