---
title: Categoría de eventos Procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Stored Procedures event category [SQL Server]
- SQL Server event classes, Stored Procedures event category
- event classes [SQL Server], Stored Procedures event category
ms.assetid: 71bebaa3-a05a-4695-b349-078cecd0949a
author: stevestein
ms.author: sstein
ms.openlocfilehash: df2e0d9a4c077ff16eba09bc5ebb6447d5d27595
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752185"
---
# <a name="stored-procedures-event-category"></a><span data-ttu-id="cf88d-102">Procedimientos almacenados (categoría de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-102">Stored Procedures Event Category</span></span>
  <span data-ttu-id="cf88d-103">La categoría de eventos **Procedimientos almacenados** contiene eventos de procedimientos almacenados generales.</span><span class="sxs-lookup"><span data-stu-id="cf88d-103">The **Stored Procedures** event category contains general stored procedure events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf88d-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cf88d-104">In This Section</span></span>  
  
|<span data-ttu-id="cf88d-105">Tema</span><span class="sxs-lookup"><span data-stu-id="cf88d-105">Topic</span></span>|<span data-ttu-id="cf88d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf88d-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="cf88d-107">RPC:Completed (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-107">RPC:Completed Event Class</span></span>](rpc-completed-event-class.md)|<span data-ttu-id="cf88d-108">Indica que se ha completado una llamada a procedimiento remoto (RPC).</span><span class="sxs-lookup"><span data-stu-id="cf88d-108">Indicates that a remote procedure call (RPC) has been completed.</span></span>|  
|[<span data-ttu-id="cf88d-109">PreConnect:Completed (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-109">PreConnect:Completed Event Class</span></span>](preconnect-completed-event-class.md)|<span data-ttu-id="cf88d-110">Indica el momento en que la función clasificadora del regulador de recursos finaliza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="cf88d-110">Indicates when the Resource Governor classifier function finishes execution.</span></span>|  
|[<span data-ttu-id="cf88d-111">PreConnect:Starting, clase de eventos</span><span class="sxs-lookup"><span data-stu-id="cf88d-111">PreConnect:Starting Event Class</span></span>](preconnect-starting-event-class.md)|<span data-ttu-id="cf88d-112">Indica el momento en que la función clasificadora del regulador de recursos inicia la ejecución.</span><span class="sxs-lookup"><span data-stu-id="cf88d-112">Indicates when the Resource Governor classifier function starts execution.</span></span>|  
|[<span data-ttu-id="cf88d-113">RPC Output Parameter (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-113">RPC Output Parameter Event Class</span></span>](rpc-output-parameter-event-class.md)|<span data-ttu-id="cf88d-114">Realiza un seguimiento de los valores de parámetros de salida de las llamadas a procedimiento remoto tras su ejecución.</span><span class="sxs-lookup"><span data-stu-id="cf88d-114">Traces the output parameter values of remote procedure calls after execution.</span></span>|  
|[<span data-ttu-id="cf88d-115">RPC:Starting (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-115">RPC:Starting Event Class</span></span>](rpc-starting-event-class.md)|<span data-ttu-id="cf88d-116">Indica que se está iniciando una llamada a procedimiento remoto.</span><span class="sxs-lookup"><span data-stu-id="cf88d-116">Indicates that a remote procedure call is starting.</span></span>|  
|[<span data-ttu-id="cf88d-117">SP:CacheHit (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-117">SP:CacheHit Event Class</span></span>](sp-cachehit-event-class.md)|<span data-ttu-id="cf88d-118">Indica que el procedimiento almacenado se encuentra en la caché.</span><span class="sxs-lookup"><span data-stu-id="cf88d-118">Indicates that the stored procedure is in the cache.</span></span>|  
|[<span data-ttu-id="cf88d-119">SP:CacheInsert (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-119">SP:CacheInsert Event Class</span></span>](sp-cacheinsert-event-class.md)|<span data-ttu-id="cf88d-120">Indica que el procedimiento almacenado se ha incluido en la caché.</span><span class="sxs-lookup"><span data-stu-id="cf88d-120">Indicates that the stored procedure has been brought into the cache.</span></span>|  
|[<span data-ttu-id="cf88d-121">SP:CacheMiss (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-121">SP:CacheMiss Event Class</span></span>](sp-cachemiss-event-class.md)|<span data-ttu-id="cf88d-122">Indica que el procedimiento almacenado no se encontró en la caché.</span><span class="sxs-lookup"><span data-stu-id="cf88d-122">Indicates that the stored procedure was not found in the cache.</span></span>|  
|[<span data-ttu-id="cf88d-123">SP:CacheRemove (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-123">SP:CacheRemove Event Class</span></span>](sp-cacheremove-event-class.md)|<span data-ttu-id="cf88d-124">Indica que el procedimiento almacenado se ha eliminado de la caché.</span><span class="sxs-lookup"><span data-stu-id="cf88d-124">Indicates that the stored procedure has been removed from the cache.</span></span>|  
|[<span data-ttu-id="cf88d-125">SP:Completed (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-125">SP:Completed Event Class</span></span>](sp-completed-event-class.md)|<span data-ttu-id="cf88d-126">Indica que ha terminado la ejecución del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="cf88d-126">Indicates that execution of the stored procedure has completed.</span></span>|  
|[<span data-ttu-id="cf88d-127">SP:Recompile (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-127">SP:Recompile Event Class</span></span>](sp-recompile-event-class.md)|<span data-ttu-id="cf88d-128">Indica que se ha vuelto a compilar el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="cf88d-128">Indicates that the stored procedure has been recompiled.</span></span>|  
|[<span data-ttu-id="cf88d-129">SP:Starting (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-129">SP:Starting Event Class</span></span>](sp-starting-event-class.md)|<span data-ttu-id="cf88d-130">Indica que se está iniciando la ejecución del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="cf88d-130">Indicates that execution of the stored procedure is starting.</span></span>|  
|[<span data-ttu-id="cf88d-131">SP:StmtCompleted (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-131">SP:StmtCompleted Event Class</span></span>](sp-stmtcompleted-event-class.md)|<span data-ttu-id="cf88d-132">Indica que ha finalizado una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] de un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="cf88d-132">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has completed.</span></span>|  
|[<span data-ttu-id="cf88d-133">SP:StmtStarting (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="cf88d-133">SP:StmtStarting Event Class</span></span>](sp-stmtstarting-event-class.md)|<span data-ttu-id="cf88d-134">Indica que se ha iniciado una instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] de un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="cf88d-134">Indicates that a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement within a stored procedure has started.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cf88d-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cf88d-135">See Also</span></span>  
 <span data-ttu-id="cf88d-136">[Eventos extendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="cf88d-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="cf88d-137">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cf88d-137">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
