---
title: Compresión de copia de seguridad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server], backup compression
- backup compression [SQL Server], about backup compression
- compression [SQL Server], backup compression
- backups [SQL Server], compression
- backing up [SQL Server], backup compression
- backup compression [SQL Server]
ms.assetid: 05bc9c4f-3947-4dd4-b823-db77519bd4d2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3291a858d8ef037e7cca92eb2e6abb19aec4da8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663540"
---
# <a name="backup-compression-sql-server"></a><span data-ttu-id="4d5cb-102">Compresión de copia de seguridad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4d5cb-102">Backup Compression (SQL Server)</span></span>
  <span data-ttu-id="4d5cb-103">En este tema se describe la compresión de copias de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , incluidas las restricciones, las ventajas y desventajas de la compresión de las copias de seguridad respecto al rendimiento, la configuración de la compresión de copias de seguridad y la razón de compresión.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-103">This topic describes the compression of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups, including restrictions, performance trade-off of compressing backups, the configuration of backup compression, and the compression ratio.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d5cb-104">Para obtener información sobre las ediciones de que [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] admiten la compresión de copia de seguridad, vea [características compatibles con las ediciones de SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="4d5cb-104">For information which editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] support backup compression, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="4d5cb-105">Cada edición de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] y posteriores pueden restaurar una copia de seguridad cifrada.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-105">Every edition of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later can restore a compressed backup.</span></span>  
  
  
##  <a name="benefits"></a><a name="Benefits"></a> <span data-ttu-id="4d5cb-106">Ventajas</span><span class="sxs-lookup"><span data-stu-id="4d5cb-106">Benefits</span></span>  
  
-   <span data-ttu-id="4d5cb-107">Dado que el tamaño de una copia de seguridad comprimida es menor que el de una sin comprimir de los mismos datos, normalmente la compresión de una copia de seguridad requiere menos operaciones de E/S en los dispositivos y, por consiguiente, suele aumentar significativamente la velocidad de creación de la copia.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-107">Because a compressed backup is smaller than an uncompressed backup of the same data, compressing a backup typically requires less device I/O and therefore usually increases backup speed significantly.</span></span>  
  
     <span data-ttu-id="4d5cb-108">Para obtener más información, vea [Impacto en el rendimiento de la compresión de las copias de seguridad](#PerfImpact), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-108">For more information, see [Performance Impact of Compressing Backups](#PerfImpact), later in this topic.</span></span>  
  
  
##  <a name="restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4d5cb-109">Restricciones</span><span class="sxs-lookup"><span data-stu-id="4d5cb-109">Restrictions</span></span>  
 <span data-ttu-id="4d5cb-110">La compresión de las copias de seguridad está sujeta a las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="4d5cb-110">The following restrictions apply to compressed backups:</span></span>  
  
-   <span data-ttu-id="4d5cb-111">Las copias de seguridad comprimidas y sin comprimir no pueden coexistir al mismo tiempo en un mismo conjunto de medios.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-111">Compressed and uncompressed backups cannot co-exist in a media set.</span></span>  
  
-   <span data-ttu-id="4d5cb-112">Las versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no pueden leer copias de seguridad comprimidas.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-112">Previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot read compressed backups.</span></span>  
  
-   <span data-ttu-id="4d5cb-113">NTbackups no puede compartir una cinta con copias de seguridad comprimidas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4d5cb-113">NTbackups cannot share a tape with compressed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backups.</span></span>  
  
  
##  <a name="performance-impact-of-compressing-backups"></a><a name="PerfImpact"></a> <span data-ttu-id="4d5cb-114">Impacto en el rendimiento de la compresión de las copias de seguridad</span><span class="sxs-lookup"><span data-stu-id="4d5cb-114">Performance Impact of Compressing Backups</span></span>  
 <span data-ttu-id="4d5cb-115">De forma predeterminada, la compresión aumenta significativamente el uso de CPU y la CPU adicional que consume el proceso de compresión puede afectar adversamente a las operaciones simultáneas.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-115">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="4d5cb-116">Por consiguiente, podría ser conveniente crear copias de seguridad comprimidas de prioridad baja en una sesión en la que el[regulador de recursos](../resource-governor/resource-governor.md)limite el uso de CPU.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-116">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by[Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="4d5cb-117">Para obtener más información, vea [Usar el regulador de recursos para limitar el uso de CPU mediante compresión de copia de seguridad &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)limite el uso de CPU.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-117">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
 <span data-ttu-id="4d5cb-118">Para hacerse una idea acertada del rendimiento de la E/S de su copia de seguridad, puede aislar la E/S de la copia de seguridad realizada hacia o desde los dispositivos evaluando los siguientes tipos de contadores de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="4d5cb-118">To obtain a good picture of your backup I/O performance, you can isolate the backup I/O to or from devices by evaluating the following sorts of performance counters:</span></span>  
  
-   <span data-ttu-id="4d5cb-119">Contadores de rendimiento de la E/S de Windows, tales como los contadores de disco físico</span><span class="sxs-lookup"><span data-stu-id="4d5cb-119">Windows I/O performance counters, such as the physical-disk counters</span></span>  
  
-   <span data-ttu-id="4d5cb-120">El contador **Rendimiento del dispositivo en bytes/s** del objeto [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md)</span><span class="sxs-lookup"><span data-stu-id="4d5cb-120">The **Device Throughput Bytes/sec** counter of the [SQLServer:Backup Device](../performance-monitor/sql-server-backup-device-object.md) object</span></span>  
  
-   <span data-ttu-id="4d5cb-121">El contador **Rendimiento de copia de seguridad o restauración/s** del objeto [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md)</span><span class="sxs-lookup"><span data-stu-id="4d5cb-121">The **Backup/Restore Throughput/sec** counter of the [SQLServer:Databases](../performance-monitor/sql-server-databases-object.md) object</span></span>  
  
 <span data-ttu-id="4d5cb-122">Para obtener más información acerca de los contadores de Windows, vea la ayuda de Windows.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-122">For information about Windows counters, see Windows help.</span></span> <span data-ttu-id="4d5cb-123">Para obtener información sobre el trabajo con contadores de SQL Server, vea [Usar objetos de SQL Server](../performance-monitor/use-sql-server-objects.md).</span><span class="sxs-lookup"><span data-stu-id="4d5cb-123">For information about how to work with SQL Server counters, see [Use SQL Server Objects](../performance-monitor/use-sql-server-objects.md).</span></span>  
  
  
##  <a name="calculate-the-compression-ratio-of-a-compressed-backup"></a><a name="CompressionRatio"></a> <span data-ttu-id="4d5cb-124">Calcular la razón de compresión de una copia de seguridad comprimida</span><span class="sxs-lookup"><span data-stu-id="4d5cb-124">Calculate the Compression Ratio of a Compressed Backup</span></span>  
 <span data-ttu-id="4d5cb-125">Para calcular la razón de compresión de una copia de seguridad, use los valores de la copia de seguridad de las columnas **backup_size** y **compressed_backup_size** de la tabla de historial [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) , de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="4d5cb-125">To calculate the compression ratio of a backup, use the values for the backup in the **backup_size** and **compressed_backup_size** columns of the [backupset](/sql/relational-databases/system-tables/backupset-transact-sql) history table, as follows:</span></span>  
  
 <span data-ttu-id="4d5cb-126">**backup_size**:**compressed_backup_size**</span><span class="sxs-lookup"><span data-stu-id="4d5cb-126">**backup_size**:**compressed_backup_size**</span></span>  
  
 <span data-ttu-id="4d5cb-127">Por ejemplo, una razón de compresión de 3:1 indica que está ahorrando aproximadamente un 66% del espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-127">For example, a 3:1 compression ratio indicates that you are saving about 66% on disk space.</span></span> <span data-ttu-id="4d5cb-128">Para consultar estas columnas, puede utilizar la siguiente instrucción de Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="4d5cb-128">To query on these columns, you can use the following Transact-SQL statement:</span></span>  
  
```  
SELECT backup_size/compressed_backup_size FROM msdb..backupset;  
```  
  
 <span data-ttu-id="4d5cb-129">La razón de compresión de una copia de seguridad comprimida depende de los datos que se hayan comprimido.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-129">The compression ratio of a compressed backup depends on the data that has been compressed.</span></span> <span data-ttu-id="4d5cb-130">La razón de compresión obtenida puede verse influenciada por diversos factores.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-130">A variety of factors can impact the compression ratio obtained.</span></span> <span data-ttu-id="4d5cb-131">Entre los factores más importantes tenemos:</span><span class="sxs-lookup"><span data-stu-id="4d5cb-131">Major factors include:</span></span>  
  
-   <span data-ttu-id="4d5cb-132">El tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-132">The type of data.</span></span>  
  
     <span data-ttu-id="4d5cb-133">El texto se comprime más que otros tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-133">Character data compresses more than other types of data.</span></span>  
  
-   <span data-ttu-id="4d5cb-134">La coherencia de los datos entre las filas de una página.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-134">The consistency of the data among rows on a page.</span></span>  
  
     <span data-ttu-id="4d5cb-135">Normalmente, si una página contiene varias filas en las que un campo contiene el mismo valor, se podría producir una compresión significativa para ese valor.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-135">Typically, if a page contains several rows in which a field contains the same value, significant compression might occur for that value.</span></span> <span data-ttu-id="4d5cb-136">En contraste, para una base de datos que contiene datos aleatorios o que contiene solo una fila de gran tamaño por página, la copia de seguridad comprimida sería casi tan grande como la copia de seguridad sin comprimir.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-136">In contrast, for a database that contains random data or that contains only one large row per page, a compressed backup would be almost as large as an uncompressed backup.</span></span>  
  
-   <span data-ttu-id="4d5cb-137">Si los datos están o no cifrados.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-137">Whether the data is encrypted.</span></span>  
  
     <span data-ttu-id="4d5cb-138">Los datos cifrados se comprimen mucho menos que los datos no cifrados equivalentes.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-138">Encrypted data compresses significantly less than equivalent unencrypted data.</span></span> <span data-ttu-id="4d5cb-139">Si se usa el cifrado transparente de los datos para cifrar una base de datos completa, al comprimir las copias de seguridad, podría no reducirse mucho su tamaño, o nada en absoluto.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-139">If transparent data encryption is used to encrypt an entire database, compressing backups might not reduce their size by much, if at all.</span></span>  
  
-   <span data-ttu-id="4d5cb-140">Si la base de datos está comprimida.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-140">Whether the database is compressed.</span></span>  
  
     <span data-ttu-id="4d5cb-141">Si la base de datos está comprimida, puede que la compresión de las copias de seguridad no reduzca demasiado su tamaño, si es que logra alguna reducción.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-141">If the database is compressed, compressing backups might not reduce their size by much, if at all.</span></span>  
  
  
##  <a name="allocation-of-space-for-the-backup-file"></a><a name="Allocation"></a> <span data-ttu-id="4d5cb-142">Asignación de espacio para el archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-142">Allocation of Space for the Backup File</span></span>  
 <span data-ttu-id="4d5cb-143">Para las copias de seguridad comprimidas, el tamaño del archivo de copia de seguridad final depende de en qué grado puedan comprimirse los datos y esto no se conoce antes de que la operación de copia de seguridad finalice.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-143">For compressed backups, the size of the final backup file depends on how compressible the data is, and this is unknown before the backup operation finishes.</span></span>  <span data-ttu-id="4d5cb-144">Por lo tanto, de forma predeterminada al hacer una copia de seguridad de una base de datos usando la compresión, el Motor de base de datos usa un algoritmo de preasignación para el archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-144">Therefore, by default, when backing up a database using compression, the Database Engine uses a pre-allocation algorithm for the backup file.</span></span> <span data-ttu-id="4d5cb-145">Este algoritmo preasigna una porcentaje predefinido del tamaño de la base de datos para el archivo de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-145">This algorithm pre-allocates a predefined percentage of the size of the database for the backup file.</span></span> <span data-ttu-id="4d5cb-146">Si se necesita más espacio durante la operación de copia de seguridad, el Motor de base de datos hace crecer el archivo.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-146">If more space is needed during the backup operation, the Database Engine grows the file.</span></span> <span data-ttu-id="4d5cb-147">Si el tamaño final es menor que el espacio asignado, al final de la operación de copia de seguridad, el Motor de base de datos reduce el archivo hasta el tamaño final real de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-147">If the final size is less than the allocated space, at the end of the backup operation, the Database Engine shrinks the file to the actual final size of the backup.</span></span>  
  
 <span data-ttu-id="4d5cb-148">Para que el archivo de copia de seguridad crezca solo lo necesario para alcanzar su tamaño final, use la marca de seguimiento 3042.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-148">To allow the backup file to grow only as needed to reach its final size, use trace flag 3042.</span></span> <span data-ttu-id="4d5cb-149">La marca de seguimiento 3042 hace que la operación de copia de seguridad omita el algoritmo de preasignación de compresión de copia de seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-149">Trace flag 3042 causes the backup operation to bypass the default backup compression pre-allocation algorithm.</span></span> <span data-ttu-id="4d5cb-150">Esta marca de seguimiento es útil si tiene que ahorrar espacio asignando solo el tamaño real requerido para la copia de seguridad comprimida.</span><span class="sxs-lookup"><span data-stu-id="4d5cb-150">This trace flag is useful if you need to save on space by allocating only the actual size required for the compressed backup.</span></span> <span data-ttu-id="4d5cb-151">No obstante, el uso de esta marca de seguimiento podría ocasionar una ligera reducción en el rendimiento (un posible aumento de la duración de la operación de copia de seguridad).</span><span class="sxs-lookup"><span data-stu-id="4d5cb-151">However, using this trace flag might cause a slight performance penalty (a possible increase in the duration of the backup operation).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4d5cb-152">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="4d5cb-152">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4d5cb-153">Configurar la compresión de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4d5cb-153">Configure Backup Compression &#40;SQL Server&#41;</span></span>](backup-compression-sql-server.md)  
  
-   [<span data-ttu-id="4d5cb-154">Ver o establecer la opción de configuración del servidor de compresión de copia de seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="4d5cb-154">View or Configure the backup compression default Server Configuration Option</span></span>](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md)  
  
-   [<span data-ttu-id="4d5cb-155">Usar el regulador de recursos para limitar el uso de CPU mediante compresión de copia de seguridad &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d5cb-155">Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;</span></span>](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md)  
  
-   [<span data-ttu-id="4d5cb-156">DBCC TRACEON &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d5cb-156">DBCC TRACEON &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-transact-sql)  
  
-   [<span data-ttu-id="4d5cb-157">DBCC TRACEOFF &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d5cb-157">DBCC TRACEOFF &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceoff-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="4d5cb-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d5cb-158">See Also</span></span>  
 <span data-ttu-id="4d5cb-159">[Información general de copia de seguridad &#40;SQL Server&#41;](backup-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4d5cb-159">[Backup Overview &#40;SQL Server&#41;](backup-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="4d5cb-160">Marcas de seguimiento &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4d5cb-160">Trace Flags &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql)  
  
  
