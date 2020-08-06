---
title: Propiedades de los protocolos de cliente (pestaña pedido) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client protocols [SQL Server]
ms.assetid: 64fd7135-1756-4885-bed9-9ab8997ecc6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: a367cff3495389d1a707ed108ba75e1e736538b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744942"
---
# <a name="client-protocols-properties-order-tab"></a><span data-ttu-id="0a1ab-102">Propiedades de los protocolos de cliente (pestaña Ordenar)</span><span class="sxs-lookup"><span data-stu-id="0a1ab-102">Client Protocols Properties (Order Tab)</span></span>
  <span data-ttu-id="0a1ab-103">Utilice la página **Ordenar**del cuadro de diálogo **Propiedades de los protocolos de cliente** para ver y habilitar los protocolos de cliente.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-103">Use the **Order**page on the **Client Protocols Properties** dialog box to view and enable the client protocols.</span></span>  
  
 <span data-ttu-id="0a1ab-104">Haga clic en un protocolo y, a continuación, haga clic en **Habilitar** o **Deshabilitar** para mover el protocolo seleccionado a la lista **Protocolos deshabilitados** o **Protocolos habilitados** .</span><span class="sxs-lookup"><span data-stu-id="0a1ab-104">Click a protocol, and then click **Enable** or **Disable** to move the selected protocol to the **Disabled Protocols** or **Enabled Protocols** list.</span></span>  
  
 <span data-ttu-id="0a1ab-105">Los protocolos se intentan utilizar en el orden enumerado. Primero se intenta la conexión con el protocolo que está en primer lugar, después con el segundo, etc. Para subir o bajar los protocolos en la lista **Protocolos habilitados** , haga clic en los botones de flecha arriba y flecha abajo.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-105">Protocols are tried in the order listed, attempting to connect using the top protocol first, and then the second listed protocol, etc. Move protocols up or down the **Enabled Protocols** list, by clicking the up arrow and down arrow buttons.</span></span> <span data-ttu-id="0a1ab-106">Al conectarse a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde un cliente que se encuentre en ese equipo, siempre se intentará utilizar en primer lugar el protocolo **Memoria compartida** si está habilitado.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-106">When connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer, the **Shared Memory** protocol will always be tried first, if enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a1ab-107">En [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient, no se utiliza esta configuración.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-107">These settings are not used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient.</span></span> <span data-ttu-id="0a1ab-108">El orden de los protocolos para .NET SqlClient es primero TCP y, después, las canalizaciones con nombre, que no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-108">The protocol order for .NET SqlClient is first TCP, and then named pipes, which cannot be changed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0a1ab-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="0a1ab-109">Options</span></span>  
 <span data-ttu-id="0a1ab-110">**Protocolos deshabilitados**</span><span class="sxs-lookup"><span data-stu-id="0a1ab-110">**Disabled Protocols**</span></span>  
 <span data-ttu-id="0a1ab-111">Muestra una lista de los protocolos que están instalados pero no se utilizan actualmente.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-111">Lists protocols which are installed but are not currently used.</span></span>  
  
 <span data-ttu-id="0a1ab-112">**Protocolos habilitados**</span><span class="sxs-lookup"><span data-stu-id="0a1ab-112">**Enabled Protocols**</span></span>  
 <span data-ttu-id="0a1ab-113">Enumera los protocolos que están disponibles para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] los clientes de en este equipo.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-113">Lists protocols which are available for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this computer.</span></span>  
  
 **>**  
 <span data-ttu-id="0a1ab-114">Habilita el protocolo que se encuentre resaltado en el cuadro **Protocolos deshabilitados** y lo mueve al cuadro **Protocolos habilitados** .</span><span class="sxs-lookup"><span data-stu-id="0a1ab-114">Enables the currently highlighted protocol in the **Disabled Protocols** box, moving it to the **Enabled Protocols** box.</span></span>  
  
 **\<**  
 <span data-ttu-id="0a1ab-115">Deshabilita el protocolo que se encuentre resaltado en el cuadro **Protocolos habilitados** y lo mueve al cuadro **Protocolos deshabilitados** .</span><span class="sxs-lookup"><span data-stu-id="0a1ab-115">Disables the currently highlighted protocol in the **Enabled Protocols** box, moving it to the **Disabled Protocols** box.</span></span>  
  
 <span data-ttu-id="0a1ab-116">Flecha arriba</span><span class="sxs-lookup"><span data-stu-id="0a1ab-116">Up arrow</span></span>  
 <span data-ttu-id="0a1ab-117">Mueve el protocolo resaltado hacia arriba en la lista.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-117">Moves the highlighted protocol up in the list.</span></span> <span data-ttu-id="0a1ab-118">Esto le permite aumentar la prioridad con la que la biblioteca de red intentará utilizar el protocolo seleccionado para las conexiones.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-118">This allows you to increase the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="0a1ab-119">Flecha abajo</span><span class="sxs-lookup"><span data-stu-id="0a1ab-119">Down arrow</span></span>  
 <span data-ttu-id="0a1ab-120">Mueve el protocolo resaltado hacia abajo en la lista.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-120">Moves the highlighted protocol down in the list.</span></span> <span data-ttu-id="0a1ab-121">Esto le permite reducir la prioridad con la que la biblioteca de red intentará utilizar el protocolo seleccionado para las conexiones.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-121">This allows you to decrease the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="0a1ab-122">**Habilitar el protocolo de memoria compartida**</span><span class="sxs-lookup"><span data-stu-id="0a1ab-122">**Enable Shared Memory Protocol**</span></span>  
 <span data-ttu-id="0a1ab-123">Habilita el protocolo de memoria compartida, que siempre se intenta usar en primer lugar (si está habilitado), al conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde un cliente que resida en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-123">Enables the shared memory protocol which is always tried first (if enabled), when connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a1ab-124">Si el protocolo se especifica mediante un prefijo o como parte de la cadena de conexión, solo se intenta utilizar el protocolo especificado.</span><span class="sxs-lookup"><span data-stu-id="0a1ab-124">If the protocol is specified through a prefix or as part of the connection string, only the specified protocol is attempted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a1ab-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a1ab-125">See Also</span></span>  
 [<span data-ttu-id="0a1ab-126">Elegir un protocolo de red</span><span class="sxs-lookup"><span data-stu-id="0a1ab-126">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
