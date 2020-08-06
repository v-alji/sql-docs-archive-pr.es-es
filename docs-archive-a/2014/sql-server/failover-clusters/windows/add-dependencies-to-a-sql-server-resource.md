---
title: Agregar dependencias a un recurso de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- resource dependencies [SQL Server]
- failover clustering [SQL Server], dependencies
- clusters [SQL Server], dependencies
- dependencies [SQL Server], clustering
ms.assetid: 25dbb751-139b-4c8e-ac62-3ec23110611f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8610d3dc847d0d2b8dd6f570aa543d766adf68c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672571"
---
# <a name="add-dependencies-to-a-sql-server-resource"></a><span data-ttu-id="509de-102">Agregar dependencias a un recurso de SQL Server</span><span class="sxs-lookup"><span data-stu-id="509de-102">Add Dependencies to a SQL Server Resource</span></span>
  <span data-ttu-id="509de-103">En este tema se describe cómo se agregan dependencias a un recurso de instancia de clúster de conmutación por error (FCI) AlwaysOn con el complemento Administrador de clústeres de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="509de-103">This topic describes how to add dependencies to an AlwaysOn Failover Cluster Instance (FCI) resource by using the Failover Cluster Manager snap-in.</span></span> <span data-ttu-id="509de-104">El complemento Administrador de clústeres de conmutación por error es la aplicación de administración de clústeres del servicio de clústeres de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="509de-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Server Failover Clustering (WSFC) service.</span></span>  
  
-   <span data-ttu-id="509de-105">**Antes de empezar:**  [Limitaciones y restricciones](#Restrictions), [Requisitos previos](#Prerequisites)</span><span class="sxs-lookup"><span data-stu-id="509de-105">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Prerequisites](#Prerequisites)</span></span>  
  
-   <span data-ttu-id="509de-106">**Para agregar una dependencia a un recurso de SQL Server, mediante:** [Administrador de clústeres de conmutación por error de Windows](#WinClusManager)</span><span class="sxs-lookup"><span data-stu-id="509de-106">**To add a dependency to a SQL Server resource, using:** [Windows Failover Cluster Manager](#WinClusManager)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="509de-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="509de-107">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="509de-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="509de-108">Limitations and Restrictions</span></span>  
 <span data-ttu-id="509de-109">Tenga en cuenta que si agrega otros recursos al grupo de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , dichos recursos deben tener siempre sus propios recursos de nombre de red SQL únicos y sus propios recursos de dirección IP de SQL.</span><span class="sxs-lookup"><span data-stu-id="509de-109">It is important to note that if you add any other resources to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] group, those resources must always have their own unique SQL network name resources and their own SQL IP address resources.</span></span>  
  
 <span data-ttu-id="509de-110">No utilice los recursos de nombre de red SQL ni los recursos de dirección IP SQL existentes en ningún otro entorno que no sea [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="509de-110">Do not use the existing SQL network name resources and SQL IP address resources for anything other than [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="509de-111">Si los recursos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se comparten con otros recursos pueden producirse los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="509de-111">If [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resources are shared with other resources, the following problems may occur:</span></span>  
  
-   <span data-ttu-id="509de-112">Interrupciones inesperadas.</span><span class="sxs-lookup"><span data-stu-id="509de-112">Outages that are not expected may occur.</span></span>  
  
-   <span data-ttu-id="509de-113">Es posible que la instalación de los Service Pack no se haya realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="509de-113">Service pack installations may not be successful.</span></span>  
  
-   <span data-ttu-id="509de-114">Puede que el programa de instalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no se ejecute correctamente.</span><span class="sxs-lookup"><span data-stu-id="509de-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup program may not be successful.</span></span> <span data-ttu-id="509de-115">Si ocurre este problema, no puede instalar instancias adicionales de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ni realizar un mantenimiento rutinario del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="509de-115">If this problem occurs, you cannot install additional instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or perform routine maintenance.</span></span>  
  
 <span data-ttu-id="509de-116">Tenga en cuenta también estos problemas adicionales:</span><span class="sxs-lookup"><span data-stu-id="509de-116">Consider these additional issues:</span></span>  
  
-   <span data-ttu-id="509de-117">FTP con replicación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: para las instancias de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que utilicen FTP con replicación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], el servicio FTP debe usar uno de los mismos discos físicos configurados para que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilice el servicio FTP.</span><span class="sxs-lookup"><span data-stu-id="509de-117">FTP with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replication: For instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that use FTP with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replication, your FTP service must use one of the same physical disks as the installation of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is set up to use the FTP service.</span></span>  
  
-   <span data-ttu-id="509de-118">Dependencias de recursos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]: si agrega un recurso a un grupo de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y tiene una dependencia en el recurso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para asegurarse de que esté disponible [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], [!INCLUDE[msCoName](../../../includes/msconame-md.md)] recomienda agregar una dependencia en el recurso del Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="509de-118">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource dependencies: If you add a resource to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] group and you have a dependency on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource to make sure that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is available, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] recommends that you add a dependency on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent resource.</span></span> <span data-ttu-id="509de-119">No agregue una dependencia en el recurso [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="509de-119">Do not add a dependency on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource.</span></span> <span data-ttu-id="509de-120">Para asegurarse de que el equipo en el que se ejecuta [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] permanece altamente disponible, configure el recurso del Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de modo que no afecte al grupo de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] si se produce un error en el recurso del Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="509de-120">To make sure that the computer that is running [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] remains highly available, configure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent resource so that it does not affect the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] group if the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent resource fails.</span></span>  
  
-   <span data-ttu-id="509de-121">Recursos compartidos de archivos e impresoras: cuando instale recursos de archivo o recursos de clústeres de impresora, no los coloque en los mismos recursos de disco físico que el equipo en el que se ejecuta [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="509de-121">File shares and printer resources: When you install File Share resources or Printer cluster resources, they should not be put on the same physical disk resources as the computer that is running [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="509de-122">Si los coloca en los mismos recursos de disco físico, puede experimentar una degradación del rendimiento y la pérdida de servicio en el equipo donde se ejecuta [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="509de-122">If they are put on the same physical disk resources, you may experience performance degradation and loss of service to the computer that is running [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="509de-123">Consideraciones de MS DTC: después de instalar el sistema operativo y configurar la FCI, debe configurar el coordinador de transacciones distribuidas de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] (MS DTC) para que funcione en un clúster mediante el complemento Administrador de clústeres de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="509de-123">MS DTC considerations: After you install the operating system and configure your FCI, you must configure [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) to work in a cluster by using the Failover Cluster Manager snap-in.</span></span> <span data-ttu-id="509de-124">Si no logra crear el clúster de MS DTC, no se bloqueará el programa de instalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , pero la funcionalidad de la aplicación [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] puede verse afectada si MS DTC no se configura correctamente.</span><span class="sxs-lookup"><span data-stu-id="509de-124">Failure to cluster MS DTC will not block [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup, but [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] application functionality may be affected if MS DTC is not properly configured.</span></span>  
  
     <span data-ttu-id="509de-125">Si instala MS DTC en el grupo de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y tiene otros recursos que dependen de MS DTC, MS DTC no estará disponible si este grupo se encuentra en modo sin conexión ni durante una conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="509de-125">If you install MS DTC in your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] group and you have other resources that are dependent on MS DTC, MS DTC will not be available if this group is offline or during a failover.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="509de-126">recomienda que, si es posible, sitúe MS DTC en su propio grupo con su propio recurso de disco físico.</span><span class="sxs-lookup"><span data-stu-id="509de-126">recommends that you put MS DTC in its own group with its own physical disk resource, if it is possible.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="509de-127">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="509de-127">Prerequisites</span></span>  
 <span data-ttu-id="509de-128">Si instala [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en un grupo de recursos de WSFC con varias unidades de disco y decide colocar los datos en una de las unidades, el recurso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se configurará para que solo dependa de dicha unidad.</span><span class="sxs-lookup"><span data-stu-id="509de-128">If you install [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] into a WSFC resource group with multiple disk drives and choose to place your data on one of the drives, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource will be set to be dependent only on that drive.</span></span> <span data-ttu-id="509de-129">Para colocar datos o registros en otro disco, primero debe agregar una dependencia al recurso [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para el disco adicional.</span><span class="sxs-lookup"><span data-stu-id="509de-129">To put data or logs on another disk, you must first add a dependency to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource for the additional disk.</span></span>  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WinClusManager"></a> <span data-ttu-id="509de-130">Usar el complemento Administrador de clústeres de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="509de-130">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="509de-131">**Para agregar una dependencia a un recurso de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="509de-131">**To add a dependency to a SQL Server resource**</span></span>  
  
-   <span data-ttu-id="509de-132">Abra el complemento Administrador de clústeres de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="509de-132">Open the Failover Cluster Manager snap-in.</span></span>  
  
-   <span data-ttu-id="509de-133">Busque el grupo que contiene el recurso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aplicable que desearía convertir en dependiente.</span><span class="sxs-lookup"><span data-stu-id="509de-133">Locate the group that contains the applicable [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource that you would like to make dependent.</span></span>  
  
-   <span data-ttu-id="509de-134">Si el recurso del disco ya está en este grupo, vaya al paso 4.</span><span class="sxs-lookup"><span data-stu-id="509de-134">If the resource for the disk is already in this group, go to step 4.</span></span> <span data-ttu-id="509de-135">De lo contrario, busque el grupo que contiene el disco.</span><span class="sxs-lookup"><span data-stu-id="509de-135">Otherwise, locate the group that contains the disk.</span></span> <span data-ttu-id="509de-136">Si ese grupo y el grupo que contiene [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] no son propiedad del mismo nodo, mueva el grupo que contiene el recurso del disco al nodo propietario del grupo de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="509de-136">If that group and the group that contains [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are not owned by the same node, move the group containing the resource for the disk to the node that owns the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] group.</span></span>  
  
-   <span data-ttu-id="509de-137">Seleccione el recurso de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , abra el cuadro de diálogo **Propiedades** y utilice la pestaña **Dependencias** para agregar el disco al conjunto de dependencias de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="509de-137">Select the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resource, open the **Properties** dialog box, and use the **Dependencies** tab to add the disk to the set of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dependencies.</span></span>  
  
  