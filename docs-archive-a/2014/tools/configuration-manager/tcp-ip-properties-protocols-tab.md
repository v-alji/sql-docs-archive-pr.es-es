---
title: Propiedades TCP/IP (pestaña protocolos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], configuration options
ms.assetid: 007638fc-3a24-4460-adbe-545ded5d6f88
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d5bc28faddae9a86a6636b56b907b57a2d8711a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663260"
---
# <a name="tcp---ip-properties-protocols-tab"></a><span data-ttu-id="e0fe2-102">Propiedades de TCP-IP (pestaña protocolos)</span><span class="sxs-lookup"><span data-stu-id="e0fe2-102">TCP - IP Properties (Protocols Tab)</span></span>
  <span data-ttu-id="e0fe2-103">Use el cuadro de diálogo **Propiedades de TCP/IP** para configurar las opciones para el protocolo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="e0fe2-103">Use the **TCP/IP Properties** dialog box to configure the options for the TCP/IP protocol.</span></span> <span data-ttu-id="e0fe2-104">Haga clic en **TCP/IP** en el panel izquierdo para mostrar configuraciones de direcciones IP individuales en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="e0fe2-104">Click **TCP/IP** in the left pane, to show individual IP address configurations in the details pane.</span></span>  
  
 <span data-ttu-id="e0fe2-105">Es necesario reiniciar Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para que se apliquen los cambios.</span><span class="sxs-lookup"><span data-stu-id="e0fe2-105">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted before the changes take effect.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e0fe2-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="e0fe2-106">Options</span></span>  
 <span data-ttu-id="e0fe2-107">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="e0fe2-107">**Enabled**</span></span>  
 <span data-ttu-id="e0fe2-108">Los valores posibles son **Yes** y **No**.</span><span class="sxs-lookup"><span data-stu-id="e0fe2-108">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="e0fe2-109">**Keep Alive**</span><span class="sxs-lookup"><span data-stu-id="e0fe2-109">**Keep Alive**</span></span>  
 <span data-ttu-id="e0fe2-110">Especifique el intervalo (en milisegundos) en el que los paquetes de mantenimiento de conexión se transmitirán para comprobar si el equipo que está en la parte remota de una conexión todavía está disponible.</span><span class="sxs-lookup"><span data-stu-id="e0fe2-110">Specify the interval (milliseconds) in which keep-alive packets are transmitted to verify that the computer at the remote end of a connection is still available.</span></span>  
  
 <span data-ttu-id="e0fe2-111">**Listen All**</span><span class="sxs-lookup"><span data-stu-id="e0fe2-111">**Listen All**</span></span>  
 <span data-ttu-id="e0fe2-112">Especifique si SQL Server escuchará en todas las direcciones IP que están enlazadas a tarjetas de red en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e0fe2-112">Specify whether SQL Server will listen on all the IP addresses that are bound to network cards on the computer.</span></span> <span data-ttu-id="e0fe2-113">Si se establece en **No**, configure cada dirección IP por separado con el cuadro de diálogo de propiedades de cada dirección IP.</span><span class="sxs-lookup"><span data-stu-id="e0fe2-113">If set to **No**, configure each IP address separately using the properties dialog box for each IP address.</span></span> <span data-ttu-id="e0fe2-114">Si se establece en **Yes**, la configuración del cuadro de propiedades de **IPAll** se aplicará en todas las direcciones IP.</span><span class="sxs-lookup"><span data-stu-id="e0fe2-114">If set to **Yes**, the settings of the **IPAll** properties box will apply to all IP addresses.</span></span> <span data-ttu-id="e0fe2-115">El valor predeterminado es **Yes**.</span><span class="sxs-lookup"><span data-stu-id="e0fe2-115">Default value is **Yes**.</span></span>  
  
 <span data-ttu-id="e0fe2-116">**No Delay**</span><span class="sxs-lookup"><span data-stu-id="e0fe2-116">**No Delay**</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e0fe2-117">no implementa cambios en esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="e0fe2-117">does not implement changes to this property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0fe2-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0fe2-118">See Also</span></span>  
 <span data-ttu-id="e0fe2-119">[Elegir un protocolo de red](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="e0fe2-119">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="e0fe2-120">Crear una cadena de conexión válida con TCP/IP</span><span class="sxs-lookup"><span data-stu-id="e0fe2-120">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
  
