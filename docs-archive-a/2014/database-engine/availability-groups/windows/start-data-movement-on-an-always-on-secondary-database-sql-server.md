---
title: Iniciar el movimiento de datos en una base de datos secundaria AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], databases
ms.assetid: 498eb3fb-6a43-434d-ad95-68a754232c45
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3ce4f80b456244cd6e024377383abe75e002057a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750189"
---
# <a name="start-data-movement-on-an-alwayson-secondary-database-sql-server"></a><span data-ttu-id="1f399-102">Iniciar el movimiento de datos en una base de datos secundaria AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="1f399-102">Start Data Movement on an AlwaysOn Secondary Database (SQL Server)</span></span>
  <span data-ttu-id="1f399-103">Este tema contiene información sobre cómo iniciar la sincronización de datos después de agregar una base de datos a un grupo de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="1f399-103">This topic contains information about how to start data synchronization after you add a database to an AlwaysOn availability group.</span></span> <span data-ttu-id="1f399-104">Para cada nueva réplica principal, las bases de datos secundarias deben estar preparadas en las instancias de servidor que hospedan las réplicas secundarias.</span><span class="sxs-lookup"><span data-stu-id="1f399-104">For each new primary replica, secondary databases must be prepared on the server instances that host the secondary replicas.</span></span> <span data-ttu-id="1f399-105">Después, cada una de estas bases de datos secundarias se debe unir manualmente al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1f399-105">Then each of these secondary databases must be manually joined to the availability group.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f399-106">Si las rutas de acceso de archivos son idénticas en cada instancia de servidor que hospeda una réplica de disponibilidad para un grupo de disponibilidad, el [Asistente para nuevo grupo de disponibilidad](use-the-availability-group-wizard-sql-server-management-studio.md), el [Asistente para agregar réplica al grupo de disponibilidad](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)o el [Asistente para agregar base de datos al grupo de disponibilidad](availability-group-add-database-to-group-wizard.md) pueden iniciar automáticamente la sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="1f399-106">If the file paths are identical on every server instance that hosts an availability replica for an availability group, the [New Availability Group Wizard](use-the-availability-group-wizard-sql-server-management-studio.md), [Add Replica to Availability Group Wizard](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md), or [Add Database to Availability Group Wizard](availability-group-add-database-to-group-wizard.md) might be able to automatically start data synchronization for you.</span></span>  
  
 <span data-ttu-id="1f399-107">Para iniciar manualmente la sincronización de datos, debe conectarse, a su vez, a cada instancia de servidor que esté hospedando una réplica secundaria para el grupo de disponibilidad y completar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f399-107">To start data synchronization manually, you need to connect, in turn, to each server instance that is hosting a secondary replica for the availability group and complete the following steps:</span></span>  
  
1.  <span data-ttu-id="1f399-108">Restaure las copias de seguridad actuales de cada base de datos principal y del registro de transacciones (mediante RESTORE WITH NORECOVERY).</span><span class="sxs-lookup"><span data-stu-id="1f399-108">Restore current backups of each primary database and its transaction log (using RESTORE WITH NORECOVERY).</span></span> <span data-ttu-id="1f399-109">Puede usar alguna de las alternativas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f399-109">You can use either of the following alternative approaches:</span></span>  
  
    -   <span data-ttu-id="1f399-110">Restaure manualmente una copia de seguridad reciente de la base de datos principal utilizando RESTORE WITH NORECOVERY y restaure después cada copia de seguridad de registros posterior utilizando RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="1f399-110">Manually restore a recent database backup of the primary database using RESTORE WITH NORECOVERY, and then restore each subsequent log backup using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="1f399-111">Realice esta secuencia de restauración en cada instancia del servidor que hospeda una réplica secundaria del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1f399-111">Perform this restore sequence on every server instance that hosts a secondary replica for the availability group.</span></span>  
  
         <span data-ttu-id="1f399-112">**Para obtener más información:**</span><span class="sxs-lookup"><span data-stu-id="1f399-112">**For more information:**</span></span>  
  
         [<span data-ttu-id="1f399-113">Preparar manualmente una base de datos secundaria para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1f399-113">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
    -   <span data-ttu-id="1f399-114">Si va a agregar una o varias bases de datos principales de trasvase de registros en un grupo de disponibilidad, es posible que pueda migrar una o varias de sus bases de datos secundarias correspondientes de los grupos de trasvase de registros a los grupos de disponibilidad AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="1f399-114">If you are adding one or more log shipping primary databases to an availability group, you might be able to migrate one or more of the corresponding secondary databases from log shipping to AlwaysOn Availability Groups.</span></span> <span data-ttu-id="1f399-115">Para migrar una base de datos secundaria de trasvase de registros, es necesario usar el mismo nombre de base de datos que la base de datos principal que reside en una instancia de servidor que hospeda una réplica secundaria para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1f399-115">Migrating a log shipping secondary database requires that it use the same database name as the primary database and that it reside on a server instance that is hosting a secondary replica for the availability group.</span></span> <span data-ttu-id="1f399-116">Además, el grupo de disponibilidad debe configurarse de modo que la réplica principal se prefiera para las copias de seguridad y sea candidata para realizar copias de seguridad (es decir, que la prioridad de copia de seguridad sea > 0).</span><span class="sxs-lookup"><span data-stu-id="1f399-116">Furthermore, the availability group must be configured so that the primary replica is preferred for backups and is a candidate for performing backups (that is, that has a backup priority that is >0).</span></span> <span data-ttu-id="1f399-117">Una vez que el trabajo de copia de seguridad se ejecute en la base de datos principal, tendrá que deshabilitar el trabajo de copia de seguridad y, una vez que el trabajo de restauración se haya ejecutado en una base de datos secundaria, deshabilitar el trabajo de restauración.</span><span class="sxs-lookup"><span data-stu-id="1f399-117">Once the backup job has run on the primary database, you will need to disable the backup job, and once the restore job has run on a given secondary database, you will need to disable the restore job.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="1f399-118">Después de crear todas las bases de datos secundarias para el grupo de disponibilidad, si desea realizar copias de seguridad en las réplicas secundarias, deberá configurar de nuevo la preferencia de copia de seguridad automatizada del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1f399-118">After you have created all the secondary databases for the availability group, if you want to perform backups on secondary replicas, you will need to re-configure the automated backup preference of the availability group.</span></span>  
  
         <span data-ttu-id="1f399-119">**Para obtener más información:**</span><span class="sxs-lookup"><span data-stu-id="1f399-119">**For more information:**</span></span>  
  
         [<span data-ttu-id="1f399-120">Requisitos previos para la migración desde el trasvase de registros a Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1f399-120">Prerequisites for Migrating from Log Shipping to AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-migrating-log-shipping-to-always-on-availability-groups.md)  
  
         [<span data-ttu-id="1f399-121">Configurar la copia de seguridad en réplicas de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1f399-121">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
2.  <span data-ttu-id="1f399-122">En cuanto sea posible, una cada base de datos secundaria preparada al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="1f399-122">As soon as possible, join each newly prepared secondary database to the availability group.</span></span>  
  
     <span data-ttu-id="1f399-123">**Para obtener más información:**</span><span class="sxs-lookup"><span data-stu-id="1f399-123">**For more information:**</span></span>  
  
     [<span data-ttu-id="1f399-124">Combinar una base de datos secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1f399-124">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="LaunchWiz"></a> <span data-ttu-id="1f399-125">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="1f399-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="1f399-126">Usar el cuadro de diálogo Nuevo grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1f399-126">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="1f399-127">Usar el Asistente para agregar una réplica al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1f399-127">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="1f399-128">Usar el Asistente para agregar una base de datos al grupo de disponibilidad &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="1f399-128">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="1f399-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f399-129">See Also</span></span>  
 [<span data-ttu-id="1f399-130">Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1f399-130">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
