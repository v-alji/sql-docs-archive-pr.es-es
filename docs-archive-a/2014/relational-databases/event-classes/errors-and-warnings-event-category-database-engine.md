---
title: Errores y advertencias (categoría de eventos del motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Errors and Warnings event category [SQL Server]
- SQL Server event classes, Errors and Warnings event category
- event classes [SQL Server], Errors and Warnings event category
ms.assetid: 249c19b5-af68-4433-80f6-337395176641
author: stevestein
ms.author: sstein
ms.openlocfilehash: d55f37f5401f60ddfeec340af1ae6d532eb6ad01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747574"
---
# <a name="errors-and-warnings-event-category-database-engine"></a><span data-ttu-id="5bba6-102">Errores y advertencias (categoría de eventos del motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-102">Errors and Warnings Event Category (Database Engine)</span></span>
  <span data-ttu-id="5bba6-103">La categoría de eventos **Errores y advertencias** contiene eventos generales de errores y advertencias.</span><span class="sxs-lookup"><span data-stu-id="5bba6-103">The **Errors and Warnings** event category contains general error and warning events.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5bba6-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5bba6-104">In This Section</span></span>  
  
|<span data-ttu-id="5bba6-105">Tema</span><span class="sxs-lookup"><span data-stu-id="5bba6-105">Topic</span></span>|<span data-ttu-id="5bba6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bba6-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5bba6-107">Attention (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-107">Attention Event Class</span></span>](attention-event-class.md)|<span data-ttu-id="5bba6-108">Indica que se ha producido un evento **Attention** .</span><span class="sxs-lookup"><span data-stu-id="5bba6-108">Indicates that an **Attention** event has occurred.</span></span>|  
|[<span data-ttu-id="5bba6-109">Background Job Error (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-109">Background Job Error Event Class</span></span>](background-job-error-event-class.md)|<span data-ttu-id="5bba6-110">Indica que un trabajo en segundo plano ha terminado de forma anómala.</span><span class="sxs-lookup"><span data-stu-id="5bba6-110">Indicates that a background job has terminated abnormally.</span></span>|  
|[<span data-ttu-id="5bba6-111">Bitmap Warning (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-111">Bitmap Warning Event Class</span></span>](bitmap-warning-event-class.md)|<span data-ttu-id="5bba6-112">Indica que el filtrado de mapas de bits se ha deshabilitado en una consulta.</span><span class="sxs-lookup"><span data-stu-id="5bba6-112">Indicates that bitmap filtering has been disabled in a query.</span></span>|  
|[<span data-ttu-id="5bba6-113">Blocked Process Report (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-113">Blocked Process Report Event Class</span></span>](blocked-process-report-event-class.md)|<span data-ttu-id="5bba6-114">Indica que una tarea ha estado bloqueada durante más tiempo del especificado.</span><span class="sxs-lookup"><span data-stu-id="5bba6-114">Indicates that a task has been blocked for more than a specified amount of time.</span></span>|  
|[<span data-ttu-id="5bba6-115">CPU Threshold Exceeded (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-115">CPU Threshold Exceeded Event Class</span></span>](cpu-threshold-exceeded-event-class.md)|<span data-ttu-id="5bba6-116">Indica que el regulador de recursos detecta una consulta que supera el umbral de la CPU especificado.</span><span class="sxs-lookup"><span data-stu-id="5bba6-116">Indicates that the Resource Governor detects a query that exceeds the specified CPU threshold.</span></span>|  
|[<span data-ttu-id="5bba6-117">ErrorLog (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-117">ErrorLog Event Class</span></span>](errorlog-event-class.md)|<span data-ttu-id="5bba6-118">Indica que se han registrado eventos de error en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5bba6-118">Indicates that error events have been logged in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>|  
|[<span data-ttu-id="5bba6-119">EventLog (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-119">EventLog Event Class</span></span>](eventlog-event-class.md)|<span data-ttu-id="5bba6-120">Indica que se han registrado eventos en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="5bba6-120">Indicates that events have been logged in the Windows event log.</span></span>|  
|[<span data-ttu-id="5bba6-121">Exception (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-121">Exception Event Class</span></span>](exception-event-class.md)|<span data-ttu-id="5bba6-122">Indica que se ha producido una excepción en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bba6-122">Indicates that an exception has occurred in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="5bba6-123">Exchange Spill (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-123">Exchange Spill Event Class</span></span>](exchange-spill-event-class.md)|<span data-ttu-id="5bba6-124">Indica que los búferes de comunicaciones de un plan de consulta paralelo se han escrito en la base de datos tempdb.</span><span class="sxs-lookup"><span data-stu-id="5bba6-124">Indicates that communication buffers in a parallel query plan have been written to the tempdb database.</span></span>|  
|[<span data-ttu-id="5bba6-125">Execution Warnings (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-125">Execution Warnings Event Class</span></span>](execution-warnings-event-class.md)|<span data-ttu-id="5bba6-126">Indica que se produjeron advertencias de concesión de memoria durante la ejecución de una instrucción o procedimiento almacenado de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5bba6-126">Indicates that memory grant warnings occurred during the execution of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] statement or stored procedure.</span></span>|  
|[<span data-ttu-id="5bba6-127">Hash Warning (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-127">Hash Warning Event Class</span></span>](hash-warning-event-class.md)|<span data-ttu-id="5bba6-128">Indica que se ha producido una recursividad hash o un salida hash durante una operación de hash.</span><span class="sxs-lookup"><span data-stu-id="5bba6-128">Indicates that a hash recursion or hash bailout has occurred during a hashing operation.</span></span>|  
|[<span data-ttu-id="5bba6-129">Missing Column Statistics (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-129">Missing Column Statistics Event Class</span></span>](missing-column-statistics-event-class.md)|<span data-ttu-id="5bba6-130">Indica que no están disponibles las estadísticas de columna que podrían haber resultado útiles para el optimizador.</span><span class="sxs-lookup"><span data-stu-id="5bba6-130">Indicates that column statistics that could have been useful for the optimizer are not available.</span></span>|  
|[<span data-ttu-id="5bba6-131">Missing Join Predicate (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-131">Missing Join Predicate Event Class</span></span>](missing-join-predicate-event-class.md)|<span data-ttu-id="5bba6-132">Indica que se está ejecutando una consulta que no tiene ningún predicado de combinación.</span><span class="sxs-lookup"><span data-stu-id="5bba6-132">Indicates that a query is being executed that has no join predicate.</span></span>|  
|[<span data-ttu-id="5bba6-133">Sort Warnings (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-133">Sort Warnings Event Class</span></span>](sort-warnings-event-class.md)|<span data-ttu-id="5bba6-134">Indica que las operaciones de orden no caben en la memoria.</span><span class="sxs-lookup"><span data-stu-id="5bba6-134">Indicates that sort operations do not fit into memory.</span></span>|  
|[<span data-ttu-id="5bba6-135">User Error Message (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="5bba6-135">User Error Message Event Class</span></span>](user-error-message-event-class.md)|<span data-ttu-id="5bba6-136">Muestra mensajes de error que ve el usuario.</span><span class="sxs-lookup"><span data-stu-id="5bba6-136">Displays error messages that are seen by the user.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5bba6-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5bba6-137">See Also</span></span>  
 [<span data-ttu-id="5bba6-138">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5bba6-138">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
