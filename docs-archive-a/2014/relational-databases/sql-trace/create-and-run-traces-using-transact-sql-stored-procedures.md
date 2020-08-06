---
title: Creación y ejecución de seguimientos mediante procedimientos almacenados de Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 80347417-338d-4bea-8885-91fae5181cfe
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2905ce2822598502ef6337d1a083fb6fde001c2d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674045"
---
# <a name="create-and-run-traces-using-transact-sql-stored-procedures"></a><span data-ttu-id="4660c-102">Crear y ejecutar seguimientos mediante procedimientos almacenados de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4660c-102">Create and Run Traces Using Transact-SQL Stored Procedures</span></span>
  <span data-ttu-id="4660c-103">El proceso de creación de trazas con Seguimiento de SQL varía en función de si el usuario crea y ejecuta su seguimiento mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] de Microsoft o mediante procedimientos almacenados del sistema.</span><span class="sxs-lookup"><span data-stu-id="4660c-103">The process of tracing with SQL Trace varies depending on whether you create and run your trace by using Microsoft [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or by using system stored procedures.</span></span>  
  
 <span data-ttu-id="4660c-104">Como alternativa al [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], se pueden utilizar procedimientos almacenados del sistema de [!INCLUDE[tsql](../../includes/tsql-md.md)] para crear y ejecutar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="4660c-104">As an alternative to [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can use [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures to create and run traces.</span></span> <span data-ttu-id="4660c-105">El proceso de creación de trazas mediante procedimientos almacenados del sistema es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="4660c-105">The process of tracing by using system stored procedures is as follows:</span></span>  
  
1.  <span data-ttu-id="4660c-106">Cree un seguimiento mediante **sp_trace_create**.</span><span class="sxs-lookup"><span data-stu-id="4660c-106">Create a trace by using **sp_trace_create**.</span></span>  
  
2.  <span data-ttu-id="4660c-107">Agregue eventos con **sp_trace_setevent**.</span><span class="sxs-lookup"><span data-stu-id="4660c-107">Add events with **sp_trace_setevent**.</span></span>  
  
3.  <span data-ttu-id="4660c-108">(Opcional) Establezca un filtro con **sp_trace_setfilter**.</span><span class="sxs-lookup"><span data-stu-id="4660c-108">(Optional) Set a filter with **sp_trace_setfilter**.</span></span>  
  
4.  <span data-ttu-id="4660c-109">Inicie el seguimiento con **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="4660c-109">Start the trace with **sp_trace_setstatus**.</span></span>  
  
5.  <span data-ttu-id="4660c-110">Detenga el seguimiento con **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="4660c-110">Stop the trace with **sp_trace_setstatus**.</span></span>  
  
6.  <span data-ttu-id="4660c-111">Cierre el seguimiento con **sp_trace_setstatus**.</span><span class="sxs-lookup"><span data-stu-id="4660c-111">Close the trace with **sp_trace_setstatus**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4660c-112">El uso de procedimientos almacenados del sistema de [!INCLUDE[tsql](../../includes/tsql-md.md)] crea un seguimiento en el servidor, que garantiza que no se perderá ningún evento mientras haya espacio en el disco y no se produzcan errores de escritura.</span><span class="sxs-lookup"><span data-stu-id="4660c-112">Using [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures creates a server-side trace, which guarantees that no events will be lost as long as there is space on the disk and no write errors occur.</span></span> <span data-ttu-id="4660c-113">Si el disco se llena o tiene un error, la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sigue ejecutándose, pero se detiene la traza.</span><span class="sxs-lookup"><span data-stu-id="4660c-113">If the disk becomes full or the disk fails, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance continues to run, but tracing stops.</span></span> <span data-ttu-id="4660c-114">Si está establecida la opción **c2 audit mode** y hay un error de escritura, se detiene la traza y se cierra la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4660c-114">If the **c2 audit mode** is set, and there is a write failure, tracing stops and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span> <span data-ttu-id="4660c-115">Para obtener más información sobre la opción **c2 audit mode** , vea [c2 audit mode (opción de configuración del servidor)](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="4660c-115">For more information about the **c2 audit mode** setting, see [c2 audit mode Server Configuration Option](../../database-engine/configure-windows/c2-audit-mode-server-configuration-option.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4660c-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4660c-116">In This Section</span></span>  
  
|<span data-ttu-id="4660c-117">Tema</span><span class="sxs-lookup"><span data-stu-id="4660c-117">Topic</span></span>|<span data-ttu-id="4660c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="4660c-118">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4660c-119">Optimizar el seguimiento de SQL</span><span class="sxs-lookup"><span data-stu-id="4660c-119">Optimize SQL Trace</span></span>](sql-trace.md)|<span data-ttu-id="4660c-120">Contiene información acerca de cómo se pueden reducir los efectos de la traza en el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="4660c-120">Contains information about ways you can reduce the effects of tracing on system performance.</span></span>|  
|[<span data-ttu-id="4660c-121">Filtrar un seguimiento</span><span class="sxs-lookup"><span data-stu-id="4660c-121">Filter a Trace</span></span>](filter-a-trace.md)|<span data-ttu-id="4660c-122">Contiene información acerca del uso de filtros para la traza.</span><span class="sxs-lookup"><span data-stu-id="4660c-122">Contains information about using filters for tracing.</span></span>|  
|[<span data-ttu-id="4660c-123">Limitar el tamaño de la tabla y el archivo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4660c-123">Limit Trace File and Table Sizes</span></span>](limit-trace-file-and-table-sizes.md)|<span data-ttu-id="4660c-124">Contiene información acerca de cómo limitar el tamaño de los archivos y las tablas donde se escriben los datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4660c-124">Contains information about how to limit the size of files and tables where trace data is written.</span></span> <span data-ttu-id="4660c-125">Tenga en cuenta que solo el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] puede escribir información sobre el seguimiento en las tablas.</span><span class="sxs-lookup"><span data-stu-id="4660c-125">Note that only [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] can write trace information to tables.</span></span>|  
|[<span data-ttu-id="4660c-126">Programar seguimientos</span><span class="sxs-lookup"><span data-stu-id="4660c-126">Schedule Traces</span></span>](schedule-traces.md)|<span data-ttu-id="4660c-127">Contiene información acerca de cómo establecer la hora de inicio y de finalización de la traza.</span><span class="sxs-lookup"><span data-stu-id="4660c-127">Contains information about how to set the start time and the end time for tracing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4660c-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4660c-128">See Also</span></span>  
 <span data-ttu-id="4660c-129">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4660c-129">[sp_trace_create &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-create-transact-sql) </span></span>  
 <span data-ttu-id="4660c-130">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4660c-130">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 <span data-ttu-id="4660c-131">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4660c-131">[sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql) </span></span>  
 [<span data-ttu-id="4660c-132">sp_trace_setstatus &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4660c-132">sp_trace_setstatus &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql)  
  
  
