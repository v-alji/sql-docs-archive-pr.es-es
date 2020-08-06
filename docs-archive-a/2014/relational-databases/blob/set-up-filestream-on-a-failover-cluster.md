---
title: Configurar FILESTREAM en un clúster de conmutación por error | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], setting up on a failover cluster
ms.assetid: 6721f780-20b7-4109-8ddb-ac327310699e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 29541bbcfd323a85a3fa751f60904fd1a26e1199
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744139"
---
# <a name="set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="06f7a-102">Configurar FILESTREAM en un clúster de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="06f7a-102">Set Up FILESTREAM on a Failover Cluster</span></span>
  <span data-ttu-id="06f7a-103">En este tema se describe cómo habilitar FILESTREAM en un clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="06f7a-103">This topic describes how to enable FILESTREAM on a failover cluster.</span></span> <span data-ttu-id="06f7a-104">Antes de probar este procedimiento, debería conocer los [clústeres de conmutación por error](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) y tener habilitado FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="06f7a-104">Before you try this procedure, you should understand [failover clustering](../../sql-server/failover-clusters/windows/always-on-failover-cluster-instances-sql-server.md) and have FILESTREAM enabled.</span></span> <span data-ttu-id="06f7a-105">Para obtener información sobre cómo habilitar FILESTREAM, vea [Habilitar y configurar FILESTREAM](enable-and-configure-filestream.md).</span><span class="sxs-lookup"><span data-stu-id="06f7a-105">For information about how to enable FILESTREAM, see [Enable and Configure FILESTREAM](enable-and-configure-filestream.md).</span></span>  
  
### <a name="to-set-up-filestream-on-a-failover-cluster"></a><span data-ttu-id="06f7a-106">Para configurar FILESTREAM en un clúster de conmutación por error</span><span class="sxs-lookup"><span data-stu-id="06f7a-106">To set up FILESTREAM on a failover cluster</span></span>  
  
1.  <span data-ttu-id="06f7a-107">Configure el nodo principal para el clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="06f7a-107">Set up the primary node for the failover cluster.</span></span>  
  
     <span data-ttu-id="06f7a-108">Cuando finalice el programa de instalación, habilite FILESTREAM en el nodo principal utilizando **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="06f7a-108">After the setup finishes, enable FILESTREAM on the primary node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="06f7a-109">De este modo habilita la configuración que requiere los privilegios de administrador de Windows.</span><span class="sxs-lookup"><span data-stu-id="06f7a-109">This enables the settings that require Windows Admin privileges.</span></span> <span data-ttu-id="06f7a-110">Si se requiere acceso remoto, seleccione **Permitir que los clientes remotos tengan acceso de transmisión por secuencias a los datos de FILESTREAM**.</span><span class="sxs-lookup"><span data-stu-id="06f7a-110">If remote access is required, select **Allow remote clients to have streaming access to FILESTREAM data**.</span></span> <span data-ttu-id="06f7a-111">De esta forma creará un recurso de clúster de recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="06f7a-111">This will create a file-share cluster resource.</span></span>  
  
2.  <span data-ttu-id="06f7a-112">Configure un nodo pasivo.</span><span class="sxs-lookup"><span data-stu-id="06f7a-112">Set up a passive node.</span></span>  
  
     <span data-ttu-id="06f7a-113">Cuando finalice el programa de instalación, habilite FILESTREAM en el nodo pasivo utilizando **Administrador de configuración de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="06f7a-113">After the setup finishes, enable FILESTREAM on the passive node by using **SQL Server Configuration Manager**.</span></span> <span data-ttu-id="06f7a-114">El nombre que especifica para **Nombre de recurso compartido de Windows** debe ser el mismo en todos los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="06f7a-114">The name that you specify for **Windows Share Name** must be the same across all nodes in the cluster.</span></span>  
  
3.  <span data-ttu-id="06f7a-115">Repita el paso 2 para agregar más nodos pasivos.</span><span class="sxs-lookup"><span data-stu-id="06f7a-115">To add more passive nodes, repeat step 2.</span></span>  
  
4.  <span data-ttu-id="06f7a-116">Una vez agregados todos los nodos, complete el proceso ejecutando el procedimiento almacenado sp_configure en cada sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06f7a-116">After all the nodes are added, complete the process by executing the sp_configure stored procedure on each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="06f7a-117">Puede repetir los pasos 2, 3 y 4 para agregar y habilitar nodos adicionales en el clúster en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="06f7a-117">To add and enable additional nodes to the cluster at any time, you can repeat steps 2, 3, and 4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06f7a-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06f7a-118">See Also</span></span>  
 <span data-ttu-id="06f7a-119">[Opciones de configuración de servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="06f7a-119">[Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="06f7a-120">[Crear un nuevo clúster de conmutación por error de SQL Server &#40;programa de instalación&#41;](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span><span class="sxs-lookup"><span data-stu-id="06f7a-120">[Create a New SQL Server Failover Cluster &#40;Setup&#41;](../../sql-server/failover-clusters/install/create-a-new-sql-server-failover-cluster-setup.md) </span></span>  
 <span data-ttu-id="06f7a-121">[Quitar una instancia de clúster de conmutación por error de SQL Server &#40;programa de instalación&#41;](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span><span class="sxs-lookup"><span data-stu-id="06f7a-121">[Remove a SQL Server Failover Cluster Instance &#40;Setup&#41;](../../sql-server/failover-clusters/install/remove-a-sql-server-failover-cluster-instance-setup.md) </span></span>  
 [<span data-ttu-id="06f7a-122">Agregar o quitar nodos en un clúster de conmutación por error de SQL Server &#40;programa de instalación&#41;</span><span class="sxs-lookup"><span data-stu-id="06f7a-122">Add or Remove Nodes in a SQL Server Failover Cluster &#40;Setup&#41;</span></span>](../../sql-server/failover-clusters/install/add-or-remove-nodes-in-a-sql-server-failover-cluster-setup.md)  
  
  
