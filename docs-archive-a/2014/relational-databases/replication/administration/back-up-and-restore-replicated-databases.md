---
title: Hacer copias de seguridad y restaurar bases de datos replicadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- backups [SQL Server replication]
- administering replication, restoring
- backing up replicated databases
- backups [SQL Server replication], about backups
- restoring replicated databases [SQL Server replication]
- recovery [SQL Server replication], about recovery
- restoring databases [SQL Server], replicated databases
- backing up databases [SQL Server], replicated databases
- restoring [SQL Server replication], about restoring
- recovery [SQL Server replication]
- replication [SQL Server], administering
- distribution databases [SQL Server replication], backing up
- restoring [SQL Server replication]
- administering replication, backing up
ms.assetid: 04588807-21e7-4bbe-9727-b72f692cffa7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e91505bacf67f7f4628bd1b3f6b2cc78a6bc4c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673655"
---
# <a name="back-up-and-restore-replicated-databases"></a><span data-ttu-id="e4346-102">Hacer copias de seguridad y restaurar bases de datos replicadas</span><span class="sxs-lookup"><span data-stu-id="e4346-102">Back Up and Restore Replicated Databases</span></span>
  <span data-ttu-id="e4346-103">Las bases de datos replicadas requieren una atención especial en relación con la copia de seguridad y restauración de los datos.</span><span class="sxs-lookup"><span data-stu-id="e4346-103">Replicated databases require special attention with regards to backing up and restoring data.</span></span> <span data-ttu-id="e4346-104">En este tema se proporciona información preliminar y vínculos a información adicional sobre las estrategias para realizar copias de seguridad y restauración de cada tipo de replicación.</span><span class="sxs-lookup"><span data-stu-id="e4346-104">This topic provides introductory information and links to further information on backup and restore strategies for each type of replication.</span></span>  
  
 <span data-ttu-id="e4346-105">La replicación permite restaurar las bases de datos replicadas en el mismo servidor y base de datos de los que se creó la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e4346-105">Replication supports restoring replicated databases to the same server and database from which the backup was created.</span></span> <span data-ttu-id="e4346-106">Si restaura una copia de seguridad de una base de datos replicada en otro servidor o base de datos, no se conservará la configuración de la replicación.</span><span class="sxs-lookup"><span data-stu-id="e4346-106">If you restore a backup of a replicated database to another server or database, replication settings cannot be preserved.</span></span> <span data-ttu-id="e4346-107">En este caso, debe volver a crear todas las publicaciones y suscripciones después de restaurar las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e4346-107">In this case, you must recreate all publications and subscriptions after backups are restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4346-108">Es posible restaurar una base de datos replicada en un servidor en espera si se utiliza el trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="e4346-108">It is possible to restore a replicated database to a standby server if log shipping is being used.</span></span> <span data-ttu-id="e4346-109">Para obtener más información, vea [Trasvase de registros y replicación &#40;SQL Server&#41;](../../../database-engine/log-shipping/log-shipping-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e4346-109">For more information, see [Log Shipping and Replication &#40;SQL Server&#41;](../../../database-engine/log-shipping/log-shipping-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="e4346-110">La copia de seguridad de las bases de datos replicadas y las bases de datos del sistema asociadas debe realizarse con regularidad.</span><span class="sxs-lookup"><span data-stu-id="e4346-110">Replicated databases and their associated system databases should be backed up regularly.</span></span> <span data-ttu-id="e4346-111">Realice una copia de seguridad de las siguientes bases de datos:</span><span class="sxs-lookup"><span data-stu-id="e4346-111">Back up the following databases:</span></span>  
  
-   <span data-ttu-id="e4346-112">Base de datos de publicaciones en el publicador</span><span class="sxs-lookup"><span data-stu-id="e4346-112">The publication database at the Publisher</span></span>  
  
-   <span data-ttu-id="e4346-113">Base de datos de distribución en el distribuidor</span><span class="sxs-lookup"><span data-stu-id="e4346-113">The distribution database at the Distributor</span></span>  
  
-   <span data-ttu-id="e4346-114">Base de datos de suscripciones en el suscriptor</span><span class="sxs-lookup"><span data-stu-id="e4346-114">The subscription database at each Subscriber</span></span>  
  
-   <span data-ttu-id="e4346-115">Las bases de datos del sistema **maestra** y **msdb** en el publicador, el distribuidor y todos los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="e4346-115">The **master** and **msdb** system databases at the Publisher, Distributor and all Subscribers.</span></span> <span data-ttu-id="e4346-116">La copia de seguridad de cada una de estas bases de datos debe realizarse al mismo tiempo que la de las otras y la base de datos de replicación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e4346-116">These databases should be backed up at the same time as each other and the relevant replication database.</span></span> <span data-ttu-id="e4346-117">Por ejemplo, cree la copia de seguridad de las bases de datos **master** y **msdb** en el publicador al mismo tiempo que crea la copia de seguridad de la base de datos de publicaciones.</span><span class="sxs-lookup"><span data-stu-id="e4346-117">For example, back up the **master** and **msdb** databases at the Publisher at the same time you back up the publication database.</span></span> <span data-ttu-id="e4346-118">Al restaurar la base de datos de publicaciones, asegúrese de que las bases de datos **master** y **msdb** sean coherentes con la base de datos de publicaciones en términos de configuración general y configuración de la replicación.</span><span class="sxs-lookup"><span data-stu-id="e4346-118">If the publication database is restored, ensure that the **master** and **msdb** database are consistent with the publication database in terms of replication configuration and settings.</span></span>  
  
 <span data-ttu-id="e4346-119">Si realiza regularmente copias de seguridad de registros, éstas deben capturar todos los cambios relacionados con la replicación.</span><span class="sxs-lookup"><span data-stu-id="e4346-119">If you perform regular log backups, any replication-related changes should be captured in the log backups.</span></span> <span data-ttu-id="e4346-120">Si no se realizan copias de seguridad de registros, debe realizarse una copia de seguridad siempre que se cambie un valor importante en la replicación.</span><span class="sxs-lookup"><span data-stu-id="e4346-120">If you do not perform log backups, a backup should be performed whenever a setting relevant to replication is changed.</span></span> <span data-ttu-id="e4346-121">Para más información, vea [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span><span class="sxs-lookup"><span data-stu-id="e4346-121">For more information, see [Common Actions Requiring an Updated Backup](common-actions-requiring-an-updated-backup.md).</span></span>  
  
## <a name="backup-and-restore-strategies"></a><span data-ttu-id="e4346-122">Estrategias para realizar copias de seguridad y restauración</span><span class="sxs-lookup"><span data-stu-id="e4346-122">Backup and Restore Strategies</span></span>  
 <span data-ttu-id="e4346-123">Las estrategias de copia de seguridad y restauración de cada nodo en una topología de replicación difieren según el tipo de replicación utilizada.</span><span class="sxs-lookup"><span data-stu-id="e4346-123">The strategies for backing up and restoring each node in a replication topology differ according to the type of replication used.</span></span> <span data-ttu-id="e4346-124">Para obtener información sobre las estrategias para realizar copias de seguridad y restauración de cada tipo de replicación, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="e4346-124">For information on backup and restore strategies for each type of replication, see the following topics:</span></span>  
  
-   [<span data-ttu-id="e4346-125">Estrategias para hacer copias de seguridad y restaurar replicación de instantáneas o replicación transaccional</span><span class="sxs-lookup"><span data-stu-id="e4346-125">Strategies for Backing Up and Restoring Snapshot and Transactional Replication</span></span>](strategies-for-backing-up-and-restoring-snapshot-and-transactional-replication.md)  
  
-   [<span data-ttu-id="e4346-126">Estrategias para hacer copias de seguridad y restaurar la replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="e4346-126">Strategies for Backing Up and Restoring Merge Replication</span></span>](strategies-for-backing-up-and-restoring-merge-replication.md)  
  
 <span data-ttu-id="e4346-127">Como parte de cualquier estrategia de recuperación, mantenga siempre el script actual de la configuración de replicación en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="e4346-127">As part of any recovery strategy, always keep a current script of your replication settings in a safe location.</span></span> <span data-ttu-id="e4346-128">En el caso de un error en un servidor o de que sea necesario establecer un entorno de pruebas, puede modificar el script con solo cambiar las referencias al nombre del servidor y utilizarla para volver a crear la configuración de replicación.</span><span class="sxs-lookup"><span data-stu-id="e4346-128">In the event of server failure or the need to set up a test environment, you can modify the script by changing server name references, and it can be used to help recreate your replication settings.</span></span> <span data-ttu-id="e4346-129">Además de generar script para la configuración de replicación actual, debe generar script para habilitar y deshabilitar la replicación.</span><span class="sxs-lookup"><span data-stu-id="e4346-129">In addition to scripting your current replication settings, you should script the enabling and disabling of replication.</span></span> <span data-ttu-id="e4346-130">Para obtener información acerca del scripting para de objetos de replicación, vea [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="e4346-130">For information about scripting replication objects, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4346-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e4346-131">See Also</span></span>  
 <span data-ttu-id="e4346-132">[Realizar copias de seguridad y restaurar bases de datos de SQL Server](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="e4346-132">[Back Up and Restore of SQL Server Databases](../../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 [<span data-ttu-id="e4346-133">Best Practices for Replication Administration</span><span class="sxs-lookup"><span data-stu-id="e4346-133">Best Practices for Replication Administration</span></span>](best-practices-for-replication-administration.md)  
  
  
