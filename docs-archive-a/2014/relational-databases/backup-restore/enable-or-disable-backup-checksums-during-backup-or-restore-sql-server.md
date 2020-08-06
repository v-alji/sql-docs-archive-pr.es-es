---
title: Habilitar o deshabilitar sumas de comprobación de copia de seguridad durante copia de seguridad o restauración (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup checksums [SQL Server]
- disabling checksums
- checksums [SQL Server]
ms.assetid: 6786bd1e-ad97-430a-8dfb-d4ba952d6c4d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a239dcdfca689be8555117104264d66a2ac037f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751230"
---
# <a name="enable-or-disable-backup-checksums-during-backup-or-restore-sql-server"></a><span data-ttu-id="0c056-102">Habilitar o deshabilitar sumas de comprobación de copia de seguridad durante copia de seguridad o restauración (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0c056-102">Enable or Disable Backup Checksums During Backup or Restore (SQL Server)</span></span>
  <span data-ttu-id="0c056-103">En este tema se describe cómo habilitar o deshabilitar sumas de comprobación de copia de seguridad cuando se realiza una copia de seguridad o se restaura una base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c056-103">This topic describes how to enable or disable backup checksums when you are backing up or restoring a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0c056-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="0c056-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0c056-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="0c056-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0c056-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0c056-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0c056-107">**Para habilitar o deshabilitar sumas de comprobación de copias de seguridad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="0c056-107">**To enable or disable backup checksums, using:**</span></span>  
  
     [<span data-ttu-id="0c056-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c056-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0c056-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0c056-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0c056-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="0c056-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0c056-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0c056-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0c056-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="0c056-112">Permissions</span></span>  
 <span data-ttu-id="0c056-113">BACKUP</span><span class="sxs-lookup"><span data-stu-id="0c056-113">BACKUP</span></span>  
 <span data-ttu-id="0c056-114">De forma predeterminada, los permisos BACKUP DATABASE y BACKUP LOG corresponden a los miembros del rol fijo de servidor **sysadmin** y de los roles fijos de base de datos **db_owner** y **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="0c056-114">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="0c056-115">Los problemas de propiedad y permisos del archivo físico del dispositivo de copia de seguridad pueden interferir con una operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0c056-115">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0c056-116">debe poder leer y escribir en el dispositivo y la cuenta en la que se ejecuta el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe tener permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="0c056-116">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="0c056-117">En cambio, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que agrega una entrada para un dispositivo de copia de seguridad en las tablas del sistema, no comprueba los permisos de acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="0c056-117">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="0c056-118">Es posible que estos problemas con el archivo físico del dispositivo de copia de seguridad no aparezcan hasta que se tenga acceso al recurso físico, al intentar la copia de seguridad o la restauración.</span><span class="sxs-lookup"><span data-stu-id="0c056-118">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
 <span data-ttu-id="0c056-119">RESTORE</span><span class="sxs-lookup"><span data-stu-id="0c056-119">RESTORE</span></span>  
 <span data-ttu-id="0c056-120">Si la base de datos que se va a restaurar no existe, el usuario debe tener permisos CREATE DATABASE para poder ejecutar RESTORE.</span><span class="sxs-lookup"><span data-stu-id="0c056-120">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="0c056-121">Si la base de datos existe, los permisos RESTORE corresponden de forma predeterminada a los miembros de los roles fijos de servidor **sysadmin** y **dbcreator** , y al propietario (**dbo**) de la base de datos (para la opción FROM DATABASE_SNAPSHOT, la base de datos siempre existe).</span><span class="sxs-lookup"><span data-stu-id="0c056-121">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="0c056-122">Los permisos RESTORE se conceden a los roles en los que la información acerca de la pertenencia está siempre disponible para el servidor.</span><span class="sxs-lookup"><span data-stu-id="0c056-122">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="0c056-123">Debido a que la pertenencia a un rol fijo de base de datos solo se puede comprobar cuando la base de datos es accesible y no está dañada, lo que no siempre ocurre cuando se ejecuta RESTORE, los miembros del rol fijo de base de datos **db_owner** no tienen permisos RESTORE.</span><span class="sxs-lookup"><span data-stu-id="0c056-123">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0c056-124">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c056-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-or-disable-checksums-during-a-backup-operation"></a><span data-ttu-id="0c056-125">Para habilitar o deshabilitar sumas de comprobación durante una operación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="0c056-125">To enable or disable checksums during a backup operation</span></span>  
  
1.  <span data-ttu-id="0c056-126">Siga los pasos para [crear una copia de seguridad de la base de datos](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0c056-126">Follow the steps to [create a database backup](create-a-full-database-backup-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="0c056-127">En la página **Opciones** , en la sección de **Confiabilidad** , haga clic en **Realizar suma de comprobación antes de escribir en los medios**.</span><span class="sxs-lookup"><span data-stu-id="0c056-127">On the **Options** page, in the **Reliability** section, click **Perform checksum before writing to media**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0c056-128">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0c056-128">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-backup-operation"></a><span data-ttu-id="0c056-129">Para habilitar o deshabilitar una suma de comprobación de copia de seguridad para una operación de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="0c056-129">To enable or disable backup checksum for a backup operation</span></span>  
  
1.  <span data-ttu-id="0c056-130">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c056-130">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0c056-131">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="0c056-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0c056-132">Para habilitar las sumas de comprobación de copia de seguridad en una instrucción [BACKUP](/sql/t-sql/statements/backup-transact-sql) , especifique la opción WITH CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="0c056-132">To enable backup checksums in a [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="0c056-133">Para deshabilitar sumas de comprobación de copia de seguridad, especifique la opción WITH NO_CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="0c056-133">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="0c056-134">Es el comportamiento predeterminado, salvo para una copia de seguridad comprimida.</span><span class="sxs-lookup"><span data-stu-id="0c056-134">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="0c056-135">En el siguiente ejemplo se especifica que se realicen sumas de comprobación.</span><span class="sxs-lookup"><span data-stu-id="0c056-135">The following example specifies that checksums be performed.</span></span>  
  
```sql  
BACKUP DATABASE AdventureWorks2012   
 TO DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
#### <a name="to-enable-or-disable-backup-checksum-for-a-restore-operation"></a><span data-ttu-id="0c056-136">Para habilitar o deshabilitar una suma de comprobación de copia de seguridad para una operación de restauración</span><span class="sxs-lookup"><span data-stu-id="0c056-136">To enable or disable backup checksum for a restore operation</span></span>  
  
1.  <span data-ttu-id="0c056-137">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c056-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0c056-138">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="0c056-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0c056-139">Para habilitar las sumas de comprobación de copia de seguridad en una instrucción [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , especifique la opción WITH CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="0c056-139">To enable backup checksums in a [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify the WITH CHECKSUM option.</span></span> <span data-ttu-id="0c056-140">Es el comportamiento predeterminado para una copia de seguridad comprimida.</span><span class="sxs-lookup"><span data-stu-id="0c056-140">This is the default behavior for a compressed backup.</span></span> <span data-ttu-id="0c056-141">Para deshabilitar sumas de comprobación de copia de seguridad, especifique la opción WITH NO_CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="0c056-141">To disable backup checksums, specify the WITH NO_CHECKSUM option.</span></span> <span data-ttu-id="0c056-142">Es el comportamiento predeterminado, salvo para una copia de seguridad comprimida.</span><span class="sxs-lookup"><span data-stu-id="0c056-142">This is the default behavior, except for a compressed backup.</span></span> <span data-ttu-id="0c056-143">En el siguiente ejemplo se especifica que se realicen sumas de comprobación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0c056-143">The following example specifies that backup checksums be performed.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012   
 FROM DISK = 'Z:\SQLServerBackups\AdvWorksData.bak'  
   WITH CHECKSUM;  
GO  
```  
  
> [!WARNING]  
>  <span data-ttu-id="0c056-144">Si solicita de forma explícita a CHECKSUM para una operación de restauración y la copia de seguridad contiene sumas de comprobación de copia de seguridad, se comprueban estas sumas y las sumas de comprobación de página, como en el caso predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0c056-144">If you explicitly request CHECKSUM for a restore operation and if the backup contains backup checksums, backup checksums and page checksums are both verified, as in the default case.</span></span> <span data-ttu-id="0c056-145">No obstante, si el conjunto de copia de seguridad no tiene sumas de comprobación de copia de seguridad, la operación de restauración da error con un mensaje que indica que no hay sumas de comprobación.</span><span class="sxs-lookup"><span data-stu-id="0c056-145">However, if the backup set lacks backup checksums, the restore operation fails with a message indicating that checksums are not present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c056-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c056-146">See Also</span></span>  
 <span data-ttu-id="0c056-147">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0c056-147">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="0c056-148">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0c056-148">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="0c056-149">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0c056-149">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="0c056-150">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0c056-150">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="0c056-151">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0c056-151">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="0c056-152">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0c056-152">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="0c056-153">[Argumentos RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0c056-153">[RESTORE Arguments &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-arguments-transact-sql) </span></span>  
 <span data-ttu-id="0c056-154">[Errores posibles de medios durante copia de seguridad y restauración &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0c056-154">[Possible Media Errors During Backup and Restore &#40;SQL Server&#41;](possible-media-errors-during-backup-and-restore-sql-server.md) </span></span>  
 [<span data-ttu-id="0c056-155">Especificar si una operación de copia de seguridad o restauración continúa o se detiene después de encontrar un error &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0c056-155">Specify Whether a Backup or Restore Operation Continues or Stops After Encountering an Error &#40;SQL Server&#41;</span></span>](specify-if-backup-or-restore-continues-or-stops-after-error.md)  
  
  
