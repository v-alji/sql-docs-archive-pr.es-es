---
title: Quitar una instancia de clúster de conmutación por error de SQL Server (programa de instalación) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
helpviewer_keywords:
- clusters [SQL Server], removing failover clustered instance
- failover clustering [SQL Server], removing failover clustered instance
- uninstalling failover clustered instances
- removing failover clustered instances
ms.assetid: bf63353b-69cf-4c5c-98ea-7b151e36537f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a4d0ae492481b0677be2d2692fbda0fbc8eb604b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672586"
---
# <a name="remove-a-sql-server-failover-cluster-instance-setup"></a><span data-ttu-id="d3a4d-102">Quitar una instancia de clúster de conmutación por error de SQL Server (programa de instalación)</span><span class="sxs-lookup"><span data-stu-id="d3a4d-102">Remove a SQL Server Failover Cluster Instance (Setup)</span></span>
  <span data-ttu-id="d3a4d-103">Utilice este procedimiento para desinstalar una instancia en clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3a4d-103">Use this procedure to uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover clustered instance.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d3a4d-104">Para actualizar o quitar un clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] es preciso ser administrador local con derecho de iniciar sesión como servicio en todos los nodos del clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="d3a4d-104">To update or remove a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster, you must be a local administrator with permission to login as a service on all nodes of the failover cluster.</span></span>  
  
 <span data-ttu-id="d3a4d-105">**Antes de empezar**</span><span class="sxs-lookup"><span data-stu-id="d3a4d-105">**Before you begin**</span></span>  
  
 <span data-ttu-id="d3a4d-106">Tenga en cuenta los siguiente puntos importantes antes de desinstalar un clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="d3a4d-106">Consider the following important points before you uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster:</span></span>  
  
-   <span data-ttu-id="d3a4d-107">Si se desinstala [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client por accidente, se generará un error al iniciar los recursos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3a4d-107">If [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is uninstalled by accident, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resources will fail to start.</span></span> <span data-ttu-id="d3a4d-108">Para volver a instalar [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, ejecute el programa de instalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para instalar los requisitos previos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d3a4d-108">To reinstall [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, run the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup program to install [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] prerequisites.</span></span>  
  
-   <span data-ttu-id="d3a4d-109">Si desinstala un clúster de conmutación por error que tenga más de un recurso de clúster IP de SQL, debe quitar los recursos IP de SQL adicionales mediante el Administrador de clústeres.</span><span class="sxs-lookup"><span data-stu-id="d3a4d-109">If you uninstall a failover cluster that has more than one SQL IP cluster resource, you must remove the additional SQL IP resources using cluster administrator.</span></span>  
  
 <span data-ttu-id="d3a4d-110">Para obtener información acerca de la sintaxis del símbolo del sistema, consulte [Install SQL Server 2014 desde el símbolo del sistema](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="d3a4d-110">For information about command prompt syntax, see [Install SQL Server 2014 from the Command Prompt](../../../database-engine/install-windows/install-sql-server-from-the-command-prompt.md).</span></span>  
  
### <a name="to-uninstall-a-ssnoversion-failover-cluster"></a><span data-ttu-id="d3a4d-111">Para desinstalar un clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3a4d-111">To uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster</span></span>  
  
1.  <span data-ttu-id="d3a4d-112">Para desinstalar un clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , utilice la funcionalidad Eliminar nodo proporcionada por el programa de instalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para quitar cada nodo individualmente.</span><span class="sxs-lookup"><span data-stu-id="d3a4d-112">To uninstall a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] failover cluster, use the Remove Node functionality provided by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Setup to remove each node individually.</span></span> <span data-ttu-id="d3a4d-113">Para obtener más información, vea [Agregar o quitar nodos en un clúster de conmutación por error de SQL Server &#40;programa de instalación&#41;](add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span><span class="sxs-lookup"><span data-stu-id="d3a4d-113">For more information, see [Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;](add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3a4d-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3a4d-114">See Also</span></span>  
 [<span data-ttu-id="d3a4d-115">Ver y leer los archivos de registro de instalación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="d3a4d-115">View and Read SQL Server Setup Log Files</span></span>](../../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)  
  
  
