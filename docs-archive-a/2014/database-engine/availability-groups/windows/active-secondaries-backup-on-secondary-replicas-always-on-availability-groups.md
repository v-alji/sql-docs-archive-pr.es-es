---
title: 'Secundarias activas: copia de seguridad en las réplicas secundarias (Always On grupos de disponibilidad) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- backup priority
- backup on secondary replicas
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], backup on secondary replicas
- active secondary replicas [SQL Server], backup on
- automated backup preference
- Availability Groups [SQL Server], active secondary replicas
ms.assetid: 82afe51b-71d1-4d5b-b20a-b57afc002405
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0cf899cdbeb1ae4ede6c9196b8eb93a9d9e54f05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746542"
---
# <a name="active-secondaries-backup-on-secondary-replicas-always-on-availability-groups"></a><span data-ttu-id="c8912-102">Secundarias activas: copia de seguridad en las réplicas secundarias (grupos de disponibilidad AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="c8912-102">Active Secondaries: Backup on Secondary Replicas (Always On Availability Groups)</span></span>
  <span data-ttu-id="c8912-103">Las funciones secundarias activas de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] incluyen compatibilidad para realizar operaciones de copia de seguridad en las réplicas secundarias.</span><span class="sxs-lookup"><span data-stu-id="c8912-103">The [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] active secondary capabilities include support for performing backup operations on secondary replicas.</span></span> <span data-ttu-id="c8912-104">Las operaciones de copia de seguridad pueden provocar una demanda significativa de E/S y CPU (con la compresión de copia de seguridad).</span><span class="sxs-lookup"><span data-stu-id="c8912-104">Backup operations can put significant strain on I/O and CPU (with backup compression).</span></span> <span data-ttu-id="c8912-105">La descarga de las copias de seguridad en una réplica secundaria sincronizada o en proceso de sincronización permite utilizar los recursos de la instancia del servidor que hospeda la réplica principal para las cargas de trabajo de nivel 1.</span><span class="sxs-lookup"><span data-stu-id="c8912-105">Offloading backups to a synchronized or synchronizing secondary replica allows you to use the resources on server instance that hosts the primary replica for your tier-1 workloads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8912-106">Las instrucciones RESTORE no se permiten en las bases de datos principales o secundarias de un grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="c8912-106">RESTORE statements are not allowed on either the primary or secondary databases of an availability group.</span></span>  
  
  
  
##  <a name="backup-types-supported-on-secondary-replicas"></a><a name="SupportedBuTypes"></a><span data-ttu-id="c8912-107">Tipos de copia de seguridad admitidos en las réplicas secundarias</span><span class="sxs-lookup"><span data-stu-id="c8912-107">Backup Types Supported on Secondary Replicas</span></span>  
  
-   <span data-ttu-id="c8912-108">`BACKUP DATABASE` solo admite copias de seguridad completas de solo copia de bases de datos, archivos o grupos de archivos cuando se ejecuta en réplicas secundarias.</span><span class="sxs-lookup"><span data-stu-id="c8912-108">`BACKUP DATABASE` supports only copy-only full backups of databases, files, or filegroups when it is executed on secondary replicas.</span></span> <span data-ttu-id="c8912-109">Tenga en cuenta que las copias de seguridad de solo copia no afectan a la cadena de registros ni borran el mapa de bits diferencial.</span><span class="sxs-lookup"><span data-stu-id="c8912-109">Note that copy-only backups do not impact the log chain or clear the differential bitmap.</span></span>  
  
-   <span data-ttu-id="c8912-110">Las copias de seguridad diferenciales no se admiten en las réplicas secundarias.</span><span class="sxs-lookup"><span data-stu-id="c8912-110">Differential backups are not supported on secondary replicas.</span></span>  
  
-   <span data-ttu-id="c8912-111">**BACKUP LOG** solo admite copias de seguridad de registros periódicas (la opción COPY_ONLY no se admite para las copias de seguridad de registros en réplicas secundarias).</span><span class="sxs-lookup"><span data-stu-id="c8912-111">**BACKUP LOG** supports only regular log backups (the COPY_ONLY option is not supported for log backups on secondary replicas).</span></span>  
  
     <span data-ttu-id="c8912-112">Se garantiza una cadena de registro coherente entre las copias de seguridad de registros realizaron en cualquiera de las réplicas (principal o secundaria), con independencia de su modo de disponibilidad (confirmación sincrónica o asincrónica).</span><span class="sxs-lookup"><span data-stu-id="c8912-112">A consistent log chain is ensured across log backups taken on any of the replicas (primary or secondary), irrespective of their availability mode (synchronous-commit or asynchronous-commit).</span></span>  
  
-   <span data-ttu-id="c8912-113">Para realizar una copia de seguridad de una base de datos secundaria, una réplica secundaria debe poder comunicarse con la réplica principal y su estado debe ser `SYNCHRONIZED` o `SYNCHRONIZING`.</span><span class="sxs-lookup"><span data-stu-id="c8912-113">To back up a secondary database, a secondary replica must be able to communicate with the primary replica and must be `SYNCHRONIZED` or `SYNCHRONIZING`.</span></span>  
  
##  <a name="configuring-where-backup-jobs-run"></a><a name="WhereBuJobsRun"></a><span data-ttu-id="c8912-114">Configurar dónde se ejecutan los trabajos de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="c8912-114">Configuring Where Backup Jobs Run</span></span>  
 <span data-ttu-id="c8912-115">La realización de copias de seguridad en una réplica secundaria para descargar la carga de trabajo de copias de seguridad del servidor de producción principal es un gran ventaja.</span><span class="sxs-lookup"><span data-stu-id="c8912-115">Performing backups on a secondary replica to offload the backup workload from the primary production server is a great benefit.</span></span> <span data-ttu-id="c8912-116">Sin embargo, realizar copias de seguridad en réplicas secundarias agrega una gran complejidad al proceso de determinar dónde deben ejecutarse los trabajos de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c8912-116">However, performing backups on secondary replicas introduce significant complexity to the process of determining where backup jobs should run.</span></span> <span data-ttu-id="c8912-117">Para solucionar este problema, configure dónde se han de ejecutar los trabajos de copia de seguridad del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8912-117">To address this, configure where backup jobs run as follows:</span></span>  
  
1.  <span data-ttu-id="c8912-118">Configure el grupo de disponibilidad para que se especifiquen las réplicas de disponibilidad donde preferiría que se realizasen las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c8912-118">Configure the availability group to specify which availability replicas where you would prefer backups to be performed.</span></span> <span data-ttu-id="c8912-119">Para obtener más información, vea los parámetros *AUTOMATED_BACKUP_PREFERENCE* y *BACKUP_PRIORITY* en [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) o [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c8912-119">For more information, see *AUTOMATED_BACKUP_PREFERENCE* and *BACKUP_PRIORITY* parameters in [CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) or [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql).</span></span>  
  
2.  <span data-ttu-id="c8912-120">Cree los trabajos de copia de seguridad incluidos en script para cada base de datos de disponibilidad de cada instancia de servidor que hospeda una réplica de disponibilidad que es candidata para realizar copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c8912-120">Create scripted backup jobs for every availability database on every server instance that hosts an availability replica that is a candidate for performing backups.</span></span> <span data-ttu-id="c8912-121">Para obtener más información, vea la sección "Seguimiento: después de configurar la copia de seguridad en las réplicas secundarias" de [Configurar la copia de seguridad en réplicas de disponibilidad &#40;SQL Server&#41;](configure-backup-on-availability-replicas-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c8912-121">For more information, see the "Follow Up: After Configuring Backup on Secondary Replicas" section of [Configure Backup on Availability Replicas &#40;SQL Server&#41;](configure-backup-on-availability-replicas-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="c8912-122">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="c8912-122">Related Tasks</span></span>  
 <span data-ttu-id="c8912-123">**Para configurar la copia de seguridad en las réplicas secundarias**</span><span class="sxs-lookup"><span data-stu-id="c8912-123">**To configure backup on secondary replicas**</span></span>  
  
-   [<span data-ttu-id="c8912-124">Configurar la copia de seguridad en réplicas de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c8912-124">Configure Backup on Availability Replicas &#40;SQL Server&#41;</span></span>](configure-backup-on-availability-replicas-sql-server.md)  
  
 <span data-ttu-id="c8912-125">**Para determina sir la réplica actual es la réplica de copia de seguridad preferida**</span><span class="sxs-lookup"><span data-stu-id="c8912-125">**To determine whether the current replica is the preferred backup replica**</span></span>  
  
-   [<span data-ttu-id="c8912-126">sys.fn_hadr_backup_is_preferred_replica</span><span class="sxs-lookup"><span data-stu-id="c8912-126">sys.fn_hadr_backup_is_preferred_replica</span></span>](/sql/relational-databases/system-functions/sys-fn-hadr-backup-is-preferred-replica-transact-sql)  
  
 <span data-ttu-id="c8912-127">**Para crear un trabajo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="c8912-127">**To create a backup job**</span></span>  
  
-   [<span data-ttu-id="c8912-128">Usar el Asistente para planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="c8912-128">Use the Maintenance Plan Wizard</span></span>](../../../relational-databases/maintenance-plans/use-the-maintenance-plan-wizard.md)  
  
-   [<span data-ttu-id="c8912-129">Implementar trabajos</span><span class="sxs-lookup"><span data-stu-id="c8912-129">Implement Jobs</span></span>](../../../ssms/agent/implement-jobs.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="c8912-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c8912-130">See Also</span></span>  
 <span data-ttu-id="c8912-131">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c8912-131">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="c8912-132">[Copias de seguridad de solo copia &#40;SQL Server&#41;](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c8912-132">[Copy-Only Backups &#40;SQL Server&#41;](../../../relational-databases/backup-restore/copy-only-backups-sql-server.md) </span></span>  
 <span data-ttu-id="c8912-133">[CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c8912-133">[CREATE AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-availability-group-transact-sql) </span></span>  
 [<span data-ttu-id="c8912-134">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8912-134">ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-availability-group-transact-sql)  
  
  
