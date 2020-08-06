---
title: MSSQLSERVER_17887 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17887 (Database Engine error)
ms.assetid: ad0806e6-3296-4c32-b103-fccf0f8a8d3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 006e616d80ef7e8d083f60675b02b4e6a4e8dc24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663002"
---
# <a name="mssqlserver_17887"></a><span data-ttu-id="b2c3a-102">MSSQLSERVER_17887</span><span class="sxs-lookup"><span data-stu-id="b2c3a-102">MSSQLSERVER_17887</span></span>
    
## <a name="details"></a><span data-ttu-id="b2c3a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b2c3a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b2c3a-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="b2c3a-104">Product Name</span></span>|<span data-ttu-id="b2c3a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b2c3a-105">SQL Server</span></span>|  
|<span data-ttu-id="b2c3a-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b2c3a-106">Event ID</span></span>|<span data-ttu-id="b2c3a-107">17887</span><span class="sxs-lookup"><span data-stu-id="b2c3a-107">17887</span></span>|  
|<span data-ttu-id="b2c3a-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="b2c3a-108">Event Source</span></span>|<span data-ttu-id="b2c3a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b2c3a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b2c3a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b2c3a-110">Component</span></span>|<span data-ttu-id="b2c3a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b2c3a-111">SQLEngine</span></span>|  
|<span data-ttu-id="b2c3a-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b2c3a-112">Symbolic Name</span></span>|<span data-ttu-id="b2c3a-113">SRV_IO_COMP_LISTENER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="b2c3a-113">SRV_IO_COMP_LISTENER_NONYIELDING</span></span>|  
|<span data-ttu-id="b2c3a-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b2c3a-114">Message Text</span></span>|<span data-ttu-id="b2c3a-115">Parece que la escucha de finalización de E/S (0x%lx) Trabajo 0x%p no rinde en el nodo %ld.</span><span class="sxs-lookup"><span data-stu-id="b2c3a-115">IO Completion Listener (0x%lx) Worker 0x%p appears to be non-yielding on Node %ld.</span></span> <span data-ttu-id="b2c3a-116">Uso de CPU (aprox.): kernel %I64d ms, usuario %I64d ms, Intervalo: %I64d.</span><span class="sxs-lookup"><span data-stu-id="b2c3a-116">Approx CPU Used: kernel %I64d ms, user %I64d ms, Interval: %I64d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b2c3a-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="b2c3a-117">Explanation</span></span>  
 <span data-ttu-id="b2c3a-118">Indica que hay un posible problema con la escucha del puerto de finalización de E/S en el nodo especificado al ejecutar la rutina de finalización de E/S para un evento de lectura/escritura de red.</span><span class="sxs-lookup"><span data-stu-id="b2c3a-118">Indicates that there is a possible problem with the I/O Completion Port Listener on the specified node when executing the I/O Completion routine for a network read/write event.</span></span> <span data-ttu-id="b2c3a-119">Este error desaparecerá cuando la escucha del puerto de finalización de E/S vuelva de ejecutar la rutina de finalización de E/S.</span><span class="sxs-lookup"><span data-stu-id="b2c3a-119">This error will go away when the I/O Completion Port Listener returns from executing the I/O Completion routine.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b2c3a-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b2c3a-120">User Action</span></span>  
 <span data-ttu-id="b2c3a-121">Póngase en contacto con los servicios de soporte al cliente de Microsoft (CSS).</span><span class="sxs-lookup"><span data-stu-id="b2c3a-121">Contact Microsoft Customer Support Services (CSS).</span></span>  
  
  
