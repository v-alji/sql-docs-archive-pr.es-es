---
title: Extraer un script de un seguimiento (SQL Server Profiler) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server], traces
- extracting script from trace [SQL Server]
ms.assetid: 431126a6-ff91-4818-8763-4442152bd571
author: stevestein
ms.author: sstein
ms.openlocfilehash: f6633fafb8a39b189093044ef39694afa601af7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743741"
---
# <a name="extract-a-script-from-a-trace-sql-server-profiler"></a><span data-ttu-id="f6060-102">Extraer un script de un seguimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="f6060-102">Extract a Script from a Trace (SQL Server Profiler)</span></span>
  <span data-ttu-id="f6060-103">En este tema se describe cómo extraer eventos de [!INCLUDE[tsql](../../includes/tsql-md.md)] de una tabla o archivo de seguimiento y guardarlos como archivo de script de [!INCLUDE[tsql](../../includes/tsql-md.md)] mediante el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f6060-103">This topic describes how to extract [!INCLUDE[tsql](../../includes/tsql-md.md)] events from a trace file or table and save them as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].</span></span>  
  
### <a name="to-extract-a-transact-sql-script-from-a-trace-file-or-table"></a><span data-ttu-id="f6060-104">Para extraer un script de Transact-SQL de una tabla o archivo de seguimiento</span><span class="sxs-lookup"><span data-stu-id="f6060-104">To extract a Transact-SQL script from a trace file or table</span></span>  
  
1.  <span data-ttu-id="f6060-105">Abra la tabla o archivo de seguimiento que contiene los eventos de [!INCLUDE[tsql](../../includes/tsql-md.md)] que desea guardar en un archivo de script de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6060-105">Open a trace file or table that contains [!INCLUDE[tsql](../../includes/tsql-md.md)] events that you want to save to a [!INCLUDE[tsql](../../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="f6060-106">Para obtener más información, vea [Abrir un archivo de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) o el Asistente para la optimización del [Abrir una tabla de seguimiento &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span><span class="sxs-lookup"><span data-stu-id="f6060-106">For more information, see [Open a Trace File &#40;SQL Server Profiler&#41;](open-a-trace-file-sql-server-profiler.md) or [Open a Trace Table &#40;SQL Server Profiler&#41;](open-a-trace-table-sql-server-profiler.md).</span></span>  
  
2.  <span data-ttu-id="f6060-107">En el menú **Archivo** , seleccione **Exportar**, **Extraer eventos de SQL Server**y, luego, haga clic en **Extraer eventos de Transact-SQL**.</span><span class="sxs-lookup"><span data-stu-id="f6060-107">On the **File** menu, point to **Export**, point to **Extract SQL Server Events**, and then click **Extract Transact-SQL Events**.</span></span>  
  
3.  <span data-ttu-id="f6060-108">En el cuadro de diálogo **Guardar como** , escriba un nombre para el archivo de [!INCLUDE[tsql](../../includes/tsql-md.md)] y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f6060-108">In the **Save As** dialog box, type a name for the [!INCLUDE[tsql](../../includes/tsql-md.md)] file, and click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6060-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f6060-109">See Also</span></span>  
 [<span data-ttu-id="f6060-110">SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="f6060-110">SQL Server Profiler</span></span>](sql-server-profiler.md)  
  
  
