---
title: Ver el contenido de una cinta o un archivo de copia de seguridad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- backup devices [SQL Server], tapes
- displaying backup content
- viewing backup content
- tape backup devices, viewing contents
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
ms.assetid: cd6674a2-ca55-4b5a-a971-878ba001821e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 044519b64d41fbbdfc9302ce24369ab282727f67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747047"
---
# <a name="view-the-contents-of-a-backup-tape-or-file-sql-server"></a><span data-ttu-id="fc467-102">Ver el contenido de una cinta o un archivo de copia de seguridad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fc467-102">View the Contents of a Backup Tape or File (SQL Server)</span></span>
  <span data-ttu-id="fc467-103">En este tema se describe cómo ver el contenido de un archivo o una cinta de copia de seguridad en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc467-103">This topic describes how to view the content of a backup tape or file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc467-104">La compatibilidad con dispositivos de cinta de copia de seguridad se quitará en una versión futura de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc467-104">Support for tape backup devices will be removed in a future version of SQL Server.</span></span> <span data-ttu-id="fc467-105">Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan.</span><span class="sxs-lookup"><span data-stu-id="fc467-105">Avoid using this feature in new development work, and plan to modify applications that currently use this feature.</span></span>  
  
 <span data-ttu-id="fc467-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="fc467-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="fc467-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="fc467-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="fc467-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fc467-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="fc467-109">**Para ver el contenido de una cinta o un archivo de copia de seguridad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="fc467-109">**To view the content of a backup tape or file, using:**</span></span>  
  
     [<span data-ttu-id="fc467-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fc467-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="fc467-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fc467-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="fc467-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="fc467-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="fc467-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fc467-113">Security</span></span>  
 <span data-ttu-id="fc467-114">Para obtener más información sobre seguridad, vea [RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fc467-114">For information about security, see [RESTORE HEADERONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-headeronly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="fc467-115">Permisos</span><span class="sxs-lookup"><span data-stu-id="fc467-115">Permissions</span></span>  
 <span data-ttu-id="fc467-116">En [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] y versiones posteriores, la obtención de información sobre un conjunto de copia de seguridad o un dispositivo de copia de seguridad requiere el permiso CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="fc467-116">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="fc467-117">Para obtener más información, vea [GRANT &#40;permisos de base de datos de Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fc467-117">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="fc467-118">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="fc467-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="fc467-119">Para ver el contenido de una cinta o un archivo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="fc467-119">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="fc467-120">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="fc467-120">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="fc467-121">Expanda **Bases de datos**y, en función de la base de datos, seleccione la base de datos de un usuario o expanda **Bases de datos del sistema** y seleccione una base de datos del sistema.</span><span class="sxs-lookup"><span data-stu-id="fc467-121">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="fc467-122">Haga clic con el botón derecho en la base de datos de la que quiera hacer una copia de seguridad, seleccione **Tareas**y haga clic en **Copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="fc467-122">Right-click the database you want to backup, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="fc467-123">Aparece el cuadro de diálogo **Copia de seguridad de base de datos** .</span><span class="sxs-lookup"><span data-stu-id="fc467-123">The **Back Up Database** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="fc467-124">En la sección **Destino** de la página **General** , haga clic en **Disco** o **Cinta**.</span><span class="sxs-lookup"><span data-stu-id="fc467-124">In the **Destination** section of the **General** page, click either **Disk** or **Tape**.</span></span> <span data-ttu-id="fc467-125">En el cuadro de lista **Copia de seguridad en** , busque el archivo de disco o la cinta que desea.</span><span class="sxs-lookup"><span data-stu-id="fc467-125">In the **Back up to** list box, look for the disk file or tape you want.</span></span>  
  
     <span data-ttu-id="fc467-126">Si el archivo de disco o la cinta no se muestra en el cuadro de lista, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fc467-126">If the disk file or tape is not displayed in the list-box, click **Add**.</span></span> <span data-ttu-id="fc467-127">Seleccione una unidad de cinta o un nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="fc467-127">Select a file name or tape drive.</span></span> <span data-ttu-id="fc467-128">Para agregarlo al cuadro de lista **Copia de seguridad en** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fc467-128">To add it to the **Back up to** list-box, click **OK**.</span></span>  
  
5.  <span data-ttu-id="fc467-129">En el cuadro de lista **Copia de seguridad en** , seleccione la ruta de acceso del disco o de la unidad de cinta que quiera ver y haga clic en **Contenido**.</span><span class="sxs-lookup"><span data-stu-id="fc467-129">In the **Back up to** list-box, select the path of the disk or tape drive you want to view, and click **Contents**.</span></span> <span data-ttu-id="fc467-130">De este modo se abre el cuadro de diálogo **Contenido del dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="fc467-130">This opens the **Device Contents** dialog box.</span></span>  
  
6.  <span data-ttu-id="fc467-131">En el panel derecho se muestra información sobre el conjunto de medios y los conjuntos de copia de seguridad de la cinta o del archivo seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fc467-131">The right-hand pane displays information about the media set and backup sets on the selected tape or file.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="fc467-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="fc467-132">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-content-of-a-backup-tape-or-file"></a><span data-ttu-id="fc467-133">Para ver el contenido de una cinta o un archivo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="fc467-133">To view the content of a backup tape or file</span></span>  
  
1.  <span data-ttu-id="fc467-134">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fc467-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fc467-135">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="fc467-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="fc467-136">Use la instrucción [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="fc467-136">Use the [RESTORE HEADERONLY](/sql/t-sql/statements/restore-statements-headeronly-transact-sql) statement.</span></span> <span data-ttu-id="fc467-137">En este ejemplo se devuelve información sobre el archivo denominado `AdventureWorks2012-FullBackup.bak`.</span><span class="sxs-lookup"><span data-stu-id="fc467-137">This example returns information about the file named `AdventureWorks2012-FullBackup.bak`.</span></span>  
  
```sql  
USE AdventureWorks2012;  
RESTORE HEADERONLY   
FROM DISK = N'C:\AdventureWorks2012-FullBackup.bak' ;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc467-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fc467-138">See Also</span></span>  
 <span data-ttu-id="fc467-139">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fc467-139">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="fc467-140">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fc467-140">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="fc467-141">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fc467-141">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="fc467-142">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fc467-142">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="fc467-143">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fc467-143">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="fc467-144">[Dispositivos de copia de seguridad &#40;SQL Server&#41;](backup-devices-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fc467-144">[Backup Devices &#40;SQL Server&#41;](backup-devices-sql-server.md) </span></span>  
 <span data-ttu-id="fc467-145">[Definir un dispositivo lógico de copia de seguridad para un archivo de disco &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fc467-145">[Define a Logical Backup Device for a Disk File &#40;SQL Server&#41;](define-a-logical-backup-device-for-a-disk-file-sql-server.md) </span></span>  
 [<span data-ttu-id="fc467-146">Definir un dispositivo lógico de copia de seguridad en una unidad de cinta &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fc467-146">Define a Logical Backup Device for a Tape Drive &#40;SQL Server&#41;</span></span>](define-a-logical-backup-device-for-a-tape-drive-sql-server.md)  
  
  
