---
title: Categoría de eventos Bloqueos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Locks event category [SQL Server]
- SQL Server event classes, Locks event category
- event classes [SQL Server], Locks event category
- lock escalation [SQL Server], locks event category
ms.assetid: 27d6afa2-7dab-4fe7-a1ad-064b879dc654
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a202279021e3e6c7c3c44a167792bb9439567aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669690"
---
# <a name="locks-event-category"></a><span data-ttu-id="267f7-102">Bloqueos (categoría de eventos)</span><span class="sxs-lookup"><span data-stu-id="267f7-102">Locks Event Category</span></span>
  <span data-ttu-id="267f7-103">Use las clases de eventos de la categoría de eventos **Bloqueos** para supervisar la actividad de bloqueo en una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="267f7-103">Use the event classes in the **Locks** event category to monitor locking activity in an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="267f7-104">Estas clases de evento pueden ayudarle a investigar los problemas de bloqueo provocados por varios usuarios que leen y modifican datos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="267f7-104">These event classes can help you investigate locking problems caused by multiple users reading and modifying data concurrently.</span></span>  
  
 <span data-ttu-id="267f7-105">Puesto que el [!INCLUDE[ssDE](../../includes/ssde-md.md)] a menudo procesa varios bloqueos, la captura de las clases de eventos en **Bloqueos** durante un seguimiento puede incurrir en un aumento significativo de la carga y dar como resultado archivos o tablas de seguimiento muy grandes.</span><span class="sxs-lookup"><span data-stu-id="267f7-105">Because the [!INCLUDE[ssDE](../../includes/ssde-md.md)] often processes many locks, capturing the **Locks** event classes during a trace can incur significant overhead and result in large trace files or tables.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="267f7-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="267f7-106">In This Section</span></span>  
  
|<span data-ttu-id="267f7-107">Tema</span><span class="sxs-lookup"><span data-stu-id="267f7-107">Topic</span></span>|<span data-ttu-id="267f7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="267f7-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="267f7-109">Deadlock Graph (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="267f7-109">Deadlock Graph Event Class</span></span>](deadlock-graph-event-class.md)|<span data-ttu-id="267f7-110">Proporciona una descripción en XML de un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="267f7-110">Provides an XML description of a deadlock.</span></span>|  
|[<span data-ttu-id="267f7-111">Lock:Acquired (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="267f7-111">Lock:Acquired Event Class</span></span>](lock-acquired-event-class.md)|<span data-ttu-id="267f7-112">Indica que se ha adquirido un bloqueo en un recurso, por ejemplo una fila de una tabla.</span><span class="sxs-lookup"><span data-stu-id="267f7-112">Indicates that a lock has been acquired on a resource, such as a row in a table.</span></span>|  
|[<span data-ttu-id="267f7-113">Lock:Cancel (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="267f7-113">Lock:Cancel Event Class</span></span>](lock-cancel-event-class.md)|<span data-ttu-id="267f7-114">Realiza un seguimiento de las solicitudes de bloqueos que se cancelaron antes de adquirirse el bloqueo (por ejemplo, para impedir un interbloqueo).</span><span class="sxs-lookup"><span data-stu-id="267f7-114">Tracks requests for locks that were canceled before the lock was acquired (for example, to prevent a deadlock).</span></span>|  
|[<span data-ttu-id="267f7-115">Lock:Deadlock Chain (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="267f7-115">Lock:Deadlock Chain Event Class</span></span>](lock-deadlock-chain-event-class.md)|<span data-ttu-id="267f7-116">Supervisa cuándo se producen condiciones de interbloqueo y a qué objetos afectan.</span><span class="sxs-lookup"><span data-stu-id="267f7-116">Monitors when deadlock conditions occur and which objects are involved.</span></span>|  
|[<span data-ttu-id="267f7-117">Lock:Deadlock (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="267f7-117">Lock:Deadlock Event Class</span></span>](lock-deadlock-event-class.md)|<span data-ttu-id="267f7-118">Realiza un seguimiento de cuándo una transacción ha solicitado un bloqueo en un recurso ya bloqueado por otra transacción, con el resultado de un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="267f7-118">Tracks when a transaction has requested a lock on a resource already locked by another transaction, resulting in a deadlock.</span></span>|  
|[<span data-ttu-id="267f7-119">Lock:Escalation (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="267f7-119">Lock:Escalation Event Class</span></span>](lock-escalation-event-class.md)|<span data-ttu-id="267f7-120">Indica que un bloqueo específico se ha convertido en un bloqueo general.</span><span class="sxs-lookup"><span data-stu-id="267f7-120">Indicates that a finer-grained lock has been converted to a coarser-grained lock.</span></span>|  
|[<span data-ttu-id="267f7-121">Lock:Released (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="267f7-121">Lock:Released Event Class</span></span>](lock-released-event-class.md)|<span data-ttu-id="267f7-122">Realiza un seguimiento de cuándo se libera un bloqueo.</span><span class="sxs-lookup"><span data-stu-id="267f7-122">Tracks when a lock is released.</span></span>|  
|[<span data-ttu-id="267f7-123">Clase de eventos Lock:Timeout &#40;timeout &#62; 0&#41;</span><span class="sxs-lookup"><span data-stu-id="267f7-123">Lock:Timeout &#40;timeout &#62; 0&#41; Event Class</span></span>](lock-timeout-timeout-0-event-class.md)|<span data-ttu-id="267f7-124">Realiza un seguimiento de cuándo no se pueden completar solicitudes de bloqueo porque otra transacción tiene bloqueado el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="267f7-124">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span> <span data-ttu-id="267f7-125">Este evento solo se produce en situaciones en las que el valor de tiempo de espera del bloqueo es superior a cero.</span><span class="sxs-lookup"><span data-stu-id="267f7-125">This event occurs only in situations where the lock time-out value is greater than zero.</span></span>|  
|[<span data-ttu-id="267f7-126">Lock:Timeout (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="267f7-126">Lock:Timeout Event Class</span></span>](lock-timeout-event-class.md)|<span data-ttu-id="267f7-127">Realiza un seguimiento de cuándo no se pueden completar solicitudes de bloqueo porque otra transacción tiene bloqueado el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="267f7-127">Tracks when lock requests cannot be completed because another transaction has a blocking lock on the requested resource.</span></span>|  
  
  
