---
title: Configurar las directivas de mantenimiento (utilidad de SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 030aac3b-8901-4c41-91ed-aba96420276c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c5ee466dd2d5bac2ea64364bfc78de8f2f5bea10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669687"
---
# <a name="configure-health-policies-sql-server-utility"></a><span data-ttu-id="8437c-102">Configurar las directivas de mantenimiento (utilidad de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8437c-102">Configure Health Policies (SQL Server Utility)</span></span>
  <span data-ttu-id="8437c-103">Use el panel de Utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para ver los parámetros de recursos de la utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para instancias administradas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y aplicaciones de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="8437c-103">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility dashboard in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility resource parameters for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and data-tier applications.</span></span> <span data-ttu-id="8437c-104">Para obtener más información, vea [Características y tareas de la utilidad de SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="8437c-104">For more information, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="8437c-105">Para ver los resultados de la directiva de mantenimiento de la Utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , conéctese a un punto de control de la utilidad desde [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8437c-105">To view [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility health policy results, connect to a utility control point from [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="8437c-106">Para obtener más información, vea [Utilizar el explorador de Utilidad para administrar la utilidad de SQL Server](use-utility-explorer-to-manage-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="8437c-106">For more information, see [Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8437c-107">Las directivas de mantenimiento de la utilidad se pueden configurar para las aplicaciones de capa de datos y las instancias administradas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8437c-107">Utility health policies can be configured for data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8437c-108">Las directivas de mantenimiento se pueden definir globalmente para todas las aplicaciones de capa de datos y las instancias administradas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la Utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , o bien se pueden definir individualmente para cada aplicación de capa de datos y para cada instancia administrada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la Utilidad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8437c-108">Health policies can be defined globally for all data-tier applications and managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, or they can be defined individually for each data-tier application and for each managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
## <a name="monitoring-policies-for-data-tier-applications"></a><span data-ttu-id="8437c-109">Directivas de supervisión para aplicaciones de capa de datos</span><span class="sxs-lookup"><span data-stu-id="8437c-109">Monitoring Policies for Data-tier Applications</span></span>  
 <span data-ttu-id="8437c-110">Las directivas de sobreutilización e infrautilización para las aplicaciones de capa de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] son como sigue:</span><span class="sxs-lookup"><span data-stu-id="8437c-110">Overutilization and underutilization policies for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data-tier applications are as follows:</span></span>  
  
-   <span data-ttu-id="8437c-111">Uso del procesador en la aplicaciones de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="8437c-111">Data-tier application processor utilization.</span></span>  
  
-   <span data-ttu-id="8437c-112">Espacio de archivo de aplicación de capa de datos para los archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="8437c-112">Data-tier application file space for database files.</span></span>  
  
-   <span data-ttu-id="8437c-113">Espacio de archivo de aplicación de capa de datos para los volúmenes de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="8437c-113">Data-tier application file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="8437c-114">Uso del procesador del sistema informático.</span><span class="sxs-lookup"><span data-stu-id="8437c-114">Computer processor utilization.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8437c-115">El uso de los volúmenes de almacenamiento y del procesador son directivas de solo lectura para las aplicaciones de capa de datos.</span><span class="sxs-lookup"><span data-stu-id="8437c-115">Storage volume and processor utilization are read-only policies for data-tier applications.</span></span>  
  
 <span data-ttu-id="8437c-116">Para obtener más información sobre la visualización o modificación de directivas de supervisión globales para las aplicaciones de capa de datos, vea [Administración de utilidades &#40;Utilidad de SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="8437c-116">For more information about viewing or changing global monitoring policies for data-tier applications, see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="8437c-117">Para obtener más información sobre la visualización o modificación de directivas de supervisión para aplicaciones individuales de capa de datos, vea [Detalles de la aplicación de capa de datos implementada &#40;Utilidad de SQL Server&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="8437c-117">For more information about viewing or changing monitoring policies for individual data-tier applications, see [Deployed Data-tier Application Details &#40;SQL Server Utility&#41;](../../database-engine/deployed-data-tier-application-details-sql-server-utility.md).</span></span>  
  
## <a name="monitoring-policies-for-managed-instances-of-sql-server"></a><span data-ttu-id="8437c-118">Directivas de supervisión para instancias administradas de SQL Server</span><span class="sxs-lookup"><span data-stu-id="8437c-118">Monitoring Policies for Managed Instances of SQL Server</span></span>  
 <span data-ttu-id="8437c-119">Las directivas de sobreutilización e infrautilización para las instancias administradas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] son como sigue:</span><span class="sxs-lookup"><span data-stu-id="8437c-119">Overutilization and underutilization policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are as follows:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8437c-120">.</span><span class="sxs-lookup"><span data-stu-id="8437c-120">instance processor utilization.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8437c-121">para archivos de base de datos.</span><span class="sxs-lookup"><span data-stu-id="8437c-121">instance file space for database files.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8437c-122">para volúmenes de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="8437c-122">instance file space for storage volumes.</span></span>  
  
-   <span data-ttu-id="8437c-123">Uso del procesador del sistema informático.</span><span class="sxs-lookup"><span data-stu-id="8437c-123">Computer processor utilization.</span></span>  
  
 <span data-ttu-id="8437c-124">Para obtener más información sobre la visualización o modificación de directivas de supervisión globales para las instancias administradas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Administración de utilidades &#40;Utilidad de SQL Server&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="8437c-124">For more information about viewing or changing global monitoring policies for managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Utility Administration &#40;SQL Server Utility&#41;](../../database-engine/utility-administration-sql-server-utility.md).</span></span>  
  
 <span data-ttu-id="8437c-125">Para obtener más información sobre la visualización o modificación de directivas de supervisión para instancias individuales administradas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vea [Detalles de las instancias administradas &#40;Utilidad de SQL Server&#41;](../../database-engine/managed-instance-details-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="8437c-125">For more information about viewing or changing monitoring policies for individual managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Managed Instance Details &#40;SQL Server Utility&#41;](../../database-engine/managed-instance-details-sql-server-utility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8437c-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8437c-126">See Also</span></span>  
 <span data-ttu-id="8437c-127">[Características y tareas de la utilidad de SQL Server](sql-server-utility-features-and-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="8437c-127">[SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md) </span></span>  
 [<span data-ttu-id="8437c-128">Reducir el ruido en las directivas de uso de la CPU &#40;Utilidad de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8437c-128">Reduce Noise in CPU Utilization Policies &#40;SQL Server Utility&#41;</span></span>](reduce-noise-in-cpu-utilization-policies-sql-server-utility.md)  
  
  
