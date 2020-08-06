---
title: Cambiar la dirección IP de una instancia de clúster de conmutación por error | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- modifying IP addresses
- failover clustering [SQL Server], IP addresses
- IP addresses [SQL Server]
- clusters [SQL Server], IP addresses
ms.assetid: b685f400-cbfe-4c5d-a070-227a1123dae4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45d3ef0b70282efd870e4a076663719c2549deaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672568"
---
# <a name="change-the-ip-address-of-a-failover-cluster-instance"></a><span data-ttu-id="1fcb3-102">Cambiar la dirección IP de una instancia de clúster de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="1fcb3-102">Change the IP Address of a Failover Cluster Instance</span></span>
  <span data-ttu-id="1fcb3-103">En este tema se describe cómo se cambia el recurso de dirección IP de una instancia de clúster de conmutación por error (FCI) AlwaysOn con el complemento Administrador de clústeres de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="1fcb3-103">This topic describes how to change the IP address resource in an AlwaysOn Failover Cluster Instance (FCI) by using the Failover Cluster Manager snap-in.</span></span> <span data-ttu-id="1fcb3-104">El complemento Administrador de clústeres de conmutación por error es la aplicación de administración de clústeres del servicio de clústeres de conmutación por error de Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="1fcb3-104">The Failover Cluster Manager snap-in is the cluster management application for the Windows Server Failover Clustering (WSFC) service.</span></span>  
  
-   <span data-ttu-id="1fcb3-105">**Antes de empezar:**  [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="1fcb3-105">**Before you begin:**  [Security](#Security)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1fcb3-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="1fcb3-106">Before You Begin</span></span>  
 <span data-ttu-id="1fcb3-107">Antes de comenzar, revise el siguiente tema de los Libros en pantalla de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] : [Antes de instalar los clústeres de conmutación por error](../install/before-installing-failover-clustering.md).</span><span class="sxs-lookup"><span data-stu-id="1fcb3-107">Before you begin, review the following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online topic: [Before Installing Failover Clustering](../install/before-installing-failover-clustering.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1fcb3-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="1fcb3-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1fcb3-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="1fcb3-109">Permissions</span></span>  
 <span data-ttu-id="1fcb3-110">Para mantener o actualizar una DCI, debe ser administrador local y tener permisos para iniciar sesión como servicio en todos los nodos de la FCI.</span><span class="sxs-lookup"><span data-stu-id="1fcb3-110">To maintain or update an FCI, you must be a local administrator with permission to logon as a service on all nodes of the FCI.</span></span>  
  
##  <a name="using-the-failover-cluster-manager-snap-in"></a><a name="WSFC"></a> <span data-ttu-id="1fcb3-111">Usar el complemento Administrador de clústeres de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="1fcb3-111">Using the Failover Cluster Manager Snap-in</span></span>  
 <span data-ttu-id="1fcb3-112">**Para cambiar el recurso de dirección IP de una FCI**</span><span class="sxs-lookup"><span data-stu-id="1fcb3-112">**To change the IP address resource for an FCI**</span></span>  
  
1.  <span data-ttu-id="1fcb3-113">Abra el complemento Administrador de clústeres de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="1fcb3-113">Open the Failover Cluster Manager snap-in.</span></span>  
  
2.  <span data-ttu-id="1fcb3-114">Expanda el nodo **servicios y aplicaciones** en el panel izquierdo y haga clic en la FCI.</span><span class="sxs-lookup"><span data-stu-id="1fcb3-114">Expand the **Services and applications** node, in the left pane and click on the FCI.</span></span>  
  
3.  <span data-ttu-id="1fcb3-115">En el panel derecho, en la categoría **Nombre del servidor** , haga clic con el botón derecho en la instancia de SQL Server y seleccione la opción **Propiedades** para abrir el cuadro de diálogo **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="1fcb3-115">On the right pane, under the **Server Name** category, right-click the SQL Server Instance, and select **Properties** option to open the **Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="1fcb3-116">En la pestaña **General** , cambie el recurso de dirección IP.</span><span class="sxs-lookup"><span data-stu-id="1fcb3-116">On the **General** tab, change the IP address resource.</span></span>  
  
5.  <span data-ttu-id="1fcb3-117">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1fcb3-117">Click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="1fcb3-118">En el panel derecho, haga clic con el botón derecho en la dirección IP1 de SQL (nombre de la instancia en clúster de conmutación por error) y seleccione **Poner sin conexión**.</span><span class="sxs-lookup"><span data-stu-id="1fcb3-118">In the right-hand pane, right-click the SQL IP Address1(failover cluster instance name) and select **Take Offline**.</span></span> <span data-ttu-id="1fcb3-119">Verá que el estado de la dirección IP1 de SQL (nombre de la instancia en clúster de conmutación por error), el nombre de red de SQL (nombre de la instancia en clúster de conmutación por error) y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pasa de En línea a Sin conexión pendiente y luego a Sin conexión.</span><span class="sxs-lookup"><span data-stu-id="1fcb3-119">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Online to Offline Pending, and then to Offline.</span></span>  
  
7.  <span data-ttu-id="1fcb3-120">En el panel derecho, haga clic con el botón derecho en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]y seleccione **Poner en línea**.</span><span class="sxs-lookup"><span data-stu-id="1fcb3-120">In the right-hand pane, right-click [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and then select **Bring Online**.</span></span> <span data-ttu-id="1fcb3-121">Verá que el estado de la dirección IP1 de SQL (nombre de la instancia en clúster de conmutación por error), el nombre de red de SQL (nombre de la instancia en clúster de conmutación por error) y [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pasa de Sin conexión a Sin conexión pendiente y luego a En línea.</span><span class="sxs-lookup"><span data-stu-id="1fcb3-121">You will see the SQL IP Address1(failover cluster instance name), SQL Network Name(failover cluster instance name), and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] status change from Offline to Online Pending, and then to Online.</span></span>  
  
8.  <span data-ttu-id="1fcb3-122">Cierre el complemento Administrador de clústeres de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="1fcb3-122">Close the Failover Cluster Manager snap-in.</span></span>  
  
  
