---
title: MSSQLSERVER_-1 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "-1"
helpviewer_keywords:
- -1 (Database Engine error)
ms.assetid: bad25b91-eaed-46c0-a5b7-71117a32304c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 880212b1d2e9572bbb31535a5ba68b445c7e6f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747601"
---
# <a name="mssqlserver_-1"></a><span data-ttu-id="59132-102">MSSQLSERVER_-1</span><span class="sxs-lookup"><span data-stu-id="59132-102">MSSQLSERVER_-1</span></span>
    
## <a name="details"></a><span data-ttu-id="59132-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="59132-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59132-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="59132-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="59132-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="59132-105">Event ID</span></span>|<span data-ttu-id="59132-106">-1</span><span class="sxs-lookup"><span data-stu-id="59132-106">-1</span></span>|  
|<span data-ttu-id="59132-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="59132-107">Event Source</span></span>|<span data-ttu-id="59132-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="59132-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="59132-109">Componente</span><span class="sxs-lookup"><span data-stu-id="59132-109">Component</span></span>|<span data-ttu-id="59132-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="59132-110">SQLEngine</span></span>|  
|<span data-ttu-id="59132-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="59132-111">Symbolic Name</span></span>||  
|<span data-ttu-id="59132-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="59132-112">Message Text</span></span>|<span data-ttu-id="59132-113">Error al establecer una conexión al servidor.</span><span class="sxs-lookup"><span data-stu-id="59132-113">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="59132-114">Cuando se conecta con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o con versiones posteriores, la configuración predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no permite conexiones remotas.</span><span class="sxs-lookup"><span data-stu-id="59132-114">When connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this failure may be caused by the fact that under the default settings [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not allow remote connections.</span></span> <span data-ttu-id="59132-115">(proveedor: Interfaces de red de SQL; error: 28 - el servidor no admite el protocolo requerido) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], error: -1)</span><span class="sxs-lookup"><span data-stu-id="59132-115">(provider: SQL Network Interfaces, error: 28 - Server doesn't support requested protocol) (Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Error: -1)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="59132-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="59132-116">Explanation</span></span>  
 <span data-ttu-id="59132-117">El cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se puede conectar al servidor.</span><span class="sxs-lookup"><span data-stu-id="59132-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="59132-118">Este error podría deberse a uno de los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="59132-118">This error could be caused by one of the following reasons:</span></span>  
  
-   <span data-ttu-id="59132-119">El nombre de instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] especificado no es válido.</span><span class="sxs-lookup"><span data-stu-id="59132-119">A specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name is not valid.</span></span>  
  
-   <span data-ttu-id="59132-120">Los protocolos de canalizaciones con nombre o TCP no están habilitados.</span><span class="sxs-lookup"><span data-stu-id="59132-120">The TCP, or named pipes protocols are not enabled.</span></span>  
  
-   <span data-ttu-id="59132-121">El firewall en el servidor ha rechazado la conexión.</span><span class="sxs-lookup"><span data-stu-id="59132-121">The firewall on the server has refused the connection.</span></span>  
  
-   <span data-ttu-id="59132-122">El servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser (sqlbrowser) no se inició.</span><span class="sxs-lookup"><span data-stu-id="59132-122">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service (sqlbrowser) is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="59132-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="59132-123">User Action</span></span>  
 <span data-ttu-id="59132-124">Para resolver este error, intente una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="59132-124">To resolve this error, try one of the following actions:</span></span>  
  
-   <span data-ttu-id="59132-125">Compruebe la ortografía del nombre de instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se especifica en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="59132-125">Check the spelling of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name that is specified in the connection string.</span></span>  
  
-   <span data-ttu-id="59132-126">Use la herramienta Administrador de configuración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para habilitar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y aceptar las conexiones remotas a través de los protocolos de canalizaciones con nombre o TCP.</span><span class="sxs-lookup"><span data-stu-id="59132-126">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager tool to enable [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept remote connections over the TCP or named pipes protocols.</span></span>  
  
-   <span data-ttu-id="59132-127">Asegúrese de que ha configurado el firewall en la instancia de servidor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para abrir los puertos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el puerto de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser (UDP 1434).</span><span class="sxs-lookup"><span data-stu-id="59132-127">Make sure that you have configured the firewall on the server instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to open ports for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser port (UDP 1434).</span></span>  
  
-   <span data-ttu-id="59132-128">Asegúrese de que el servicio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser se inició en el servidor.</span><span class="sxs-lookup"><span data-stu-id="59132-128">Make sure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service is started on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59132-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59132-129">See Also</span></span>  
 <span data-ttu-id="59132-130">[Configurar un firewall de Windows para el acceso a Motor de base de datos](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span><span class="sxs-lookup"><span data-stu-id="59132-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md) </span></span>  
 <span data-ttu-id="59132-131">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="59132-131">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="59132-132">[Protocolos de red y bibliotecas de red](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="59132-132">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="59132-133">[Configuración de red de cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="59132-133">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="59132-134">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="59132-134">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="59132-135">Habilitar o deshabilitar un protocolo de red de servidor</span><span class="sxs-lookup"><span data-stu-id="59132-135">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
