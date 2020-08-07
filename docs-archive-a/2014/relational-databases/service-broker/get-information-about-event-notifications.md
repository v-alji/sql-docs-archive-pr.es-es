---
title: Obtener información sobre notificaciones de eventos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- event notifications [SQL Server], metadata
- status information [SQL Server], event notifications
- metadata [SQL Server], event notifications
ms.assetid: 8bc10867-66d6-4f57-ac32-a6c29f3327cd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8d8271b6279910321058d01c7b2f96b1df62bd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746199"
---
# <a name="get-information-about-event-notifications"></a><span data-ttu-id="3dd87-102">Obtener información sobre notificaciones de eventos</span><span class="sxs-lookup"><span data-stu-id="3dd87-102">Get Information About Event Notifications</span></span>
  <span data-ttu-id="3dd87-103">A continuación se indican las vistas de catálogo que están disponibles para consultar metadatos acerca de las notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="3dd87-103">The following catalog views are available to query metadata about event notifications.</span></span>  
  
 <span data-ttu-id="3dd87-104">**Para obtener información acerca de notificaciones de eventos que no tengan lugar en servidores**</span><span class="sxs-lookup"><span data-stu-id="3dd87-104">**To get information about nonserver-level event notifications**</span></span>  
  
-   [<span data-ttu-id="3dd87-105">sys.event_notifications &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dd87-105">sys.event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="3dd87-106">Para ver los metadatos de cualquier notificación de eventos de **sys.event_notifications** creada en bases de datos, como mínimo debe tener el permiso CONTROL, ALTER, TAKE OWNERSHIP o VIEW DEFINITION en la base de datos, ser el propietario de la notificación de eventos o tener el permiso ALTER ANY DATABASE EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="3dd87-106">To view metadata about any event notification in **sys.event_notifications** created at the database level, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the database, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span> <span data-ttu-id="3dd87-107">Para las notificaciones de eventos creadas en una cola específica, como mínimo debe tener el permiso CONTROL, ALTER, TAKE OWNERSHIP o VIEW DEFINITION en el objeto, ser el propietario de la notificación de eventos o tener el permiso ALTER ANY DATABASE EVENT NOTIFICATION.</span><span class="sxs-lookup"><span data-stu-id="3dd87-107">For event notifications created on a specific queue, at the minimum you must have the following: CONTROL, ALTER, TAKE OWNERSHIP, or VIEW DEFINITION permission on the object, be the owner of the event notification, or have ALTER ANY DATABASE EVENT NOTIFICATION permission.</span></span>  
  
 <span data-ttu-id="3dd87-108">**Para obtener información acerca de notificaciones de eventos que tienen lugar en servidores**</span><span class="sxs-lookup"><span data-stu-id="3dd87-108">**To get information about server-level event notifications**</span></span>  
  
-   [<span data-ttu-id="3dd87-109">sys.server_event_notifications &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dd87-109">sys.server_event_notifications &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-event-notifications-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="3dd87-110">Como mínimo requiere el permiso CONTROL o VIEW ANY DEFINITION en el servidor, ser el inicio de sesión o propietario de la notificación de eventos, o bien tener el permiso ALTER ANY EVENT NOTIFICATION para ver los metadatos de cualquier notificación de eventos de **sys.server_event_notifications**.</span><span class="sxs-lookup"><span data-stu-id="3dd87-110">At the minimum, you must have the following: CONTROL or VIEW ANY DEFINITION permission on the server, be the logon or owner of the event notification, or have ALTER ANY EVENT NOTIFICATION permission to view metadata about any event notification in **sys.server_event_notifications**.</span></span>  
  
 <span data-ttu-id="3dd87-111">**Para obtener información acerca de todos los eventos que pueden desencadenar notificaciones de eventos**</span><span class="sxs-lookup"><span data-stu-id="3dd87-111">**To get information about all events that can fire event notifications**</span></span>  
  
-   [<span data-ttu-id="3dd87-112">sys.event_notification_event_types &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3dd87-112">sys.event_notification_event_types &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-event-notification-event-types-transact-sql)  
  
> [!NOTE]  
>  <span data-ttu-id="3dd87-113">Esta vista de catálogo no devuelve grupos de eventos.</span><span class="sxs-lookup"><span data-stu-id="3dd87-113">This catalog view does not return event groups.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dd87-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3dd87-114">See Also</span></span>  
 [<span data-ttu-id="3dd87-115">Notificaciones de eventos</span><span class="sxs-lookup"><span data-stu-id="3dd87-115">Event Notifications</span></span>](event-notifications.md)  
  
  
