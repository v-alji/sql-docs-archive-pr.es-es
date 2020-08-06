---
title: Restauración por etapas de bases de datos con tablas con optimización para memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 732c9721-8dd4-481d-8ff9-1feaaa63f84f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ed23f08d40e23b1d43c1b642f4089fe77646b675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748788"
---
# <a name="piecemeal-restore-of-databases-with-memory-optimized-tables"></a><span data-ttu-id="1706d-102">Restauración por etapas de bases de datos con tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="1706d-102">Piecemeal Restore of Databases With Memory-Optimized Tables</span></span>
  <span data-ttu-id="1706d-103">La restauración por etapas se admite en bases de datos con tablas optimizadas para memoria, a excepción de una restricción que describe más adelante.</span><span class="sxs-lookup"><span data-stu-id="1706d-103">Piecemeal restore is supported on databases with memory-optimized tables except for one restriction described below.</span></span> <span data-ttu-id="1706d-104">Para obtener más información sobre la restauración y la copia de seguridad por etapas, vea [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) y [Restauraciones por etapas &#40;SQL Server&#41;](../backup-restore/piecemeal-restores-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1706d-104">For more information about piecemeal backup and restore, see [RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) and [Piecemeal Restores &#40;SQL Server&#41;](../backup-restore/piecemeal-restores-sql-server.md).</span></span>  
  
 <span data-ttu-id="1706d-105">La copia de seguridad y la restauración de un grupo de archivos principal y de un grupo de archivos optimizados para memoria deben realizarse conjuntamente:</span><span class="sxs-lookup"><span data-stu-id="1706d-105">A memory-optimized filegroup must be backed up and restored together with the primary filegroup:</span></span>  
  
-   <span data-ttu-id="1706d-106">Si realiza una copia de seguridad (o restaura) el grupo de archivos principal, debe especificar el grupo de archivos optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="1706d-106">If you back up (or restore) the primary filegroup you must specify the memory-optimized filegroup.</span></span>  
  
-   <span data-ttu-id="1706d-107">Si realiza una copia de seguridad (o restaura) el grupo de archivos optimizados para memoria, debe especificar el grupo de archivos principal.</span><span class="sxs-lookup"><span data-stu-id="1706d-107">If you backup (or restore) the memory-optimized filegroup you must specify the primary filegroup.</span></span>  
  
 <span data-ttu-id="1706d-108">Estos son los escenarios clave para la copia de seguridad y la restauración por etapas:</span><span class="sxs-lookup"><span data-stu-id="1706d-108">Key scenarios for piecemeal backup and restore are,</span></span>  
  
-   <span data-ttu-id="1706d-109">La copia de seguridad por etapas permite reducir el tamaño de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1706d-109">Piecemeal backup allows you to reduce the size of backup.</span></span> <span data-ttu-id="1706d-110">He aquí algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="1706d-110">Some examples:</span></span>  
  
    -   <span data-ttu-id="1706d-111">Configure la copia de seguridad de la base de datos para que se realice a horas o en días diferentes con el fin de minimizar el impacto sobre la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1706d-111">Configure the database backup to occur at different times or days to minimize the impact on the workload.</span></span> <span data-ttu-id="1706d-112">Un ejemplo es una base de datos muy grande (mayor de 1 TB) en la que no se puede completar una copia de seguridad completa de la base de datos en el tiempo asignado para el mantenimiento de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="1706d-112">One example is a very large database (greater than 1 TB) where a full database backup cannot complete in the time allocated for database maintenance.</span></span> <span data-ttu-id="1706d-113">En esa situación, puede usar la copia de seguridad por etapas para hacer copia de seguridad de toda la base de datos en varias copias de seguridad por etapas.</span><span class="sxs-lookup"><span data-stu-id="1706d-113">In that situation, you can use piecemeal backup to backup the full database in multiple piecemeal backups.</span></span>  
  
    -   <span data-ttu-id="1706d-114">Si un grupo de archivos está marcado como de solo lectura, no requiere una copia de seguridad de registros de transacciones después de que se haya marcado como de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1706d-114">If a filegroup is marked read-only, it does not require a transaction log backup after it was marked read-only.</span></span> <span data-ttu-id="1706d-115">Puede decidir realizar la copia de seguridad del grupo de archivos solo una vez después de marcarlo de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="1706d-115">You can choose to back up the filegroup only once after marking it read-only.</span></span>  
  
-   <span data-ttu-id="1706d-116">Restauración por etapas.</span><span class="sxs-lookup"><span data-stu-id="1706d-116">Piecemeal restore.</span></span>  
  
    -   <span data-ttu-id="1706d-117">El objetivo de una restauración por etapas es poner en línea las partes fundamentales de la base de datos sin esperar a todos los datos.</span><span class="sxs-lookup"><span data-stu-id="1706d-117">The goal of a piecemeal restore is to bring the critical parts of database online without waiting for all the data.</span></span> <span data-ttu-id="1706d-118">Un ejemplo es si una base de datos tiene datos particionados, como los de particiones antiguas que se usan con poca frecuencia.</span><span class="sxs-lookup"><span data-stu-id="1706d-118">One example is if a database has partitioned data, such that older partitions are only used rarely.</span></span> <span data-ttu-id="1706d-119">Puede restaurar solo esos datos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1706d-119">You can restore them only on an as-needed basis.</span></span> <span data-ttu-id="1706d-120">Esto es similar para los grupos de archivos que contienen, por ejemplo, datos históricos.</span><span class="sxs-lookup"><span data-stu-id="1706d-120">Similar for filegroups that contain, for example, historical data.</span></span>  
  
    -   <span data-ttu-id="1706d-121">Mediante la reparación de página, puede corregir daños en una página restaurando específicamente esa página.</span><span class="sxs-lookup"><span data-stu-id="1706d-121">Using page repair, you can fix page corruption by specifically restoring the page.</span></span> <span data-ttu-id="1706d-122">Para obtener más información, vea [Restaurar páginas &#40;SQL Server&#41;](../backup-restore/restore-pages-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="1706d-122">For more information, see [Restore Pages &#40;SQL Server&#41;](../backup-restore/restore-pages-sql-server.md).</span></span>  
  
## <a name="samples"></a><span data-ttu-id="1706d-123">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1706d-123">Samples</span></span>  
 <span data-ttu-id="1706d-124">En los ejemplos se usa el esquema siguiente:</span><span class="sxs-lookup"><span data-stu-id="1706d-124">The examples use the following schema:</span></span>  
  
```  
CREATE DATABASE imoltp  
ON PRIMARY (name = imoltp_primary1, filename = 'c:\data\imoltp_data1.mdf')  
LOG ON (name = imoltp_log, filename = 'c:\data\imoltp_log.ldf')  
GO  
  
ALTER DATABASE imoltp ADD FILE (name = imoltp_primary2, filename = 'c:\data\imoltp_data2.ndf')  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_secondary  
ALTER DATABASE imoltp ADD FILE (name = imoltp_secondary, filename = 'c:\data\imoltp_secondary.ndf') TO FILEGROUP imoltp_secondary  
GO  
  
ALTER DATABASE imoltp ADD FILEGROUP imoltp_mod CONTAINS MEMORY_OPTIMIZED_DATA   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod1', filename='c:\data\imoltp_mod1') TO FILEGROUP imoltp_mod   
ALTER DATABASE imoltp ADD FILE (name='imoltp_mod2', filename='c:\data\imoltp_mod2') TO FILEGROUP imoltp_mod   
GO  
```  
  
### <a name="backup"></a><span data-ttu-id="1706d-125">Copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="1706d-125">Backup</span></span>  
 <span data-ttu-id="1706d-126">En este ejemplo se muestra cómo hacer copia de seguridad del grupo de archivos principal y el grupo de archivos optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="1706d-126">This sample shows how to backup the primary filegroup and the memory-optimized filegroup.</span></span> <span data-ttu-id="1706d-127">Debe especificar juntos el grupo de archivos principal y el grupo de archivos optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="1706d-127">You must specify both primary and memory-optimized filegroup together.</span></span>  
  
```  
backup database imoltp filegroup='primary', filegroup='imoltp_mod' to disk='c:\data\imoltp.dmp' with init  
```  
  
 <span data-ttu-id="1706d-128">En el ejemplo siguiente se muestra que una copia de seguridad de grupos de archivos que no son del grupo de archivos principal y optimizados para memoria es similar a las bases de datos que no tienen tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="1706d-128">The following sample shows that a back up of filegroup(s) other than primary and memory-optimized filegroup works similar to the databases without memory-optimized tables.</span></span> <span data-ttu-id="1706d-129">El comando siguiente hace copia de seguridad hasta el grupo de archivos secundario</span><span class="sxs-lookup"><span data-stu-id="1706d-129">The following command backups up the secondary filegroup</span></span>  
  
```  
backup database imoltp filegroup='imoltp_secondary' to disk='c:\data\imoltp_secondary.dmp' with init  
```  
  
### <a name="restore"></a><span data-ttu-id="1706d-130">Restauración</span><span class="sxs-lookup"><span data-stu-id="1706d-130">Restore</span></span>  
 <span data-ttu-id="1706d-131">En el ejemplo siguiente se muestra cómo restaurar conjuntamente el grupo de archivos principal y el grupo de archivos optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="1706d-131">The following sample shows how to restore the primary filegroup and memory-optimized filegroup together.</span></span>  
  
```  
restore database imoltp filegroup = 'primary', filegroup = 'imoltp_mod'   
from disk='c:\data\imoltp.dmp' with partial, norecovery  
  
--restore the transaction log  
 RESTORE LOG [imoltp] FROM DISK = N'c:\data\imoltp_log.dmp' WITH  FILE = 1,  NOUNLOAD,  STATS = 10  
GO  
```  
  
 <span data-ttu-id="1706d-132">En el ejemplo siguiente se muestra que la restauración de grupos de archivos distintos del grupo de archivos principal y optimizado para memoria es similar a las bases de datos que no tienen tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="1706d-132">The next sample shows that restoring filegroup(s) other than the primary and memory-optimized filegroup works similar to the databases without memory-optimized tables</span></span>  
  
```  
RESTORE DATABASE [imoltp] FILE = N'imoltp_secondary'   
FROM  DISK = N'c:\data\imoltp_secondary.dmp' WITH  FILE = 1,  RECOVERY,  NOUNLOAD,  STATS = 10  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1706d-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1706d-133">See Also</span></span>  
 [<span data-ttu-id="1706d-134">Hacer copia de seguridad, restaurar y recuperar tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="1706d-134">Backup, Restore, and Recovery of Memory-Optimized Tables</span></span>](../../database-engine/backup-restore-and-recovery-of-memory-optimized-tables.md)  
  
  
