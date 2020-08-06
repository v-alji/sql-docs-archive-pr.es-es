---
title: Ver la configuración de NodeWeight de cuórum de clúster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: b845e73a-bb01-4de2-aac2-8ac12abebc95
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef2176d4916e8affbb9ef89c9b26499289c520ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672551"
---
# <a name="view-cluster-quorum-nodeweight-settings"></a><span data-ttu-id="4201f-102">Ver la configuración de NodeWeight de quórum de clúster</span><span class="sxs-lookup"><span data-stu-id="4201f-102">View Cluster Quorum NodeWeight Settings</span></span>
  <span data-ttu-id="4201f-103">En este tema se describe cómo ver la configuración de NodeWeight para cada nodo miembro en un clúster de clústeres de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="4201f-103">This topic describes how to view NodeWeight settings for each member node in a Windows Server Failover Clustering (WSFC) cluster.</span></span> <span data-ttu-id="4201f-104">La configuración de NodeWeight durante el voto de quórum para admitir los escenarios de recuperación de desastres y de múltiples subredes para las instancias de clúster de conmutación por error de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4201f-104">NodeWeight settings are used during quorum voting to support disaster recovery and multi-subnet scenarios for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="4201f-105">**Antes de empezar:**  [Requisitos previos](#Prerequisites), [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="4201f-105">**Before you start:**  [Prerequisites](#Prerequisites), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="4201f-106">**Para ver la configuración de NodeWeight de quórum con:** [Uso de Transact-SQL](#TsqlProcedure), [Uso de Powershell](#PowerShellProcedure), [Uso de Cluster.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="4201f-106">**To view quorum NodeWeight settings using:** [Using Transact-SQL](#TsqlProcedure), [Using Powershell](#PowerShellProcedure), [Using Cluster.exe](#CommandPromptProcedure)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4201f-107">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="4201f-107">Before You Start</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4201f-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4201f-108">Prerequisites</span></span>  
 <span data-ttu-id="4201f-109">Esta característica solo se admite en [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="4201f-109">This feature is supported only in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] or later versions.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4201f-110">Para usar la configuración de NodeWeight, se debe aplicar la siguiente revisión a todos los servidores del clúster de WSFC:</span><span class="sxs-lookup"><span data-stu-id="4201f-110">In order to use NodeWeight settings, the following hotfix must be applied to all servers in the WSFC cluster:</span></span>  
>   
>  <span data-ttu-id="4201f-111">[KB2494036](https://support.microsoft.com/kb/2494036): hay disponible una revisión para permitir configurar un nodo de clúster que no tiene votos de quórum en [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] y en [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4201f-111">[KB2494036](https://support.microsoft.com/kb/2494036): A hotfix is available to let you configure a cluster node that does not have quorum votes in [!INCLUDE[firstref_longhorn](../../../includes/firstref-longhorn-md.md)] and in [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)]</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="4201f-112">Si esta revisión no está instalada, los ejemplos de este tema devolverán valores vacíos o NULL para NodeWeight.</span><span class="sxs-lookup"><span data-stu-id="4201f-112">If this hotfix is not installed, the examples in this topic will return empty or NULL values for NodeWeight.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4201f-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4201f-113">Security</span></span>  
 <span data-ttu-id="4201f-114">El usuario debe ser una cuenta de dominio que sea miembro del grupo Administradores en cada nodo del clúster de WSFC.</span><span class="sxs-lookup"><span data-stu-id="4201f-114">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4201f-115">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4201f-115">Using Transact-SQL</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="4201f-116">Para ver la configuración de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="4201f-116">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="4201f-117">Conéctese a cualquier instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] del clúster.</span><span class="sxs-lookup"><span data-stu-id="4201f-117">Connect to any [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the cluster.</span></span>  
  
2.  <span data-ttu-id="4201f-118">Consulte la vista [sys].[dm_hadr_cluster_members].</span><span class="sxs-lookup"><span data-stu-id="4201f-118">Query the [sys].[dm_hadr_cluster_members] view.</span></span>  
  
### <a name="example-transact-sql"></a><span data-ttu-id="4201f-119">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="4201f-119">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="4201f-120">En el ejemplo siguiente se consulta una vista del sistema para devolver valores para todos los nodos del clúster de esa instancia.</span><span class="sxs-lookup"><span data-stu-id="4201f-120">The following example queries a system view to return values for all of the nodes in that instance's cluster.</span></span>  
  
```sql  
SELECT  member_name, member_state_desc, number_of_quorum_votes  
 FROM   sys.dm_hadr_cluster_members;  
```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4201f-121">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="4201f-121">Using Powershell</span></span>  
  
### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="4201f-122">Para ver la configuración de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="4201f-122">To view NodeWeight settings</span></span>
  
1.  <span data-ttu-id="4201f-123">Inicie Windows PowerShell con derechos elevados mediante **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="4201f-123">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="4201f-124">Importe el módulo `FailoverClusters` para habilitar los commandlets de clúster.</span><span class="sxs-lookup"><span data-stu-id="4201f-124">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="4201f-125">Use el objeto `Get-ClusterNode` para devolver una colección de objetos de nodo de clúster.</span><span class="sxs-lookup"><span data-stu-id="4201f-125">Use the `Get-ClusterNode` object to return a collection of cluster node objects.</span></span>  
  
4.  <span data-ttu-id="4201f-126">Enviar las propiedades de nodo de clúster en un formato legible.</span><span class="sxs-lookup"><span data-stu-id="4201f-126">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="4201f-127">Ejemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="4201f-127">Example (Powershell)</span></span>  
 <span data-ttu-id="4201f-128">En el ejemplo siguiente se envían algunas de las propiedades de nodo para el clúster denominado "Cluster001".</span><span class="sxs-lookup"><span data-stu-id="4201f-128">The following example output some of the node properties for the cluster called "Cluster001".</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$cluster = "Cluster001"  
$nodes = Get-ClusterNode -Cluster $cluster  
  
$nodes | Format-Table -Property NodeName, State, NodeWeight  
```  
  
##  <a name="using-clusterexe"></a><a name="CommandPromptProcedure"></a> <span data-ttu-id="4201f-129">Usar Cluster.exe</span><span class="sxs-lookup"><span data-stu-id="4201f-129">Using Cluster.exe</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4201f-130">La utilidad cluster.exe se ha desusado en la versión de [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4201f-130">The cluster.exe utility is deprecated in the [!INCLUDE[winserver2008r2](../../../includes/winserver2008r2-md.md)] release.</span></span>  <span data-ttu-id="4201f-131">Use PowerShell con clústeres de conmutación por error para el desarrollo futuro.</span><span class="sxs-lookup"><span data-stu-id="4201f-131">Please use PowerShell with Failover Clustering for future development.</span></span>  <span data-ttu-id="4201f-132">La utilidad cluster.exe se quitará en la siguiente versión de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4201f-132">The cluster.exe utility will be removed in the next release of Windows Server.</span></span> <span data-ttu-id="4201f-133">Para obtener más información, vea [Asignar comandos de Cluster.exe a cmdlets de Windows PowerShell para clústeres de conmutación por error](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="4201f-133">For more information, see [Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters](https://technet.microsoft.com/library/ee619744\(WS.10\).aspx).</span></span>  
  
##### <a name="to-view-nodeweight-settings"></a><span data-ttu-id="4201f-134">Para ver la configuración de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="4201f-134">To view NodeWeight settings</span></span>  
  
1.  <span data-ttu-id="4201f-135">Inicie un símbolo del sistema con privilegios elevados mediante **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="4201f-135">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="4201f-136">Use **cluster.exe** para devolver el estado de nodo y los valores de NodeWeight</span><span class="sxs-lookup"><span data-stu-id="4201f-136">Use **cluster.exe** to return node status and NodeWeight values</span></span>  
  
### <a name="example-clusterexe"></a><span data-ttu-id="4201f-137">Ejemplo (Cluster.exe)</span><span class="sxs-lookup"><span data-stu-id="4201f-137">Example (Cluster.exe)</span></span>  
 <span data-ttu-id="4201f-138">En el ejemplo siguiente se envían algunas de las propiedades de nodo para el clúster denominado "Cluster001".</span><span class="sxs-lookup"><span data-stu-id="4201f-138">The following example outputs some of the node properties for the cluster called "Cluster001".</span></span>  
  
```cmd
cluster.exe Cluster001 node /status /properties  
```  
  
## <a name="see-also"></a><span data-ttu-id="4201f-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4201f-139">See Also</span></span>  
 <span data-ttu-id="4201f-140">[Configuración de los votos y modos de cuórum WSFC &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4201f-140">[WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md) </span></span>  
 <span data-ttu-id="4201f-141">[Configurar los valores de NodeWeight de quórum de clúster](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="4201f-141">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="4201f-142">[sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4201f-142">[sys.dm_hadr_cluster_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-hadr-cluster-members-transact-sql) </span></span>  
 <span data-ttu-id="4201f-143">[Cmdlets de clúster de conmutación por error en Windows PowerShell enumerados por tarea](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4201f-143">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
