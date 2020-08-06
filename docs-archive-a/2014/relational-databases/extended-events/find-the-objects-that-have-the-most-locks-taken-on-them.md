---
title: Buscar los objetos que han obtenido más bloqueos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- objects [SQL Server], extended events
- xe
- extended events [SQL Server], locks
- objects [SQL Server], locks
ms.assetid: fcbadbda-c91c-43f0-a1b5-601e40110e07
author: rothja
ms.author: jroth
ms.openlocfilehash: 345c5f179358bd7b8df587b76c9c6053235d3a73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662931"
---
# <a name="find-the-objects-that-have-the-most-locks-taken-on-them"></a><span data-ttu-id="28a71-102">Buscar los objetos que han obtenido más bloqueos</span><span class="sxs-lookup"><span data-stu-id="28a71-102">Find the Objects That Have the Most Locks Taken on Them</span></span>
  <span data-ttu-id="28a71-103">A menudo, los administradores de bases de datos necesitan identificar el origen de bloqueos que reducen el rendimiento de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="28a71-103">Database administrators often need to identify the source of locks that are hindering database performance.</span></span>  
  
 <span data-ttu-id="28a71-104">Por ejemplo, suponga que está supervisando posibles cuellos de botella en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="28a71-104">For example, you are monitoring your production server for any possible bottlenecks.</span></span> <span data-ttu-id="28a71-105">Sospecha que podría haber recursos muy disputados y desearía saber cuántos bloqueos se han realizado en esos objetos.</span><span class="sxs-lookup"><span data-stu-id="28a71-105">You suspect that there might be highly contested resources, and would like to know how many locks are taken on those objects.</span></span> <span data-ttu-id="28a71-106">Una vez identificados los objetos que se bloquean con más con frecuencia, se pueden tomar medidas para optimizar el acceso a dichos objetos.</span><span class="sxs-lookup"><span data-stu-id="28a71-106">Once the most frequently locked objects are identified, steps can be taken to optimize access to the contended objects.</span></span>  
  
 <span data-ttu-id="28a71-107">Para ello, utilice el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28a71-107">To do this, use Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="to-find-the-objects-that-have-the-most-locks"></a><span data-ttu-id="28a71-108">Para buscar los objetos que han obtenido más bloqueos</span><span class="sxs-lookup"><span data-stu-id="28a71-108">To find the objects that have the most locks</span></span>  
  
1.  <span data-ttu-id="28a71-109">En el Editor de consultas, emita las instrucciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="28a71-109">In Query Editor, issue the following statements.</span></span>  
  
    ```  
    -- Find objects in a particular database that have the most  
    -- lock acquired. This sample uses AdventureWorksDW2012.  
    -- Create the session and add an event and target.  
    --   
    IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='LockCounts')  
    DROP EVENT session LockCounts ON SERVER  
    GO  
    DECLARE @dbid int  
  
    SELECT @dbid = db_id('AdventureWorksDW2012')  
  
    DECLARE @sql nvarchar(1024)  
    SET @sql = '  
    CREATE event session LockCounts ON SERVER  
    ADD EVENT sqlserver.lock_acquired (WHERE database_id =' + CAST(@dbid AS nvarchar) +')  
    ADD TARGET package0.histogram(   
    SET filtering_event_name=''sqlserver.lock_acquired'', source_type=0, source=''resource_0'')'  
  
    EXEC (@sql)  
    GO  
    ALTER EVENT session LockCounts ON SERVER   
    STATE=start  
    GO  
    --   
    -- Create a simple workload that takes locks.  
    --   
    USE AdventureWorksDW2012  
    GO  
    SELECT TOP 1 * FROM dbo.vAssocSeqLineItems  
    GO  
    -- The histogram target output is available from the   
    -- sys.dm_xe_session_targets dynamic management view in  
    -- XML format.  
    -- The following query joins the bucketizing target output with  
    -- sys.objects to obtain the object names.  
    --  
    SELECT name, object_id, lock_count FROM   
    (SELECT objstats.value('.','bigint') AS lobject_id,   
    objstats.value('@count', 'bigint') AS lock_count  
    FROM (  
    SELECT CAST(xest.target_data AS XML)  
    LockData  
    FROM sys.dm_xe_session_targets xest  
    JOIN sys.dm_xe_sessions xes ON xes.address = xest.event_session_address  
    JOIN sys.server_event_sessions ses ON xes.name = ses.name  
    WHERE xest.target_name = 'histogram' AND xes.name = 'LockCounts'  
    ) Locks  
    CROSS APPLY LockData.nodes('//HistogramTarget/Slot') AS T(objstats)  
     ) LockedObjects   
    INNER JOIN sys.objects o  
    ON LockedObjects.lobject_id = o.object_id  
    WHERE o.type != 'S' AND o.type = 'U'  
    ORDER BY lock_count desc  
    GO  
    --   
    -- Stop the event session.  
    --   
    ALTER EVENT SESSION LockCounts ON SERVER  
    state=stop  
    GO  
  
    ```  
  
 <span data-ttu-id="28a71-110">Una vez finalizadas las instrucciones de este procedimiento, la pestaña **Resultados** del Editor de consultas mostrará las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="28a71-110">After the statements in this procedure finish, the **Results** tab of Query Editor displays the following columns:</span></span>  
  
-   <span data-ttu-id="28a71-111">name</span><span class="sxs-lookup"><span data-stu-id="28a71-111">name</span></span>  
  
-   <span data-ttu-id="28a71-112">object_id</span><span class="sxs-lookup"><span data-stu-id="28a71-112">object_id</span></span>  
  
-   <span data-ttu-id="28a71-113">lock_count</span><span class="sxs-lookup"><span data-stu-id="28a71-113">lock_count</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a71-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28a71-114">See Also</span></span>  
 <span data-ttu-id="28a71-115">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28a71-115">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="28a71-116">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28a71-116">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 <span data-ttu-id="28a71-117">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28a71-117">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span></span>  
 <span data-ttu-id="28a71-118">[Sys. dm_xe_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-sessions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28a71-118">[sys.dm_xe_sessions &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-sessions-transact-sql) </span></span>  
 [<span data-ttu-id="28a71-119">sys.server_event_sessions &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="28a71-119">sys.server_event_sessions &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-server-event-sessions-transact-sql)  
  
  