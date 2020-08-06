---
title: MSSQLSERVER_10061 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "10061"
helpviewer_keywords:
- 10061 (Database Engine error)
ms.assetid: 729602f3-08df-474c-8740-8dea13c1eee3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0c866bd8dce01f65036f1d508a94252a97613424
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747598"
---
# <a name="mssqlserver_10061"></a><span data-ttu-id="b1146-102">MSSQLSERVER_10061</span><span class="sxs-lookup"><span data-stu-id="b1146-102">MSSQLSERVER_10061</span></span>
    
## <a name="details"></a><span data-ttu-id="b1146-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b1146-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1146-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="b1146-104">Product Name</span></span>|<span data-ttu-id="b1146-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b1146-105">SQL Server</span></span>|  
|<span data-ttu-id="b1146-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b1146-106">Event ID</span></span>|<span data-ttu-id="b1146-107">10061</span><span class="sxs-lookup"><span data-stu-id="b1146-107">10061</span></span>|  
|<span data-ttu-id="b1146-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="b1146-108">Event Source</span></span>|<span data-ttu-id="b1146-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b1146-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b1146-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b1146-110">Component</span></span>|<span data-ttu-id="b1146-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b1146-111">SQLEngine</span></span>|  
|<span data-ttu-id="b1146-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b1146-112">Symbolic Name</span></span>||  
|<span data-ttu-id="b1146-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b1146-113">Message Text</span></span>|<span data-ttu-id="b1146-114">Error al establecer una conexión al servidor.</span><span class="sxs-lookup"><span data-stu-id="b1146-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="b1146-115">La causa del problema en la conexión a SQL Server puede deberse a que SQL Server no permite conexiones remotas en su configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b1146-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="b1146-116">(proveedor: Proveedor TCP, error: 0 - No se estableció ninguna conexión porque el equipo de destino la rechazó). (Microsoft SQL Server, Error: 10061)</span><span class="sxs-lookup"><span data-stu-id="b1146-116">(provider: TCP Provider, error: 0 - No connection could be made because the target machine actively refused it.) (Microsoft SQL Server, Error: 10061)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b1146-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="b1146-117">Explanation</span></span>  
 <span data-ttu-id="b1146-118">El servidor no respondió a la solicitud del cliente.</span><span class="sxs-lookup"><span data-stu-id="b1146-118">The server did not respond to the client request.</span></span> <span data-ttu-id="b1146-119">Este error puede producirse porque el servidor no se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="b1146-119">This error could occur because the server is not started.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b1146-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b1146-120">User Action</span></span>  
 <span data-ttu-id="b1146-121">Asegúrese de que el servidor se haya iniciado.</span><span class="sxs-lookup"><span data-stu-id="b1146-121">Make sure that the server is started.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1146-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b1146-122">See Also</span></span>  
 <span data-ttu-id="b1146-123">[Administrar el servicio del motor de base de datos](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span><span class="sxs-lookup"><span data-stu-id="b1146-123">[Manage the Database Engine Services](../../database-engine/configure-windows/manage-the-database-engine-services.md) </span></span>  
 <span data-ttu-id="b1146-124">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="b1146-124">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 <span data-ttu-id="b1146-125">[Protocolos de red y bibliotecas de red](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="b1146-125">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="b1146-126">[Configuración de red de cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="b1146-126">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="b1146-127">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="b1146-127">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="b1146-128">Habilitar o deshabilitar un protocolo de red de servidor</span><span class="sxs-lookup"><span data-stu-id="b1146-128">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
