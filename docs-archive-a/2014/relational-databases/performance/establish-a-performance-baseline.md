---
title: Establecer una línea base del rendimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- database performance [SQL Server], baselines
- monitoring performance [SQL Server], baselines
- tuning databases [SQL Server], baselines
- server performance [SQL Server], baselines
- performance [SQL Server], baselines
- baseline performance [SQL Server]
- measurements for baseline statistics [SQL Server]
- monitoring server performance [SQL Server], establishing baseline
- database monitoring [SQL Server], baselines
ms.assetid: dc5aa8d6-2507-448f-ad86-4196443915fc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0cb85ae8ad370b816c6240b58aabd247c7593c16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744648"
---
# <a name="establish-a-performance-baseline"></a><span data-ttu-id="72085-102">Establecer una línea base del rendimiento</span><span class="sxs-lookup"><span data-stu-id="72085-102">Establish a Performance Baseline</span></span>
  <span data-ttu-id="72085-103">Para determinar si el sistema [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funciona de forma óptima, tome medidas del rendimiento a intervalos regulares, incluso cuando no existan problemas, para establecer una línea base del rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="72085-103">To determine whether your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system is performing optimally, take performance measurements at regular intervals over time, even when no problems occur, to establish a server performance baseline.</span></span> <span data-ttu-id="72085-104">Compare cada conjunto de medidas nuevo con las medidas tomadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="72085-104">Compare each new set of measurements with those taken earlier.</span></span>  
  
 <span data-ttu-id="72085-105">Las áreas siguientes afectan al rendimiento de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="72085-105">The following areas affect the performance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="72085-106">Recursos del sistema (hardware)</span><span class="sxs-lookup"><span data-stu-id="72085-106">System resources (hardware)</span></span>  
  
-   <span data-ttu-id="72085-107">Arquitectura de red</span><span class="sxs-lookup"><span data-stu-id="72085-107">Network architecture</span></span>  
  
-   <span data-ttu-id="72085-108">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="72085-108">The operating system</span></span>  
  
-   <span data-ttu-id="72085-109">Aplicaciones de bases de datos</span><span class="sxs-lookup"><span data-stu-id="72085-109">Database applications</span></span>  
  
-   <span data-ttu-id="72085-110">Aplicaciones cliente</span><span class="sxs-lookup"><span data-stu-id="72085-110">Client applications</span></span>  
  
 <span data-ttu-id="72085-111">Como mínimo, utilice las medidas de línea base para determinar:</span><span class="sxs-lookup"><span data-stu-id="72085-111">At a minimum, use baseline measurements to determine:</span></span>  
  
-   <span data-ttu-id="72085-112">Las horas con el máximo y el mínimo nivel de funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="72085-112">Peak and off-peak hours of operation.</span></span>  
  
-   <span data-ttu-id="72085-113">Tiempos de respuesta de comandos de procesamiento por lotes o consultas de producción.</span><span class="sxs-lookup"><span data-stu-id="72085-113">Production-query or batch-command response times.</span></span>  
  
-   <span data-ttu-id="72085-114">Tiempos de finalización de operaciones de copias de seguridad y restauración de bases de datos</span><span class="sxs-lookup"><span data-stu-id="72085-114">Database backup and restore completion times.</span></span>  
  
 <span data-ttu-id="72085-115">Cuando haya establecido la línea base para el rendimiento del servidor, compare las estadísticas de la línea base con el rendimiento actual del servidor.</span><span class="sxs-lookup"><span data-stu-id="72085-115">After you establish a server performance baseline, compare the baseline statistics to current server performance.</span></span> <span data-ttu-id="72085-116">Unas cifras demasiado elevadas o demasiado reducidas con respecto a la línea base indican que hay que realizar una investigación más detallada.</span><span class="sxs-lookup"><span data-stu-id="72085-116">Numbers far above or far below your baseline are candidates for further investigation.</span></span> <span data-ttu-id="72085-117">Pueden indicar áreas que hay que optimizar o volver a configurar.</span><span class="sxs-lookup"><span data-stu-id="72085-117">They may indicate areas in need of tuning or reconfiguration.</span></span> <span data-ttu-id="72085-118">Por ejemplo, si aumenta el tiempo necesario para ejecutar un conjunto de consultas, examine las consultas para determinar si puede volver a escribirlas o si es necesario agregar estadísticas de columnas u otros índices.</span><span class="sxs-lookup"><span data-stu-id="72085-118">For example, if the amount of time to execute a set of queries increases, examine the queries to determine if they can be rewritten, or if column statistics or new indexes must be added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72085-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72085-119">See Also</span></span>  
 [<span data-ttu-id="72085-120">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="72085-120">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
