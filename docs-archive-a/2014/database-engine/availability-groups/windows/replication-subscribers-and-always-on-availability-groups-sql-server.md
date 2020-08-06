---
title: Suscriptores de replicación y Grupos de disponibilidad AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/16/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover subscribers with AlwaysOn
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 0995f269-0580-43ed-b8bf-02b9ad2d7ee6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 449b5ac416f2ae86395c40a984678ed4258b3b85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673901"
---
# <a name="replication-subscribers-and-alwayson-availability-groups-sql-server"></a><span data-ttu-id="576cb-102">Suscriptores de replicación y grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="576cb-102">Replication Subscribers and AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="576cb-103">Cuando el grupo de disponibilidad AlwaysOn que contiene una base de datos que es un suscriptor de replicación realiza una conmutación por error, se puede producir un error en la suscripción de replicación.</span><span class="sxs-lookup"><span data-stu-id="576cb-103">When an AlwaysOn availability group containing a database that is a replication subscriber fails over, the replication subscription might fail.</span></span> <span data-ttu-id="576cb-104">Para los suscriptores de inserción de replicación transaccional, el agente de distribución se seguirá replicando automáticamente después de una conmutación por error si la suscripción se creó mediante el nombre de la escucha de grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="576cb-104">For transactional replication push subscribers, the distribution agent will continue to replicate automatically after a failover if the subscription was created using the AG listener name.</span></span> <span data-ttu-id="576cb-105">Para los suscriptores de extracción de replicación transaccional, el agente de distribución se seguirá replicando automáticamente después de una conmutación por error si la suscripción se creó mediante el nombre de la escucha de grupo de disponibilidad y el servidor del suscriptor original está activo y en ejecución.</span><span class="sxs-lookup"><span data-stu-id="576cb-105">For transactional replication pull subscribers, the distribution agent will continue to replicate automatically after a failover, if the subscription was created using the AG listener name and the original subscriber server is up and running.</span></span> <span data-ttu-id="576cb-106">El motivo es que los trabajos del agente de distribución solo se crean en el suscriptor original (réplica principal del grupo de disponibilidad).</span><span class="sxs-lookup"><span data-stu-id="576cb-106">This is because the distribution agent jobs only get created on the original subscriber (primary replica of the AG).</span></span> <span data-ttu-id="576cb-107">Para los suscriptores de mezcla, un administrador de replicación debe volver a configurar manualmente el suscriptor volviendo a crear la suscripción.</span><span class="sxs-lookup"><span data-stu-id="576cb-107">For merge subscribers, a replication administrator must manually reconfigure the subscriber, by recreating the subscription.</span></span>  
  
## <a name="what-is-supported"></a><span data-ttu-id="576cb-108">Qué se admite</span><span class="sxs-lookup"><span data-stu-id="576cb-108">What is Supported</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="576cb-109">admite la conmutación por error automática del publicador, la conmutación por error de suscriptores transaccionales y la conmutación por error manual de los suscriptores de mezcla.</span><span class="sxs-lookup"><span data-stu-id="576cb-109">replication supports the automatic failover of the publisher, the automatic failover of transactional subscribers, and the manual failover of merge subscribers.</span></span> <span data-ttu-id="576cb-110">No se admite la conmutación por error de un distribuidor de una base de datos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="576cb-110">The failover of a distributor on an availability database is not supported.</span></span> <span data-ttu-id="576cb-111">AlwaysOn no puede combinarse con escenarios de Websync ni [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact.</span><span class="sxs-lookup"><span data-stu-id="576cb-111">AlwaysOn cannot be combined with Websync and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Compact scenarios.</span></span>  
  
 <span data-ttu-id="576cb-112">**Conmutación por error de una suscripción de extracción de mezcla**</span><span class="sxs-lookup"><span data-stu-id="576cb-112">**Failover of a Merge Pull Subscription**</span></span>  
  
 <span data-ttu-id="576cb-113">Se produce un error en una suscripción de extracción tras la conmutación por error del grupo de disponibilidad porque el agente de extracción no puede encontrar los trabajos almacenados en la base de datos **msdb** de la instancia de servidor que hospeda la réplica principal, que no está disponible porque se ha producido un error en la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="576cb-113">A pull subscription fails upon availability group failover, because pull agent cannot find the jobs stored in the **msdb** database of the server instance that hosts the primary replica; which is not available because the server instance has failed.</span></span>  
  
 <span data-ttu-id="576cb-114">**Conmutación por error de una suscripción de inserción de mezcla**</span><span class="sxs-lookup"><span data-stu-id="576cb-114">**Failover of a Merge Push Subscription**</span></span>  
  
 <span data-ttu-id="576cb-115">Se produce un error en una suscripción de inserción tras la conmutación por error del grupo de disponibilidad porque el agente de inserción ya no puede conectarse a la base de datos de suscripciones original en el suscriptor original.</span><span class="sxs-lookup"><span data-stu-id="576cb-115">A push subscription fails upon availability group failover, because the push agent can no longer connect to original subscription database on original subscriber.</span></span>  
  
## <a name="how-to-create-transactional-subscription-in-an-alwayson-environment"></a><span data-ttu-id="576cb-116">Cómo crear una suscripción transaccional en un entorno de AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="576cb-116">How to Create Transactional Subscription in an AlwaysOn Environment</span></span>  
 <span data-ttu-id="576cb-117">Para la replicación transaccional, utilice los pasos siguientes para configurar y conmutar por error un grupo de disponibilidad de suscriptor:</span><span class="sxs-lookup"><span data-stu-id="576cb-117">For transactional replication, use the following steps to configure and failover a subscriber availability group:</span></span>  
  
1.  <span data-ttu-id="576cb-118">Antes de crear la suscripción, agregue la base de datos del suscriptor al grupo de disponibilidad AlwaysOn adecuado.</span><span class="sxs-lookup"><span data-stu-id="576cb-118">Before creating the subscription, add the subscriber database to the appropriate AlwaysOn availability group.</span></span>  
  
2.  <span data-ttu-id="576cb-119">Agregue el agente de escucha del grupo de disponibilidad del suscriptor como un servidor vinculado a todos los nodos del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="576cb-119">Add the subscriber's availability group Listener as a linked server to all nodes of the availability group.</span></span> <span data-ttu-id="576cb-120">Este paso garantiza que todos los posibles asociados de conmutación por error sean conscientes del agente de escucha y se puedan conectar al mismo.</span><span class="sxs-lookup"><span data-stu-id="576cb-120">This step ensures that all potential failover partners are aware of and can connect to the listener.</span></span>  
  
3.  <span data-ttu-id="576cb-121">Con el script de la sección **Crear una suscripción de inserción para una replicación transaccional** de más abajo, cree la suscripción y use el nombre del agente de escucha del grupo de disponibilidad del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="576cb-121">Using the script in the **Creating a Transactional Replication Push Subscription** section below, create the subscription using the name of the availability group listener of the subscriber.</span></span> <span data-ttu-id="576cb-122">Después de una conmutación por error, el nombre del agente de escucha siempre sigue siendo válido, mientras que el nombre de servidor real del suscriptor dependerá del nodo real que se convirtió en el nuevo primario.</span><span class="sxs-lookup"><span data-stu-id="576cb-122">After a failover, the listener name will always remain valid, whereas the actual server name of the subscriber will depend on the actual node that became the new primary.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="576cb-123">Es preciso que la suscripción se cree mediante un script de [!INCLUDE[tsql](../../../includes/tsql-md.md)] y no se puede crear con [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="576cb-123">The subscription must be created by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] script and cannot be created using [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="576cb-124">Si se va a crear una suscripción de extracción:</span><span class="sxs-lookup"><span data-stu-id="576cb-124">If creating a pull subscription:</span></span>  
  
    1.  <span data-ttu-id="576cb-125">En [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], en el nodo principal del suscriptor, abra el árbol del Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="576cb-125">In [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], on the primary subscriber node, open the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent tree.</span></span>  
  
    2.  <span data-ttu-id="576cb-126">Identifique el trabajo **Agente de distribución de extracción** y edite el trabajo.</span><span class="sxs-lookup"><span data-stu-id="576cb-126">Identify the **Pull Distribution Agent** job and edit the job.</span></span>  
  
    3.  <span data-ttu-id="576cb-127">En el paso de trabajo **Ejecutar agente** , active los parámetros `-Publisher` y `-Distributor` .</span><span class="sxs-lookup"><span data-stu-id="576cb-127">On the **Run Agent** job step, check the `-Publisher` and `-Distributor` parameters.</span></span> <span data-ttu-id="576cb-128">Asegúrese de que estos parámetros contienen los nombres de servidor y de instancia directos correctos del servidor del publicador y del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="576cb-128">Make sure that these parameters contain the correct direct server and instance names of the publisher and distributor server.</span></span>  
  
    4.  <span data-ttu-id="576cb-129">Cambie el parámetro `-Subscriber` al nombre del agente de escucha del grupo de disponibilidad del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="576cb-129">Change the `-Subscriber` parameter to the subscriber's availability group listener name.</span></span>  
  
 <span data-ttu-id="576cb-130">Cuando cree la suscripción siguiendo estos pasos, no tendrá que hacer nada tras una conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="576cb-130">When you create your subscription following these steps, then you won't have to do anything after a failover.</span></span>  
  
## <a name="creating-a-transactional-replication-push-subscription"></a><span data-ttu-id="576cb-131">Crear una suscripción de inserción para una replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="576cb-131">Creating a Transactional Replication Push Subscription</span></span>  
  
```  
-- commands to execute at the publisher, in the publisher database:  
use [<publisher database name>]  
EXEC sp_addsubscription @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @destination_db = N'<subscriber database name>',   
       @subscription_type = N'Push',   
       @sync_type = N'automatic', @article = N'all', @update_mode = N'read only', @subscriber_type = 0;  
GO  
  
EXEC sp_addpushsubscription_agent @publication = N'<publication name>',   
       @subscriber = N'<availability group listener name>',   
       @subscriber_db = N'<subscriber database name>',   
       @job_login = null, @job_password = null, @subscriber_security_mode = 1;  
GO  
```  
  
## <a name="to-resume-the-merge-agents-after-the-availability-group-of-the-subscriber-fails-over"></a><span data-ttu-id="576cb-132">Para reanudar los agentes de mezcla después de la conmutación por error del grupo de disponibilidad del suscriptor</span><span class="sxs-lookup"><span data-stu-id="576cb-132">To Resume the Merge Agents After the Availability Group of the Subscriber Fails Over</span></span>  
 <span data-ttu-id="576cb-133">Para la replicación de mezcla, un administrador de replicación debe volver a configurar manualmente el suscriptor con los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="576cb-133">For merge replication, a replication administrator must manually reconfigure the subscriber with the following steps:</span></span>  
  
1.  <span data-ttu-id="576cb-134">Ejecute `sp_subscription_cleanup` para eliminar la suscripción antigua del suscriptor.</span><span class="sxs-lookup"><span data-stu-id="576cb-134">Execute `sp_subscription_cleanup` to remove the old subscription for the subscriber.</span></span> <span data-ttu-id="576cb-135">Realice esta acción en la nueva réplica principal (que era antes la réplica secundaria).</span><span class="sxs-lookup"><span data-stu-id="576cb-135">Perform this action on the new primary replica (which was formerly the secondary replica).</span></span>  
  
2.  <span data-ttu-id="576cb-136">Vuelva a crear la suscripción, para ello cree una nueva suscripción, comenzando por una nueva instantánea.</span><span class="sxs-lookup"><span data-stu-id="576cb-136">Recreate the subscription by creating a new subscription, beginning with a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="576cb-137">El proceso actual no es apto para los suscriptores de replicación de mezcla, aunque el escenario principal para la replicación de mezcla son los usuarios desconectados (escritorio, equipos portátiles, dispositivos de auricular) que no utilizarán los grupos de disponibilidad AlwaysOn en el suscriptor.</span><span class="sxs-lookup"><span data-stu-id="576cb-137">The current process is inconvenient for merge replication subscribers, however the main scenario for merge replication is disconnected users (desktops, laptops, handset devices) which will not use AlwaysOn availability groups on the subscriber.</span></span>  
  
  
