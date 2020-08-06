---
title: Correlacionar un seguimiento con los datos del registro de rendimiento de Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
helpviewer_keywords:
- correlating trace with log data
- logs [SQL Server], traces
- Profiler [SQL Server Profiler], correlating trace with log data
- traces [SQL Server], logs
- SQL Server Profiler, correlating trace with log data
ms.assetid: 1e4412c8-d27c-4aae-9b35-214128d1d00a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 879441c948f0ad04b971159a37ec0dcec90e3ada
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743758"
---
# <a name="correlate-a-trace-with-windows-performance-log-data"></a><span data-ttu-id="c62d5-102">Correlacionar un seguimiento con los datos del registro de rendimiento de Windows</span><span class="sxs-lookup"><span data-stu-id="c62d5-102">Correlate a Trace with Windows Performance Log Data</span></span>
  <span data-ttu-id="c62d5-103">El [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]permite abrir un registro de rendimiento de Microsoft Windows, elegir los contadores que desea correlacionar con un seguimiento y ver los contadores de rendimiento seleccionados junto con el seguimiento en la interfaz gráfica de usuario del [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c62d5-103">Using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], you can open a Microsoft Windows performance log, choose the counters you want to correlate with a trace, and display the selected performance counters alongside the trace in the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] graphical user interface.</span></span> <span data-ttu-id="c62d5-104">Al seleccionar un evento en la ventana de seguimiento, una barra vertical roja en el panel de la ventana de datos del Monitor de sistema del [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] indica los datos del registro de rendimiento que se correlacionan con el evento de seguimiento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c62d5-104">When you select an event in the trace window, a vertical red bar in the System Monitor data window pane of [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] indicates the performance log data that correlates with the selected trace event.</span></span>  
  
 <span data-ttu-id="c62d5-105">Para correlacionar un seguimiento con contadores de rendimiento, abra un archivo o una tabla de seguimiento que contenga las columnas de datos **StartTime** y **EndTime** y luego haga clic en **Importar datos de rendimiento** del menú [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]Archivo**de**.</span><span class="sxs-lookup"><span data-stu-id="c62d5-105">To correlate a trace with performance counters, open a trace file or table that contains the **StartTime** and **EndTime** data columns, and then click **Import Performance Data** on the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] **File** menu.</span></span> <span data-ttu-id="c62d5-106">Puede abrir un registro de rendimiento y seleccionar los objetos y contadores del Monitor de sistema que desea correlacionar con el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c62d5-106">You can then open a performance log, and select the System Monitor objects and counters that you want to correlate with the trace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c62d5-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c62d5-107">See Also</span></span>  
 [<span data-ttu-id="c62d5-108">Establecer correlaciones de un seguimiento con datos del registro de rendimiento de Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="c62d5-108">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](correlate-a-trace-with-windows-performance-log-data.md)  
  
  
