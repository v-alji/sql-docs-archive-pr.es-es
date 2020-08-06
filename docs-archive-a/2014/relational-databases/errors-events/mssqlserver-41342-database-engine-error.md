---
title: MSSQLSERVER_41342 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41342 (Database Engine error)
ms.assetid: 28270d98-c543-4e7d-b40c-2200e38dce1c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c0269322b30cee88e5ba3d50b6d391464b735f54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674868"
---
# <a name="mssqlserver_41342"></a><span data-ttu-id="0d3e0-102">MSSQLSERVER_41342</span><span class="sxs-lookup"><span data-stu-id="0d3e0-102">MSSQLSERVER_41342</span></span>
    
## <a name="details"></a><span data-ttu-id="0d3e0-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="0d3e0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d3e0-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="0d3e0-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0d3e0-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="0d3e0-105">Event ID</span></span>|<span data-ttu-id="0d3e0-106">41342</span><span class="sxs-lookup"><span data-stu-id="0d3e0-106">41342</span></span>|  
|<span data-ttu-id="0d3e0-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="0d3e0-107">Event Source</span></span>|<span data-ttu-id="0d3e0-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0d3e0-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0d3e0-109">Componente</span><span class="sxs-lookup"><span data-stu-id="0d3e0-109">Component</span></span>|<span data-ttu-id="0d3e0-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0d3e0-110">SQLEngine</span></span>|  
|<span data-ttu-id="0d3e0-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="0d3e0-111">Symbolic Name</span></span>|<span data-ttu-id="0d3e0-112">HK_HW_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="0d3e0-112">HK_HW_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="0d3e0-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="0d3e0-113">Message Text</span></span>|<span data-ttu-id="0d3e0-114">El modelo del procesador del sistema no permite crear *construct*.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-114">The model of the processor on the system does not support creating *construct*.</span></span> <span data-ttu-id="0d3e0-115">Este error suele producirse con procesadores antiguos.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-115">This error typically occurs with older processors.</span></span> <span data-ttu-id="0d3e0-116">Para obtener información sobre los modelos admitidos, vea los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d3e0-116">See [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online for information on supported models.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0d3e0-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="0d3e0-117">Explanation</span></span>  
 <span data-ttu-id="0d3e0-118">Las tablas con optimización para memoria requieren un modelo de procesador compatible con las operaciones atómicas de comparación e intercambio con valores de 128 bits, que requieren la instrucción CMPXCHG16B del lenguaje ensamblador.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-118">Memory-optimized tables require a processor model that supports atomic compare-and-exchange operations on 128-bit values, which require the assembly instruction CMPXCHG16B.</span></span> <span data-ttu-id="0d3e0-119">Ciertos modelos anteriores de procesadores AMD no admiten la instrucción CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-119">Certain older AMD processor models do not support the CMPXCHG16B instruction.</span></span> <span data-ttu-id="0d3e0-120">Además, algunos entornos de virtualización no tienen habilitada esta instrucción de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-120">Also, certain virtualization environments do not enable this instruction by default.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0d3e0-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="0d3e0-121">User Action</span></span>  
 <span data-ttu-id="0d3e0-122">Actualice el procesador.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-122">Upgrade your processor.</span></span> <span data-ttu-id="0d3e0-123">Si su procesador admite la instrucción y está ejecutando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en una máquina virtual, cambie la configuración para admitir la instrucción CMPXCHG16B.</span><span class="sxs-lookup"><span data-stu-id="0d3e0-123">If your processor supports the instruction and you are running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in a virtual machine, change the configuration to support the instruction CMPXCHG16B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d3e0-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d3e0-124">See Also</span></span>  
 [<span data-ttu-id="0d3e0-125">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="0d3e0-125">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
