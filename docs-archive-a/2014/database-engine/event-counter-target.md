---
title: Destino del contador de eventos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- synchronous event counter target [SQL Server extended events]
- targets [SQL Server extended events], synchronous event counter target
ms.assetid: 342e08d1-dcca-4a71-ae64-cb61b55b85bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f540f39176ec638cdc9236b315e306ecebfdcb1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746433"
---
# <a name="event-counter-target"></a><span data-ttu-id="c7f82-102">Destino del contador de eventos</span><span class="sxs-lookup"><span data-stu-id="c7f82-102">Event Counter Target</span></span>
  <span data-ttu-id="c7f82-103">El destino del contador de eventos cuenta todos los eventos que se producen durante una sesión de Extended Events.</span><span class="sxs-lookup"><span data-stu-id="c7f82-103">The event counter target counts all events that occur during an Extended Events session.</span></span> <span data-ttu-id="c7f82-104">Si utiliza el destino del contador de eventos, puede obtener información sobre las características de la carga de trabajo sin agregar la sobrecarga que supone una recopilación de eventos completa.</span><span class="sxs-lookup"><span data-stu-id="c7f82-104">By using the event counter target, you can obtain information about workload characteristics without adding the overhead of full event collection.</span></span> <span data-ttu-id="c7f82-105">Este destino no tiene parámetros personalizables.</span><span class="sxs-lookup"><span data-stu-id="c7f82-105">This target has no customizable parameters.</span></span>  
  
## <a name="adding-the-target-to-a-session"></a><span data-ttu-id="c7f82-106">Agregar el destino a una sesión</span><span class="sxs-lookup"><span data-stu-id="c7f82-106">Adding the Target to a Session</span></span>  
 <span data-ttu-id="c7f82-107">Para agregar el destino del contador de eventos a una sesión de Extended Events, debe incluir la siguiente instrucción al crear o modificar una sesión de eventos:</span><span class="sxs-lookup"><span data-stu-id="c7f82-107">To add the event counter target to an Extended Events session, you must include the following statement when you create or alter an event session:</span></span>  
  
```  
ADD TARGET package0.event_counter  
```  
  
## <a name="reviewing-the-target-output"></a><span data-ttu-id="c7f82-108">Revisar la salida del destino</span><span class="sxs-lookup"><span data-stu-id="c7f82-108">Reviewing the Target Output</span></span>  
 <span data-ttu-id="c7f82-109">Para revisar la salida del destino del contador de eventos, puede usar la siguiente consulta, reemplazando *nombre_de_sesión* por el nombre de la sesión de eventos:</span><span class="sxs-lookup"><span data-stu-id="c7f82-109">To review the output from the event counter target, you can use the following query, replacing *session_name* with the name of the event session:</span></span>  
  
```  
SELECT name, target_name, CAST(xet.target_data AS xml)  
FROM sys.dm_xe_session_targets AS xet  
JOIN sys.dm_xe_sessions AS xe  
   ON (xe.address = xet.event_session_address)  
WHERE xe.name = 'session_name'  
```  
  
 <span data-ttu-id="c7f82-110">En el ejemplo siguiente se muestra el formato de la salida del destino del contador de eventos.</span><span class="sxs-lookup"><span data-stu-id="c7f82-110">The following example shows the event counter target output format.</span></span>  
  
```  
<CounterTarget truncated = "0">  
  <Packages>  
    <Package name = "[package name]">  
      <Event name = "[event name]" count = "[number]" />  
    </Package>  
  </Packages>  
</CounterTarget>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7f82-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c7f82-111">See Also</span></span>  
 <span data-ttu-id="c7f82-112">[Destinos de SQL Server Extended Events](../../2014/database-engine/sql-server-extended-events-targets.md) </span><span class="sxs-lookup"><span data-stu-id="c7f82-112">[SQL Server Extended Events Targets](../../2014/database-engine/sql-server-extended-events-targets.md) </span></span>  
 <span data-ttu-id="c7f82-113">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c7f82-113">[sys.dm_xe_session_targets &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-xe-session-targets-transact-sql) </span></span>  
 <span data-ttu-id="c7f82-114">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c7f82-114">[CREATE EVENT SESSION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-event-session-transact-sql) </span></span>  
 [<span data-ttu-id="c7f82-115">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c7f82-115">ALTER EVENT SESSION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-event-session-transact-sql)  
  
  
