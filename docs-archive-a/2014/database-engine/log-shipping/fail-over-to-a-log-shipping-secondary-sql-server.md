---
title: Conmutar por error a una base de datos secundaria de trasvase de registros (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- primary databases [SQL Server]
- secondary data files [SQL Server], manual fail over
- log shipping [SQL Server], failover
- failover [SQL Server], log shipping
ms.assetid: edfe5d59-4287-49c1-96c9-dd56212027bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 164e2809e4eff5a14ef54124df7c7ca9077793ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747167"
---
# <a name="fail-over-to-a-log-shipping-secondary-sql-server"></a><span data-ttu-id="cf988-102">Conmutar por error a una base de datos secundaria de trasvase de registros (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cf988-102">Fail Over to a Log Shipping Secondary (SQL Server)</span></span>
  <span data-ttu-id="cf988-103">La conmutación por error a una base de datos secundaria de trasvase de registros es útil si la instancia del servidor principal produce un error o requiere mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="cf988-103">Failing over to a log shipping secondary is useful if the primary server instance fails or requires maintenance.</span></span>  
  
## <a name="preparing-for-a-controlled-failover"></a><span data-ttu-id="cf988-104">Preparación para una conmutación por error controlada</span><span class="sxs-lookup"><span data-stu-id="cf988-104">Preparing for a Controlled Failover</span></span>  
 <span data-ttu-id="cf988-105">Las bases de datos principal y secundaria no suelen estar sincronizadas, ya que la base de datos principal continúa actualizándose después del último trabajo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="cf988-105">Typically, the primary and secondary databases are unsynchronized, because the primary database continues to be updated after its latest backup job.</span></span> <span data-ttu-id="cf988-106">Además, en algunos casos, es posible que las copias de seguridad recientes del registro de transacciones no se hayan copiado en las instancias del servidor secundario, o bien que algunas copias de seguridad de registros copiadas aún no se hayan aplicado a la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="cf988-106">Also, in some cases, recent transaction log backups have not been copied to the secondary server instances, or some copied log backups might still not have been applied to the secondary database.</span></span> <span data-ttu-id="cf988-107">Si es posible, se recomienda comenzar por la sincronización de todas las bases de datos secundarias con la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="cf988-107">We recommend that you begin by synchronizing all of the secondary databases with the primary database, if possible.</span></span>  
  
 <span data-ttu-id="cf988-108">Para obtener más información sobre los trabajos de trasvase de registros, vea [Acerca del trasvase de registros &#40;SQL Server&#41;](about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cf988-108">For information about log shipping jobs, see [About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md).</span></span>  
  
## <a name="failing-over"></a><span data-ttu-id="cf988-109">Realizar una conmutación por error</span><span class="sxs-lookup"><span data-stu-id="cf988-109">Failing Over</span></span>  
 <span data-ttu-id="cf988-110">Para realizar una conmutación por error a una base de datos secundaria:</span><span class="sxs-lookup"><span data-stu-id="cf988-110">To fail over to a secondary database:</span></span>  
  
1.  <span data-ttu-id="cf988-111">Copie los archivos de copia de seguridad que aún no se hayan copiado del recurso compartido de copia de seguridad en la carpeta de destino de la copia de cada servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="cf988-111">Copy any uncopied backup files from the backup share to the copy destination folder of each secondary server.</span></span>  
  
2.  <span data-ttu-id="cf988-112">Aplique, por orden, las copias de seguridad del registro de transacciones que aún no se hayan aplicado a las bases de datos secundarias.</span><span class="sxs-lookup"><span data-stu-id="cf988-112">Apply any unapplied transaction log backups in sequence to each secondary database.</span></span> <span data-ttu-id="cf988-113">Para obtener más información, vea [Aplicar copias de seguridad del registro de transacciones &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cf988-113">For more information, see [Apply Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md).</span></span>  
  
3.  <span data-ttu-id="cf988-114">Si se puede tener acceso a la base de datos principal, realice una copia de seguridad del registro de transacciones activo y aplíquela a las bases de datos secundarias.</span><span class="sxs-lookup"><span data-stu-id="cf988-114">If the primary database is accessible, back up the active transaction log and apply the log backup to the secondary databases.</span></span>  
  
     <span data-ttu-id="cf988-115">Si la instancia del servidor principal original no está dañada, realice una copia de seguridad del final del registro de transacciones de la base de datos principal mediante WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="cf988-115">If the original primary server instance is not damaged, back up the tail of the transaction log of the primary database using WITH NORECOVERY.</span></span> <span data-ttu-id="cf988-116">Esto deja la base de datos en estado restauración y, por consiguiente, no disponible a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="cf988-116">This leaves the database in the restoring state and therefore unavailable to users.</span></span> <span data-ttu-id="cf988-117">Finalmente, podrá poner al día esta base de datos mediante la aplicación de copias de seguridad del registro de transacciones desde la base de datos principal de sustitución.</span><span class="sxs-lookup"><span data-stu-id="cf988-117">Eventually you will be able to roll this database forward by applying transaction log backups from the replacement primary database.</span></span>  
  
     <span data-ttu-id="cf988-118">Para obtener más información, vea [Copias de seguridad del registro de transacciones &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cf988-118">For more information, see [Transaction Log Backups &#40;SQL Server&#41;](../../relational-databases/backup-restore/transaction-log-backups-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="cf988-119">Una vez sincronizados los servidores secundarios, podrá realizar una conmutación por error al servidor que prefiera mediante la recuperación de su base de datos secundaria y la redirección de los clientes a dicha instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="cf988-119">After the secondary servers are synchronized, you can fail over to whichever one you prefer by recovering its secondary database and redirecting clients to that server instance.</span></span> <span data-ttu-id="cf988-120">La recuperación coloca a la base de datos en un estado coherente y en línea.</span><span class="sxs-lookup"><span data-stu-id="cf988-120">Recovering puts the database into a consistent state and brings it online.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="cf988-121">Cuando haga que una base de datos secundaria esté disponible, debe asegurarse de que sus metadatos sean coherentes con los metadatos de la base de datos principal original.</span><span class="sxs-lookup"><span data-stu-id="cf988-121">When you make a secondary database available, you should ensure that its metadata is consistent with the metadata of the original primary database.</span></span> <span data-ttu-id="cf988-122">Para obtener más información, vea [Administrar los metadatos cuando una base de datos pasa a estar disponible en otra instancia del servidor &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="cf988-122">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span>  
  
5.  <span data-ttu-id="cf988-123">Una vez que haya recuperado una base de datos secundaria, puede configurarla de nuevo para que actúe como base de datos principal para otras bases de datos secundarias.</span><span class="sxs-lookup"><span data-stu-id="cf988-123">After you have recovered a secondary database, you can reconfigure it to act as a primary database for other secondary databases.</span></span>  
  
     <span data-ttu-id="cf988-124">Si no hay ninguna otra base de datos secundaria disponible, vea [Configurar el trasvase de registros &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="cf988-124">If no other secondary database is available, see [Configure Log Shipping &#40;SQL Server&#41;](configure-log-shipping-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="cf988-125">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="cf988-125">Related Tasks</span></span>  
  
-   [<span data-ttu-id="cf988-126">Cambiar los roles entre el servidor de trasvase de registros primario y secundario &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cf988-126">Change Roles Between Primary and Secondary Log Shipping Servers &#40;SQL Server&#41;</span></span>](change-roles-between-primary-and-secondary-log-shipping-servers-sql-server.md)  
  
-   [<span data-ttu-id="cf988-127">Administración de inicios de sesión y trabajos tras la conmutación de roles &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cf988-127">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="cf988-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf988-128">See Also</span></span>  
 <span data-ttu-id="cf988-129">[Tablas y procedimientos almacenados de trasvase de registros](log-shipping-tables-and-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="cf988-129">[Log Shipping Tables and Stored Procedures](log-shipping-tables-and-stored-procedures.md) </span></span>  
 <span data-ttu-id="cf988-130">[Acerca del trasvase de registros &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cf988-130">[About Log Shipping &#40;SQL Server&#41;](about-log-shipping-sql-server.md) </span></span>  
 [<span data-ttu-id="cf988-131">Copias del final del registro &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="cf988-131">Tail-Log Backups &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/tail-log-backups-sql-server.md)  
  
  
