---
title: MSSQLSERVER_-2 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- -2 (Database Engine error)
ms.assetid: f37a7b7d-26e1-4b9e-bcb4-57f7805393d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d39b4a11387a60056bba3f87adffcb2653b60f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746302"
---
# <a name="mssqlserver_-2"></a><span data-ttu-id="80b93-102">MSSQLSERVER_-2</span><span class="sxs-lookup"><span data-stu-id="80b93-102">MSSQLSERVER_-2</span></span>
    
## <a name="details"></a><span data-ttu-id="80b93-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="80b93-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="80b93-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="80b93-104">Product Name</span></span>|<span data-ttu-id="80b93-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="80b93-105">SQL Server</span></span>|  
|<span data-ttu-id="80b93-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="80b93-106">Event ID</span></span>|<span data-ttu-id="80b93-107">-2</span><span class="sxs-lookup"><span data-stu-id="80b93-107">-2</span></span>|  
|<span data-ttu-id="80b93-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="80b93-108">Event Source</span></span>|<span data-ttu-id="80b93-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="80b93-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="80b93-110">Componente</span><span class="sxs-lookup"><span data-stu-id="80b93-110">Component</span></span>|<span data-ttu-id="80b93-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="80b93-111">SQLEngine</span></span>|  
|<span data-ttu-id="80b93-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="80b93-112">Symbolic Name</span></span>||  
|<span data-ttu-id="80b93-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="80b93-113">Message Text</span></span>|<span data-ttu-id="80b93-114">Tiempo de espera agotado.</span><span class="sxs-lookup"><span data-stu-id="80b93-114">Timeout expired.</span></span>  <span data-ttu-id="80b93-115">El tiempo de espera transcurrió antes de que se completase la operación, o bien el servidor no responde.</span><span class="sxs-lookup"><span data-stu-id="80b93-115">The timeout period elapsed prior to completion of the operation or the server is not responding.</span></span> <span data-ttu-id="80b93-116">(Microsoft SQL Server, Error: -2)</span><span class="sxs-lookup"><span data-stu-id="80b93-116">(Microsoft SQL Server, Error: -2)</span></span>|   
  
## <a name="explanation"></a><span data-ttu-id="80b93-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="80b93-117">Explanation</span></span>  
 <span data-ttu-id="80b93-118">El cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se puede conectar al servidor.</span><span class="sxs-lookup"><span data-stu-id="80b93-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="80b93-119">Este error puede producirse porque el firewall en el servidor ha rechazado la conexión.</span><span class="sxs-lookup"><span data-stu-id="80b93-119">This error could occur because the firewall on the server has refused the connection.</span></span> 
  
## <a name="user-action"></a><span data-ttu-id="80b93-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="80b93-120">User Action</span></span>  
 <span data-ttu-id="80b93-121">Asegúrese de haber configurado el firewall en la instancia del servidor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para aceptar las conexiones.</span><span class="sxs-lookup"><span data-stu-id="80b93-121">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b93-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80b93-122">See Also</span></span>  
 <span data-ttu-id="80b93-123">[Configurar el Firewall de Windows para permitir el acceso a SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span><span class="sxs-lookup"><span data-stu-id="80b93-123">[Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md) </span></span>  
 <span data-ttu-id="80b93-124">[Configurar un firewall de Windows para el acceso a Motor de base de datos](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="80b93-124">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="80b93-125">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="80b93-125">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="80b93-126">[Protocolos de red y bibliotecas de red](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="80b93-126">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="80b93-127">[Configuración de red de cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="80b93-127">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="80b93-128">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="80b93-128">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="80b93-129">Habilitar o deshabilitar un protocolo de red de servidor</span><span class="sxs-lookup"><span data-stu-id="80b93-129">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
