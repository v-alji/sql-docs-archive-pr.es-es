---
title: Desinstalar SQL Server 2014 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: e6255f8e-a25e-4b3d-9310-c5da2f9c9333
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e72f153c28a1ccd827150eb3dddc0b52321518a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672425"
---
# <a name="uninstall-sql-server-2014"></a><span data-ttu-id="fdff2-102">Desinstalar SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="fdff2-102">Uninstall SQL Server 2014</span></span>
  <span data-ttu-id="fdff2-103">Consulte los temas siguientes para desinstalar totalmente una instancia existente de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] y preparar el sistema para poder volver a instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdff2-103">Follow the topics below to uninstall an existing instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] completely, and prepare the system so that you can reinstall [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdff2-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="fdff2-104">In This Section</span></span>  
 [<span data-ttu-id="fdff2-105">Desinstalar una instancia existente de SQL Server &#40;programa de instalación&#41;</span><span class="sxs-lookup"><span data-stu-id="fdff2-105">Uninstall an Existing Instance of SQL Server &#40;Setup&#41;</span></span>](uninstall-an-existing-instance-of-sql-server-setup.md)  
 <span data-ttu-id="fdff2-106">En este tema se describe cómo desinstalar manualmente una instancia independiente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdff2-106">This topic describes how to manually uninstall a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="fdff2-107">Desinstalar PowerPivot para SharePoint</span><span class="sxs-lookup"><span data-stu-id="fdff2-107">Uninstall PowerPivot for SharePoint</span></span>](uninstall-power-pivot-for-sharepoint.md)  
 <span data-ttu-id="fdff2-108">En este tema se describe cómo desinstalar manualmente PowerPivot para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fdff2-108">This topic describes how to manually uninstall PowerPivot for SharePoint.</span></span>  
  
 [<span data-ttu-id="fdff2-109">Desinstalar Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fdff2-109">Uninstall Reporting Services</span></span>](uninstall-reporting-services.md)  
 <span data-ttu-id="fdff2-110">En este tema se describe cómo desinstalar los servidores de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para el modo de SharePoint y los servidores en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="fdff2-110">This topic describes how to uninstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] servers for both SharePoint mode and Native mode servers.</span></span>  
  
 [<span data-ttu-id="fdff2-111">Desinstalar y quitar Master Data Services</span><span class="sxs-lookup"><span data-stu-id="fdff2-111">Uninstall and Remove Master Data Services</span></span>](uninstall-and-remove-master-data-services.md)  
 <span data-ttu-id="fdff2-112">En este tema se describe el proceso para desinstalar y quitar [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] del equipo local.</span><span class="sxs-lookup"><span data-stu-id="fdff2-112">This topic describes the process of uninstalling and removing [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] from the local computer.</span></span>  
  
 [<span data-ttu-id="fdff2-113">Quitar objetos del servidor de calidad de datos</span><span class="sxs-lookup"><span data-stu-id="fdff2-113">Remove Data Quality Server Objects</span></span>](remove-data-quality-server-objects.md)  
 <span data-ttu-id="fdff2-114">En este tema se describe cómo quitar manualmente los objetos de [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] después de desinstalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o simplemente el componente de [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] en [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="fdff2-114">This topic describes how to manually remove the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] objects after uninstalling either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or just the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] component in [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] (DQS).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fdff2-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="fdff2-115">Related Sections</span></span>  
  
-   [<span data-ttu-id="fdff2-116">Quitar una instancia de clúster de conmutación por error de SQL Server &#40;programa de instalación&#41;</span><span class="sxs-lookup"><span data-stu-id="fdff2-116">Remove a SQL Server Failover Cluster Instance &#40;Setup&#41;</span></span>](../failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md)  
  
-   [<span data-ttu-id="fdff2-117">Agregar o quitar nodos en un clúster de conmutación por error de SQL Server &#40;programa de instalación&#41;</span><span class="sxs-lookup"><span data-stu-id="fdff2-117">Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;</span></span>](../failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
-   [<span data-ttu-id="fdff2-118">Anular una instalación de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="fdff2-118">Drop a SQL Server 2014 Installation</span></span>](../../database-engine/install-windows/repair-a-failed-sql-server-installation.md)  
  
## <a name="see-also"></a><span data-ttu-id="fdff2-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fdff2-119">See Also</span></span>  
 <span data-ttu-id="fdff2-120">[Planear una instalación de SQL Server](planning-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="fdff2-120">[Planning a SQL Server Installation](planning-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="fdff2-121">[Instalación de SQL Server 2014](../../database-engine/install-windows/install-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fdff2-121">[Install SQL Server 2014](../../database-engine/install-windows/install-sql-server.md) </span></span>  
 [<span data-ttu-id="fdff2-122">Actualizar a SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="fdff2-122">Upgrade to SQL Server 2014</span></span>](../../database-engine/install-windows/upgrade-sql-server.md)  
  
  
