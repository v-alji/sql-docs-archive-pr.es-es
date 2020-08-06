---
title: Restaurar la base de datos maestra (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- master database [SQL Server], restoring
ms.assetid: c83d802c-e84e-4458-b3ca-173d9ba32f73
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7c9cb078b7af60fc5e060bcb144fc9cbaee8ecf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675451"
---
# <a name="restore-the-master-database-transact-sql"></a><span data-ttu-id="b3144-102">Restaurar la base de datos maestra (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="b3144-102">Restore the master Database (Transact-SQL)</span></span>
  <span data-ttu-id="b3144-103">En este tema se explica cómo restaurar la base de datos **maestra** desde una copia de seguridad de base de datos completa.</span><span class="sxs-lookup"><span data-stu-id="b3144-103">This topic explains how to restore the **master** database from a full database backup.</span></span>  
  
### <a name="to-restore-the-master-database"></a><span data-ttu-id="b3144-104">Para restaurar la base de datos maestra</span><span class="sxs-lookup"><span data-stu-id="b3144-104">To restore the master database</span></span>  
  
1.  <span data-ttu-id="b3144-105">Inicie la instancia de servidor en modo de usuario único.</span><span class="sxs-lookup"><span data-stu-id="b3144-105">Start the server instance in single-user mode.</span></span>  
  
     <span data-ttu-id="b3144-106">Para obtener más información sobre cómo especificar el parámetro de inicio de usuario único ( **-m**), vea [Configurar opciones de inicio del servidor &#40;Administrador de configuración de SQL Server&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3144-106">For information about how to specify the single-user startup parameter (**-m**), see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
2.  <span data-ttu-id="b3144-107">Para restaurar una copia de seguridad de base de datos completa de **maestra**, use la siguiente instrucción [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="b3144-107">To restore a full database backup of **master**, use the following [RESTORE DATABASE](/sql/t-sql/statements/restore-statements-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="b3144-108">`RESTORE DATABASE master FROM`  *<backup_device>*  `WITH REPLACE`</span><span class="sxs-lookup"><span data-stu-id="b3144-108">`RESTORE DATABASE master FROM`  *<backup_device>*  `WITH REPLACE`</span></span>  
  
     <span data-ttu-id="b3144-109">La opción REPLACE indica a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que restaure la base de datos especificada incluso cuando ya exista otra con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="b3144-109">The REPLACE option instructs [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to restore the specified database even when a database of the same name already exists.</span></span> <span data-ttu-id="b3144-110">La base de datos existente, si existe, se elimina.</span><span class="sxs-lookup"><span data-stu-id="b3144-110">The existing database, if any, is deleted.</span></span> <span data-ttu-id="b3144-111">En el modo de usuario único, es recomendable introducir la instrucción RESTORE DATABASE en la [utilidad sqlcmd](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b3144-111">In single-user mode, we recommend that you enter the RESTORE DATABASE statement in the [sqlcmd utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="b3144-112">Para obtener más información, vea [Usar la utilidad sqlcmd](../scripting/sqlcmd-use-the-utility.md).</span><span class="sxs-lookup"><span data-stu-id="b3144-112">For more information, see [Use the sqlcmd Utility](../scripting/sqlcmd-use-the-utility.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b3144-113">Después de que la base de datos **maestra** se haya restaurado, la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se cierra y finaliza el proceso **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="b3144-113">After **master** is restored, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] shuts down and terminates the **sqlcmd** process.</span></span> <span data-ttu-id="b3144-114">Antes de reiniciar la instancia de servidor, quite el parámetro de inicio de usuario único.</span><span class="sxs-lookup"><span data-stu-id="b3144-114">Before you restart the server instance, remove the single-user startup parameter.</span></span> <span data-ttu-id="b3144-115">Para obtener más información, vea [Configurar opciones de inicio del servidor &#40;Administrador de configuración de SQL Server&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="b3144-115">For more information, see [Configure Server Startup Options &#40;SQL Server Configuration Manager&#41;](../../database-engine/configure-windows/scm-services-configure-server-startup-options.md).</span></span>  
  
3.  <span data-ttu-id="b3144-116">Reinicie la instancia del servidor y continúe con otros pasos de la recuperación, por ejemplo, restaurando otras bases de datos, adjuntando bases de datos y corrigiendo incoherencias de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b3144-116">Restart the server instance and continue other recovery steps such as restoring other databases, attaching databases, and correcting user mismatches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3144-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b3144-117">Example</span></span>  
 <span data-ttu-id="b3144-118">El ejemplo siguiente restaura la base de datos `master` en la instancia de servidor predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b3144-118">The following example restores the `master` database on the default server instance.</span></span> <span data-ttu-id="b3144-119">En el ejemplo se asume que la instancia de servidor ya se ejecuta en modo de usuario único.</span><span class="sxs-lookup"><span data-stu-id="b3144-119">The example assumes that the server instance is already running in single-user mode.</span></span> <span data-ttu-id="b3144-120">El ejemplo inicia `sqlcmd` y ejecuta una instrucción `RESTORE DATABASE` que restaura una copia de seguridad de base de datos completa de `master` desde un dispositivo de disco: `Z:\SQLServerBackups\master.bak`.</span><span class="sxs-lookup"><span data-stu-id="b3144-120">The example starts `sqlcmd` and executes a `RESTORE DATABASE` statement that restores a full database backup of `master` from a disk device: `Z:\SQLServerBackups\master.bak`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3144-121">En el caso de una instancia con nombre, el comando **sqlcmd** debe especificar la opción **-S** _\<ComputerName>_ \\ *\<InstanceName>* .</span><span class="sxs-lookup"><span data-stu-id="b3144-121">For a named instance, the **sqlcmd** command must specify the **-S**_\<ComputerName>_\\*\<InstanceName>* option.</span></span>  
  
```  
  
      C:\> sqlcmd  
1> RESTORE DATABASE master FROM DISK = 'Z:\SQLServerBackups\master.bak' WITH REPLACE;  
2> GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3144-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3144-122">See Also</span></span>  
 <span data-ttu-id="b3144-123">[Restauraciones de base de datos completas &#40;modelo de recuperación simple&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="b3144-123">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="b3144-124">[Restauraciones de base de datos completas &#40;modelo de recuperación completa&#41;](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="b3144-124">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="b3144-125">[Solucionar problemas de usuarios huérfanos &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b3144-125">[Troubleshoot Orphaned Users &#40;SQL Server&#41;](../../sql-server/failover-clusters/troubleshoot-orphaned-users-sql-server.md) </span></span>  
 <span data-ttu-id="b3144-126">[Adjuntar y separar bases de datos &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b3144-126">[Database Detach and Attach &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md) </span></span>  
 <span data-ttu-id="b3144-127">[Volver a generar bases de datos del sistema](../databases/system-databases.md) </span><span class="sxs-lookup"><span data-stu-id="b3144-127">[Rebuild System Databases](../databases/system-databases.md) </span></span>  
 <span data-ttu-id="b3144-128">[Opciones de inicio del servicio de motor de base de datos](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span><span class="sxs-lookup"><span data-stu-id="b3144-128">[Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) </span></span>  
 <span data-ttu-id="b3144-129">[Administrador de configuración de SQL Server](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b3144-129">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="b3144-130">[Realizar copias de seguridad y restaurar bases de datos del sistema &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b3144-130">[Back Up and Restore of System Databases &#40;SQL Server&#41;](back-up-and-restore-of-system-databases-sql-server.md) </span></span>  
 <span data-ttu-id="b3144-131">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b3144-131">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 [<span data-ttu-id="b3144-132">Iniciar SQL Server en modo de usuario único</span><span class="sxs-lookup"><span data-stu-id="b3144-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
