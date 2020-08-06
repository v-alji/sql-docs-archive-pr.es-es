---
title: Actualizar un clúster de conmutación por error de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- upgrading failover clusters
- clusters [SQL Server], upgrading
- failover clustering [SQL Server], upgrading
ms.assetid: daac41fe-7d0b-4f14-84c2-62952ad8cbfa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ca08e83c362e714f234a60ee358df3bcb03ade93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672553"
---
# <a name="upgrade-a-sql-server-failover-cluster"></a><span data-ttu-id="f2ad9-102">Actualizar un clúster de conmutación por error de SQL Server</span><span class="sxs-lookup"><span data-stu-id="f2ad9-102">Upgrade a SQL Server Failover Cluster</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="f2ad9-103">admite la actualización de [!INCLUDE[ssDE](../../../includes/ssde-md.md)] y [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] desde los clústeres de conmutación por error de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] y [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] por separado en todos los nodos de clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="f2ad9-103">supports upgrade of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)], and [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] failover clusters separately on all failover cluster nodes.</span></span>  
  
 <span data-ttu-id="f2ad9-104">Los detalles de compatibilidad son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="f2ad9-104">Support details are as follows:</span></span>  
  
-   <span data-ttu-id="f2ad9-105">La actualización se puede realizar tanto a través de la interfaz de usuario como desde el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="f2ad9-105">Upgrade is supported both through the user interface and from the command prompt.</span></span> <span data-ttu-id="f2ad9-106">Para más información, vea [Actualizar una instancia de clúster de conmutación por error de SQL Server &#40;programa de instalación&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) e [Instalar SQL Server 2014 desde el símbolo del sistema](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="f2ad9-106">For more information, see [Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) and [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
-   <span data-ttu-id="f2ad9-107">Actualizar desde [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] : puede ejecutar la actualización desde el símbolo del sistema en cada nodo de clúster de conmutación por error o mediante la interfaz de usuario del programa de instalación para actualizar cada nodo de clúster.</span><span class="sxs-lookup"><span data-stu-id="f2ad9-107">Upgrading from [!INCLUDE[ssKilimanjaro](../../../includes/sskilimanjaro-md.md)] - You can run upgrade from the command prompt on each failover cluster node, or by using the Setup UI to upgrade each cluster node.</span></span> <span data-ttu-id="f2ad9-108">Si la instancia que se va a actualizar no dispone de las características de replicación y búsqueda de texto completo, éstas se instalarán automáticamente sin posibilidad de omitirlas.</span><span class="sxs-lookup"><span data-stu-id="f2ad9-108">If Full-text search and Replication features do not exist on the instance being upgraded, they will be installed automatically with no option to omit them.</span></span>  
  
-   <span data-ttu-id="f2ad9-109">Instalación de los Service Pack: debe aplicar los Service Pack y las revisiones de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a los clústeres de conmutación por error de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] por separado en todos los nodos.</span><span class="sxs-lookup"><span data-stu-id="f2ad9-109">Service pack installation - you must apply [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service packs and patches to [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] failover clusters separately on all nodes.</span></span>  
  
-   <span data-ttu-id="f2ad9-110">Los siguientes escenarios no se admiten:</span><span class="sxs-lookup"><span data-stu-id="f2ad9-110">The following scenarios are not supported:</span></span>  
  
    -   <span data-ttu-id="f2ad9-111">No puede realizar la migración desde una instancia independiente de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a un clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="f2ad9-111">You cannot migrate from a stand-alone instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to a failover cluster.</span></span>  
  
    -   <span data-ttu-id="f2ad9-112">Agregar características a un clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="f2ad9-112">Add features to a failover cluster.</span></span> <span data-ttu-id="f2ad9-113">Por ejemplo, no se puede agregar [!INCLUDE[ssDE](../../../includes/ssde-md.md)] a un clúster de conmutación por error existente de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2ad9-113">For example, you cannot add the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to an existing [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]-only failover cluster.</span></span>  
  
    -   <span data-ttu-id="f2ad9-114">No puede degradar un nodo de clúster de conmutación por error a una instancia independiente.</span><span class="sxs-lookup"><span data-stu-id="f2ad9-114">You cannot downgrade a failover cluster node to a stand-alone instance.</span></span>  
  
-   <span data-ttu-id="f2ad9-115">Para obtener más información, vea [Always On Failover Cluster Instances (SQL Server)](always-on-failover-cluster-instances-sql-server.md) (Instancias de clúster de conmutación por error de Always On [SQL Server]).</span><span class="sxs-lookup"><span data-stu-id="f2ad9-115">For more information, see [AlwaysOn Failover Cluster Instances (SQL Server)](always-on-failover-cluster-instances-sql-server.md).</span></span>  
  
## <a name="upgrading-a-ssnoversion-multi-subnet-failover-cluster"></a><span data-ttu-id="f2ad9-116">Actualizar un clúster de conmutación por error de varias subredes de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ad9-116">Upgrading a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Multi-Subnet Failover Cluster</span></span>  
 <span data-ttu-id="f2ad9-117">No se puede actualizar directamente un clúster de conmutación por error que no sea de varias subredes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a un [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] clúster de conmutación por error de varias subredes.</span><span class="sxs-lookup"><span data-stu-id="f2ad9-117">You cannot directly upgrade a non-multi-subnet [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] multi-subnet failover cluster.</span></span> <span data-ttu-id="f2ad9-118">Para más información, vea [Actualizar una instancia de clúster de conmutación por error de SQL Server &#40;programa de instalación&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md).</span><span class="sxs-lookup"><span data-stu-id="f2ad9-118">For more information, see [Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ad9-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f2ad9-119">See Also</span></span>  
 <span data-ttu-id="f2ad9-120">[Actualizaciones de ediciones y versiones admitidas](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span><span class="sxs-lookup"><span data-stu-id="f2ad9-120">[Supported Version and Edition Upgrades](../../../database-engine/install-windows/supported-version-and-edition-upgrades.md) </span></span>  
 <span data-ttu-id="f2ad9-121">[Actualizar una instancia de clúster de conmutación por error de SQL Server &#40;la instalación&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) </span><span class="sxs-lookup"><span data-stu-id="f2ad9-121">[Upgrade a SQL Server Failover Cluster Instance &#40;Setup&#41;](upgrade-a-sql-server-failover-cluster-instance-setup.md) </span></span>  
 [<span data-ttu-id="f2ad9-122">Instalar SQL Server 2014 desde el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="f2ad9-122">Install SQL Server 2014 from the Command Prompt</span></span>](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md)  
  
  
