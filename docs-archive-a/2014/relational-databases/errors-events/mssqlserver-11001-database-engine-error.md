---
title: MSSQLSERVER_11001 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "12001"
helpviewer_keywords:
- 11001 (Database Engine error)
ms.assetid: 53d4d63a-61e3-441f-bfe9-9d44f7a05fd4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: da7dd171d1b6a64e0cc1666eda1e3593a81eece1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675963"
---
# <a name="mssqlserver_11001"></a><span data-ttu-id="180c9-102">MSSQLSERVER_11001</span><span class="sxs-lookup"><span data-stu-id="180c9-102">MSSQLSERVER_11001</span></span>
    
## <a name="details"></a><span data-ttu-id="180c9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="180c9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="180c9-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="180c9-104">Product Name</span></span>|<span data-ttu-id="180c9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="180c9-105">SQL Server</span></span>|  
|<span data-ttu-id="180c9-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="180c9-106">Event ID</span></span>|<span data-ttu-id="180c9-107">11001</span><span class="sxs-lookup"><span data-stu-id="180c9-107">11001</span></span>|  
|<span data-ttu-id="180c9-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="180c9-108">Event Source</span></span>|<span data-ttu-id="180c9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="180c9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="180c9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="180c9-110">Component</span></span>|<span data-ttu-id="180c9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="180c9-111">SQLEngine</span></span>|  
|<span data-ttu-id="180c9-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="180c9-112">Symbolic Name</span></span>||  
|<span data-ttu-id="180c9-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="180c9-113">Message Text</span></span>|<span data-ttu-id="180c9-114">Error al establecer una conexión al servidor.</span><span class="sxs-lookup"><span data-stu-id="180c9-114">An error has occurred while establishing a connection to the server.</span></span>  <span data-ttu-id="180c9-115">La causa del problema en la conexión a SQL Server puede deberse a que SQL Server no permite conexiones remotas en su configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="180c9-115">When connecting to SQL Server, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.</span></span> <span data-ttu-id="180c9-116">(proveedor: Proveedor TCP, error: 0: Este host es desconocido). (Proveedor de datos SqlClient de .NET)</span><span class="sxs-lookup"><span data-stu-id="180c9-116">(provider: TCP Provider, error: 0 - No such host is known.) (.Net SqlClient Data Provider)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="180c9-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="180c9-117">Explanation</span></span>  
 <span data-ttu-id="180c9-118">El cliente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se puede conectar al servidor.</span><span class="sxs-lookup"><span data-stu-id="180c9-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client cannot connect to the server.</span></span> <span data-ttu-id="180c9-119">Este error se puede producir porque el cliente no puede resolver el nombre del servidor o porque el nombre del servidor no es correcto.</span><span class="sxs-lookup"><span data-stu-id="180c9-119">The error could occur because either the client cannot resolve the name of the server or the name of the server is incorrect.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="180c9-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="180c9-120">User Action</span></span>  
 <span data-ttu-id="180c9-121">Asegúrese de haber escrito correctamente el nombre del servidor en el cliente y que puede resolver el nombre del servidor desde el cliente.</span><span class="sxs-lookup"><span data-stu-id="180c9-121">Make sure that you have entered the correct server name on the client, and that you can resolve the name of the server from the client.</span></span> <span data-ttu-id="180c9-122">Para comprobar la resolución de nombres de TCP/IP, puede usar el comando **ping** en el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="180c9-122">To check TCP/IP name resolution, you can use the **ping** command in the Windows operating system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="180c9-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="180c9-123">See Also</span></span>  
 <span data-ttu-id="180c9-124">[Protocolos de red y bibliotecas de red](../../sql-server/install/network-protocols-and-network-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="180c9-124">[Network Protocols and Network Libraries](../../sql-server/install/network-protocols-and-network-libraries.md) </span></span>  
 <span data-ttu-id="180c9-125">[Configuración de red de cliente](../../database-engine/configure-windows/client-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="180c9-125">[Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md) </span></span>  
 <span data-ttu-id="180c9-126">[Configurar protocolos de cliente](../../database-engine/configure-windows/configure-client-protocols.md) </span><span class="sxs-lookup"><span data-stu-id="180c9-126">[Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md) </span></span>  
 [<span data-ttu-id="180c9-127">Habilitar o deshabilitar un protocolo de red de servidor</span><span class="sxs-lookup"><span data-stu-id="180c9-127">Enable or Disable a Server Network Protocol</span></span>](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)  
  
  
