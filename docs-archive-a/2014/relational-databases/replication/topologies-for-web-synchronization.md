---
title: Topologías para sincronización web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Web synchronization, topologies
- IIS server configuration [SQL Server replication]
ms.assetid: 59444faf-bcb6-4421-a3df-8715753e453b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5e28ca5a222e2286d154c16ef41d3147dc56e25a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673637"
---
# <a name="topologies-for-web-synchronization"></a><span data-ttu-id="ea65c-102">Topologies for Web Synchronization</span><span class="sxs-lookup"><span data-stu-id="ea65c-102">Topologies for Web Synchronization</span></span>
  <span data-ttu-id="ea65c-103">Puede elegir entre una serie de topologías de replicación de sincronización web de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea65c-103">You can choose from a variety of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Web synchronization replication topologies.</span></span> <span data-ttu-id="ea65c-104">Entre las maneras habituales de configurar una sincronización web se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ea65c-104">Common ways to configure Web synchronization include:</span></span>  
  
-   <span data-ttu-id="ea65c-105">Servidor único</span><span class="sxs-lookup"><span data-stu-id="ea65c-105">Single server</span></span>  
  
-   <span data-ttu-id="ea65c-106">Dos servidores</span><span class="sxs-lookup"><span data-stu-id="ea65c-106">Two servers</span></span>  
  
-   <span data-ttu-id="ea65c-107">Varios sistemas con [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) y republicación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea65c-107">Multiple [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) systems and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] republishing</span></span>  
  
 <span data-ttu-id="ea65c-108">Para más información sobre cómo configurar la sincronización web, vea [Configurar la sincronización web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="ea65c-108">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="single-server"></a><span data-ttu-id="ea65c-109">Servidor único</span><span class="sxs-lookup"><span data-stu-id="ea65c-109">Single Server</span></span>  
 <span data-ttu-id="ea65c-110">En la topología más sencilla, IIS, el publicador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el distribuidor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] residen en un único servidor.</span><span class="sxs-lookup"><span data-stu-id="ea65c-110">In the simplest topology, IIS, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher, and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor all reside on a single server.</span></span> <span data-ttu-id="ea65c-111">Los suscriptores se sincronizan conectándose a IIS en el publicador.</span><span class="sxs-lookup"><span data-stu-id="ea65c-111">Subscribers synchronize by connecting to IIS on the Publisher.</span></span> <span data-ttu-id="ea65c-112">El publicador puede estar situado detrás de un firewall.</span><span class="sxs-lookup"><span data-stu-id="ea65c-112">The Publisher can be located behind a firewall.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea65c-113">Esta configuración se recomienda solo para intranet.</span><span class="sxs-lookup"><span data-stu-id="ea65c-113">This configuration is recommended only for intranet scenarios.</span></span> <span data-ttu-id="ea65c-114">En el resto de las situaciones, se recomienda que el servidor IIS y el distribuidor o publicador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estén en equipos independientes.</span><span class="sxs-lookup"><span data-stu-id="ea65c-114">For other scenarios, it is recommended that the IIS server and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher/Distributor be on separate computers.</span></span>  
  
 <span data-ttu-id="ea65c-115">![Sincronización web con un solo servidor](media/web-sync02.gif "Sincronización web con un solo servidor")</span><span class="sxs-lookup"><span data-stu-id="ea65c-115">![Web synchronization with a single server](media/web-sync02.gif "Web synchronization with a single server")</span></span>  
  
## <a name="two-servers"></a><span data-ttu-id="ea65c-116">Dos servidores</span><span class="sxs-lookup"><span data-stu-id="ea65c-116">Two Servers</span></span>  
 <span data-ttu-id="ea65c-117">Se puede colocar IIS en un servidor y configurar el publicador y el distribuidor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en otro distinto.</span><span class="sxs-lookup"><span data-stu-id="ea65c-117">You can place IIS on one server and configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher and Distributor on another server.</span></span> <span data-ttu-id="ea65c-118">El servidor en el que se ejecuta IIS puede aislarse de Internet mediante un firewall.</span><span class="sxs-lookup"><span data-stu-id="ea65c-118">The server running IIS can be isolated from the Internet by a firewall.</span></span> <span data-ttu-id="ea65c-119">Los suscriptores se sincronizan conectándose a IIS.</span><span class="sxs-lookup"><span data-stu-id="ea65c-119">Subscribers synchronize by connecting to IIS.</span></span>  
  
 <span data-ttu-id="ea65c-120">![Sincronización web con dos servidores](media/web-sync03.gif "Sincronización web con dos servidores")</span><span class="sxs-lookup"><span data-stu-id="ea65c-120">![Web synchronization with two servers](media/web-sync03.gif "Web synchronization with two servers")</span></span>  
  
## <a name="multiple-iis-systems-and-sql-server-republishing"></a><span data-ttu-id="ea65c-121">Varios sistemas IIS y republicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="ea65c-121">Multiple IIS Systems and SQL Server Republishing</span></span>  
 <span data-ttu-id="ea65c-122">Si dispone de un gran número de suscriptores que se sincronizan al mismo tiempo, puede dividir el trabajo entre varios equipos que ejecuten IIS.</span><span class="sxs-lookup"><span data-stu-id="ea65c-122">If you need to support very large numbers of Subscribers that synchronize at the same time, you can partition the work across multiple computers running IIS.</span></span>  
  
 <span data-ttu-id="ea65c-123">![Sincronización web con varios servidores IIS](media/web-sync04.gif "Sincronización web con varios servidores IIS")</span><span class="sxs-lookup"><span data-stu-id="ea65c-123">![Web synchronization with multiple IIS servers](media/web-sync04.gif "Web synchronization with multiple IIS servers")</span></span>  
  
 <span data-ttu-id="ea65c-124">Si necesita mayor equilibrio de carga en el equipo en el que se ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], puede crear una jerarquía de republicación en varios equipos.</span><span class="sxs-lookup"><span data-stu-id="ea65c-124">If further load balancing is required on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can create a republishing hierarchy on multiple computers.</span></span> <span data-ttu-id="ea65c-125">El publicador de más alto nivel publica datos en los suscriptores, que a su vez los vuelven a publicar, con lo que se equilibra la carga de las solicitudes de los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="ea65c-125">The top-level Publisher publishes data to Subscribers, which in turn republish the data, load balancing requests from the Subscribers.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ea65c-126">Los suscriptores solo pueden sincronizarse con un publicador específico.</span><span class="sxs-lookup"><span data-stu-id="ea65c-126">Subscribers can only synchronize with a specific Publisher.</span></span> <span data-ttu-id="ea65c-127">Por ejemplo, un suscriptor a un republicador A no puede sincronizarse con el republicador B si A no está disponible.</span><span class="sxs-lookup"><span data-stu-id="ea65c-127">For example, a Subscriber to republisher A cannot synchronize with republisher B when A is not available.</span></span>  
  
 <span data-ttu-id="ea65c-128">![Sincronización web con nueva publicación](media/web-sync05.gif "Sincronización web con nueva publicación")</span><span class="sxs-lookup"><span data-stu-id="ea65c-128">![Web synchronization with republishing](media/web-sync05.gif "Web synchronization with republishing")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea65c-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea65c-129">See Also</span></span>  
 <span data-ttu-id="ea65c-130">[Configurar sincronización web](configure-web-synchronization.md) </span><span class="sxs-lookup"><span data-stu-id="ea65c-130">[Configure Web Synchronization](configure-web-synchronization.md) </span></span>  
 [<span data-ttu-id="ea65c-131">Sincronización web para la replicación de mezcla</span><span class="sxs-lookup"><span data-stu-id="ea65c-131">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
