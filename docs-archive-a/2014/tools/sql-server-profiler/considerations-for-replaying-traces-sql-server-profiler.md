---
title: Consideraciones para reproducir seguimientos (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], replaying
- replaying traces
ms.assetid: 73fa339f-b71a-4be4-97ca-d4ae84c8b90b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0c2f030a0191596e40ef1ee9e2b0b2d4da34c773
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743759"
---
# <a name="considerations-for-replaying-traces-sql-server-profiler"></a><span data-ttu-id="ba04e-102">Consideraciones para reproducir seguimientos (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="ba04e-102">Considerations for Replaying Traces (SQL Server Profiler)</span></span>
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="ba04e-103">no puede reproducir los siguientes tipos de seguimientos:</span><span class="sxs-lookup"><span data-stu-id="ba04e-103">cannot replay the following kinds of traces:</span></span>  
  
-   <span data-ttu-id="ba04e-104">Seguimientos que contengan actividad de replicación transaccional y otra actividad del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="ba04e-104">Traces that contain transactional replication and other transaction log activity.</span></span> <span data-ttu-id="ba04e-105">Estos eventos se omiten.</span><span class="sxs-lookup"><span data-stu-id="ba04e-105">These events are skipped.</span></span> <span data-ttu-id="ba04e-106">Otros tipos de replicación no marcan el registro de transacciones, por lo que esto no los afecta.</span><span class="sxs-lookup"><span data-stu-id="ba04e-106">Other types of replication do not mark the transaction log so they are not affected.</span></span>  
  
-   <span data-ttu-id="ba04e-107">Seguimientos que contengan operaciones que incluyan identificadores únicos globales (GUID).</span><span class="sxs-lookup"><span data-stu-id="ba04e-107">Traces that contain operations that involve globally unique identifiers (GUID).</span></span> <span data-ttu-id="ba04e-108">Estos eventos se omiten.</span><span class="sxs-lookup"><span data-stu-id="ba04e-108">These events will be skipped.</span></span>  
  
-   <span data-ttu-id="ba04e-109">Seguimientos que contengan operaciones en las columnas **text**, **ntext**e **image** para los que se haya usado la utilidad **bcp** , las instrucciones BULK INSERT, READTEXT, WRITETEXT y UPDATETEXT y operaciones de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ba04e-109">Traces that contain operations on **text**, **ntext**, and **image** columns involving the **bcp** utility, the BULK INSERT, READTEXT, WRITETEXT, and UPDATETEXT statements, and full-text operations.</span></span> <span data-ttu-id="ba04e-110">Estos eventos se omiten.</span><span class="sxs-lookup"><span data-stu-id="ba04e-110">These events are skipped.</span></span>  
  
-   <span data-ttu-id="ba04e-111">Seguimientos que contienen enlaces de sesión: procedimientos almacenados del sistema **sp_getbindtoken** y **sp_bindsession** .</span><span class="sxs-lookup"><span data-stu-id="ba04e-111">Traces that contain session binding: **sp_getbindtoken** and **sp_bindsession** system stored procedures.</span></span> <span data-ttu-id="ba04e-112">Estos eventos se omiten.</span><span class="sxs-lookup"><span data-stu-id="ba04e-112">These events are skipped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba04e-113">Si no usa la plantilla de reproducción preconfigurada (**TSQL_Replay**), y no captura todos los datos necesarios, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] no reproducirá el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ba04e-113">If you do not use the preconfigured replay template (**TSQL_Replay**), and do not capture all required data, [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] does not replay the trace.</span></span> <span data-ttu-id="ba04e-114">Para más información, consulte [Replay Requirements](replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba04e-114">For more information, see [Replay Requirements](replay-requirements.md).</span></span>  
  
 <span data-ttu-id="ba04e-115">Para obtener información acerca de los permisos necesarios para reproducir un seguimiento, vea [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="ba04e-115">For information about what permissions are required to replay a trace, see [Permissions Required to Run SQL Server Profiler](sql-server-profiler.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba04e-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba04e-116">See Also</span></span>  
 <span data-ttu-id="ba04e-117">[bcp (utilidad)](../bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ba04e-117">[bcp Utility](../bcp-utility.md) </span></span>  
 <span data-ttu-id="ba04e-118">[Referencia de las clase de eventos de SQL Server](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ba04e-118">[SQL Server Event Class Reference](../../relational-databases/event-classes/sql-server-event-class-reference.md) </span></span>  
 <span data-ttu-id="ba04e-119">[sp_getbindtoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba04e-119">[sp_getbindtoken &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-getbindtoken-transact-sql) </span></span>  
 <span data-ttu-id="ba04e-120">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba04e-120">[sp_bindsession &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-bindsession-transact-sql) </span></span>  
 <span data-ttu-id="ba04e-121">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba04e-121">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="ba04e-122">[READTEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/readtext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba04e-122">[READTEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/readtext-transact-sql) </span></span>  
 <span data-ttu-id="ba04e-123">[WRITETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/writetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba04e-123">[WRITETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/writetext-transact-sql) </span></span>  
 [<span data-ttu-id="ba04e-124">UPDATETEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ba04e-124">UPDATETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/updatetext-transact-sql)  
  
  
