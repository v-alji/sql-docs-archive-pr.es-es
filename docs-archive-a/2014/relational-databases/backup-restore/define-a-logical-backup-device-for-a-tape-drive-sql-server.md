---
title: Definición de un dispositivo lógico de copia de seguridad en una unidad de cinta (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], defining
- backup devices [SQL Server], tapes
- backing up databases [SQL Server], tapes
- database backups [SQL Server], tapes
- tape backup devices, creating
ms.assetid: 66f36e1d-0287-4fac-8a51-71f9f0d7ad5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8728df2cc0b5907e51da84ed9e77d897a1718d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751233"
---
# <a name="define-a-logical-backup-device-for-a-tape-drive-sql-server"></a><span data-ttu-id="41fc6-102">Definir un dispositivo lógico de copia de seguridad en una unidad de cinta (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="41fc6-102">Define a Logical Backup Device for a Tape Drive (SQL Server)</span></span>
  <span data-ttu-id="41fc6-103">En este tema se describe cómo definir un dispositivo lógico de copia de seguridad para una unidad de cinta en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41fc6-103">This topic describes how to define a logical backup device for a tape drive in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="41fc6-104">Un dispositivo lógico es un nombre definido por el usuario que señala un dispositivo físico de copia de seguridad específico (un archivo de disco o unidad de cinta).</span><span class="sxs-lookup"><span data-stu-id="41fc6-104">A logical device is a user-defined name that points to a specific physical backup device (a disk file or tape drive).</span></span>  <span data-ttu-id="41fc6-105">La inicialización del dispositivo físico tiene lugar posteriormente, cuando se escribe una copia de seguridad en el dispositivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="41fc6-105">The initialization of the physical device occurs later, when a backup is written to the backup device.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="41fc6-106">La compatibilidad con dispositivos de cinta de copia de seguridad se quitará en una versión futura de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41fc6-106">Support for tape backup devices will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="41fc6-107">Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan.</span><span class="sxs-lookup"><span data-stu-id="41fc6-107">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="41fc6-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="41fc6-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="41fc6-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="41fc6-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="41fc6-110">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="41fc6-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="41fc6-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="41fc6-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="41fc6-112">**Para definir un dispositivo lógico de copia de seguridad en una unidad de cinta, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="41fc6-112">**To define a logical backup device for a tape drive, using:**</span></span>  
  
     [<span data-ttu-id="41fc6-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="41fc6-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="41fc6-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="41fc6-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="41fc6-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="41fc6-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="41fc6-116">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="41fc6-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="41fc6-117">La unidad o unidades de cinta deben ser compatibles con el sistema operativo Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="41fc6-117">The tape drive or drives must be supported by the Microsoft Windows operating system.</span></span>  
  
-   <span data-ttu-id="41fc6-118">El dispositivo de cinta debe estar conectado físicamente al equipo donde se ejecuta una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41fc6-118">The tape device must be connected physically to the computer that is running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="41fc6-119">No se admite la creación de copias de seguridad en dispositivos de cinta remotos.</span><span class="sxs-lookup"><span data-stu-id="41fc6-119">Backing up to remote tape devices is not supported.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="41fc6-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="41fc6-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="41fc6-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="41fc6-121">Permissions</span></span>  
 <span data-ttu-id="41fc6-122">Debe pertenecer al rol fijo de servidor **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="41fc6-122">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="41fc6-123">Requiere permiso para escribir en el disco.</span><span class="sxs-lookup"><span data-stu-id="41fc6-123">Requires permission to write to the disk.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="41fc6-124">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="41fc6-124">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="41fc6-125">Para definir un dispositivo lógico de copia de seguridad en una unidad de cinta</span><span class="sxs-lookup"><span data-stu-id="41fc6-125">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="41fc6-126">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="41fc6-126">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="41fc6-127">Expanda **Objetos de servidor**y, luego, haga clic con el botón derecho en **Dispositivos de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="41fc6-127">Expand **Server Objects**, and then right-click **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="41fc6-128">Haga clic en **Nuevo dispositivo de copia de seguridad**, que abre el cuadro de diálogo **Dispositivo de copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="41fc6-128">Click **New Backup Device**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="41fc6-129">Escriba un nombre para el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="41fc6-129">Enter a device name.</span></span>  
  
5.  <span data-ttu-id="41fc6-130">Para el destino, haga clic en **Cinta** y seleccione una unidad de cinta que aún no esté asociada a otro dispositivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="41fc6-130">For the destination, click **Tape** and select a tape drive that is not already associated with another backup device.</span></span> <span data-ttu-id="41fc6-131">Si no hay ninguna disponible, la opción **Cinta** está inactiva.</span><span class="sxs-lookup"><span data-stu-id="41fc6-131">If no such tape drives are available, the **Tape** option is inactive.</span></span>  
  
6.  <span data-ttu-id="41fc6-132">Para definir el nuevo dispositivo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41fc6-132">To define the new device, click **OK**.</span></span>  
  
 <span data-ttu-id="41fc6-133">Para realizar una copia de seguridad en este nuevo dispositivo, agréguelo en el campo **Copia de seguridad en:** del cuadro de diálogo **Copia de seguridad de base de datos** (**General**).</span><span class="sxs-lookup"><span data-stu-id="41fc6-133">To back up to this new device, add it to the **Back up to:** field in the **Back up Database** (**General**) dialog box.</span></span> <span data-ttu-id="41fc6-134">Para obtener más información, vea [Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="41fc6-134">For more information, see [Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="41fc6-135">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="41fc6-135">Using Transact-SQL</span></span>  
  
#### <a name="to-define-a-logical-backup-device-for-a-tape-drive"></a><span data-ttu-id="41fc6-136">Para definir un dispositivo lógico de copia de seguridad en una unidad de cinta</span><span class="sxs-lookup"><span data-stu-id="41fc6-136">To define a logical backup device for a tape drive</span></span>  
  
1.  <span data-ttu-id="41fc6-137">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41fc6-137">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="41fc6-138">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="41fc6-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="41fc6-139">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="41fc6-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="41fc6-140">En este ejemplo se muestra cómo usar [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) para definir un dispositivo lógico de copia de seguridad para una cinta.</span><span class="sxs-lookup"><span data-stu-id="41fc6-140">This example shows how to use [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) to define a logical backup device for a tape.</span></span> <span data-ttu-id="41fc6-141">En el ejemplo se agrega el dispositivo de copia de seguridad de cinta denominado `tapedump1`, con el nombre físico `\\.\tape0`.</span><span class="sxs-lookup"><span data-stu-id="41fc6-141">The example adds the tape backup device named `tapedump1`, with the physical name `\\.\tape0`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'tape', 'tapedump1', '\\.\tape0' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="41fc6-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41fc6-142">See Also</span></span>  
 <span data-ttu-id="41fc6-143">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41fc6-143">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="41fc6-144">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41fc6-144">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="41fc6-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41fc6-145">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 <span data-ttu-id="41fc6-146">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="41fc6-146">[sp_dropdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) </span></span>  
 <span data-ttu-id="41fc6-147">[Dispositivos de copia de seguridad &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="41fc6-147">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="41fc6-148">[Definir un dispositivo lógico de copia de seguridad para un archivo de disco &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="41fc6-148">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="41fc6-149">Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="41fc6-149">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
  
