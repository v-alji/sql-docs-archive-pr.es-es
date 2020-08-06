---
title: Modificar las conexiones que usan los protocolos de red SPP (Protocolo de paquetes secuenciados) de Banyan VINEs, multiprotocolo, AppleTalk o NWLink IPX SPX | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- network protocols [SQL Server], modifying connections
- SPP [SQL Server]
- NWLink IPX/SPX [SQL Server]
- connections [SQL Server]
- AppleTalk [SQL Server]
- Sequenced Packet Protocol [SQL Server]
- Multiprotocol Net-Library [SQL Server]
- Banyan VINES Sequenced Package Protocol [SQL Server]
- IPX/SPX [SQL Server]
- protocols [SQL Server], modifying connections
- RPC [SQL Server]
ms.assetid: 5c5ae453-cc5b-4898-95c7-ad34157b1f60
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 750b9c0b76ab6c3b43908ecb8454f31ac1a25b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749593"
---
# <a name="modify-connections-that-use-banyan-vines-sequenced-packet-protocol-spp-multiprotocol-appletalk-or-nwlink-ipx-spx-network-protocols"></a><span data-ttu-id="40a1a-102">Modificar las conexiones que utilizan el protocolo de red SPP (Protocolo de paquetes secuenciados) de Banyan VINES o los protocolos Multiprotocolo, AppleTalk o NWLink IPX/SPX.</span><span class="sxs-lookup"><span data-stu-id="40a1a-102">Modify connections that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX SPX network protocols</span></span>
  <span data-ttu-id="40a1a-103">El Asesor de actualizaciones ha detectado protocolos de conectividad cliente-servidor que no se admiten en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40a1a-103">The Upgrade Advisor has detected client server connectivity protocols that are not supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="40a1a-104">Las aplicaciones cliente que utilicen el protocolo de red SPP (Protocolo de paquetes secuenciados) de Banyan VINES o los protocolos de red Multiprotocolo (RPC), AppleTalk o NWLink IPX/SPX deben conectarse utilizando uno de los protocolos admitidos.</span><span class="sxs-lookup"><span data-stu-id="40a1a-104">Client applications that use Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol (RPC), AppleTalk, or NWLink IPX/SPX network protocols must connect using a supported protocol.</span></span>  
  
## <a name="component"></a><span data-ttu-id="40a1a-105">Componente</span><span class="sxs-lookup"><span data-stu-id="40a1a-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="40a1a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="40a1a-106">Description</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="40a1a-107">no es compatible con los protocolos de red SPP (Protocolo de paquetes secuenciados) de Banyan VINES, Multiprotocolo, AppleTalk o NWLink IPX/SPX.</span><span class="sxs-lookup"><span data-stu-id="40a1a-107">does not support the Banyan VINES Sequenced Packet Protocol (SPP), Multiprotocol, AppleTalk, or NWLink IPX/SPX network protocols.</span></span> <span data-ttu-id="40a1a-108">Los clientes anteriormente conectados con estos protocolos deben seleccionar uno distinto.</span><span class="sxs-lookup"><span data-stu-id="40a1a-108">Clients previously connecting with these protocols must select a different protocol.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="40a1a-109">Acción correctora</span><span class="sxs-lookup"><span data-stu-id="40a1a-109">Corrective Action</span></span>  
 <span data-ttu-id="40a1a-110">Modifique las aplicaciones cliente para utilizar un protocolo compatible al conectarlas con el servidor.</span><span class="sxs-lookup"><span data-stu-id="40a1a-110">Change the client applications to use a supported protocol when connecting to the server.</span></span> <span data-ttu-id="40a1a-111">Si ha configurado un alias que utiliza uno de los protocolos no compatibles, deberá modificar el alias para que utilice uno compatible.</span><span class="sxs-lookup"><span data-stu-id="40a1a-111">If you have an alias setup that uses one of the unsupported protocols then the alias must be modified to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="40a1a-112">Si la cadena de conexión de la aplicación usa o carga específicamente uno de estos protocolos, especificando NETWORK = DBMSRPCN para RPC, NETWORK = DBMSADSN para AppleTalk o NETWORK = DBMSVINN para la propiedad Banyan VINEs, o mediante un prefijo explícito como "SPX:*servidor\instancia*" para SPX, "BV:*Server*" para Banyan Vines, "ADSP:*Server*" para AppleTalk o "RPC:*Server*" para multiprotocolo, debe modificar la aplicación para que use uno de los protocolos admitidos.</span><span class="sxs-lookup"><span data-stu-id="40a1a-112">If your application connection string specifically uses or loads one of these protocols, by either specifying NETWORK=DBMSRPCN for RPC, NETWORK=DBMSADSN for Appletalk, or NETWORK=DBMSVINN for Banyan VINES property, or by using an explicit prefix such as "spx:*server\instance*" for SPX, "bv:*server*" for Banyan VINES, "adsp:*server*" for AppleTalk, or "rpc:*server*" for multiprotocol, then you must modify your application to use one of the supported protocols.</span></span>  
  
 <span data-ttu-id="40a1a-113">Para obtener más información, vea "Elegir un protocolo de red" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40a1a-113">For more information, see "Choosing a Network Protocol" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a1a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40a1a-114">See Also</span></span>  
 <span data-ttu-id="40a1a-115">[Problemas de actualización Motor de base de datos](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="40a1a-115">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="40a1a-116">SQL Server el asesor de actualizaciones de 2014 &#91;nuevo&#93;</span><span class="sxs-lookup"><span data-stu-id="40a1a-116">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
