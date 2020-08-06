---
title: Motor de SQL Server Extended Events | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], engine
ms.assetid: d74642a5-42b9-4a15-aa3d-f98bfe695050
author: rothja
ms.author: jroth
ms.openlocfilehash: ef11ac8e2cfaf39d2bca90f1d5d52439989ee327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662924"
---
# <a name="sql-server-extended-events-engine"></a><span data-ttu-id="170f5-102">Motor de SQL Server Extended Events</span><span class="sxs-lookup"><span data-stu-id="170f5-102">SQL Server Extended Events Engine</span></span>
  <span data-ttu-id="170f5-103">El motor de Extended Events [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es una colección de servicios y objetos que:</span><span class="sxs-lookup"><span data-stu-id="170f5-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Extended Events engine is a collection of services and objects that:</span></span>  
  
-   <span data-ttu-id="170f5-104">Habilita la definición de eventos.</span><span class="sxs-lookup"><span data-stu-id="170f5-104">Enable the definition of events.</span></span>  
  
-   <span data-ttu-id="170f5-105">Habilita el procesamiento de los datos de eventos.</span><span class="sxs-lookup"><span data-stu-id="170f5-105">Enable processing event data.</span></span>  
  
-   <span data-ttu-id="170f5-106">Administra los objetos y servicios de Extended Events en el sistema.</span><span class="sxs-lookup"><span data-stu-id="170f5-106">Manage Extended Events services and objects in the system.</span></span>  
  
-   <span data-ttu-id="170f5-107">Mantiene una lista de las sesiones de Extended Events y administra el acceso a dicha lista.</span><span class="sxs-lookup"><span data-stu-id="170f5-107">Maintain a list of Extended Events sessions and manage access to that list.</span></span>  
  
 <span data-ttu-id="170f5-108">El motor de Extended Events no proporciona eventos o acciones que se van a llevar a cabo cuando se activa un evento.</span><span class="sxs-lookup"><span data-stu-id="170f5-108">The Extended Events engine itself does not provide any events or actions to take when an event fires.</span></span> <span data-ttu-id="170f5-109">Los procesos que utiliza el motor de Extended Events definen la interacción con el motor.</span><span class="sxs-lookup"><span data-stu-id="170f5-109">The processes that use the Extended Events engine define interaction with the engine.</span></span> <span data-ttu-id="170f5-110">Estos procesos agregan los puntos de evento y proporcionan las acciones que se van a llevar a cabo en respuesta a la activación de eventos.</span><span class="sxs-lookup"><span data-stu-id="170f5-110">These processes add event points and supply the actions to take in response to event firing.</span></span>  
  
 <span data-ttu-id="170f5-111">La ilustración siguiente muestra una vista simplificada de una sesión de Extended Events.</span><span class="sxs-lookup"><span data-stu-id="170f5-111">The following illustration shows a simplified view of an Extended Events session.</span></span> <span data-ttu-id="170f5-112">Para más información, consulte [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="170f5-112">For more information, see [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).</span></span>  
  
 <span data-ttu-id="170f5-113">![Arquitectura de eventos extendidos detallada](../../database-engine/media/xearchitecturedetailed.gif "Arquitectura de eventos extendidos detallada")</span><span class="sxs-lookup"><span data-stu-id="170f5-113">![Detailed extended events architecture](../../database-engine/media/xearchitecturedetailed.gif "Detailed extended events architecture")</span></span>  
  
 <span data-ttu-id="170f5-114">Tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="170f5-114">Note the following:</span></span>  
  
-   <span data-ttu-id="170f5-115">Cada proceso de Windows puede tener uno o más módulos (**proceso Win32**, **módulo Win32**).</span><span class="sxs-lookup"><span data-stu-id="170f5-115">Each Windows process can have one or more modules (**Win32 process**, **Win32 module**).</span></span> <span data-ttu-id="170f5-116">También se les conoce como módulos *binarios* o *ejecutables*.</span><span class="sxs-lookup"><span data-stu-id="170f5-116">These are also known as *binaries* or *executable modules*.</span></span>  
  
-   <span data-ttu-id="170f5-117">Cada uno de los módulos de los procesos de Windows puede contener uno o varios paquetes de eventos extendidos (**Paquete**), que contienen uno o más objetos de eventos extendidos (**Tipo**, **Destino**, **Acción**, **Asignación**, **Predicado**y **Evento**).</span><span class="sxs-lookup"><span data-stu-id="170f5-117">Each of the Windows process modules can contain one or more Extended Events packages (**Package**), which contain one or more Extended Events objects (**Type**, **Target**, **Action**, **Map**, **Predicate**, and **Event**).</span></span>  
  
-   <span data-ttu-id="170f5-118">Dentro de un proceso de host solo puede haber una instancia del motor de eventos extendidos (**motor de eventos extendidos**) que:</span><span class="sxs-lookup"><span data-stu-id="170f5-118">Inside a host process there can only be one instance of the Extended Events engine (**Extended event engine**), which:</span></span>  
  
    -   <span data-ttu-id="170f5-119">Administra algunos aspectos de la sesión (por ejemplo, enumerar las sesiones).</span><span class="sxs-lookup"><span data-stu-id="170f5-119">Manages some aspects of the session (for example, enumerating sessions).</span></span>  
  
    -   <span data-ttu-id="170f5-120">Administra el envío (**Distribuidor**).</span><span class="sxs-lookup"><span data-stu-id="170f5-120">Handles dispatching (**Dispatcher**).</span></span> <span data-ttu-id="170f5-121">Es similar a un grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="170f5-121">This is similar to a thread pool.</span></span>  
  
    -   <span data-ttu-id="170f5-122">Administra los búferes de la memoria (**Búfer**) para los eventos.</span><span class="sxs-lookup"><span data-stu-id="170f5-122">Handles memory buffers (**Buffer**) for events.</span></span> <span data-ttu-id="170f5-123">Cuando se llenan los búferes, los búferes se envían a los destinos.</span><span class="sxs-lookup"><span data-stu-id="170f5-123">When buffers are filled, the buffers are dispatched to targets.</span></span>  
  
-   <span data-ttu-id="170f5-124">Una vez que se crea una sesión y, opcionalmente, los eventos se enlazan a la sesión (**Contexto de la sesión**):</span><span class="sxs-lookup"><span data-stu-id="170f5-124">After a session is created and events are optionally bound to the session (**Session context**):</span></span>  
  
    -   <span data-ttu-id="170f5-125">Las instancias de los destinos (**Instancia de destino**) también pueden crearse y agregarse a la sesión.</span><span class="sxs-lookup"><span data-stu-id="170f5-125">Instances of targets (**Target instance**) may be also be created and added to the session.</span></span>  
  
    -   <span data-ttu-id="170f5-126">Cuando se llenan los búferes, dichos búferes se envían a los destinos.</span><span class="sxs-lookup"><span data-stu-id="170f5-126">When buffers are filled, those buffers are dispatched to targets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="170f5-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="170f5-127">See Also</span></span>  
 [<span data-ttu-id="170f5-128">Eventos extendidos</span><span class="sxs-lookup"><span data-stu-id="170f5-128">Extended Events</span></span>](extended-events.md)  
  
  
