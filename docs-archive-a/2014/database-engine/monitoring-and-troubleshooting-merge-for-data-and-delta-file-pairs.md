---
title: Supervisión y solución de problemas de combinación de pares de archivos Delta y de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: a8b0bacc-4d2c-42e4-84bf-1a97e0bd385b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5dc57d08f3db1792a9359b3aa79aaceecd03a025
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676663"
---
# <a name="monitoring-and-troubleshooting-merge-for-data-and-delta-file-pairs"></a><span data-ttu-id="ddb10-102">Supervisar y solucionar los problemas de la mezcla para los pares de archivos delta y de datos</span><span class="sxs-lookup"><span data-stu-id="ddb10-102">Monitoring and Troubleshooting Merge for Data and Delta File Pairs</span></span>
  <span data-ttu-id="ddb10-103">OLTP en memoria usa una directiva de mezcla para mezclar los pares de archivos delta y de datos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="ddb10-103">In-Memory OLTP uses a merge policy to merge adjacent data and delta file pairs automatically.</span></span> <span data-ttu-id="ddb10-104">No puede deshabilitar la actividad de mezcla.</span><span class="sxs-lookup"><span data-stu-id="ddb10-104">You cannot disable merge activity.</span></span>  
  
 <span data-ttu-id="ddb10-105">Puede supervisar los pares de archivos delta y de datos como sigue:</span><span class="sxs-lookup"><span data-stu-id="ddb10-105">You can monitor data and delta file pairs, as follows:</span></span>  
  
-   <span data-ttu-id="ddb10-106">Compare el tamaño del almacenamiento en memoria con el tamaño total del almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ddb10-106">Compare the size of in-memory storage to overall size of storage.</span></span> <span data-ttu-id="ddb10-107">Si el almacenamiento es desproporcionadamente grande, es probable que la mezcla no se esté realizando.</span><span class="sxs-lookup"><span data-stu-id="ddb10-107">If the storage is dis-proportionately large, then it is likely that merge is not getting triggered.</span></span> <span data-ttu-id="ddb10-108">Para obtener información</span><span class="sxs-lookup"><span data-stu-id="ddb10-108">For information</span></span>  
  
-   <span data-ttu-id="ddb10-109">Observe el espacio usado en los archivos Delta y de datos mediante [Sys. dm_db_xtp_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) para ver si la combinación no se desencadena cuando debería.</span><span class="sxs-lookup"><span data-stu-id="ddb10-109">Look at the used space in data and delta files using [sys.dm_db_xtp_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-xtp-checkpoint-files-transact-sql) to see if merge is not getting triggered when it should.</span></span>  
  
## <a name="performing-a-manual-merge"></a><span data-ttu-id="ddb10-110">Realizar una mezcla manual</span><span class="sxs-lookup"><span data-stu-id="ddb10-110">Performing a Manual Merge</span></span>  
 <span data-ttu-id="ddb10-111">Puede usar [Sys. sp_xtp_merge_checkpoint_files &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) para realizar una combinación manual.</span><span class="sxs-lookup"><span data-stu-id="ddb10-111">You can use [sys.sp_xtp_merge_checkpoint_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-merge-checkpoint-files-transact-sql) to perform a manual merge.</span></span>  
  
 <span data-ttu-id="ddb10-112">Utilice la siguiente consulta para recuperar información sobre los archivos delta y de datos,</span><span class="sxs-lookup"><span data-stu-id="ddb10-112">Use the following query to retrieve information about the data and delta files,</span></span>  
  
```sql  
select checkpoint_file_id, file_type_desc, internal_storage_slot, file_size_in_bytes, file_size_used_in_bytes,   
inserted_row_count, deleted_row_count, lower_bound_tsn, upper_bound_tsn   
from sys.dm_db_xtp_checkpoint_files  
where state = 1  
order by file_type_desc, upper_bound_tsn  
```  
  
 <span data-ttu-id="ddb10-113">Supongamos que encontró tres archivos de datos que no se han combinado.</span><span class="sxs-lookup"><span data-stu-id="ddb10-113">Assume that you found three data files that have not been merged.</span></span> <span data-ttu-id="ddb10-114">Con el valor `lower_bound_tsn` del primer archivo de datos y `upper_bound_tsn` del último, puede emitir el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="ddb10-114">Using the `lower_bound_tsn` value of the first data file and the `upper_bound_tsn` of the last data file, you can issue the following command:</span></span>  
  
```sql  
exec sys.sp_xtp_merge_checkpoint_files 'H_DB',  12345, 67890  
```  
  
 <span data-ttu-id="ddb10-115">Imagine que los tres pares de archivos delta y de datos tenían cada uno 15.836 filas y 5.279 filas eliminadas.</span><span class="sxs-lookup"><span data-stu-id="ddb10-115">Assume that the three data and delta file pairs each had 15,836 rows and 5,279 deleted rows.</span></span> <span data-ttu-id="ddb10-116">Después de la mezcla, el nuevo archivo de datos tiene 31.872 filas y 0 filas eliminadas.</span><span class="sxs-lookup"><span data-stu-id="ddb10-116">After the merge, the new data file has 31,872 rows and 0 deleted rows.</span></span> <span data-ttu-id="ddb10-117">El tamaño del nuevo archivo de datos puede ser mucho mayor que el tamaño asignado inicialmente de 128 MB.</span><span class="sxs-lookup"><span data-stu-id="ddb10-117">The size of the new data file can be much larger than the initially allocated size of 128MB.</span></span> <span data-ttu-id="ddb10-118">Esto se debe a que la mezcla manual invalida la directiva de mezcla y aplica la mezcla de los archivos solicitados.</span><span class="sxs-lookup"><span data-stu-id="ddb10-118">This is because manual merge overrides the merge policy and forces the merge of the requested files.</span></span>  
  
 <span data-ttu-id="ddb10-119">La [transición del estado del blog de los archivos de punto de comprobación de las bases de datos con tablas optimizadas para memoria describe la](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) transición de estado de los pares de archivos Delta y de datos desde el inicio hasta la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ddb10-119">The blog [State Transition of Checkpoint Files in Databases with Memory-Optimized Tables](https://cloudblogs.microsoft.com/sqlserver/2014/01/23/state-transition-of-checkpoint-files-in-databases-with-memory-optimized-tables/) describes state transition of data and delta file pairs from inception to garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb10-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ddb10-120">See Also</span></span>  
 [<span data-ttu-id="ddb10-121">Crear y administrar el almacenamiento de objetos optimizados para memoria</span><span class="sxs-lookup"><span data-stu-id="ddb10-121">Creating and Managing Storage for Memory-Optimized Objects</span></span>](../relational-databases/in-memory-oltp/creating-and-managing-storage-for-memory-optimized-objects.md)  
  
