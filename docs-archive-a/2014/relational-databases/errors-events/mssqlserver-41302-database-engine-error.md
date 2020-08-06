---
title: MSSQLSERVER_41302 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41302 (Database Engine error)
ms.assetid: 01e75618-afec-4232-ba68-93ab7bc31003
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 751dac91378c002a7e6c6c619ddaf12be8173400
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671569"
---
# <a name="mssqlserver_41302"></a><span data-ttu-id="81473-102">MSSQLSERVER_41302</span><span class="sxs-lookup"><span data-stu-id="81473-102">MSSQLSERVER_41302</span></span>
    
## <a name="details"></a><span data-ttu-id="81473-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="81473-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="81473-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="81473-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="81473-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="81473-105">Event ID</span></span>|<span data-ttu-id="81473-106">41302</span><span class="sxs-lookup"><span data-stu-id="81473-106">41302</span></span>|  
|<span data-ttu-id="81473-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="81473-107">Event Source</span></span>|<span data-ttu-id="81473-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="81473-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="81473-109">Componente</span><span class="sxs-lookup"><span data-stu-id="81473-109">Component</span></span>|<span data-ttu-id="81473-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="81473-110">SQLEngine</span></span>|  
|<span data-ttu-id="81473-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="81473-111">Symbolic Name</span></span>|<span data-ttu-id="81473-112">WRITE_WRITE_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="81473-112">WRITE_WRITE_CONFLICT</span></span>|  
|<span data-ttu-id="81473-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="81473-113">Message Text</span></span>|<span data-ttu-id="81473-114">La transacción actual intentó actualizar un registro que se ha actualizado desde que esta transacción se inició.</span><span class="sxs-lookup"><span data-stu-id="81473-114">The current transaction attempted to update a record that has been updated since this transaction started.</span></span> <span data-ttu-id="81473-115">Se anuló la transacción.</span><span class="sxs-lookup"><span data-stu-id="81473-115">The transaction was aborted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="81473-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="81473-116">Explanation</span></span>  
 <span data-ttu-id="81473-117">La transacción encontró un conflicto de escritura contra escritura y la instrucción se terminó.</span><span class="sxs-lookup"><span data-stu-id="81473-117">The transaction encountered a write/write conflict and the statement terminated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="81473-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="81473-118">User Action</span></span>  
 <span data-ttu-id="81473-119">Intente de nuevo la operación posterior en otra transacción.</span><span class="sxs-lookup"><span data-stu-id="81473-119">Retry the operation later in a different transaction.</span></span> <span data-ttu-id="81473-120">Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="81473-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81473-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81473-121">See Also</span></span>  
 [<span data-ttu-id="81473-122">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="81473-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
