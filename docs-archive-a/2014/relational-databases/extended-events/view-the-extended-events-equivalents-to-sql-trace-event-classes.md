---
title: Ver los eventos extendidos equivalentes a las clases de evento de Seguimiento de SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- SQL Trace, extended events equivalents
- extended events [SQL Server], SQL Trace equivalents
- extended events [SQL Server], user configurable events
ms.assetid: 7f24104c-201d-4361-9759-f78a27936011
author: rothja
ms.author: jroth
ms.openlocfilehash: 37459359f9f6cb7e3951b705c4007477ec43e36a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744079"
---
# <a name="view-the-extended-events-equivalents-to-sql-trace-event-classes"></a><span data-ttu-id="7e4eb-102">Ver los eventos extendidos equivalentes a las clases de evento de Seguimiento de SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e4eb-102">View the Extended Events Equivalents to SQL Trace Event Classes</span></span>
  <span data-ttu-id="7e4eb-103">Si desea utilizar los eventos extendidos para recopilar datos de evento que son equivalentes a clases de eventos de Seguimiento de SQL y columnas, es útil saber cómo los eventos de Seguimiento de SQL se asignan a eventos y acciones de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-103">If you want to use Extended Events to collect event data that is equivalent to SQL Trace event classes and columns, it is useful to understand how the SQL Trace events map to Extended Events events and actions.</span></span>  
  
 <span data-ttu-id="7e4eb-104">Puede utilizar el procedimiento siguiente para ver los eventos y acciones de eventos extendidos que son equivalentes a cada evento de Seguimiento de SQL y sus columnas asociadas.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-104">You can use the following procedure to view the Extended Events events and actions that are equivalent to each SQL Trace event and its associated columns.</span></span>  
  
## <a name="to-view-the-extended-events-equivalents-to-sql-trace-events-using-query-editor"></a><span data-ttu-id="7e4eb-105">Para ver los equivalentes de eventos extendidos a los eventos de Seguimiento de SQL mediante el Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="7e4eb-105">To view the Extended Events equivalents to SQL Trace events using Query Editor</span></span>  
  
-   <span data-ttu-id="7e4eb-106">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ejecute la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="7e4eb-106">From Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], run the following query:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    SELECT DISTINCT  
       tb.trace_event_id,  
       te.name AS 'Event Class',  
       em.package_name AS 'Package',  
       em.xe_event_name AS 'XEvent Name',  
       tb.trace_column_id,  
       tc.name AS 'SQL Trace Column',  
       am.xe_action_name as 'Extended Events action'  
    FROM (sys.trace_events te LEFT OUTER JOIN sys.trace_xe_event_map em  
       ON te.trace_event_id = em.trace_event_id) LEFT OUTER JOIN sys.trace_event_bindings tb  
       ON em.trace_event_id = tb.trace_event_id LEFT OUTER JOIN sys.trace_columns tc  
       ON tb.trace_column_id = tc.trace_column_id LEFT OUTER JOIN sys.trace_xe_action_map am  
       ON tc.trace_column_id = am.trace_column_id  
    ORDER BY te.name, tc.name  
    ```  
  
 <span data-ttu-id="7e4eb-107">Cuando vea los resultados, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7e4eb-107">When you view the results, note the following:</span></span>  
  
-   <span data-ttu-id="7e4eb-108">Si todas las columnas devuelven NULL a excepción de la columna Event Class, indica que la clase de eventos no se ha migrado desde el Seguimiento de SQL.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-108">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="7e4eb-109">Si solo el valor de la columna de acción Extended Events es NULL, indica que una de las siguientes condiciones es cierta:</span><span class="sxs-lookup"><span data-stu-id="7e4eb-109">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="7e4eb-110">La columna de Seguimiento de SQL se asigna a uno de los campos de datos asociado al evento de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-110">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="7e4eb-111">Cada evento de eventos extendidos tiene un conjunto predeterminado de campos de datos que se incluyen automáticamente en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-111">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="7e4eb-112">La columna de acción no tiene un equivalente significativo de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-112">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="7e4eb-113">Un ejemplo de esto es la columna EventClass de Seguimiento de SQL.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-113">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="7e4eb-114">Esta columna no es necesaria en eventos extendidos porque el nombre del evento sirve para el mismo fin.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-114">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="7e4eb-115">Para las clases de eventos de Seguimiento de SQL configurables por el usuario (de UserConfigurable:1 a UserConfigurable:9), los eventos extendidos usan un solo evento para reemplazarlos.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-115">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="7e4eb-116">El evento se denomina user_event.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-116">The event is named user_event.</span></span> <span data-ttu-id="7e4eb-117">Este evento se produce al usar sp_trace_generateevent, que es el mismo procedimiento almacenado usado por el Seguimiento de SQL.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-117">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="7e4eb-118">El evento user_event se devuelve independientemente del identificador de evento que se pase al procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-118">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="7e4eb-119">Pero un campo event_id se devuelve como parte de los datos de evento.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-119">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="7e4eb-120">Esto permite generar un predicado basado en el identificador de evento.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-120">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="7e4eb-121">Por ejemplo, si usa UserConfigurable:0 (event_id = 82) en el código, puede agregar el evento user_event a la sesión y especificar un predicado de "event_id = 82".</span><span class="sxs-lookup"><span data-stu-id="7e4eb-121">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="7e4eb-122">Por tanto, no tiene que cambiar el código porque el procedimiento almacenado sp_trace_generateevent genera el evento user_event de eventos extendidos y la clase de eventos de Seguimiento de SQL equivalente.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-122">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
-   <span data-ttu-id="7e4eb-123">Si todas las columnas devuelven NULL a excepción de la columna Event Class, indica que la clase de eventos no se ha migrado desde el Seguimiento de SQL.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-123">If all columns return NULL except for the Event Class column, this indicates that the event class was not migrated from SQL Trace.</span></span>  
  
-   <span data-ttu-id="7e4eb-124">Si solo el valor de la columna de acción Extended Events es NULL, indica que una de las siguientes condiciones es cierta:</span><span class="sxs-lookup"><span data-stu-id="7e4eb-124">If only the value in the Extended Events action column is NULL, this indicates that either of the following conditions is true:</span></span>  
  
    -   <span data-ttu-id="7e4eb-125">La columna de Seguimiento de SQL se asigna a uno de los campos de datos asociado al evento de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-125">The SQL Trace column maps to one of the data fields that is associated with the Extended Events event.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="7e4eb-126">Cada evento de eventos extendidos tiene un conjunto predeterminado de campos de datos que se incluyen automáticamente en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-126">Each Extended Events event has a default set of data fields that are automatically included in the result set.</span></span>  
  
    -   <span data-ttu-id="7e4eb-127">La columna de acción no tiene un equivalente significativo de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-127">The action column does not have a meaningful Extended Events equivalent.</span></span> <span data-ttu-id="7e4eb-128">Un ejemplo de esto es la columna EventClass de Seguimiento de SQL.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-128">An example of this is the EventClass column in SQL Trace.</span></span> <span data-ttu-id="7e4eb-129">Esta columna no es necesaria en eventos extendidos porque el nombre del evento sirve para el mismo fin.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-129">This column is not needed in Extended Events because the event name serves the same purpose.</span></span>  
  
-   <span data-ttu-id="7e4eb-130">Para las clases de eventos de Seguimiento de SQL configurables por el usuario (de UserConfigurable:1 a UserConfigurable:9), los eventos extendidos usan un solo evento para reemplazarlos.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-130">For user configurable SQL Trace event classes (UserConfigurable:1 through UserConfigurable:9), Extended Events uses a single event to replace these.</span></span> <span data-ttu-id="7e4eb-131">El evento se denomina user_event.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-131">The event is named user_event.</span></span> <span data-ttu-id="7e4eb-132">Este evento se produce al usar sp_trace_generateevent, que es el mismo procedimiento almacenado usado por el Seguimiento de SQL.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-132">This event is raised by using sp_trace_generateevent, which is the same stored procedure that is used by SQL Trace.</span></span> <span data-ttu-id="7e4eb-133">El evento user_event se devuelve independientemente del identificador de evento que se pase al procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-133">The user_event event is returned regardless of which event ID is passed to the stored procedure.</span></span> <span data-ttu-id="7e4eb-134">Pero un campo event_id se devuelve como parte de los datos de evento.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-134">However, an event_id field is returned as part of the event data.</span></span> <span data-ttu-id="7e4eb-135">Esto permite generar un predicado basado en el identificador de evento.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-135">This enables you to build a predicate that is based on the event ID.</span></span> <span data-ttu-id="7e4eb-136">Por ejemplo, si usa UserConfigurable:0 (event_id = 82) en el código, puede agregar el evento user_event a la sesión y especificar un predicado de "event_id = 82".</span><span class="sxs-lookup"><span data-stu-id="7e4eb-136">For example, if you use UserConfigurable:0 (event ID = 82) in the code, you can add the user_event event to the session, and specify a predicate of 'event_id = 82'.</span></span> <span data-ttu-id="7e4eb-137">Por tanto, no tiene que cambiar el código porque el procedimiento almacenado sp_trace_generateevent genera el evento user_event de eventos extendidos y la clase de eventos de Seguimiento de SQL equivalente.</span><span class="sxs-lookup"><span data-stu-id="7e4eb-137">Therefore, you do not have to change the code because the sp_trace_generateevent stored procedure generates the Extended Events user_event event, and the equivalent SQL Trace event class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4eb-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e4eb-138">See Also</span></span>  
 [<span data-ttu-id="7e4eb-139">sp_trace_generateevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4eb-139">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)  
  
  
