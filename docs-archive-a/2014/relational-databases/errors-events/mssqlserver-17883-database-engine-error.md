---
title: MSSQLSERVER_17883 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17883 (Database Engine error)
ms.assetid: adaf1c04-e397-4a69-90b8-9353a37277ea
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46488fb6f7adac2c1109871f2aad4c79352829ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744719"
---
# <a name="mssqlserver_17883"></a><span data-ttu-id="82034-102">MSSQLSERVER_17883</span><span class="sxs-lookup"><span data-stu-id="82034-102">MSSQLSERVER_17883</span></span>
    
## <a name="details"></a><span data-ttu-id="82034-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="82034-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82034-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="82034-104">Product Name</span></span>|<span data-ttu-id="82034-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="82034-105">SQL Server</span></span>|  
|<span data-ttu-id="82034-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="82034-106">Event ID</span></span>|<span data-ttu-id="82034-107">17883</span><span class="sxs-lookup"><span data-stu-id="82034-107">17883</span></span>|  
|<span data-ttu-id="82034-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="82034-108">Event Source</span></span>|<span data-ttu-id="82034-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="82034-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="82034-110">Componente</span><span class="sxs-lookup"><span data-stu-id="82034-110">Component</span></span>|<span data-ttu-id="82034-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="82034-111">SQLEngine</span></span>|  
|<span data-ttu-id="82034-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="82034-112">Symbolic Name</span></span>|<span data-ttu-id="82034-113">SRV_SCHEDULER_NONYIELDING</span><span class="sxs-lookup"><span data-stu-id="82034-113">SRV_SCHEDULER_NONYIELDING</span></span>|  
|<span data-ttu-id="82034-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="82034-114">Message Text</span></span>|<span data-ttu-id="82034-115">Parece que el proceso %ld:%ld:%ld (0x%lx) Trabajo 0x%p no rinde en el programador %ld.</span><span class="sxs-lookup"><span data-stu-id="82034-115">Process %ld:%ld:%ld (0x%lx) Worker 0x%p appears to be non-yielding on Scheduler %ld.</span></span> <span data-ttu-id="82034-116">Thread creation time: %I64d.</span><span class="sxs-lookup"><span data-stu-id="82034-116">Thread creation time: %I64d.</span></span> <span data-ttu-id="82034-117">CPU usada por el subproceso (aprox.): kernel %I64d ms, usuario %I64d ms.</span><span class="sxs-lookup"><span data-stu-id="82034-117">Approx Thread CPU Used: kernel %I64d ms, user %I64d ms.</span></span> <span data-ttu-id="82034-118">Uso del proceso %d%%.</span><span class="sxs-lookup"><span data-stu-id="82034-118">Process Utilization %d%%.</span></span> <span data-ttu-id="82034-119">Sistema inactivo %d%%.</span><span class="sxs-lookup"><span data-stu-id="82034-119">System Idle %d%%.</span></span> <span data-ttu-id="82034-120">Intervalo: %I64d ms.</span><span class="sxs-lookup"><span data-stu-id="82034-120">Interval: %I64d ms.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="82034-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="82034-121">Explanation</span></span>  
 <span data-ttu-id="82034-122">Indica que hay un posible problema con un subproceso que no rinde en un programador.</span><span class="sxs-lookup"><span data-stu-id="82034-122">Indicates that there is a possible problem with a thread not yielding on a scheduler.</span></span>  <span data-ttu-id="82034-123">Esto podría deberse a un error en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o a que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no esté obteniendo bastantes ciclos para ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="82034-123">This could be caused by a bug in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not getting enough cycles to execute.</span></span>  <span data-ttu-id="82034-124">Este error podría desaparecer si el subproceso rinde finalmente.</span><span class="sxs-lookup"><span data-stu-id="82034-124">This error could go away if the thread eventually yields.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="82034-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="82034-125">User Action</span></span>  
 <span data-ttu-id="82034-126">Si la carga es excesiva en el sistema, redúzcala; de lo contrario, póngase en contacto con los servicios de soporte al cliente de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="82034-126">If excessive load on system reduce load otherwise contact Microsoft Customer Support Services.</span></span>  
  
  
