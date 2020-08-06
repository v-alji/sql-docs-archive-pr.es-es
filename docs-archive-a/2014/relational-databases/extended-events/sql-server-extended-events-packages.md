---
title: Paquetes de SQL Server Extended Events | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], packages
- xe
ms.assetid: 6bcb04fc-ca04-48f4-b96a-20b604973447
author: rothja
ms.author: jroth
ms.openlocfilehash: 45c452300c008d486bd1f4ab4c92b5f76b96ecd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662922"
---
# <a name="sql-server-extended-events-packages"></a><span data-ttu-id="b6388-102">Paquetes de SQL Server Extended Events</span><span class="sxs-lookup"><span data-stu-id="b6388-102">SQL Server Extended Events Packages</span></span>
  <span data-ttu-id="b6388-103">Un paquete es un contenedor para objetos de eventos extendidos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6388-103">A package is a container for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Extended Events objects.</span></span> <span data-ttu-id="b6388-104">Hay tres tipos de paquetes de eventos extendidos, que son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b6388-104">There are three kinds of Extended Events packages, which include the following:</span></span>  
  
-   <span data-ttu-id="b6388-105">package0: objetos de sistema de Extended Events.</span><span class="sxs-lookup"><span data-stu-id="b6388-105">package0 - Extended Events system objects.</span></span> <span data-ttu-id="b6388-106">Este es el paquete predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b6388-106">This is the default package.</span></span>  
  
-   <span data-ttu-id="b6388-107">sqlserver: objetos relacionados de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6388-107">sqlserver - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] related objects.</span></span>  
  
-   <span data-ttu-id="b6388-108">sqlos: objetos relacionados de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Operating System (SQLOS).</span><span class="sxs-lookup"><span data-stu-id="b6388-108">sqlos - [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Operating System (SQLOS) related objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6388-109">El paquete de SecAudit es utilizado por la Auditoría de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b6388-109">The SecAudit package is used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Audit.</span></span> <span data-ttu-id="b6388-110">Ninguno de los objetos del paquete están disponibles con el lenguaje de definición de datos (DDL) de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="b6388-110">None of the objects in the package are available through the Extended Events data definition language (DDL).</span></span>  
  
 <span data-ttu-id="b6388-111">Los paquetes se identifican por un nombre, un GUID y el módulo binario que contiene el paquete.</span><span class="sxs-lookup"><span data-stu-id="b6388-111">Packages are identified by a name, a GUID, and the binary module that contains the package.</span></span> <span data-ttu-id="b6388-112">Para obtener más información, vea [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b6388-112">For more information, see [sys.dm_xe_packages &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-packages-transact-sql).</span></span>  
  
 <span data-ttu-id="b6388-113">Un paquete puede contener cualquiera de los objetos siguientes, o todos ellos, que se describen pormenorizadamente más adelante en este tema:</span><span class="sxs-lookup"><span data-stu-id="b6388-113">A package can contain any or all of the following objects, which are discussed in greater detail later in this topic:</span></span>  
  
-   <span data-ttu-id="b6388-114">Eventos</span><span class="sxs-lookup"><span data-stu-id="b6388-114">Events</span></span>  
  
-   <span data-ttu-id="b6388-115">Destinos</span><span class="sxs-lookup"><span data-stu-id="b6388-115">Targets</span></span>  
  
-   <span data-ttu-id="b6388-116">Acciones</span><span class="sxs-lookup"><span data-stu-id="b6388-116">Actions</span></span>  
  
-   <span data-ttu-id="b6388-117">Tipos</span><span class="sxs-lookup"><span data-stu-id="b6388-117">Types</span></span>  
  
-   <span data-ttu-id="b6388-118">Predicados</span><span class="sxs-lookup"><span data-stu-id="b6388-118">Predicates</span></span>  
  
-   <span data-ttu-id="b6388-119">Mapas</span><span class="sxs-lookup"><span data-stu-id="b6388-119">Maps</span></span>  
  
 <span data-ttu-id="b6388-120">Se pueden mezclar objetos de distintos paquetes en una sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="b6388-120">Objects from different packages can be mixed in an event session.</span></span> <span data-ttu-id="b6388-121">Para más información, consulte [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="b6388-121">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
## <a name="package-contents"></a><span data-ttu-id="b6388-122">Contenido de los paquetes</span><span class="sxs-lookup"><span data-stu-id="b6388-122">Package Contents</span></span>  
 <span data-ttu-id="b6388-123">La ilustración siguiente muestra los objetos que pueden existir en paquetes, que se encuentran en un módulo.</span><span class="sxs-lookup"><span data-stu-id="b6388-123">The following illustration shows the objects that can exist in packages, which are contained in a module.</span></span> <span data-ttu-id="b6388-124">Un módulo puede ser un archivo ejecutable o una biblioteca de vínculos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="b6388-124">A module can be an executable or a dynamic link library.</span></span>  
  
 <span data-ttu-id="b6388-125">![Relación de un módulo, varios paquetes y un objeto](../../database-engine/media/xepackagesobjects.gif "Relación de un módulo, varios paquetes y un objeto")</span><span class="sxs-lookup"><span data-stu-id="b6388-125">![The relationship of a module, packages, and object](../../database-engine/media/xepackagesobjects.gif "The relationship of a module, packages, and object")</span></span>  
  
### <a name="events"></a><span data-ttu-id="b6388-126">Eventos</span><span class="sxs-lookup"><span data-stu-id="b6388-126">Events</span></span>  
 <span data-ttu-id="b6388-127">Los eventos son puntos de supervisión de interés en la ruta de ejecución de un programa, como [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6388-127">Events are monitoring points of interest in the execution path of a program, such as [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b6388-128">La activación de un evento conlleva el hecho de que se ha llegado al punto de interés, así como información de estado del momento en que se activó el evento.</span><span class="sxs-lookup"><span data-stu-id="b6388-128">An event firing carries with it the fact that the point of interest was reached, and state information from the time the event was fired.</span></span>  
  
 <span data-ttu-id="b6388-129">Los eventos se pueden utilizar únicamente para realizar el seguimiento o para activar acciones.</span><span class="sxs-lookup"><span data-stu-id="b6388-129">Events can be used solely for tracing purposes or for triggering actions.</span></span> <span data-ttu-id="b6388-130">Estas acciones pueden ser sincrónicas o asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="b6388-130">These actions can either be synchronous or asynchronous.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6388-131">Un evento desconoce las acciones que se pueden activar en respuesta a la activación del evento.</span><span class="sxs-lookup"><span data-stu-id="b6388-131">An event does not have any knowledge of the actions that may be triggered in response to the event firing.</span></span>  
  
 <span data-ttu-id="b6388-132">Un conjunto de eventos de un paquete no se puede cambiar una vez que el paquete se registra con Extended Events.</span><span class="sxs-lookup"><span data-stu-id="b6388-132">A set of events in a package cannot change after the package is registered with Extended Events.</span></span>  
  
 <span data-ttu-id="b6388-133">Todos los eventos tienen un esquema con versiones que define su contenido.</span><span class="sxs-lookup"><span data-stu-id="b6388-133">All events have a versioned schema which defines their contents.</span></span> <span data-ttu-id="b6388-134">Este esquema está formado por columnas de eventos con tipos bien definidos.</span><span class="sxs-lookup"><span data-stu-id="b6388-134">This schema is composed of event columns with well defined types.</span></span> <span data-ttu-id="b6388-135">Un evento de un tipo específico siempre debe proporcionar sus datos en exactamente el mismo orden que se especifica en el esquema.</span><span class="sxs-lookup"><span data-stu-id="b6388-135">An event of a specific type must always provide its data in exactly the same order that is specified in the schema.</span></span> <span data-ttu-id="b6388-136">Sin embargo, un destino de evento no tiene que utilizar todos los datos que se proporcionan.</span><span class="sxs-lookup"><span data-stu-id="b6388-136">However, an event target does not have to consume all the data that is provided.</span></span>  
  
#### <a name="event-categorization"></a><span data-ttu-id="b6388-137">Clasificación de eventos</span><span class="sxs-lookup"><span data-stu-id="b6388-137">Event Categorization</span></span>  
 <span data-ttu-id="b6388-138">Extended Events utiliza un modelo de clasificación de eventos parecido al Seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="b6388-138">Extended Events uses an event categorization model similar to Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="b6388-139">Para la clasificación se utilizan dos propiedades de eventos, canal y palabra clave.</span><span class="sxs-lookup"><span data-stu-id="b6388-139">Two event properties are used for categorization, channel and keyword.</span></span> <span data-ttu-id="b6388-140">La utilización de estas propiedades es compatible con la integración de Extended Events en ETW y sus herramientas.</span><span class="sxs-lookup"><span data-stu-id="b6388-140">Using these properties supports the integration of Extended Events with ETW and its tools.</span></span>  
  
 <span data-ttu-id="b6388-141">**Canal**</span><span class="sxs-lookup"><span data-stu-id="b6388-141">**Channel**</span></span>  
  
 <span data-ttu-id="b6388-142">Un canal identifica a los destinatarios de un evento.</span><span class="sxs-lookup"><span data-stu-id="b6388-142">A channel identifies the audience for an event.</span></span> <span data-ttu-id="b6388-143">Estos canales se describen en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="b6388-143">These channels are described in the following table.</span></span>  
  
|<span data-ttu-id="b6388-144">Término</span><span class="sxs-lookup"><span data-stu-id="b6388-144">Term</span></span>|<span data-ttu-id="b6388-145">Definición</span><span class="sxs-lookup"><span data-stu-id="b6388-145">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="b6388-146">Administración</span><span class="sxs-lookup"><span data-stu-id="b6388-146">Admin</span></span>|<span data-ttu-id="b6388-147">Los eventos de administración se destinan principalmente a usuarios finales, administradores y soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="b6388-147">Admin events are primarily targeted to the end users, administrators, and support.</span></span> <span data-ttu-id="b6388-148">Los eventos que se encuentran en los canales de administración indican un problema con una solución bien determinada ante la que un administrador puede emprender una acción.</span><span class="sxs-lookup"><span data-stu-id="b6388-148">The events that are found in the admin channels indicate a problem with a well-defined solution that an administrator can act on.</span></span> <span data-ttu-id="b6388-149">Un ejemplo de un evento de administración es cuando una aplicación no conecta a una impresora.</span><span class="sxs-lookup"><span data-stu-id="b6388-149">An example of an admin event is when an application fails to connect to a printer.</span></span> <span data-ttu-id="b6388-150">Estos eventos están bien documentados o tienen un mensaje asociado que indica al lector qué hacer para rectificar el problema.</span><span class="sxs-lookup"><span data-stu-id="b6388-150">These events are either well-documented or have a message associated with them that tells the reader what to do to rectify the problem.</span></span>|  
|<span data-ttu-id="b6388-151">Operativos</span><span class="sxs-lookup"><span data-stu-id="b6388-151">Operational</span></span>|<span data-ttu-id="b6388-152">Los eventos operativos se utilizan para analizar y diagnosticar un problema o situación concreta.</span><span class="sxs-lookup"><span data-stu-id="b6388-152">Operational events are used for analyzing and diagnosing a problem or occurrence.</span></span> <span data-ttu-id="b6388-153">Se pueden utilizar para activar herramientas o tareas según el problema o la incidencia.</span><span class="sxs-lookup"><span data-stu-id="b6388-153">They can be used to trigger tools or tasks based on the problem or occurrence.</span></span> <span data-ttu-id="b6388-154">Un ejemplo de evento operativo se produce cuando una impresora se agrega o quita de un sistema.</span><span class="sxs-lookup"><span data-stu-id="b6388-154">An example of an operational event is when a printer is added or removed from a system.</span></span>|  
|<span data-ttu-id="b6388-155">Analíticos</span><span class="sxs-lookup"><span data-stu-id="b6388-155">Analytic</span></span>|<span data-ttu-id="b6388-156">Los eventos analíticos se publican en grandes cantidades.</span><span class="sxs-lookup"><span data-stu-id="b6388-156">Analytic events are published in high volume.</span></span> <span data-ttu-id="b6388-157">Describen el funcionamiento del programa y se utilizan normalmente en investigaciones sobre rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b6388-157">They describe program operation and are typically used in performance investigations.</span></span>|  
|<span data-ttu-id="b6388-158">Depuración</span><span class="sxs-lookup"><span data-stu-id="b6388-158">Debug</span></span>|<span data-ttu-id="b6388-159">Únicamente los programadores utilizan los eventos de depuración para diagnosticar un problema y depurarlo.</span><span class="sxs-lookup"><span data-stu-id="b6388-159">Debug events are used solely by developers to diagnose a problem for debugging.</span></span><br /><br /> <span data-ttu-id="b6388-160">Nota: los eventos del canal de depuración devuelven datos internos de estado específicos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b6388-160">Note: Events in the Debug channel return internal implementation-specific state data.</span></span> <span data-ttu-id="b6388-161">Los esquemas y los datos que devuelven los eventos pueden cambiar o dejar de ser válidos en versiones futuras de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b6388-161">The schemas and data that the events return may change or become invalid in future versions of SQL Server.</span></span> <span data-ttu-id="b6388-162">Por lo tanto, los eventos del canal Depurar pueden cambiar o quitarse en versiones futuras de SQL Server sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="b6388-162">Therefore, events in the Debug channel may change or be removed in future versions of SQL Server without notice.</span></span>|  
  
 <span data-ttu-id="b6388-163">**Palabra clave**</span><span class="sxs-lookup"><span data-stu-id="b6388-163">**Keyword**</span></span>  
  
 <span data-ttu-id="b6388-164">Una palabra clave es específica de la aplicación y permite llevar a cabo una agrupación más precisa de eventos relacionados, lo que facilita la especificación y recuperación de un evento que se desea utilizar en una sesión.</span><span class="sxs-lookup"><span data-stu-id="b6388-164">A keyword is application specific and enables a finer-grained grouping of related events, which makes it easier for you to specify and retrieve an event that you want to use in a session.</span></span> <span data-ttu-id="b6388-165">Se puede utilizar la siguiente consulta para obtener información sobre palabras clave:</span><span class="sxs-lookup"><span data-stu-id="b6388-165">You can use the following query to obtain keyword information.</span></span>  
  
```  
select map_value Keyword from sys.dm_xe_map_values  
where name = 'keyword_map'  
```  
  
> [!NOTE]  
>  <span data-ttu-id="b6388-166">Las palabras clave se asignan estrechamente a la agrupación actual de los eventos de Seguimiento de SQL.</span><span class="sxs-lookup"><span data-stu-id="b6388-166">Keywords map closely to the current grouping of SQL Trace events.</span></span>  
  
### <a name="targets"></a><span data-ttu-id="b6388-167">Destinos</span><span class="sxs-lookup"><span data-stu-id="b6388-167">Targets</span></span>  
 <span data-ttu-id="b6388-168">Los destinos son los consumidores de evento.</span><span class="sxs-lookup"><span data-stu-id="b6388-168">Targets are event consumers.</span></span> <span data-ttu-id="b6388-169">Los destinos procesan los eventos, ya sea de forma sincrónica en el subproceso que activa el evento o de forma asincrónica en un subproceso proporcionado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="b6388-169">Targets process events, either synchronously on the thread that fires the event or asynchronously on a system provided thread.</span></span> <span data-ttu-id="b6388-170">Eventos extendidos proporciona varios destinos que se pueden utilizar según corresponda para dirigir el resultado de los eventos.</span><span class="sxs-lookup"><span data-stu-id="b6388-170">Extended Events provides several targets that you can use as appropriate for directing event output.</span></span> <span data-ttu-id="b6388-171">Para más información, consulte [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span><span class="sxs-lookup"><span data-stu-id="b6388-171">For more information, see [SQL Server Extended Events Targets](../../database-engine/sql-server-extended-events-targets.md).</span></span>  
  
### <a name="actions"></a><span data-ttu-id="b6388-172">Acciones</span><span class="sxs-lookup"><span data-stu-id="b6388-172">Actions</span></span>  
 <span data-ttu-id="b6388-173">Una acción es una respuesta o serie de respuestas de programación a un evento.</span><span class="sxs-lookup"><span data-stu-id="b6388-173">An action is a programmatic response or series of responses to an event.</span></span> <span data-ttu-id="b6388-174">Están enlazadas a un evento y cada evento puede tener un conjunto único de acciones.</span><span class="sxs-lookup"><span data-stu-id="b6388-174">Actions are bound to an event, and each event may have a unique set of actions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6388-175">Las acciones dirigidas a un conjunto concreto de eventos no se pueden enlazar a eventos desconocidos.</span><span class="sxs-lookup"><span data-stu-id="b6388-175">Actions that are intended for a specific set of events cannot bind to unknown events.</span></span>  
  
 <span data-ttu-id="b6388-176">Una acción enlazada a un evento se invoca sincrónicamente en el subproceso que activó el evento.</span><span class="sxs-lookup"><span data-stu-id="b6388-176">An action bound to an event is invoked synchronously on the thread that fired the event.</span></span> <span data-ttu-id="b6388-177">Hay muchos tipos de acciones y tienen gran cantidad de funciones.</span><span class="sxs-lookup"><span data-stu-id="b6388-177">There are many types of actions and they have a wide range of capabilities.</span></span> <span data-ttu-id="b6388-178">Las acciones pueden:</span><span class="sxs-lookup"><span data-stu-id="b6388-178">Actions can:</span></span>  
  
-   <span data-ttu-id="b6388-179">Capturar un volcado de la pila e inspeccionar los datos.</span><span class="sxs-lookup"><span data-stu-id="b6388-179">Capture a stack dump and inspect data.</span></span>  
  
-   <span data-ttu-id="b6388-180">Almacenar información de estado en un contexto local utilizando almacenamiento variable.</span><span class="sxs-lookup"><span data-stu-id="b6388-180">Store state information in a local context using variable storage.</span></span>  
  
-   <span data-ttu-id="b6388-181">Agregar datos de eventos.</span><span class="sxs-lookup"><span data-stu-id="b6388-181">Aggregate event data.</span></span>  
  
-   <span data-ttu-id="b6388-182">Anexar datos a datos de eventos.</span><span class="sxs-lookup"><span data-stu-id="b6388-182">Append data to event data.</span></span>  
  
 <span data-ttu-id="b6388-183">Algunos ejemplos bien conocidos de acciones son:</span><span class="sxs-lookup"><span data-stu-id="b6388-183">Some typical and well known examples of actions are:</span></span>  
  
-   <span data-ttu-id="b6388-184">Volcado de la pila</span><span class="sxs-lookup"><span data-stu-id="b6388-184">Stack dumper</span></span>  
  
-   <span data-ttu-id="b6388-185">Detección del plan de ejecución (solamente[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="b6388-185">Execution plan detection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="b6388-186">recopilación de la pila (solamente[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] )</span><span class="sxs-lookup"><span data-stu-id="b6388-186">stack collection ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] only)</span></span>  
  
-   <span data-ttu-id="b6388-187">Cálculo de estadísticas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b6388-187">Run time statistics calculation</span></span>  
  
-   <span data-ttu-id="b6388-188">Recopilación de datos proporcionados por el usuario si se produce una excepción</span><span class="sxs-lookup"><span data-stu-id="b6388-188">Gather user input on exception</span></span>  
  
### <a name="predicates"></a><span data-ttu-id="b6388-189">Predicados</span><span class="sxs-lookup"><span data-stu-id="b6388-189">Predicates</span></span>  
 <span data-ttu-id="b6388-190">Los predicados son un conjunto de reglas lógicas que se utilizan para evaluar los eventos cuando se procesan.</span><span class="sxs-lookup"><span data-stu-id="b6388-190">Predicates are a set of logical rules that are used to evaluate events when they are processed.</span></span> <span data-ttu-id="b6388-191">Esto permite al usuario de Extended Events capturar selectivamente datos de eventos en función de criterios concretos.</span><span class="sxs-lookup"><span data-stu-id="b6388-191">This enables the Extended Events user to selectively capture event data based on specific criteria.</span></span>  
  
 <span data-ttu-id="b6388-192">Los predicados pueden almacenar datos en un contexto local que se puede utilizar para crear predicados que devuelven el valor verdadero cada *n* minutos o cada *n* veces que se activa un evento.</span><span class="sxs-lookup"><span data-stu-id="b6388-192">Predicates can store data in a local context that can be used for creating predicates that return true once every *n* minutes or every *n* times that an event fires.</span></span> <span data-ttu-id="b6388-193">Este almacenamiento en el contexto local también se puede utilizar para actualizar dinámicamente el predicado, suprimiendo así activaciones futuras del evento si los eventos contienen datos similares.</span><span class="sxs-lookup"><span data-stu-id="b6388-193">This local context storage can also be used to dynamically update the predicate, thereby suppressing future event firing if the events contain similar data.</span></span>  
  
 <span data-ttu-id="b6388-194">Los predicados tienen la capacidad de recuperar información de contexto, como el Id. de subproceso, así como datos específicos del evento.</span><span class="sxs-lookup"><span data-stu-id="b6388-194">Predicates have the ability to retrieve context information, such as the thread ID, as well as event specific data.</span></span> <span data-ttu-id="b6388-195">Los predicados se evalúan como expresiones booleanas completas y admiten un cortocircuito en el primer punto donde se detecta que la expresión completa es falsa.</span><span class="sxs-lookup"><span data-stu-id="b6388-195">Predicates are evaluated as full Boolean expressions, and support short circuiting at the first point where the entire expression is found to be false.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6388-196">No se pueden evaluar los predicados con efectos secundarios si se produce un error de comprobación de predicado con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="b6388-196">Predicates with side effects may not be evaluated if an earlier predicate check fails.</span></span>  
  
### <a name="types"></a><span data-ttu-id="b6388-197">Tipos</span><span class="sxs-lookup"><span data-stu-id="b6388-197">Types</span></span>  
 <span data-ttu-id="b6388-198">Puesto que los datos son una colección de bytes agrupados, la longitud y características de la colección de bytes son necesarias para interpretar los datos.</span><span class="sxs-lookup"><span data-stu-id="b6388-198">Because data is a collection of bytes strung together, the length and characteristics of the byte collection are required in order to interpret the data.</span></span> <span data-ttu-id="b6388-199">Esta información se encapsula en el objeto Tipo.</span><span class="sxs-lookup"><span data-stu-id="b6388-199">This information is encapsulated in the Type object.</span></span> <span data-ttu-id="b6388-200">Los tipos siguientes se proporcionan para los objetos de paquete:</span><span class="sxs-lookup"><span data-stu-id="b6388-200">The following types are provided for package objects:</span></span>  
  
-   <span data-ttu-id="b6388-201">event</span><span class="sxs-lookup"><span data-stu-id="b6388-201">event</span></span>  
  
-   <span data-ttu-id="b6388-202">action</span><span class="sxs-lookup"><span data-stu-id="b6388-202">action</span></span>  
  
-   <span data-ttu-id="b6388-203">Destino</span><span class="sxs-lookup"><span data-stu-id="b6388-203">target</span></span>  
  
-   <span data-ttu-id="b6388-204">pred_source</span><span class="sxs-lookup"><span data-stu-id="b6388-204">pred_source</span></span>  
  
-   <span data-ttu-id="b6388-205">pred_compare</span><span class="sxs-lookup"><span data-stu-id="b6388-205">pred_compare</span></span>  
  
-   <span data-ttu-id="b6388-206">type</span><span class="sxs-lookup"><span data-stu-id="b6388-206">type</span></span>  
  
 <span data-ttu-id="b6388-207">Para obtener más información, vea [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b6388-207">For more information, see [sys.dm_xe_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-objects-transact-sql).</span></span>  
  
### <a name="maps"></a><span data-ttu-id="b6388-208">Mapas</span><span class="sxs-lookup"><span data-stu-id="b6388-208">Maps</span></span>  
 <span data-ttu-id="b6388-209">Una tabla de asignación asigna un valor interno a una cadena, que permite a un usuario saber qué representa el valor.</span><span class="sxs-lookup"><span data-stu-id="b6388-209">A map table maps an internal value to a string, which enables a user to know what the value represents.</span></span> <span data-ttu-id="b6388-210">En lugar de poder obtener solo un valor numérico, un usuario puede obtener una descripción significativa del valor interno.</span><span class="sxs-lookup"><span data-stu-id="b6388-210">Instead of only being able to obtain a numeric value, a user can get a meaningful description of the internal value.</span></span> <span data-ttu-id="b6388-211">La consulta siguiente muestra cómo obtener valores de asignaciones.</span><span class="sxs-lookup"><span data-stu-id="b6388-211">The following query shows how to obtain map values.</span></span>  
  
```  
select map_key, map_value from sys.dm_xe_map_values  
where name = 'lock_mode'  
```  
  
 <span data-ttu-id="b6388-212">La consulta anterior produce el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6388-212">The preceding query produces the following output.</span></span>  
  
 `map_key     map_value`  
  
 `---------------------`  
  
 `0           NL`  
  
 `1           SCH_S`  
  
 `2           SCH_M`  
  
 `3           S`  
  
 `4           U`  
  
 `5           X`  
  
 `6           IS`  
  
 `7           IU`  
  
 `8           IX`  
  
 `9           SIU`  
  
 `10          SIX`  
  
 `11          UIX`  
  
 `12          BU`  
  
 `13          RS_S`  
  
 `14          RS_U`  
  
 `15          RI_NL`  
  
 `16          RI_S`  
  
 `17          RI_U`  
  
 `18          RI_X`  
  
 `19          RX_S`  
  
 `20          RX_U`  
  
 `21          RX_X`  
  
 `21          RX_X`  
  
 <span data-ttu-id="b6388-213">Utilizando esta tabla como ejemplo, suponga que tiene una columna denominada modo, y su valor es 5.</span><span class="sxs-lookup"><span data-stu-id="b6388-213">Using this table as an example, assume that you have a column named mode, and its value is 5.</span></span> <span data-ttu-id="b6388-214">La tabla indica que 5 se asigna a X, lo que quiere decir el tipo de bloqueo es Exclusivo.</span><span class="sxs-lookup"><span data-stu-id="b6388-214">The table indicates that 5 maps to X, which means the lock type is Exclusive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6388-215">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6388-215">See Also</span></span>  
 <span data-ttu-id="b6388-216">[SQL Server sesiones de eventos extendidos](sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="b6388-216">[SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md) </span></span>  
 <span data-ttu-id="b6388-217">[SQL Server motor de eventos extendidos](sql-server-extended-events-engine.md) </span><span class="sxs-lookup"><span data-stu-id="b6388-217">[SQL Server Extended Events Engine](sql-server-extended-events-engine.md) </span></span>  
 [<span data-ttu-id="b6388-218">Destinos de SQL Server Extended Events</span><span class="sxs-lookup"><span data-stu-id="b6388-218">SQL Server Extended Events Targets</span></span>](../../database-engine/sql-server-extended-events-targets.md)  
  
  
