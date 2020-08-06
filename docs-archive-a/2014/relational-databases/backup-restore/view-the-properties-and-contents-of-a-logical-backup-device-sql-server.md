---
title: Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- displaying backup content
- viewing backup content
- database backups [SQL Server], viewing content
- backing up databases [SQL Server], viewing content
- backing up databases [SQL Server], properties
- displaying backup properties
- backup devices [SQL Server], viewing information
- viewing backup properties
- database backups [SQL Server], properties
ms.assetid: 3a309074-e816-454d-b6c3-fcfdde0cbf74
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f2bdf41e3dbda079e3627ff7a7c1c3c78103b728
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747040"
---
# <a name="view-the-properties-and-contents-of-a-logical-backup-device-sql-server"></a><span data-ttu-id="f1ab7-102">Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f1ab7-102">View the Properties and Contents of a Logical Backup Device (SQL Server)</span></span>
  <span data-ttu-id="f1ab7-103">En este tema se describe cómo ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1ab7-103">This topic describes how to view the properties and contents of a logical backup device in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="f1ab7-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f1ab7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f1ab7-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f1ab7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f1ab7-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f1ab7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f1ab7-107">**Para ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="f1ab7-107">**To view the properties and contents of a logical backup device, using:**</span></span>  
  
     [<span data-ttu-id="f1ab7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1ab7-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f1ab7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1ab7-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f1ab7-110">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f1ab7-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f1ab7-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f1ab7-111">Security</span></span>  
 <span data-ttu-id="f1ab7-112">Para obtener información sobre seguridad, vea [RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f1ab7-112">For information about security, see [RESTORE LABELONLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-labelonly-transact-sql).</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f1ab7-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="f1ab7-113">Permissions</span></span>  
 <span data-ttu-id="f1ab7-114">En [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] y versiones posteriores, la obtención de información sobre un conjunto de copia de seguridad o un dispositivo de copia de seguridad requiere el permiso CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="f1ab7-114">In [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions, obtaining information about a backup set or backup device requires CREATE DATABASE permission.</span></span> <span data-ttu-id="f1ab7-115">Para obtener más información, vea [GRANT &#40;permisos de base de datos de Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f1ab7-115">For more information, see [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f1ab7-116">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f1ab7-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="f1ab7-117">Para ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="f1ab7-117">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="f1ab7-118">Después de conectarse a la instancia apropiada de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f1ab7-118">After connecting to the appropriate instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="f1ab7-119">Expanda **Objetos de servidor**y expanda **Dispositivos de copia de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="f1ab7-119">Expand **Server Objects**, and expand **Backup Devices**.</span></span>  
  
3.  <span data-ttu-id="f1ab7-120">Haga clic en el dispositivo y, luego, con el botón derecho, haga clic en **Propiedades**para abrir el cuadro de diálogo **Dispositivo de copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="f1ab7-120">Click the device and right-click **Properties**, which opens the **Backup Device** dialog box.</span></span>  
  
4.  <span data-ttu-id="f1ab7-121">En la página **General** se muestra el nombre del dispositivo y el destino, que puede ser un dispositivo de cinta o la ruta de acceso de un archivo.</span><span class="sxs-lookup"><span data-stu-id="f1ab7-121">The **General** page displays the device name and destination, which is either a tape device or file path.</span></span>  
  
5.  <span data-ttu-id="f1ab7-122">En el panel **Seleccionar una página** , haga clic en **Contenido de los medios**.</span><span class="sxs-lookup"><span data-stu-id="f1ab7-122">In the **Select a Page** pane, click **Media Contents**.</span></span>  
  
6.  <span data-ttu-id="f1ab7-123">El panel de la derecha se muestra en los siguientes paneles de propiedades:</span><span class="sxs-lookup"><span data-stu-id="f1ab7-123">The right-hand pane displays in the following properties panels:</span></span>  
  
    -   <span data-ttu-id="f1ab7-124">**Elementos multimedia**</span><span class="sxs-lookup"><span data-stu-id="f1ab7-124">**Media**</span></span>  
  
         <span data-ttu-id="f1ab7-125">Información de secuencia del medio (número de secuencia del medio, número de secuencia de la familia e identificador del reflejo, si está presente) y la fecha y hora de creación del medio.</span><span class="sxs-lookup"><span data-stu-id="f1ab7-125">Media sequence information (the media sequence number, the family sequence number, and the mirror identifier, if any) and the media creation date and time.</span></span>  
  
    -   <span data-ttu-id="f1ab7-126">**Conjunto de medios**</span><span class="sxs-lookup"><span data-stu-id="f1ab7-126">**Media set**</span></span>  
  
         <span data-ttu-id="f1ab7-127">Información del conjunto de medios: nombre del conjunto de medios y su descripción, si está disponible, y el número de familias dentro del conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="f1ab7-127">Media set information: the media set name and description, if any, and the number of families in the media set.</span></span>  
  
7.  <span data-ttu-id="f1ab7-128">La cuadrícula **Conjuntos de copia de seguridad** muestra información sobre el contenido del conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="f1ab7-128">The **Backup sets** grid displays information about the contents of the media set.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1ab7-129">Para obtener más información, vea [Media Contents Page (Página Contenido de los medios)](backup-device-media-contents-page.md).</span><span class="sxs-lookup"><span data-stu-id="f1ab7-129">For more information, see [Media Contents Page](backup-device-media-contents-page.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f1ab7-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f1ab7-130">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-properties-and-contents-of-a-logical-backup-device"></a><span data-ttu-id="f1ab7-131">Para ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="f1ab7-131">To view the properties and contents of a logical backup device</span></span>  
  
1.  <span data-ttu-id="f1ab7-132">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1ab7-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f1ab7-133">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f1ab7-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f1ab7-134">Use la instrucción [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="f1ab7-134">Use the [RESTORE LABELONLY](/sql/t-sql/statements/restore-statements-labelonly-transact-sql) statement.</span></span> <span data-ttu-id="f1ab7-135">En este ejemplo se devuelve información acerca del dispositivo lógico de copia de seguridad `AdvWrks2008R2Backup` .</span><span class="sxs-lookup"><span data-stu-id="f1ab7-135">This example returns information about the `AdvWrks2008R2Backup` logical backup device.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
RESTORE LABELONLY  
   FROM AdvWrks2008R2Backup ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1ab7-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1ab7-136">See Also</span></span>  
 <span data-ttu-id="f1ab7-137">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f1ab7-137">[backupfilegroup &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfilegroup-transact-sql) </span></span>  
 <span data-ttu-id="f1ab7-138">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f1ab7-138">[backupfile &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupfile-transact-sql) </span></span>  
 <span data-ttu-id="f1ab7-139">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f1ab7-139">[backupset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupset-transact-sql) </span></span>  
 <span data-ttu-id="f1ab7-140">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f1ab7-140">[backupmediaset &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediaset-transact-sql) </span></span>  
 <span data-ttu-id="f1ab7-141">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f1ab7-141">[backupmediafamily &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/backupmediafamily-transact-sql) </span></span>  
 <span data-ttu-id="f1ab7-142">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f1ab7-142">[sp_addumpdevice &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addumpdevice-transact-sql) </span></span>  
 [<span data-ttu-id="f1ab7-143">Dispositivos de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f1ab7-143">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
