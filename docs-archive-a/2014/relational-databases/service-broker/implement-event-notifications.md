---
title: Implementar notificaciones de eventos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], target service
- target service [SQL Server]
- event notifications [SQL Server], creating
ms.assetid: 29ac8f68-a28a-4a77-b67b-a8663001308c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6a89c66ca5c3b420fff14c087bd604b16c641369
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673601"
---
# <a name="implement-event-notifications"></a><span data-ttu-id="3e7ae-102">Implementar notificaciones de eventos</span><span class="sxs-lookup"><span data-stu-id="3e7ae-102">Implement Event Notifications</span></span>
  <span data-ttu-id="3e7ae-103">Para implementar una notificación de eventos, debe crear primero un servicio de destino para que reciba las notificaciones de eventos y, a continuación, crear la notificación de eventos.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-103">To implement an event notification, you must first create a target service to receive event notifications, and then create the event notification.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="3e7ae-104">se debe configurar para las notificaciones de eventos que envíen mensajes a un Service Broker en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-104">dialog security should be configured for event notifications that send messages to a service broker on a remote server.</span></span> <span data-ttu-id="3e7ae-105">La seguridad del diálogo debe configurarse manualmente según el modelo de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-105">Dialog security must be configured manually according to the full security model.</span></span>  
  
## <a name="creating-the-target-service"></a><span data-ttu-id="3e7ae-106">Crear el servicio de destino</span><span class="sxs-lookup"><span data-stu-id="3e7ae-106">Creating the Target Service</span></span>  
 <span data-ttu-id="3e7ae-107">No es necesario que cree un servicio de inicio de [!INCLUDE[ssSB](../../includes/sssb-md.md)]debido a que [!INCLUDE[ssSB](../../includes/sssb-md.md)] incluye el siguiente tipo de mensaje y contrato para notificaciones de eventos:</span><span class="sxs-lookup"><span data-stu-id="3e7ae-107">You do not have to create a [!INCLUDE[ssSB](../../includes/sssb-md.md)]-initiating service because [!INCLUDE[ssSB](../../includes/sssb-md.md)] includes the following specific message type and contract for event notifications:</span></span>  
  
```  
https://schemas.microsoft.com/SQL/Notifications/PostEventNotification  
```  
  
 <span data-ttu-id="3e7ae-108">El servicio de destino que recibe notificaciones de eventos debe respetar este contrato preexistente.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-108">The target service that receives event notifications must honor this preexisting contract.</span></span>  
  
 <span data-ttu-id="3e7ae-109">**Para crear un servicio de destino**:</span><span class="sxs-lookup"><span data-stu-id="3e7ae-109">**To create a target service**:</span></span>  
  
1.  <span data-ttu-id="3e7ae-110">Cree una cola para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-110">Create a queue to receive messages.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3e7ae-111">La cola recibe el siguiente tipo de mensaje: `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-111">The queue receives the following message type: `https://schemas.microsoft.com/SQL/Notifications/QueryNotification`.</span></span>  
  
2.  <span data-ttu-id="3e7ae-112">Cree un servicio en la cola que hace referencia al contrato de notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-112">Create a service on the queue that references the event notifications contract.</span></span>  
  
3.  <span data-ttu-id="3e7ae-113">Cree una ruta en el servicio para definir la dirección a la que [!INCLUDE[ssSB](../../includes/sssb-md.md)] envía los mensajes de ese servicio.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-113">Create a route on the service to define the address to which [!INCLUDE[ssSB](../../includes/sssb-md.md)] sends messages for the service.</span></span> <span data-ttu-id="3e7ae-114">Para las notificaciones de eventos que tengan como destino un servicio en la misma base de datos, especifique `ADDRESS = 'LOCAL'`.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-114">For event notifications that target a service in the same database, specify `ADDRESS = 'LOCAL'`.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssSB](../../includes/sssb-md.md)] <span data-ttu-id="3e7ae-115">determina el servicio que recibe los mensajes de notificación.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-115">routing determines the service that receives the notification messages.</span></span> <span data-ttu-id="3e7ae-116">Si la notificación de eventos tiene como destino un servicio en un servidor remoto, tanto el servidor de origen como el servidor de destino deben tener rutas definidas en este servidor para garantizar que se produce comunicación en los dos sentidos.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-116">If the event notification targets a service on a remote server, both the source server and the target server must have routes defined on them to make sure that two-way communication occurs.</span></span>  
  
 <span data-ttu-id="3e7ae-117">En el ejemplo siguiente se crea una cola, un servicio en la cola y una ruta en el servicio para procesar los mensajes del contrato de notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-117">The following example creates a queue, a service on the queue, and a route on the service to handle messages from the event notification contract.</span></span>  
  
```  
CREATE QUEUE NotifyQueue ;  
GO  
CREATE SERVICE NotifyService  
ON QUEUE NotifyQueue  
(  
[https://schemas.microsoft.com/SQL/Notifications/PostEventNotification]  
);  
GO  
CREATE ROUTE NotifyRoute  
WITH SERVICE_NAME = 'NotifyService',  
ADDRESS = 'LOCAL';  
GO  
```  
  
## <a name="creating-the-event-notification"></a><span data-ttu-id="3e7ae-118">Crear la notificación de eventos</span><span class="sxs-lookup"><span data-stu-id="3e7ae-118">Creating the Event Notification</span></span>  
 <span data-ttu-id="3e7ae-119">Las notificaciones de eventos se crean mediante la instrucción CREATE EVENT NOTIFICATION de [!INCLUDE[tsql](../../includes/tsql-md.md)] y se quitan con DROP EVENT NOTIFICATION STATEMENT.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-119">Event notifications are created by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE EVENT NOTIFICATION statement, and are dropped by using the DROP EVENT NOTIFICATION STATEMENT.</span></span> <span data-ttu-id="3e7ae-120">Para modificar una notificación de eventos, debe quitarla y volver a crearla.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-120">To modify an event notification, you must drop and re-create the event notification.</span></span>  
  
 <span data-ttu-id="3e7ae-121">En el ejemplo siguiente se crea la notificación de eventos `CreateDatabaseNotification`.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-121">The following example creates the event notification `CreateDatabaseNotification`.</span></span> <span data-ttu-id="3e7ae-122">Esta notificación envía un mensaje acerca de cualquier evento `CREATE_DATABASE` que se produzca en el servidor en el servicio `NotifyService` que se creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-122">This notification sends a message about any `CREATE_DATABASE` event that occurs on the server to the `NotifyService` service that was previously created.</span></span>  
  
```  
CREATE EVENT NOTIFICATION CreateDatabaseNotification  
ON SERVER  
FOR CREATE_DATABASE  
TO SERVICE 'NotifyService', '8140a771-3c4b-4479-8ac0-81008ab17984' ;  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="3e7ae-123">Las notificaciones de eventos reconocen los eventos CREATE_SCHEMA y las definiciones <schema_element> de las instrucciones CREATE SCHEMA como eventos independientes.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-123">Event notifications recognize CREATE_SCHEMA events and the <schema_element> definitions of CREATE SCHEMA statements as separate events.</span></span> <span data-ttu-id="3e7ae-124">Por ejemplo, una notificación de eventos se crea en los dos eventos CREATE_SCHEMA y CREATE_TABLE, y se ejecuta el siguiente lote.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-124">For example, an event notification is created on both the CREATE_SCHEMA and CREATE_TABLE events, and you run the following batch.</span></span>  
>   
>  `CREATE SCHEMA s`  
>   
>  `CREATE TABLE t1 (col1 int)`  
>   
>  <span data-ttu-id="3e7ae-125">En este caso, el evento se notifica dos veces: una vez cuando se produce el evento CREATE_SCHEMA y otra vez cuando ocurre el evento CREATE_TABLE.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-125">In this case, the event notification is raised two times: Onne time when the CREATE_SCHEMA event occurs, and again when the CREATE_TABLE event occurs.</span></span> <span data-ttu-id="3e7ae-126">Es recomendable que no cree notificaciones de eventos en los eventos CREATE_SCHEMA ni en los textos <schema_element> de las definiciones CREATE SCHEMA correspondientes, y que no genere lógica en la aplicación para evitar capturar datos de eventos no deseados.</span><span class="sxs-lookup"><span data-stu-id="3e7ae-126">We recommend that you either avoid creating event notifications on both the CREATE_SCHEMA events and the <schema_element> texts of any corresponding CREATE SCHEMA definitions, or build logic into your application to avoid capturing unwanted event data.</span></span>  
  
 <span data-ttu-id="3e7ae-127">**Para crear una notificación de eventos**</span><span class="sxs-lookup"><span data-stu-id="3e7ae-127">**To create an event notification**</span></span>  
  
-   [<span data-ttu-id="3e7ae-128">CREATE EVENT NOTIFICATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e7ae-128">CREATE EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-notification-transact-sql)  
  
 <span data-ttu-id="3e7ae-129">**Para quitar una notificación de eventos**</span><span class="sxs-lookup"><span data-stu-id="3e7ae-129">**To drop an event notification**</span></span>  
  
-   [<span data-ttu-id="3e7ae-130">DROP EVENT NOTIFICATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e7ae-130">DROP EVENT NOTIFICATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-event-notification-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="3e7ae-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e7ae-131">See Also</span></span>  
 <span data-ttu-id="3e7ae-132">[Obtener información sobre notificaciones de eventos](event-notifications.md) </span><span class="sxs-lookup"><span data-stu-id="3e7ae-132">[Get Information About Event Notifications](event-notifications.md) </span></span>  
 [<span data-ttu-id="3e7ae-133">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e7ae-133">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
