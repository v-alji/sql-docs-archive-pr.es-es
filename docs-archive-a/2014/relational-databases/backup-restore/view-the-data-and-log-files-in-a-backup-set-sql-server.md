---
title: Ver los archivos de datos y de registro en un conjunto de copia de seguridad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- database backups [SQL Server], viewing backup sets
- viewing backup set information
- backup sets [SQL Server], viewing files in
- displaying backup set information
- transaction log backups [SQL Server], viewing backup sets
- backing up [SQL Server], viewing backup sets
ms.assetid: abb6420c-f809-426e-aeb4-d0a74989cf39
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7dbcb14a658b49aba6f5f2ebe3425a2ab5759efa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747046"
---
# <a name="view-the-data-and-log-files-in-a-backup-set-sql-server"></a><span data-ttu-id="668ae-102">Ver los archivos de datos y de registro en un conjunto de copia de seguridad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="668ae-102">View the Data and Log Files in a Backup Set (SQL Server)</span></span>
  <span data-ttu-id="668ae-103">En este tema se describe cómo ver los archivos de datos y de registro de una copia de seguridad en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="668ae-103">This topic describes how to view the data and log files in a backup set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="668ae-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="668ae-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="668ae-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="668ae-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="668ae-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="668ae-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="668ae-107">**Para ver los archivos de datos y de registro en un conjunto de copia de seguridad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="668ae-107">**To view the data and log files in a backup set, using:**</span></span>  
  
     [<span data-ttu-id="668ae-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="668ae-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="668ae-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="668ae-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="668ae-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="668ae-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="668ae-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="668ae-111">Security</span></span>  
 <span data-ttu-id="668ae-112">Para obtener más información sobre seguridad, vea [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="668ae-112">For information about security, see [RESTORE FILELISTONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql)</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="668ae-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="668ae-113">Permissions</span></span>  
 <span data-ttu-id="668ae-114">En [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] y versiones posteriores, la obtención de información sobre un conjunto de copia de seguridad o un dispositivo de copia de seguridad requiere el permiso CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="668ae-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="668ae-115">Para obtener más información, vea [GRANT &#40;permisos de base de datos de Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="668ae-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="668ae-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="668ae-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="668ae-117">Para ver los archivos de datos y de registro en un conjunto de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="668ae-117">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="668ae-118">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="668ae-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="668ae-119">Expanda **Bases de datos**y, en función de la base de datos, seleccione la base de datos de un usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="668ae-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="668ae-120">Haga clic con el botón derecho en la base de datos y haga clic en **Propiedades**, lo que abre el cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="668ae-120">Right-click the database, and then click **Properties**, which opens the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="668ae-121">En el panel **Seleccionar una página** , haga clic en **Archivos**.</span><span class="sxs-lookup"><span data-stu-id="668ae-121">In the **Select a Page** pane, click **Files**.</span></span>  
  
5.  <span data-ttu-id="668ae-122">En la cuadrícula **Archivos de la base de datos** , busque una lista de los archivos de datos y de registro, y sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="668ae-122">Look in the **Database files** grid for a list of the data and log files and their properties.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="668ae-123">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="668ae-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-data-and-log-files-in-a-backup-set"></a><span data-ttu-id="668ae-124">Para ver los archivos de datos y de registro en un conjunto de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="668ae-124">To view the data and log files in a backup set</span></span>  
  
1.  <span data-ttu-id="668ae-125">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="668ae-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="668ae-126">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="668ae-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="668ae-127">Use la instrucción [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="668ae-127">Use the [RESTORE FILELISTONLY](/sql/t-sql/statements/restore-statements-filelistonly-transact-sql) statement.</span></span> <span data-ttu-id="668ae-128">En este ejemplo se devuelve información acerca del segundo conjunto de copia de seguridad (`FILE=2`) del dispositivo de copia de seguridad de `AdventureWorksBackups` .</span><span class="sxs-lookup"><span data-stu-id="668ae-128">This example returns information about the second backup set (`FILE=2`) on the `AdventureWorksBackups` backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE FILELISTONLY FROM AdventureWorksBackups   
   WITH FILE=2;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="668ae-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="668ae-129">See Also</span></span>  
 <span data-ttu-id="668ae-130">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="668ae-130">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="668ae-131">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="668ae-131">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="668ae-132">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="668ae-132">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="668ae-133">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="668ae-133">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="668ae-134">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="668ae-134">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 [<span data-ttu-id="668ae-135">Dispositivos de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="668ae-135">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
