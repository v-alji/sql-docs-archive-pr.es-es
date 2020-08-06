---
title: Proteger la replicación por Internet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- security [SQL Server replication], Internet
- Internet [SQL Server replication], security
ms.assetid: 25b7af05-2721-4b24-9083-fb671e8bf4e0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 47408b2b9559d33da4563c6fc9560d20338ee01d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749705"
---
# <a name="securing-replication-over-the-internet"></a><span data-ttu-id="fbbd1-102">Securing Replication Over the Internet</span><span class="sxs-lookup"><span data-stu-id="fbbd1-102">Securing Replication Over the Internet</span></span>
  <span data-ttu-id="fbbd1-103">La replicación por Internet puede proporcionar flexibilidad, en especial a los suscriptores móviles, pero debe configurarla de forma correcta para garantizar la seguridad adecuada.</span><span class="sxs-lookup"><span data-stu-id="fbbd1-103">Replication over the Internet can provide flexibility, particularly for mobile Subscribers, but you must configure Internet replication appropriately to ensure adequate security.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="fbbd1-104">recomienda utilizar una de estas dos técnicas para compartir información de forma segura en Internet:</span><span class="sxs-lookup"><span data-stu-id="fbbd1-104">recommends using one of two techniques for securely sharing information over the Internet:</span></span>  
  
-   <span data-ttu-id="fbbd1-105">Red privada virtual (VPN)</span><span class="sxs-lookup"><span data-stu-id="fbbd1-105">Virtual private network (VPN)</span></span>  
  
-   <span data-ttu-id="fbbd1-106">La opción Sincronización web para la replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="fbbd1-106">The Web synchronization option for merge replication</span></span>  
  
## <a name="virtual-private-network"></a><span data-ttu-id="fbbd1-107">Red privada virtual</span><span class="sxs-lookup"><span data-stu-id="fbbd1-107">Virtual Private Network</span></span>  
 <span data-ttu-id="fbbd1-108">Las redes privadas virtuales proporcionan un método por capas seguro y sencillo para replicar datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] por Internet.</span><span class="sxs-lookup"><span data-stu-id="fbbd1-108">Virtual private networks provide a simple and secure layered approach to replicating [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data over the Internet.</span></span> <span data-ttu-id="fbbd1-109">La conexión VPN a través de Internet funciona lógicamente como un vínculo de red de área extensa (WAN) entre los sitios.</span><span class="sxs-lookup"><span data-stu-id="fbbd1-109">The VPN connection over the Internet logically operates as a Wide Area Network (WAN) link between the sites.</span></span>  
  
 <span data-ttu-id="fbbd1-110">Esto se consigue permitiendo que el usuario utilice Internet u otra red pública por medio de un protocolo como el Protocolo de túnel punto a punto (PPTP) de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] , incluido en el sistema operativo [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows NT versión 4.0 o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000, o el Protocolo de túnel de capa dos (L2TP), incluido en Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="fbbd1-110">This is achieved by allowing the user to tunnel through the Internet or another public network using a protocol such as [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Point-to-Point Tunneling Protocol (PPTP) available with the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows NT version 4.0 or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000 operating system, or Layer Two Tunneling Protocol (L2TP) available with the Windows 2000 operating system.</span></span> <span data-ttu-id="fbbd1-111">Este proceso proporciona seguridad y características parecidas a las disponibles en una red privada.</span><span class="sxs-lookup"><span data-stu-id="fbbd1-111">This process provides security and features similar to those available in a private network.</span></span>  
  
 <span data-ttu-id="fbbd1-112">Para obtener más información acerca de la configuración de una VPN, vea la documentación de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="fbbd1-112">For more information about setting up a VPN, see the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
## <a name="web-synchronization-through-iis"></a><span data-ttu-id="fbbd1-113">Sincronización web mediante IIS</span><span class="sxs-lookup"><span data-stu-id="fbbd1-113">Web Synchronization Through IIS</span></span>  
 <span data-ttu-id="fbbd1-114">La opción de sincronización web en la replicación de mezcla proporciona la capacidad de replicar datos utilizando el protocolo HTTPS, que puede ser un método cómodo para replicar datos a través de un firewall.</span><span class="sxs-lookup"><span data-stu-id="fbbd1-114">The web synchronization option for merge replication provides the ability to replicate data using the HTTPS protocol, which can be a convenient approach to replicating data through a firewall.</span></span> <span data-ttu-id="fbbd1-115">Para más información sobre la seguridad en la sincronización web, vea [Configure Web Synchronization](../configure-web-synchronization.md) (Configurar la sincronización web) y [Security Architecture for Web Synchronization](security-architecture-for-web-synchronization.md) (Arquitectura de seguridad para la sincronización web).</span><span class="sxs-lookup"><span data-stu-id="fbbd1-115">For more information, see [Configure Web Synchronization](../configure-web-synchronization.md) and [Security Architecture for Web Synchronization](security-architecture-for-web-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbbd1-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fbbd1-116">See Also</span></span>  
 <span data-ttu-id="fbbd1-117">[Replication Security Best Practices](replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="fbbd1-117">[Replication Security Best Practices](replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="fbbd1-118">Seguridad de Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="fbbd1-118">SQL Server Replication Security</span></span>](view-and-modify-replication-security-settings.md)  
  
  
