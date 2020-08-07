---
title: Administrar eventos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- event-triggered jobs [SQL Server]
- forwarding events [SQL Server]
- alerts [SQL Server], forwarded events
- alerts [SQL Server], management servers
- SQL Server Agent alerts, management servers
ms.assetid: 8f4ee7f5-80df-49fd-b2b8-d020e04b6e1b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7ca6d56440b06d285cbb90f8d92325d59a452c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743907"
---
# <a name="manage-events"></a><span data-ttu-id="e6062-102">Administrar eventos</span><span class="sxs-lookup"><span data-stu-id="e6062-102">Manage Events</span></span>
  <span data-ttu-id="e6062-103">Puede reenviar todos los mensajes de eventos que tengan o superen un nivel de gravedad de error específico a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6062-103">You can forward to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all event messages that meet or exceed a specific error severity level.</span></span> <span data-ttu-id="e6062-104">Esto se denomina *reenvío de eventos*.</span><span class="sxs-lookup"><span data-stu-id="e6062-104">This is called *event forwarding*.</span></span> <span data-ttu-id="e6062-105">El servidor de reenvío es un servidor dedicado que también puede ser un servidor maestro.</span><span class="sxs-lookup"><span data-stu-id="e6062-105">The forwarding server is a dedicated server that can also be a master server.</span></span> <span data-ttu-id="e6062-106">Puede utilizar el reenvío de eventos para centralizar la administración de alertas para un grupo de servidores, con lo que se reduce la carga de trabajo de los servidores con un alto grado de utilización.</span><span class="sxs-lookup"><span data-stu-id="e6062-106">You can use event forwarding to centralize alert management for a group of servers, thereby reducing the workload on heavily used servers.</span></span>  
  
 <span data-ttu-id="e6062-107">Un servidor que recibe eventos para un grupo de servidores distintos se denomina *servidor de administración de alertas*.</span><span class="sxs-lookup"><span data-stu-id="e6062-107">When one server receives events for a group of other servers, the server that receives events is called an *alerts management server*.</span></span> <span data-ttu-id="e6062-108">En un entorno multiservidor, el servidor maestro se designa como servidor de administración de alertas.</span><span class="sxs-lookup"><span data-stu-id="e6062-108">In a multiserver environment, you designate the master server as the alerts management server.</span></span>  
  
## <a name="advantages-of-using-an-alerts-management-server"></a><span data-ttu-id="e6062-109">Ventajas del uso de un servidor de administración de alertas</span><span class="sxs-lookup"><span data-stu-id="e6062-109">Advantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="e6062-110">Entre las ventajas de configurar un servidor de administración de alertas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6062-110">The advantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="e6062-111">**Centralización**.</span><span class="sxs-lookup"><span data-stu-id="e6062-111">**Centralization**.</span></span> <span data-ttu-id="e6062-112">Es posible un control centralizado y una vista consolidada de los eventos de varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde un único servidor.</span><span class="sxs-lookup"><span data-stu-id="e6062-112">Centralized control and a consolidated view of the events of several instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are possible from a single server.</span></span>  
  
-   <span data-ttu-id="e6062-113">**Escalabilidad**.</span><span class="sxs-lookup"><span data-stu-id="e6062-113">**Scalability**.</span></span> <span data-ttu-id="e6062-114">Se pueden administrar muchos servidores físicos como un servidor lógico.</span><span class="sxs-lookup"><span data-stu-id="e6062-114">Many physical servers can be administered as one logical server.</span></span> <span data-ttu-id="e6062-115">Puede agregar o quitar servidores en este grupo de servidores físicos, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e6062-115">You can add or remove servers to this physical server group as needed.</span></span>  
  
-   <span data-ttu-id="e6062-116">**Eficacia**.</span><span class="sxs-lookup"><span data-stu-id="e6062-116">**Efficiency**.</span></span> <span data-ttu-id="e6062-117">El tiempo de configuración disminuye gracias a que solo debe definir una vez las alertas y los operadores.</span><span class="sxs-lookup"><span data-stu-id="e6062-117">Configuration time is reduced, because you need to define alerts and operators only once.</span></span>  
  
## <a name="disadvantages-of-using-an-alerts-management-server"></a><span data-ttu-id="e6062-118">Desventajas del uso de un servidor de administración de alertas</span><span class="sxs-lookup"><span data-stu-id="e6062-118">Disadvantages of Using an Alerts Management Server</span></span>  
 <span data-ttu-id="e6062-119">Entre las desventajas de configurar un servidor de administración de alertas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="e6062-119">The disadvantages of setting up an alerts management server include:</span></span>  
  
-   <span data-ttu-id="e6062-120">**Aumento del tráfico**.</span><span class="sxs-lookup"><span data-stu-id="e6062-120">**Increased traffic**.</span></span> <span data-ttu-id="e6062-121">El reenvío de eventos a un servidor de administración de alertas puede aumentar el tráfico de la red.</span><span class="sxs-lookup"><span data-stu-id="e6062-121">Forwarding events to an alerts management server can increase network traffic.</span></span> <span data-ttu-id="e6062-122">Este aumento se puede moderar si se limita el reenvío a eventos que superan un nivel de gravedad especificado.</span><span class="sxs-lookup"><span data-stu-id="e6062-122">This increase can be moderated by restricting event forwarding to events that are above a designated severity level.</span></span>  
  
-   <span data-ttu-id="e6062-123">**Único punto de error**.</span><span class="sxs-lookup"><span data-stu-id="e6062-123">**Single point of failure**.</span></span> <span data-ttu-id="e6062-124">Si el servidor de administración de alertas se deja sin conexión, no se emite ninguna alerta para los eventos del grupo de servidores administrado.</span><span class="sxs-lookup"><span data-stu-id="e6062-124">If the alerts management server goes offline, no alerts are issued for any event on the managed group of servers.</span></span>  
  
-   <span data-ttu-id="e6062-125">**Carga del servidor**.</span><span class="sxs-lookup"><span data-stu-id="e6062-125">**Server load**.</span></span> <span data-ttu-id="e6062-126">La administración de alertas de los eventos reenviados provoca un aumento de la carga de procesamiento en el servidor de administración de alertas.</span><span class="sxs-lookup"><span data-stu-id="e6062-126">Handling alerts for the forwarded events causes an increased processing load on the alerts management server.</span></span>  
  
## <a name="guidelines-for-using-an-alerts-management-server"></a><span data-ttu-id="e6062-127">Directrices de uso de un servidor de administración de alertas</span><span class="sxs-lookup"><span data-stu-id="e6062-127">Guidelines for Using an Alerts Management Server</span></span>  
 <span data-ttu-id="e6062-128">Al configurar un servidor de administración de alertas, siga las siguientes directrices:</span><span class="sxs-lookup"><span data-stu-id="e6062-128">When configuring an alerts management server, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="e6062-129">Para recibir eventos reenviados, el servidor de administración de alertas debe ser una instancia predeterminada de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6062-129">In order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
-   <span data-ttu-id="e6062-130">Evite ejecutar aplicaciones muy importantes o con un alto grado de uso en el servidor de administración de alertas.</span><span class="sxs-lookup"><span data-stu-id="e6062-130">Avoid running critical or heavily used applications on the alerts management server.</span></span>  
  
-   <span data-ttu-id="e6062-131">Planee cuidadosamente el tráfico de red ocasionado por la configuración de muchos servidores para compartir el mismo servidor de administración de alertas.</span><span class="sxs-lookup"><span data-stu-id="e6062-131">Carefully plan for the network traffic involved in configuring many servers to share the same alerts management server.</span></span> <span data-ttu-id="e6062-132">Si se produce una congestión, reduzca el número de servidores que utilizan un servidor de administración de alertas determinado.</span><span class="sxs-lookup"><span data-stu-id="e6062-132">If congestion results, reduce the number of servers that use a particular alerts management server.</span></span>  
  
     <span data-ttu-id="e6062-133">Los servidores registrados en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] en un servidor concreto constituyen la lista de servidores disponibles entre los que ese servidor puede elegir el servidor de reenvío de alertas.</span><span class="sxs-lookup"><span data-stu-id="e6062-133">The servers that are registered within [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] constitute the list of servers available to be chosen by that server as the alerts-forwarding server.</span></span>  
  
-   <span data-ttu-id="e6062-134">Defina alertas en la instancia local de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que requieran una respuesta específica del servidor, en lugar de reenviar las alertas al servidor de administración de alertas.</span><span class="sxs-lookup"><span data-stu-id="e6062-134">Define alerts on the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that require a server-specific response, instead of forwarding the alerts to the alerts management server.</span></span>  
  
     <span data-ttu-id="e6062-135">El servidor de administración de alertas considera a todos los servidores que le reenvían alertas como un único servidor lógico.</span><span class="sxs-lookup"><span data-stu-id="e6062-135">The alerts management server views all the servers forwarding to it as a logical whole.</span></span> <span data-ttu-id="e6062-136">Por ejemplo, un servidor de administración de alertas responde de la misma manera a un evento 605 del servidor A que a un evento 605 del servidor B.</span><span class="sxs-lookup"><span data-stu-id="e6062-136">For example, an alerts management server responds in the same way to a 605 event from server A and a 605 event from server B.</span></span>  
  
-   <span data-ttu-id="e6062-137">Tras configurar el sistema de alertas, compruebe periódicamente si hay eventos del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el registro de aplicación de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="e6062-137">After configuring your alert system, periodically check the Microsoft Windows application log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events.</span></span>  
  
     <span data-ttu-id="e6062-138">Las condiciones de error encontradas por el motor de alertas se escriben en el registro de aplicación Windows local con el nombre de origen "Agente SQL Server".</span><span class="sxs-lookup"><span data-stu-id="e6062-138">Failure conditions encountered by the alerts engine are written to the local Windows application log with a source name of "SQL Server Agent."</span></span> <span data-ttu-id="e6062-139">Por ejemplo, si el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no puede enviar una notificación de correo electrónico como se ha definido, se escribirá un evento en el registro de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e6062-139">For example, if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent cannot send an e-mail notification as it has been defined, an event is logged in the application log.</span></span>  
  
 <span data-ttu-id="e6062-140">Si se desactiva una alerta definida localmente y se produce un evento que habría causado la activación de la alerta, el evento se reenviará al servidor de administración de alertas (si cumple la condición para el reenvío de alertas).</span><span class="sxs-lookup"><span data-stu-id="e6062-140">If a locally defined alert is inactivated, and an event occurs that would have caused the alert to fire, the event is forwarded to the alerts management server (if it satisfies the alert-forwarding condition).</span></span> <span data-ttu-id="e6062-141">Este reenvío permite al usuario activar y desactivar suplantaciones locales (alertas definidas localmente que también están definidas en el servidor de administración de alertas) según sea necesario, en el sitio local.</span><span class="sxs-lookup"><span data-stu-id="e6062-141">This forwarding allows local overrides (alerts defined locally that are also defined on the alerts management server) to be turned off and on as needed by the user at the local site.</span></span> <span data-ttu-id="e6062-142">También puede solicitar que se reenvíen siempre los eventos, aunque también se controlen mediante alertas locales.</span><span class="sxs-lookup"><span data-stu-id="e6062-142">You can also request that events always be forwarded, even if they are also handled by local alerts.</span></span>  
  
 <span data-ttu-id="e6062-143">A continuación se presentan tareas habituales para administrar eventos en un entorno multiservidor:</span><span class="sxs-lookup"><span data-stu-id="e6062-143">The following are common tasks for managing events in a multiserver environment:</span></span>  
  
 <span data-ttu-id="e6062-144">**Para designar un servidor de administración de alertas**</span><span class="sxs-lookup"><span data-stu-id="e6062-144">**To designate an alerts management server**</span></span>  
  
-   [<span data-ttu-id="e6062-145">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6062-145">SQL Server Management Studio</span></span>](../sql-server-management-studio-ssms.md)  
  
 <span data-ttu-id="e6062-146">**Para definir la respuesta a una alerta**</span><span class="sxs-lookup"><span data-stu-id="e6062-146">**To define the response to an alert**</span></span>  
  
-   [<span data-ttu-id="e6062-147">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6062-147">SQL Server Management Studio</span></span>](define-the-response-to-an-alert-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="e6062-148">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e6062-148">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql)  
  
## <a name="running-event-triggered-jobs"></a><span data-ttu-id="e6062-149">Ejecutar trabajos desencadenados por eventos</span><span class="sxs-lookup"><span data-stu-id="e6062-149">Running Event-Triggered Jobs</span></span>  
 <span data-ttu-id="e6062-150">Puede definir la ejecución de un trabajo en respuesta a una alerta.</span><span class="sxs-lookup"><span data-stu-id="e6062-150">You can define a job to be executed in response to an alert.</span></span> <span data-ttu-id="e6062-151">Por ejemplo, puede ejecutar un trabajo que solucione o diagnostique más exhaustivamente un problema detectado mediante la alerta.</span><span class="sxs-lookup"><span data-stu-id="e6062-151">For example, you can execute a job that corrects or further diagnoses a problem detected by the alert.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6062-152">Dado que un trabajo puede activar un evento, tenga cuidado de no crear un bucle recursivo de trabajos y alertas.</span><span class="sxs-lookup"><span data-stu-id="e6062-152">Because a job can raise an event, be careful not to create a recursive alert-job loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6062-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6062-153">See Also</span></span>  
 [<span data-ttu-id="e6062-154">Mensajes desys.sys&#40;&#41;de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e6062-154">sys.sysmessages &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-sysmessages-transact-sql)  
  
  
