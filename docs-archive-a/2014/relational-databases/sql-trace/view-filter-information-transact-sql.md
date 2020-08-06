---
title: Ver la información del filtro (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- displaying filter information
- filters [SQL Server], viewing
- filters [SQL Server], traces
- traces [SQL Server], filters
- viewing filter information
ms.assetid: b7e52c13-8c83-47c2-8cd0-af7a49eceb5c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d94a7b4a73c264c1fb3a950aa1c9615a73db956
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752037"
---
# <a name="view-filter-information-transact-sql"></a><span data-ttu-id="2f161-102">Ver la información del filtro (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="2f161-102">View Filter Information (Transact-SQL)</span></span>
  <span data-ttu-id="2f161-103">En este tema se describe cómo utilizar las funciones integradas para ver la información del filtro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2f161-103">This topic describes how to use built-in functions to view trace filter information.</span></span>  
  
### <a name="to-view-filter-information"></a><span data-ttu-id="2f161-104">Para ver la información del filtro</span><span class="sxs-lookup"><span data-stu-id="2f161-104">To view filter information</span></span>  
  
1.  <span data-ttu-id="2f161-105">Ejecute **fn_trace_getfilterinfo** especificando el identificador del seguimiento del que se precisa información de filtro.</span><span class="sxs-lookup"><span data-stu-id="2f161-105">Execute **fn_trace_getfilterinfo** by specifying the ID of the trace about which filter information is needed.</span></span> <span data-ttu-id="2f161-106">Esta función devuelve una tabla con los filtros, las columnas a las que se aplican los filtros y los valores a los que se aplica el filtro.</span><span class="sxs-lookup"><span data-stu-id="2f161-106">This function returns a table that lists the filters, the columns on which the filters are applied, and the values on which the filter is applied.</span></span>  
  
     <span data-ttu-id="2f161-107">Llame a la función de esta manera:</span><span class="sxs-lookup"><span data-stu-id="2f161-107">Invoke the function this way:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getfilterinfo(trace_id)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2f161-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f161-108">See Also</span></span>  
 <span data-ttu-id="2f161-109">[sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f161-109">[sys.fn_trace_getfilterinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getfilterinfo-transact-sql) </span></span>  
 <span data-ttu-id="2f161-110">[Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2f161-110">[System Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql) </span></span>  
 [<span data-ttu-id="2f161-111">Procedimientos almacenados de SQL Server Profiler &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2f161-111">SQL Server Profiler Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sql-server-profiler-stored-procedures-transact-sql)  
  
  
