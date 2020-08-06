---
title: MSSQLSERVER_2 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "2"
helpviewer_keywords:
- 2 (Database Engine error)
ms.assetid: 567fb571-7cda-4ce8-a702-cdff2df5d419
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 87d19a24219fda79de2cad4c06af4f1936b37b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675921"
---
# <a name="mssqlserver_2"></a><span data-ttu-id="0b7a0-102">MSSQLSERVER_2</span><span class="sxs-lookup"><span data-stu-id="0b7a0-102">MSSQLSERVER_2</span></span>
    
## <a name="details"></a><span data-ttu-id="0b7a0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0b7a0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b7a0-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="0b7a0-104">Product Name</span></span>|<span data-ttu-id="0b7a0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0b7a0-105">SQL Server</span></span>|  
|<span data-ttu-id="0b7a0-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="0b7a0-106">Event ID</span></span>|<span data-ttu-id="0b7a0-107">2</span><span class="sxs-lookup"><span data-stu-id="0b7a0-107">2</span></span>|  
|<span data-ttu-id="0b7a0-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="0b7a0-108">Event Source</span></span>|<span data-ttu-id="0b7a0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0b7a0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0b7a0-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0b7a0-110">Component</span></span>|<span data-ttu-id="0b7a0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0b7a0-111">SQLEngine</span></span>|  
|<span data-ttu-id="0b7a0-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0b7a0-112">Symbolic Name</span></span>||  
|<span data-ttu-id="0b7a0-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0b7a0-113">Message Text</span></span>|<span data-ttu-id="0b7a0-114">Error al establecer una conexión al servidor.</span><span class="sxs-lookup"><span data-stu-id="0b7a0-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="0b7a0-115">La causa del problema en la conexión a SQL Server puede deberse a que SQL Server no permite conexiones remotas en su configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0b7a0-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="0b7a0-116">(proveedor: Proveedor de canalizaciones con nombre; error: 40 - No se pudo abrir la conexión con SQL Server) (Proveedor de datos SqlClient de .Net)</span><span class="sxs-lookup"><span data-stu-id="0b7a0-116">(provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0b7a0-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="0b7a0-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0b7a0-118">no respondió a la solicitud del cliente porque es probable que el servidor no se hubiera iniciado.</span><span class="sxs-lookup"><span data-stu-id="0b7a0-118">did not respond to the client request because the server is probably not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b7a0-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0b7a0-119">User Action</span></span>  
 <span data-ttu-id="0b7a0-120">Asegúrese de que el servidor se haya iniciado.</span><span class="sxs-lookup"><span data-stu-id="0b7a0-120">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b7a0-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0b7a0-121">See Also</span></span>  
 <span data-ttu-id="0b7a0-122">[Administrar el servicio del motor de base de datos](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="0b7a0-122">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="0b7a0-123">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="0b7a0-123">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="0b7a0-124">[Protocolos de red y bibliotecas de red](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="0b7a0-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="0b7a0-125">[Configuración de red de cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0b7a0-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="0b7a0-126">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="0b7a0-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="0b7a0-127">Habilitar o deshabilitar un protocolo de red de servidor</span><span class="sxs-lookup"><span data-stu-id="0b7a0-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
