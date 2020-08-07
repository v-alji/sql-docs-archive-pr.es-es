---
title: Especificar un disco o una cinta como destino de copia de seguridad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
- backups [SQL Server], creating
- tape backup devices, backing up
ms.assetid: e391f452-ed8c-4b40-b846-ac3881271b94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a0f8ec5d9741e42f3b7d8eda8ebdba23622982d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745824"
---
# <a name="specify-a-disk-or-tape-as-a-backup-destination-sql-server"></a><span data-ttu-id="e1e35-102">Especificar un disco o una cinta como destino de copia de seguridad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e1e35-102">Specify a Disk or Tape As a Backup Destination (SQL Server)</span></span>
  <span data-ttu-id="e1e35-103">En este tema se describe cómo especificar un disco o una cinta como destino de la copia de seguridad en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1e35-103">This topic describes how to specify a disk or tape as a backup destination in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1e35-104">La compatibilidad con dispositivos de cinta de copia de seguridad se quitará en una versión futura de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e1e35-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="e1e35-105">Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan.</span><span class="sxs-lookup"><span data-stu-id="e1e35-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="e1e35-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="e1e35-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="e1e35-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="e1e35-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e1e35-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e1e35-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e1e35-109">**Para especificar un disco o una cinta como destino de copia de seguridad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="e1e35-109">**To specify a disk or tape as a backup destination, using:**</span></span>  
  
     [<span data-ttu-id="e1e35-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1e35-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="e1e35-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e1e35-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e1e35-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e1e35-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e1e35-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e1e35-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e1e35-114">Permisos</span><span class="sxs-lookup"><span data-stu-id="e1e35-114">Permissions</span></span>  
 <span data-ttu-id="e1e35-115">De forma predeterminada, los permisos BACKUP DATABASE y BACKUP LOG corresponden a los miembros del rol fijo de servidor **sysadmin** y de los roles fijos de base de datos **db_owner** y **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="e1e35-115">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="e1e35-116">Los problemas de propiedad y permisos del archivo físico del dispositivo de copia de seguridad pueden interferir con una operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e1e35-116">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e1e35-117">debe poder leer y escribir en el dispositivo y la cuenta en la que se ejecuta el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe tener permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="e1e35-117">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="e1e35-118">En cambio, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que agrega una entrada para un dispositivo de copia de seguridad en las tablas del sistema, no comprueba los permisos de acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="e1e35-118">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="e1e35-119">Es posible que estos problemas con el archivo físico del dispositivo de copia de seguridad no aparezcan hasta que se tenga acceso al recurso físico, al intentar la copia de seguridad o la restauración.</span><span class="sxs-lookup"><span data-stu-id="e1e35-119">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e1e35-120">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e1e35-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="e1e35-121">Para especificar un disco o una cinta como destino de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="e1e35-121">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="e1e35-122">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e1e35-122">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="e1e35-123">Expanda **Bases de datos**y, en función de la base de datos, seleccione la base de datos de un usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="e1e35-123">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="e1e35-124">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y haga clic en **Copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="e1e35-124">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="e1e35-125">Aparece el cuadro de diálogo **Copia de seguridad de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="e1e35-125">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="e1e35-126">En la sección **Destino** de la página **General** , haga clic en **Disco** o **Cinta**.</span><span class="sxs-lookup"><span data-stu-id="e1e35-126">In the **Destination** section of the **General** page, click **Disk** or **Tape**.</span></span> <span data-ttu-id="e1e35-127">Para seleccionar las rutas de acceso de hasta 64 unidades de disco o cinta que contienen un solo conjunto de medios, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e1e35-127">To select the paths of up to 64 disk or tape drives containing a single media set, click **Add**.</span></span>  
  
     <span data-ttu-id="e1e35-128">Para eliminar un destino de copia de seguridad, selecciónelo y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="e1e35-128">To remove a backup destination, select it and click **Remove**.</span></span> <span data-ttu-id="e1e35-129">Para ver el contenido de un destino de copia de seguridad, selecciónelo y haga clic en **Contenido**.</span><span class="sxs-lookup"><span data-stu-id="e1e35-129">To view the contents of a backup destination, select it and click **Contents**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e1e35-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e1e35-130">Using Transact-SQL</span></span>  
  
#### <a name="to-specify-a-disk-or-tape-as-a-backup-destination"></a><span data-ttu-id="e1e35-131">Para especificar un disco o una cinta como destino de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="e1e35-131">To specify a disk or tape as a backup destination</span></span>  
  
1.  <span data-ttu-id="e1e35-132">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1e35-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e1e35-133">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e1e35-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e1e35-134">En la instrucción [BACKUP](/sql/t-sql/statements/backup-transact-sql) , especifique el archivo o el dispositivo y su nombre físico.</span><span class="sxs-lookup"><span data-stu-id="e1e35-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify the file or device and its physical name.</span></span> <span data-ttu-id="e1e35-135">En este ejemplo se realiza una copia de seguridad de la base de datos `AdventureWorks2012` en el archivo de disco `Z:\SQLServerBackups\AdventureWorks2012.Bak`.</span><span class="sxs-lookup"><span data-stu-id="e1e35-135">This example backs up the `AdventureWorks2012` database to the disk file `Z:\SQLServerBackups\AdventureWorks2012.Bak`.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1e35-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e1e35-136">See Also</span></span>  
 <span data-ttu-id="e1e35-137">[Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e1e35-137">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="e1e35-138">[Realizar copias de seguridad de archivos y grupos de archivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e1e35-138">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="e1e35-139">[Definir un dispositivo lógico de copia de seguridad para un archivo de disco &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e1e35-139">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 <span data-ttu-id="e1e35-140">[Crear una copia de seguridad diferencial de una base de datos &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e1e35-140">[Create a Differential Database Backup &#40;SQL Server&#41;](create-a-differential-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="e1e35-141">Definir un dispositivo lógico de copia de seguridad en una unidad de cinta &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e1e35-141">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
