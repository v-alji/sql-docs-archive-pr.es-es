---
title: Inicializar una suscripción transaccional a partir de una copia de seguridad (programación de la replicación con Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: d0637fc4-27cc-4046-98ea-dc86b7a3bd75
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1563d58f2d54f77680781e22a162112ade1658e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663344"
---
# <a name="initialize-a-transactional-subscription-from-a-backup-replication-transact-sql-programming"></a><span data-ttu-id="43c3f-102">Inicializar una suscripción transaccional desde una copia de seguridad (programación de la replicación con Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="43c3f-102">Initialize a Transactional Subscription from a Backup (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="43c3f-103">Aunque una suscripción a una publicación transaccional se inicializa normalmente con una instantánea, también se puede inicializar desde una copia de seguridad mediante procedimientos almacenados de replicación.</span><span class="sxs-lookup"><span data-stu-id="43c3f-103">Although a subscription to a transactional publication is typically initialized with a snapshot, a subscription can be initialized from a backup using replication stored procedures.</span></span> <span data-ttu-id="43c3f-104">Para obtener más información, consulte [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="43c3f-104">For more information, see [Initialize a Transactional Subscription Without a Snapshot](initialize-a-transactional-subscription-without-a-snapshot.md).</span></span>  
  
### <a name="to-initialize-a-transactional-subscriber-from-a-backup"></a><span data-ttu-id="43c3f-105">Para inicializar una suscripción transaccional desde una copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="43c3f-105">To initialize a transactional subscriber from a backup</span></span>  
  
1.  <span data-ttu-id="43c3f-106">En una publicación existente, asegúrese de que la publicación admite la capacidad de inicializarse desde la copia de seguridad ejecutando [sp_helppublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) en la base de datos de publicación del publicador.</span><span class="sxs-lookup"><span data-stu-id="43c3f-106">For an existing publication, ensure that the publication supports the ability to initialize from backup by executing [sp_helppublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helppublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="43c3f-107">Tenga en cuenta el valor de **allow_initialize_from_backup** en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="43c3f-107">Note the value of **allow_initialize_from_backup** in the result set.</span></span>  
  
    -   <span data-ttu-id="43c3f-108">Si el valor es **1**, la publicación admite esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="43c3f-108">If the value is **1**, the publication supports this functionality.</span></span>  
  
    -   <span data-ttu-id="43c3f-109">Si el valor es **0**, ejecute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) en el Publicador de la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="43c3f-109">If the value is **0**, execute [sp_changepublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-changepublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="43c3f-110">Especifique un valor de **allow_initialize_from_backup** para la \*\* \@ propiedad\*\* y un valor de `true` para \*\* \@ valor\*\*.</span><span class="sxs-lookup"><span data-stu-id="43c3f-110">Specify a value of **allow_initialize_from_backup** for **\@property** and a value of `true` for **\@value**.</span></span>  
  
2.  <span data-ttu-id="43c3f-111">Para una nueva publicación, ejecute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) en el Publicador de la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="43c3f-111">For a new publication, execute [sp_addpublication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpublication-transact-sql) at the Publisher on the publication database.</span></span> <span data-ttu-id="43c3f-112">Especifique un valor de `true` para **allow_initialize_from_backup**.</span><span class="sxs-lookup"><span data-stu-id="43c3f-112">Specify a value of `true` for **allow_initialize_from_backup**.</span></span> <span data-ttu-id="43c3f-113">Para obtener más información, vea [Crear una suscripción](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="43c3f-113">For more information, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="43c3f-114">Para evitar perder los datos del suscriptor, al utilizar **sp_addpublication** con `@allow_initialize_from_backup = N'true'`, utilice siempre `@immediate_sync = N'true'`.</span><span class="sxs-lookup"><span data-stu-id="43c3f-114">To avoid missing subscriber data, when using **sp_addpublication** with `@allow_initialize_from_backup = N'true'`, always use `@immediate_sync = N'true'`.</span></span>  
  
3.  <span data-ttu-id="43c3f-115">Cree una copia de seguridad de la base de datos de publicación con la instrucción [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="43c3f-115">Create a backup of the publication database using the [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
4.  <span data-ttu-id="43c3f-116">Restaure la copia de seguridad en el suscriptor con la instrucción [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="43c3f-116">Restore the backup on the Subscriber using the [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) statement.</span></span>  
  
5.  <span data-ttu-id="43c3f-117">En la base de datos de publicación del publicador, ejecute el procedimiento almacenado [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="43c3f-117">At the Publisher on the publication database, execute the stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span></span> <span data-ttu-id="43c3f-118">Especifique los parámetros siguientes:</span><span class="sxs-lookup"><span data-stu-id="43c3f-118">Specify the following parameters:</span></span>  
  
    -   <span data-ttu-id="43c3f-119">\*\* \@ sync_type\*\* -un valor de **Initialize with backup**.</span><span class="sxs-lookup"><span data-stu-id="43c3f-119">**\@sync_type** - a value of **initialize with backup**.</span></span>  
  
    -   <span data-ttu-id="43c3f-120">\*\* \@ backupdevicetype\*\* : el tipo de dispositivo de copia de seguridad: **Logical** (predeterminado), **Disk**o **Tape**.</span><span class="sxs-lookup"><span data-stu-id="43c3f-120">**\@backupdevicetype** - the type of backup device: **logical** (default), **disk**, or **tape**.</span></span>  
  
    -   <span data-ttu-id="43c3f-121">\*\* \@ backupdevicename\*\* : el dispositivo de copia de seguridad físico o lógico que se va a usar para la restauración.</span><span class="sxs-lookup"><span data-stu-id="43c3f-121">**\@backupdevicename** - the logical or physical backup device to use for the restore.</span></span>  
  
         <span data-ttu-id="43c3f-122">Para una unidad lógica, especifique el nombre del dispositivo de copia de seguridad especificado cuando se usó **sp_addumpdevice** para crear el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43c3f-122">For a logical device, specify the name of the backup device specified when **sp_addumpdevice** was used to create the device.</span></span>  
  
         <span data-ttu-id="43c3f-123">Para un dispositivo físico, especifique una ruta de acceso y un nombre de archivo completos, como `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` o `TAPE = '\\.\TAPE0'`.</span><span class="sxs-lookup"><span data-stu-id="43c3f-123">For a physical device, specify a complete path and file name, such as `DISK = 'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\BACKUP\Mybackup.dat'` or `TAPE = '\\.\TAPE0'`.</span></span>  
  
    -   <span data-ttu-id="43c3f-124">Opta \*\* \@ password\*\* : una contraseña que se proporcionó cuando se creó el conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="43c3f-124">(Optional) **\@password** - a password that was provided when the backup set was created.</span></span>  
  
    -   <span data-ttu-id="43c3f-125">Opta \*\* \@ MEDIAPASSWORD\*\* : una contraseña que se proporcionó cuando se dio formato al conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="43c3f-125">(Optional) **\@mediapassword** - a password that was provided when the media set was formatted.</span></span>  
  
    -   <span data-ttu-id="43c3f-126">Opta \*\* \@ fileidhint\*\* : identificador del conjunto de copia de seguridad que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="43c3f-126">(Optional) **\@fileidhint** - identifier for the backup set to be restored.</span></span> <span data-ttu-id="43c3f-127">Por ejemplo, **1** indica el primer conjunto de copia de seguridad del medio de copia de seguridad y **2** indica el segundo conjunto de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="43c3f-127">For example, specifying **1** indicates the first backup set on the backup medium and **2** indicates the second backup set.</span></span>  
  
    -   <span data-ttu-id="43c3f-128">(Opcional para los dispositivos de cinta) \*\* \@ Unload\*\* : especifique un valor de **1** (valor predeterminado) si la cinta debe descargarse de la unidad una vez completada la restauración y **0** si no debe descargarse.</span><span class="sxs-lookup"><span data-stu-id="43c3f-128">(Optional for tape devices) **\@unload** - specify a value of **1** (default) if the tape should be unloaded from the drive after the restore is complete and **0** if it should not be unloaded.</span></span>  
  
6.  <span data-ttu-id="43c3f-129">(Opcional) Para una suscripción de extracción, ejecute [sp_addpullsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) y [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) en el suscriptor de la base de datos de suscripción.</span><span class="sxs-lookup"><span data-stu-id="43c3f-129">(Optional) For a pull subscription, execute [sp_addpullsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-transact-sql) and [sp_addpullsubscription_agent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addpullsubscription-agent-transact-sql) at the Subscriber on the subscription database.</span></span> <span data-ttu-id="43c3f-130">Para obtener más información, consulte [Create a Pull Subscription](create-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="43c3f-130">For more information, see [Create a Pull Subscription](create-a-pull-subscription.md).</span></span>  
  
7.  <span data-ttu-id="43c3f-131">(Opcional) Inicio el Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="43c3f-131">(Optional) Start the Distribution Agent.</span></span> <span data-ttu-id="43c3f-132">Para obtener más información, consulte [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) o [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="43c3f-132">For more information, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md) or [Synchronize a Push Subscription](synchronize-a-push-subscription.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c3f-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43c3f-133">See Also</span></span>  
 <span data-ttu-id="43c3f-134">[Copiar bases de datos con Copias de seguridad y restauración](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="43c3f-134">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="43c3f-135">Copia de seguridad y restauración de bases de datos de SQL Server</span><span class="sxs-lookup"><span data-stu-id="43c3f-135">Back Up and Restore of SQL Server Databases</span></span>](../backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
  
