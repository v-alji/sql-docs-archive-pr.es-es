---
title: MSSQLSERVER_41332 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41332 (Database Engine error)
ms.assetid: d3403c3e-d178-4006-b6c9-c18609562db5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72a87838673f07f7a40596517ab54533d944e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674870"
---
# <a name="mssqlserver_41332"></a><span data-ttu-id="1b9ce-102">MSSQLSERVER_41332</span><span class="sxs-lookup"><span data-stu-id="1b9ce-102">MSSQLSERVER_41332</span></span>
    
## <a name="details"></a><span data-ttu-id="1b9ce-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1b9ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1b9ce-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="1b9ce-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="1b9ce-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1b9ce-105">Event ID</span></span>|<span data-ttu-id="1b9ce-106">41332</span><span class="sxs-lookup"><span data-stu-id="1b9ce-106">41332</span></span>|  
|<span data-ttu-id="1b9ce-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="1b9ce-107">Event Source</span></span>|<span data-ttu-id="1b9ce-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1b9ce-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1b9ce-109">Componente</span><span class="sxs-lookup"><span data-stu-id="1b9ce-109">Component</span></span>|<span data-ttu-id="1b9ce-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1b9ce-110">SQLEngine</span></span>|  
|<span data-ttu-id="1b9ce-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1b9ce-111">Symbolic Name</span></span>|<span data-ttu-id="1b9ce-112">SQL_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="1b9ce-112">SQL_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="1b9ce-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1b9ce-113">Message Text</span></span>|<span data-ttu-id="1b9ce-114">No se puede tener acceso ni crear tablas optimizadas en memoria ni procedimientos almacenados compilados de forma nativa cuando la configuración de TRANSACTION ISOLATION LEVEL para la sesión se ha establecido en SNAPSHOT.</span><span class="sxs-lookup"><span data-stu-id="1b9ce-114">Memory optimized tables and natively compiled stored procedures cannot be accessed or created when the session TRANSACTION ISOLATION LEVEL is set to SNAPSHOT.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1b9ce-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="1b9ce-115">Explanation</span></span>  
 <span data-ttu-id="1b9ce-116">La transacción se inició con el nivel de aislamiento de instantánea y luego se intentó utilizar una función incompatible.</span><span class="sxs-lookup"><span data-stu-id="1b9ce-116">The transaction was started in snapshot isolation level and then attempted to use an incompatible feature.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1b9ce-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1b9ce-117">User Action</span></span>  
 <span data-ttu-id="1b9ce-118">Inicie la transacción con otro nivel de aislamiento.</span><span class="sxs-lookup"><span data-stu-id="1b9ce-118">Start the transaction with a different isolation level.</span></span> <span data-ttu-id="1b9ce-119">Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="1b9ce-119">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b9ce-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b9ce-120">See Also</span></span>  
 [<span data-ttu-id="1b9ce-121">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="1b9ce-121">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
