---
title: MSSQLSERVER_41365 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41365 (Database Engine error)
ms.assetid: 4fc7ec15-b722-4e3d-b7f9-3d39d171e96e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1382a6395f1929a5d5552113e07376bcbf80bf35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674136"
---
# <a name="mssqlserver_41365"></a><span data-ttu-id="a5622-102">MSSQLSERVER_41365</span><span class="sxs-lookup"><span data-stu-id="a5622-102">MSSQLSERVER_41365</span></span>
    
## <a name="details"></a><span data-ttu-id="a5622-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a5622-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5622-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a5622-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="a5622-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a5622-105">Event ID</span></span>|<span data-ttu-id="a5622-106">41365</span><span class="sxs-lookup"><span data-stu-id="a5622-106">41365</span></span>|  
|<span data-ttu-id="a5622-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a5622-107">Event Source</span></span>|<span data-ttu-id="a5622-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a5622-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a5622-109">Componente</span><span class="sxs-lookup"><span data-stu-id="a5622-109">Component</span></span>|<span data-ttu-id="a5622-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a5622-110">SQLEngine</span></span>|  
|<span data-ttu-id="a5622-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a5622-111">Symbolic Name</span></span>|<span data-ttu-id="a5622-112">HK_MERGE_SCHEDULE_ERROR</span><span class="sxs-lookup"><span data-stu-id="a5622-112">HK_MERGE_SCHEDULE_ERROR</span></span>|  
|<span data-ttu-id="a5622-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a5622-113">Message Text</span></span>|<span data-ttu-id="a5622-114">La solicitud de combinación para el intervalo de transacción [%ld, %ld] en la base de datos %.\*ls no se ha programado.</span><span class="sxs-lookup"><span data-stu-id="a5622-114">Merge request for transaction range [%ld, %ld] on database %.\*ls was not scheduled.</span></span> <span data-ttu-id="a5622-115">Los archivos de puntos de comprobación que representan el intervalo no están disponibles para la combinación o para parte de una combinación en curso.</span><span class="sxs-lookup"><span data-stu-id="a5622-115">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a5622-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a5622-116">Explanation</span></span>  
 <span data-ttu-id="a5622-117">Los archivos de puntos de comprobación que representan el intervalo no están disponibles para la combinación o para parte de una combinación en curso.</span><span class="sxs-lookup"><span data-stu-id="a5622-117">The checkpoint files representing the range are either not available for merge or part of an ongoing merge.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a5622-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a5622-118">User Action</span></span>  
 <span data-ttu-id="a5622-119">Proporciona un mejor intervalo de transacciones para la combinación y la espera antes de emitir la misma solicitud de nuevo.</span><span class="sxs-lookup"><span data-stu-id="a5622-119">Provide a better transaction range for merge/wait before issuing the same request again.</span></span> <span data-ttu-id="a5622-120">Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="a5622-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5622-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5622-121">See Also</span></span>  
 [<span data-ttu-id="a5622-122">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="a5622-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
