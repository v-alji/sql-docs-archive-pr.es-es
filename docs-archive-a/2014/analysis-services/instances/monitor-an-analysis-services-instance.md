---
title: Supervisar una instancia de Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- monitoring [Analysis Services - multidimensional data]
- multidimensional data [Analysis Services], monitoring
- monitoring performance [SQL Server], SQL Server Profiler
- performance [SQL Server], monitoring tools
ms.assetid: 2f0ab717-05f3-427e-b8cd-a8bdca374add
author: minewiskan
ms.author: owend
ms.openlocfilehash: b98037ea9f26c339cdf7aba22c37e2cfb3dfbb97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675033"
---
# <a name="monitor-an-analysis-services-instance"></a><span data-ttu-id="a311e-102">Supervisar una instancia de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a311e-102">Monitor an Analysis Services Instance</span></span>
  <span data-ttu-id="a311e-103">Puede supervisar el rendimiento de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] mediante [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] o mediante el Monitor de Rendimiento, una aplicación que se denomina a veces **PerfMon**.</span><span class="sxs-lookup"><span data-stu-id="a311e-103">You can monitor the performance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] or Performance Monitor, an application sometimes referred to as **PerfMon**.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="a311e-104">permite crear y administrar seguimientos y analizar y reproducir resultados de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a311e-104">lets you create and manage traces and analyze and replay trace results.</span></span> <span data-ttu-id="a311e-105">El Monitor de rendimiento notifica el estado del producto tal como se indiza a través de ciertos contadores, que se analizan en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="a311e-105">Performance Monitor reports on server status, as indexed through certain counters, which are discussed in the next section.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a311e-106">Para obtener más información sobre la supervisión, vea [SQL Server 2008 R2 Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539)(Guía de operaciones de SQL Server 2008 R2).</span><span class="sxs-lookup"><span data-stu-id="a311e-106">For more information about monitoring, see the [SQL Server 2008 R2 Operations Guide](https://go.microsoft.com/fwlink/?LinkID=225539).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a311e-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a311e-107">In This Section</span></span>  
 <span data-ttu-id="a311e-108">Siga estos vínculos para obtener más información sobre la supervisión.</span><span class="sxs-lookup"><span data-stu-id="a311e-108">Follow these links to learn more about monitoring.</span></span>  
  
 [<span data-ttu-id="a311e-109">Eventos de seguimiento de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a311e-109">Analysis Services Trace Events</span></span>](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events)  
  
 [<span data-ttu-id="a311e-110">Usar SQL Server Profiler para supervisar Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a311e-110">Use SQL Server Profiler to Monitor Analysis Services</span></span>](use-sql-server-profiler-to-monitor-analysis-services.md)  
  
 [<span data-ttu-id="a311e-111">Use SQL Server Extended Events &#40;XEvents&#41; para supervisar Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a311e-111">Use SQL Server Extended Events &#40;XEvents&#41; to Monitor Analysis Services</span></span>](../instances/monitor-analysis-services-with-sql-server-extended-events.md)  
  
 [<span data-ttu-id="a311e-112">Usar vistas de administración dinámica &#40;DMV&#41; para supervisar Analysis Services</span><span class="sxs-lookup"><span data-stu-id="a311e-112">Use Dynamic Management Views &#40;DMVs&#41; to Monitor Analysis Services</span></span>](use-dynamic-management-views-dmvs-to-monitor-analysis-services.md)  
  
 [<span data-ttu-id="a311e-113">Contadores de rendimiento &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="a311e-113">Performance Counters &#40;SSAS&#41;</span></span>](performance-counters-ssas.md)  
  
  
