---
title: MSSQLSERVER_9692 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9692 (Database Engine error)
ms.assetid: 02399d6e-ab5e-4f30-8a3e-2bb1e8c135b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6ba95771aafffa5a322ffa1b7443419936addd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672029"
---
# <a name="mssqlserver_9692"></a><span data-ttu-id="df0ed-102">MSSQLSERVER_9692</span><span class="sxs-lookup"><span data-stu-id="df0ed-102">MSSQLSERVER_9692</span></span>
    
## <a name="details"></a><span data-ttu-id="df0ed-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="df0ed-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df0ed-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="df0ed-104">Product Name</span></span>|<span data-ttu-id="df0ed-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="df0ed-105">SQL Server</span></span>|  
|<span data-ttu-id="df0ed-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="df0ed-106">Event ID</span></span>|<span data-ttu-id="df0ed-107">9692</span><span class="sxs-lookup"><span data-stu-id="df0ed-107">9692</span></span>|  
|<span data-ttu-id="df0ed-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="df0ed-108">Event Source</span></span>|<span data-ttu-id="df0ed-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="df0ed-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="df0ed-110">Componente</span><span class="sxs-lookup"><span data-stu-id="df0ed-110">Component</span></span>|<span data-ttu-id="df0ed-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="df0ed-111">SQLEngine</span></span>|  
|<span data-ttu-id="df0ed-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="df0ed-112">Symbolic Name</span></span>|<span data-ttu-id="df0ed-113">SB2_CANT_LISTEN_PORT_IN_USE</span><span class="sxs-lookup"><span data-stu-id="df0ed-113">SB2_CANT_LISTEN_PORT_IN_USE</span></span>|  
|<span data-ttu-id="df0ed-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="df0ed-114">Message Text</span></span>|<span data-ttu-id="df0ed-115">El transporte de protocolo %S_MSG no puede escuchar en el puerto %d porque lo está utilizando otro proceso.</span><span class="sxs-lookup"><span data-stu-id="df0ed-115">The %S_MSG protocol transport cannot listen on port %d because it is in use by another process.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="df0ed-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="df0ed-116">Explanation</span></span>  
 <span data-ttu-id="df0ed-117">Otro programa del equipo está usando el puerto TCP indicado.</span><span class="sxs-lookup"><span data-stu-id="df0ed-117">Another program on the computer is using the TCP port indicated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="df0ed-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="df0ed-118">User Action</span></span>  
 <span data-ttu-id="df0ed-119">Ejecute `netstat -aon` para determinar qué programa está usando el puerto.</span><span class="sxs-lookup"><span data-stu-id="df0ed-119">Run `netstat -aon` to determine what program is using the port.</span></span> <span data-ttu-id="df0ed-120">Deshabilite esa aplicación o especifique otro puerto para Service Broker.</span><span class="sxs-lookup"><span data-stu-id="df0ed-120">Disable that application or specify a different port for Service Broker.</span></span>  
  
  
