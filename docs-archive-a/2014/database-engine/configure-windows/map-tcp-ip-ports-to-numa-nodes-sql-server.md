---
title: Asignación de puertos TCP/IP a nodos NUMA (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- NUMA
- memory [SQL Server], NUMA
- affinity NUMA
- ports [SQL Server], working with NUMA
- CPU [SQL Server], NUMA support
- NUMA, How to map a port to a NUMA node
- NUMA affinity
- TCP/IP [SQL Server], NUMA support
- non-uniform memory access
ms.assetid: 07727642-0266-4cbc-8c55-3c367e4458ca
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf4a1bd7e02719d3884011ad3faa20a1ccc6466a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744304"
---
# <a name="map-tcp-ip-ports-to-numa-nodes-sql-server"></a><span data-ttu-id="636d5-102">Asignación de puertos TCP/IP a nodos NUMA (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="636d5-102">Map TCP IP Ports to NUMA Nodes (SQL Server)</span></span>
  <span data-ttu-id="636d5-103">En este tema se describe cómo asignar puertos TCP/IP a los nodos de acceso a memoria no uniforme (NUMA) mediante el Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="636d5-103">This topic describes how to map TCP/IP ports to non-uniform memory access (NUMA) nodes by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="636d5-104">Durante el inicio, el [!INCLUDE[ssDE](../../includes/ssde-md.md)] escribe la información del nodo en el registro de errores.</span><span class="sxs-lookup"><span data-stu-id="636d5-104">On startup, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] writes the node information to the error log.</span></span>  
  
 <span data-ttu-id="636d5-105">Para determinar el número de nodo correspondiente al nodo que quiere usar, lea la información del nodo en el registro de errores o en la vista **sys.dm_os_schedulers** .</span><span class="sxs-lookup"><span data-stu-id="636d5-105">To determine the node number of the node you want to use, either read the node information from the error log, or from the **sys.dm_os_schedulers** view.</span></span> <span data-ttu-id="636d5-106">Para asignar una dirección y un puerto TCP/IP a uno o a varios nodos, adjunte un mapa de bits de identificación del nodo (una máscara de afinidad) entre paréntesis después del número de puerto.</span><span class="sxs-lookup"><span data-stu-id="636d5-106">To set a TCP/IP address and port to single or multiple nodes, append a node identification bitmap (an affinity mask) in brackets after the port number.</span></span> <span data-ttu-id="636d5-107">Los nodos se pueden especificar en formato decimal o hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="636d5-107">Nodes can be specified in either decimal or hexadecimal format.</span></span> <span data-ttu-id="636d5-108">Para crear el mapa de bits, primero numere los nodos de derecha a izquierda empezando por cero, como en 76543210.</span><span class="sxs-lookup"><span data-stu-id="636d5-108">To create the bitmap, first number the nodes from right to left starting with zero, as in 76543210.</span></span> <span data-ttu-id="636d5-109">Cree una representación binaria de la lista de nodos, especificando 1 para los nodos que desee usar y 0 para los que no vaya a utilizar.</span><span class="sxs-lookup"><span data-stu-id="636d5-109">Create a binary representation of the node list, providing 1 for nodes you want to use, and 0 for nodes you do not want to use.</span></span> <span data-ttu-id="636d5-110">Por ejemplo, para usar los nodos NUMA 0, 2 y 5, deberá especificar 00100101.</span><span class="sxs-lookup"><span data-stu-id="636d5-110">For example, to use NUMA nodes 0, 2, and 5, specify 00100101.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="636d5-111">Número de nodo NUMA</span><span class="sxs-lookup"><span data-stu-id="636d5-111">NUMA node number</span></span>|<span data-ttu-id="636d5-112">76543210</span><span class="sxs-lookup"><span data-stu-id="636d5-112">76543210</span></span>|  
|<span data-ttu-id="636d5-113">Máscara para 0, 2 y 5 contando desde la derecha</span><span class="sxs-lookup"><span data-stu-id="636d5-113">Mask for 0, 2, and 5 counting from right</span></span>|<span data-ttu-id="636d5-114">00100101</span><span class="sxs-lookup"><span data-stu-id="636d5-114">00100101</span></span>|  
  
 <span data-ttu-id="636d5-115">Convierta la representación binaria (00100101) en decimal `[37]`o en hexadecimal `[0x25]`.</span><span class="sxs-lookup"><span data-stu-id="636d5-115">Convert the binary representation (00100101), into decimal `[37]`, or hexadecimal `[0x25]`.</span></span> <span data-ttu-id="636d5-116">Para escuchar en todos los nodos, no especifique ningún identificador de nodo.</span><span class="sxs-lookup"><span data-stu-id="636d5-116">To listen on all nodes, provide no node identifier.</span></span>  
  
 <span data-ttu-id="636d5-117">Si un puerto está asignado a varios nodos NUMA, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asigna conexiones a los nodos por turnos sin intentar equilibrar la carga entre los nodos.</span><span class="sxs-lookup"><span data-stu-id="636d5-117">If a port is mapped to more than one NUMA node, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] assigns connections to nodes in a round-robin fashion without attempting to balance load across the nodes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="636d5-118">Para habilitar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de modo que escuche en varios puertos TCP para cada dirección IP, vea [Configurar el motor de base de datos para escuchar en varios puertos TCP](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md).</span><span class="sxs-lookup"><span data-stu-id="636d5-118">To enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to listen on multiple TCP ports for each IP address, see [Configure the Database Engine to Listen on Multiple TCP Ports](configure-the-database-engine-to-listen-on-multiple-tcp-ports.md).</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="636d5-119">Usar el Administrador de configuración de SQL Server</span><span class="sxs-lookup"><span data-stu-id="636d5-119">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-map-a-tcpip-port-to-a-numa-node"></a><span data-ttu-id="636d5-120">Para asignar un puerto TCP/IP a un nodo NUMA</span><span class="sxs-lookup"><span data-stu-id="636d5-120">To map a TCP/IP port to a NUMA node</span></span>  
  
1.  <span data-ttu-id="636d5-121">En Configuration Manager de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], expanda **Configuración de red de SQL Server** y, después, haga clic en **Protocolos de** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="636d5-121">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Network Configuration**, and then click **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="636d5-122">En el panel de detalles, haga doble clic en **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="636d5-122">In the details pane, double-click **TCP/IP**.</span></span>  
  
3.  <span data-ttu-id="636d5-123">En la pestaña **Direcciones IP** , en la sección correspondiente a la dirección IP que se va a configurar, en el cuadro **Puerto TCP** , agregue el identificador del nodo NUMA entre paréntesis a continuación del número de puerto.</span><span class="sxs-lookup"><span data-stu-id="636d5-123">On the **IP Addresses** tab, in the section corresponding to the IP address to configure, in the **TCP Port** box, add the NUMA node identifier in brackets after the port number.</span></span> <span data-ttu-id="636d5-124">Por ejemplo, para el puerto TCP 1500 y los nodos 0, 2 y 5, utilice `1500[37]` o `1500[0x25]`.</span><span class="sxs-lookup"><span data-stu-id="636d5-124">For example, for TCP port 1500 and nodes 0, 2, and 5, use `1500[37]`, or `1500[0x25]`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="636d5-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="636d5-125">See Also</span></span>  
 [<span data-ttu-id="636d5-126">Configure SQL Server para usar &#40;de Soft-NUMA SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="636d5-126">Configure SQL Server to Use Soft-NUMA &#40;SQL Server&#41;</span></span>](soft-numa-sql-server.md)  
  
  
