---
title: Enlazar una base de datos con tablas con optimización para memoria a un grupo de recursos de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f222b1d5-d2fa-4269-8294-4575a0e78636
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: cd163c5d3bc7a2cd9051b8d37b8127a1cc88c30b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678182"
---
# <a name="bind-a-database-with-memory-optimized-tables-to-a-resource-pool"></a><span data-ttu-id="deb32-102">Enlazar una base de datos con tablas con optimización para memoria a un grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="deb32-102">Bind a Database with Memory-Optimized Tables to a Resource Pool</span></span>
  <span data-ttu-id="deb32-103">Un grupo de recursos de servidor representa un subconjunto de recursos físicos que se pueden regular.</span><span class="sxs-lookup"><span data-stu-id="deb32-103">A resource pool represents a subset of physical resources that can be governed.</span></span> <span data-ttu-id="deb32-104">De forma predeterminada, las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] están enlazadas a los recursos del grupo de recursos de servidor predeterminado y los consumen.</span><span class="sxs-lookup"><span data-stu-id="deb32-104">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases are bound to and consume the resources of the default resource pool.</span></span> <span data-ttu-id="deb32-105">Para proteger [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de manera que una o más tablas optimizadas para memoria no consuman sus recursos, y evitar que otros usuarios consuman memoria que las tablas optimizadas para memoria necesitan, debe crear un grupo de recursos de servidor diferente para administrar el consumo de memoria para la base de datos con tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="deb32-105">To protect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from having its resources consumed by one or more memory-optimized tables, and to prevent other memory users from consuming memory needed by memory-optimized tables, you should create a separate resource pool to manage memory consumption for the database with memory-optimized tables.</span></span>  
  
 <span data-ttu-id="deb32-106">Una base de datos solo se puede enlazar a un grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="deb32-106">A database can be bound on only one resource pool.</span></span> <span data-ttu-id="deb32-107">Sin embargo, puede enlazar varias bases de datos al mismo grupo.</span><span class="sxs-lookup"><span data-stu-id="deb32-107">However, you can bind multiple databases to the same pool.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="deb32-108">permite enlazar una base de datos sin tablas optimizadas para memoria a un grupo de recursos de servidor, pero ello no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="deb32-108">allows binding a database without memory-optimized tables to a resource pool but it has no effect.</span></span> <span data-ttu-id="deb32-109">Puede enlazar una base de datos a un grupo de recursos de servidor con nombre si en el futuro desea crear tablas optimizadas para memoria en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="deb32-109">You may want to bind a database to a named resource pool if, in future, you may want to create memory-optimized tables in the database.</span></span>  
  
 <span data-ttu-id="deb32-110">Para poder enlazar una base de datos a un grupo de recursos de servidor, tanto la base de datos como el grupo de recursos de servidor deben existir.</span><span class="sxs-lookup"><span data-stu-id="deb32-110">Before you can bind a database to a resource pool both the database and the resource pool must exist.</span></span> <span data-ttu-id="deb32-111">El enlace surte efecto la próxima vez que la base de datos pase a estar en línea.</span><span class="sxs-lookup"><span data-stu-id="deb32-111">The binding takes effect the next time the database is brought online.</span></span> <span data-ttu-id="deb32-112">Consulte [Database States](../databases/database-states.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="deb32-112">See [Database States](../databases/database-states.md) for more information.</span></span>  
  
 <span data-ttu-id="deb32-113">Para obtener más información acerca de los grupos de recursos de servidor, vea [Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md).</span><span class="sxs-lookup"><span data-stu-id="deb32-113">For information about resource pools, see [Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md).</span></span>  
  
  
## <a name="create-the-database-and-resource-pool"></a><span data-ttu-id="deb32-114">Crear la base de datos y el grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="deb32-114">Create the database and resource pool</span></span>  
 <span data-ttu-id="deb32-115">Puede crear la base de datos y el grupo de recursos de servidor en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="deb32-115">You can create the database and resource pool in any order.</span></span> <span data-ttu-id="deb32-116">Lo que importa es que ambos existan antes de enlazar la base de datos al grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="deb32-116">What matters is that they both exist prior to binding the database to the resource pool.</span></span>  
  
### <a name="create-the-database"></a><span data-ttu-id="deb32-117">Creación de la base de datos</span><span class="sxs-lookup"><span data-stu-id="deb32-117">Create the database</span></span>  
 <span data-ttu-id="deb32-118">El código [!INCLUDE[tsql](../../includes/tsql-md.md)] siguiente crea una base de datos denominada IMOLTP_DB que contendrá una o varias tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="deb32-118">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] creates a database named IMOLTP_DB which will contain one or more memory-optimized tables.</span></span> <span data-ttu-id="deb32-119">La ruta de acceso \<driveAndPath> debe haberse creado antes de ejecutar este comando.</span><span class="sxs-lookup"><span data-stu-id="deb32-119">The path \<driveAndPath> must exist prior to running this command.</span></span>  
  
```sql  
CREATE DATABASE IMOLTP_DB  
GO  
ALTER DATABASE IMOLTP_DB ADD FILEGROUP IMOLTP_DB_fg CONTAINS MEMORY_OPTIMIZED_DATA  
ALTER DATABASE IMOLTP_DB ADD FILE( NAME = 'IMOLTP_DB_fg' , FILENAME = 'c:\data\IMOLTP_DB_fg') TO FILEGROUP IMOLTP_DB_fg;  
GO  
```  
  
### <a name="determine-the-minimum-value-for-min_memory_percent-and-max_memory_percent"></a><span data-ttu-id="deb32-120">Determinar el valor mínimo de MIN_MEMORY_PERCENT y MAX_MEMORY_PERCENT</span><span class="sxs-lookup"><span data-stu-id="deb32-120">Determine the minimum value for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT</span></span>  
 <span data-ttu-id="deb32-121">Una vez que determine las necesidades de memoria para las tablas optimizadas para memoria, debe determinar qué porcentaje de memoria disponible se necesita y establecer los porcentajes de memoria en ese valor o uno superior.</span><span class="sxs-lookup"><span data-stu-id="deb32-121">Once you determine the memory needs for your memory-optimized tables, you need to determine what percentage of available memory you need, and set the memory percentages to that value or higher.</span></span>  
  
 <span data-ttu-id="deb32-122">**Ejemplo:**  </span><span class="sxs-lookup"><span data-stu-id="deb32-122">**Example:** </span></span>  
<span data-ttu-id="deb32-123">En este ejemplo supondremos que en sus cálculos ha determinado que las tablas y los índices optimizados para memoria necesitan 16 GB de memoria.</span><span class="sxs-lookup"><span data-stu-id="deb32-123">For this example we will assume that from your calculations you determined that your memory-optimized tables and indexes need 16 GB of memory.</span></span> <span data-ttu-id="deb32-124">Suponga que tiene 32 GB de memoria asignada para su uso.</span><span class="sxs-lookup"><span data-stu-id="deb32-124">Assume that you have 32 GB of memory committed for your use.</span></span>  
  
 <span data-ttu-id="deb32-125">A primera vista, podría parecer que necesita establecer MIN_MEMORY_PERCENT y MAX_MEMORY_PERCENT en 50 (16 es el 50 % de 32).</span><span class="sxs-lookup"><span data-stu-id="deb32-125">At first glance it could seem that you need to set MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT to 50 (16 is 50% of 32).</span></span>  <span data-ttu-id="deb32-126">Sin embargo, ese valor no proporcionaría suficiente memoria a las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="deb32-126">However, that would not give your memory-optimized tables sufficient memory.</span></span> <span data-ttu-id="deb32-127">Si miramos la tabla siguiente ([Porcentaje de memoria disponible para tablas e índices optimizados para memoria](#percent-of-memory-available-for-memory-optimized-tables-and-indexes)), vemos que si hay 32 GB de memoria asignada, solo el 80 % está disponible para tablas e índices optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="deb32-127">Looking at the table below ([Percent of memory available for memory-optimized tables and indexes](#percent-of-memory-available-for-memory-optimized-tables-and-indexes)) we see that if there is 32 GB of committed memory, only 80% of that is available for memory-optimized tables and indexes.</span></span>  <span data-ttu-id="deb32-128">Por tanto, calculamos los porcentajes mínimo y máximo en función de la memoria disponible, no de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="deb32-128">Therefore, we calculate the min and max percentages based upon the available memory, not the committed memory.</span></span>  
  
 `memoryNeedeed = 16`   
 `memoryCommitted = 32`   
 `availablePercent = 0.8`   
 `memoryAvailable = memoryCommitted * availablePercent`   
 `percentNeeded = memoryNeeded / memoryAvailable`  
  
 <span data-ttu-id="deb32-129">Es decir, en números reales sería:</span><span class="sxs-lookup"><span data-stu-id="deb32-129">Plugging in real numbes:</span></span>   
`percentNeeded = 16 / (32 * 0.8) = 16 / 25.6 = 0.625`  
  
 <span data-ttu-id="deb32-130">Necesita al menos el 62,5 % de la memoria disponible para satisfacer el requisito de 16 GB de las tablas y los índices optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="deb32-130">Thus you need at least 62.5% of the available memory to meet the 16 GB requirement of your memory-optimized tables and indexes.</span></span>  <span data-ttu-id="deb32-131">Puesto que los valores de MIN_MEMORY_PERCENT y MAX_MEMORY_PERCENT deben ser enteros, los estableceremos como mínimo en el 63 %.</span><span class="sxs-lookup"><span data-stu-id="deb32-131">Since the values for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT must be integers, we set them to at least 63%.</span></span>  
  
### <a name="create-a-resource-pool-and-configure-memory"></a><span data-ttu-id="deb32-132">Crear un grupo de recursos de servidor y configurar la memoria</span><span class="sxs-lookup"><span data-stu-id="deb32-132">Create a resource pool and configure memory</span></span>  
 <span data-ttu-id="deb32-133">A la hora de configurar memoria para las tablas optimizadas para memoria, el planeamiento de capacidad debe realizarse en función de MIN_MEMORY_PERCENT, no de MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="deb32-133">When configuring memory for memory-optimized tables, the capacity planning should be done based on MIN_MEMORY_PERCENT, not on MAX_MEMORY_PERCENT.</span></span>  <span data-ttu-id="deb32-134">Vea [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) para obtener más información sobre MIN_MEMORY_PERCENT y MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="deb32-134">See [ALTER RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-pool-transact-sql) for information on MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span> <span data-ttu-id="deb32-135">Esto proporciona una disponibilidad de memoria más predecible en las tablas optimizadas para memoria, ya que MIN_MEMORY_PERCENT produce presión de memoria en otros grupos de recursos de servidor para asegurarse de que se respeta.</span><span class="sxs-lookup"><span data-stu-id="deb32-135">This provides more predictable memory availability for memory-optimized tables as MIN_MEMORY_PERCENT causes memory pressure to other resource pools to make sure it is honored.</span></span> <span data-ttu-id="deb32-136">Para asegurarse de que hay memoria disponible e impedir condiciones de memoria insuficiente, los valores de MIN_MEMORY_PERCENT y MAX_MEMORY_PERCENT deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="deb32-136">To ensure that memory is available and help avoid out-of-memory conditions, the values for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT should be the same.</span></span> <span data-ttu-id="deb32-137">Vea la tabla [Porcentaje de memoria disponible para tablas e índices optimizados para memoria](#percent-of-memory-available-for-memory-optimized-tables-and-indexes) de abajo para conocer el porcentaje de memoria disponible para las tablas optimizadas para memoria según la cantidad de memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="deb32-137">See [Percent of memory available for memory-optimized tables and indexes](#percent-of-memory-available-for-memory-optimized-tables-and-indexes) below for the percent of memory available for memory-optimized tables based on the amount of committed memory.</span></span>  
  
 <span data-ttu-id="deb32-138">Vea [Prácticas recomendadas: usar OLTP en memoria en un entorno de máquinas virtuales](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) para obtener más información sobre cómo trabajar en un entorno de máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="deb32-138">See [Best Practices: Using In-Memory OLTP in a VM environment](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) for more information when working in a VM environment.</span></span>  
  
 <span data-ttu-id="deb32-139">El siguiente código [!INCLUDE[tsql](../../includes/tsql-md.md)] crea un grupo de recursos de servidor denominado Pool_IMOLTP con la mitad de memoria disponible para su uso.</span><span class="sxs-lookup"><span data-stu-id="deb32-139">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] code creates a resource pool named Pool_IMOLTP with half of the memory available for its use.</span></span>  <span data-ttu-id="deb32-140">Una vez creado el grupo, hay que reconfigurar el Regulador de recursos para incluir Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="deb32-140">After the pool is created Resource Governor is reconfigured to include Pool_IMOLTP.</span></span>  
  
```sql  
-- set MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT to the same value  
CREATE RESOURCE POOL Pool_IMOLTP   
  WITH   
    ( MIN_MEMORY_PERCENT = 63,   
    MAX_MEMORY_PERCENT = 63 );  
GO  
  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
## <a name="bind-the-database-to-the-pool"></a><span data-ttu-id="deb32-141">Enlazar la base de datos al grupo</span><span class="sxs-lookup"><span data-stu-id="deb32-141">Bind the database to the pool</span></span>  
 <span data-ttu-id="deb32-142">Use la función del sistema `sp_xtp_bind_db_resource_pool` para enlazar la base de datos al grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="deb32-142">Use the system function `sp_xtp_bind_db_resource_pool` to bind the database to the resource pool.</span></span> <span data-ttu-id="deb32-143">La función utiliza dos parámetros: el nombre de la base de datos y el nombre del grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="deb32-143">The function takes two parameters: the database name and the resource pool name.</span></span>  
  
 <span data-ttu-id="deb32-144">El siguiente código [!INCLUDE[tsql](../../includes/tsql-md.md)] define un enlace de la base de datos IMOLTP_DB con el grupo de recursos de servidor Pool_IMOLTP.</span><span class="sxs-lookup"><span data-stu-id="deb32-144">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] defines a binding of the database IMOLTP_DB to the resource pool Pool_IMOLTP.</span></span> <span data-ttu-id="deb32-145">El enlace no surte efecto hasta que la base de datos pase a estar en línea.</span><span class="sxs-lookup"><span data-stu-id="deb32-145">The binding does not become effective until you bring the database online.</span></span>  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
 <span data-ttu-id="deb32-146">La función del sistema sp_xtp_bind_db_resource_pool usa dos parámetros de cadena: database_name y pool_name.</span><span class="sxs-lookup"><span data-stu-id="deb32-146">The system function sp_xtp_bind_db_resourece_pool takes two string parameters: database_name and pool_name.</span></span>  
  
## <a name="confirm-the-binding"></a><span data-ttu-id="deb32-147">Confirmar el enlace</span><span class="sxs-lookup"><span data-stu-id="deb32-147">Confirm the binding</span></span>  
 <span data-ttu-id="deb32-148">Confirme el enlace, teniendo en cuenta el identificador del grupo de recursos de servidor para IMOLTP_DB.</span><span class="sxs-lookup"><span data-stu-id="deb32-148">Confirm the binding, noting the resource pool id for IMOLTP_DB.</span></span> <span data-ttu-id="deb32-149">No puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="deb32-149">It should not be NULL.</span></span>  
  
```sql  
SELECT d.database_id, d.name, d.resource_pool_id  
FROM sys.databases d  
GO  
```  
  
## <a name="make-the-binding-effective"></a><span data-ttu-id="deb32-150">Activar el enlace</span><span class="sxs-lookup"><span data-stu-id="deb32-150">Make the binding effective</span></span>  
 <span data-ttu-id="deb32-151">Debe poner la base de datos sin conexión y volver a ponerla en línea después de enlazarla al grupo de recursos de servidor para que el enlace surta efecto.</span><span class="sxs-lookup"><span data-stu-id="deb32-151">You must take the database offline and back online after binding it to the resource pool for binding to take effect.</span></span> <span data-ttu-id="deb32-152">Si la base de datos se enlazó a otro grupo diferente, esto quita la memoria asignada del grupo de recursos de servidor anterior y las asignaciones de memoria para la tabla y los índices optimizados para memoria provendrán ahora del grupo de recursos de servidor recién enlazado a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="deb32-152">If your database was bound to an a different pool earlier, this removes the allocated memory from the previous resource pool and memory allocations for your memory-optimized table and indexes will now come from the resource pool newly bound with the database.</span></span>  
  
```sql  
USE master  
GO  
  
ALTER DATABASE IMOLTP_DB SET OFFLINE  
GO  
ALTER DATABASE IMOLTP_DB SET ONLINE  
GO  
  
USE IMOLTP_DB  
GO  
```  
  
 <span data-ttu-id="deb32-153">Ahora, la base de datos está enlazada al grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="deb32-153">And now, the database is bound to the resource pool.</span></span>  
  
## <a name="change-min-memory-percent-and-max-memory-percent-on-an-existing-pool"></a><span data-ttu-id="deb32-154">Cambiar el porcentaje de memoria mínima y el porcentaje máximo de memoria en un grupo existente</span><span class="sxs-lookup"><span data-stu-id="deb32-154">Change MIN MEMORY PERCENT and MAX MEMORY PERCENT on an existing pool</span></span>  
 <span data-ttu-id="deb32-155">Si agrega memoria adicional al servidor o si cambia la cantidad de memoria necesaria para las tablas optimizadas para memoria, puede ser necesario modificar el valor de MIN_MEMORY_PERCENT y MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="deb32-155">If you add additional memory to the server or the amount of memory needed for your memory-optimized tables changes, you may need to alter the value of MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span> <span data-ttu-id="deb32-156">Los pasos siguientes muestran cómo modificar el valor de MIN_MEMORY_PERCENT y MAX_MEMORY_PERCENT en un grupo de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="deb32-156">The following steps show you how to alter the value of MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT on a resource pool.</span></span> <span data-ttu-id="deb32-157">Vea la próxima sección para obtener información sobre qué valores se deben usar para MIN_MEMORY_PERCENT y MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="deb32-157">See the section below, for guidance on what values to use for MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span>  <span data-ttu-id="deb32-158">Vea el tema [Prácticas recomendadas: usar OLTP en memoria en un entorno de máquinas virtuales](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="deb32-158">See the topic [Best Practices: Using In-Memory OLTP in a VM environment](../../database-engine/using-in-memory-oltp-in-a-vm-environment.md) for more information.</span></span>  
  
1.  <span data-ttu-id="deb32-159">Utilice `ALTER RESOURCE POOL` para cambiar el valor de MIN_MEMORY_PERCENT y MAX_MEMORY_PERCENT.</span><span class="sxs-lookup"><span data-stu-id="deb32-159">Use `ALTER RESOURCE POOL` to change the value of both MIN_MEMORY_PERCENT and MAX_MEMORY_PERCENT.</span></span>  
  
2.  <span data-ttu-id="deb32-160">Use `ALTER RESURCE GOVERNOR` para reconfigurar el regulador de recursos con los nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="deb32-160">Use `ALTER RESURCE GOVERNOR` to reconfigure the Resource Governor with the new values.</span></span>  
  
 <span data-ttu-id="deb32-161">**Código de ejemplo**</span><span class="sxs-lookup"><span data-stu-id="deb32-161">**Sample Code**</span></span>  
  
```sql  
ALTER RESOURCE POOL Pool_IMOLTP  
WITH  
     ( MIN_MEMORY_PERCENT = 70,  
       MAX_MEMORY_PERCENT = 70 )   
GO  
  
-- reconfigure the Resource Governor  
ALTER RESOURCE GOVERNOR RECONFIGURE  
GO  
```  
  
## <a name="percent-of-memory-available-for-memory-optimized-tables-and-indexes"></a><span data-ttu-id="deb32-162">Porcentaje de memoria disponible para tablas e índices optimizados para memoria</span><span class="sxs-lookup"><span data-stu-id="deb32-162">Percent of memory available for memory-optimized tables and indexes</span></span>  
 <span data-ttu-id="deb32-163">Si asigna una base de datos con tablas optimizadas para memoria y una carga de trabajo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al mismo grupo de recursos de servidor, el regulador de recursos establece un umbral interno para uso de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] de modo que los usuarios del grupo no experimenten conflictos al usar el grupo.</span><span class="sxs-lookup"><span data-stu-id="deb32-163">If you map a database with memory-optimized tables and a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] workload to the same resource pool, the Resource Governor sets an internal threshold for [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] use so that the users of the pool do not have conflicts over pool usage.</span></span> <span data-ttu-id="deb32-164">En general, el umbral para el uso de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] es aproximadamente el 80 % del valor del grupo.</span><span class="sxs-lookup"><span data-stu-id="deb32-164">Generally speaking, the threshold for [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] use is about 80% of the pool.</span></span> <span data-ttu-id="deb32-165">En la tabla siguiente se muestran los umbrales reales para diversos tamaños de memoria.</span><span class="sxs-lookup"><span data-stu-id="deb32-165">The following table shows actual thresholds for various memory sizes.</span></span>  
  
 <span data-ttu-id="deb32-166">Al crear un grupo de recursos de servidor dedicado para la base de datos de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] , debe evaluar cuánta memoria física necesita para las tablas en memoria después de tener en cuenta las versiones de filas y el aumento de datos.</span><span class="sxs-lookup"><span data-stu-id="deb32-166">When you create a dedicated resource pool for the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] database, you need to estimate how much physical memory you need for the in-memory tables after accounting for row versions and data growth.</span></span> <span data-ttu-id="deb32-167">Una vez calculada la memoria necesaria, puede crear un grupo de recursos de servidor con un porcentaje de memoria de destino de confirmación para la instancia de SQL como se refleja en la columna "committed_target_kb" en la DMV `sys.dm_os_sys_info` (vea [sys.dm_os_sys_info](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-sys-info-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="deb32-167">Once estimate the memory needed, you create a resource pool with a percent of the commit target memory for SQL Instance as reflected by column 'committed_target_kb' in the DMV `sys.dm_os_sys_info` (see [sys.dm_os_sys_info](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-sys-info-transact-sql)).</span></span> <span data-ttu-id="deb32-168">Por ejemplo, puede crear un grupo de recursos de servidor P1 con el 40 % de la memoria total disponible para la instancia.</span><span class="sxs-lookup"><span data-stu-id="deb32-168">For example, you can create a resource pool P1 with 40% of the total memory available to the instance.</span></span> <span data-ttu-id="deb32-169">Fuera de este 40 %, el motor de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] obtiene un porcentaje inferior para almacenar los datos de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="deb32-169">Out of this 40%, the [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] engine gets a smaller percent to store [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] data.</span></span>  <span data-ttu-id="deb32-170">Esto se hace para asegurarse de que [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] no usa toda la memoria de este grupo.</span><span class="sxs-lookup"><span data-stu-id="deb32-170">This is done to make sure [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] does not consume all the memory from this pool.</span></span>  <span data-ttu-id="deb32-171">Este valor del porcentaje menor depende de la memoria confirmada de destino.</span><span class="sxs-lookup"><span data-stu-id="deb32-171">This value of the smaller percent depends upon the Target committed Memory.</span></span> <span data-ttu-id="deb32-172">En la siguiente tabla se describe la memoria disponible para la base de datos de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] en un grupo de recursos de servidor (designado o predeterminado) antes de que se genere un error de OOM.</span><span class="sxs-lookup"><span data-stu-id="deb32-172">The following table describes memory available to [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] database in a resource pool (named or default) before an OOM error is raised.</span></span>  
  
|<span data-ttu-id="deb32-173">Memoria asignada de destino</span><span class="sxs-lookup"><span data-stu-id="deb32-173">Target Committed Memory</span></span>|<span data-ttu-id="deb32-174">Porcentaje disponible para tablas en memoria</span><span class="sxs-lookup"><span data-stu-id="deb32-174">Percent available for in-memory tables</span></span>|  
|-----------------------------|---------------------------------------------|  
|<span data-ttu-id="deb32-175"><= 8 GB</span><span class="sxs-lookup"><span data-stu-id="deb32-175"><= 8 GB</span></span>|<span data-ttu-id="deb32-176">70%</span><span class="sxs-lookup"><span data-stu-id="deb32-176">70%</span></span>|  
|<span data-ttu-id="deb32-177"><= 16 GB</span><span class="sxs-lookup"><span data-stu-id="deb32-177"><= 16 GB</span></span>|<span data-ttu-id="deb32-178">75 %</span><span class="sxs-lookup"><span data-stu-id="deb32-178">75%</span></span>|  
|<span data-ttu-id="deb32-179"><= 32 GB</span><span class="sxs-lookup"><span data-stu-id="deb32-179"><= 32 GB</span></span>|<span data-ttu-id="deb32-180">80 %</span><span class="sxs-lookup"><span data-stu-id="deb32-180">80%</span></span>|  
|<span data-ttu-id="deb32-181">\<= 96 GB</span><span class="sxs-lookup"><span data-stu-id="deb32-181">\<= 96 GB</span></span>|<span data-ttu-id="deb32-182">85%</span><span class="sxs-lookup"><span data-stu-id="deb32-182">85%</span></span>|  
|<span data-ttu-id="deb32-183">>96 GB</span><span class="sxs-lookup"><span data-stu-id="deb32-183">>96 GB</span></span>|<span data-ttu-id="deb32-184">90%</span><span class="sxs-lookup"><span data-stu-id="deb32-184">90%</span></span>|  
  
 <span data-ttu-id="deb32-185">Por ejemplo, si la "memoria confirmada de destino" es de 100 GB y calcula que las tablas e índices optimizados para memoria necesitan 60 GB de memoria, puede crear un grupo de recursos de servidor con MAX_MEMORY_PERCENT = 67 (60 GB necesarios / 0,90 = 66,667 GB - redondear hasta 67 GB; 67 GB / 100 GB instalados = 67 %) para garantizar que los objetos de [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] tengan los 60 GB que necesitan.</span><span class="sxs-lookup"><span data-stu-id="deb32-185">For example, if your 'target committed memory' is 100 GB, and you estimate your memory-optimized tables and indexes need 60GBof memory, then you can create a resource pool with MAX_MEMORY_PERCENT = 67 (60GB needed / 0.90 = 66.667GB - round up to 67GB; 67GB / 100GB installed = 67%) to ensure that your [!INCLUDE[hek_2](../../../includes/hek-2-md.md)] objects have the 60GB they need.</span></span>  
  
 <span data-ttu-id="deb32-186">Una vez que una base de datos se ha enlazado a un grupo de recursos de servidor con nombre, utilice la consulta siguiente para ver las asignaciones de memoria en distintos grupos de recursos de servidor.</span><span class="sxs-lookup"><span data-stu-id="deb32-186">Once a database has been bound to a named resource pool, use the following query to see memory allocations across different resource pools.</span></span>  
  
```sql  
SELECT pool_id  
     , Name  
     , min_memory_percent  
     , max_memory_percent  
     , max_memory_kb/1024 AS max_memory_mb  
     , used_memory_kb/1024 AS used_memory_mb   
     , target_memory_kb/1024 AS target_memory_mb  
   FROM sys.dm_resource_governor_resource_pools  
```  
  
 <span data-ttu-id="deb32-187">Esta salida de ejemplo muestra que la memoria usada por los objetos optimizados para memoria es de 1356 MB en el grupo de recursos de servidor, PoolIMOLTP, con un límite superior de 2307 MB.</span><span class="sxs-lookup"><span data-stu-id="deb32-187">This sample output shows that the memory taken by memory-optimized objects is 1356 MB in resource pool, PoolIMOLTP, with an upper bound of 2307 MB.</span></span> <span data-ttu-id="deb32-188">Este límite superior controla la memoria total que el usuario puede emplear y los objetos del sistema optimizados para memoria asignados a este grupo.</span><span class="sxs-lookup"><span data-stu-id="deb32-188">This upper bound controls the total memory that can be taken by user and system memory-optimized objects mapped to this pool.</span></span>  
  
 <span data-ttu-id="deb32-189">**Salida del ejemplo** </span><span class="sxs-lookup"><span data-stu-id="deb32-189">**Sample Output** </span></span>  
<span data-ttu-id="deb32-190">Esta salida es de la base de datos y las tablas que hemos creado antes.</span><span class="sxs-lookup"><span data-stu-id="deb32-190">This output is from the database and tables we created above.</span></span>  
  
```  
pool_id     Name        min_memory_percent max_memory_percent max_memory_mb used_memory_mb target_memory_mb  
----------- ----------- ------------------ ------------------ ------------- -------------- ----------------   
1           internal    0                  100                3845          125            3845  
2           default     0                  100                3845          32             3845  
259         PoolIMOLTP 0                  100                3845          1356           2307  
```  
  
 <span data-ttu-id="deb32-191">Para obtener más información, vea [sys.dm_resource_governor_resource_pools (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="deb32-191">For more information see [sys.dm_resource_governor_resource_pools (Transact-SQL)](/sql/relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pools-transact-sql).</span></span>  
  
 <span data-ttu-id="deb32-192">Si no enlaza la base de datos a un grupo de recursos de servidor con nombre, se enlaza al grupo "default".</span><span class="sxs-lookup"><span data-stu-id="deb32-192">If you do not bind your database to a named resource pool, it is bound to the 'default' pool.</span></span> <span data-ttu-id="deb32-193">Puesto que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa el grupo de recursos de servidor predeterminado para la mayoría de las demás asignaciones, no podrá supervisar con precisión la memoria usada por las tablas optimizadas para memoria mediante la DMV sys.dm_resource_governor_resource_pools para la base de datos de interés.</span><span class="sxs-lookup"><span data-stu-id="deb32-193">Since default resource pool is used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for most other allocations, you will not be able to monitor memory consumed by memory-optimized tables using the DMV sys.dm_resource_governor_resource_pools accurately for the database of interest.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deb32-194">Consulte también</span><span class="sxs-lookup"><span data-stu-id="deb32-194">See Also</span></span>  
 <span data-ttu-id="deb32-195">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="deb32-195">[sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="deb32-196">[sys.sp_xtp_unbind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="deb32-196">[sys.sp_xtp_unbind_db_resource_pool &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="deb32-197">[Regulador de recursos](../resource-governor/resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="deb32-197">[Resource Governor](../resource-governor/resource-governor.md) </span></span>  
 <span data-ttu-id="deb32-198">[Grupo de recursos de servidor del regulador de recursos](../resource-governor/resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="deb32-198">[Resource Governor Resource Pool](../resource-governor/resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="deb32-199">[Crear un grupo de recursos de servidor](../resource-governor/create-a-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="deb32-199">[Create a Resource Pool](../resource-governor/create-a-resource-pool.md) </span></span>  
 <span data-ttu-id="deb32-200">[Cambiar la configuración del grupo de recursos de servidor](../resource-governor/change-resource-pool-settings.md) </span><span class="sxs-lookup"><span data-stu-id="deb32-200">[Change Resource Pool Settings](../resource-governor/change-resource-pool-settings.md) </span></span>  
 [<span data-ttu-id="deb32-201">Eliminar un grupo de recursos de servidor</span><span class="sxs-lookup"><span data-stu-id="deb32-201">Delete a Resource Pool</span></span>](../resource-governor/delete-a-resource-pool.md)  
  
  
