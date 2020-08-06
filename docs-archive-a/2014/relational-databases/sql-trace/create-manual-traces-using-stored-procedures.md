---
title: Creación de seguimientos manuales mediante procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: f6f47fa2-7c17-41d4-9f69-9be144d56832
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e2840dced22ccdba8fe71cc87c05d7fd6fb4be58
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674043"
---
# <a name="create-manual-traces-using-stored-procedures"></a><span data-ttu-id="c8c62-102">Crear seguimientos manuales mediante procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="c8c62-102">Create Manual Traces using Stored Procedures</span></span>
  <span data-ttu-id="c8c62-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ofrece procedimientos almacenados del sistema [!INCLUDE[tsql](../../includes/tsql-md.md)] para crear seguimientos en una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8c62-103">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create traces on an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="c8c62-104">Puede utilizar estos procedimientos almacenados del sistema desde sus propias aplicaciones para crear seguimientos manualmente, en lugar de utilizar el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8c62-104">These system stored procedures can be used from within your own applications to create traces manually, instead of using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span> <span data-ttu-id="c8c62-105">Esto permite escribir aplicaciones personalizadas específicas para las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="c8c62-105">This allows you to write custom applications specific to the needs of your enterprise.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8c62-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c8c62-106">In This Section</span></span>  
 <span data-ttu-id="c8c62-107">En la tabla siguiente se enumeran los procedimientos almacenados del sistema para realizar el seguimiento de una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c8c62-107">The following table lists the system stored procedures for tracing an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
|<span data-ttu-id="c8c62-108">Procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="c8c62-108">Stored procedure</span></span>|<span data-ttu-id="c8c62-109">Tarea realizada</span><span class="sxs-lookup"><span data-stu-id="c8c62-109">Task performed</span></span>|  
|----------------------|--------------------|  
|[<span data-ttu-id="c8c62-110">sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8c62-110">sys.fn_trace_geteventinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-geteventinfo-transact-sql)|<span data-ttu-id="c8c62-111">Devuelve información acerca de los eventos incluidos en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c8c62-111">Returns information about events included in a trace.</span></span>|  
|[<span data-ttu-id="c8c62-112">sys.fn_trace_getinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8c62-112">sys.fn_trace_getinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql)|<span data-ttu-id="c8c62-113">Devuelve información acerca de un seguimiento especificado o de todas los seguimientos existentes.</span><span class="sxs-lookup"><span data-stu-id="c8c62-113">Returns information about a specified trace or all existing traces.</span></span>|  
|[<span data-ttu-id="c8c62-114">sp_trace_create &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8c62-114">sp_trace_create &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql)|<span data-ttu-id="c8c62-115">Crea una definición de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c8c62-115">Creates a trace definition.</span></span> <span data-ttu-id="c8c62-116">El nuevo seguimiento estará en estado de detención.</span><span class="sxs-lookup"><span data-stu-id="c8c62-116">The new trace will be in a stopped state.</span></span>|  
|[<span data-ttu-id="c8c62-117">sp_trace_generateevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8c62-117">sp_trace_generateevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-generateevent-transact-sql)|<span data-ttu-id="c8c62-118">Crea un evento definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c8c62-118">Creates a user-defined event.</span></span>|  
|[<span data-ttu-id="c8c62-119">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8c62-119">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)|<span data-ttu-id="c8c62-120">Agrega o quita una clase de evento o columna de datos de un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c8c62-120">Adds an event class or data column to a trace, or removes one from it.</span></span>|  
|[<span data-ttu-id="c8c62-121">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8c62-121">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)|<span data-ttu-id="c8c62-122">Inicia, detiene o cierra un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c8c62-122">Starts, stops, or closes a trace.</span></span>|  
|[<span data-ttu-id="c8c62-123">sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8c62-123">sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql)|<span data-ttu-id="c8c62-124">Devuelve información acerca de los filtros que se aplicaron a un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c8c62-124">Returns information about filters applied to a trace.</span></span>|  
|[<span data-ttu-id="c8c62-125">sp_trace_setfilter &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c8c62-125">sp_trace_setfilter &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)|<span data-ttu-id="c8c62-126">Aplica un filtro nuevo o modificado a un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c8c62-126">Applies a new or modified filter to a trace.</span></span>|  
  
 <span data-ttu-id="c8c62-127">**Para definir su propio seguimiento mediante procedimientos almacenados**</span><span class="sxs-lookup"><span data-stu-id="c8c62-127">**To define your own trace using stored procedures**</span></span>  
  
1.  <span data-ttu-id="c8c62-128">Especifique los eventos que quiera capturar con **sp_trace_setevent**.</span><span class="sxs-lookup"><span data-stu-id="c8c62-128">Specify the events to capture using **sp_trace_setevent**.</span></span>  
  
2.  <span data-ttu-id="c8c62-129">Especifique los filtros de eventos.</span><span class="sxs-lookup"><span data-stu-id="c8c62-129">Specify any event filters.</span></span> <span data-ttu-id="c8c62-130">Para obtener más información, vea [Establecer un filtro de seguimiento &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="c8c62-130">For more information, see [Set a Trace Filter &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md).</span></span>  
  
3.  <span data-ttu-id="c8c62-131">Especifique el destino de los datos de eventos capturados con **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="c8c62-131">Specify the destination for the captured event data using **sp_trace_create**.</span></span>  
  
 <span data-ttu-id="c8c62-132">Para obtener un ejemplo de cómo usar los procedimientos almacenados de seguimiento, vea [Crear un seguimiento &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c8c62-132">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](../sql-trace/create-a-trace-transact-sql.md).</span></span>  
  
 <span data-ttu-id="c8c62-133">**Para configurar los valores predeterminados de definición de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="c8c62-133">**To set trace definition defaults**</span></span>  
  
 [<span data-ttu-id="c8c62-134">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c8c62-134">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
 <span data-ttu-id="c8c62-135">**Para establecer las opciones predeterminadas de presentación de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="c8c62-135">**To set trace display defaults**</span></span>  
  
 [<span data-ttu-id="c8c62-136">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c8c62-136">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/set-trace-display-defaults-sql-server-profiler.md)  
  
 <span data-ttu-id="c8c62-137">**Para crear un seguimiento**</span><span class="sxs-lookup"><span data-stu-id="c8c62-137">**To create a trace**</span></span>  
  
 [<span data-ttu-id="c8c62-138">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c8c62-138">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
 [<span data-ttu-id="c8c62-139">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8c62-139">Transact-SQL</span></span>](../sql-trace/create-a-trace-transact-sql.md)  
  
 <span data-ttu-id="c8c62-140">**Para agregar o quitar eventos de una plantilla de seguimiento**</span><span class="sxs-lookup"><span data-stu-id="c8c62-140">**To add or remove events from a trace template**</span></span>  
  
 [<span data-ttu-id="c8c62-141">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="c8c62-141">SQL Server Profiler</span></span>](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
 [<span data-ttu-id="c8c62-142">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c8c62-142">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
