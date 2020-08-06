---
title: 'SQL Server Profiler: límite de contadores de rendimiento | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.performancecounterlimit.f1
helpviewer_keywords:
- Performance Counters List dialog box
ms.assetid: d10140ef-36c4-449c-b365-1cff1b2524e4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 27bda135abaf9d91b078e36a69a87098a734acbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748229"
---
# <a name="sql-server-profiler---performance-counters-limit"></a><span data-ttu-id="176d5-102">Límite de contadores de rendimiento (SQL Server Profiler)</span><span class="sxs-lookup"><span data-stu-id="176d5-102">SQL Server Profiler - Performance Counters Limit</span></span>
  <span data-ttu-id="176d5-103">Utilice el cuadro de diálogo Límite de contadores de rendimiento para limitar la información de un archivo de registro de rendimiento del Monitor de sistema cuando lo correlacione con un seguimiento del [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="176d5-103">Use the Performance Counters Limit dialog box to limit the information from a System Monitor performance log file when correlating it with a [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace.</span></span> <span data-ttu-id="176d5-104">Puede utilizar este cuadro de diálogo para seleccionar los contadores que deben mostrarse y utilizarse para la correlación.</span><span class="sxs-lookup"><span data-stu-id="176d5-104">You can use this dialog box to select counters that should be displayed and used for correlation.</span></span>  
  
 <span data-ttu-id="176d5-105">El cuadro de diálogo **Límite de contadores de rendimiento** se llena con los objetos y contadores de rendimiento que contiene el archivo de registro de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="176d5-105">The **Performance Counters Limit** dialog box is populated with the performance objects and counters that the performance log file contains.</span></span>  
  
### <a name="to-select-performance-objects-and-counters-to-correlate-with-a-trace"></a><span data-ttu-id="176d5-106">Para seleccionar los objetos y contadores de rendimiento que deben correlacionarse con un seguimiento</span><span class="sxs-lookup"><span data-stu-id="176d5-106">To select performance objects and counters to correlate with a trace</span></span>  
  
1.  <span data-ttu-id="176d5-107">Expanda un objeto de rendimiento para ver los contadores que se incluyen en el archivo de registro de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="176d5-107">Expand a performance object to see which counters are included in the performance log file.</span></span>  
  
2.  <span data-ttu-id="176d5-108">Seleccione los contadores que desea correlacionar con el archivo de seguimiento del [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="176d5-108">Check the counters that you want to correlate with the [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace file.</span></span>  
  
     <span data-ttu-id="176d5-109">Si desea seleccionar todos los contadores para un objeto de rendimiento, active la casilla que se encuentra junto a dicho objeto.</span><span class="sxs-lookup"><span data-stu-id="176d5-109">If you want to select all counters for a performance object, check the box that is adjacent to the performance object.</span></span> <span data-ttu-id="176d5-110">Si selecciona el nodo superior, que indica el equipo, selecciona todos los objetos y contadores de rendimiento que contiene el archivo de registro de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="176d5-110">Checking the topmost node, which indicates the computer, selects all performance objects and counters contained in the performance log file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="176d5-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="176d5-111">See Also</span></span>  
 [<span data-ttu-id="176d5-112">Establecer correlaciones de un seguimiento con datos del registro de rendimiento de Windows &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="176d5-112">Correlate a Trace with Windows Performance Log Data &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/correlate-a-trace-with-windows-performance-log-data.md)  
  
  
