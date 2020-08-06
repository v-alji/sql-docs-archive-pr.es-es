---
title: Ejecutar trabajos de mantenimiento de replicación (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server replication]
ms.assetid: 0dc485a0-5a50-41eb-a29d-f2b2fb920174
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9dc27c65e96a9f956ffa6d3edf9c72ed52f721a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748082"
---
# <a name="run-replication-maintenance-jobs-sql-server-management-studio"></a><span data-ttu-id="4899e-102">Ejecutar trabajos de mantenimiento de replicación (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="4899e-102">Run Replication Maintenance Jobs (SQL Server Management Studio)</span></span>
  <span data-ttu-id="4899e-103">La replicación utiliza los siguientes trabajos de mantenimiento:</span><span class="sxs-lookup"><span data-stu-id="4899e-103">Replication uses the following maintenance jobs:</span></span>  
  
-   <span data-ttu-id="4899e-104">**Reinicializar suscripciones con errores de validación de datos**</span><span class="sxs-lookup"><span data-stu-id="4899e-104">**Reinitialize subscriptions having data validation failures**</span></span>
-   <span data-ttu-id="4899e-105">**Limpieza de historial del agente: distribución**</span><span class="sxs-lookup"><span data-stu-id="4899e-105">**Agent history clean up: distribution**</span></span>
-   <span data-ttu-id="4899e-106">**Actualizador de supervisión de replicación para distribución.**</span><span class="sxs-lookup"><span data-stu-id="4899e-106">**Replication monitoring refresher for distribution.**</span></span>
-   <span data-ttu-id="4899e-107">**Comprobación de agentes de replicación**</span><span class="sxs-lookup"><span data-stu-id="4899e-107">**Replication agents checkup**</span></span>
-   <span data-ttu-id="4899e-108">**Limpieza de la distribución: distribución**</span><span class="sxs-lookup"><span data-stu-id="4899e-108">**Distribution clean up: distribution**</span></span>
-   <span data-ttu-id="4899e-109">**Limpieza de suscripciones expiradas**</span><span class="sxs-lookup"><span data-stu-id="4899e-109">**Expired subscription clean up**</span></span>  
  
 <span data-ttu-id="4899e-110">Inicie y detenga estos trabajos en la carpeta **Trabajos** en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] y en la pestaña **Agentes** del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="4899e-110">Start and stop these jobs from the **Jobs** folder in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] and from the **Agents** tab in Replication Monitor.</span></span> <span data-ttu-id="4899e-111">Para información sobre cómo iniciar el Monitor de replicación, vea [Iniciar el Monitor de replicación](../monitor/start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="4899e-111">For information about starting Replication Monitor, see [Start the Replication Monitor](../monitor/start-the-replication-monitor.md).</span></span> <span data-ttu-id="4899e-112">Vea y modifique las propiedades de cada trabajo en el cuadro de diálogo **Propiedades del trabajo: \<Job>** , que está disponible en la misma carpeta y pestaña.</span><span class="sxs-lookup"><span data-stu-id="4899e-112">View and modify properties for each job in the **Job Properties - \<Job>** dialog box, which is available from the same folder and tab.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="4899e-113">Para iniciar o detener un mantenimiento de replicación en Management Studio</span><span class="sxs-lookup"><span data-stu-id="4899e-113">To start or stop a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="4899e-114">Conéctese al distribuidor en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="4899e-114">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="4899e-115">Expanda la carpeta **Agente SQL Server** y a continuación la carpeta **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="4899e-115">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="4899e-116">Haga clic con el botón secundario en un trabajo y, a continuación, haga clic en **Iniciar el trabajo** o **Detener el trabajo**.</span><span class="sxs-lookup"><span data-stu-id="4899e-116">Right-click a job, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-start-or-stop-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="4899e-117">Para iniciar o detener un mantenimiento de replicación en el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="4899e-117">To start or stop a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="4899e-118">Expanda un grupo de publicador en el Monitor de replicación y, a continuación, seleccione un publicador.</span><span class="sxs-lookup"><span data-stu-id="4899e-118">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="4899e-119">Haga clic en la pestaña **Agentes** .</span><span class="sxs-lookup"><span data-stu-id="4899e-119">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="4899e-120">Haga clic con el botón secundario en la cuadrícula y, a continuación, haga clic en **Iniciar el trabajo** o **Detener el trabajo**.</span><span class="sxs-lookup"><span data-stu-id="4899e-120">Right-click a job in the grid, and then click **Start Job** or **Stop Job**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-management-studio"></a><span data-ttu-id="4899e-121">Para ver y modificar las propiedades de un mantenimiento de replicación en Management Studio</span><span class="sxs-lookup"><span data-stu-id="4899e-121">To view and modify properties for a replication maintenance job in Management Studio</span></span>  
  
1.  <span data-ttu-id="4899e-122">Conéctese al distribuidor en [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]y expanda el nodo de servidor.</span><span class="sxs-lookup"><span data-stu-id="4899e-122">Connect to the Distributor in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="4899e-123">Expanda la carpeta **Agente SQL Server** y a continuación la carpeta **Trabajos** .</span><span class="sxs-lookup"><span data-stu-id="4899e-123">Expand the **SQL Server Agent** folder, and then expand the **Jobs** folder.</span></span>  
  
3.  <span data-ttu-id="4899e-124">Haga clic con el botón derecho en un trabajo y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4899e-124">Right-click a job, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="4899e-125">En el cuadro de diálogo **Propiedades del trabajo: \<Job>** , realice las modificaciones necesarias y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4899e-125">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
### <a name="to-view-and-modify-properties-for-a-replication-maintenance-job-in-replication-monitor"></a><span data-ttu-id="4899e-126">Para ver y modificar las propiedades de un mantenimiento de replicación en el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="4899e-126">To view and modify properties for a replication maintenance job in Replication Monitor</span></span>  
  
1.  <span data-ttu-id="4899e-127">Expanda un grupo de publicador en el Monitor de replicación y, a continuación, seleccione un publicador.</span><span class="sxs-lookup"><span data-stu-id="4899e-127">Expand a Publisher group in Replication Monitor, and then select a Publisher.</span></span>  
  
2.  <span data-ttu-id="4899e-128">Haga clic en la pestaña **Agentes** .</span><span class="sxs-lookup"><span data-stu-id="4899e-128">Click the **Agents** tab.</span></span>  
  
3.  <span data-ttu-id="4899e-129">Haga clic con el botón secundario en un trabajo en la cuadrícula y , a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4899e-129">Right-click a job in the grid, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="4899e-130">En el cuadro de diálogo **Propiedades del trabajo: \<Job>** , realice las modificaciones necesarias y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4899e-130">In the **Job Properties - \<Job>** dialog box, modify any properties if necessary, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4899e-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4899e-131">See Also</span></span>  
 <span data-ttu-id="4899e-132">[Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="4899e-132">[Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](../agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="4899e-133">[Visualización de información y realización de tareas mediante el Monitor de replicación](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="4899e-133">[View Information and Perform Tasks using Replication Monitor](../monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="4899e-134">Administración del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="4899e-134">Replication Agent Administration</span></span>](../agents/replication-agent-administration.md)  
  
  
