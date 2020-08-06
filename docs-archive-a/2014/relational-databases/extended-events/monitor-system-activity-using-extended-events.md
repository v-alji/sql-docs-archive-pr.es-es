---
title: Supervisión de la actividad del sistema mediante eventos extendidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- xe
- extended events [SQL Server], monitoring system activity
ms.assetid: d83ad88f-818c-49fe-a9a9-299f704fca53
author: rothja
ms.author: jroth
ms.openlocfilehash: d847d156d8244ede533e684c9e6b753d7d7b5047
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662930"
---
# <a name="monitor-system-activity-using-extended-events"></a><span data-ttu-id="43a37-102">Supervisar la actividad del sistema mediante eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="43a37-102">Monitor System Activity Using Extended Events</span></span>
  <span data-ttu-id="43a37-103">En el siguiente procedimiento se muestra el uso de Extended Events con el Seguimiento de eventos para Windows (ETW) para supervisar la actividad del sistema.</span><span class="sxs-lookup"><span data-stu-id="43a37-103">This procedure illustrates how Extended Events can be used with Event Tracing for Windows (ETW) to monitor system activity.</span></span> <span data-ttu-id="43a37-104">El procedimiento también muestra el uso de las instrucciones CREATE EVENT SESSION, ALTER EVENT SESSION y DROP EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="43a37-104">The procedure also shows how the CREATE EVENT SESSION, ALTER EVENT SESSION, and DROP EVENT SESSION statements are used.</span></span>  
  
 <span data-ttu-id="43a37-105">Para realizar estas tareas debe usar el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y llevar a cabo el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="43a37-105">Accomplishing these tasks involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span> <span data-ttu-id="43a37-106">El procedimiento también utiliza el símbolo del sistema para ejecutar los comandos ETW.</span><span class="sxs-lookup"><span data-stu-id="43a37-106">The procedure also requires using the command prompt to run ETW commands.</span></span>  
  
### <a name="to-monitor-system-activity-using-extended-events"></a><span data-ttu-id="43a37-107">Para supervisar la actividad del sistema mediante Extended Events</span><span class="sxs-lookup"><span data-stu-id="43a37-107">To monitor system activity using Extended Events</span></span>  
  
1.  <span data-ttu-id="43a37-108">En el Editor de consultas, emita las instrucciones siguientes para crear una sesión de eventos y agregar dos eventos.</span><span class="sxs-lookup"><span data-stu-id="43a37-108">In Query Editor, issue the following statements to create an event session and add two events.</span></span> <span data-ttu-id="43a37-109">Estos eventos, checkpoint_begin y checkpoint_end, se activan al principio y al final de un punto de comprobación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="43a37-109">These events, checkpoint_begin and checkpoint_end, fire at the beginning and end of a database checkpoint.</span></span>  
  
    ```  
    CREATE EVENT SESSION test0  
    ON SERVER  
    ADD EVENT sqlserver.checkpoint_begin,  
    ADD EVENT sqlserver.checkpoint_end  
    WITH (MAX_DISPATCH_LATENCY = 1 SECONDS)  
    go  
    ```  
  
2.  <span data-ttu-id="43a37-110">Agregue el destino de creación de depósitos con 32 depósitos para contar el número de puntos de comprobación en función del identificador de base de datos.</span><span class="sxs-lookup"><span data-stu-id="43a37-110">Add the bucketing target with 32 buckets to count the number of checkpoints based on the database ID.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.histogram  
    (  
          SET slots = 32, filtering_event_name = 'sqlserver.checkpoint_end', source_type = 0, source = 'database_id'  
    )  
    go  
    ```  
  
3.  <span data-ttu-id="43a37-111">Emita las instrucciones siguientes para agregar el destino ETW.</span><span class="sxs-lookup"><span data-stu-id="43a37-111">Issue the following statements to add the ETW target.</span></span> <span data-ttu-id="43a37-112">Esto le permitirá ver los eventos inicial y final, utilizados para determinar el tiempo que tarda el punto de comprobación.</span><span class="sxs-lookup"><span data-stu-id="43a37-112">This will enable you to see the begin and end events, which is used to determine how long the checkpoint takes.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    ADD TARGET package0.etw_classic_sync_target  
    go  
    ```  
  
4.  <span data-ttu-id="43a37-113">Emita las instrucciones siguientes para iniciar la sesión y comenzar la recopilación de eventos.</span><span class="sxs-lookup"><span data-stu-id="43a37-113">Issue the following statements to start the session and begin event collection.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = start  
    go  
    ```  
  
5.  <span data-ttu-id="43a37-114">Emita las instrucciones siguientes para activar tres eventos.</span><span class="sxs-lookup"><span data-stu-id="43a37-114">Issue the following statements to cause three events to fire.</span></span>  
  
    ```  
    USE tempdb  
          checkpoint  
    go  
    USE master  
          checkpoint  
          checkpoint  
    go  
    ```  
  
6.  <span data-ttu-id="43a37-115">Emita las instrucciones siguientes para ver los recuentos de eventos.</span><span class="sxs-lookup"><span data-stu-id="43a37-115">Issue the following statements to view the event counts.</span></span>  
  
    ```  
    SELECT CAST(xest.target_data AS xml) Bucketizer_Target_Data_in_XML  
    FROM sys.dm_xe_session_targets xest  
    JOIN sys.dm_xe_sessions xes ON xes.address = xest.event_session_address  
    JOIN sys.server_event_sessions ses ON xes.name = ses.name  
    WHERE xest.target_name = 'histogram' AND xes.name = 'test0'  
    go  
    ```  
  
7.  <span data-ttu-id="43a37-116">En el símbolo del sistema, ejecute los comandos siguientes para ver los datos ETW.</span><span class="sxs-lookup"><span data-stu-id="43a37-116">At the command prompt, issue the following commands to view the ETW data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43a37-117"> Para obtener ayuda sobre el comando **tracerpt** , en el símbolo del sistema, escriba `tracerpt /?`.</span><span class="sxs-lookup"><span data-stu-id="43a37-117">To get help for the **tracerpt** command, at the command prompt, enter `tracerpt /?`.</span></span>  
  
    ```  
    logman query -ets --- List the ETW sessions. This is optional.  
    logman update XE_DEFAULT_ETW_SESSION -fd -ets --- Flush the ETW log.  
    tracerpt %temp%\xeetw.etl -o xeetw.txt --- Dump the events so they can be seen.  
    ```  
  
8.  <span data-ttu-id="43a37-118">Emita las instrucciones siguientes para detener la sesión de eventos y quitarla del servidor.</span><span class="sxs-lookup"><span data-stu-id="43a37-118">Issue the following statements to stop the event session and remove it from the server.</span></span>  
  
    ```  
    ALTER EVENT SESSION test0  
    ON SERVER  
    STATE = STOP  
    go  
  
    DROP EVENT SESSION test0  
    ON SERVER  
    go  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="43a37-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43a37-119">See Also</span></span>  
 <span data-ttu-id="43a37-120">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="43a37-120">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="43a37-121">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="43a37-121">[ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql) </span></span>  
 <span data-ttu-id="43a37-122">[DROP EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="43a37-122">[DROP EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="43a37-123">Vistas de catálogo de eventos extendidos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="43a37-123">Extended Events Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql)  
 <span data-ttu-id="43a37-124">[Vistas de administración dinámica de eventos extendidos](../views/views.md) </span><span class="sxs-lookup"><span data-stu-id="43a37-124">[Extended Events Dynamic Management Views](../views/views.md) </span></span>  
 [<span data-ttu-id="43a37-125">Destinos de SQL Server Extended Events</span><span class="sxs-lookup"><span data-stu-id="43a37-125">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)  
  
  
