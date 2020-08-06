---
title: Restaurar una base de datos y enlazarla a un grupo de recursos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0d20a569-8a27-409c-bcab-0effefb48013
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0b518c93ca9d5e7157ceaa20d9548d7b6061017d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662029"
---
# <a name="restore-a-database-and-bind-it-to-a-resource-pool"></a><span data-ttu-id="c00f4-102">Restaurar una base de datos y enlazarla a un grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="c00f4-102">Restore a Database and Bind it to a Resource Pool</span></span>
  <span data-ttu-id="c00f4-103">Aunque tenga memoria suficiente para restaurar una base de datos con tablas optimizadas para memoria, se aconseja seguir los procedimientos recomendados y enlazar la base de datos a un grupo de recursos de servidor con nombre.</span><span class="sxs-lookup"><span data-stu-id="c00f4-103">Even though you have enough memory to restore a database with memory-optimized tables, you want to follow best practices and bind the database to a named resource pool.</span></span> <span data-ttu-id="c00f4-104">Puesto que es preciso que la base de datos exista antes de poder enlazarla al grupo que restaura la base de datos, se trata de un proceso en varias fases.</span><span class="sxs-lookup"><span data-stu-id="c00f4-104">Since the database must exist before you can bind it to the pool restoring your database is a multi-step process.</span></span> <span data-ttu-id="c00f4-105">Este tema le guiará a través de ese proceso.</span><span class="sxs-lookup"><span data-stu-id="c00f4-105">This topic walks you through that process.</span></span>  
  
##  <a name="restore-with-norecovery"></a><span data-ttu-id="c00f4-106">Restaure con NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="c00f4-106">Restore with NORECOVERY</span></span>  
 <span data-ttu-id="c00f4-107">Cuando se restaura una base de datos, NORECOVERY provoca que se cree la base de datos y se restaura la imagen de disco sin consumir memoria.</span><span class="sxs-lookup"><span data-stu-id="c00f4-107">When you restore a database, NORECOVERY causes the database to be created and the disk image restored without consuming memory.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   FROM DISK = 'C:\IMOLTP_test\IMOLTP_DB.bak'  
   WITH NORECOVERY  
```  
  
##  <a name="create-the-resource-pool"></a><span data-ttu-id="c00f4-108">Crear el grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="c00f4-108">Create the resource pool</span></span>  
 <span data-ttu-id="c00f4-109">El siguiente código [!INCLUDE[tsql](../../includes/tsql-md.md)] crea un grupo de recursos de servidor denominado Pool_IMOLTP con el 50 % de memoria disponible para su uso.</span><span class="sxs-lookup"><span data-stu-id="c00f4-109">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] creates a resource pool named Pool_IMOLTP with 50% of memory available for its use.</span></span>  <span data-ttu-id="c00f4-110">Una vez creado el grupo, hay que reconfigurar el Regulador de recursos para incluir Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="c00f4-110">After the pool is created, the Resource Governor is reconfigured to include Pool_IMOLTP.</span></span>  
  
```sql  
CREATE RESOURCE POOL Pool_IMOLTP WITH (MAX_MEMORY_PERCENT = 50);  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
##  <a name="bind-the-database-and-resource-pool"></a><span data-ttu-id="c00f4-111">Enlazar la base de datos y el grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="c00f4-111">Bind the database and resource pool</span></span>  
 <span data-ttu-id="c00f4-112">Use la función del sistema `sp_xtp_bind_db_resource_pool` para enlazar la base de datos al grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="c00f4-112">Use the system function `sp_xtp_bind_db_resource_pool` to bind the database to the resource pool.</span></span> <span data-ttu-id="c00f4-113">La función utiliza dos parámetros: el nombre de la base de datos seguido del nombre del grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="c00f4-113">The function takes two parameters: the database name followed by the resource pool name.</span></span>  
  
 <span data-ttu-id="c00f4-114">El siguiente código [!INCLUDE[tsql](../../includes/tsql-md.md)] define un enlace de la base de datos IMOLTP_DB con el grupo de recursos de servidor Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="c00f4-114">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] defines a binding of the database IMOLTP_DB to the resource pool Pool_IMOLTP.</span></span> <span data-ttu-id="c00f4-115">El enlace no toma efecto hasta que se complete el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="c00f4-115">The binding does not become effective until you complete the next step.</span></span>  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
##  <a name="restore-with-recovery"></a><span data-ttu-id="c00f4-116">Restaurar con RECOVERY</span><span class="sxs-lookup"><span data-stu-id="c00f4-116">Restore with RECOVERY</span></span>  
 <span data-ttu-id="c00f4-117">Cuando restaure la base de datos con RECOVERY, la base de datos se conecta y se restauran todos los datos.</span><span class="sxs-lookup"><span data-stu-id="c00f4-117">When you restore the database with recovery the database is brought online and all the data restored.</span></span>  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   WITH RECOVERY  
```  
  
##  <a name="monitor-the-resource-pool-performance"></a><span data-ttu-id="c00f4-118">Supervisar el rendimiento del grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="c00f4-118">Monitor the resource pool performance</span></span>  
 <span data-ttu-id="c00f4-119">Una vez que la base de datos se enlaza al grupo de recursos de servidor con nombre y se restaura con la recuperación, supervise el objeto de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Estadísticas de grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="c00f4-119">Once the database is bound to the named resource pool and restored with recovery, monitor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Resource Pool Stats Object.</span></span> <span data-ttu-id="c00f4-120">Para obtener más información vea [Objeto SQL Server: Estadísticas de grupo de recursos de servidor](../performance-monitor/sql-server-resource-pool-stats-object.md).</span><span class="sxs-lookup"><span data-stu-id="c00f4-120">For more information see [SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00f4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c00f4-121">See Also</span></span>  
 <span data-ttu-id="c00f4-122">[Enlazar una base de datos con tablas con optimización para memoria a un grupo de recursos de servidor](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="c00f4-122">[Bind a Database with Memory-Optimized Tables to a Resource Pool](bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md) </span></span>  
 <span data-ttu-id="c00f4-123">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c00f4-123">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="c00f4-124">[Objeto SQL Server: Estadísticas de grupo de recursos de servidor](../performance-monitor/sql-server-resource-pool-stats-object.md) </span><span class="sxs-lookup"><span data-stu-id="c00f4-124">[SQL Server, Resource Pool Stats Object](../performance-monitor/sql-server-resource-pool-stats-object.md) </span></span>  
 [<span data-ttu-id="c00f4-125">sys.dm_resource_governor_resource_pools</span><span class="sxs-lookup"><span data-stu-id="c00f4-125">sys.dm_resource_governor_resource_pools</span></span>](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql)  
  
  
