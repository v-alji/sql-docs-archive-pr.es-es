---
title: Ver un seguimiento guardado (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], viewing
- displaying traces
- viewing traces
ms.assetid: 3a95a816-aa89-4d5f-858c-968a9cb3ee87
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f8b67760d575b651b089a6936adc945d74a1c62b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752041"
---
# <a name="view-a-saved-trace-transact-sql"></a><span data-ttu-id="8b9e3-102">Ver un seguimiento guardado (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="8b9e3-102">View a Saved Trace (Transact-SQL)</span></span>
  <span data-ttu-id="8b9e3-103">En este tema se describe cómo utilizar las funciones integradas para ver un seguimiento guardado.</span><span class="sxs-lookup"><span data-stu-id="8b9e3-103">This topic describes how to use built-in functions to view a saved trace.</span></span>  
  
### <a name="to-view-a-specific-trace"></a><span data-ttu-id="8b9e3-104">Para ver un seguimiento específico</span><span class="sxs-lookup"><span data-stu-id="8b9e3-104">To view a specific trace</span></span>  
  
1.  <span data-ttu-id="8b9e3-105">Ejecute **fn_trace_getinfo** especificando el identificador del seguimiento del que se precisa información.</span><span class="sxs-lookup"><span data-stu-id="8b9e3-105">Execute **fn_trace_getinfo** by specifying the ID of the trace about which information is needed.</span></span> <span data-ttu-id="8b9e3-106">Esta función devuelve una tabla con el seguimiento, la propiedad del seguimiento e información acerca de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8b9e3-106">This function returns a table that lists the trace, trace property, and information about the property.</span></span>  
  
     <span data-ttu-id="8b9e3-107">Llame a la función de esta manera:</span><span class="sxs-lookup"><span data-stu-id="8b9e3-107">Invoke the function this way:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(trace_id)  
    ```  
  
### <a name="to-view-all-existing-traces"></a><span data-ttu-id="8b9e3-108">Para ver todas los seguimientos existentes</span><span class="sxs-lookup"><span data-stu-id="8b9e3-108">To view all existing traces</span></span>  
  
1.  <span data-ttu-id="8b9e3-109">Ejecute **fn_trace_getinfo** especificando `0` o `default`.</span><span class="sxs-lookup"><span data-stu-id="8b9e3-109">Execute **fn_trace_getinfo** by specifying `0` or `default`.</span></span> <span data-ttu-id="8b9e3-110">Esta función devuelve una tabla con todos los seguimiento, sus propiedades e información acerca de estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="8b9e3-110">This function returns a table that lists all the traces, their properties, and information about these properties.</span></span>  
  
     <span data-ttu-id="8b9e3-111">Invoque la función de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8b9e3-111">Invoke the function as follows:</span></span>  
  
    ```  
    SELECT *  
    FROM ::fn_trace_getinfo(default)  
    ```  
  
## <a name="net-framework-security"></a><span data-ttu-id="8b9e3-112">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8b9e3-112">.NET Framework Security</span></span>  
 <span data-ttu-id="8b9e3-113">Para ejecutar la función integrada **fn_trace_getinfo**, el usuario necesita el siguiente permiso:</span><span class="sxs-lookup"><span data-stu-id="8b9e3-113">To run the built-in function **fn_trace_getinfo**, the user needs the following permission:</span></span>  
  
 <span data-ttu-id="8b9e3-114">ALTER TRACE en el servidor.</span><span class="sxs-lookup"><span data-stu-id="8b9e3-114">ALTER TRACE on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b9e3-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b9e3-115">See Also</span></span>  
 <span data-ttu-id="8b9e3-116">[sys.fn_trace_getinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8b9e3-116">[sys.fn_trace_getinfo &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-trace-getinfo-transact-sql) </span></span>  
 [<span data-ttu-id="8b9e3-117">Ver y analizar seguimientos con SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="8b9e3-117">View and Analyze Traces with SQL Server Profiler</span></span>](../../tools/sql-server-profiler/view-and-analyze-traces-with-sql-server-profiler.md)  
  
  
