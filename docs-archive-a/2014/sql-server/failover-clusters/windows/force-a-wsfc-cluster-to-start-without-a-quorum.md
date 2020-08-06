---
title: Forzar el inicio de un clúster WSFC sin un quórum | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], WSFC clusters
- quorum [SQL Server], AlwaysOn and WSFC quorum
ms.assetid: 4a121375-7424-4444-b876-baefa8fe9015
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b6f2110b706de015d0c7b19475b335908c118267
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672554"
---
# <a name="force-a-wsfc-cluster-to-start-without-a-quorum"></a><span data-ttu-id="3def1-102">Forzar el inicio de un clúster WSFC sin un quórum</span><span class="sxs-lookup"><span data-stu-id="3def1-102">Force a WSFC Cluster to Start Without a Quorum</span></span>
  <span data-ttu-id="3def1-103">En este tema se describe cómo forzar que un nodo de clúster de los clústeres de conmutación por error de Windows Server (WSFC) se inicie sin un quórum.</span><span class="sxs-lookup"><span data-stu-id="3def1-103">This topic describes how to force a Windows Server Failover Clustering (WSFC) cluster node to start without a quorum.</span></span>  <span data-ttu-id="3def1-104">Esto puede ser necesario en los escenarios de recuperación de desastres y de múltiples subredes para recuperar datos y reestablecer por completo la alta disponibilidad para las instancias de clúster de conmutación por error de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3def1-104">This may be required in disaster recovery and multi-subnet scenarios to recover data and fully re-establish high-availability for [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Failover Cluster Instances.</span></span>  
  
-   <span data-ttu-id="3def1-105">**Antes de empezar:**  [Recomendaciones](#Recommendations), [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="3def1-105">**Before you start:**  [Recommendations](#Recommendations), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="3def1-106">**Para forzar que un clúster se inicie sin un quórum con:**  [Usar el Administrador de clústeres de conmutación por error](#FailoverClusterManagerProcedure), [Usar PowerShell](#PowerShellProcedure), [Usar Net.exe](#CommandPromptProcedure)</span><span class="sxs-lookup"><span data-stu-id="3def1-106">**To force a cluster to start without a quorum using:**  [Using Failover Cluster Manager](#FailoverClusterManagerProcedure), [Using Powershell](#PowerShellProcedure), [Using Net.exe](#CommandPromptProcedure)</span></span>  
  
-   <span data-ttu-id="3def1-107">**Seguimiento:**  [Seguimiento: Después de forzar que el clúster se inicie sin un quórum](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="3def1-107">**Follow up:**  [Follow Up: After Forcing Cluster to Start without a Quorum](#FollowUp)</span></span>  
  
##  <a name="before-you-start"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3def1-108">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="3def1-108">Before You Start</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="3def1-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="3def1-109">Recommendations</span></span>  
 <span data-ttu-id="3def1-110">Excepto donde se indique de forma explícita, los procedimientos de este tema deben funcionar si se ejecutan desde cualquier nodo del clúster de WSFC.</span><span class="sxs-lookup"><span data-stu-id="3def1-110">Except where explicitly directed, the procedures in this topic should work if you execute them from any node in the WSFC cluster.</span></span>  <span data-ttu-id="3def1-111">No obstante, se pueden obtener mejores resultados, y evitar programas de red, si se ejecutan estos pasos desde el nodo que se desea forzar para que se inicie sin un quórum.</span><span class="sxs-lookup"><span data-stu-id="3def1-111">However, you may obtain better results, and avoid networking issues, by executing these steps from the node that you intend to force to start without a quorum.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3def1-112">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3def1-112">Security</span></span>  
 <span data-ttu-id="3def1-113">El usuario debe ser una cuenta de dominio que sea miembro del grupo Administradores en cada nodo del clúster de WSFC.</span><span class="sxs-lookup"><span data-stu-id="3def1-113">The user must be a domain account that is member of the local Administrators group on each node of the WSFC cluster.</span></span>  
  
##  <a name="using-failover-cluster-manager"></a><a name="FailoverClusterManagerProcedure"></a><span data-ttu-id="3def1-114">Usar Administrador de clústeres de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="3def1-114">Using Failover Cluster Manager</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="3def1-115">Para forzar que un clúster se inicie sin un quórum</span><span class="sxs-lookup"><span data-stu-id="3def1-115">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="3def1-116">Abra el Administrador de clústeres de conmutación por error y conéctese al nodo de clúster deseado para forzarlo en línea.</span><span class="sxs-lookup"><span data-stu-id="3def1-116">Open a Failover Cluster Manager and connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="3def1-117">En el panel **acciones** , haga clic en **Forzar inicio de clúster**y, a continuación, haga clic en **sí: forzar el inicio del clúster**.</span><span class="sxs-lookup"><span data-stu-id="3def1-117">In the **Actions** pane, click **Force Cluster Start**, and then click **Yes - Force my cluster to start**.</span></span>  
  
3.  <span data-ttu-id="3def1-118">En el panel izquierda, en el árbol **Administrador de clústeres de conmutación por error** , haga clic en el nombre del clúster.</span><span class="sxs-lookup"><span data-stu-id="3def1-118">In the left pane, in the **Failover Cluster Manager** tree, click the cluster name.</span></span>  
  
4.  <span data-ttu-id="3def1-119">En el panel de resumen, configure que el valor de **Configuración de quórum** actual es:  **Advertencia: el clúster se está ejecutando en el estado ForceQuorum**.</span><span class="sxs-lookup"><span data-stu-id="3def1-119">In the summary pane, confirm that the current **Quorum Configuration** value is:  **Warning: Cluster is running in ForceQuorum state**.</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a><span data-ttu-id="3def1-120">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="3def1-120">Using Powershell</span></span>  
  
##### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="3def1-121">Para forzar que un clúster se inicie sin un quórum</span><span class="sxs-lookup"><span data-stu-id="3def1-121">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="3def1-122">Inicie Windows PowerShell con derechos elevados mediante **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="3def1-122">Start an elevated Windows PowerShell via **Run as Administrator**.</span></span>  
  
2.  <span data-ttu-id="3def1-123">Importe el módulo `FailoverClusters` para habilitar los commandlets de clúster.</span><span class="sxs-lookup"><span data-stu-id="3def1-123">Import the `FailoverClusters` module to enable cluster commandlets.</span></span>  
  
3.  <span data-ttu-id="3def1-124">Use `Stop-ClusterNode` para asegurarse de que el servicio de clúster está detenido.</span><span class="sxs-lookup"><span data-stu-id="3def1-124">Use `Stop-ClusterNode` to make sure that the cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="3def1-125">Use `Start-ClusterNode` con `-FixQuorum` para forzar que se inicie el servicio de clúster.</span><span class="sxs-lookup"><span data-stu-id="3def1-125">Use `Start-ClusterNode` with `-FixQuorum` to force the cluster service to start.</span></span>  
  
5.  <span data-ttu-id="3def1-126">Use `Get-ClusterNode` con `-Propery NodeWieght = 1` para establecer el valor que garantiza que el nodo es un miembro con derecho a voto del quórum.</span><span class="sxs-lookup"><span data-stu-id="3def1-126">Use `Get-ClusterNode` with `-Propery NodeWieght = 1` to set the value the guarantees that the node is a voting member of the quorum.</span></span>  
  
6.  <span data-ttu-id="3def1-127">Enviar las propiedades de nodo de clúster en un formato legible.</span><span class="sxs-lookup"><span data-stu-id="3def1-127">Output the cluster node properties in a readable format.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="3def1-128">Ejemplo (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="3def1-128">Example (Powershell)</span></span>  
 <span data-ttu-id="3def1-129">En el siguiente ejemplo se fuerza que el servicio de clúster de nodo AlwaysOnSrv02 se inicie sin un quórum, establece `NodeWeight = 1`y, a continuación, enumera el estado de nodo de clúster a partir del nodo que se acaba de forzar.</span><span class="sxs-lookup"><span data-stu-id="3def1-129">The following example forces the AlwaysOnSrv02 node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```powershell  
Import-Module FailoverClusters  
  
$node = "AlwaysOnSrv02"  
Stop-ClusterNode -Name $node  
Start-ClusterNode -Name $node -FixQuorum  
  
(Get-ClusterNode $node).NodeWeight = 1  
  
$nodes = Get-ClusterNode -Cluster $node  
$nodes | Format-Table -property NodeName, State, NodeWeight
```  
  
##  <a name="using-netexe"></a><a name="CommandPromptProcedure"></a><span data-ttu-id="3def1-130">Usar Net.exe</span><span class="sxs-lookup"><span data-stu-id="3def1-130">Using Net.exe</span></span>  
  
### <a name="to-force-a-cluster-to-start-without-a-quorum"></a><span data-ttu-id="3def1-131">Para forzar que un clúster se inicie sin un quórum</span><span class="sxs-lookup"><span data-stu-id="3def1-131">To force a cluster to start without a quorum</span></span>  
  
1.  <span data-ttu-id="3def1-132">Use Escritorio remoto para conectarse al nodo de clúster deseado para forzarlo en línea.</span><span class="sxs-lookup"><span data-stu-id="3def1-132">Use Remote Desktop to connect to the desired cluster node to force online.</span></span>  
  
2.  <span data-ttu-id="3def1-133">Inicie un símbolo del sistema con privilegios elevados mediante **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="3def1-133">Start an elevated Command Prompt via **Run as Administrator**.</span></span>  
  
3.  <span data-ttu-id="3def1-134">Use **net.exe** para asegurarse de que el servicio de clúster local está detenido.</span><span class="sxs-lookup"><span data-stu-id="3def1-134">Use **net.exe** to make sure that the local cluster service is stopped.</span></span>  
  
4.  <span data-ttu-id="3def1-135">Use **net.exe** con `/forcequorum` para forzar que se inicie el servicio de clúster local.</span><span class="sxs-lookup"><span data-stu-id="3def1-135">Use **net.exe** with `/forcequorum` to force the local cluster service to start.</span></span>  
  
### <a name="example-netexe"></a><span data-ttu-id="3def1-136">Ejemplo (Net.exe)</span><span class="sxs-lookup"><span data-stu-id="3def1-136">Example (Net.exe)</span></span>  
 <span data-ttu-id="3def1-137">En el siguiente ejemplo se fuerza que un servicio de clúster de nodo se inicie sin un quórum, establece `NodeWeight = 1`y, a continuación, enumera el estado de nodo de clúster a partir del nodo que se acaba de forzar.</span><span class="sxs-lookup"><span data-stu-id="3def1-137">The following example forces a node cluster service to start without a quorum, sets the `NodeWeight = 1`, and then enumerates cluster node status from the newly forced node.</span></span>  
  
```cmd
net.exe stop clussvc  
net.exe start clussvc /forcequorum  
```  
  
##  <a name="follow-up-after-forcing-cluster-to-start-without-a-quorum"></a><a name="FollowUp"></a><span data-ttu-id="3def1-138">Seguimiento: después de forzar que el clúster se inicie sin un Cuórum</span><span class="sxs-lookup"><span data-stu-id="3def1-138">Follow Up: After Forcing Cluster to Start without a Quorum</span></span>  
  
-   <span data-ttu-id="3def1-139">Debe evaluar y configurar de nuevo los valores de NodeWeight para construir correctamente un nuevo quórum antes de volver a poner otros nodos en línea.</span><span class="sxs-lookup"><span data-stu-id="3def1-139">You must re-evaluate and reconfigure NodeWeight values to correctly construct a new quorum before bringing other nodes back online.</span></span> <span data-ttu-id="3def1-140">De lo contrario, el clúster puede volver a estar sin conexión.</span><span class="sxs-lookup"><span data-stu-id="3def1-140">Otherwise, the cluster may go back offline again.</span></span>  
  
     <span data-ttu-id="3def1-141">Para obtener más información, vea [Configuración de los votos y modos de cuórum WSFC &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3def1-141">For more information, see [WSFC Quorum Modes and Voting Configuration &#40;SQL Server&#41;](wsfc-quorum-modes-and-voting-configuration-sql-server.md).</span></span>  
  
-   <span data-ttu-id="3def1-142">Los procedimientos de este tema constituyen solo en paso para volver a poner en línea el clúster de WSFC si se produce un error de quórum no planificado.</span><span class="sxs-lookup"><span data-stu-id="3def1-142">The procedures in this topic are only one step in bringing the WSFC cluster back online if an un-planned quorum failure were to occur.</span></span>  <span data-ttu-id="3def1-143">Puede que también desee llevar a cabo pasos adicionales para impedir que otros nodos de clúster de WSFC interfieran en la nueva configuración de quórum.</span><span class="sxs-lookup"><span data-stu-id="3def1-143">You may also want to take additional steps to prevent other WSFC cluster nodes from interfering with the new quorum configuration.</span></span>  
  
-   <span data-ttu-id="3def1-144">Otras características de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], creación de reflejo de la base de datos y trasvase de registros también pueden necesitar acciones posteriores para recuperar los datos y volver a establecer la alta disponibilidad por completo.</span><span class="sxs-lookup"><span data-stu-id="3def1-144">Other [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features such as [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], database mirroring, and log shipping may also require subsequent actions to recover data and to fully re-establish high-availability.</span></span>  
  
     <span data-ttu-id="3def1-145">**Para obtener más información:**</span><span class="sxs-lookup"><span data-stu-id="3def1-145">**For more information:**</span></span>  
  
     [<span data-ttu-id="3def1-146">Realizar una conmutación por error manual forzada de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3def1-146">Perform a Forced Manual Failover of an Availability Group &#40;SQL Server&#41;</span></span>](../../../database-engine/availability-groups/windows/perform-a-forced-manual-failover-of-an-availability-group-sql-server.md)  
  
     [<span data-ttu-id="3def1-147">Forzar el servicio en una sesión de creación de reflejo de la base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3def1-147">Force Service in a Database Mirroring Session &#40;Transact-SQL&#41;</span></span>](../../../database-engine/database-mirroring/force-service-in-a-database-mirroring-session-transact-sql.md)  
  
     [<span data-ttu-id="3def1-148">Conmutar por error a una base de datos secundaria de trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3def1-148">Fail Over to a Log Shipping Secondary &#40;SQL Server&#41;</span></span>](../../../database-engine/log-shipping/fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="3def1-149">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="3def1-149">Related Content</span></span>  
  
-   <span data-ttu-id="3def1-150">[View Events and Logs for a Failover Cluster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="3def1-150">[View Events and Logs for a Failover Cluster](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772342(v=ws.11))</span></span>  
  
-   [<span data-ttu-id="3def1-151">Cmdlet de clúster de conmutación por error Get-ClusterLog</span><span class="sxs-lookup"><span data-stu-id="3def1-151">Get-ClusterLog Failover Cluster Cmdlet</span></span>](https://technet.microsoft.com/library/ee461045.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="3def1-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3def1-152">See Also</span></span>  
 <span data-ttu-id="3def1-153">[Recuperación ante desastres de WSFC mediante &#40;de Cuórum SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3def1-153">[WSFC Disaster Recovery through Forced Quorum &#40;SQL Server&#41;](wsfc-disaster-recovery-through-forced-quorum-sql-server.md) </span></span>  
 <span data-ttu-id="3def1-154">[Configurar los valores de NodeWeight de Cuórum de clúster](configure-cluster-quorum-nodeweight-settings.md) </span><span class="sxs-lookup"><span data-stu-id="3def1-154">[Configure Cluster Quorum NodeWeight Settings](configure-cluster-quorum-nodeweight-settings.md) </span></span>  
 <span data-ttu-id="3def1-155">[Cmdlets de clúster de conmutación por error en Windows PowerShell enumerados por tarea](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3def1-155">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://technet.microsoft.com/library/ee619761\(WS.10\).aspx)</span></span>  
