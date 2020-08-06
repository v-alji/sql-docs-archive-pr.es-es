---
title: Usar objetos de rendimiento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, monitoring
- SQL Server Agent service, monitoring
- SQL Server Agent service, performance objects
- SQL Server Agent, performance objects
- performance objects [SQL Server Agent]
- monitoring [SQL Server], SQL Server Agent
- monitoring [SQL Server Agent]
- performance counters [SQL Server], SQL Server Agent
- counters [SQL Server], SQL Server Agent
ms.assetid: 830b843a-6b2a-4620-a51b-98358e9fc54b
author: stevestein
ms.author: sstein
ms.openlocfilehash: d7c1fe3f4a7d9a5fec901f84d8e913e49a4dbd1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674525"
---
# <a name="use-performance-objects"></a><span data-ttu-id="9c2f1-102">Usar objetos de rendimiento</span><span class="sxs-lookup"><span data-stu-id="9c2f1-102">Use Performance Objects</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9c2f1-103">El Agente incluye objetos y contadores de rendimiento para supervisar el rendimiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="9c2f1-103">Agent includes performance objects and counters to monitor how the service is performing.</span></span> <span data-ttu-id="9c2f1-104">Estos objetos de rendimiento le permiten utilizar el Monitor de rendimiento, una herramienta de Windows, para identificar las actividades que realiza el servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9c2f1-104">These performance objects allow you to use Performance Monitor, a Windows tool, to identify what the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is doing in the background.</span></span> <span data-ttu-id="9c2f1-105">Por ejemplo, puede identificar cuántos trabajos activos ejecuta actualmente el servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para identificar los trabajos bloqueados.</span><span class="sxs-lookup"><span data-stu-id="9c2f1-105">For example, you can identify how many active jobs the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service is currently running to identify those jobs that are blocked.</span></span>  
  
 <span data-ttu-id="9c2f1-106">Hay objetos y contadores de rendimiento del servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para cada instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9c2f1-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects and counters exist for each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is installed on a computer.</span></span> <span data-ttu-id="9c2f1-107">La denominación que adoptan los objetos de rendimiento depende de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que representa cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="9c2f1-107">Performance objects are named according to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that each object represents.</span></span>  
  
 <span data-ttu-id="9c2f1-108">La tabla siguiente muestra cómo se denominan los objetos de rendimiento del servicio Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="9c2f1-108">The following table shows how the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service performance objects are named:</span></span>  
  
|<span data-ttu-id="9c2f1-109">Tipo de instancia</span><span class="sxs-lookup"><span data-stu-id="9c2f1-109">Instance type</span></span>|<span data-ttu-id="9c2f1-110">Nombre del objeto</span><span class="sxs-lookup"><span data-stu-id="9c2f1-110">Object name</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="9c2f1-111">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9c2f1-111">Default</span></span>|<span data-ttu-id="9c2f1-112">**SQLAgent:** *objeto*:*contador*</span><span class="sxs-lookup"><span data-stu-id="9c2f1-112">**SQLAgent:** *object*:*counter*</span></span>|  
|<span data-ttu-id="9c2f1-113">con nombre</span><span class="sxs-lookup"><span data-stu-id="9c2f1-113">Named</span></span>|<span data-ttu-id="9c2f1-114">**SQLAgent$**</span><span class="sxs-lookup"><span data-stu-id="9c2f1-114">**SQLAgent$**</span></span><br /> <span data-ttu-id="9c2f1-115">***instance_name* :** *objeto*:*contador*</span><span class="sxs-lookup"><span data-stu-id="9c2f1-115">***instance_name* :** *object*:*counter*</span></span>|  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9c2f1-116">incluye los siguientes objetos de rendimiento para el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9c2f1-116">includes the following performance objects for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
|<span data-ttu-id="9c2f1-117">Nombre del objeto</span><span class="sxs-lookup"><span data-stu-id="9c2f1-117">Object name</span></span>|<span data-ttu-id="9c2f1-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c2f1-118">Description</span></span>|  
|-----------------|-----------------|  
|[<span data-ttu-id="9c2f1-119">SQLAgent:Jobs</span><span class="sxs-lookup"><span data-stu-id="9c2f1-119">SQLAgent:Jobs</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobs-object.md)|<span data-ttu-id="9c2f1-120">Información de rendimiento acerca de trabajos que se han iniciado, tasas de éxito y estado actual</span><span class="sxs-lookup"><span data-stu-id="9c2f1-120">Performance information about jobs that have been started, success rates, and current status</span></span>|  
|[<span data-ttu-id="9c2f1-121">SQLAgent:JobSteps</span><span class="sxs-lookup"><span data-stu-id="9c2f1-121">SQLAgent:JobSteps</span></span>](../../relational-databases/performance-monitor/sql-server-agent-jobsteps-object.md)|<span data-ttu-id="9c2f1-122">Información de estado acerca de pasos de trabajos</span><span class="sxs-lookup"><span data-stu-id="9c2f1-122">Status information about job steps</span></span>|  
|[<span data-ttu-id="9c2f1-123">SQLAgent:Alerts</span><span class="sxs-lookup"><span data-stu-id="9c2f1-123">SQLAgent:Alerts</span></span>](../../relational-databases/performance-monitor/sql-server-agent-alerts-object.md)|<span data-ttu-id="9c2f1-124">Información acerca del número de alertas y notificaciones</span><span class="sxs-lookup"><span data-stu-id="9c2f1-124">Information about number of alerts and notifications</span></span>|  
|[<span data-ttu-id="9c2f1-125">SQLAgent:Statistics</span><span class="sxs-lookup"><span data-stu-id="9c2f1-125">SQLAgent:Statistics</span></span>](../../relational-databases/performance-monitor/sql-server-agent-statistics-object.md)|<span data-ttu-id="9c2f1-126">Información general de rendimiento</span><span class="sxs-lookup"><span data-stu-id="9c2f1-126">General performance information</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c2f1-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c2f1-127">See Also</span></span>  
 <span data-ttu-id="9c2f1-128">[Supervisión y optimización del rendimiento](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span><span class="sxs-lookup"><span data-stu-id="9c2f1-128">[Monitor and Tune for Performance](../../relational-databases/performance/monitor-and-tune-for-performance.md) </span></span>  
 [<span data-ttu-id="9c2f1-129">Iniciar el Monitor de sistema &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="9c2f1-129">Start System Monitor &#40;Windows&#41;</span></span>](../../relational-databases/performance/start-system-monitor-windows.md)  
  
  
