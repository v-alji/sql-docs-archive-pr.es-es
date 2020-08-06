---
title: Detener un seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- traces [SQL Server], stopping
- stopping traces
ms.assetid: 47c4f33d-63e0-4444-bec8-4c1c91f8e25c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 501ea4a4838f8e2ea42fc475c486466d48020a4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747328"
---
# <a name="stop-a-trace-sql-server-profiler"></a><span data-ttu-id="43b01-102">Detener un seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="43b01-102">Stop a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="43b01-103">En este tema se describe cómo detener un seguimiento que se está ejecutando mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43b01-103">This topic describes how to stop a trace that is running by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
 <span data-ttu-id="43b01-104">Al detener un seguimiento, se interrumpe la captura de datos.</span><span class="sxs-lookup"><span data-stu-id="43b01-104">Stopping a trace stops data from being captured.</span></span> <span data-ttu-id="43b01-105">Cuando se detiene un seguimiento, no se puede volver a iniciar sin perder los datos capturados anteriormente, a menos que los datos se hayan capturado en un archivo de seguimiento o en una tabla de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="43b01-105">After a trace is stopped, it cannot be restarted without losing previously captured data, unless the data has been captured to a trace file or trace table.</span></span> <span data-ttu-id="43b01-106">También puede guardar los datos recopilados en una tabla o archivo después de detener el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="43b01-106">You can also save the collected data to a table or file after stopping a trace.</span></span> <span data-ttu-id="43b01-107">Todas las propiedades del seguimiento que se habían seleccionado anteriormente se mantienen cuando se detiene.</span><span class="sxs-lookup"><span data-stu-id="43b01-107">All trace properties that were previously selected are preserved when a trace is stopped.</span></span> <span data-ttu-id="43b01-108">Cuando un seguimiento se detiene, puede cambiar el nombre, los eventos, las columnas y los filtros.</span><span class="sxs-lookup"><span data-stu-id="43b01-108">When a trace is stopped, you can change the name, events, columns, and filters.</span></span>  
  
### <a name="to-stop-a-trace"></a><span data-ttu-id="43b01-109">Para detener un seguimiento</span><span class="sxs-lookup"><span data-stu-id="43b01-109">To stop a trace</span></span>  
  
1.  <span data-ttu-id="43b01-110">Seleccione el seguimiento que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="43b01-110">Select a trace that is running.</span></span>  
  
2.  <span data-ttu-id="43b01-111">En el menú **Archivo** , haga clic en **Detener seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="43b01-111">On the **File** menu, click **Stop Trace**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b01-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43b01-112">See Also</span></span>  
 [<span data-ttu-id="43b01-113">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="43b01-113">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
