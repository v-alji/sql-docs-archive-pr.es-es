---
title: MSSQLSERVER_10060 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10060"
helpviewer_keywords:
- 10060 (Database Engine error)
ms.assetid: 28c21277-cad8-406c-a955-07933a56982a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d634cfb06381fb916ef2e421e0677e76edb9ae02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748814"
---
# <a name="mssqlserver_10060"></a><span data-ttu-id="3c8ae-102">MSSQLSERVER_10060</span><span class="sxs-lookup"><span data-stu-id="3c8ae-102">MSSQLSERVER_10060</span></span>
    
## <a name="details"></a><span data-ttu-id="3c8ae-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="3c8ae-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c8ae-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="3c8ae-104">Product Name</span></span>|<span data-ttu-id="3c8ae-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3c8ae-105">SQL Server</span></span>|  
|<span data-ttu-id="3c8ae-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="3c8ae-106">Event ID</span></span>|<span data-ttu-id="3c8ae-107">10060</span><span class="sxs-lookup"><span data-stu-id="3c8ae-107">10060</span></span>|  
|<span data-ttu-id="3c8ae-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="3c8ae-108">Event Source</span></span>|<span data-ttu-id="3c8ae-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3c8ae-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3c8ae-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3c8ae-110">Component</span></span>|<span data-ttu-id="3c8ae-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3c8ae-111">SQLEngine</span></span>|  
|<span data-ttu-id="3c8ae-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3c8ae-112">Symbolic Name</span></span>||  
|<span data-ttu-id="3c8ae-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3c8ae-113">Message Text</span></span>|<span data-ttu-id="3c8ae-114">Error al establecer una conexión al servidor.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="3c8ae-115">La causa del problema en la conexión a SQL Server puede deberse a que SQL Server no permite conexiones remotas en su configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="3c8ae-116">(proveedor: Proveedor TCP, error: 0 - Se produjo un error durante el intento de conexión ya que la parte conectada no respondió adecuadamente tras un periodo de tiempo, o bien se produjo un error en la conexión establecida ya que el host conectado no ha podido responder). (Microsoft SQL Server, Error: 10060)</span><span class="sxs-lookup"><span data-stu-id="3c8ae-116">(provider: TCP Provider, error: 0 - A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond.) (Microsoft SQL Server, Error: 10060)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3c8ae-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="3c8ae-117">Explanation</span></span>  
 <span data-ttu-id="3c8ae-118">El cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se puede conectar al servidor.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="3c8ae-119">Este error se puede producir porque el firewall en el servidor ha rechazado la conexión o el servidor no está configurado para aceptar conexiones remotas.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-119">This error could occur because either the firewall on the server has refused the connection or the server is not configured to accept remote connections.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3c8ae-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3c8ae-120">User Action</span></span>  
 <span data-ttu-id="3c8ae-121">Para resolver este error, intente una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="3c8ae-121">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="3c8ae-122">Asegúrese de haber configurado el firewall en el equipo de modo que esta instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] acepte conexiones.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-122">Make sure that you have configured the firewall on the computer to allow this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
-   <span data-ttu-id="3c8ae-123">Use la herramienta Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] acepte conexiones remotas.</span><span class="sxs-lookup"><span data-stu-id="3c8ae-123">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to allow [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c8ae-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c8ae-124">See Also</span></span>  
 <span data-ttu-id="3c8ae-125">[Configurar un firewall de Windows para el acceso a Motor de base de datos](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="3c8ae-125">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="3c8ae-126">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="3c8ae-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="3c8ae-127">[Protocolos de red y bibliotecas de red](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="3c8ae-127">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="3c8ae-128">[Configuración de red de cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="3c8ae-128">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="3c8ae-129">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="3c8ae-129">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="3c8ae-130">Habilitar o deshabilitar un protocolo de red de servidor</span><span class="sxs-lookup"><span data-stu-id="3c8ae-130">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
