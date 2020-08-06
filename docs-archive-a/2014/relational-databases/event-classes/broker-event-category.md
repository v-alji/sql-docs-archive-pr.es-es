---
title: Categoría de eventos Broker | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- SQL Server event classes, Broker event category
- Broker event category [SQL Server]
- event classes [SQL Server], Broker event category
ms.assetid: 470dc93c-0dda-4d89-829b-937738d59b31
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23f839416e3404bfdf0a7e61d1b1e8dbbb90ec95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663532"
---
# <a name="broker-event-category"></a><span data-ttu-id="40d0e-102">Broker (categoría de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-102">Broker Event Category</span></span>
  <span data-ttu-id="40d0e-103">La categoría de eventos **Broker** contiene eventos generales de Service Broker.</span><span class="sxs-lookup"><span data-stu-id="40d0e-103">The **Broker** event category contains general Service Broker events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="40d0e-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="40d0e-104">In This Section</span></span>  
  
|<span data-ttu-id="40d0e-105">Tema</span><span class="sxs-lookup"><span data-stu-id="40d0e-105">Topic</span></span>|<span data-ttu-id="40d0e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="40d0e-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="40d0e-107">Broker:Activation (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-107">Broker:Activation Event Class</span></span>](broker-activation-event-class.md)|<span data-ttu-id="40d0e-108">Evento que se genera cuando un monitor de cola inicia un procedimiento almacenado de activación.</span><span class="sxs-lookup"><span data-stu-id="40d0e-108">An event generated when a queue monitor starts an activation stored procedure.</span></span>|  
|[<span data-ttu-id="40d0e-109">Broker:Connection (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-109">Broker:Connection Event Class</span></span>](broker-connection-event-class.md)|<span data-ttu-id="40d0e-110">Evento generado para informar del estado de una conexión de transporte administrada por Service Broker.</span><span class="sxs-lookup"><span data-stu-id="40d0e-110">An event generated to report the status of a transport connection managed by Service Broker.</span></span>|  
|[<span data-ttu-id="40d0e-111">Broker:Conversation (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-111">Broker:Conversation Event Class</span></span>](broker-conversation-event-class.md)|<span data-ttu-id="40d0e-112">Evento generado para informar sobre el progreso de una conversación.</span><span class="sxs-lookup"><span data-stu-id="40d0e-112">An event generated to report the progress of a conversation.</span></span>|  
|[<span data-ttu-id="40d0e-113">Broker:Conversation Group (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-113">Broker:Conversation Group Event Class</span></span>](broker-conversation-group-event-class.md)|<span data-ttu-id="40d0e-114">Evento generado cuando la base de datos crea o quita un grupo de conversación.</span><span class="sxs-lookup"><span data-stu-id="40d0e-114">An event generated when the database creates or drops a conversation group.</span></span>|  
|[<span data-ttu-id="40d0e-115">Broker:Corrupted Message (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-115">Broker:Corrupted Message Event Class</span></span>](broker-corrupted-message-event-class.md)|<span data-ttu-id="40d0e-116">Evento que se genera para informar de que la base de datos ha recibido un mensaje dañado.</span><span class="sxs-lookup"><span data-stu-id="40d0e-116">An event generated to report that the database has received a corrupt message.</span></span>|  
|[<span data-ttu-id="40d0e-117">Broker:Forwarded Message Dropped (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-117">Broker:Forwarded Message Dropped Event Class</span></span>](broker-forwarded-message-dropped-event-class.md)|<span data-ttu-id="40d0e-118">Evento que se genera cuando SQL Server quita un mensaje de Service Broker que tenía que haberse reenviado.</span><span class="sxs-lookup"><span data-stu-id="40d0e-118">An event generated when SQL Server drops a Service Broker message that was to have been forwarded.</span></span>|  
|[<span data-ttu-id="40d0e-119">Broker:Forwarded Message Sent (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-119">Broker:Forwarded Message Sent Event Class</span></span>](broker-forwarded-message-sent-event-class.md)|<span data-ttu-id="40d0e-120">Evento que se genera cuando SQL Server reenvía un mensaje de Service Broker.</span><span class="sxs-lookup"><span data-stu-id="40d0e-120">An event generated when SQL Server forwards a Service Broker message.</span></span>|  
|[<span data-ttu-id="40d0e-121">Broker:Message Classify (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-121">Broker:Message Classify Event Class</span></span>](broker-message-classify-event-class.md)|<span data-ttu-id="40d0e-122">Evento que se genera cuando Service Broker determina el enrutamiento de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="40d0e-122">An event generated when Service Broker determines the routing for a message.</span></span>|  
|[<span data-ttu-id="40d0e-123">Broker:Message Drop (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-123">Broker:Message Drop Event Class</span></span>](broker-message-drop-event-class.md)|<span data-ttu-id="40d0e-124">Evento que se genera cuando Service Broker no puede retener un mensaje recibido que debería haberse entregado a un servicio de esta instancia.</span><span class="sxs-lookup"><span data-stu-id="40d0e-124">An event generated when Service Broker is unable to retain a received message that should have been delivered to a service in this instance</span></span>|  
|[<span data-ttu-id="40d0e-125">Broker:Remote Message Ack (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-125">Broker:Remote Message Ack Event Class</span></span>](broker-remote-message-ack-event-class.md)|<span data-ttu-id="40d0e-126">Evento que se genera cuando Service Broker envía o recibe un reconocimiento de mensaje.</span><span class="sxs-lookup"><span data-stu-id="40d0e-126">An event generated when Service Broker sends or receives a message acknowledgement.</span></span>|  
  
 <span data-ttu-id="40d0e-127">También se proporcionan dos eventos de auditoría de seguridad para Service Broker.</span><span class="sxs-lookup"><span data-stu-id="40d0e-127">Two security audit events are also provided for Service Broker.</span></span> <span data-ttu-id="40d0e-128">Para obtener más información sobre estos eventos, vea [Clase de eventos Audit Broker Login](audit-broker-login-event-class.md) y [Audit Broker Conversation (clase de eventos)](audit-broker-conversation-event-class.md).</span><span class="sxs-lookup"><span data-stu-id="40d0e-128">For more information on those events, see [Audit Broker Login Event Class](audit-broker-login-event-class.md) and [Audit Broker Conversation Event Class](audit-broker-conversation-event-class.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40d0e-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40d0e-129">See Also</span></span>  
 [<span data-ttu-id="40d0e-130">Auditoría de seguridad (categoría de eventos)</span><span class="sxs-lookup"><span data-stu-id="40d0e-130">Security Audit Event Category</span></span>](https://docs.microsoft.com/bi-reference/trace-events/security-audit-event-category)  
  
  
