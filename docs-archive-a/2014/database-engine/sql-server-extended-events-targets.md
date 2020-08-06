---
title: SQL Server destinos de eventos extendidos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events]
- extended events [SQL Server], targets
ms.assetid: e281684c-40d1-4cf9-a0d4-7ea1ecffa384
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 010b7cc29543f266b77aaf180c50173ef9f70346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663076"
---
# <a name="sql-server-extended-events-targets"></a><span data-ttu-id="b591a-102">SQL Server Extended Events Targets</span><span class="sxs-lookup"><span data-stu-id="b591a-102">SQL Server Extended Events Targets</span></span>
  <span data-ttu-id="b591a-103">Los destinos de Extended Events de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] son los consumidores de eventos.</span><span class="sxs-lookup"><span data-stu-id="b591a-103">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events targets are event consumers.</span></span> <span data-ttu-id="b591a-104">Los destinos escriben en un archivo, almacenan los datos de evento en un búfer de memoria o agregan los datos de evento.</span><span class="sxs-lookup"><span data-stu-id="b591a-104">Targets can write to a file, store event data in a memory buffer, or aggregate event data.</span></span> <span data-ttu-id="b591a-105">Los destinos procesan los datos de forma sincrónica o asincrónica.</span><span class="sxs-lookup"><span data-stu-id="b591a-105">Targets can process data synchronously or asynchronously.</span></span>  
  
 <span data-ttu-id="b591a-106">El diseño de Extended Events garantiza que los destinos reciban eventos una sola vez por sesión.</span><span class="sxs-lookup"><span data-stu-id="b591a-106">The Extended Events design ensures that targets are guaranteed to receive events once and only once per session.</span></span>  
  
 <span data-ttu-id="b591a-107">Los eventos extendidos proporcionan los destinos siguientes que pueden utilizarse en una sesión de eventos extendidos:</span><span class="sxs-lookup"><span data-stu-id="b591a-107">Extended Events provide the following targets that you can use for an Extended Events session:</span></span>  
  
-   [<span data-ttu-id="b591a-108">Contador de eventos</span><span class="sxs-lookup"><span data-stu-id="b591a-108">Event counter</span></span>](../../2014/database-engine/event-counter-target.md)  
  
     <span data-ttu-id="b591a-109">Cuenta todos los eventos especificados que se producen durante una sesión de eventos extendidos.</span><span class="sxs-lookup"><span data-stu-id="b591a-109">Counts all specified events that occur during an Extended Events session.</span></span> <span data-ttu-id="b591a-110">Se usa para obtener información sobre las características de carga de trabajo sin agregar la sobrecarga que supone una colección de eventos completa.</span><span class="sxs-lookup"><span data-stu-id="b591a-110">Use to obtain information about workload characteristics without adding the overhead of full event collection.</span></span> <span data-ttu-id="b591a-111">Es un destino sincrónico.</span><span class="sxs-lookup"><span data-stu-id="b591a-111">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="b591a-112">Archivo de eventos</span><span class="sxs-lookup"><span data-stu-id="b591a-112">Event file</span></span>](../../2014/database-engine/event-file-target.md)  
  
     <span data-ttu-id="b591a-113">Se usa para escribir en disco la salida de la sesión de eventos de los búferes de memoria completos.</span><span class="sxs-lookup"><span data-stu-id="b591a-113">Use to write event session output from complete memory buffers to disk.</span></span> <span data-ttu-id="b591a-114">Es un destino asincrónico.</span><span class="sxs-lookup"><span data-stu-id="b591a-114">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="b591a-115">Emparejamiento de eventos</span><span class="sxs-lookup"><span data-stu-id="b591a-115">Event pairing</span></span>](../../2014/database-engine/event-pairing-target.md)  
  
     <span data-ttu-id="b591a-116">Muchos tipos de eventos se producen en parejas, como por ejemplo, bloqueo y desbloqueo.</span><span class="sxs-lookup"><span data-stu-id="b591a-116">Many kinds of events occur in pairs, such as lock acquires and lock releases.</span></span> <span data-ttu-id="b591a-117">Se usa para determinar cuándo un determinado evento emparejado no se produce en el conjunto correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b591a-117">Use to determine when a specified paired event does not occur in a matched set.</span></span> <span data-ttu-id="b591a-118">Es un destino asincrónico.</span><span class="sxs-lookup"><span data-stu-id="b591a-118">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="b591a-119">Seguimiento de eventos para Windows (ETW)</span><span class="sxs-lookup"><span data-stu-id="b591a-119">Event Tracing for Windows (ETW)</span></span>](../relational-databases/extended-events/event-tracing-for-windows-target.md)  
  
     <span data-ttu-id="b591a-120">Se usa para establecer correlaciones entre los eventos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] y los datos de evento de la aplicación o del sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="b591a-120">Use to correlate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events with Windows operating system or application event data.</span></span> <span data-ttu-id="b591a-121">Es un destino sincrónico.</span><span class="sxs-lookup"><span data-stu-id="b591a-121">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="b591a-122">Histograma</span><span class="sxs-lookup"><span data-stu-id="b591a-122">Histogram</span></span>](../../2014/database-engine/histogram-target.md)  
  
     <span data-ttu-id="b591a-123">Se usa para contar el número de veces que se produce el evento especificado en función de la acción o columna de evento indicada.</span><span class="sxs-lookup"><span data-stu-id="b591a-123">Use to count the number of times that a specified event occurs, based on a specified event column or action.</span></span> <span data-ttu-id="b591a-124">Es un destino asincrónico.</span><span class="sxs-lookup"><span data-stu-id="b591a-124">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="b591a-125">Búfer en anillo</span><span class="sxs-lookup"><span data-stu-id="b591a-125">Ring buffer</span></span>](../../2014/database-engine/ring-buffer-target.md)  
  
     <span data-ttu-id="b591a-126">Se usa para mantener los datos de evento en memoria con un orden FIFO (primero en entrar, primero en salir) o con un orden FIFO por evento.</span><span class="sxs-lookup"><span data-stu-id="b591a-126">Use to hold the event data in memory on a first-in first-out (FIFO) basis, or on a per-event FIFO basis.</span></span> <span data-ttu-id="b591a-127">Es un destino asincrónico.</span><span class="sxs-lookup"><span data-stu-id="b591a-127">This is an asynchronous target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b591a-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b591a-128">See Also</span></span>  
 <span data-ttu-id="b591a-129">[Eventos extendidos](../relational-databases/extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="b591a-129">[Extended Events](../relational-databases/extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="b591a-130">[Paquetes de SQL Server Extended Events](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span><span class="sxs-lookup"><span data-stu-id="b591a-130">[SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span></span>  
 <span data-ttu-id="b591a-131">[SQL Server sesiones de eventos extendidos](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="b591a-131">[SQL Server Extended Events Sessions](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span></span>  
 [<span data-ttu-id="b591a-132">Motor de SQL Server Extended Events</span><span class="sxs-lookup"><span data-stu-id="b591a-132">SQL Server Extended Events Engine</span></span>](../relational-databases/extended-events/sql-server-extended-events-engine.md)  
  
  
