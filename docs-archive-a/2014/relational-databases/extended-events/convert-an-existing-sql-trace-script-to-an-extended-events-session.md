---
title: Conversión de un script de seguimiento de SQL existente en una sesión de eventos extendidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace, convert script to extended events
- extended events [SQL Server], convert SQL Trace script
ms.assetid: 4c8f29e6-0a37-490f-88b3-33493871b3f9
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e5b0d0e20fbf4fd55398c130abf6cfff128ebe8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675397"
---
# <a name="convert-an-existing-sql-trace-script-to-an-extended-events-session"></a><span data-ttu-id="685da-102">Convertir un script de seguimiento de SQL existente en una sesión de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="685da-102">Convert an Existing SQL Trace Script to an Extended Events Session</span></span>
  <span data-ttu-id="685da-103">Si tiene un script existente de Seguimiento de SQL que desea convertir a una sesión de eventos extendidos, puede usar los procedimientos de este tema para crear una sesión de eventos extendidos equivalente.</span><span class="sxs-lookup"><span data-stu-id="685da-103">If you have an existing SQL Trace script that you want to convert to an Extended Events session, you can use the procedures in this topic to create an equivalent Extended Events session.</span></span> <span data-ttu-id="685da-104">Con la información de las tablas del sistema trace_xe_action_map y trace_xe_event_map, puede recopilar la información que necesita para realizar la conversión.</span><span class="sxs-lookup"><span data-stu-id="685da-104">By using the information in the trace_xe_action_map and trace_xe_event_map system tables, you can collect the information that you must have to do the conversion.</span></span>  
  
 <span data-ttu-id="685da-105">Los pasos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="685da-105">The steps include the following:</span></span>  
  
1.  <span data-ttu-id="685da-106">Ejecute el script existente para crear una sesión de Seguimiento de SQL y obtener después el identificador del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="685da-106">Execute the existing script to create a SQL Trace session, and then obtain the ID of the trace.</span></span>  
  
2.  <span data-ttu-id="685da-107">Ejecute una consulta que use la función fn_trace_geteventinfo para buscar los eventos y acciones equivalentes de eventos extendidos para cada clase de eventos de Seguimiento de SQL y sus columnas asociadas.</span><span class="sxs-lookup"><span data-stu-id="685da-107">Run a query that uses the fn_trace_geteventinfo function to find the equivalent Extended Events events and actions for each SQL Trace event class and its associated columns.</span></span>  
  
3.  <span data-ttu-id="685da-108">Use la función fn_trace_getfilterinfo para enumerar los filtros y las acciones equivalentes de eventos extendidos que vaya a usar.</span><span class="sxs-lookup"><span data-stu-id="685da-108">Use the fn_trace_getfilterinfo function to list the filters and the equivalent Extended Events actions to use.</span></span>  
  
4.  <span data-ttu-id="685da-109">Cree manualmente una sesión de eventos extendidos utilizando los eventos, acciones, y predicados (filtros) equivalentes de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="685da-109">Manually create an Extended Events session, using the equivalent Extended Events events, actions, and predicates (filters).</span></span>  
  
## <a name="to-obtain-the-trace-id"></a><span data-ttu-id="685da-110">Para obtener el identificador de seguimiento</span><span class="sxs-lookup"><span data-stu-id="685da-110">To obtain the trace ID</span></span>  
  
1.  <span data-ttu-id="685da-111">Abra el script de Seguimiento de SQL en el Editor de consultas y, a continuación, ejecute el script para crear la sesión de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="685da-111">Open the SQL Trace script in Query Editor, and then execute the script to create the trace session.</span></span> <span data-ttu-id="685da-112">Tenga en cuenta que no es necesario que la sesión de seguimiento esté ejecutándose para completar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="685da-112">Note that the trace session does not need to be running to complete this procedure.</span></span>  
  
2.  <span data-ttu-id="685da-113">Obtenga el identificador del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="685da-113">Obtain the ID of the trace.</span></span> <span data-ttu-id="685da-114">Para ello, utilice la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="685da-114">To do this, use the following query:</span></span>  
  
    ```sql
    SELECT * FROM sys.traces;  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="685da-115">El identificador de seguimiento 1 indica normalmente el seguimiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="685da-115">Trace ID 1 typically indicates the default trace.</span></span>  
  
## <a name="to-determine-the-extended-events-equivalents"></a><span data-ttu-id="685da-116">Para determinar los equivalentes de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="685da-116">To determine the Extended Events equivalents</span></span>  
  
1.  <span data-ttu-id="685da-117">Para determinar los eventos y acciones equivalentes de eventos extendidos, ejecute la consulta siguiente, donde *trace_id* se establece en el valor del identificador de seguimiento obtenido en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="685da-117">To determine the equivalent Extended Events events and actions, run the following query, where *trace_id* is set to the value of the trace ID that you obtained in the previous procedure.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="685da-118">En este ejemplo, se utiliza el identificador de seguimiento para el seguimiento predeterminado (1).</span><span class="sxs-lookup"><span data-stu-id="685da-118">In this example, the trace ID for the default trace (1) is used.</span></span>  
  
    ```sql
    USE MASTER;  
    GO  
    DECLARE @trace_id int;  
    SET @trace_id = 1;  
    SELECT DISTINCT el.eventid, em.package_name, em.xe_event_name AS 'event'  
       , el.columnid, ec.xe_action_name AS 'action'  
    FROM (sys.fn_trace_geteventinfo(@trace_id) AS el  
       LEFT OUTER JOIN sys.trace_xe_event_map AS em  
          ON el.eventid = em.trace_event_id)  
    LEFT OUTER JOIN sys.trace_xe_action_map AS ec  
       ON el.columnid = ec.trace_column_id  
    WHERE em.xe_event_name IS NOT NULL AND ec.xe_action_name IS NOT NULL;  
    ```  
  
     <span data-ttu-id="685da-119">Se devuelven el identificador de evento, nombre de paquete, nombre de evento, identificador de columna y nombre de acción equivalentes de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="685da-119">The equivalent Extended Events event ID, package name, event name, column ID and action name are returned.</span></span> <span data-ttu-id="685da-120">Utilizará esta salida en el procedimiento "Para crear la sesión de eventos extendidos" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="685da-120">You will use this output in the procedure "To create the Extended Events session" later in this topic.</span></span>  
  
     <span data-ttu-id="685da-121">En algunos casos, la columna filtrada se asigna a un campo de datos de evento que se incluye de forma predeterminada en el evento de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="685da-121">In some cases, the filtered column maps to an event data field that is included by default in the Extended Events event.</span></span> <span data-ttu-id="685da-122">Por consiguiente, la columna "Extended_Events_action_name" será NULL.</span><span class="sxs-lookup"><span data-stu-id="685da-122">Therefore, the "Extended_Events_action_name" column will be NULL.</span></span> <span data-ttu-id="685da-123">Si esto se produce, debe realizar lo siguiente para determinar qué campo de datos es equivalente a la columna filtrada:</span><span class="sxs-lookup"><span data-stu-id="685da-123">If this occurs, you must do the following to determine which data field is equivalent to the filtered column:</span></span>  
  
    1.  <span data-ttu-id="685da-124">Para las acciones que devuelven NULL, identifique qué clases de eventos de Seguimiento de SQL en el script contienen la columna que se está filtrando.</span><span class="sxs-lookup"><span data-stu-id="685da-124">For the actions that return NULL, identify which SQL Trace event classes in the script contain the column that is being filtered.</span></span>  
  
         <span data-ttu-id="685da-125">Por ejemplo, puede haber usado la clase de eventos SP:StmtCompleted y especificado un filtro en el nombre de columna de seguimiento Duration (identificador 45 de la clase de eventos de Seguimiento de SQL e identificador 13 de la columna de Seguimiento de SQL).</span><span class="sxs-lookup"><span data-stu-id="685da-125">For example, you may have used the SP:StmtCompleted event class, and specified a filter on the Duration trace column name (SQL Trace event class ID 45, and SQL Trace column ID 13).</span></span> <span data-ttu-id="685da-126">En este caso, el nombre de acción aparecerá como NULL en los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="685da-126">In this case, the action name will appear as NULL in the query results.</span></span>  
  
    2.  <span data-ttu-id="685da-127">Para cada clase de eventos de Seguimiento de SQL identificada en el paso anterior, busque el nombre de evento equivalente de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="685da-127">For each SQL Trace event class that you identified in the previous step, find the equivalent Extended Events event name.</span></span> <span data-ttu-id="685da-128">(Si no está seguro del nombre de evento equivalente, use la consulta del tema [Ver los eventos extendidos equivalentes a las clases de evento de Seguimiento de SQL Server](view-the-extended-events-equivalents-to-sql-trace-event-classes.md)).</span><span class="sxs-lookup"><span data-stu-id="685da-128">(If you are not sure of the equivalent event name, use the query in the topic [View the Extended Events Equivalents to SQL Trace Event Classes](view-the-extended-events-equivalents-to-sql-trace-event-classes.md).)</span></span>  
  
    3.  <span data-ttu-id="685da-129">Utilice la consulta siguiente para identificar los campos de datos correctos que va a utilizar para los eventos identificados en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="685da-129">Use the following query to identify the correct data fields to use for the events that you identified in the previous step.</span></span> <span data-ttu-id="685da-130">La consulta muestra los campos de datos de eventos extendidos en la columna "event_field".</span><span class="sxs-lookup"><span data-stu-id="685da-130">The query shows the Extended Events data fields in the "event_field" column.</span></span> <span data-ttu-id="685da-131">En la consulta, reemplace *<nombre_evento>* por el nombre de un evento especificado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="685da-131">In the query, replace *<event_name>* with the name of an event that you specified in the previous step.</span></span>  
  
        ```sql
        SELECT xp.name package_name, xe.name event_name  
           ,xc.name event_field, xc.description  
        FROM sys.trace_xe_event_map AS em  
        INNER JOIN sys.dm_xe_objects AS xe  
           ON em.xe_event_name = xe.name  
        INNER JOIN sys.dm_xe_packages AS xp  
           ON xe.package_guid = xp.guid AND em.package_name = xp.name  
        INNER JOIN sys.dm_xe_object_columns AS xc  
           ON xe.name = xc.object_name  
        WHERE xe.object_type = 'event' AND xc.column_type <> 'readonly'  
           AND em.xe_event_name = '<event_name>';  
        ```  
  
         <span data-ttu-id="685da-132">Por ejemplo, la clase de eventos SP:StmtCompleted se asigna al evento sp_statement_completed de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="685da-132">For example, the SP:StmtCompleted event class maps to the sp_statement_completed Extended Events event.</span></span> <span data-ttu-id="685da-133">Si especifica sp_statement_completed como nombre de evento en la consulta, la columna "event_field" muestra los campos que se incluyen de forma predeterminada con el evento.</span><span class="sxs-lookup"><span data-stu-id="685da-133">If you specify sp_statement_completed as the event name in the query, the "event_field" column shows the fields that are included by default with the event.</span></span> <span data-ttu-id="685da-134">Examinando los campos, puede ver que hay un campo de "duración".</span><span class="sxs-lookup"><span data-stu-id="685da-134">Looking at the fields, you can see that there is a "duration" field.</span></span> <span data-ttu-id="685da-135">Para crear el filtro en la sesión equivalente de eventos extendidos, agregaría un predicado como "WHERE duration > 0".</span><span class="sxs-lookup"><span data-stu-id="685da-135">To create the filter in the equivalent Extended Events session, you would add a predicate such as "WHERE duration > 0".</span></span> <span data-ttu-id="685da-136">Para obtener un ejemplo, vea el procedimiento "Para crear la sesión de eventos extendidos" en este tema.</span><span class="sxs-lookup"><span data-stu-id="685da-136">For an example, see the "To create the Extended Events session" procedure in this topic.</span></span>  
  
## <a name="to-create-the-extended-events-session"></a><span data-ttu-id="685da-137">Para crear la sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="685da-137">To create the Extended Events session</span></span>  
 <span data-ttu-id="685da-138">Utilice el Editor de consultas para crear la sesión de eventos extendidos y para escribir la salida en un destino de archivo.</span><span class="sxs-lookup"><span data-stu-id="685da-138">Use Query Editor to create the Extended Events session, and to write the output to a file target.</span></span> <span data-ttu-id="685da-139">Los siguientes pasos describen una consulta única con explicaciones que le muestran cómo se genera la consulta.</span><span class="sxs-lookup"><span data-stu-id="685da-139">The following steps describe a single query, with explanations to show you how to build the query.</span></span> <span data-ttu-id="685da-140">Para obtener el ejemplo completo de la consulta, vea la sección "Ejemplo" de este tema.</span><span class="sxs-lookup"><span data-stu-id="685da-140">For the full query example, see the "Example" section of this topic.</span></span>  
  
1.  <span data-ttu-id="685da-141">Agregue instrucciones para crear la sesión de eventos, reemplazando*nombre_de_sesión* por el nombre que quiere usar para la sesión de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="685da-141">Add statements to create the event session, replacing s*ession_name* with the name that you want to use for the Extended Events session.</span></span>  
  
    ```sql
    IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
       DROP EVENT SESSION [Session_Name] ON SERVER;  
    CREATE EVENT SESSION [Session_Name]  
    ON SERVER;  
    ```  
  
2.  <span data-ttu-id="685da-142">Agregue los eventos y acciones de eventos extendidos que se devolvieron como salida en el procedimiento "Para determinar los equivalentes de eventos extendidos" y agregue los predicados (filtros) identificados en el procedimiento "Para determinar los filtros que se utilizan en el script".</span><span class="sxs-lookup"><span data-stu-id="685da-142">Add the Extended Events events and actions that were returned as output in the procedure "Determine the Extended Events equivalents", and add the predicates (filters) that you identified in the procedure "To determine the filters that were used in the script".</span></span>  
  
     <span data-ttu-id="685da-143">En el ejemplo siguiente se usa un script de Seguimiento de SQL que incluye las clases de eventos SQL:StmtStarting y SP:StmtCompleted, con filtros para el identificador y la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="685da-143">The following example uses a SQL Trace script that includes the SQL:StmtStarting and SP:StmtCompleted event classes, with filters for session ID and duration.</span></span> <span data-ttu-id="685da-144">La salida de ejemplo para la consulta del procedimiento "Para determinar los equivalentes de eventos extendidos" devolvió el siguiente conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="685da-144">Sample output for the query in the "Determine the Extended Events equivalents" procedure returned the following result set:</span></span>  
  
    ```  
    Eventid  package_name  event                   columnid  action  
    44       sqlserver     sp_statement_starting   6         nt_username  
    44       sqlserver     sp_statement_starting   9         client_pid  
    44       sqlserver     sp_statement_starting   10        client_app_name  
    44       sqlserver     sp_statement_starting   11        server_principal_name  
    44       sqlserver     sp_statement_starting   12        session_id  
    45       sqlserver     sp_statement_completed  6         nt_username  
    45       sqlserver     sp_statement_completed  9         client_pid  
    45       sqlserver     sp_statement_completed  10        client_app_name  
    45       sqlserver     sp_statement_completed  11        server_principal_name  
    45       sqlserver     sp_statement_completed  12        session_id  
    ```  
  
     <span data-ttu-id="685da-145">Para convertir esto en el equivalente de eventos extendidos, se agregan los eventos sqlserver.sp_statement_starting y sqlserver.sp_statement_completed con una lista de acciones.</span><span class="sxs-lookup"><span data-stu-id="685da-145">To convert this to the Extended Events equivalent, the sqlserver.sp_statement_starting and the sqlserver.sp_statement_completed events are added, with a list of actions.</span></span> <span data-ttu-id="685da-146">Las instrucciones de predicado se incluyen como cláusulas WHERE.</span><span class="sxs-lookup"><span data-stu-id="685da-146">Predicate statements are included as WHERE clauses.</span></span>  
  
    ```sql
    ADD EVENT sqlserver.sp_statement_starting  
       (ACTION  
          (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
          )  
       WHERE sqlserver.session_id = 59   
       ),  
  
    ADD EVENT sqlserver.sp_statement_completed  
       (ACTION  
          (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
          )  
       WHERE sqlserver.session_id = 59 AND duration > 0  
       )  
    ```  
  
3.  <span data-ttu-id="685da-147">Agregue el destino de archivo asincrónico, reemplazando las rutas de acceso de archivo por la ubicación donde quiere guardar la salida.</span><span class="sxs-lookup"><span data-stu-id="685da-147">Add the asynchronous file target, replacing the file paths with the location where you want to save the output.</span></span> <span data-ttu-id="685da-148">Cuando especifique el destino de archivo, debe incluir una ruta de acceso del archivo de registro y del archivo de metadatos.</span><span class="sxs-lookup"><span data-stu-id="685da-148">When specifying the file target, you must include a log file and metadata file path file.</span></span>  
  
    ```sql
    ADD TARGET package0.asynchronous_file_target(  
       SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
    ```  
  
## <a name="to-view-the-results"></a><span data-ttu-id="685da-149">Para ver los resultados</span><span class="sxs-lookup"><span data-stu-id="685da-149">To view the results</span></span>  
  
1.  <span data-ttu-id="685da-150">Puede usar la función sys.fn_xe_file_target_read_file para ver la salida.</span><span class="sxs-lookup"><span data-stu-id="685da-150">You can use the sys.fn_xe_file_target_read_file function to view the output.</span></span> <span data-ttu-id="685da-151">Para ello, ejecute la consulta siguiente, reemplazando las rutas de acceso de archivo por las rutas de acceso que haya especificado:</span><span class="sxs-lookup"><span data-stu-id="685da-151">To do this, run the following query, replacing the file paths with the paths that you specified:</span></span>  
  
    ```sql
    SELECT *, CAST(event_data as XML) AS 'event_data_XML'  
    FROM sys.fn_xe_file_target_read_file('c:\temp\ExtendedEventsStoredProcs*.xel', 'c:\temp\ExtendedEventsStoredProcs*.xem', NULL, NULL);  
  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="685da-152">La conversión de los datos de evento como XML es opcional.</span><span class="sxs-lookup"><span data-stu-id="685da-152">Casting the event data as XML is optional.</span></span>  
  
     <span data-ttu-id="685da-153">Para obtener más información sobre la función sys.fn_xe_file_target_read_file, vea [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="685da-153">For more information about the sys.fn_xe_file_target_read_file function, see [sys.fn_xe_file_target_read_file &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-xe-file-target-read-file-transact-sql).</span></span>  
  
    ```sql
    IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
       DROP EVENT SESSION [session_name] ON SERVER;  
    CREATE EVENT SESSION [session_name]  
    ON SERVER  
  
    ADD EVENT sqlserver.sp_statement_starting  
       (ACTION  
       (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
       )  
       WHERE sqlserver.session_id = 59   
       ),  
  
    ADD EVENT sqlserver.sp_statement_completed  
       (ACTION  
       (  
          sqlserver.nt_username,  
          sqlserver.client_pid,  
          sqlserver.client_app_name,  
          sqlserver.server_principal_name,  
          sqlserver.session_id  
       )  
       WHERE sqlserver.session_id = 59 AND duration > 0  
       );  
  
    ADD TARGET package0.asynchronous_file_target  
       (SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
    ```  
  
## <a name="example"></a><span data-ttu-id="685da-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="685da-154">Example</span></span>  
  
```sql
IF EXISTS(SELECT * FROM sys.server_event_sessions WHERE name='session_name')  
   DROP EVENT SESSION [session_name] ON SERVER;  
CREATE EVENT SESSION [session_name]  
ON SERVER  
  
ADD EVENT sqlserver.sp_statement_starting  
   (ACTION  
   (  
      sqlserver.nt_username,  
      sqlserver.client_pid,  
      sqlserver.client_app_name,  
      sqlserver.server_principal_name,  
      sqlserver.session_id  
   )  
   WHERE sqlserver.session_id = 59   
   ),  
  
ADD EVENT sqlserver.sp_statement_completed  
   (ACTION  
   (  
      sqlserver.nt_username,  
      sqlserver.client_pid,  
      sqlserver.client_app_name,  
      sqlserver.server_principal_name,  
      sqlserver.session_id  
   )  
   WHERE sqlserver.session_id = 59 AND duration > 0  
   )  
  
ADD TARGET package0.asynchronous_file_target  
   (SET filename='c:\temp\ExtendedEventsStoredProcs.xel', metadatafile='c:\temp\ExtendedEventsStoredProcs.xem');  
```  
  
## <a name="see-also"></a><span data-ttu-id="685da-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="685da-155">See Also</span></span>  
 [<span data-ttu-id="685da-156">Ver los eventos extendidos equivalentes a las clases de evento de Seguimiento de SQL</span><span class="sxs-lookup"><span data-stu-id="685da-156">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>](view-the-extended-events-equivalents-to-sql-trace-event-classes.md)  
  
  