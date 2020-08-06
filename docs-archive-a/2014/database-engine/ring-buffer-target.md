---
title: Destino de búfer en anillo | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events], ring buffer target
- ring buffer target [SQL Server extended events]
ms.assetid: 54494e11-b56b-43b7-aa5e-c8724e56b251
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 186e847bb9f9b621543119c25510dc5d6107e274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676150"
---
# <a name="ring-buffer-target"></a><span data-ttu-id="955bd-102">Destino de búfer de anillo</span><span class="sxs-lookup"><span data-stu-id="955bd-102">Ring Buffer Target</span></span>
  <span data-ttu-id="955bd-103">El destino de búfer de anillo guarda datos de eventos en la memoria durante un corto espacio de tiempo.</span><span class="sxs-lookup"><span data-stu-id="955bd-103">The ring buffer target briefly holds event data in memory.</span></span> <span data-ttu-id="955bd-104">Este destino puede administrar los eventos de uno de los dos modos siguientes.</span><span class="sxs-lookup"><span data-stu-id="955bd-104">This target can manage events in one of two modes.</span></span>  
  
-   <span data-ttu-id="955bd-105">El primer modo es un orden FIFO (First In, First Out; primero en entrar, primero en salir) estricto, en el que el evento más antiguo se descarta cuando se usa toda la memoria asignada al destino.</span><span class="sxs-lookup"><span data-stu-id="955bd-105">The first mode is strict first-in first-out (FIFO), where the oldest event is discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="955bd-106">En este modo (valor predeterminado), la opción occurrence_number se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="955bd-106">In this mode (the default), the occurrence_number option is set to 0.</span></span>  
  
-   <span data-ttu-id="955bd-107">El segundo modo es un orden FIFO por evento, en el que se conserva un número determinado de eventos de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="955bd-107">The second mode is per-event FIFO, where a specified number of events of each type is kept.</span></span> <span data-ttu-id="955bd-108">En este modo, los eventos más antiguos de cada tipo se descartan cuando se usa toda la memoria asignada al destino.</span><span class="sxs-lookup"><span data-stu-id="955bd-108">In this mode, the oldest events of each type are discarded when all the memory allocated to the target is used.</span></span> <span data-ttu-id="955bd-109">Puede configurar la opción occurrence_number para especificar el número de eventos de cada tipo que se desea conservar.</span><span class="sxs-lookup"><span data-stu-id="955bd-109">You can configure the occurrence_number option to specify the number of events of each type to keep.</span></span>  
  
 <span data-ttu-id="955bd-110">En la tabla siguiente se describen las opciones disponibles para configurar el destino de búfer de anillo.</span><span class="sxs-lookup"><span data-stu-id="955bd-110">The following table describes the available options for configuring the ring buffer target.</span></span>  
  
|<span data-ttu-id="955bd-111">Opción</span><span class="sxs-lookup"><span data-stu-id="955bd-111">Option</span></span>|<span data-ttu-id="955bd-112">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="955bd-112">Allowed values</span></span>|<span data-ttu-id="955bd-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="955bd-113">Description</span></span>|  
|------------|--------------------|-----------------|  
|<span data-ttu-id="955bd-114">max_memory</span><span class="sxs-lookup"><span data-stu-id="955bd-114">max_memory</span></span>|<span data-ttu-id="955bd-115">Cualquier entero de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="955bd-115">Any 32-bit integer.</span></span> <span data-ttu-id="955bd-116">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="955bd-116">This value is optional.</span></span>|<span data-ttu-id="955bd-117">La cantidad de memoria máxima en kilobytes (kB) que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="955bd-117">The maximum amount of memory in kilobytes (KB) to use.</span></span> <span data-ttu-id="955bd-118">Los eventos existentes se quitan en función del límite que se alcance primero: max_event_limit o max_memory.</span><span class="sxs-lookup"><span data-stu-id="955bd-118">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="955bd-119">El valor máximo es 4194303 KB.</span><span class="sxs-lookup"><span data-stu-id="955bd-119">The maximum value is 4194303 KB.</span></span> <span data-ttu-id="955bd-120">Antes de establecer el tamaño del búfer de anillo en límites en el intervalo de GB, se debe tener en cuenta una consideración cuidadosa, ya que puede afectar a otros consumidores de memoria en SQL Server</span><span class="sxs-lookup"><span data-stu-id="955bd-120">A careful consideration should be made before setting the ring buffer size to limits in the GB range as it may impact other memory consumers in SQL Server</span></span>|  
|<span data-ttu-id="955bd-121">max_event_limit</span><span class="sxs-lookup"><span data-stu-id="955bd-121">max_event_limit</span></span>|<span data-ttu-id="955bd-122">Cualquier entero de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="955bd-122">Any 32-bit integer.</span></span> <span data-ttu-id="955bd-123">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="955bd-123">This value is optional.</span></span>|<span data-ttu-id="955bd-124">El número máximo de eventos que se mantiene en el búfer en anillo.</span><span class="sxs-lookup"><span data-stu-id="955bd-124">The maximum number of events kept in the ring_buffer.</span></span> <span data-ttu-id="955bd-125">Los eventos existentes se quitan en función del límite que se alcance primero: max_event_limit o max_memory.</span><span class="sxs-lookup"><span data-stu-id="955bd-125">Existing events are dropped based on the limit that is first reached: max_event_limit or max_memory.</span></span> <span data-ttu-id="955bd-126">Valor predeterminado = 1000.</span><span class="sxs-lookup"><span data-stu-id="955bd-126">Default = 1000.</span></span>|  
|<span data-ttu-id="955bd-127">occurrence_number</span><span class="sxs-lookup"><span data-stu-id="955bd-127">occurrence_number</span></span>|<span data-ttu-id="955bd-128">Uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="955bd-128">One of the following values:</span></span><br /><br /> <span data-ttu-id="955bd-129">0 (valor predeterminado) = El evento más antiguo se descarta cuando se usa toda la memoria asignada al destino.</span><span class="sxs-lookup"><span data-stu-id="955bd-129">0 (the default) = Oldest event is discarded when all the memory allocated to the target is used.</span></span><br /><br /> <span data-ttu-id="955bd-130">Cualquier entero de 32 bits = el número de eventos de cada tipo que se conservarán antes de que se descarten por cada FIFO.</span><span class="sxs-lookup"><span data-stu-id="955bd-130">Any 32-bit integer = The number of events of each type to keep before being discarded on a per-event FIFO basis.</span></span><br /><br /> <br /><br /> <span data-ttu-id="955bd-131">Este valor es opcional.</span><span class="sxs-lookup"><span data-stu-id="955bd-131">This value is optional.</span></span>|<span data-ttu-id="955bd-132">Modo FIFO que se va a usar y, si se establece en un valor mayor que 0, el número preferido de eventos de cada tipo que se desea conservar en el búfer.</span><span class="sxs-lookup"><span data-stu-id="955bd-132">The FIFO mode to use, and, if set to a value greater than 0, the preferred number of events of each type to keep in the buffer.</span></span>|
| &nbsp; | &nbsp; | &nbsp; |
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="955bd-133">Agregar el destino a una sesión</span><span class="sxs-lookup"><span data-stu-id="955bd-133">Adding the Target to a Session</span></span>  
 <span data-ttu-id="955bd-134">Para agregar el destino del búfer de anillo a una sesión de eventos extendidos, debe incluir la siguiente instrucción al crear o modificar una sesión de eventos:</span><span class="sxs-lookup"><span data-stu-id="955bd-134">To add the ring buffer target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```sql
ADD TARGET package0.ring_buffer  
```  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="955bd-135">Revisar la salida del destino</span><span class="sxs-lookup"><span data-stu-id="955bd-135">Reviewing the Target Output</span></span>  
 <span data-ttu-id="955bd-136">Para revisar la salida del destino de búfer de anillo, puede usar la siguiente consulta, reemplazando *session_name* por el nombre de la sesión de eventos.</span><span class="sxs-lookup"><span data-stu-id="955bd-136">To review the output from the ring buffer target, you can use the following query, replacing *session_name* with the name of the event session.</span></span>  
  
```sql
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="955bd-137">En el siguiente ejemplo se muestra el formato de salida del destino de búfer de anillo.</span><span class="sxs-lookup"><span data-stu-id="955bd-137">The following example shows the ring buffer target output format.</span></span>  
  
```  
<RingBufferTarget eventsPerSec="" processingTime="" totalEventsProcessed="" eventCount="" droppedCount="" memoryUsed="">  
 <event name="" package="" id="" version="" timestamp="">  
    <data name="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </data>  
    <action name="" package="">  
      <type name="" package="" />  
      <value></value>  
      <text></text>  
    </action>  
  </event>  
</RingBufferTarget>  
```


## <a name="see-also"></a><span data-ttu-id="955bd-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="955bd-138">See Also</span></span>

- [<span data-ttu-id="955bd-139">Destinos de SQL Server Extended Events</span><span class="sxs-lookup"><span data-stu-id="955bd-139">SQL Server Extended Events Targets</span></span>](../../2014/database-engine/sql-server-extended-events-targets.md)
- [<span data-ttu-id="955bd-140">sys.dm_xe_session_targets &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="955bd-140">sys.dm_xe_session_targets &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="955bd-141">CREATE EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="955bd-141">CREATE EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-event-session-transact-sql?view=sql-server-2016)
- [<span data-ttu-id="955bd-142">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="955bd-142">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](https://docs.microsoft.com/sql/t-sql/statements/alter-event-session-transact-sql?view=sql-server-2016)

