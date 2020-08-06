---
title: Establecer la fecha de expiración de una copia de seguridad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [SQL Server], expiration dates
- expiration [SQL Server]
- database backups [SQL Server], expiration dates
ms.assetid: 76e814df-6487-4893-9f09-7759f1863a5c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9185222df93e0a1150256535526ba910c593cf6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671104"
---
# <a name="set-the-expiration-date-on-a-backup-sql-server"></a><span data-ttu-id="92f47-102">Establecer la fecha de expiración de una copia de seguridad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="92f47-102">Set the Expiration Date on a Backup (SQL Server)</span></span>
  <span data-ttu-id="92f47-103">En este tema se describe cómo establecer la fecha de expiración de una copia de seguridad en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92f47-103">This topic describes how to set the expiration date on a backup in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="92f47-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="92f47-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="92f47-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="92f47-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="92f47-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="92f47-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="92f47-107">**Para establecer la fecha de expiración de una copia de seguridad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="92f47-107">**To set the expiration date on a backup, using:**</span></span>  
  
     [<span data-ttu-id="92f47-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92f47-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="92f47-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92f47-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="92f47-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="92f47-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="92f47-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="92f47-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="92f47-112">Permisos</span><span class="sxs-lookup"><span data-stu-id="92f47-112">Permissions</span></span>  
 <span data-ttu-id="92f47-113">De forma predeterminada, los permisos BACKUP DATABASE y BACKUP LOG corresponden a los miembros del rol fijo de servidor **sysadmin** y de los roles fijos de base de datos **db_owner** y **db_backupoperator** .</span><span class="sxs-lookup"><span data-stu-id="92f47-113">BACKUP DATABASE and BACKUP LOG permissions default to members of the **sysadmin** fixed server role and the **db_owner** and **db_backupoperator** fixed database roles.</span></span>  
  
 <span data-ttu-id="92f47-114">Los problemas de propiedad y permisos del archivo físico del dispositivo de copia de seguridad pueden interferir con una operación de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="92f47-114">Ownership and permission problems on the backup device's physical file can interfere with a backup operation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="92f47-115">debe poder leer y escribir en el dispositivo y la cuenta en la que se ejecuta el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe tener permisos de escritura.</span><span class="sxs-lookup"><span data-stu-id="92f47-115">must be able to read and write to the device; the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs must have write permissions.</span></span> <span data-ttu-id="92f47-116">En cambio, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), que agrega una entrada para un dispositivo de copia de seguridad en las tablas del sistema, no comprueba los permisos de acceso a los archivos.</span><span class="sxs-lookup"><span data-stu-id="92f47-116">However, [sp_addumpdevice](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql), which adds an entry for a backup device in the system tables, does not check file access permissions.</span></span> <span data-ttu-id="92f47-117">Es posible que estos problemas con el archivo físico del dispositivo de copia de seguridad no aparezcan hasta que se tenga acceso al recurso físico, al intentar la copia de seguridad o la restauración.</span><span class="sxs-lookup"><span data-stu-id="92f47-117">Such problems on the backup device's physical file may not appear until the physical resource is accessed when the backup or restore is attempted.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="92f47-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92f47-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="92f47-119">Para establecer la fecha de expiración de una copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="92f47-119">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="92f47-120">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="92f47-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="92f47-121">Expanda **Bases de datos**y, en función de la base de datos, seleccione la base de datos de un usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="92f47-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="92f47-122">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y haga clic en **Copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="92f47-122">Right-click the database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="92f47-123">Aparece el cuadro de diálogo **Copia de seguridad de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="92f47-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="92f47-124">En la página **General** , en **El conjunto de copia de seguridad expira**, especifique una fecha de expiración para indicar cuándo se puede sobrescribir el conjunto de copia de seguridad por otra copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="92f47-124">On the **General** page, for **Backup set will expire**, specify an expiration date to indicate when the backup set can be overwritten by another backup:</span></span>  
  
    -   <span data-ttu-id="92f47-125">Para que el conjunto de copia de seguridad expire al cabo de un número de días específico, haga clic en **Después de** (opción predeterminada) y escriba el número de días tras la creación del conjunto en que este expirará.</span><span class="sxs-lookup"><span data-stu-id="92f47-125">To have the backup set expire after a specific number of days, click **After** (the default option), and enter the number of days after set creation that the set will expire.</span></span> <span data-ttu-id="92f47-126">Este valor puede estar entre 0 y 99999 días; el valor 0 significa que el conjunto de copia de seguridad no expirará nunca.</span><span class="sxs-lookup"><span data-stu-id="92f47-126">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span>  
  
         <span data-ttu-id="92f47-127">El valor predeterminado se establece en la opción **Tiempo predeterminado de retención de medios de copia de seguridad (días)** del cuadro de diálogo **Propiedades del servidor** (página**Configuración de base de datos** ).</span><span class="sxs-lookup"><span data-stu-id="92f47-127">The default value is set in the **Default backup media retention (in days)** option of the **Server Properties** dialog box (**Database Settings** page).</span></span> <span data-ttu-id="92f47-128">Para acceder a esta opción, en el Explorador de objetos, haga clic con el botón derecho en el nombre del servidor y seleccione Propiedades; después, seleccione la página **Configuración de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="92f47-128">To access this, right-click the server name in Object Explorer and select properties; then select the **Database Settings** page.</span></span>  
  
    -   <span data-ttu-id="92f47-129">Para que el conjunto de copia de seguridad expire en una determinada fecha, haga clic en **El**y escriba la fecha en la que expirará.</span><span class="sxs-lookup"><span data-stu-id="92f47-129">To have the backup set expire on a specific date, click **On**, and enter the date on which the set will expire.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="92f47-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92f47-130">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-expiration-date-on-a-backup"></a><span data-ttu-id="92f47-131">Para establecer la fecha de expiración de una copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="92f47-131">To set the expiration date on a backup</span></span>  
  
1.  <span data-ttu-id="92f47-132">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92f47-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="92f47-133">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="92f47-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="92f47-134">En la instrucción [BACKUP](/sql/t-sql/statements/backup-transact-sql) , especifique la opción EXPIREDATE o RETAINDAYS para determinar cuándo [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] puede sobrescribir la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="92f47-134">In the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement, specify either the EXPIREDATE or RETAINDAYS option to determine when the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] can overwrite the backup.</span></span> <span data-ttu-id="92f47-135">Si no se especifica ninguna opción, la fecha de expiración se determina con el valor de configuración de servidor [media retention](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) .</span><span class="sxs-lookup"><span data-stu-id="92f47-135">If neither option is specified, the expiration date is determined by the [media retention](../../database-engine/configure-windows/configure-the-media-retention-server-configuration-option.md) server configuration setting.</span></span> <span data-ttu-id="92f47-136">En este ejemplo se utiliza la opción `EXPIREDATE` para especificar la fecha de expiración 30 de junio de 2015 (`6/30/2015`).</span><span class="sxs-lookup"><span data-stu-id="92f47-136">This example uses the `EXPIREDATE` option to specify an expiration date of June 30, 2015 (`6/30/2015`).</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
BACKUP DATABASE AdventureWorks2012  
 TO DISK = 'Z:\SQLServerBackups\AdventureWorks2012.Bak'  
   WITH EXPIREDATE = '6/30/2015' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="92f47-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92f47-137">See Also</span></span>  
 <span data-ttu-id="92f47-138">[Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="92f47-138">[Create a Full Database Backup &#40;SQL Server&#41;](create-a-full-database-backup-sql-server.md) </span></span>  
 <span data-ttu-id="92f47-139">[Realizar copias de seguridad de archivos y grupos de archivos &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="92f47-139">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 <span data-ttu-id="92f47-140">[Realizar copia de seguridad de un registro de transacciones &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="92f47-140">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 [<span data-ttu-id="92f47-141">Crear una copia de seguridad diferencial de una base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="92f47-141">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
  
