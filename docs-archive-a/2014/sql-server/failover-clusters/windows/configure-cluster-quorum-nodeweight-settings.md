---
title: Configurar los valores de NodeWeight de cuórum de clúster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: cb3fd9a6-39a2-4e9c-9157-619bf3db9951
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e469d5fc0fc030304a7cf2f1bdd894eb578aa056
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672566"
---
# <a name="configure-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="82b11-102">Configurar los valores de NodeWeight de quórum de clúster</span><span class="sxs-lookup"><span data-stu-id="82b11-102">Configure Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="82b11-103">En este tema se describe cómo configurar los valores de NodeWeight para un nodo miembro en un clúster de clústeres de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="82b11-103">This topic describes how to configure NodeWeight settings for a member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="82b11-104">La configuración de NodeWeight durante el voto de quórum para admitir los escenarios de recuperación de desastres y de múltiples subredes para las instancias de clúster de conmutación por error de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82b11-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="82b11-105">**Antes de empezar:**  [Requisitos previos](#Prerequisites), [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="82b11-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="82b11-106">**Para ver la configuración de NodeWeight de quórum con:** [Usar PowerShell](#PowerShellProcedure), [Usar Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="82b11-106">**To view quorum NodeWeight settings using:** [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
-   [<span data-ttu-id="82b11-107">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="82b11-107">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="82b11-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="82b11-108">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="82b11-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="82b11-109">Prerequisites</span></span>  
 <span data-ttu-id="82b11-110">Esta característica solo se admite en [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="82b11-110">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="82b11-111">Para usar la configuración de NodeWeight, se debe aplicar la siguiente revisión a todos los servidores del clúster de WSFC:</span><span class="sxs-lookup"><span data-stu-id="82b11-111">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="82b11-112">[KB2494036](https://support.microsoft.com/kb/2494036): hay disponible una revisión para permitir configurar un nodo de clúster que no tiene votos de quórum en [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] y en [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82b11-112">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="82b11-113">Si esta revisión no está instalada, los ejemplos de este tema devolverán valores vacíos o NULL para NodeWeight.</span><span class="sxs-lookup"><span data-stu-id="82b11-113">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="82b11-114">Seguridad</span><span class="sxs-lookup"><span data-stu-id="82b11-114">Security</span></span>  
 <span data-ttu-id="82b11-115">El usuario debe ser una cuenta de dominio que sea miembro del grupo Administradores en cada nodo del clúster de WSFC.</span><span class="sxs-lookup"><span data-stu-id="82b11-115">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="82b11-116">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="82b11-116">Using Powershell</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="82b11-117">Para configurar las opciones de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="82b11-117">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="82b11-118">Inicie Windows PowerShell con derechos elevados mediante **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="82b11-118">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="82b11-119">Importe el módulo `FailoverClusters` para habilitar los commandlets de clúster.</span><span class="sxs-lookup"><span data-stu-id="82b11-119">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="82b11-120">Use el objeto `Get-ClusterNode` para establecer la propiedad `NodeWeight` para cada nodo del clúster.</span><span class="sxs-lookup"><span data-stu-id="82b11-120">Use the `Get-ClusterNode` object to set the `NodeWeight` property for each node in the cluster.</span></span>  
  
4.  <span data-ttu-id="82b11-121">Enviar las propiedades de nodo de clúster en un formato legible.</span><span class="sxs-lookup"><span data-stu-id="82b11-121">Output the cluster node properties in a readable format.</span></span>  
  
 <span data-ttu-id="82b11-122">En el ejemplo siguiente se cambia la configuración de NodeWeight para quitar el voto de quórum del nodo "AlwaysOnSrv1" y, después, se envía la configuración para todos los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="82b11-122">The following example changes the NodeWeight setting to remove the quorum vote for the "AlwaysOnSrv1" node, and then outputs the settings for all nodes in the cluster.</span></span>
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv1"  
(Get-ClusterNode $node).NodeWeight = 0  
  
$cluster = (Get-ClusterNode $node).Cluster  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="82b11-123">Usar Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="82b11-123">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82b11-124">La utilidad cluster.exe se ha desusado en la versión de [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82b11-124">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="82b11-125">Use PowerShell con clústeres de conmutación por error para el desarrollo futuro.</span><span class="sxs-lookup"><span data-stu-id="82b11-125">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="82b11-126">La utilidad cluster.exe se quitará en la siguiente versión de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="82b11-126">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="82b11-127">Para obtener más información, vea [Asignar comandos de Cluster.exe a cmdlets de Windows PowerShell para clústeres de conmutación por error](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="82b11-127">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
### <a name="to-configure-nodeweight-settings"></a><span data-ttu-id="82b11-128">Para configurar las opciones de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="82b11-128">To configure NodeWeight settings</span></span>
  
1.  <span data-ttu-id="82b11-129">Inicie un símbolo del sistema con privilegios elevados mediante **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="82b11-129">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="82b11-130">Use **cluster.exe** para establecer los valores de `NodeWeight` .</span><span class="sxs-lookup"><span data-stu-id="82b11-130">Use **cluster.exe** to set `NodeWeight` values.</span></span>  

 <span data-ttu-id="82b11-131">En el ejemplo siguiente se cambia el valor de NodeWeight para quitar el voto de quórum del nodo "AlwaysOnSrv1" en el clúster "Cluster001".</span><span class="sxs-lookup"><span data-stu-id="82b11-131">The following example changes the NodeWeight value to remove the quorum vote of the "AlwaysOnSrv1" node in the "Cluster001" cluster.</span></span>  
  
```cmd
cluster.exe Cluster001 node AlwaysOnSrv1 /prop NodeWeight=0  
```  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="82b11-132">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="82b11-132">Related Content</span></span>  
  
-   <span data-ttu-id="82b11-133">[View Events and Logs for a Failover Cluster](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="82b11-133">[View Events and Logs for a Failover Cluster](https://technet.microsoft.com/library/cc772342\(WS.10\).aspx)</span></span>  
  
-   [<span data-ttu-id="82b11-134">Cmdlet de clúster de conmutación por error Get-ClusterLog</span><span class="sxs-lookup"><span data-stu-id="82b11-134">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="82b11-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82b11-135">See Also</span></span>  
 <span data-ttu-id="82b11-136">[Modos de Cuórum de WSFC y configuración de votación &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="82b11-136">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="82b11-137">[Ver la configuración de NodeWeight de Cuórum de clúster](view-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="82b11-137">[View Cluster Quorum NodeWeight Settings](view-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="82b11-138">[Cmdlets de clúster de conmutación por error en Windows PowerShell enumerados por tarea](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="82b11-138">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
