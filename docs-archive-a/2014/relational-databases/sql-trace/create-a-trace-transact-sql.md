---
title: Creación de un seguimiento guardado (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], example
- traces [SQL Server], creating
ms.assetid: 79dd4254-e3c6-467a-bb6f-f99e51757e99
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 35644891b2dca8359d6dc68fbddb67288d241cb4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674044"
---
# <a name="create-a-trace-transact-sql"></a><span data-ttu-id="5d66e-102">Crear un seguimiento (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="5d66e-102">Create a Trace (Transact-SQL)</span></span>
  <span data-ttu-id="5d66e-103">En este tema se describe el modo de utilizar procedimientos almacenados para crear un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5d66e-103">This topic describes how to use stored procedures to create a trace.</span></span>  
  
### <a name="to-create-a-trace"></a><span data-ttu-id="5d66e-104">Para crear un seguimiento</span><span class="sxs-lookup"><span data-stu-id="5d66e-104">To create a trace</span></span>  
  
1.  <span data-ttu-id="5d66e-105">Ejecute **sp_trace_create** con los parámetros necesarios para crear un seguimiento nuevo.</span><span class="sxs-lookup"><span data-stu-id="5d66e-105">Execute **sp_trace_create** with the required parameters to create a new trace.</span></span> <span data-ttu-id="5d66e-106">El nuevo seguimiento estará en estado de detención (el*estado* es **0**).</span><span class="sxs-lookup"><span data-stu-id="5d66e-106">The new trace will be in a stopped state (*status* is **0**).</span></span>  
  
2.  <span data-ttu-id="5d66e-107">Ejecute **sp_trace_setevent** con los parámetros necesarios para seleccionar los eventos y las columnas de las que va a realizar un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5d66e-107">Execute **sp_trace_setevent** with the required parameters to select the events and columns to trace.</span></span>  
  
3.  <span data-ttu-id="5d66e-108">Opcionalmente, ejecute **sp_trace_setfilter** para establecer un filtro o una combinación de filtros.</span><span class="sxs-lookup"><span data-stu-id="5d66e-108">Optionally, execute **sp_trace_setfilter** to set any or a combination of filters.</span></span>  
  
     <span data-ttu-id="5d66e-109">**sp_trace_setevent** y **sp_trace_setfilter** solo se pueden ejecutar en seguimientos existentes que estén detenidos.</span><span class="sxs-lookup"><span data-stu-id="5d66e-109">**sp_trace_setevent** and **sp_trace_setfilter** can be executed only on existing traces that are stopped.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="5d66e-110">A diferencia de los procedimientos almacenados normales, los parámetros de todos los procedimientos almacenados de SQL Server Profiler (<strong>sp_trace_*xx*</strong>) tienen establecimiento inflexible de tipos y no admiten la conversión de tipos de datos automática.</span><span class="sxs-lookup"><span data-stu-id="5d66e-110">Unlike regular stored procedures, parameters of all SQL Server Profiler stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="5d66e-111">Si no se llama a estos parámetros con los tipos de datos de parámetros de entrada correctos, según se especifica en la descripción del argumento, el procedimiento almacenado devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="5d66e-111">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d66e-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d66e-112">Example</span></span>  
 <span data-ttu-id="5d66e-113">En el ejemplo de código siguiente se muestra la forma de crear un seguimiento con [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d66e-113">The following code demonstrates creating a trace using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5d66e-114">Se divide en tres secciones: crear el seguimiento, rellenar el archivo de seguimiento y detener el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5d66e-114">It is in three sections: creating the trace, populating the trace file, and stopping the trace.</span></span> <span data-ttu-id="5d66e-115">Personalice el seguimiento agregando los eventos que desee seguir.</span><span class="sxs-lookup"><span data-stu-id="5d66e-115">Customize the trace by adding the events that you want to trace.</span></span> <span data-ttu-id="5d66e-116">Para obtener la lista de eventos y columnas, vea [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5d66e-116">For the list of events and columns, see [sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql).</span></span>  
  
 <span data-ttu-id="5d66e-117">En el código siguiente se crea un seguimiento, se agregan los eventos al seguimiento y, a continuación, se inicia el seguimiento:</span><span class="sxs-lookup"><span data-stu-id="5d66e-117">The following code creates a trace, adds events to the trace, and then starts the trace:</span></span>  
  
```  
DECLARE @RC int, @TraceID int, @on BIT  
EXEC @rc = sp_trace_create @TraceID output, 0, N'C:\SampleTrace'  
  
-- Select the return code to see if the trace creation was successful.  
SELECT RC = @RC, TraceID = @TraceID  
  
-- Set the events and data columns you need to capture.  
SELECT @on = 1  
  
-- 10 is RPC:Completed event. 1 is TextData column.   
EXEC sp_trace_setevent @TraceID, 10, 1, @on   
-- 13 is SQL:BatchStarting, 11 is LoginName  
EXEC sp_trace_setevent @TraceID, 13, 11, @on   
-- 13 is SQL:BatchStarting, 14 is StartTime  
EXEC sp_trace_setevent @TraceID, 13, 14, @on   
-- 12 is SQL:BatchCompleted, 15 is EndTime  
EXEC sp_trace_setevent @TraceID, 12, 15, @on   
-- 13 is SQL:BatchStarting, 1 is TextData  
EXEC sp_trace_setevent @TraceID, 13, 1, @on   
  
-- Set any filter. Not provided in this example  
--EXEC sp_trace_setfilter 1, 10, 0, 6, N'%Profiler%'  
  
-- Start Trace (status 1 = start)  
EXEC @RC = sp_trace_setstatus @TraceID, 1  
GO  
  
```  
  
## <a name="example"></a><span data-ttu-id="5d66e-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d66e-118">Example</span></span>  
 <span data-ttu-id="5d66e-119">Ahora que se ha creado el seguimiento y se ha iniciado, ejecute el código siguiente para rellenarlo con actividad.</span><span class="sxs-lookup"><span data-stu-id="5d66e-119">Now that the trace has been created and started, execute the following code to populate the trace with activity.</span></span>  
  
```  
SELECT * FROM master.sys.databases  
GO  
SELECT * FROM ::fn_trace_getinfo(default)  
GO  
  
```  
  
## <a name="example"></a><span data-ttu-id="5d66e-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d66e-120">Example</span></span>  
 <span data-ttu-id="5d66e-121">Se puede detener el seguimiento y reiniciar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="5d66e-121">The trace can be stopped and restarted at any time.</span></span> <span data-ttu-id="5d66e-122">En este ejemplo, ejecute el código siguiente para detener el seguimiento, cerrarlo y eliminar su definición.</span><span class="sxs-lookup"><span data-stu-id="5d66e-122">In this example, execute the following code to stop the trace, close the trace, and delete the trace definition.</span></span>  
  
```  
DECLARE @TraceID int  
-- Populate a variable with the trace_id of the current trace  
SELECT  @TraceID = TraceID FROM ::fn_trace_getinfo(default) WHERE VALUE = N'C:\SampleTrace.trc'  
  
-- First stop the trace.   
EXEC sp_trace_setstatus @TraceID, 0  
  
-- Close and then delete its definition from SQL Server.   
EXEC sp_trace_setstatus @TraceID, 2  
  
```  
  
## <a name="example"></a><span data-ttu-id="5d66e-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d66e-123">Example</span></span>  
 <span data-ttu-id="5d66e-124">Para examinar el archivo de seguimiento, abra el archivo SampleTrace.trc mediante [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5d66e-124">To examine the trace file, open the SampleTrace.trc file using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d66e-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d66e-125">See Also</span></span>  
 <span data-ttu-id="5d66e-126">[Procedimientos almacenados de SQL Server Profiler &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d66e-126">[SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="5d66e-127">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d66e-127">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="5d66e-128">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5d66e-128">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="5d66e-129">sp_trace_setfilter &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5d66e-129">sp_trace_setfilter &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql)  
  
  
