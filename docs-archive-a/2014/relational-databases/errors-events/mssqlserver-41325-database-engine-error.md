---
title: MSSQLSERVER_41325 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41325 (Database Engine error)
ms.assetid: 97c6a8bb-139a-44f3-9ed5-f46d047e8ed3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a512d7db6529876259d889d04aabf3d07747cafe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746304"
---
# <a name="mssqlserver_41325"></a><span data-ttu-id="11dbf-102">MSSQLSERVER_41325</span><span class="sxs-lookup"><span data-stu-id="11dbf-102">MSSQLSERVER_41325</span></span>
    
## <a name="details"></a><span data-ttu-id="11dbf-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="11dbf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11dbf-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="11dbf-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="11dbf-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="11dbf-105">Event ID</span></span>|<span data-ttu-id="11dbf-106">41325</span><span class="sxs-lookup"><span data-stu-id="11dbf-106">41325</span></span>|  
|<span data-ttu-id="11dbf-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="11dbf-107">Event Source</span></span>|<span data-ttu-id="11dbf-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="11dbf-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="11dbf-109">Componente</span><span class="sxs-lookup"><span data-stu-id="11dbf-109">Component</span></span>|<span data-ttu-id="11dbf-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="11dbf-110">SQLEngine</span></span>|  
|<span data-ttu-id="11dbf-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="11dbf-111">Symbolic Name</span></span>|<span data-ttu-id="11dbf-112">HK_TX_COMMIT_SR_VALIDATION</span><span class="sxs-lookup"><span data-stu-id="11dbf-112">HK_TX_COMMIT_SR_VALIDATION</span></span>|  
|<span data-ttu-id="11dbf-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="11dbf-113">Message Text</span></span>|<span data-ttu-id="11dbf-114">La transacción actual no pudo confirmarse debido a un error serializable de validación.</span><span class="sxs-lookup"><span data-stu-id="11dbf-114">The current transaction failed to commit due to a serializable validation failure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="11dbf-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="11dbf-115">Explanation</span></span>  
 <span data-ttu-id="11dbf-116">La transacción encontró un error de validación y ahora está condenada.</span><span class="sxs-lookup"><span data-stu-id="11dbf-116">The transaction encountered a validation failure and is now doomed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="11dbf-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="11dbf-117">User Action</span></span>  
 <span data-ttu-id="11dbf-118">Vuelva a intentar la transacción con error.</span><span class="sxs-lookup"><span data-stu-id="11dbf-118">Retry the failed transaction.</span></span> <span data-ttu-id="11dbf-119">Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="11dbf-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11dbf-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11dbf-120">See Also</span></span>  
 [<span data-ttu-id="11dbf-121">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="11dbf-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
