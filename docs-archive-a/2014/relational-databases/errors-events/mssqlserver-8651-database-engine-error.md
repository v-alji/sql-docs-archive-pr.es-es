---
title: MSSQLSERVER_8651 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8651 (Database Engine error)
ms.assetid: 4cc3498d-5449-4c4e-b1f9-3271831c725a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 43a385350a05edee3759ab83d318e365f5b4f3e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745306"
---
# <a name="mssqlserver_8651"></a><span data-ttu-id="38fe4-102">MSSQLSERVER_8651</span><span class="sxs-lookup"><span data-stu-id="38fe4-102">MSSQLSERVER_8651</span></span>
    
## <a name="details"></a><span data-ttu-id="38fe4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="38fe4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="38fe4-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="38fe4-104">Product Name</span></span>|<span data-ttu-id="38fe4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="38fe4-105">SQL Server</span></span>|  
|<span data-ttu-id="38fe4-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="38fe4-106">Event ID</span></span>|<span data-ttu-id="38fe4-107">8651</span><span class="sxs-lookup"><span data-stu-id="38fe4-107">8651</span></span>|  
|<span data-ttu-id="38fe4-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="38fe4-108">Event Source</span></span>|<span data-ttu-id="38fe4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="38fe4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="38fe4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="38fe4-110">Component</span></span>|<span data-ttu-id="38fe4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="38fe4-111">SQLEngine</span></span>|  
|<span data-ttu-id="38fe4-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="38fe4-112">Symbolic Name</span></span>|<span data-ttu-id="38fe4-113">MEMGRANT_ERR</span><span class="sxs-lookup"><span data-stu-id="38fe4-113">MEMGRANT_ERR</span></span>|  
|<span data-ttu-id="38fe4-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="38fe4-114">Message Text</span></span>|<span data-ttu-id="38fe4-115">No se puede realizar la operación solicitada, la memoria de consulta mínima no está disponible.</span><span class="sxs-lookup"><span data-stu-id="38fe4-115">Could not perform the requested operation because the minimum query memory is not available.</span></span> <span data-ttu-id="38fe4-116">Reduzca el valor de la opción de configuración del servidor 'min memory per query'.</span><span class="sxs-lookup"><span data-stu-id="38fe4-116">Decrease the configured value for the 'min memory per query' server configuration option.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="38fe4-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="38fe4-117">Explanation</span></span>  
 <span data-ttu-id="38fe4-118">Otros procesos están consumiendo memoria del servidor (ejerciendo presión en la memoria del servidor).</span><span class="sxs-lookup"><span data-stu-id="38fe4-118">Other processes are consuming server memory (exerting memory pressure in the server).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="38fe4-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="38fe4-119">User Action</span></span>  
 <span data-ttu-id="38fe4-120">Reduzca el valor configurado de la opción de configuración del servidor 'min memory per query' o reduzca la carga de consultas del servidor.</span><span class="sxs-lookup"><span data-stu-id="38fe4-120">Either decrease the configured value for the min memory per query' server configuration option or reduce the query load to the server.</span></span>  
  
 <span data-ttu-id="38fe4-121">En la siguiente lista se describen los pasos generales que ayudarán a resolver los errores de memoria:</span><span class="sxs-lookup"><span data-stu-id="38fe4-121">The following list outlines general steps that will help in troubleshooting memory errors:</span></span>  
  
1.  <span data-ttu-id="38fe4-122">Compruebe si otras aplicaciones o servicios están consumiendo memoria en este servidor.</span><span class="sxs-lookup"><span data-stu-id="38fe4-122">Verify whether other applications or services are consuming memory on this server.</span></span> <span data-ttu-id="38fe4-123">Vuelva a configurar las aplicaciones o servicios menos críticos para que consuman menos memoria.</span><span class="sxs-lookup"><span data-stu-id="38fe4-123">Reconfigure less critical applications or services to consume less memory.</span></span>  
  
2.  <span data-ttu-id="38fe4-124">Empiece a recopilar los contadores del monitor de rendimiento para **SQL Server: Administrador de búfer**, **SQL Server: Administrador de memoria**.</span><span class="sxs-lookup"><span data-stu-id="38fe4-124">Start collecting performance monitor counters for **SQL Server: Buffer Manager**, **SQL Server: Memory Manager**.</span></span>  
  
3.  <span data-ttu-id="38fe4-125">Compruebe los siguientes parámetros de configuración de memoria de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="38fe4-125">Check the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory configuration parameters:</span></span>  
  
    -   <span data-ttu-id="38fe4-126">**memoria de servidor máxima**</span><span class="sxs-lookup"><span data-stu-id="38fe4-126">**max server memory**</span></span>  
  
    -   <span data-ttu-id="38fe4-127">**memoria de servidor mínima**</span><span class="sxs-lookup"><span data-stu-id="38fe4-127">**min server memory**</span></span>  
  
    -   <span data-ttu-id="38fe4-128">**memoria mínima por consulta**</span><span class="sxs-lookup"><span data-stu-id="38fe4-128">**min memory per query**</span></span>  
  
     <span data-ttu-id="38fe4-129">Observe si hay algún valor fuera de lo normal.</span><span class="sxs-lookup"><span data-stu-id="38fe4-129">Notice unusual settings.</span></span> <span data-ttu-id="38fe4-130">Corríjalos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="38fe4-130">Correct them as necessary.</span></span> <span data-ttu-id="38fe4-131">La configuración predeterminada se enumera en "Establecer las opciones de configuración del servidor" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="38fe4-131">Default settings are listed in "Setting Server Configuration Options" in SQL Server Books Online.</span></span>  
  
4.  <span data-ttu-id="38fe4-132">Compruebe la carga de trabajo (por ejemplo, el número de sesiones simultáneas y las consultas que se están ejecutando actualmente).</span><span class="sxs-lookup"><span data-stu-id="38fe4-132">Check the workload (for example, number of concurrent sessions, currently executing queries).</span></span>  
  
 <span data-ttu-id="38fe4-133">Las siguientes acciones pueden hacer que haya más memoria disponible para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="38fe4-133">The following actions may make more memory available to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="38fe4-134">Si otras aplicaciones además de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] están consumiendo recursos, intente detener su ejecución o plantéese ejecutarlas en otro servidor.</span><span class="sxs-lookup"><span data-stu-id="38fe4-134">If applications besides [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are consuming resources, try stopping running these applications or consider running them on a separate server.</span></span> <span data-ttu-id="38fe4-135">Esto quitará presión externa de la memoria.</span><span class="sxs-lookup"><span data-stu-id="38fe4-135">This will remove external memory pressure.</span></span>  
  
-   <span data-ttu-id="38fe4-136">Si ha configurado **max server memory**, aumente su valor.</span><span class="sxs-lookup"><span data-stu-id="38fe4-136">If you have configured **max server memory,** increase its setting.</span></span>  
  
 <span data-ttu-id="38fe4-137">Ejecute los siguientes comandos DBCC para liberar varias cachés de la memoria de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38fe4-137">Run the following DBCC commands to free several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory caches.</span></span>  
  
-   <span data-ttu-id="38fe4-138">DBCC FREESYSTEMCACHE</span><span class="sxs-lookup"><span data-stu-id="38fe4-138">DBCC FREESYSTEMCACHE</span></span>  
  
-   <span data-ttu-id="38fe4-139">DBCC FREESESSIONCACHE</span><span class="sxs-lookup"><span data-stu-id="38fe4-139">DBCC FREESESSIONCACHE</span></span>  
  
-   <span data-ttu-id="38fe4-140">DBCC FREEPROCCACHE</span><span class="sxs-lookup"><span data-stu-id="38fe4-140">DBCC FREEPROCCACHE</span></span>  
  
 <span data-ttu-id="38fe4-141">Si el problema persiste, necesitará investigar más y, posiblemente, reducir la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="38fe4-141">If the problem continues, you will need to investigate further and possibly reduce workload.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38fe4-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38fe4-142">See Also</span></span>  
 <span data-ttu-id="38fe4-143">[DBCC FREESYSTEMCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38fe4-143">[DBCC FREESYSTEMCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesystemcache-transact-sql) </span></span>  
 <span data-ttu-id="38fe4-144">[DBCC FREESESSIONCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38fe4-144">[DBCC FREESESSIONCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freesessioncache-transact-sql) </span></span>  
 <span data-ttu-id="38fe4-145">[DBCC FREEPROCCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="38fe4-145">[DBCC FREEPROCCACHE &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-freeproccache-transact-sql) </span></span>  
 <span data-ttu-id="38fe4-146">[Opciones de configuración de servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="38fe4-146">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="38fe4-147">[Buffer Manager (objeto de SQL Server)](../performance-monitor/sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="38fe4-147">[SQL Server, Buffer Manager Object](../performance-monitor/sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="38fe4-148">Memory Manager (objeto de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="38fe4-148">SQL Server, Memory Manager Object</span></span>](../performance-monitor/sql-server-memory-manager-object.md)  
  
  
