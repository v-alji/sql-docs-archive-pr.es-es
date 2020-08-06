---
title: Modificación de un seguimiento existente (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], modifying
- modifying traces
ms.assetid: 8792b43f-2510-44e3-9239-e73ad8227b89
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 55b8172ef8e6188059c484ab41f1a719e0e9f8c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663307"
---
# <a name="modify-an-existing-trace-transact-sql"></a><span data-ttu-id="67c0d-102">Modificar un seguimiento existente (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="67c0d-102">Modify an Existing Trace (Transact-SQL)</span></span>
  <span data-ttu-id="67c0d-103">En este tema se describe cómo utilizar procedimientos almacenados para modificar un seguimiento existente.</span><span class="sxs-lookup"><span data-stu-id="67c0d-103">This topic describes how to use stored procedures to modify an existing trace.</span></span>  
  
### <a name="to-modify-an-existing-trace"></a><span data-ttu-id="67c0d-104">Para modificar un seguimiento existente</span><span class="sxs-lookup"><span data-stu-id="67c0d-104">To modify an existing trace</span></span>  
  
1.  <span data-ttu-id="67c0d-105">Si el seguimiento ya se está ejecutando, ejecute **sp_trace_setstatus** especificando **@status = 0** para detener el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="67c0d-105">If the trace is already running, execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="67c0d-106">Para modificar los eventos del seguimiento, ejecute **sp_trace_setevent** , especificando los cambios a través de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="67c0d-106">To modify trace events, execute **sp_trace_setevent** by specifying the changes through the parameters.</span></span> <span data-ttu-id="67c0d-107">Los parámetros son, por este orden:</span><span class="sxs-lookup"><span data-stu-id="67c0d-107">Listed in order, the parameters are:</span></span>  
  
    -   <span data-ttu-id="67c0d-108">**@traceid**(ID. de seguimiento)</span><span class="sxs-lookup"><span data-stu-id="67c0d-108">**@traceid** (Trace ID)</span></span>  
  
    -   <span data-ttu-id="67c0d-109">**@eventid**(ID. de evento)</span><span class="sxs-lookup"><span data-stu-id="67c0d-109">**@eventid** (Event ID)</span></span>  
  
    -   <span data-ttu-id="67c0d-110">**@columnid**(ID. de columna)</span><span class="sxs-lookup"><span data-stu-id="67c0d-110">**@columnid** (Column ID)</span></span>  
  
    -   <span data-ttu-id="67c0d-111">**@on**EN</span><span class="sxs-lookup"><span data-stu-id="67c0d-111">**@on** (ON)</span></span>  
  
     <span data-ttu-id="67c0d-112">Al modificar el **@on** parámetro, tenga en cuenta su interacción con el **@columnid** parámetro:</span><span class="sxs-lookup"><span data-stu-id="67c0d-112">When you modify the **@on** parameter, keep in mind its interaction with the **@columnid** parameter:</span></span>  
  
    |<span data-ttu-id="67c0d-113">ACTIVAR</span><span class="sxs-lookup"><span data-stu-id="67c0d-113">ON</span></span>|<span data-ttu-id="67c0d-114">Identificador de columna</span><span class="sxs-lookup"><span data-stu-id="67c0d-114">Column ID</span></span>|<span data-ttu-id="67c0d-115">Resultado</span><span class="sxs-lookup"><span data-stu-id="67c0d-115">Result</span></span>|  
    |--------|---------------|------------|  
    |<span data-ttu-id="67c0d-116">ON (**1**)</span><span class="sxs-lookup"><span data-stu-id="67c0d-116">ON (**1**)</span></span>|<span data-ttu-id="67c0d-117">NULL</span><span class="sxs-lookup"><span data-stu-id="67c0d-117">NULL</span></span>|<span data-ttu-id="67c0d-118">El evento se activa, se establece en ON.</span><span class="sxs-lookup"><span data-stu-id="67c0d-118">Event is turned on.</span></span> <span data-ttu-id="67c0d-119">Se borran todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="67c0d-119">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="67c0d-120">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="67c0d-120">NOT NULL</span></span>|<span data-ttu-id="67c0d-121">La columna se activa, se establece en ON, para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="67c0d-121">Column is turned on for the specified event.</span></span>|  
    |<span data-ttu-id="67c0d-122">OFF (**0**)</span><span class="sxs-lookup"><span data-stu-id="67c0d-122">OFF (**0**)</span></span>|<span data-ttu-id="67c0d-123">NULL</span><span class="sxs-lookup"><span data-stu-id="67c0d-123">NULL</span></span>|<span data-ttu-id="67c0d-124">El evento se desactiva, se establece en OFF.</span><span class="sxs-lookup"><span data-stu-id="67c0d-124">Event is turned off.</span></span> <span data-ttu-id="67c0d-125">Se borran todas las columnas.</span><span class="sxs-lookup"><span data-stu-id="67c0d-125">All columns are cleared.</span></span>|  
    ||<span data-ttu-id="67c0d-126">NOT NULL</span><span class="sxs-lookup"><span data-stu-id="67c0d-126">NOT NULL</span></span>|<span data-ttu-id="67c0d-127">La columna se desactiva, se establece en OFF, para el evento especificado.</span><span class="sxs-lookup"><span data-stu-id="67c0d-127">Column is turned off for the specified event.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="67c0d-128">A diferencia de los procedimientos almacenados normales, los parámetros de todos los procedimientos almacenados de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] (<strong>sp_trace_*xx*</strong>) tienen establecimiento inflexible de tipos y no admiten la conversión automática de tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="67c0d-128">Unlike regular stored procedures, parameters of all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] stored procedures (<strong>sp_trace_*xx*</strong>) are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="67c0d-129">Si no se llama a estos parámetros con los tipos de datos de parámetros de entrada correctos, según se especifica en la descripción del argumento, el procedimiento almacenado devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="67c0d-129">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  

## <a name="see-also"></a><span data-ttu-id="67c0d-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67c0d-130">See Also</span></span>  
 <span data-ttu-id="67c0d-131">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67c0d-131">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="67c0d-132">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67c0d-132">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="67c0d-133">[Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="67c0d-133">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="67c0d-134">Procedimientos almacenados de SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="67c0d-134">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
