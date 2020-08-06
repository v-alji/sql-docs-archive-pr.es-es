---
title: 'Protocolos de cliente: propiedades de TCP y IP (pestaña protocolo) | Microsoft Docs'
description: Obtenga información acerca de cómo especificar las opciones de TCP/IP en Microsoft SQL Server Configuration Manager, como el parámetro Keep Alive y el número de puerto predeterminado.
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], client protocols
- client protocols [SQL Server]
ms.assetid: d04f1bce-069c-4a02-b561-c87c3282be36
author: rothja
ms.author: jroth
ms.openlocfilehash: dfcf0348dc863970384a40cc9e773481adeedb35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748449"
---
# <a name="client-protocols---tcp-and-ip-properties-protocol-tab"></a><span data-ttu-id="f38f8-103">Protocolos de cliente y Propiedades de TCP/IP (pestaña Protocolo)</span><span class="sxs-lookup"><span data-stu-id="f38f8-103">Client Protocols - TCP and IP Properties (Protocol Tab)</span></span>
  <span data-ttu-id="f38f8-104">En el Administrador de configuración de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use la pestaña **Protocolo** del cuadro de diálogo **Propiedades de TCP/IP** para ver o especificar las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="f38f8-104">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, use the **Protocol** tab on the **TCP/IP Properties** dialog box to view or specify the following options.</span></span> <span data-ttu-id="f38f8-105">Para conectar a un puerto diferente, escriba el número de puerto en el cuadro **Puerto predeterminado** .</span><span class="sxs-lookup"><span data-stu-id="f38f8-105">To connect to a different port, type the port number in the **Default Port** box.</span></span> <span data-ttu-id="f38f8-106">Para obtener más información sobre cadenas de conexión, vea [Crear una cadena de conexión válida con TCP/IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span><span class="sxs-lookup"><span data-stu-id="f38f8-106">For more information about connection strings, see [Creating a Valid Connection String Using TCP IP](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f38f8-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="f38f8-107">Options</span></span>  
 <span data-ttu-id="f38f8-108">**Puerto predeterminado**</span><span class="sxs-lookup"><span data-stu-id="f38f8-108">**Default Port**</span></span>  
 <span data-ttu-id="f38f8-109">Especifica el puerto que la biblioteca de red de TCP/IP utilizará para intentar conectarse a la instancia de destino de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f38f8-109">Specifies the port that the TCP/IP Net-library will use to attempt to connect to the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f38f8-110">El puerto predeterminado es 1433.</span><span class="sxs-lookup"><span data-stu-id="f38f8-110">The default value port is 1433.</span></span>  
  
 <span data-ttu-id="f38f8-111">Al conectar a una instancia predeterminada del [!INCLUDE[ssDE](../../includes/ssde-md.md)], el cliente utiliza este valor.</span><span class="sxs-lookup"><span data-stu-id="f38f8-111">When connecting to a default instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client uses this value.</span></span> <span data-ttu-id="f38f8-112">Si se ha configurado una instancia predeterminada para que escuche en un puerto diferente, cambie este valor a dicho número de puerto.</span><span class="sxs-lookup"><span data-stu-id="f38f8-112">If a default instance has been configured to listen on a different port, change this value to that port number.</span></span>  
  
 <span data-ttu-id="f38f8-113">Al conectar a una instancia con nombre del [!INCLUDE[ssDE](../../includes/ssde-md.md)], el cliente intentará obtener el número de puerto desde el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que se ejecuta en el servidor.</span><span class="sxs-lookup"><span data-stu-id="f38f8-113">When connecting to a named instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)], the client will attempt to obtain the port number from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service running on the server computer.</span></span> <span data-ttu-id="f38f8-114">Si el servicio Explorador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no se está ejecutando, se debe proporcionar el número de puerto mediante esta configuración o como parte de la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="f38f8-114">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser Service is not running, the port number must be provided through this setting, or as part of the connection string.</span></span>  
  
 <span data-ttu-id="f38f8-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="f38f8-115">**Enabled**</span></span>  
 <span data-ttu-id="f38f8-116">Los valores posibles son **sí** y **no**.</span><span class="sxs-lookup"><span data-stu-id="f38f8-116">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="f38f8-117">**Mantener activo**</span><span class="sxs-lookup"><span data-stu-id="f38f8-117">**Keep Alive**</span></span>  
 <span data-ttu-id="f38f8-118">Este parámetro (en milisegundos) controla la frecuencia con la que TCP intenta comprobar que una conexión inactiva sigue intacta mediante el envío de un paquete **KEEPALIVE** .</span><span class="sxs-lookup"><span data-stu-id="f38f8-118">This parameter (in milliseconds) controls how often TCP attempts to verify that an idle connection is still intact by sending a **KEEPALIVE** packet.</span></span> <span data-ttu-id="f38f8-119">El valor predeterminado es 30000 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="f38f8-119">The default is 30000 milliseconds.</span></span>  
  
 <span data-ttu-id="f38f8-120">**Intervalo entre mensajes de mantenimiento de conexión**</span><span class="sxs-lookup"><span data-stu-id="f38f8-120">**Keep Alive Interval**</span></span>  
 <span data-ttu-id="f38f8-121">Este parámetro (en milisegundos) determina el intervalo que separa las retransmisiones **KEEPALIVE** hasta que se recibe una respuesta.</span><span class="sxs-lookup"><span data-stu-id="f38f8-121">This parameter (in milliseconds) determines the interval separating **KEEPALIVE** retransmissions until a response is received.</span></span> <span data-ttu-id="f38f8-122">El valor predeterminado es 1000 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="f38f8-122">The default is 1000 milliseconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f38f8-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f38f8-123">See Also</span></span>  
 <span data-ttu-id="f38f8-124">[Elección de un protocolo de red](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="f38f8-124">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 <span data-ttu-id="f38f8-125">[Nuevo alias &#40;pestaña alias&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span><span class="sxs-lookup"><span data-stu-id="f38f8-125">[New Alias &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/new-alias-alias-tab.md) </span></span>  
 [<span data-ttu-id="f38f8-126">Propiedades de &#60;Alias&#62; &#40;pestaña Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="f38f8-126">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
  
