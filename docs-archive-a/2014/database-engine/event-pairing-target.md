---
title: Destino de emparejamiento de eventos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- pairing target [SQL Server extended events]
- event pairing target
- targets [SQL Server extended events], pairing target
ms.assetid: 3c87dcfb-543a-4bd8-a73d-1390bdf4ffa3
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: a1a6beb1c6996e6e12f16c4555fd9dfcab97617d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746429"
---
# <a name="event-pairing-target"></a><span data-ttu-id="8c507-102">Destino de emparejamiento de eventos</span><span class="sxs-lookup"><span data-stu-id="8c507-102">Event Pairing Target</span></span>
  <span data-ttu-id="8c507-103">El destino de emparejamiento de eventos asocia dos eventos usando una o varias columnas de datos presentes en cada evento.</span><span class="sxs-lookup"><span data-stu-id="8c507-103">The event pairing target matches two events using one or more columns of data that are present in each event.</span></span> <span data-ttu-id="8c507-104">Muchos eventos vienen en parejas, como por ejemplo, bloqueo y desbloqueo.</span><span class="sxs-lookup"><span data-stu-id="8c507-104">Many events come in pairs, for example, lock acquires and lock releases.</span></span> <span data-ttu-id="8c507-105">Una vez emparejada un flujo de eventos, se descartan ambos eventos.</span><span class="sxs-lookup"><span data-stu-id="8c507-105">After an event sequence is paired, both events are discarded.</span></span> <span data-ttu-id="8c507-106">El descarte de los conjuntos asociados permite una detección fácil de adquisiciones de bloqueos que no se han liberado.</span><span class="sxs-lookup"><span data-stu-id="8c507-106">Discarding matched sets allows for easy detection of lock acquisitions that have not been released.</span></span>  
  
 <span data-ttu-id="8c507-107">Al emplear los filtros de nivel de eventos, el destino de emparejamientos puede usarse para capturar solo eventos que no coincidan con los criterios predefinidos.</span><span class="sxs-lookup"><span data-stu-id="8c507-107">By using event-level filters, the pairing target can be used to only capture events that do not match pre-set criteria.</span></span>  
  
 <span data-ttu-id="8c507-108">Al usar el destino de emparejamiento de eventos, se podrán elegir los dos eventos que se van a asociar, junto con una secuencia de columnas en la que realizar la asociación.</span><span class="sxs-lookup"><span data-stu-id="8c507-108">When you use the event pairing target, you can choose two events that will be matched, together with a sequence of columns to perform the matching on.</span></span> <span data-ttu-id="8c507-109">Todas las columnas de este flujo deben ser del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="8c507-109">All the columns in this sequence must be of the same type.</span></span>  
  
 <span data-ttu-id="8c507-110">La siguiente tabla describe las opciones disponibles para configurar el emparejamiento de eventos.</span><span class="sxs-lookup"><span data-stu-id="8c507-110">The following table describes the available options for configuring event pairing.</span></span>  
  
|<span data-ttu-id="8c507-111">Opción</span><span class="sxs-lookup"><span data-stu-id="8c507-111">Option</span></span>|<span data-ttu-id="8c507-112">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="8c507-112">Allowed values</span></span>|<span data-ttu-id="8c507-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c507-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="8c507-114">begin_event</span><span class="sxs-lookup"><span data-stu-id="8c507-114">begin_event</span></span>|<span data-ttu-id="8c507-115">Un nombre de evento presente en la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="8c507-115">Any event name that is present in the current session.</span></span>|<span data-ttu-id="8c507-116">El nombre de evento que especifica el evento de inicio en una secuencia emparejada.</span><span class="sxs-lookup"><span data-stu-id="8c507-116">The event name specifying the beginning event in a paired sequence.</span></span>|  
|<span data-ttu-id="8c507-117">end_event</span><span class="sxs-lookup"><span data-stu-id="8c507-117">end_event</span></span>|<span data-ttu-id="8c507-118">Un nombre de evento presente en la sesión actual.</span><span class="sxs-lookup"><span data-stu-id="8c507-118">Any event name that is present in the current session.</span></span>|<span data-ttu-id="8c507-119">El nombre de evento que especifica el evento final en una secuencia emparejada.</span><span class="sxs-lookup"><span data-stu-id="8c507-119">The event name specifying the ending event in a paired sequence.</span></span>|  
|<span data-ttu-id="8c507-120">begin_matching_columns</span><span class="sxs-lookup"><span data-stu-id="8c507-120">begin_matching_columns</span></span>|<span data-ttu-id="8c507-121">Una lista ordenada y delimitada por comas de nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="8c507-121">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="8c507-122">Las columnas en las que realizar la asociación.</span><span class="sxs-lookup"><span data-stu-id="8c507-122">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="8c507-123">end_matching_columns</span><span class="sxs-lookup"><span data-stu-id="8c507-123">end_matching_columns</span></span>|<span data-ttu-id="8c507-124">Una lista ordenada y delimitada por comas de nombres de columna.</span><span class="sxs-lookup"><span data-stu-id="8c507-124">A comma-delimited, ordered list of column names.</span></span>|<span data-ttu-id="8c507-125">Las columnas en las que realizar la asociación.</span><span class="sxs-lookup"><span data-stu-id="8c507-125">The columns to perform matching on.</span></span>|  
|<span data-ttu-id="8c507-126">begin_matching_actions</span><span class="sxs-lookup"><span data-stu-id="8c507-126">begin_matching_actions</span></span>|<span data-ttu-id="8c507-127">Una lista de acciones ordenada y delimitada por comas.</span><span class="sxs-lookup"><span data-stu-id="8c507-127">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="8c507-128">Las acciones en las que se debe realizar la asociación.</span><span class="sxs-lookup"><span data-stu-id="8c507-128">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="8c507-129">end_matching_actions</span><span class="sxs-lookup"><span data-stu-id="8c507-129">end_matching_actions</span></span>|<span data-ttu-id="8c507-130">Una lista de acciones ordenada y delimitada por comas.</span><span class="sxs-lookup"><span data-stu-id="8c507-130">A comma-delimited, ordered list of actions.</span></span>|<span data-ttu-id="8c507-131">Las acciones en las que se debe realizar la asociación.</span><span class="sxs-lookup"><span data-stu-id="8c507-131">The actions to perform matching on.</span></span>|  
|<span data-ttu-id="8c507-132">respond_to_memory_pressure</span><span class="sxs-lookup"><span data-stu-id="8c507-132">respond_to_memory_pressure</span></span>|<span data-ttu-id="8c507-133">Uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="8c507-133">One of the following values:</span></span><br /><br /> <span data-ttu-id="8c507-134">0 = No responder.</span><span class="sxs-lookup"><span data-stu-id="8c507-134">0 = Do not respond.</span></span><br /><br /> <span data-ttu-id="8c507-135">1 = Dejar de agregar nuevos elementos huérfanos a la lista en caso de que exista presión de memoria.</span><span class="sxs-lookup"><span data-stu-id="8c507-135">1 = Stop adding new orphans to the list when there is memory pressure.</span></span>|<span data-ttu-id="8c507-136">La respuesta del destino a los eventos de memoria.</span><span class="sxs-lookup"><span data-stu-id="8c507-136">The target response to memory events.</span></span> <span data-ttu-id="8c507-137">Si se estable en 1 y la memoria del servidor es insuficiente, se quitará la información no emparejada.</span><span class="sxs-lookup"><span data-stu-id="8c507-137">If set to 1 and the server is low on memory, unpaired information that is being maintained is removed.</span></span>|  
|<span data-ttu-id="8c507-138">max_orphans</span><span class="sxs-lookup"><span data-stu-id="8c507-138">max_orphans</span></span>||<span data-ttu-id="8c507-139">Especifica el número total de eventos no emparejados que se recopilarán en el destino.</span><span class="sxs-lookup"><span data-stu-id="8c507-139">Specifies the total number of unpaired events that will be collected in the target.</span></span> <span data-ttu-id="8c507-140">Una vez alcanzado el límite, los eventos no emparejados se quitan con un orden FIFO (primero en entrar, primero en salir).</span><span class="sxs-lookup"><span data-stu-id="8c507-140">Once the limit is reached, unpaired events are removed on a first-in, first-out (FIFO) basis.</span></span> <span data-ttu-id="8c507-141">Valor predeterminado = 10,000.</span><span class="sxs-lookup"><span data-stu-id="8c507-141">Default = 10,000.</span></span>|  
  
 <span data-ttu-id="8c507-142">Todos los datos asociados a un evento se capturan y almacenan para futuros emparejamientos.</span><span class="sxs-lookup"><span data-stu-id="8c507-142">All the data associated with an event is captured and stored for future pairing.</span></span> <span data-ttu-id="8c507-143">Además, se recopilan los datos agregados por las acciones.</span><span class="sxs-lookup"><span data-stu-id="8c507-143">In addition, data added by actions is also collected.</span></span> <span data-ttu-id="8c507-144">Los datos de eventos recopilados se almacenan en la memoria y, por lo tanto, tienen un límite finito.</span><span class="sxs-lookup"><span data-stu-id="8c507-144">The collected event data is stored in memory, and therefore has a finite limit.</span></span> <span data-ttu-id="8c507-145">Este límite depende de la actividad y capacidad del sistema.</span><span class="sxs-lookup"><span data-stu-id="8c507-145">This limit is based on system capacity and activity.</span></span> <span data-ttu-id="8c507-146">En lugar de tomar la cantidad de memoria máxima que se va a utilizar como un parámetro, la memoria utilizada dependerá de los recursos disponibles del sistema.</span><span class="sxs-lookup"><span data-stu-id="8c507-146">Instead of taking the maximum amount of memory to be used as a parameter, the amount of memory used will be based on available system resources.</span></span> <span data-ttu-id="8c507-147">Cuando no hay recursos, se quitarán los eventos no emparejados que se han conservado.</span><span class="sxs-lookup"><span data-stu-id="8c507-147">When these are not available, unpaired events that have been retained will be dropped.</span></span> <span data-ttu-id="8c507-148">Si un evento no se ha emparejado y se quita, el evento asociado aparecerá como un evento no emparejado.</span><span class="sxs-lookup"><span data-stu-id="8c507-148">If an event has not been paired and is dropped, the matching event will appear as an unpaired event.</span></span>  
  
 <span data-ttu-id="8c507-149">El destino de emparejamiento serializa los eventos no emparejados a un formato XML.</span><span class="sxs-lookup"><span data-stu-id="8c507-149">The pairing target serializes unpaired events to an XML format.</span></span> <span data-ttu-id="8c507-150">Este formato no sigue ningún esquema.</span><span class="sxs-lookup"><span data-stu-id="8c507-150">This format does not conform to any schema.</span></span> <span data-ttu-id="8c507-151">El formato solo contiene dos tipos de elementos.</span><span class="sxs-lookup"><span data-stu-id="8c507-151">The format only contains two element types.</span></span> <span data-ttu-id="8c507-152">El **\<unpaired>** elemento es la raíz, seguido de uno.</span><span class="sxs-lookup"><span data-stu-id="8c507-152">The **\<unpaired>** element is the root, followed by one.</span></span> <span data-ttu-id="8c507-153">**\<event>** elemento para cada evento no emparejado que se está realizando actualmente.</span><span class="sxs-lookup"><span data-stu-id="8c507-153">**\<event>** element for each unpaired event that is currently being tracked.</span></span> <span data-ttu-id="8c507-154">El **\<event>** elemento contiene un atributo que contiene el nombre del evento no emparejado.</span><span class="sxs-lookup"><span data-stu-id="8c507-154">The **\<event>** element contains one attribute that contains the name of the unpaired event.</span></span>  
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="8c507-155">Agregar el destino a una sesión</span><span class="sxs-lookup"><span data-stu-id="8c507-155">Adding the Target to a Session</span></span>  
 <span data-ttu-id="8c507-156">Para agregar el destino de búsqueda del par a una sesión de eventos extendidos, debe incluir la siguiente instrucción al crear o modificar una sesión de eventos:</span><span class="sxs-lookup"><span data-stu-id="8c507-156">To add the pair matching target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```  
ADD TARGET package0.pair_matching   
```  
  
 <span data-ttu-id="8c507-157">Para ello se usaría una instrucción SET, para definir los eventos del principio y el fin, y qué acciones o columnas hacer coincidir.</span><span class="sxs-lookup"><span data-stu-id="8c507-157">You would follow this with a SET statement, to define the beginning and ending events, and which actions or columns to match.</span></span> <span data-ttu-id="8c507-158">En el ejemplo siguiente se muestra la sintaxis de ejemplo de la coincidencia de pares de los eventos sqlserver.lock_acquired y sqlserver.lock_released.</span><span class="sxs-lookup"><span data-stu-id="8c507-158">The following example shows sample syntax for pair matching the sqlserver.lock_acquired and sqlserver.lock_released events.</span></span>  
  
```  
   ( SET begin_event = 'sqlserver.lock_acquired',  
      begin_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
      end_event = 'sqlserver.lock_released',  
      end_matching_columns = 'database_id, resource_0, resource_1, resource_2, transaction_id, mode',  
   respond_to_memory_pressure = 1)  
```  
  
 <span data-ttu-id="8c507-159">Para obtener más información, vea [Determinar las consultas que mantienen bloqueos](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span><span class="sxs-lookup"><span data-stu-id="8c507-159">For more information, see [Determine Which Queries Are Holding Locks](../relational-databases/extended-events/determine-which-queries-are-holding-locks.md).</span></span>  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="8c507-160">Revisar la salida del destino</span><span class="sxs-lookup"><span data-stu-id="8c507-160">Reviewing the Target Output</span></span>  
 <span data-ttu-id="8c507-161">Para revisar la salida del destino de coincidencia del par, puede usar la siguiente consulta, reemplazando *session_name* por el nombre de la sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="8c507-161">To review the output for the pair matching target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```  
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="8c507-162">En el siguiente ejemplo se muestra el formato de salida del destino de emparejamiento.</span><span class="sxs-lookup"><span data-stu-id="8c507-162">The following example shows the pairing target output format.</span></span>  
  
```  
<unpaired truncated = "0" matchedCount = "[matched count]" memoryPressureDroppedCount = " [lost count]">  
    <event name  = "[event name]" package = "[package]" id= "[event ID value]" version = "[event version]">  
    <data name = "[column name]">   
    <type name = "[column type]" package = "[type package]" />   
    <value>[column value]</value>  
    <text value>[text value]</text>>  
        </data>  
    </event>  
</unpaired>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c507-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c507-163">See Also</span></span>  
 <span data-ttu-id="8c507-164">[Destinos de SQL Server Extended Events](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="8c507-164">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 <span data-ttu-id="8c507-165">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8c507-165">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span></span>  
 <span data-ttu-id="8c507-166">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8c507-166">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="8c507-167">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8c507-167">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-event-session-transact-sql)  
  
  
