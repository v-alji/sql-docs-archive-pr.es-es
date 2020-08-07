---
title: Restaurar una copia de seguridad desde un dispositivo (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restoring databases [SQL Server], device restores
- backup devices [SQL Server], restoring from
- database restores [SQL Server], device restores
- devices [SQL Server]
ms.assetid: 6e139de7-7de2-4d18-9df0-beac31ba7ff1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50d7f7b8e255aea470a1065df669c0cc3169a8dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745337"
---
# <a name="restore-a-backup-from-a-device-sql-server"></a><span data-ttu-id="9adfb-102">Restaurar una copia de seguridad desde un dispositivo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="9adfb-102">Restore a Backup from a Device (SQL Server)</span></span>
  <span data-ttu-id="9adfb-103">En este tema se describe cómo restaurar una copia de seguridad desde un dispositivo en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9adfb-103">This topic describes how to restore a backup from a device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9adfb-104">Para obtener información sobre SQL Server copia de seguridad en el servicio de almacenamiento de blobs de Azure, consulte [SQL Server Backup and restore with Azure BLOB Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span><span class="sxs-lookup"><span data-stu-id="9adfb-104">For information on SQL Server backup to the Azure Blob storage service, see, [SQL Server Backup and Restore with Azure Blob Storage Service](sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md).</span></span>  
  
 <span data-ttu-id="9adfb-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="9adfb-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9adfb-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="9adfb-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9adfb-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9adfb-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9adfb-108">**Para restaurar una copia de seguridad desde un dispositivo, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="9adfb-108">**To restore a backup from a device, using:**</span></span>  
  
     [<span data-ttu-id="9adfb-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9adfb-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9adfb-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9adfb-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9adfb-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9adfb-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9adfb-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9adfb-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9adfb-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="9adfb-113">Permissions</span></span>  
 <span data-ttu-id="9adfb-114">Si la base de datos que se va a restaurar no existe, el usuario debe tener permisos CREATE DATABASE para poder ejecutar RESTORE.</span><span class="sxs-lookup"><span data-stu-id="9adfb-114">If the database being restored does not exist, the user must have CREATE DATABASE permissions to be able to execute RESTORE.</span></span> <span data-ttu-id="9adfb-115">Si la base de datos existe, los permisos RESTORE corresponden de forma predeterminada a los miembros de los roles fijos de servidor **sysadmin** y **dbcreator** , y al propietario (**dbo**) de la base de datos (para la opción FROM DATABASE_SNAPSHOT, la base de datos siempre existe).</span><span class="sxs-lookup"><span data-stu-id="9adfb-115">If the database exists, RESTORE permissions default to members of the **sysadmin** and **dbcreator** fixed server roles and the owner (**dbo**) of the database (for the FROM DATABASE_SNAPSHOT option, the database always exists).</span></span>  
  
 <span data-ttu-id="9adfb-116">Los permisos RESTORE se conceden a los roles en los que la información acerca de la pertenencia está siempre disponible para el servidor.</span><span class="sxs-lookup"><span data-stu-id="9adfb-116">RESTORE permissions are given to roles in which membership information is always readily available to the server.</span></span> <span data-ttu-id="9adfb-117">Debido a que la pertenencia a un rol fijo de base de datos solo se puede comprobar cuando la base de datos es accesible y no está dañada, lo que no siempre ocurre cuando se ejecuta RESTORE, los miembros del rol fijo de base de datos **db_owner** no tienen permisos RESTORE.</span><span class="sxs-lookup"><span data-stu-id="9adfb-117">Because fixed database role membership can be checked only when the database is accessible and undamaged, which is not always the case when RESTORE is executed, members of the **db_owner** fixed database role do not have RESTORE permissions.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9adfb-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9adfb-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="9adfb-119">Para restaurar una copia de seguridad desde un dispositivo</span><span class="sxs-lookup"><span data-stu-id="9adfb-119">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="9adfb-120">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9adfb-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="9adfb-121">Expanda **Bases de datos**y, en función de la base de datos, seleccione la base de datos de un usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="9adfb-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="9adfb-122">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y, después, haga clic en **Restaurar**.</span><span class="sxs-lookup"><span data-stu-id="9adfb-122">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="9adfb-123">Haga clic en el tipo de operación de restauración que quiera (**Base de datos**, **Archivos y grupos de archivos**o **Registro de transacciones**).</span><span class="sxs-lookup"><span data-stu-id="9adfb-123">Click the type of restore operation you want (**Database**, **Files and Filegroups**, or **Transaction Log**).</span></span> <span data-ttu-id="9adfb-124">De este modo se abre el cuadro de diálogo de restauración correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9adfb-124">This opens the corresponding restore dialog box.</span></span>  
  
5.  <span data-ttu-id="9adfb-125">En la página **General** , en la sección **Origen de restauración** , haga clic en **Desde dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="9adfb-125">On the **General** page, in the **Restore source** section, click **From device**.</span></span>  
  
6.  <span data-ttu-id="9adfb-126">Haga clic en el botón Examinar del cuadro de texto **Desde dispositivo** , que abre el cuadro de diálogo **Especificar copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="9adfb-126">Click the browse button for the **From device** text box, which opens the **Specify Backup** dialog box.</span></span>  
  
7.  <span data-ttu-id="9adfb-127">En el cuadro de texto **Medio para copia de seguridad** , seleccione **Dispositivo de copia de seguridad**y haga clic en el botón **Agregar** para abrir el cuadro de diálogo **Seleccionar dispositivo de copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="9adfb-127">In the **Backup media** text box, select **Backup Device**, and click the **Add** button to open the **Select Backup Device** dialog box.</span></span>  
  
8.  <span data-ttu-id="9adfb-128">En el cuadro de texto **Dispositivo de copia de seguridad** , seleccione el dispositivo que desee usar para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="9adfb-128">In the **Backup device** text box, select the device you want to use for the restore operation.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9adfb-129">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9adfb-129">Using Transact-SQL</span></span>  
  
#### <a name="to-restore-a-backup-from-a-device"></a><span data-ttu-id="9adfb-130">Para restaurar una copia de seguridad desde un dispositivo</span><span class="sxs-lookup"><span data-stu-id="9adfb-130">To restore a backup from a device</span></span>  
  
1.  <span data-ttu-id="9adfb-131">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9adfb-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9adfb-132">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="9adfb-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9adfb-133">En la instrucción [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) , especifique el dispositivo de copia de seguridad físico o lógico que se va a utilizar para la operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9adfb-133">In the [RESTORE](/sql/t-sql/statements/restore-statements-transact-sql) statement, specify a logical or physical backup device to use for the backup operation.</span></span> <span data-ttu-id="9adfb-134">En este ejemplo se realiza una restauración desde un archivo de disco con el nombre físico `Z:\SQLServerBackups\AdventureWorks2012.bak`.</span><span class="sxs-lookup"><span data-stu-id="9adfb-134">This example restores from a disk file that has the physical name `Z:\SQLServerBackups\AdventureWorks2012.bak`.</span></span>  
  
```sql  
RESTORE DATABASE AdventureWorks2012  
   FROM DISK = 'Z:\SQLServerBackups\AdventureWorks2012.bak' ;  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="9adfb-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9adfb-135">See Also</span></span>  
 <span data-ttu-id="9adfb-136">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9adfb-136">[RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) </span></span>  
 <span data-ttu-id="9adfb-137">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9adfb-137">[RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) </span></span>  
 <span data-ttu-id="9adfb-138">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9adfb-138">[RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) </span></span>  
 <span data-ttu-id="9adfb-139">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9adfb-139">[RESTORE VERIFYONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-verifyonly-transact-sql) </span></span>  
 <span data-ttu-id="9adfb-140">[Restaurar una copia de seguridad de base de datos en el modelo de recuperación simple &#40;Transact-SQL&#41;](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="9adfb-140">[Restore a Database Backup Under the Simple Recovery Model &#40;Transact-SQL&#41;](restore-a-database-backup-under-the-simple-recovery-model-transact-sql.md) </span></span>  
 <span data-ttu-id="9adfb-141">[Restaurar una copia de seguridad de base de datos &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="9adfb-141">[Restore a Database Backup &#40;SQL Server Management Studio&#41;](restore-a-database-backup-using-ssms.md) </span></span>  
 <span data-ttu-id="9adfb-142">[Restaurar una copia de seguridad diferencial de la base de datos &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9adfb-142">[Restore a Differential Database Backup &#40;SQL Server&#41;](restore-a-differential-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="9adfb-143">[Restaurar una base de datos a una nueva ubicación &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9adfb-143">[Restore a Database to a New Location &#40;SQL Server&#41;](restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="9adfb-144">[Realizar copias de seguridad de archivos y grupos de archivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9adfb-144">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="9adfb-145">[Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9adfb-145">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="9adfb-146">Crear una copia de seguridad diferencial de una base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9adfb-146">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
