---
title: Configuración de red en clúster | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- cluster network selection, Setup
- cluster network selection
ms.assetid: 579482ef-a023-45b2-9176-b4a4188adf9d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 17ab563817a3b9b476dfd566f4a7f2beda98ca26
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672494"
---
# <a name="cluster-network-configuration"></a><span data-ttu-id="3dcd9-102">Configuración de red en clúster</span><span class="sxs-lookup"><span data-stu-id="3dcd9-102">Cluster Network Configuration</span></span>
  <span data-ttu-id="3dcd9-103">Utilice la página **Selección de red en clúster** para especificar los recursos de red para la instancia en clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-103">Use the **Cluster Network Selection** page to specify the network resources for your failover cluster instance.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3dcd9-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="3dcd9-104">Options</span></span>  
 <span data-ttu-id="3dcd9-105">\*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Nombre de red en clúster de conmutación por error\*\* : es el nombre que se usa para identificar la instancia de clúster de conmutación por error en la red.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-105">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Failover Cluster Network Name** - This is the name used to identify your failover cluster instance on the network.</span></span>  
  
 <span data-ttu-id="3dcd9-106">**Configuración de red** : especifique el tipo de IP y la dirección IP de la instancia de clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-106">**Network Settings** - Specify the IP type and IP address for your failover cluster instance.</span></span>  
  
 <span data-ttu-id="3dcd9-107">Durante las operaciones Agregar nodo y Quitar nodo, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muestra una lista de solo lectura de las direcciones IP existentes para el clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3dcd9-107">During the Add Node and Remove Node operations, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a read-only list of the existing IP addresses for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster.</span></span>  
  
-   <span data-ttu-id="3dcd9-108">Instalación integrada:</span><span class="sxs-lookup"><span data-stu-id="3dcd9-108">Integrated Install:</span></span>  
  
    -   <span data-ttu-id="3dcd9-109">Si va a agregar un nodo que admita un conjunto idéntico de subredes de red que admitan los nodos existentes del clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , no se puede agregar ninguna dirección IP adicional.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-109">If you are adding a node that supports an identical set of network subnets supported by the existing nodes of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP addresses can be added.</span></span> <span data-ttu-id="3dcd9-110">La configuración de dependencia permanece sin modificar.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-110">The dependency setting remains unchanged.</span></span>  
  
    -   <span data-ttu-id="3dcd9-111">Si va a agregar un nodo que admita un subconjunto de las subredes de red que admitan los nodos existentes en el clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , no se pueden agregar recursos de dirección IP adicionales.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-111">If you are adding a node that supports a subset of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, no additional IP address resources can be added.</span></span> <span data-ttu-id="3dcd9-112">La dependencia de recursos de direcciones IP se establece en OR para reflejar que todas las direcciones IP especificadas no son válidas en todos los nodos de clúster.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-112">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="3dcd9-113">Si va a agregar un nodo que admita subredes además de las subredes que ya admitían los nodos existentes en el clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , tiene la opción de agregar nuevas direcciones IP válidas.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-113">If you are adding a node that supports subnets in addition to the subnets already supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you have the option of adding new valid IP addresses.</span></span> <span data-ttu-id="3dcd9-114">Si se especifican nuevas direcciones IP, la dependencia de recursos de direcciones IP se establece en OR para reflejar que todas las direcciones IP especificadas no son válidas en todos los nodos de clúster.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-114">If new IP addresses are specified, the IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
    -   <span data-ttu-id="3dcd9-115">Si va a agregar un nodo que sea compatible con subredes de red adicionales, pero no es compatible con ninguna de las subredes admitidas por los nodos existentes en el clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , tiene que agregar más direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-115">If you are adding a node that supports additional network subnets, but supports none of the subnets supported by the existing nodes on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are required to add additional IP addresses.</span></span> <span data-ttu-id="3dcd9-116">La dependencia de recursos de direcciones IP se establece en OR para reflejar que todas las direcciones IP especificadas no son válidas en todos los nodos de clúster.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-116">The IP address resource dependency is set to OR to reflect that all the specified IP addresses are not valid on all the cluster nodes.</span></span>  
  
-   <span data-ttu-id="3dcd9-117">Instalación avanzada: durante el paso para completar la instalación, especifique la dirección IP de todos los nodos y subredes de su instancia del clúster de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-117">Advanced Install: During the Complete step of the installation, specify the IP address for all the nodes and subnets for your failover cluster instance.</span></span> <span data-ttu-id="3dcd9-118">Puede especificar varias direcciones IP para un clústeres de conmutación por error de varias subredes, pero solo se admite una dirección IP por subred.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-118">You can specify multiple IP addresses for a multi-subnet failover cluster, but only one IP address per subnet is supported.</span></span> <span data-ttu-id="3dcd9-119">Cada nodo preparado debe ser propietario de al menos una dirección IP.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-119">Every prepared node should be an owner of at least one IP address.</span></span> <span data-ttu-id="3dcd9-120">Si tiene varias subredes en su clúster de conmutación por error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] m se le solicitará que establezca la dependencia de recursos de dirección IP en OR. Quitar nodo:</span><span class="sxs-lookup"><span data-stu-id="3dcd9-120">If you have multiple subnets in your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster, you are prompted to set the IP address resource dependency to OR.Remove Node:</span></span>  
  
    -   <span data-ttu-id="3dcd9-121">Si el resto de direcciones IP se admite en los nodos restantes, se le pide que establezca la dependencia de recursos de dirección IP en AND.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-121">If the remaining IP addresses are supported on all the remaining nodes, you are prompted to set the IP address resource dependencyto AND.</span></span>  
  
    -   <span data-ttu-id="3dcd9-122">Si el resto de direcciones IP no se admiten en todos los nodos restantes, la dependencia de recursos de dirección IP se deja como OR.</span><span class="sxs-lookup"><span data-stu-id="3dcd9-122">If the remaining IP addresses are not supported on all the remaining nodes, the IP address resource dependency is left as OR.</span></span>  
  
  
