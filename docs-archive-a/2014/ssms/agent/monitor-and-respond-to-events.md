---
title: Supervisar y responder a eventos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- notifications [SQL Server], alert
- events [SQL Server], alerts
- alerts [SQL Server]
- notifications [SQL Server]
- events [SQL Server], automatically responding to
- administrator notifications [SQL Server Agent]
- automatic event responses
- SQL Server Agent alerts
- monitoring [SQL Server], events
- responding to events automatically
ms.assetid: f7fbe155-5b68-4777-bc71-a47637471f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: afdf1beffd6099fce84f03a8ba65f7de9abb8f0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745622"
---
# <a name="monitor-and-respond-to-events"></a><span data-ttu-id="c0685-102">Supervisar y responder a eventos</span><span class="sxs-lookup"><span data-stu-id="c0685-102">Monitor and Respond to Events</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c0685-103">El Agente  puede supervisar y responder automáticamente a *eventos*, por ejemplo, mensajes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], condiciones de rendimiento específicas y eventos de Instrumental de administración de Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="c0685-103">Agent can monitor and automatically respond to *events*, such as messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], specific performance conditions, and Windows Management Instrumentation (WMI) events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0685-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c0685-104">In This Section</span></span>  
 [<span data-ttu-id="c0685-105">Alertas</span><span class="sxs-lookup"><span data-stu-id="c0685-105">Alerts</span></span>](alerts.md)  
 <span data-ttu-id="c0685-106">Contiene información acerca de la nomenclatura de alertas y la selección de los eventos o las condiciones de rendimiento a las que responden las alertas.</span><span class="sxs-lookup"><span data-stu-id="c0685-106">Contains information about naming an alert and selecting the events or performance conditions to which alerts respond.</span></span>  
  
 [<span data-ttu-id="c0685-107">Crear un evento definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="c0685-107">Create a User-Defined Event</span></span>](create-a-user-defined-event.md)  
 <span data-ttu-id="c0685-108">Contiene información acerca de cómo crear eventos distintos a los predefinidos por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0685-108">Contains information about how to create events other than those that are predefined by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="c0685-109">Operadores</span><span class="sxs-lookup"><span data-stu-id="c0685-109">Operators</span></span>](operators.md)  
 <span data-ttu-id="c0685-110">Contiene información acerca de la creación de alias para administradores que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede utilizar para enviar notificaciones cuando los trabajos se realizan correctamente o generan un error.</span><span class="sxs-lookup"><span data-stu-id="c0685-110">Contains information about creating aliases for administrators that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can use to send notifications when jobs fail or succeed.</span></span>  
  
## <a name="about-monitoring-and-responding-to-events"></a><span data-ttu-id="c0685-111">Acerca de cómo supervisar y responder a eventos</span><span class="sxs-lookup"><span data-stu-id="c0685-111">About Monitoring and Responding to Events</span></span>  
 <span data-ttu-id="c0685-112">Las respuestas automatizadas a los eventos se llaman *alertas*.</span><span class="sxs-lookup"><span data-stu-id="c0685-112">Automated responses to events are called *alerts*.</span></span> <span data-ttu-id="c0685-113">Puede definir una alerta sobre uno o varios eventos para especificar cómo desea que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] responda cuando aparezcan.</span><span class="sxs-lookup"><span data-stu-id="c0685-113">You can define an alert on one or more events to specify how you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to respond to their occurrence.</span></span> <span data-ttu-id="c0685-114">Una alerta puede responder a un evento notificando a un administrador o ejecutando un trabajo, o ambos.</span><span class="sxs-lookup"><span data-stu-id="c0685-114">An alert can respond to an event by notifying an administrator or running a job, or both.</span></span> <span data-ttu-id="c0685-115">Una alerta también puede reenviar un evento al registro de la aplicación de Microsoft Windows en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="c0685-115">An alert can also forward an event to the Microsoft Windows application log on a different computer.</span></span> <span data-ttu-id="c0685-116">Por ejemplo, puede especificar que se notifique inmediatamente a un operador si se produce un evento de gravedad 19.</span><span class="sxs-lookup"><span data-stu-id="c0685-116">For example, you can specify that an operator be notified immediately if an event of severity 19 occurs.</span></span> <span data-ttu-id="c0685-117">Si se definen alertas, los administradores de bases de datos pueden supervisar y administrar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]de forma más eficaz.</span><span class="sxs-lookup"><span data-stu-id="c0685-117">By defining alerts, database administrators can more effectively monitor and manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c0685-118">El Agente solo responde a los eventos para los que se ha definido una alerta.</span><span class="sxs-lookup"><span data-stu-id="c0685-118">Agent only responds to events for which an alert is defined.</span></span> <span data-ttu-id="c0685-119">El método que utiliza el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para supervisar eventos depende del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="c0685-119">The method that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent uses to monitor events depends on the type of event.</span></span>  
  
 <span data-ttu-id="c0685-120">Cuando se define una alerta del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para un contador de rendimiento, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supervisa directamente el contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c0685-120">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert is defined for a performance counter, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent directly monitors the performance counter.</span></span> <span data-ttu-id="c0685-121">Para un evento WMI, el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registra una consulta de evento para el evento WMI.</span><span class="sxs-lookup"><span data-stu-id="c0685-121">For a WMI event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registers an event query for the WMI event.</span></span>  
  
 <span data-ttu-id="c0685-122">Para responder a mensajes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supervisa el registro de la aplicación Windows.</span><span class="sxs-lookup"><span data-stu-id="c0685-122">To respond to messages from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent monitors the Windows application log.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c0685-123">El Agente solo puede responder a mensajes que aparecen en este registro.</span><span class="sxs-lookup"><span data-stu-id="c0685-123">Agent can only respond to messages that appear in this log.</span></span> <span data-ttu-id="c0685-124">De manera predeterminada, SQL Server registra los siguientes mensajes en el registro de la aplicación de Windows:</span><span class="sxs-lookup"><span data-stu-id="c0685-124">By default, SQL Server logs the following messages in the Windows application log:</span></span>  
  
-   <span data-ttu-id="c0685-125">Errores sysmessages de gravedad 19 o superior.</span><span class="sxs-lookup"><span data-stu-id="c0685-125">Severity 19 or higher sysmessages errors.</span></span>  
  
     <span data-ttu-id="c0685-126">Si también desea registrar errores sysmessages específicos que tengan una gravedad inferior a 19, utilice el procedimiento almacenado sp_altermessage para designar tales errores como siempre registrados.</span><span class="sxs-lookup"><span data-stu-id="c0685-126">If you also want to log specific sysmessages errors that have a severity lower than 19, use the sp_altermessage stored procedure to designate such errors as "always logged".</span></span>  
  
-   <span data-ttu-id="c0685-127">Instrucciones RAISERROR invocadas mediante la sintaxis WITH LOG.</span><span class="sxs-lookup"><span data-stu-id="c0685-127">Any RAISERROR statement invoked by using the WITH LOG syntax.</span></span>  
  
     <span data-ttu-id="c0685-128">Utilizar RAISERROR WITH LOG es la manera que se recomienda para escribir en el registro de la aplicación Windows desde una instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0685-128">Using RAISERROR WITH LOG is the recommended way to write to the Windows application log from an instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="c0685-129">Cualquier evento de aplicación registrado mediante xp_logevent.</span><span class="sxs-lookup"><span data-stu-id="c0685-129">Any application event that is logged by using xp_logevent.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c0685-130">Registrar eventos de aplicación consume espacio de registro y puede provocar que el registro de la aplicación de Windows supere el tamaño máximo.</span><span class="sxs-lookup"><span data-stu-id="c0685-130">Logging application events consumes log space and can cause the Windows application log to exceed its maximum size.</span></span> <span data-ttu-id="c0685-131">Asegúrese de que el tamaño máximo del registro de la aplicación Windows es suficiente como para evitar la pérdida de información de eventos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0685-131">Make sure that the maximum Windows application log size is large enough to avoid loss of SQL Server event information.</span></span>  
  
 <span data-ttu-id="c0685-132">Cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registra un mensaje, el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] compara el mensaje con las alertas definidas por el administrador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0685-132">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logs a message, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service compares the message against the alerts defined by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="c0685-133">Independientemente del origen del evento, el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] responde al evento realizando las tareas especificadas en la alerta del evento.</span><span class="sxs-lookup"><span data-stu-id="c0685-133">Regardless of the source of the event, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service responds to the event by performing the tasks specified in the alert for the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0685-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c0685-134">See Also</span></span>  
 [<span data-ttu-id="c0685-135">sp_altermessage &#40;&#41;de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c0685-135">sp_altermessage &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-altermessage-transact-sql)  
  
  
