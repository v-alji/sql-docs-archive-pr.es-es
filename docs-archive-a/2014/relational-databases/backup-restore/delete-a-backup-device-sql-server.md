---
title: Eliminación de copia de seguridad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], deleting devices
- backup devices [SQL Server], deleting
- deleting backup devices
- removing backup devices
- backing up databases [SQL Server], backup devices
ms.assetid: 7be62480-ed6a-4262-a071-1feba73b1c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e8734e587a8ecde315fb17120511455a59e38901
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672132"
---
# <a name="delete-a-backup-device-sql-server"></a><span data-ttu-id="b608f-102">Eliminar un dispositivo de copia de seguridad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b608f-102">Delete a Backup Device (SQL Server)</span></span>
  <span data-ttu-id="b608f-103">En este tema se describe cómo eliminar un dispositivo de copia de seguridad en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b608f-103">This topic describes how to delete a backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="b608f-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="b608f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b608f-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="b608f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b608f-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b608f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b608f-107">**Para eliminar un dispositivo de copia de seguridad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="b608f-107">**To delete a backup device, using:**</span></span>  
  
     [<span data-ttu-id="b608f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b608f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b608f-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b608f-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b608f-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="b608f-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b608f-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="b608f-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b608f-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="b608f-112">Permissions</span></span>  
 <span data-ttu-id="b608f-113">Debe pertenecer al rol fijo de servidor **diskadmin** .</span><span class="sxs-lookup"><span data-stu-id="b608f-113">Requires membership in the **diskadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b608f-114">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b608f-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="b608f-115">Para eliminar un dispositivo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="b608f-115">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="b608f-116">Después de conectarse a la instancia apropiada de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="b608f-116">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="b608f-117">Expanda **Objetos de servidor**y, a continuación, **Dispositivos de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="b608f-117">Expand **Server Objects**, and then expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="b608f-118">Haga clic con el botón derecho en el dispositivo que quiera y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="b608f-118">Right-click the device you want, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="b608f-119">En el cuadro de diálogo **Eliminar objeto** , compruebe que aparezca el nombre del dispositivo correcto en la columna **Nombre de objeto** .</span><span class="sxs-lookup"><span data-stu-id="b608f-119">In the **Delete Object** dialog box, verify that the correct device name appears in the **Object Name** column.</span></span>  
  
5.  <span data-ttu-id="b608f-120">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="b608f-120">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b608f-121">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b608f-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-backup-device"></a><span data-ttu-id="b608f-122">Para eliminar un dispositivo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="b608f-122">To delete a backup device</span></span>  
  
1.  <span data-ttu-id="b608f-123">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b608f-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b608f-124">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="b608f-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b608f-125">Copie y pegue el ejemplo siguiente en la consulta.</span><span class="sxs-lookup"><span data-stu-id="b608f-125">Copy and paste the following example into the query.</span></span> <span data-ttu-id="b608f-126">En este ejemplo se muestra cómo usar [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) para eliminar un dispositivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b608f-126">This example shows how to use [sp_dropdevice](/sql/relational-databases/system-stored-procedures/sp-dropdevice-transact-sql) to delete a backup device.</span></span> <span data-ttu-id="b608f-127">Ejecute el primer ejemplo para crear el dispositivo de copia de seguridad `mybackupdisk` y el nombre físico `c:\backup\backup1.bak`.</span><span class="sxs-lookup"><span data-stu-id="b608f-127">Execute the first example to create the `mybackupdisk` backup device and the physical name `c:\backup\backup1.bak`.</span></span> <span data-ttu-id="b608f-128">Ejecute `sp_dropdevice` para eliminar el dispositivo de copia de seguridad `mybackupdisk`.</span><span class="sxs-lookup"><span data-stu-id="b608f-128">Execute `sp_dropdevice` to delete the `mybackupdisk` backup device.</span></span> <span data-ttu-id="b608f-129">El parámetro `delfile` elimina el nombre físico.</span><span class="sxs-lookup"><span data-stu-id="b608f-129">The `delfile` parameter deletes the physical name.</span></span>  
  
```sql  
--Define a backup device and physical name.   
USE AdventureWorks2012 ;  
GO  
EXEC sp_addumpdevice 'disk', 'mybackupdisk', 'c:\backup\backup1.bak' ;  
GO  
--Delete the backup device and the physical name.  
USE AdventureWorks2012 ;  
GO  
EXEC sp_dropdevice ' mybackupdisk ', 'delfile' ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="b608f-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b608f-130">See Also</span></span>  
 <span data-ttu-id="b608f-131">[Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b608f-131">[View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md) </span></span>  
 <span data-ttu-id="b608f-132">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b608f-132">[sys.backup_devices &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-backup-devices-transact-sql) </span></span>  
 <span data-ttu-id="b608f-133">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b608f-133">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="b608f-134">[Dispositivos de copia de seguridad &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b608f-134">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 [<span data-ttu-id="b608f-135">sp_addumpdevice &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b608f-135">sp_addumpdevice &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql)  
  
  