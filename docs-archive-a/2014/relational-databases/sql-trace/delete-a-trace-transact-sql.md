---
title: Eliminación de un seguimiento guardado (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], deleting
- removing traces
- deleting traces
ms.assetid: a5502814-b281-42dd-b885-5c9368025ae6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b3551cff36ef6e2c2e9cc6a4d9b7056ae44cb950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673600"
---
# <a name="delete-a-trace-transact-sql"></a><span data-ttu-id="7db6b-102">Eliminar un seguimiento (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7db6b-102">Delete a Trace (Transact-SQL)</span></span>
  <span data-ttu-id="7db6b-103">En este tema se describe el modo de utilizar procedimientos almacenados para eliminar un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7db6b-103">This topic describes how to use stored procedures to delete a trace.</span></span>  
  
 <span data-ttu-id="7db6b-104">Para obtener un ejemplo de cómo usar los procedimientos almacenados de seguimiento, vea [Crear un seguimiento &#40;Transact-SQL&#41;](create-a-trace-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="7db6b-104">For an example of using trace stored procedures, see [Create a Trace &#40;Transact-SQL&#41;](create-a-trace-transact-sql.md).</span></span>  
  
### <a name="to-delete-a-trace"></a><span data-ttu-id="7db6b-105">Para eliminar un seguimiento</span><span class="sxs-lookup"><span data-stu-id="7db6b-105">To delete a trace</span></span>  
  
1.  <span data-ttu-id="7db6b-106">Ejecute **sp_trace_setstatus** con **@status = 0** para detener el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7db6b-106">Execute **sp_trace_setstatus** by specifying **@status = 0** to stop the trace.</span></span>  
  
2.  <span data-ttu-id="7db6b-107">Ejecute **sp_trace_setstatus** con **@status = 2** para cerrar el seguimiento y eliminar su información del servidor.</span><span class="sxs-lookup"><span data-stu-id="7db6b-107">Execute **sp_trace_setstatus** by specifying **@status = 2** to close the trace and delete its information from the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7db6b-108">Para poder cerrar un seguimiento, primero debe detenerse.</span><span class="sxs-lookup"><span data-stu-id="7db6b-108">A trace must be stopped first before it can be closed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7db6b-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7db6b-109">See Also</span></span>  
 <span data-ttu-id="7db6b-110">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7db6b-110">[sp_trace_setstatus &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setstatus-transact-sql) </span></span>  
 <span data-ttu-id="7db6b-111">[Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7db6b-111">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="7db6b-112">Procedimientos almacenados de SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7db6b-112">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  