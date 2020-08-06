---
title: Ver los resultados de la directiva de mantenimiento de recursos (Utilidad de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 80cb14fb-f4c6-4be2-ba17-eb4e4cddd35f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c4ab30ad0e87782f8187370a53747be4cf5d313d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746263"
---
# <a name="view-resource-health-policy-results-sql-server-utility"></a><span data-ttu-id="b2de4-102">Ver los resultados de la directiva de mantenimiento de recursos (Utilidad de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b2de4-102">View Resource Health Policy Results (SQL Server Utility)</span></span>
  <span data-ttu-id="b2de4-103">Use el panel de Utilidad de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] para ver los parámetros de recursos de la utilidad de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para instancias administradas de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y aplicaciones de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="b2de4-103">Use the Utility dashboard in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="b2de4-104">Para obtener más información, vea [Características y tareas de la utilidad de SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="b2de4-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="view-sql-server-utility-resource-health-policy-results"></a><span data-ttu-id="b2de4-105">Ver los resultados de la directiva de mantenimiento de recursos de la Utilidad de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b2de4-105">View SQL Server Utility resource health policy results.</span></span>  
  
1.  <span data-ttu-id="b2de4-106">En [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (SSMS), haga clic en **Ver**y, a continuación, haga clic en **Explorador de Utilidad** para ver el panel de navegación del Explorador de Utilidad.</span><span class="sxs-lookup"><span data-stu-id="b2de4-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] (SSMS), click **View**, then click **Utility Explorer** to view the Utility Explorer navigation pane.</span></span> <span data-ttu-id="b2de4-107">Para ver el panel de contenido, haga clic en **Ver**y, a continuación, haga clic en **Contenido del explorador de la utilidad**.</span><span class="sxs-lookup"><span data-stu-id="b2de4-107">To view the content pane, click **View**, then click **Utility Explorer Content**.</span></span>  
  
2.  <span data-ttu-id="b2de4-108">En el panel de navegación, haga clic en ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Conectar con la utilidad**.</span><span class="sxs-lookup"><span data-stu-id="b2de4-108">In the navigation pane, click ![](../../database-engine/media/connect-to-utility.gif "Connect_to_Utility")**Connect to Utility**.</span></span> <span data-ttu-id="b2de4-109">Si no ha creado un punto de control de la utilidad (UCP) o si no ha inscrito instancias de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o aplicaciones de capa de datos en la utilidad [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , consulte [Características y tareas de la utilidad de SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="b2de4-109">If you have not created a utility control point (UCP) or if you have not enrolled instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or data-tier applications into the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
3.  <span data-ttu-id="b2de4-110">Haga clic en el nodo UCP para ver los datos de resumen para las instancias administradas de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y las aplicaciones de capa de datos (haga clic con el botón derecho para actualizar).</span><span class="sxs-lookup"><span data-stu-id="b2de4-110">Click the UCP node to view summary data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="b2de4-111">Los datos del panel se muestran en el panel de contenido.</span><span class="sxs-lookup"><span data-stu-id="b2de4-111">Dashboard data is displayed in the content pane.</span></span>  
  
4.  <span data-ttu-id="b2de4-112">Haga clic en el nodo **Instancias administradas** para ver los datos de la vista de lista para las instancias administradas de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (haga clic con el botón secundario para actualizar).</span><span class="sxs-lookup"><span data-stu-id="b2de4-112">Click the **Managed Instances** node to view list view data for managed instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (right-click to refresh).</span></span> <span data-ttu-id="b2de4-113">Los datos de la vista de lista se muestran en el panel de contenido.</span><span class="sxs-lookup"><span data-stu-id="b2de4-113">List view data is displayed in the content pane.</span></span>  
  
5.  <span data-ttu-id="b2de4-114">Haga clic en el nodo **Aplicaciones de capa de datos implementadas** para ver la vista de lista para las aplicaciones de capa de datos (haga clic con el botón derecho para actualizar).</span><span class="sxs-lookup"><span data-stu-id="b2de4-114">Click the **Deployed Data-tier Applications** node to view list view data for data-tier applications (right-click to refresh).</span></span> <span data-ttu-id="b2de4-115">Los datos de la vista de lista se muestran en el panel de contenido.</span><span class="sxs-lookup"><span data-stu-id="b2de4-115">List view data is displayed in the content pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2de4-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2de4-116">See Also</span></span>  
 <span data-ttu-id="b2de4-117">[Características y tareas de la utilidad de SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="b2de4-117">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 <span data-ttu-id="b2de4-118">[Reducir el ruido en las directivas de uso de la CPU &#40;Utilidad de SQL Server&#41;](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b2de4-118">[Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md) </span></span>  
 <span data-ttu-id="b2de4-119">[Detalles de la aplicación de capa de datos implementada &#40;Utilidad de SQL Server&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b2de4-119">[Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md) </span></span>  
 <span data-ttu-id="b2de4-120">[Detalles de las instancias administradas &#40;Utilidad de SQL Server&#41;](../../database-engine/managed-instance-details-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b2de4-120">[Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="b2de4-121">Administración de la utilidad &#40;Utilidad de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b2de4-121">Utility Administration &#40;SQL Server Utility&#41;</span></span>](../../database-engine/utility-administration-sql-server-utility.md)  
  
  
