---
title: Aislamiento de problemas de rendimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- isolating performance problems [SQL Server]
- monitoring performance [SQL Server], isolating problems
- database monitoring [SQL Server], isolating problems
- tuning databases [SQL Server], isolating problems
- monitoring server performance [SQL Server], isolating problems
- database performance [SQL Server], isolating problems
- server performance [SQL Server], isolating problems
ms.assetid: 2eb425cb-9166-4027-ae08-c8fc2d236f44
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b42d780a8174ab57d00de72e8b00ef7af0abc17e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746262"
---
# <a name="isolate-performance-problems"></a><span data-ttu-id="402ce-102">Aislar problemas de rendimiento</span><span class="sxs-lookup"><span data-stu-id="402ce-102">Isolate Performance Problems</span></span>
  <span data-ttu-id="402ce-103">Suele ser más efectivo usar conjuntamente varias herramientas de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o Microsoft Windows para aislar los problemas de rendimiento de una base de datos que usar solo una herramienta cada vez.</span><span class="sxs-lookup"><span data-stu-id="402ce-103">It is often more effective to use several [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or Microsoft Windows tools together to isolate database performance problems than to use one tool at a time.</span></span> <span data-ttu-id="402ce-104">Por ejemplo, la característica Plan de ejecución gráfico, denominada también plan de presentación, le ayuda a reconocer los interbloqueos en una sola consulta.</span><span class="sxs-lookup"><span data-stu-id="402ce-104">For example, the graphical Execution Plan feature, also called Showplan, helps you quickly recognize deadlocks in a single query.</span></span> <span data-ttu-id="402ce-105">Sin embargo, puede reconocer más fácilmente otros problemas de rendimiento si utiliza conjuntamente las características de supervisión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y Windows.</span><span class="sxs-lookup"><span data-stu-id="402ce-105">However, you can recognize some other performance problems more easily if you use the monitoring features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows together.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="402ce-106">puede usarse para supervisar y solucionar problemas de Transact-SQL o problemas relacionados con las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="402ce-106">can be used to monitor and troubleshoot Transact-SQL and application-related problems.</span></span> <span data-ttu-id="402ce-107">Asimismo, puede utilizar el Monitor de sistema para supervisar problemas relativos al hardware y otros problemas relacionados con el sistema.</span><span class="sxs-lookup"><span data-stu-id="402ce-107">System Monitor can be used to monitor hardware and other system-related problems.</span></span>  
  
 <span data-ttu-id="402ce-108">Puede supervisar las siguientes áreas para solucionar problemas:</span><span class="sxs-lookup"><span data-stu-id="402ce-108">You can monitor the following areas to troubleshoot problems:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="402ce-109">o lotes de instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] enviadas por aplicaciones de usuarios.</span><span class="sxs-lookup"><span data-stu-id="402ce-109">stored procedures or batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements submitted by user applications.</span></span>  
  
-   <span data-ttu-id="402ce-110">Actividad de los usuarios, como bloqueos o interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="402ce-110">User activity, such as blocking locks or deadlocks.</span></span>  
  
-   <span data-ttu-id="402ce-111">Actividad del hardware, como el uso de los discos.</span><span class="sxs-lookup"><span data-stu-id="402ce-111">Hardware activity, such as disk usage.</span></span>  
  
 <span data-ttu-id="402ce-112">Algunos problemas posibles son:</span><span class="sxs-lookup"><span data-stu-id="402ce-112">Problems can include:</span></span>  
  
-   <span data-ttu-id="402ce-113">Errores de programación de aplicaciones debidos a instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] escritas incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="402ce-113">Application development errors involving incorrectly written [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span>  
  
-   <span data-ttu-id="402ce-114">Errores de hardware, como los relativos a discos o a la red.</span><span class="sxs-lookup"><span data-stu-id="402ce-114">Hardware errors, such as disk- or network-related errors.</span></span>  
  
-   <span data-ttu-id="402ce-115">Bloqueo excesivo debido a un diseño incorrecto de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="402ce-115">Excessive blocking due to an incorrectly designed database.</span></span>  
  
## <a name="tools-for-common-performance-problems"></a><span data-ttu-id="402ce-116">Herramientas para solucionar problemas comunes de rendimiento</span><span class="sxs-lookup"><span data-stu-id="402ce-116">Tools for Common Performance Problems</span></span>  
 <span data-ttu-id="402ce-117">Igual de importante es la correcta selección del problema de rendimiento que desea que cada herramienta supervise u optimice.</span><span class="sxs-lookup"><span data-stu-id="402ce-117">Equally important is careful selection of the performance problem that you want each tool to monitor or tune.</span></span> <span data-ttu-id="402ce-118">La herramienta y la utilidad dependen del tipo de problema de rendimiento que desee resolver.</span><span class="sxs-lookup"><span data-stu-id="402ce-118">The tool and the utility depend on the type of performance problem you want to resolve.</span></span>  
  
 <span data-ttu-id="402ce-119">En los temas siguientes se describen diversas herramientas de supervisión y optimización y los problemas que ayudan a solucionar.</span><span class="sxs-lookup"><span data-stu-id="402ce-119">The following topics describe a variety of monitoring and tuning tools and the problems they uncover.</span></span>  
  
 [<span data-ttu-id="402ce-120">Identificar los cuellos de botella</span><span class="sxs-lookup"><span data-stu-id="402ce-120">Identify Bottlenecks</span></span>](identify-bottlenecks.md)  
  
 [<span data-ttu-id="402ce-121">Supervisar el uso de la memoria</span><span class="sxs-lookup"><span data-stu-id="402ce-121">Monitor Memory Usage</span></span>](../performance-monitor/monitor-memory-usage.md)  
  
  
