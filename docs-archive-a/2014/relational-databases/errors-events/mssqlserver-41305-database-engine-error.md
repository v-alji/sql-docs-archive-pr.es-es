---
title: MSSQLSERVER_41305 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41305 (Database Engine error)
ms.assetid: a96e5083-ff97-4003-a900-07942454151d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9c00e20ec220d7fcee0da4e99c2ef35817dae67f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674137"
---
# <a name="mssqlserver_41305"></a><span data-ttu-id="773c4-102">MSSQLSERVER_41305</span><span class="sxs-lookup"><span data-stu-id="773c4-102">MSSQLSERVER_41305</span></span>
    
## <a name="details"></a><span data-ttu-id="773c4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="773c4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="773c4-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="773c4-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="773c4-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="773c4-105">Event ID</span></span>|<span data-ttu-id="773c4-106">41305</span><span class="sxs-lookup"><span data-stu-id="773c4-106">41305</span></span>|  
|<span data-ttu-id="773c4-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="773c4-107">Event Source</span></span>|<span data-ttu-id="773c4-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="773c4-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="773c4-109">Componente</span><span class="sxs-lookup"><span data-stu-id="773c4-109">Component</span></span>|<span data-ttu-id="773c4-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="773c4-110">SQLEngine</span></span>|  
|<span data-ttu-id="773c4-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="773c4-111">Symbolic Name</span></span>|<span data-ttu-id="773c4-112">HK_TX_COMMIT_RR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="773c4-112">HK_TX_COMMIT_RR_VALIDATION</span></span>|  
|<span data-ttu-id="773c4-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="773c4-113">Message Text</span></span>|<span data-ttu-id="773c4-114">La transacción actual no pudo confirmarse debido a un error repetible de validación de lectura.</span><span class="sxs-lookup"><span data-stu-id="773c4-114">The current transaction failed to commit due to a repeatable read validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="773c4-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="773c4-115">Explanation</span></span>  
 <span data-ttu-id="773c4-116">La transacción encontró un error de validación y ahora está condenada.</span><span class="sxs-lookup"><span data-stu-id="773c4-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
 <span data-ttu-id="773c4-117">Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="773c4-117">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="773c4-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="773c4-118">User Action</span></span>  
 <span data-ttu-id="773c4-119">Vuelva a intentar la transacción con error.</span><span class="sxs-lookup"><span data-stu-id="773c4-119">Retry the failed transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="773c4-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="773c4-120">See Also</span></span>  
 [<span data-ttu-id="773c4-121">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="773c4-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
