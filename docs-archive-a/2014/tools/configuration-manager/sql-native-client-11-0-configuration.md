---
title: Configuración de SQL Native Client 11,0 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client configuration [SQL Server], SQL Server Native Client
ms.assetid: e73143e9-5e7b-4d0a-8827-ab900efdcb35
author: stevestein
ms.author: sstein
ms.openlocfilehash: 183dd2d161b1bf0b13140a607167b81dab086fdf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663881"
---
# <a name="sql-native-client-110-configuration"></a><span data-ttu-id="674fa-102">Configuración de SQL Native Client 11.0</span><span class="sxs-lookup"><span data-stu-id="674fa-102">SQL Native Client 11.0 Configuration</span></span>
  <span data-ttu-id="674fa-103">Esta sección contiene los temas de la Ayuda F1 para los cuadros de diálogo de **Configuración de SQL Server Native Client** del Administrador de configuración de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="674fa-103">This section contains the F1 Help topics for the **SQL Server Native Client Configuration** dialogs in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="674fa-104">Native Client es la biblioteca de red que los equipos cliente utilizan para conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], y se inicia con [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="674fa-104">Native Client is the network library that client computers use to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], starting with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="674fa-105">Las opciones establecidas en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuración de SQL Native Client se utilizan en el equipo que ejecuta el programa cliente.</span><span class="sxs-lookup"><span data-stu-id="674fa-105">The settings configured in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client Configuration, are used on the computer running the client program.</span></span> <span data-ttu-id="674fa-106">Si se establecen en el equipo que ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], solo afectan a los programas cliente que se ejecutan en el servidor.</span><span class="sxs-lookup"><span data-stu-id="674fa-106">When configured on the computer running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], they affect only those client programs running on the server.</span></span>  
  
 <span data-ttu-id="674fa-107">Estas opciones no afectan a los clientes que se conectan a versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], salvo que utilicen las herramientas de cliente que se inician con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], como [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="674fa-107">These settings do not affect clients connecting to previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], unless they are using the client tools starting with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="674fa-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="674fa-108">In this Section</span></span>  
  
-   [<span data-ttu-id="674fa-109">Propiedades de Configuración de SQL Server Native Client &#40;pestaña Marcas&#41;</span><span class="sxs-lookup"><span data-stu-id="674fa-109">SQL Server Native Client Configuration Properties &#40;Flags Tab&#41;</span></span>](../../../2014/tools/configuration-manager/sql-server-native-client-configuration-properties-flags-tab.md)  
  
-   [<span data-ttu-id="674fa-110">Protocolos de cliente &#40;Administrador de configuración de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="674fa-110">Client Protocols &#40;SQL Server Configuration Manager&#41;</span></span>](../../relational-databases/sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="674fa-111">Propiedades de los protocolos de cliente &#40;pestaña Ordenar&#41;</span><span class="sxs-lookup"><span data-stu-id="674fa-111">Client Protocols Properties &#40;Order Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-properties-order-tab.md)  
  
    -   [<span data-ttu-id="674fa-112">Protocolos de cliente: Propiedades de Memoria compartida &#40;pestaña Protocolo&#41;</span><span class="sxs-lookup"><span data-stu-id="674fa-112">Client Protocols - Shared Memory Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-shared-memory-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="674fa-113">Protocolos de cliente: propiedades de TCP y IP &#40;ficha protocolo&#41;</span><span class="sxs-lookup"><span data-stu-id="674fa-113">Client Protocols - TCP and IP Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-tcp-and-ip-properties-protocol-tab.md)  
  
    -   [<span data-ttu-id="674fa-114">Protocolos de cliente: Propiedades de Canalizaciones con nombre &#40;pestaña Protocolo&#41;</span><span class="sxs-lookup"><span data-stu-id="674fa-114">Client Protocols - Named Pipes Properties &#40;Protocol Tab&#41;</span></span>](../../../2014/tools/configuration-manager/client-protocols-named-pipes-properties-protocol-tab.md)  
  
-   [<span data-ttu-id="674fa-115">Alias &#40;Administrador de configuración de SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="674fa-115">Aliases &#40;SQL Server Configuration Manager&#41;</span></span>](../../../2014/tools/configuration-manager/aliases-sql-server-configuration-manager.md)  
  
    -   [<span data-ttu-id="674fa-116">Nuevo alias &#40;pestaña Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="674fa-116">New Alias &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/new-alias-alias-tab.md)  
  
    -   [<span data-ttu-id="674fa-117">Propiedades de &#60;Alias&#62; &#40;pestaña Alias&#41;</span><span class="sxs-lookup"><span data-stu-id="674fa-117">&#60;Alias&#62; Properties &#40;Alias Tab&#41;</span></span>](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md)  
  
    -   [<span data-ttu-id="674fa-118">Crear una cadena de conexión válida con el protocolo de memoria compartida</span><span class="sxs-lookup"><span data-stu-id="674fa-118">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
    -   [<span data-ttu-id="674fa-119">Crear una cadena de conexión válida con TCP/IP</span><span class="sxs-lookup"><span data-stu-id="674fa-119">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
    -   [<span data-ttu-id="674fa-120">Crear una cadena de conexión válida con canalizaciones con nombre</span><span class="sxs-lookup"><span data-stu-id="674fa-120">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
