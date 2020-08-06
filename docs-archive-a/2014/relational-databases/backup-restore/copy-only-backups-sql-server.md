---
title: Copias de seguridad de solo copia (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- copy-only backups [SQL Server]
- COPY_ONLY option [BACKUP statement]
- backups [SQL Server], copy-only backups
ms.assetid: f82d6918-a5a7-4af8-868e-4247f5b00c52
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fc74d7b1bba2a0163ac9edefb5d465c54ef6296c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677706"
---
# <a name="copy-only-backups-sql-server"></a><span data-ttu-id="5253c-102">Copias de seguridad de solo copia (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5253c-102">Copy-Only Backups (SQL Server)</span></span>
  <span data-ttu-id="5253c-103">Una *copia de seguridad de solo copia* es una copia de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] independiente de la secuencia de copias de seguridad convencionales de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5253c-103">A *copy-only backup* is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup that is independent of the sequence of conventional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span> <span data-ttu-id="5253c-104">Normalmente, la realización de una copia de seguridad cambia la base de datos y afecta a la forma de restaurar las copias de seguridad posteriores.</span><span class="sxs-lookup"><span data-stu-id="5253c-104">Usually, taking a backup changes the database and affects how later backups are restored.</span></span> <span data-ttu-id="5253c-105">Sin embargo, a veces es útil realizar una copia de seguridad con un fin específico sin afectar a los procedimientos generales para copias de seguridad y restauración de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5253c-105">However, occasionally, it is useful to take a backup for a special purpose without affecting the overall backup and restore procedures for the database.</span></span> <span data-ttu-id="5253c-106">Las copias de seguridad de solo copia sirven para este propósito.</span><span class="sxs-lookup"><span data-stu-id="5253c-106">Copy-only backups serve this purpose.</span></span>  
  
 <span data-ttu-id="5253c-107">Los tipos de copias de seguridad de solo copia son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5253c-107">The types of copy-only backups are as follows:</span></span>  
  
-   <span data-ttu-id="5253c-108">Copias de seguridad completas de solo copia (todos los modelos de recuperación)</span><span class="sxs-lookup"><span data-stu-id="5253c-108">Copy-only full backups (all recovery models)</span></span>  
  
     <span data-ttu-id="5253c-109">Una copia de seguridad de solo copia no puede servir como base diferencial ni copia de seguridad diferencial y no afecta a la base diferencial.</span><span class="sxs-lookup"><span data-stu-id="5253c-109">A copy-only backup cannot serve as a differential base or differential backup and does not affect the differential base.</span></span>  
  
     <span data-ttu-id="5253c-110">El proceso de restauración de una copia de seguridad completa de solo copia es el mismo que la restauración de cualquier otra copia de seguridad completa.</span><span class="sxs-lookup"><span data-stu-id="5253c-110">Restoring a copy-only full backup is the same as restoring any other full backup.</span></span>  
  
-   <span data-ttu-id="5253c-111">Copias de seguridad de registros de solo copia (solo modelo de recuperación completa y modelo de recuperación optimizado para cargas masivas de registros)</span><span class="sxs-lookup"><span data-stu-id="5253c-111">Copy-only log backups (full recovery model and bulk-logged recovery model only)</span></span>  
  
     <span data-ttu-id="5253c-112">Una copia de seguridad de registros de solo copia mantiene el punto de archivo del registro existente y, por tanto, no afecta a la secuenciación de copias de seguridad de registros periódicas.</span><span class="sxs-lookup"><span data-stu-id="5253c-112">A copy-only log backup preserves the existing log archive point and, therefore, does not affect the sequencing of regular log backups.</span></span> <span data-ttu-id="5253c-113">Las copias de seguridad de registros de solo copia suelen ser innecesarias.</span><span class="sxs-lookup"><span data-stu-id="5253c-113">Copy-only log backups are typically unnecessary.</span></span> <span data-ttu-id="5253c-114">En lugar de ello, puede crear una nueva copia de seguridad de registros rutinaria (con WITH NORECOVERY) y utilizarla junto con las copias de seguridad de registros anteriores que sean necesarias para la secuencia de restauración.</span><span class="sxs-lookup"><span data-stu-id="5253c-114">Instead, you can create a new routine log backup (using WITH NORECOVERY) and use that backup together with any previous log backups that are required for the restore sequence.</span></span> <span data-ttu-id="5253c-115">Sin embargo, una copia de seguridad de registros de solo copia en ocasiones puede resultar útil para realizar una restauración en línea.</span><span class="sxs-lookup"><span data-stu-id="5253c-115">However, a copy-only log backup can sometimes be useful for performing an online restore.</span></span> <span data-ttu-id="5253c-116">Para obtener un ejemplo, vea [Ejemplo: Restauración con conexión de un archivo de lectura/escritura &#40;modelo de recuperación completa&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span><span class="sxs-lookup"><span data-stu-id="5253c-116">For an example of this, see [Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;](example-online-restore-of-a-read-write-file-full-recovery-model.md).</span></span>  
  
     <span data-ttu-id="5253c-117">El registro de transacciones nunca se trunca después de una copia de seguridad de solo copia.</span><span class="sxs-lookup"><span data-stu-id="5253c-117">The transaction log is never truncated after a copy-only backup.</span></span>  
  
 <span data-ttu-id="5253c-118">Las copias de seguridad de solo copia se registran en la columna **is_copy_only** de la tabla [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="5253c-118">Copy-only backups are recorded in the **is_copy_only** column of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) table.</span></span>  
  
## <a name="to-create-a-copy-only-backup"></a><span data-ttu-id="5253c-119">Para crear una copia de seguridad de solo copia</span><span class="sxs-lookup"><span data-stu-id="5253c-119">To Create a Copy-Only Backup</span></span>  
 <span data-ttu-id="5253c-120">Para crear una copia de seguridad de solo copia, utilice [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5253c-120">You can create a copy-only backup by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span>  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5253c-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5253c-121">Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="5253c-122">En la página **General** del cuadro de diálogo **Copia de seguridad de base de datos**, seleccione la opción **Copia de seguridad de solo copia**.</span><span class="sxs-lookup"><span data-stu-id="5253c-122">On the **General** page of the **Back Up Database** dialog box, select the **Copy Only Backup** option.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5253c-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5253c-123">Using Transact-SQL</span></span>  
 <span data-ttu-id="5253c-124">La sintaxis de [!INCLUDE[tsql](../../../includes/tsql-md.md)] necesaria es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5253c-124">The essential [!INCLUDE[tsql](../../../includes/tsql-md.md)] syntax is as follows:</span></span>  
  
-   <span data-ttu-id="5253c-125">Para una copia de seguridad completa de solo copia:</span><span class="sxs-lookup"><span data-stu-id="5253c-125">For a copy-only full backup:</span></span>  
  
     <span data-ttu-id="5253c-126">Copia de seguridad de la *database_name* de base de datos en \<backup_device*> \*... CON COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="5253c-126">BACKUP DATABASE *database_name* TO \<backup_device*>\* ... WITH COPY_ONLY ...</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="5253c-127">COPY_ONLY no tiene ningún efecto cuando se especifica con la opción DIFFERENTIAL.</span><span class="sxs-lookup"><span data-stu-id="5253c-127">COPY_ONLY has no effect when specified with the DIFFERENTIAL option.</span></span>  
  
-   <span data-ttu-id="5253c-128">Para una copia de seguridad de registros de solo copia:</span><span class="sxs-lookup"><span data-stu-id="5253c-128">For a copy-only log backup:</span></span>  
  
     <span data-ttu-id="5253c-129">*Database_name* del registro de copia de seguridad en *\<*backup_device*>* ... CON COPY_ONLY...</span><span class="sxs-lookup"><span data-stu-id="5253c-129">BACKUP LOG *database_name* TO *\<*backup_device*>* ... WITH COPY_ONLY ...</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="5253c-130">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="5253c-130">Using PowerShell</span></span>  
  
<span data-ttu-id="5253c-131">Utilice el cmdlet `Backup-SqlDatabase` con el parámetro `-CopyOnly`.</span><span class="sxs-lookup"><span data-stu-id="5253c-131">Use the `Backup-SqlDatabase` cmdlet with the `-CopyOnly` parameter.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="5253c-132">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="5253c-132">Related Tasks</span></span>  

### <a name="to-create-a-full-or-log-backup"></a><span data-ttu-id="5253c-133">Para crear una copia de seguridad completa o de registros</span><span class="sxs-lookup"><span data-stu-id="5253c-133">To create a full or log backup</span></span>
  
-   [<span data-ttu-id="5253c-134">Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5253c-134">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="5253c-135">Realizar una copia de seguridad de un registro de transacciones &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5253c-135">Back Up a Transaction Log &#40;SQL Server&#41;</span></span>](back-up-a-transaction-log-sql-server.md)  
  
### <a name="to-view-copy-only-backups"></a><span data-ttu-id="5253c-136">Para ver copias de seguridad de solo copia</span><span class="sxs-lookup"><span data-stu-id="5253c-136">To view copy-only backups</span></span>
  
-   [<span data-ttu-id="5253c-137">backupset &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5253c-137">backupset &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/backupset-transact-sql)  
  
### <a name="to-set-up-and-use-the-sql-server-powershell-provider"></a><span data-ttu-id="5253c-138">Para configurar y usar el proveedor de SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="5253c-138">To set up and use the SQL Server PowerShell provider</span></span>
  
-   [<span data-ttu-id="5253c-139">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="5253c-139">SQL Server PowerShell Provider</span></span>](../../powershell/sql-server-powershell-provider.md)  

## <a name="see-also"></a><span data-ttu-id="5253c-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5253c-140">See Also</span></span>  
 <span data-ttu-id="5253c-141">[Información general de copia de seguridad &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5253c-141">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 <span data-ttu-id="5253c-142">[Modelos de recuperación &#40;SQL Server&#41;](recovery-models-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="5253c-142">[Recovery Models &#40;SQL Server&#41;](recovery-models-sql-server.md) </span></span>  
 <span data-ttu-id="5253c-143">[Copiar bases de datos con Copias de seguridad y restauración](../databases/copy-databases-with-backup-and-restore.md) </span><span class="sxs-lookup"><span data-stu-id="5253c-143">[Copy Databases with Backup and Restore](../databases/copy-databases-with-backup-and-restore.md) </span></span>  
 [<span data-ttu-id="5253c-144">Información general sobre restauración y recuperación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5253c-144">Restore and Recovery Overview &#40;SQL Server&#41;</span></span>](restore-and-recovery-overview-sql-server.md)  
