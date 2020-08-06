---
title: Definición de un dispositivo lógico de copia de seguridad para un archivo de disco (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], disks
- disk backup devices [SQL Server]
- database backups [SQL Server], disks
- backing up databases [SQL Server], disks
ms.assetid: 86331d43-c738-4523-ae3d-7d6700348ed1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8aa92296da81f984f260deace887c15f13443b95
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751238"
---
# <a name="define-a-logical-backup-device-for-a-disk-file-sql-server"></a><span data-ttu-id="51356-102">Definir un dispositivo lógico de copia de seguridad para un archivo de disco (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="51356-102">Define a Logical Backup Device for a Disk File (SQL Server)</span></span>
  <span data-ttu-id="51356-103">En este tema se describe cómo definir un dispositivo lógico de copia de seguridad para un archivo de disco en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51356-103">This topic describes how to define a logical backup device for a disk file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="51356-104">Un dispositivo lógico es un nombre definido por el usuario que señala un dispositivo físico de copia de seguridad específico (un archivo de disco o unidad de cinta).</span><span class="sxs-lookup"><span data-stu-id="51356-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="51356-105">La inicialización del dispositivo físico tiene lugar posteriormente, cuando se escribe una copia de seguridad en el dispositivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="51356-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
 <span data-ttu-id="51356-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="51356-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="51356-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="51356-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="51356-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="51356-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="51356-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="51356-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="51356-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="51356-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="51356-111">**Para definir un dispositivo lógico de copia de seguridad en un archivo de disco, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="51356-111">**To define a logical backup device for a disk file, using:**</span></span>  
  
     [<span data-ttu-id="51356-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="51356-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="51356-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="51356-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="51356-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="51356-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="51356-115">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="51356-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="51356-116">El nombre de dispositivo lógico debe ser único entre todos los dispositivos lógicos de copia de seguridad de la instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="51356-116">The logical device name must be unique among all the logical backup devices on the server instance.</span></span> <span data-ttu-id="51356-117">Para ver los nombres de los dispositivos lógicos existentes, consulte la vista de catálogo [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="51356-117">To view the existing logical device names, query the [sys.backup_devices](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) catalog view.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="51356-118">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="51356-118">Recommendations</span></span>  
  
-   <span data-ttu-id="51356-119">Se recomienda que el disco de copia de seguridad no sea el disco de datos o del registro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="51356-119">We recommend that a backup disk be a different disk than the database data and log disks.</span></span> <span data-ttu-id="51356-120">Esto es necesario para garantizar el acceso a las copias de seguridad si el disco de datos o del registro presenta errores.</span><span class="sxs-lookup"><span data-stu-id="51356-120">This is necessary to make sure that you can access the backups if the data or log disk fails.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="51356-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="51356-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="51356-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="51356-122">Permissions</span></span>  
 <span data-ttu-id="51356-123">Debe pertenecer al rol fijo de servidor **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="51356-123">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="51356-124">Requiere permiso para escribir en el disco.</span><span class="sxs-lookup"><span data-stu-id="51356-124">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="51356-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="51356-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-disk-file"></a><span data-ttu-id="51356-126">Para definir un dispositivo lógico de copia de seguridad en un archivo de disco</span><span class="sxs-lookup"><span data-stu-id="51356-126">To define a logical backup device for a disk file</span></span>  
  
1.  <span data-ttu-id="51356-127">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="51356-127">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="51356-128">Expanda **Objetos de servidor**y, después, haga clic con el botón derecho en **Dispositivos de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="51356-128">Expand **Server Objects**, and right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="51356-129">Haga clic en **Nuevo dispositivo de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="51356-129">Click **New Backup Device**.</span></span> <span data-ttu-id="51356-130">Se abrirá el cuadro de diálogo **Dispositivo de copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="51356-130">The **Backup Device** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="51356-131">Escriba un nombre para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="51356-131">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="51356-132">Para indicar el destino, haga clic en **Archivo** y especifique la ruta de acceso completa del archivo.</span><span class="sxs-lookup"><span data-stu-id="51356-132">For the destination, click **File** and specify the full path of the file.</span></span>  
  
6.  <span data-ttu-id="51356-133">Para definir el nuevo dispositivo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="51356-133">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="51356-134">Para realizar una copia de seguridad en este nuevo dispositivo, agréguelo en el campo **Copia de seguridad en:** del cuadro de diálogo **Copia de seguridad de base de datos** (**General**).</span><span class="sxs-lookup"><span data-stu-id="51356-134">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="51356-135">Para obtener más información, vea [Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="51356-135">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="51356-136">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="51356-136">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-for-a-disk-file"></a><span data-ttu-id="51356-137">Para definir un dispositivo lógico de copia de seguridad para un archivo de disco</span><span class="sxs-lookup"><span data-stu-id="51356-137">To define a logical backup for a disk file</span></span>  
  
1.  <span data-ttu-id="51356-138">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="51356-138">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="51356-139">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="51356-139">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="51356-140">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="51356-140">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="51356-141">En este ejemplo se muestra cómo usar [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) para definir un dispositivo lógico de copia de seguridad para un archivo de disco.</span><span class="sxs-lookup"><span data-stu-id="51356-141">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a disk file.</span></span> <span data-ttu-id="51356-142">El ejemplo agrega el dispositivo de copia de seguridad de disco denominado `mydiskdump`, con el nombre físico `c:\dump\dump1.bak`.</span><span class="sxs-lookup"><span data-stu-id="51356-142">The example adds the disk backup device named `mydiskdump`, with the physical name `c:\dump\dump1.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mydiskdump', 'c:\dump\dump1.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="51356-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="51356-143">See Also</span></span>  
 <span data-ttu-id="51356-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="51356-144">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="51356-145">[Dispositivos de copia de seguridad &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="51356-145">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="51356-146">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="51356-146">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="51356-147">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="51356-147">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="51356-148">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="51356-148">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="51356-149">[Definir un dispositivo lógico de copia de seguridad en una unidad de cinta &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="51356-149">[Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-tape-drive-sql-server.md) </span></span>  
 [<span data-ttu-id="51356-150">Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="51356-150">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
