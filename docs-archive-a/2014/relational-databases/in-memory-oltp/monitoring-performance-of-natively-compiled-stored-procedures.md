---
title: Supervisión del rendimiento de los procedimientos almacenados compilados de forma nativa | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 55548cb2-77a8-4953-8b5a-f2778a4f13cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d14d27cdc20c0f090c7a030efe05cfce4842f437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750966"
---
# <a name="monitoring-performance-of-natively-compiled-stored-procedures"></a><span data-ttu-id="adb97-102">Supervisar el rendimiento de los procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="adb97-102">Monitoring Performance of Natively Compiled Stored Procedures</span></span>
  <span data-ttu-id="adb97-103">En este tema se describe cómo supervisar el rendimiento de los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="adb97-103">This topic discusses how you can monitor the performance of natively compiled stored procedures</span></span>  
  
## <a name="using-extended-events"></a><span data-ttu-id="adb97-104">Utilizar eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="adb97-104">Using Extended Events</span></span>  
 <span data-ttu-id="adb97-105">Utilice el evento extendido `sp_statement_completed` para realizar el seguimiento de la ejecución de una consulta.</span><span class="sxs-lookup"><span data-stu-id="adb97-105">Use the `sp_statement_completed` extended event to trace execution of a query.</span></span> <span data-ttu-id="adb97-106">Cree una sesión de eventos extendidos con este evento, opcionalmente con un filtro en object_id para un procedimiento almacenado compilado de forma nativa específico. El evento extendido se genera tras la ejecución de cada consulta.</span><span class="sxs-lookup"><span data-stu-id="adb97-106">Create an extended event session with this event, optionally with a filter on object_id for a particular natively compiled stored procedure, The extended event is raised after the execution of each query.</span></span> <span data-ttu-id="adb97-107">El tiempo de CPU y la duración notificados por el evento extendido indican cuánta CPU utilizó la consulta y el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="adb97-107">The CPU time and duration reported by the extended event indicate how much CPU the query used and the execution time.</span></span> <span data-ttu-id="adb97-108">Un procedimiento almacenado compilado de forma nativa que utiliza mucho tiempo de CPU puede tener problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="adb97-108">A natively compiled stored procedure that uses a lot of CPU time may have performance problems.</span></span>  
  
 <span data-ttu-id="adb97-109">Se puede utilizar `line_number` junto con el `object_id` del evento extendido para investigar la consulta.</span><span class="sxs-lookup"><span data-stu-id="adb97-109">`line_number`, along with the `object_id` in the extended event can be used to investigate the query.</span></span> <span data-ttu-id="adb97-110">La siguiente consulta se puede utilizar para recuperar la definición del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="adb97-110">The following query can be used to retrieve the procedure definition.</span></span> <span data-ttu-id="adb97-111">El número de línea se puede utilizar para identificar la consulta dentro de la definición:</span><span class="sxs-lookup"><span data-stu-id="adb97-111">The line number can be used to identify the query within the definition:</span></span>  
  
```sql  
select [definition] from sys.sql_modules where object_id=object_id  
```  
  
 <span data-ttu-id="adb97-112">Para obtener más información sobre el `sp_statement_completed` evento extendido, vea [Cómo recuperar la instrucción que produjo un evento](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx).</span><span class="sxs-lookup"><span data-stu-id="adb97-112">For more information about the `sp_statement_completed` extended event, see [How to retrieve the statement that caused an event](https://blogs.msdn.com/b/extended_events/archive/2010/05/07/making-a-statement-how-to-retrieve-the-t-sql-statement-that-caused-an-event.aspx).</span></span>  
  
## <a name="using-data-management-views"></a><span data-ttu-id="adb97-113">Utilizar vistas de administración de datos</span><span class="sxs-lookup"><span data-stu-id="adb97-113">Using Data Management Views</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="adb97-114">admite la recopilación de estadísticas de ejecución para los procedimientos almacenados compilados de forma nativa, tanto en el nivel de procedimiento como en el nivel de consulta.</span><span class="sxs-lookup"><span data-stu-id="adb97-114">supports collecting execution statistics for natively compiled stored procedures, both on the procedure level and the query level.</span></span> <span data-ttu-id="adb97-115">La recopilación de estadísticas de ejecución no está habilitada de forma predeterminada debido al impacto que tiene sobre el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="adb97-115">Collecting execution statistics is not enabled by default due to performance impact.</span></span>  
  
 <span data-ttu-id="adb97-116">Puede habilitar y deshabilitar la recopilación de estadísticas en los procedimientos almacenados compilados de forma nativa con [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="adb97-116">You can enable and disable statistics collection on natively compiled stored procedures using [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="adb97-117">Cuando está habilitada la recopilación de estadísticas con [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql), puede usar [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) para supervisar el rendimiento de un procedimiento almacenado compilado de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="adb97-117">When statistics collection is enabled with [sys.sp_xtp_control_proc_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-proc-exec-stats-transact-sql), you can use [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="adb97-118">Cuando está habilitada la recopilación de estadísticas con [sys.sp_xtp_control_query_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql), puede usar [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) para supervisar el rendimiento de un procedimiento almacenado compilado de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="adb97-118">When statistics collection is enabled with [sys.sp_xtp_control_query_exec_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-xtp-control-query-exec-stats-transact-sql), you can use [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql) to monitor performance of a natively compiled stored procedure.</span></span>  
  
 <span data-ttu-id="adb97-119">Al inicio de la recopilación, habilite la recopilación de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="adb97-119">At the start of collection, enable statistics collection.</span></span> <span data-ttu-id="adb97-120">Después, ejecute el procedimiento almacenado compilado de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="adb97-120">Then, execute the natively compiled stored procedure.</span></span> <span data-ttu-id="adb97-121">Al final de la recopilación, deshabilite la recopilación de estadísticas.</span><span class="sxs-lookup"><span data-stu-id="adb97-121">At the end of collection, disable statistics collection.</span></span> <span data-ttu-id="adb97-122">A continuación, analice las estadísticas de ejecución devueltas por las DMV.</span><span class="sxs-lookup"><span data-stu-id="adb97-122">Then, analyze the execution statistics returned by the DMVs.</span></span>  
  
 <span data-ttu-id="adb97-123">Después de recopilar las estadísticas, se pueden consultar las estadísticas de ejecución de los procedimientos almacenados compilados de forma nativa de un procedimiento con [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql) y de las consultas con [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="adb97-123">After you collect statistics, the execution statistics for natively compiled stored procedures can be queried for a procedure with [sys.dm_exec_procedure_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-procedure-stats-transact-sql), and for queries with [sys.dm_exec_query_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-query-stats-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="adb97-124">En los procedimientos almacenados compilados de forma nativa, cuando la recopilación de estadísticas está habilitada, el tiempo de trabajo se recopila en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="adb97-124">For natively compiled stored procedures when statistics collection is enabled, worker time is collected in milliseconds.</span></span> <span data-ttu-id="adb97-125">Si la consulta se ejecuta en menos de un milisegundo, el valor será 0.</span><span class="sxs-lookup"><span data-stu-id="adb97-125">If the query executes in less than a millisecond, the value will be 0.</span></span> <span data-ttu-id="adb97-126">Para los procedimientos almacenados compilados de forma nativa, **total_worker_time** puede no ser exacto si varias ejecuciones tardan menos de 1 milisegundo.</span><span class="sxs-lookup"><span data-stu-id="adb97-126">For natively compiled stored procedures, **total_worker_time** may not be accurate if many executions take less than 1 millisecond.</span></span>  
  
 <span data-ttu-id="adb97-127">La consulta siguiente devuelve los nombres de los procedimientos y las estadísticas de ejecución para los procedimientos almacenados compilados de forma nativa de la base de datos actual, después de la recopilación de estadísticas:</span><span class="sxs-lookup"><span data-stu-id="adb97-127">The following query returns the procedure names and execution statistics for natively compiled stored procedures in the current database, after statistics collection:</span></span>  
  
```sql  
select object_id,  
       object_name(object_id) as 'object name',  
       cached_time,  
       last_execution_time,  
       execution_count,  
       total_worker_time,  
       last_worker_time,  
       min_worker_time,  
       max_worker_time,  
       total_elapsed_time,  
       last_elapsed_time,  
       min_elapsed_time,  
       max_elapsed_time   
from sys.dm_exec_procedure_stats  
where database_id=db_id() and object_id in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by total_worker_time desc  
```  
  
 <span data-ttu-id="adb97-128">La consulta siguiente devuelve el texto de la consulta y las estadísticas de ejecución para todas las consultas de procedimientos almacenados compilados de forma nativa de la base de datos actual para la que se han recopilado estadísticas, ordenadas por tiempo total de trabajo, en orden descendente:</span><span class="sxs-lookup"><span data-stu-id="adb97-128">The following query returns the query text as well as execution statistics for all queries in natively compiled stored procedures in the current database for which statistics have been collected, ordered by total worker time, in descending order:</span></span>  
  
```sql  
select st.objectid,   
       object_name(st.objectid) as 'object name',   
       SUBSTRING(st.text, (qs.statement_start_offset/2) + 1, ((qs.statement_end_offset-qs.statement_start_offset)/2) + 1) as 'query text',   
       qs.creation_time,  
       qs.last_execution_time,  
       qs.execution_count,  
       qs.total_worker_time,  
       qs.last_worker_time,  
       qs.min_worker_time,  
       qs.max_worker_time,  
       qs.total_elapsed_time,  
       qs.last_elapsed_time,  
       qs.min_elapsed_time,  
       qs.max_elapsed_time  
from sys.dm_exec_query_stats qs cross apply sys.dm_exec_sql_text(sql_handle) st  
where  st.dbid=db_id() and st.objectid in (select object_id   
from sys.sql_modules where uses_native_compilation=1)  
order by qs.total_worker_time desc  
```  
  
 <span data-ttu-id="adb97-129">Los procedimientos almacenados compilados de forma nativa admiten SHOWPLAN_XML (plan de ejecución estimado).</span><span class="sxs-lookup"><span data-stu-id="adb97-129">Natively compiled stored procedures support SHOWPLAN_XML (estimated execution plan).</span></span> <span data-ttu-id="adb97-130">El plan de ejecución estimado se puede utilizar para inspeccionar el plan de consulta con el fin de detectar cualquier problema de plan incorrecto.</span><span class="sxs-lookup"><span data-stu-id="adb97-130">The estimated execution plan can be used to inspect the query plan, to find any bad plan issues.</span></span> <span data-ttu-id="adb97-131">Los motivos más frecuentes de los planes no válidos son:</span><span class="sxs-lookup"><span data-stu-id="adb97-131">Common reasons for bad plans are:</span></span>  
  
-   <span data-ttu-id="adb97-132">Las estadísticas no se actualizaron antes de que se creara el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="adb97-132">Stats were not updated before the procedure was created.</span></span>  
  
-   <span data-ttu-id="adb97-133">Faltan índices</span><span class="sxs-lookup"><span data-stu-id="adb97-133">Missing indexes</span></span>  
  
 <span data-ttu-id="adb97-134">Showplan XML se obtiene ejecutando la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)]siguiente:</span><span class="sxs-lookup"><span data-stu-id="adb97-134">Showplan XML is obtained by executing the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
```sql  
SET SHOWPLAN_XML ON  
GO  
EXEC my_proc   
GO  
SET SHOWPLAN_XML OFF  
GO  
```  
  
 <span data-ttu-id="adb97-135">O bien, en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], seleccione el nombre del procedimiento y haga clic en **Mostrar plan de ejecución estimado**.</span><span class="sxs-lookup"><span data-stu-id="adb97-135">Alternatively, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], select the procedure name and click **Display Estimated Execution Plan**.</span></span>  
  
 <span data-ttu-id="adb97-136">El plan de ejecución estimado para los procedimientos almacenados compilados de forma nativa muestra los operadores y las expresiones de consulta para las consultas del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="adb97-136">The estimated execution plan for natively compiled stored procedures shows the query operators and expressions for the queries in the procedure.</span></span> [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] <span data-ttu-id="adb97-137">no admite todos los atributos SHOWPLAN_XML para los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="adb97-137">does not support all SHOWPLAN_XML attributes for natively compiled stored procedures.</span></span> <span data-ttu-id="adb97-138">Por ejemplo, los atributos relacionados con el costo del optimizador de consultas no forman parte de SHOWPLAN_XML para el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="adb97-138">For example, attributes related to query optimizer costing are not part of the SHOWPLAN_XML for the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adb97-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="adb97-139">See Also</span></span>  
 [<span data-ttu-id="adb97-140">Procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="adb97-140">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
