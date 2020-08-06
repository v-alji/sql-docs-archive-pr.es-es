---
title: Ejecutar SQL Server con o sin red | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- verifying Server service has been started
- net start [SQL Server]
- command prompt [SQL Server], connections
- SQL Server services, networks
- status information [SQL Server], Server service
- running SQL Server
- networking [SQL Server], SQL Server with or without
- services [SQL Server], networks
- starting Server service
- SQL Server, running
ms.assetid: 54eac961-5c7a-4481-982d-f93a64b5c2f4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a80e7e4d42f322bc42d0c67c57e3a1f9bddb87a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673262"
---
# <a name="run-sql-server-with-or-without-a-network"></a><span data-ttu-id="7374b-102">Ejecutar SQL Server con o sin red</span><span class="sxs-lookup"><span data-stu-id="7374b-102">Run SQL Server With or Without a Network</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="7374b-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se puede ejecutar en una red o puede funcionar sin ella.</span><span class="sxs-lookup"><span data-stu-id="7374b-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can run on a network, or it can function without a network.</span></span>  
  
## <a name="running-sql-server-on-a-network"></a><span data-ttu-id="7374b-104">Ejecutar SQL Server en una red</span><span class="sxs-lookup"><span data-stu-id="7374b-104">Running SQL Server on a Network</span></span>  
 <span data-ttu-id="7374b-105">Para que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueda comunicarse a través de una red, el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debe estar en ejecución.</span><span class="sxs-lookup"><span data-stu-id="7374b-105">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to communicate over a network, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service must be running.</span></span> <span data-ttu-id="7374b-106">De forma predeterminada, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows inicia automáticamente el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integrado.</span><span class="sxs-lookup"><span data-stu-id="7374b-106">By default, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows automatically starts the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="7374b-107">Para averiguar si se ha iniciado el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , en el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="7374b-107">To find out whether the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has been started, at the command prompt, type the following:</span></span>  
  
 <span data-ttu-id="7374b-108">**net start**</span><span class="sxs-lookup"><span data-stu-id="7374b-108">**net start**</span></span>  
  
 <span data-ttu-id="7374b-109">Si los servicios asociados con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se han iniciado, los siguientes servicios aparecerán en la salida del comando **net start** :</span><span class="sxs-lookup"><span data-stu-id="7374b-109">If the services associated with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] have been started, the following services will appear in the **net start** output:</span></span>  
  
-   <span data-ttu-id="7374b-110">Analysis Services (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="7374b-110">Analysis Services (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="7374b-111">SQL Server (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="7374b-111">SQL Server (MSSQLSERVER)</span></span>  
  
-   <span data-ttu-id="7374b-112">Agente SQL Server (MSSQLSERVER)</span><span class="sxs-lookup"><span data-stu-id="7374b-112">SQL Server Agent (MSSQLSERVER)</span></span>  
  
## <a name="running-sql-server-without-a-network"></a><span data-ttu-id="7374b-113">Ejecutar SQL Server sin una red</span><span class="sxs-lookup"><span data-stu-id="7374b-113">Running SQL Server Without a Network</span></span>  
 <span data-ttu-id="7374b-114">Cuando se ejecuta una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sin una red, no es necesario iniciar el servicio integrado [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7374b-114">When running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without a network, you do not need to start the built-in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="7374b-115">Puesto que [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], el Administrador de configuración de SQL Server y los comandos **net start** y **net stop** funcionan siempre, incluso sin una red, los procedimientos para iniciar y detener una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] son los mismos para el funcionamiento independiente o con red.</span><span class="sxs-lookup"><span data-stu-id="7374b-115">Because [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], SQL Server Configuration Manager, and the **net start** and **net stop** commands are functional even without a network, the procedures for starting and stopping an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are identical for a network or stand-alone operation.</span></span>  
  
 <span data-ttu-id="7374b-116">Al conectarse a una instancia de un servidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] independiente desde un cliente local, por ejemplo **sqlcmd**, se omite la red y se conecta directamente a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante una canalización local.</span><span class="sxs-lookup"><span data-stu-id="7374b-116">When connecting to an instance of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a local client such as **sqlcmd**, you bypass the network and connect directly to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a local pipe.</span></span> <span data-ttu-id="7374b-117">La diferencia entre una canalización local y una canalización de red es que en la primera no se utiliza la red y en la segunda sí.</span><span class="sxs-lookup"><span data-stu-id="7374b-117">The difference between a local pipe and a network pipe is whether you are using a network.</span></span> <span data-ttu-id="7374b-118">Ambas canalizaciones establecen una conexión con una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante la canalización estándar (\\\\.\pipe\sql\query), a menos que se indique otra cosa.</span><span class="sxs-lookup"><span data-stu-id="7374b-118">Both local and network pipes establish a connection with an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the standard pipe (\\\\.\pipe\sql\query), unless otherwise directed.</span></span>  
  
 <span data-ttu-id="7374b-119">Cuando se conecta a una instancia de un servidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] local sin especificar un nombre de servidor, se utiliza una canalización local.</span><span class="sxs-lookup"><span data-stu-id="7374b-119">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without specifying a server name, you are using a local pipe.</span></span> <span data-ttu-id="7374b-120">Si se conecta a una instancia de un servidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] local y se especifica explícitamente un nombre de servidor, se utiliza una canalización de red u otro mecanismo de comunicación entre procesos (IPC) de red, como IPX/SPX, suponiendo que se haya configurado [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para utilizar varias redes.</span><span class="sxs-lookup"><span data-stu-id="7374b-120">When you connect to an instance of a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and specify a server name explicitly, you are using either a network pipe or another network interprocess communication (IPC) mechanism, such as Internetwork Packet Exchange/Sequenced Packet Exchange (IPX/SPX) (assuming you have configured [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use multiple networks).</span></span> <span data-ttu-id="7374b-121">Como un servidor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] independiente no admite canalizaciones de red, debe omitir el argumento **/** _<nombre_servidor>_ , que resulta innecesario, cuando se conecte a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde un cliente.</span><span class="sxs-lookup"><span data-stu-id="7374b-121">Because a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support network pipes, you must omit the unnecessary **/**_<Server_name>_ argument when connecting to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client.</span></span> <span data-ttu-id="7374b-122">Por ejemplo, para conectarse a una instancia independiente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde **osql**, escriba:</span><span class="sxs-lookup"><span data-stu-id="7374b-122">For example, to connect to a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from **osql**, type:</span></span>  
  
 <span data-ttu-id="7374b-123">**osql /Usa /P** _\<saPassword>_</span><span class="sxs-lookup"><span data-stu-id="7374b-123">**osql /Usa /P** _\<saPassword>_</span></span>  
  
  
