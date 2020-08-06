---
title: Mantener una base de datos de publicación AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 55b345fe-2eb9-4b04-a900-63d858eec360
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8f36d29049140b6e5bbdfc1a4e716d41a766a06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672259"
---
# <a name="maintaining-an-alwayson-publication-database-sql-server"></a><span data-ttu-id="e6985-102">Mantener una base de datos de publicación AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e6985-102">Maintaining an AlwaysOn Publication Database (SQL Server)</span></span>
  <span data-ttu-id="e6985-103">En este tema se describen las consideraciones especiales para mantener una base de datos de publicación cuando se usan grupos de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e6985-103">This topic discusses special considerations for maintaining a publication database when you use AlwaysOn availability groups.</span></span>  
  
 
  
##  <a name="maintaining-a-published-database-in-an-availability-group"></a><a name="MaintainPublDb"></a><span data-ttu-id="e6985-104">Mantener una base de datos Publicada en un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="e6985-104">Maintaining a Published Database in an Availability Group</span></span>  
 <span data-ttu-id="e6985-105">El mantenimiento de una base de datos de publicación AlwaysOn se realiza básicamente de la misma forma que para una base de datos de publicación estándar, con las siguientes salvedades:</span><span class="sxs-lookup"><span data-stu-id="e6985-105">Maintaining an AlwaysOn publication database is basically the same as maintaining a standard publication database, with the following considerations:</span></span>  
  
-   <span data-ttu-id="e6985-106">La administración debe producirse en el host de réplica principal.</span><span class="sxs-lookup"><span data-stu-id="e6985-106">Administration must occur at the primary replica host.</span></span> <span data-ttu-id="e6985-107">En [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], las publicaciones aparecen bajo la carpeta de **Publicaciones locales** para el host de réplica principal y también para las réplicas secundarias legibles.</span><span class="sxs-lookup"><span data-stu-id="e6985-107">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], publications appear under the **Local Publications** folder for the primary replica host and also for readable secondary replicas.</span></span> <span data-ttu-id="e6985-108">Después de la conmutación por error, puede que tenga que actualizar manualmente [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] para que el cambio quede reflejado si el elemento secundario promovido a principal no era legible.</span><span class="sxs-lookup"><span data-stu-id="e6985-108">After failover, you might have to manually refresh [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] for the change to be reflected if the secondary that was promoted to primary was not readable.</span></span>  
  
-   <span data-ttu-id="e6985-109">El Monitor de replicación muestra siempre la información de publicación en el publicador original.</span><span class="sxs-lookup"><span data-stu-id="e6985-109">Replication Monitor always displays publication information under the original publisher.</span></span> <span data-ttu-id="e6985-110">Sin embargo, esta información se puede ver en el Monitor de replicación de cualquier réplica al agregar el publicador original como servidor.</span><span class="sxs-lookup"><span data-stu-id="e6985-110">However, this information can be viewed in Replication Monitor from any replica by adding the original publisher as a server.</span></span>  
  
-   <span data-ttu-id="e6985-111">Si se utilizan procedimientos almacenados o Replication Management Objects (RMO) para administrar la replicación en la réplica principal actual, en los casos en que se especifica el nombre del publicador, se debe especificar el nombre de la instancia en la que la base de datos se habilitó para la replicación (el publicador original).</span><span class="sxs-lookup"><span data-stu-id="e6985-111">When using stored procedures or Replication Management Objects (RMO) to administer replication at the current primary, for cases in which you specify the Publisher name, you must specify the name of the instance on which the database was enabled for replication (the original publisher).</span></span> <span data-ttu-id="e6985-112">Para determinar el nombre correcto, use la función `PUBLISHINGSERVERNAME`.</span><span class="sxs-lookup"><span data-stu-id="e6985-112">To determine the appropriate name, use the `PUBLISHINGSERVERNAME` function.</span></span> <span data-ttu-id="e6985-113">Cuando una base de datos de publicación se une a un grupo de disponibilidad, los metadatos de replicación almacenados en las réplicas de la base de datos secundaria son idénticos a los de la principal.</span><span class="sxs-lookup"><span data-stu-id="e6985-113">When a publishing database joins an availability group, the replication metadata stored in the secondary database replicas is identical to that at the primary.</span></span> <span data-ttu-id="e6985-114">En consecuencia, para las bases de datos de publicación habilitadas para replicación en la entidad principal, el nombre de la instancia del publicador que está almacenado en las tablas del sistema en la entidad secundaria es el nombre de la entidad principal en lugar del nombre de la entidad secundaria.</span><span class="sxs-lookup"><span data-stu-id="e6985-114">Consequently, for publication databases enabled for replication at the primary, the publisher instance name stored in system tables at the secondary is the name of the primary, not the secondary.</span></span> <span data-ttu-id="e6985-115">Esto afecta a la configuración y al mantenimiento de la replicación si se produce la conmutación por error de la base de datos de publicación a la entidad secundaria.</span><span class="sxs-lookup"><span data-stu-id="e6985-115">This affects replication configuration and maintenance if the publication database fails over to a secondary.</span></span> <span data-ttu-id="e6985-116">Por ejemplo, si está configurando la replicación con procedimientos almacenados en una secundaria después de la conmutación por error y desea una suscripción de extracción a una base de datos de publicación que se habilitó en otra réplica, debe especificar el nombre del publicador original en lugar del publicador actual como *@publisher* parámetro de `sp_addpullsubscription` o `sp_addmergepulllsubscription` .</span><span class="sxs-lookup"><span data-stu-id="e6985-116">For example, if you are configuring replication with stored procedures at a secondary after failover, and you want a pull subscription to a publication database that was enabled at a different replica, you must specify the name of the original publisher instead of the current publisher as the *@publisher* parameter of `sp_addpullsubscription` or `sp_addmergepulllsubscription`.</span></span> <span data-ttu-id="e6985-117">Sin embargo, si habilita una base de datos de publicación después de la conmutación por error, el nombre de la instancia del publicador almacenado en las tablas del sistema es el nombre del host principal actual.</span><span class="sxs-lookup"><span data-stu-id="e6985-117">However, if you enable a publication database after failover, the publisher instance name stored in the system tables is the name of the current primary host.</span></span> <span data-ttu-id="e6985-118">En este caso, usaría el nombre de host de la réplica principal actual para el *@publisher* parámetro.</span><span class="sxs-lookup"><span data-stu-id="e6985-118">In this case, you would use the host name of the current primary replica for the *@publisher* parameter.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e6985-119">En algunos procedimientos, como `sp_addpublication` , el *@publisher* parámetro solo se admite para publicadores que no son instancias de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ; en estos casos, no es relevante para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="e6985-119">For some procedures, such as `sp_addpublication`, the *@publisher* parameter is supported only for publishers that are not instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]; in these cases, it is not relevant for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn.</span></span>  
  
-   <span data-ttu-id="e6985-120">Para sincronizar una suscripción en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] tras una conmutación por error, sincronice las suscripciones de extracción del suscriptor y sincronice las suscripciones de inserción del publicador activo.</span><span class="sxs-lookup"><span data-stu-id="e6985-120">To synchronize a subscription in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] after a failover, synchronize pull subscriptions from the subscriber and synchronize push subscriptions from the active publisher.</span></span>  
  
##  <a name="removing-a-published-database-from-an-availability-group"></a><a name="RemovePublDb"></a> <span data-ttu-id="e6985-121">Quitar una base de datos publicada de un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="e6985-121">Removing a Published Database from an Availability Group</span></span>  
 <span data-ttu-id="e6985-122">Tenga en cuenta los siguientes problemas si quita una base de datos publicada de un grupo de disponibilidad, o si quita un grupo de disponibilidad que tiene una base de datos de miembros publicada.</span><span class="sxs-lookup"><span data-stu-id="e6985-122">Consider the following issues if a published database is removed from an availability group, or if an availability group that has a published member database is dropped.</span></span>  
  
-   <span data-ttu-id="e6985-123">Si la base de datos de publicación del publicador original se quita de una réplica principal del grupo de disponibilidad, debe ejecutar `sp_redirect_publisher` sin especificar un valor para el parámetro con el *@redirected_publisher* fin de quitar el redireccionamiento del par de publicador y base de datos.</span><span class="sxs-lookup"><span data-stu-id="e6985-123">If the publication database at the original publisher is removed from an availability group primary replica, you must run `sp_redirect_publisher` without specifying a value for the *@redirected_publisher* parameter in order to remove the redirection for the publisher/database pair.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB';  
    ```  
  
     <span data-ttu-id="e6985-124">La base de datos se quedará en el estado de recuperación en el servidor principal y debe restaurarse.</span><span class="sxs-lookup"><span data-stu-id="e6985-124">The database will be left in the recovering state at the primary and must be restored.</span></span> <span data-ttu-id="e6985-125">Una vez que haya realizado esto, la replicación debe funcionar sin cambios en el publicador original.</span><span class="sxs-lookup"><span data-stu-id="e6985-125">Once you do this, replication should work unchanged against the original Publisher.</span></span>  
  
-   <span data-ttu-id="e6985-126">Si la base de datos de publicación conmuta por error del publicador original a una réplica y la base de datos se quita de la réplica principal del grupo de disponibilidad, use el procedimiento almacenado `sp_redirect_publisher` para redirigir explícitamente el publicador original en el nuevo publicador.</span><span class="sxs-lookup"><span data-stu-id="e6985-126">If the publication database fails over from the original publisher to a replica and the database is removed from the availability group primary replica, use the stored procedure `sp_redirect_publisher` to explicitly redirect the original publisher to the new publisher.</span></span> <span data-ttu-id="e6985-127">La base de datos se quedará en el estado de recuperación y debe restaurarse.</span><span class="sxs-lookup"><span data-stu-id="e6985-127">The database will be left in the recovering state and must be restored.</span></span> <span data-ttu-id="e6985-128">Una vez que haya realizado esto, la replicación debe continuar funcionando como lo hizo con el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e6985-128">Once you do this, replication should continue to work as it did under the availability group.</span></span>  
  
    ```  
    EXEC sys.sp_redirect_publisher   
        @original_publisher = 'MyPublisher',  
        @published_database = 'MyPublishedDB',  
        @redirected_publisher = 'MyNewPublisher';  
    ```  
  
     <span data-ttu-id="e6985-129">No quite el servidor remoto para el publicador original del distribuidor, incluso si ya no se puede tener acceso al servidor.</span><span class="sxs-lookup"><span data-stu-id="e6985-129">Do not remove the remote server for the original publisher from the distributor, even if the server can no longer be accessed.</span></span> <span data-ttu-id="e6985-130">Los metadatos de servidor del publicador original son necesarios en el distribuidor para satisfacer las consultas de los metadatos de la publicación.</span><span class="sxs-lookup"><span data-stu-id="e6985-130">The server metadata for the original publisher is needed at the distributor to satisfy publication metadata queries.</span></span>  
  
-   <span data-ttu-id="e6985-131">Si se quita un grupo de disponibilidad completo, el comportamiento con respecto a una base de datos replicada de miembros es el mismo que cuando se quita una base de datos publicada de un grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e6985-131">If a complete availability group is removed, the behavior with regard to a member replicated database is the same as when a published database is removed from an availability group.</span></span> <span data-ttu-id="e6985-132">La replicación se puede reanudar desde el último servidor principal tan pronto como se haya restaurado la base de datos y se haya modificado la redirección.</span><span class="sxs-lookup"><span data-stu-id="e6985-132">Replication can be resumed from the last primary as soon as the database has been restored and the redirection has been modified.</span></span> <span data-ttu-id="e6985-133">Si la base de datos se restaura en su publicador original, debe quitase la redirección.</span><span class="sxs-lookup"><span data-stu-id="e6985-133">If the database is restored at its original publisher, redirection should be removed.</span></span> <span data-ttu-id="e6985-134">Si la base de datos se restaura en un host diferente, la redirección debe ejecutarse explícitamente el nuevo host.</span><span class="sxs-lookup"><span data-stu-id="e6985-134">If the database is restored at a different host, redirection should be explicitly directed to the new host.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e6985-135">Cuando se quita un grupo de disponibilidad que ha publicado bases de datos de miembros o una base de datos publicada de un grupo de disponibilidad, todas las copias de las bases de datos publicadas se dejarán en estado de recuperación.</span><span class="sxs-lookup"><span data-stu-id="e6985-135">When an availability group is removed that has published member databases, or a published database is removed from an availability group, all copies of the published databases will be left in the recovering state.</span></span> <span data-ttu-id="e6985-136">Si se restaura, cada una aparecerá como base de datos publicada.</span><span class="sxs-lookup"><span data-stu-id="e6985-136">If restored, each will appear as a published database.</span></span> <span data-ttu-id="e6985-137">Solo se debe conservar una copia con los metadatos de la publicación.</span><span class="sxs-lookup"><span data-stu-id="e6985-137">Only one copy should be retained with publication metadata.</span></span> <span data-ttu-id="e6985-138">Para deshabilitar la replicación para una copia de la base de datos publicada, primero debe quitar todas las suscripciones y publicaciones de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e6985-138">To disable replication for a published database copy, first remove all subscriptions and publications from the database.</span></span>  
  
     <span data-ttu-id="e6985-139">Ejecute `sp_dropsubscription` para quitar suscripciones de la publicación.</span><span class="sxs-lookup"><span data-stu-id="e6985-139">Run `sp_dropsubscription` to remove publication subscriptions.</span></span> <span data-ttu-id="e6985-140">Asegúrese de establecer el parámetro *@ignore_distributributor* en 1 para conservar los metadatos de la base de datos de publicación activa en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e6985-140">Make sure to set the parameter *@ignore_distributributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    USE MyDBName;  
    GO  
  
    EXEC sys.sp_dropsubscription   
        @subscriber = 'MySubscriber',  
        @publication = 'MyPublication',  
        @article = 'all',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="e6985-141">Ejecute `sp_droppublication` para quitar todas las publicaciones.</span><span class="sxs-lookup"><span data-stu-id="e6985-141">Run `sp_droppublication` to remove all publications.</span></span> <span data-ttu-id="e6985-142">De nuevo, establezca el parámetro *@ignore_distributor* en 1 para conservar los metadatos de la base de datos de publicación activa en el distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e6985-142">Again, set the parameter *@ignore_distributor* to 1 to preserve the metadata for the active publishing database at the distributor.</span></span>  
  
    ```  
    EXEC sys.sp_droppublication   
        @publication = 'MyPublication',  
        @ignore_distributor = 1;  
    ```  
  
     <span data-ttu-id="e6985-143">Ejecute `sp_replicationdboption` para deshabilitar la replicación para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e6985-143">Run `sp_replicationdboption` to disable replication for the database.</span></span>  
  
    ```  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'false';  
    ```  
  
     <span data-ttu-id="e6985-144">En este momento, la copia de la base de datos publicada se puede conservar o quitar.</span><span class="sxs-lookup"><span data-stu-id="e6985-144">At this point, the copy of the published database can be retained or dropped.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e6985-145">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="e6985-145">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e6985-146">Configurar la replicación para grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e6985-146">Configure Replication for AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-availability-groups-sql-server.md)  
  
-   [<span data-ttu-id="e6985-147">Replicación, Change Tracking, captura de datos modificados y Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e6985-147">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="e6985-148">Preguntas más frecuentes para administradores de replicación</span><span class="sxs-lookup"><span data-stu-id="e6985-148">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
-   [<span data-ttu-id="e6985-149">Suscriptores de replicación y Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e6985-149">Replication Subscribers and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replication-subscribers-and-always-on-availability-groups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="e6985-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6985-150">See Also</span></span>  
 <span data-ttu-id="e6985-151">[Requisitos previos, restricciones y recomendaciones para el SQL Server de &#40;de Grupos de disponibilidad AlwaysOn&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="e6985-151">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="e6985-152">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e6985-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="e6985-153">[Grupos de disponibilidad AlwaysOn: interoperabilidad (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e6985-153">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="e6985-154">Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e6985-154">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
  
  
