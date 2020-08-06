---
title: Recuperarse de un error en una instancia de clúster de conmutación por error | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- clusters [SQL Server], recovery from failure
- failover clustering [SQL Server], recovery from failure
- hardware failures [SQL Server]
- recovering failover cluster failures [SQL Server]
ms.assetid: 3d151d0c-e841-4325-8606-c094de37d7d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60db4c2e480b094c18d0a8071e947a38cdc779d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749650"
---
# <a name="recover-from-failover-cluster-instance-failure"></a><span data-ttu-id="34371-102">Recuperarse de un error en una instancia de clúster de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="34371-102">Recover from Failover Cluster Instance Failure</span></span>
  <span data-ttu-id="34371-103">En este tema se describe cómo puede recuperarse de los errores de clúster usando el complemento Administrador de clústeres de conmutación por error después de que se produzca una conmutación por error en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34371-103">This topic describes how to recover from cluster failures by using the Failover Cluster Manager snap-in after a failover occurs in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="34371-104">El complemento Administrador de clústeres de conmutación por error es la aplicación de administración de clústeres del servicio de clústeres de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="34371-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Serer Failover Clustering (WSFC) service.</span></span>  
  
-   [<span data-ttu-id="34371-105">Recuperarse de un error irreparable</span><span class="sxs-lookup"><span data-stu-id="34371-105">Recover from an irreparable failure</span></span>](#Scenario1)  
  
-   [<span data-ttu-id="34371-106">Recuperarse de un error de software</span><span class="sxs-lookup"><span data-stu-id="34371-106">Recover from a software failure</span></span>](#Scenario2)  
  
##  <a name="recover-from-an-irreparable-failure"></a><a name="Scenario1"></a><span data-ttu-id="34371-107">Recuperarse de un error irreparable</span><span class="sxs-lookup"><span data-stu-id="34371-107">Recover from an irreparable failure</span></span>  
 <span data-ttu-id="34371-108">Siga estos pasos para recuperarse de un error irreparable.</span><span class="sxs-lookup"><span data-stu-id="34371-108">Use the following steps to recover from an irreparable failure.</span></span> <span data-ttu-id="34371-109">El error puede deberse, por ejemplo, a un error del controlador de disco o del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="34371-109">The failure could be caused, for example, by the failure of a disk controller or the operating system.</span></span> <span data-ttu-id="34371-110">En este caso, el error se debe a un problema de hardware en el nodo 1 de un clúster de dos nodos.</span><span class="sxs-lookup"><span data-stu-id="34371-110">In this case, failure is caused by hardware failure in Node 1 of a two-node cluster.</span></span>  
  
1.  <span data-ttu-id="34371-111">Cuando se produce un error en el nodo 1, la FCI de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] conmuta al nodo 2.</span><span class="sxs-lookup"><span data-stu-id="34371-111">After Node 1 fails, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="34371-112">Desaloje el nodo 1 de la FCI.</span><span class="sxs-lookup"><span data-stu-id="34371-112">Evict Node 1 from the FCI.</span></span> <span data-ttu-id="34371-113">Para ello, en el nodo 2, abra el complemento Administrador de clústeres de conmutación por error, haga clic con el botón derecho en Node1, haga clic en **Acciones de desplazamiento**y luego en **Expulsar el nodo**.</span><span class="sxs-lookup"><span data-stu-id="34371-113">To do this, from Node 2, open the Failover Cluster Manager snap-in, right-click Node1, click **Move Actions**, and then click **Evict Node**.</span></span>  
  
3.  <span data-ttu-id="34371-114">Compruebe que el nodo 1 se ha desalojado de la definición del clúster.</span><span class="sxs-lookup"><span data-stu-id="34371-114">Verify that Node 1 has been evicted from the cluster definition.</span></span>  
  
4.  <span data-ttu-id="34371-115">Instale el hardware nuevo que va a sustituir al que ha producido el error en el nodo 1.</span><span class="sxs-lookup"><span data-stu-id="34371-115">Install new hardware to replace the failed hardware in Node 1.</span></span>  
  
5.  <span data-ttu-id="34371-116">Mediante el complemento Administrador de clústeres de conmutación por error, agregue el nodo 1 al clúster existente.</span><span class="sxs-lookup"><span data-stu-id="34371-116">Using the Failover Cluster Manager snap-in, add Node 1 to the existing cluster.</span></span> <span data-ttu-id="34371-117">Para obtener más información, vea [Antes de instalar los clústeres de conmutación por error](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="34371-117">For more information, see [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
6.  <span data-ttu-id="34371-118">Asegúrese de que las cuentas de administrador son las mismas en todos los nodos de clúster.</span><span class="sxs-lookup"><span data-stu-id="34371-118">Ensure that the administrator accounts are the same on all cluster nodes.</span></span>  
  
7.  <span data-ttu-id="34371-119">Ejecute el programa de instalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para agregar el nodo 1 a la FCI.</span><span class="sxs-lookup"><span data-stu-id="34371-119">Run [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup to add Node 1 to the FCI.</span></span> <span data-ttu-id="34371-120">Para obtener más información, vea [Agregar o quitar nodos en un clúster de conmutación por error de SQL Server &#40;&#41;de instalación ](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="34371-120">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](../install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
##  <a name="recover-from-a-reparable-failure"></a><a name="Scenario2"></a><span data-ttu-id="34371-121">Recuperación de un error de reparable</span><span class="sxs-lookup"><span data-stu-id="34371-121">Recover from a reparable failure</span></span>  
 <span data-ttu-id="34371-122">Siga estos pasos para recuperarse de un error reparable.</span><span class="sxs-lookup"><span data-stu-id="34371-122">Us the following steps to recover from a reparable failure.</span></span> <span data-ttu-id="34371-123">En este caso, el error se produce porque el nodo 1 está inactivo o sin conexión pero todavía se puede recuperar.</span><span class="sxs-lookup"><span data-stu-id="34371-123">In this case, failure is caused by Node 1 being down or offline but not irretrievably broken.</span></span> <span data-ttu-id="34371-124">Este error podría estar causado por un error del sistema operativo, un error de hardware o un error de la propia instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34371-124">This could be caused by an operating system failure, hardware failure, or failure in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance itself.</span></span>  
  
1.  <span data-ttu-id="34371-125">Cuando se produce un error en el nodo 1, la FCI conmuta al nodo 2.</span><span class="sxs-lookup"><span data-stu-id="34371-125">After Node 1 fails, the FCI fails over to Node 2.</span></span>  
  
2.  <span data-ttu-id="34371-126">Solucione el problema del nodo 1.</span><span class="sxs-lookup"><span data-stu-id="34371-126">Resolve the problem with Node 1.</span></span>  
  
3.  <span data-ttu-id="34371-127">Asegúrese de que todos los nodos están en línea y de que el servicio WSFC funciona.</span><span class="sxs-lookup"><span data-stu-id="34371-127">Ensure that all nodes are online and the WSFC service is working.</span></span>  
  
4.  <span data-ttu-id="34371-128">Realice la conmutación por error de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] al nodo recuperado.</span><span class="sxs-lookup"><span data-stu-id="34371-128">Fail over [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the recovered node.</span></span>  
  
  
