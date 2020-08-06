---
title: Realizar copias de seguridad y restaurar los índices y catálogos de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], backing up
- full-text search [SQL Server], back up and restore
- recovery [full-text search]
- backups [SQL Server], full-text indexes
- full-text indexes [SQL Server], restoring
- restore operations [full-text search]
ms.assetid: 6a4080d9-e43f-4b7b-a1da-bebf654c1194
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c0df49c03325da375427c6566799f374fcc9dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676440"
---
# <a name="back-up-and-restore-full-text-catalogs-and-indexes"></a><span data-ttu-id="f66fe-102">Realizar copias de seguridad de los catálogos de texto completo y restaurarlos</span><span class="sxs-lookup"><span data-stu-id="f66fe-102">Back Up and Restore Full-Text Catalogs and Indexes</span></span>
  <span data-ttu-id="f66fe-103">En este tema se explica cómo hacer una copia de seguridad y restaurar los índices de texto completo creados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f66fe-103">This topic explains how to back up and restore full-text indexes created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f66fe-104">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el catálogo de texto completo es un concepto lógico y no reside en un grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="f66fe-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the full-text catalog is a logical concept and does not reside in a filegroup.</span></span> <span data-ttu-id="f66fe-105">Por consiguiente, para hacer una copia de seguridad de un catálogo de texto completo en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], debe identificar cada grupo de archivos que contenga un índice de texto completo que pertenezca al catálogo.</span><span class="sxs-lookup"><span data-stu-id="f66fe-105">Therefore, to back up a full-text catalog in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must identify every filegroup that contains a full-text index that belongs to the catalog.</span></span> <span data-ttu-id="f66fe-106">A continuación, debe hacer copia de seguridad de cada uno de estos grupos de archivos, uno por uno.</span><span class="sxs-lookup"><span data-stu-id="f66fe-106">Then you must back up those filegroups, one by one.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f66fe-107">Se pueden importar los catálogos de texto completo al actualizar una base de datos de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f66fe-107">It is possible to import full-text catalogs when upgrading a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database.</span></span> <span data-ttu-id="f66fe-108">Cada catálogo de texto completo importado es un archivo de base de datos en su propio grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="f66fe-108">Each imported full-text catalog is a database file in its own filegroup.</span></span> <span data-ttu-id="f66fe-109">Para hacer una copia de seguridad de un catálogo importado, basta con hacer una copia de seguridad de su grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="f66fe-109">To back up an imported catalog, simply back up its filegroup.</span></span> <span data-ttu-id="f66fe-110">Para obtener más información, vea [Realizar copias de seguridad y restaurar catálogos de texto completo](https://go.microsoft.com/fwlink/?LinkID=121052), en los Libros en pantalla de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f66fe-110">For more information, see [Backing Up and Restoring Full-Text Catalogs](https://go.microsoft.com/fwlink/?LinkID=121052), in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Books Online.</span></span>  
  
##  <a name="backing-up-the-full-text-indexes-of-a-full-text-catalog"></a><a name="backingup"></a> <span data-ttu-id="f66fe-111">Hacer la copia de seguridad de los índices de texto completo de un catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="f66fe-111">Backing Up the Full-Text Indexes of a Full-Text Catalog</span></span>  
  
###  <a name="finding-the-full-text-indexes-of-a-full-text-catalog"></a><a name="Find_FTIs_of_a_Catalog"></a> <span data-ttu-id="f66fe-112">Encontrar los índices de texto completo de un catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="f66fe-112">Finding the Full-Text Indexes of a Full-Text Catalog</span></span>  
 <span data-ttu-id="f66fe-113">Puede recuperar las propiedades de los índices de texto completo mediante la instrucción [SELECT](/sql/t-sql/queries/select-transact-sql) siguiente, que selecciona las columnas de las vistas de catálogo [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) y [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="f66fe-113">You can retrieve the properties of the full-text indexes by using the following [SELECT](/sql/t-sql/queries/select-transact-sql) statement, which selects columns from the [sys.fulltext_indexes](/sql/relational-databases/system-catalog-views/sys-fulltext-indexes-transact-sql) and [sys.fulltext_catalogs](/sql/relational-databases/system-catalog-views/sys-fulltext-catalogs-transact-sql) catalog views.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @TableID int;  
SET @TableID = (SELECT OBJECT_ID('AdventureWorks2012.Production.Product'));  
SELECT object_name(@TableID), i.is_enabled, i.change_tracking_state,   
   i.has_crawl_completed, i.crawl_type, c.name as fulltext_catalog_name   
   FROM sys.fulltext_indexes i, sys.fulltext_catalogs c   
   WHERE i.fulltext_catalog_id = c.fulltext_catalog_id;  
GO  
```  
  

  
###  <a name="finding-the-filegroup-or-file-that-contains-a-full-text-index"></a><a name="Find_FG_of_FTI"></a> <span data-ttu-id="f66fe-114">Buscar el grupo de archivos o archivo que contiene un índice de texto completo</span><span class="sxs-lookup"><span data-stu-id="f66fe-114">Finding the Filegroup or File That Contains a Full-Text Index</span></span>  
 <span data-ttu-id="f66fe-115">Cuando se crea un índice de texto completo, se coloca en una de las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f66fe-115">When a full-text index is created, it is placed in one of the following locations:</span></span>  
  
-   <span data-ttu-id="f66fe-116">Un grupo de archivos especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f66fe-116">A user-specified filegroup.</span></span>  
  
-   <span data-ttu-id="f66fe-117">El mismo grupo de archivos que la vista o tabla base, para una tabla sin particiones.</span><span class="sxs-lookup"><span data-stu-id="f66fe-117">The same filegroup as base table or view, for a nonpartitioned table.</span></span>  
  
-   <span data-ttu-id="f66fe-118">El grupo de archivos principal, para una tabla con particiones.</span><span class="sxs-lookup"><span data-stu-id="f66fe-118">The primary filegroup, for a partitioned table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f66fe-119">Para obtener información sobre cómo crear un índice de texto completo, vea [Crear y administrar índices de texto completo](create-and-manage-full-text-indexes.md) y [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f66fe-119">For information about creating a full-text index, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) and [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="f66fe-120">Para buscar el grupo de archivos de índice de texto completo en una tabla o vista, use la consulta siguiente, donde *object_name* es el nombre de la tabla o vista:</span><span class="sxs-lookup"><span data-stu-id="f66fe-120">To find the filegroup of full-text index on a table or view, use the following query, where *object_name* is the name of the table or view:</span></span>  
  
```  
SELECT name FROM sys.filegroups f, sys.fulltext_indexes i   
   WHERE f.data_space_id = i.data_space_id   
      and i.object_id = object_id('object_name');  
GO  
  
```  
  

  
###  <a name="backing-up-the-filegroups-that-contain-full-text-indexes"></a><a name="Back_up_FTIs_of_FTC"></a> <span data-ttu-id="f66fe-121">Realizar la copia de seguridad de los grupos de archivos que contienen índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="f66fe-121">Backing Up the Filegroups That Contain Full-Text Indexes</span></span>  
 <span data-ttu-id="f66fe-122">Después de buscar los grupos de archivos que contienen los índices de un catálogo de texto completo, necesita hacer una copia de seguridad de cada uno de los grupos de archivos.</span><span class="sxs-lookup"><span data-stu-id="f66fe-122">After you find the filegroups that contain the indexes of a full-text catalog, you need back up each of the filegroups.</span></span> <span data-ttu-id="f66fe-123">Durante el proceso de copia de seguridad, es posible que no se quiten ni agreguen catálogos de texto completo.</span><span class="sxs-lookup"><span data-stu-id="f66fe-123">During the backup process, full-text catalogs may not be dropped or added.</span></span>  
  
 <span data-ttu-id="f66fe-124">La primera copia de seguridad de un grupo de archivos debe ser una copia de seguridad de archivos completa.</span><span class="sxs-lookup"><span data-stu-id="f66fe-124">The first backup of a filegroup must be a full file backup.</span></span> <span data-ttu-id="f66fe-125">Después de haber creado una copia de seguridad de archivos completa para un grupo de archivos, podría hacer una copia de seguridad únicamente de los cambios en un grupo de archivos creando una serie de una o varias copias de seguridad diferenciales de los archivos que se basen en la copia de seguridad de archivos completa.</span><span class="sxs-lookup"><span data-stu-id="f66fe-125">After you have created a full file backup for a filegroup, you could back up only the changes in a filegroup by creating a series of one or more differential file backups that are based on the full file backup.</span></span>  
  
 <span data-ttu-id="f66fe-126">**Para realizar copias de seguridad de archivos y grupos de archivos**</span><span class="sxs-lookup"><span data-stu-id="f66fe-126">**To back up files and filegroups**</span></span>  
  
-   [<span data-ttu-id="f66fe-127">Realizar copias de seguridad de archivos y grupos de archivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f66fe-127">Back Up Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="f66fe-128">BACKUP &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f66fe-128">BACKUP &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/backup-transact-sql)  
  

  
##  <a name="restoring-a-full-text-index"></a><a name="Restore_FTI"></a> <span data-ttu-id="f66fe-129">Restaurar un índice de texto completo</span><span class="sxs-lookup"><span data-stu-id="f66fe-129">Restoring a Full-Text Index</span></span>  
 <span data-ttu-id="f66fe-130">Al restaurar un grupo de archivos que se ha incluido en una copia de seguridad, se restauran los archivos de índice de texto completo, así como los demás archivos del grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="f66fe-130">Restoring a backed-up filegroup restores the full-text index files, as well as the other files in the filegroup.</span></span> <span data-ttu-id="f66fe-131">De forma predeterminada, el grupo de archivos se restaura en la ubicación del disco en la que se creó la copia de seguridad del grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="f66fe-131">By default, the filegroup is restored to the disk location on which the filegroup was backed up.</span></span>  
  
 <span data-ttu-id="f66fe-132">Si una tabla indizada de texto completo estaba en línea y se estaba ejecutando un rellenado cuando se creó la copia de seguridad, el rellenado se reanuda después de la restauración.</span><span class="sxs-lookup"><span data-stu-id="f66fe-132">If a full-text indexed table was online and a population was running when the backup was created, the population is resumed after the restore.</span></span>  
  
 <span data-ttu-id="f66fe-133">**Para restaurar un grupo de archivos**</span><span class="sxs-lookup"><span data-stu-id="f66fe-133">**To restore a filegroup**</span></span>  
  
-   [<span data-ttu-id="f66fe-134">Restaurar archivos y grupos de archivos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f66fe-134">Restore Files and Filegroups &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-sql-server.md)  
  
-   [<span data-ttu-id="f66fe-135">Restaurar archivos y grupos de archivos en archivos existentes &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f66fe-135">Restore Files and Filegroups over Existing Files &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-and-filegroups-over-existing-files-sql-server.md)  
  
-   [<span data-ttu-id="f66fe-136">Restaurar archivos en una nueva ubicación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f66fe-136">Restore Files to a New Location &#40;SQL Server&#41;</span></span>](../backup-restore/restore-files-to-a-new-location-sql-server.md)  
  
-   [<span data-ttu-id="f66fe-137">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f66fe-137">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  

  
## <a name="see-also"></a><span data-ttu-id="f66fe-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f66fe-138">See Also</span></span>  
 <span data-ttu-id="f66fe-139">[Administrar y supervisar la búsqueda de texto completo para una instancia de servidor](manage-and-monitor-full-text-search-for-a-server-instance.md) </span><span class="sxs-lookup"><span data-stu-id="f66fe-139">[Manage and Monitor Full-Text Search for a Server Instance](manage-and-monitor-full-text-search-for-a-server-instance.md) </span></span>  
 [<span data-ttu-id="f66fe-140">Actualizar la búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="f66fe-140">Upgrade Full-Text Search</span></span>](upgrade-full-text-search.md)  
  
  
