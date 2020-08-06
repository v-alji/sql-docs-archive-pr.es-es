---
title: Crear una sesión de eventos extendidos mediante el editor de consultas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- create extended events session
- extended events [SQL Server], create session
ms.assetid: cba0e02b-b201-4863-bf1b-9164e68e5fa8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 648370ecdd2938b6fb425955dc02da8960f884c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673254"
---
# <a name="create-an-extended-events-session-using-query-editor"></a><span data-ttu-id="b1d19-102">Crear una sesión de eventos extendidos mediante el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="b1d19-102">Create an Extended Events Session Using Query Editor</span></span>
  <span data-ttu-id="b1d19-103">Puede crear una sesión de eventos extendidos utilizando el Editor de consultas o puede crear una sesión en el Explorador de objetos.</span><span class="sxs-lookup"><span data-stu-id="b1d19-103">You can create an Extended Events session by using the Query Editor, or you can create a session in Object Explorer.</span></span> <span data-ttu-id="b1d19-104">En Explorador de objetos, Extended Events proporciona dos interfaces de usuario que puede usar para crear, modificar y ver datos de sesión de eventos: un asistente que le guía a través del proceso de creación de la sesión de eventos y una nueva interfaz de usuario de sesión que proporciona opciones de configuración más avanzadas.</span><span class="sxs-lookup"><span data-stu-id="b1d19-104">In Object Explorer, Extended Events provides two user interfaces you can use to create, modify, and view event session data - a wizard that guides you through the event session creation process, and a New Session UI that provides more advanced configuration options.</span></span> <span data-ttu-id="b1d19-105">Puede crear sesiones de eventos extendidos para diagnosticar el seguimiento de SQL Server, lo cual le permite resolver problemas como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1d19-105">You can create Extended Events sessions to diagnose SQL Server tracing, which enables you to resolve issues such as the following:</span></span>  
  
-   <span data-ttu-id="b1d19-106">Encontrar las consultas más caras</span><span class="sxs-lookup"><span data-stu-id="b1d19-106">Find your most expensive queries</span></span>  
  
-   <span data-ttu-id="b1d19-107">Encontrar las causas principales de la contención de bloqueos temporales</span><span class="sxs-lookup"><span data-stu-id="b1d19-107">Find root causes of latch contention</span></span>  
  
-   <span data-ttu-id="b1d19-108">Encontrar una consulta que esté bloqueando otras consultas</span><span class="sxs-lookup"><span data-stu-id="b1d19-108">Find a query that is blocking other queries</span></span>  
  
-   <span data-ttu-id="b1d19-109">Solucionar problemas de uso excesivo de la CPU producido por la recompilación de consultas</span><span class="sxs-lookup"><span data-stu-id="b1d19-109">Troubleshoot excessive CPU usage caused by query recompilation</span></span>  
  
-   <span data-ttu-id="b1d19-110">Solucionar problemas de interbloqueos</span><span class="sxs-lookup"><span data-stu-id="b1d19-110">Troubleshoot deadlocks</span></span>  
  
 <span data-ttu-id="b1d19-111">Para obtener más información sobre cómo crear una sesión de eventos extendidos con el Asistente para nueva sesión, vea [Crear una sesión de Extended Events utilizando el asistente &#40;Explorador de objetos&#41;](../ssms/object/object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="b1d19-111">For information about how to create an Extended Events session using the New Session Wizard, see [Create an Extended Events Session Using the Wizard &#40;Object Explorer&#41;](../ssms/object/object-explorer.md).</span></span> <span data-ttu-id="b1d19-112">Para obtener más información sobre cómo crear una sesión de eventos extendidos con la interfaz de usuario de nueva sesión, vea [Crear una sesión de eventos extendidos utilizando el cuadro de diálogo Nueva sesión](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md).</span><span class="sxs-lookup"><span data-stu-id="b1d19-112">For information about how to create an Extended Events session using the New Session UI, see [Create an Extended Events Session Using the New Session Dialog](../../2014/database-engine/create-an-extended-events-session-using-the-new-session-dialog.md).</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b1d19-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="b1d19-113">Permissions</span></span>  
 <span data-ttu-id="b1d19-114">Para crear una sesión de eventos extendidos, debe disponer del permiso ALTER ANY EVENT SESSION.</span><span class="sxs-lookup"><span data-stu-id="b1d19-114">To create an Extended Events session, you must have the ALTER ANY EVENT SESSION permission.</span></span>  
  
## <a name="creating-an-extended-events-session-using-query-editor"></a><span data-ttu-id="b1d19-115">Crear una sesión de eventos extendidos mediante el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="b1d19-115">Creating an Extended Events session using Query Editor</span></span>  
  
#### <a name="to-create-an-extended-events-session"></a><span data-ttu-id="b1d19-116">Para crear una sesión de eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="b1d19-116">To create an Extended Events session</span></span>  
  
1.  <span data-ttu-id="b1d19-117">En el siguiente procedimiento se muestra cómo crear una sesión de eventos extendidos utilizando el Editor de consultas en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1d19-117">The following procedure shows how to create an Extended Events session by using Query Editor in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
     <span data-ttu-id="b1d19-118">Determine los eventos que desea utilizar en la sesión.</span><span class="sxs-lookup"><span data-stu-id="b1d19-118">Determine which events that you want to use in the session.</span></span> <span data-ttu-id="b1d19-119">Para ver todos los eventos disponibles, junto con la palabra clave y el canal, utilice la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="b1d19-119">To see all the events that are available, together with the keyword and channel, use the following query:</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b1d19-120"> Para obtener información acerca de las palabras clave y los canales, vea [SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span><span class="sxs-lookup"><span data-stu-id="b1d19-120">For information about keywords and channels, see [SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md).</span></span>  
  
    ```  
    SELECT p.name, c.event, k.keyword, c.channel, c.description FROM  
       (  
       SELECT event_package = o.package_guid, o.description,   
       event=c.object_name, channel = v.map_value  
       FROM sys.dm_xe_objects o  
       LEFT JOIN sys.dm_xe_object_columns c ON o.name = c.object_name  
       INNER JOIN sys.dm_xe_map_values v ON c.type_name = v.name   
       AND c.column_value = cast(v.map_key AS nvarchar)  
       WHERE object_type = 'event' AND (c.name = 'CHANNEL' or c.name IS NULL)  
       ) c LEFT JOIN   
       (  
       SELECT event_package = c.object_package_guid, event = c.object_name,   
       keyword = v.map_value  
       FROM sys.dm_xe_object_columns c INNER JOIN sys.dm_xe_map_values v   
       ON c.type_name = v.name AND c.column_value = v.map_key   
       AND c.type_package_guid = v.object_package_guid  
       INNER JOIN sys.dm_xe_objects o ON o.name = c.object_name   
       AND o.package_guid = c.object_package_guid  
       WHERE object_type = 'event' AND c.name = 'KEYWORD'   
       ) k  
       ON  
       k.event_package = c.event_package AND (k.event=c.event or k.event IS NULL)  
       INNER JOIN sys.dm_xe_packages p ON p.guid = c.event_package  
    ORDER BY keyword desc, channel, event  
    ```  
  
2.  <span data-ttu-id="b1d19-121">En una nueva ventana de consulta, agregue las siguientes instrucciones para crear una sesión de eventos, reemplazando *session_name* por el nombre de la sesión que quiera usar:</span><span class="sxs-lookup"><span data-stu-id="b1d19-121">In a new query window, add the following statements to create an event session, replacing *session_name* with the session name that you want to use:</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b1d19-122">En los pasos 2 a 6 de este procedimiento se describe cada sección de la definición de la sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="b1d19-122">Steps 2 through 6 of this procedure describe each section of the event session definition.</span></span> <span data-ttu-id="b1d19-123">Debe agregar todas las instrucciones en una sola ventana de consulta antes de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="b1d19-123">You would add all the statements to a single query window before executing.</span></span> <span data-ttu-id="b1d19-124">Para obtener un ejemplo completo, vea la sección Ejemplo de este tema.</span><span class="sxs-lookup"><span data-stu-id="b1d19-124">For a full example, see the Example section of this topic.</span></span>  
  
    ```  
    CREATE EVENT SESSION session_name   
    ON SERVER  
    ```  
  
3.  <span data-ttu-id="b1d19-125">Agregue los eventos que quiere supervisar, en formato *package_name*.*event_name*.</span><span class="sxs-lookup"><span data-stu-id="b1d19-125">Add the events that you want to monitor, in the format *package_name*.*event_name*.</span></span> <span data-ttu-id="b1d19-126">Para cada evento, agregue una línea similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1d19-126">For each event, add a line similar to the following:</span></span>  
  
    ```  
    ADD EVENT package_name.event_name  
    ```  
  
     <span data-ttu-id="b1d19-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b1d19-127">For example:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed,  
    ADD EVENT sqlserver.file_write_completed  
    ```  
  
4.  <span data-ttu-id="b1d19-128">(Opcional) Después de agregar un evento, puede agregar las acciones que se han de realizar.</span><span class="sxs-lookup"><span data-stu-id="b1d19-128">(Optional) After you add an event, you can add actions to take.</span></span> <span data-ttu-id="b1d19-129">También puede agregar predicados.</span><span class="sxs-lookup"><span data-stu-id="b1d19-129">You can also add predicates.</span></span> <span data-ttu-id="b1d19-130">Los predicados se utilizan para establecer los criterios para saber en qué momento la información de eventos se debe usar en el destino.</span><span class="sxs-lookup"><span data-stu-id="b1d19-130">Predicates are used to establish criteria for when the event information should be consumed by the target.</span></span> <span data-ttu-id="b1d19-131">Las acciones se agregan utilizando una cláusula ACTION y los predicados se agregan utilizando una cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="b1d19-131">Actions are added by using an ACTION clause, and predicates are added by using a WHERE clause.</span></span> <span data-ttu-id="b1d19-132">Por ejemplo, para agregar una acción y un predicado donde se captura el texto de [!INCLUDE[tsql](../includes/tsql-md.md)] para el evento sqlserver.file_read_completed, siendo el identificador de archivo igual a 1, también debe incluir la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="b1d19-132">For example, to add an action and predicate where the [!INCLUDE[tsql](../includes/tsql-md.md)] text is captured for the sqlserver.file_read_completed event, where the file ID equals 1, you would include the following statement:</span></span>  
  
    ```  
    ADD EVENT sqlserver.file_read_completed  
       (ACTION (sqlserver.sql_text)  
       WHERE file_id = 1),  
    ```  
  
    -   <span data-ttu-id="b1d19-133">Para ver qué acciones están disponibles, utilice la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="b1d19-133">To view which actions are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS 'package_name', xo.name AS 'action_name', xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'action'  
        AND (xo.capabilities & 1 = 0   
        OR xo.capabilities IS NULL)  
        ORDER BY p.name, xo.name  
        ```  
  
    -   <span data-ttu-id="b1d19-134">Para ver los predicados disponibles para un evento, use la consulta siguiente, reemplazando *event_name* por el nombre del evento para el que quiere agregar un predicado:</span><span class="sxs-lookup"><span data-stu-id="b1d19-134">To view which predicates are available for an event, use the following query, replacing *event_name* with the name of the event for which you want to add a predicate:</span></span>  
  
        ```  
        SELECT *  
        FROM sys.dm_xe_object_columns  
        WHERE object_name = 'event_name'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="b1d19-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b1d19-135">For example:</span></span>  
  
        ```  
        SELECT *   
        FROM sys.dm_xe_object_columns   
        WHERE object_name = 'file_read_completed'  
        AND column_type = 'data'  
        ```  
  
         <span data-ttu-id="b1d19-136">Tenga en cuenta que también puede agregar orígenes globales de predicado.</span><span class="sxs-lookup"><span data-stu-id="b1d19-136">Be aware that you can also add global predicate sources.</span></span> <span data-ttu-id="b1d19-137">Un origen global de predicado se puede utilizar en cualquier expresión de predicado.</span><span class="sxs-lookup"><span data-stu-id="b1d19-137">A global predicate source can be used in any predicate expression.</span></span> <span data-ttu-id="b1d19-138">Para ver qué orígenes globales de predicado están disponibles, utilice la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="b1d19-138">To view which global predicate sources are available, use the following query:</span></span>  
  
        ```  
        SELECT p.name AS package_name, xo.name AS predicate_name  
           , xo.description, xo.object_type  
        FROM sys.dm_xe_objects AS xo  
        JOIN sys.dm_xe_packages AS p  
           ON xo.package_guid = p.guid  
        WHERE xo.object_type = 'pred_source'  
        ORDER BY p.name, xo.name  
        ```  
  
         <span data-ttu-id="b1d19-139">Por ejemplo, puede usar la expresión de predicado siguiente para especificar que se deben recopilar únicamente datos para un evento las cinco primeras veces que se produce el citado evento.</span><span class="sxs-lookup"><span data-stu-id="b1d19-139">For example, you could use the following predicate expression to specify that data should only be collected for an event the first five times that an event occurs.</span></span>  
  
        ```  
        WHERE package0.counter <= 5  
        ```  
  
5.  <span data-ttu-id="b1d19-140">Agregue el destino deseado donde se procesarán y utilizarán los datos de evento.</span><span class="sxs-lookup"><span data-stu-id="b1d19-140">Add the desired target, where the event data will be processed and consumed.</span></span> <span data-ttu-id="b1d19-141">Utilice el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="b1d19-141">Use the following format:</span></span>  
  
    ```  
    ADD TARGET package_name.target_name  
    ```  
  
     <span data-ttu-id="b1d19-142">En el ejemplo siguiente se agrega el destino de archivo asincrónico:</span><span class="sxs-lookup"><span data-stu-id="b1d19-142">The following example adds the asynchronous file target:</span></span>  
  
    ```  
    ADD TARGET package0.asynchronous_file_target  
       (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
    ```  
  
     <span data-ttu-id="b1d19-143">Para ver la lista de destinos disponibles, utilice la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="b1d19-143">To view the list of available targets, use the following query:</span></span>  
  
    ```  
    SELECT p.name AS 'package_name', xo.name AS 'target_name'  
       , xo.description, xo.object_type   
    FROM sys.dm_xe_objects AS xo  
    JOIN sys.dm_xe_packages AS p  
       ON xo.package_guid = p.guid  
    WHERE xo.object_type = 'target'  
    AND (xo.capabilities & 1 = 0  
    OR xo.capabilities IS NULL)  
    ORDER BY p.name, xo.name  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="b1d19-144"> Para obtener información acerca de los diferentes tipos de destino, vea [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="b1d19-144">For information about the different target types, see [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md).</span></span>  
  
6.  <span data-ttu-id="b1d19-145">Revise y agregue las opciones de configuración adicionales que desee.</span><span class="sxs-lookup"><span data-stu-id="b1d19-145">Review and add any additional configuration options.</span></span> <span data-ttu-id="b1d19-146">Por ejemplo, puede configurar opciones tales como el modo de retención de eventos, el tiempo que los eventos se almacenan en búfer en memoria, o si la sesión de eventos debe iniciarse automáticamente cuando se inicie [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b1d19-146">For example, you can configure options such as the event retention mode, how long events are buffered in memory, or whether the event session should start automatically when [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts.</span></span> <span data-ttu-id="b1d19-147">Las opciones se describen en el tema [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b1d19-147">The options are described in the topic [ALTER EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-event-session-transact-sql).</span></span> <span data-ttu-id="b1d19-148">Tenga en cuenta que se asignan los valores predeterminados si no se especifican estas opciones.</span><span class="sxs-lookup"><span data-stu-id="b1d19-148">Be aware that default values are assigned if these options are not specified.</span></span>  
  
7.  <span data-ttu-id="b1d19-149">Inicie la sesión.</span><span class="sxs-lookup"><span data-stu-id="b1d19-149">Start the session.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b1d19-150">Para obtener más información sobre cómo se pueden ver los resultados de una sesión, vea el tema correspondiente al tipo de destino usado en el nodo [Destinos de SQL Server Extended Events](../../2014/database-engine/sql-server-extended-events-targets.md) de los Libros en pantalla.</span><span class="sxs-lookup"><span data-stu-id="b1d19-150">For more information about how to view the session results, see the corresponding topic for the target type that you used in the [SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) node of Books Online.</span></span>  
  
 <span data-ttu-id="b1d19-151">En el ejemplo siguiente se crea una sesión de eventos extendidos denominada IOActivity que captura la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1d19-151">The following example creates an Extended Events session named IOActivity that captures the following information:</span></span>  
  
-   <span data-ttu-id="b1d19-152">Los datos de evento para lecturas de archivos completadas, incluido el texto de [!INCLUDE[tsql](../includes/tsql-md.md)] asociado para las lecturas de archivos en que el identificador de archivo es igual a 1.</span><span class="sxs-lookup"><span data-stu-id="b1d19-152">Event data for completed file reads, including the associated [!INCLUDE[tsql](../includes/tsql-md.md)] text for file reads where the file ID is equal to 1.</span></span>  
  
-   <span data-ttu-id="b1d19-153">Los datos de evento para escrituras de archivos completadas.</span><span class="sxs-lookup"><span data-stu-id="b1d19-153">Event data for completed file writes.</span></span>  
  
-   <span data-ttu-id="b1d19-154">Los datos de evento para los casos en que los datos se escriben de la memoria caché del registro al archivo de registro físico.</span><span class="sxs-lookup"><span data-stu-id="b1d19-154">Event data for when data is written from the log cache to the physical log file.</span></span>  
  
 <span data-ttu-id="b1d19-155">La sesión envía la salida a un archivo de destino.</span><span class="sxs-lookup"><span data-stu-id="b1d19-155">The session sends the output to a file target.</span></span>  
  
```  
CREATE EVENT SESSION IOActivity  
ON SERVER  
  
ADD EVENT sqlserver.file_read_completed  
   (  
   ACTION (sqlserver.sql_text)  
   WHERE file_id = 1),  
ADD EVENT sqlserver.file_write_completed,  
ADD EVENT sqlserver.databases_log_flush  
  
ADD TARGET package0.asynchronous_file_target   
   (SET filename = 'c:\temp\xelog.xel', metadatafile = 'c:\temp\xelog.xem')  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1d19-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1d19-156">See Also</span></span>  
 <span data-ttu-id="b1d19-157">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b1d19-157">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 <span data-ttu-id="b1d19-158">[Destinos de SQL Server Extended Events](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="b1d19-158">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 [<span data-ttu-id="b1d19-159">Paquetes de SQL Server Extended Events</span><span class="sxs-lookup"><span data-stu-id="b1d19-159">SQL Server Extended Events Packages</span></span>](../relational-databases/extended-events/sql-server-extended-events-packages.md)  
  
  
