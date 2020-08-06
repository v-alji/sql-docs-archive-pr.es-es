---
title: Estados de creación de reflejo (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- states [SQL Server], database mirroring
- PENDING_FAILOVER state
- mirroring states [SQL Server]
- DISCONNECTED state
- SYNCHRONIZING state
- SYNCHRONIZED state
- SUSPENDED state
- database mirroring [SQL Server], states
ms.assetid: 90062917-74f9-471b-b49e-bc153ae1a468
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d458939ba233bdfe7a99edd38afc74b5433ae061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663661"
---
# <a name="mirroring-states-sql-server"></a><span data-ttu-id="71682-102">Estados de creacion de reflejo (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="71682-102">Mirroring States (SQL Server)</span></span>
  <span data-ttu-id="71682-103">Durante una sesión de creación de reflejo de la base de datos, la base de datos reflejada siempre se encuentra en un estado específico (el *estado de creación de reflejo*).</span><span class="sxs-lookup"><span data-stu-id="71682-103">During a database mirroring session, the mirrored database is always in a specific state (the *mirroring state*).</span></span> <span data-ttu-id="71682-104">El estado de la base de datos refleja el estado de la comunicación, el flujo de datos y la diferencia de datos entre los asociados.</span><span class="sxs-lookup"><span data-stu-id="71682-104">The state of the database reflects the communication status, data flow, and the difference in data between the partners.</span></span> <span data-ttu-id="71682-105">La sesión de creación de reflejo de la base de datos adopta el mismo estado que la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="71682-105">The database mirroring session adopts the same state as the principal database.</span></span>  
  
 <span data-ttu-id="71682-106">Durante una sesión de creación de reflejo de una base de datos, las instancias de servidor se supervisan entre sí.</span><span class="sxs-lookup"><span data-stu-id="71682-106">Throughout a database mirroring session, the server instances monitor each other.</span></span> <span data-ttu-id="71682-107">Los asociados usan el estado de creación de reflejo para supervisar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="71682-107">The partners use the mirroring state to monitor the database.</span></span> <span data-ttu-id="71682-108">A excepción del estado PENDING_FAILOVER, las bases de datos principal y reflejada siempre tienen el mismo estado.</span><span class="sxs-lookup"><span data-stu-id="71682-108">With the exception of the PENDING_FAILOVER state, the principal and mirror database are always in the same state.</span></span> <span data-ttu-id="71682-109">Si se establece un testigo para la sesión, cada uno de los asociados supervisa el testigo mediante su estado de conexión (CONNECTED o DISCONNECTED).</span><span class="sxs-lookup"><span data-stu-id="71682-109">If a witness is set for the session, each of the partners monitors the witness using its connection state (CONNECTED or DISCONNECTED).</span></span>  
  
 <span data-ttu-id="71682-110">Los estados posibles de creación de reflejo de la base de datos son:</span><span class="sxs-lookup"><span data-stu-id="71682-110">The possible mirroring states of the database are as follows:</span></span>  
  
|<span data-ttu-id="71682-111">Estado de creación de reflejo</span><span class="sxs-lookup"><span data-stu-id="71682-111">Mirroring state</span></span>|<span data-ttu-id="71682-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="71682-112">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="71682-113">SYNCHRONIZING</span><span class="sxs-lookup"><span data-stu-id="71682-113">SYNCHRONIZING</span></span>|<span data-ttu-id="71682-114">El contenido de la base de datos reflejada está atrasado con respecto al contenido de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="71682-114">The contents of the mirror database are lagging behind the contents of the principal database.</span></span> <span data-ttu-id="71682-115">El servidor principal va enviando entradas del registro al servidor reflejado, que está aplicando los cambios a la base de datos reflejada para ponerla al día.</span><span class="sxs-lookup"><span data-stu-id="71682-115">The principal server is sending log records to the mirror server, which is applying the changes to the mirror database to roll it forward.</span></span><br /><br /> <span data-ttu-id="71682-116">Al inicio de una sesión de creación de reflejo de la base de datos, la base de datos se encuentra en el estado SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="71682-116">At the start of a database mirroring session, the database is in the SYNCHRONIZING state.</span></span> <span data-ttu-id="71682-117">En este estado, el servidor principal sigue dando servicio a la base de datos, mientras que el reflejado intenta ponerse al día.</span><span class="sxs-lookup"><span data-stu-id="71682-117">The principal server is serving the database, and the mirror is trying to catch up.</span></span>|  
|<span data-ttu-id="71682-118">SYNCHRONIZED</span><span class="sxs-lookup"><span data-stu-id="71682-118">SYNCHRONIZED</span></span>|<span data-ttu-id="71682-119">El estado de creación de reflejo cambia a SYNCHRONIZED cuando el servidor reflejado está suficientemente al día con respecto al servidor principal.</span><span class="sxs-lookup"><span data-stu-id="71682-119">When the mirror server becomes sufficiently caught up to the principal server, the mirroring state changes to SYNCHRONIZED.</span></span> <span data-ttu-id="71682-120">La base de datos permanece en este estado mientras el servidor principal continúa con el envío de cambios al servidor reflejado, y el servidor reflejado continúa con la aplicación de los cambios en la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="71682-120">The database remains in this state as long as the principal server continues to send changes to the mirror server and the mirror server continues to apply changes to the mirror database.</span></span><br /><br /> <span data-ttu-id="71682-121">Si la seguridad de las transacciones se establece en FULL, se admite la conmutación automática por error y la conmutación manual por error en el estado SYNCHRONIZED; no hay pérdida de datos tras la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="71682-121">If transaction safety is set to FULLautomatic failover and manual failover are both supported in the SYNCHRONIZED state, there is no data loss after a failover.</span></span><br /><br /> <span data-ttu-id="71682-122">Si la seguridad de las transacciones está desactivada, siempre es posible sufrir alguna pérdida de datos, incluso en el estado SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="71682-122">If transaction safety is off, some data loss is always possible, even in the SYNCHRONIZED state.</span></span>|  
|<span data-ttu-id="71682-123">SUSPENDED</span><span class="sxs-lookup"><span data-stu-id="71682-123">SUSPENDED</span></span>|<span data-ttu-id="71682-124">La copia reflejada de la base de datos no está disponible.</span><span class="sxs-lookup"><span data-stu-id="71682-124">The mirror copy of the database is not available.</span></span> <span data-ttu-id="71682-125">La base de datos principal se ejecuta sin enviar registros al servidor reflejado, condición conocida como *ejecución expuesta*.</span><span class="sxs-lookup"><span data-stu-id="71682-125">The principal database is running without sending any logs to the mirror server, a condition known as *running exposed*.</span></span> <span data-ttu-id="71682-126">Éste es el estado después de una conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="71682-126">This is the state after a failover.</span></span><br /><br /> <span data-ttu-id="71682-127">Una sesión también puede tener el estado SUSPENDED como resultado de errores al rehacer, o bien si el administrador pone en pausa la sesión.</span><span class="sxs-lookup"><span data-stu-id="71682-127">A session can also become SUSPENDED as a result of redo errors or if the administrator pauses the session.</span></span><br /><br /> <span data-ttu-id="71682-128">SUSPENDED es un estado persistente que sobrevive a los apagados e inicios de los asociados.</span><span class="sxs-lookup"><span data-stu-id="71682-128">SUSPENDED is a persistent state that survives partner shutdowns and startups.</span></span>|  
|<span data-ttu-id="71682-129">PENDING_FAILOVER</span><span class="sxs-lookup"><span data-stu-id="71682-129">PENDING_FAILOVER</span></span>|<span data-ttu-id="71682-130">Este estado se encuentra solo en el servidor principal después de que se haya iniciado una conmutación por error, pero el servidor todavía no se ha pasado al rol reflejado.</span><span class="sxs-lookup"><span data-stu-id="71682-130">This state is found only on the principal server after a failover has begun, but the server has not transitioned into the mirror role.</span></span><br /><br /> <span data-ttu-id="71682-131">Cuando se inicia la conmutación por error, la base de datos principal pasa al estado PENDING_FAILOVER, finaliza rápidamente cualquier conexión de usuario y asume el rol reflejado inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="71682-131">When the failover is initiated, the principal database goes into the PENDING_FAILOVER state, quickly terminates any user connections, and takes over the mirror role soon thereafter.</span></span>|  
|<span data-ttu-id="71682-132">DISCONNECTED</span><span class="sxs-lookup"><span data-stu-id="71682-132">DISCONNECTED</span></span>|<span data-ttu-id="71682-133">El asociado ha perdido la comunicación con el otro asociado.</span><span class="sxs-lookup"><span data-stu-id="71682-133">The partner has lost communication with the other partner.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71682-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71682-134">See Also</span></span>  
 [<span data-ttu-id="71682-135">Supervisar la creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="71682-135">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  