---
title: MSSQLSERVER_41359 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41359 (Database Engine error)
ms.assetid: 02b717c7-9170-4676-b0f6-4dec9eb5b5d4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cf45a117dcda0827672c6072c603a1fc0866a33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676502"
---
# <a name="mssqlserver_41359"></a><span data-ttu-id="14a42-102">MSSQLSERVER_41359</span><span class="sxs-lookup"><span data-stu-id="14a42-102">MSSQLSERVER_41359</span></span>
    
## <a name="details"></a><span data-ttu-id="14a42-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="14a42-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14a42-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="14a42-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="14a42-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="14a42-105">Event ID</span></span>|<span data-ttu-id="14a42-106">41359</span><span class="sxs-lookup"><span data-stu-id="14a42-106">41359</span></span>|  
|<span data-ttu-id="14a42-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="14a42-107">Event Source</span></span>|<span data-ttu-id="14a42-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="14a42-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="14a42-109">Componente</span><span class="sxs-lookup"><span data-stu-id="14a42-109">Component</span></span>|<span data-ttu-id="14a42-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="14a42-110">SQLEngine</span></span>|  
|<span data-ttu-id="14a42-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="14a42-111">Symbolic Name</span></span>|<span data-ttu-id="14a42-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="14a42-112">SQL_READ_COMMITTED_SNAPSHOT_NOT_SUPPORTED</span></span>|  
|<span data-ttu-id="14a42-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="14a42-113">Message Text</span></span>|<span data-ttu-id="14a42-114">Una consulta que tiene acceso a las tablas optimizadas en memoria con el nivel de aislamiento READ COMMITTED no puede tener acceso a las tablas basadas en disco cuando la opción de base de datos READ_COMMITTED_SNAPSHOT está establecida en ON.</span><span class="sxs-lookup"><span data-stu-id="14a42-114">A query that accesses memory optimized tables using the READ COMMITTED isolation level, cannot access disk based tables when the database option READ_COMMITTED_SNAPSHOT is set to ON.</span></span> <span data-ttu-id="14a42-115">Proporciona un nivel de aislamiento admitido para la tabla optimizada en memoria mediante una sugerencia de tabla, como WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="14a42-115">Provide a supported isolation level for the memory optimized table using a table hint, such as WITH (SNAPSHOT).</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="14a42-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="14a42-116">Explanation</span></span>  
 <span data-ttu-id="14a42-117">La base de datos con READ_COMMITTED_SNAPSHOT=ON no admite las transacciones que tienen acceso a las tablas optimizadas en memoria a las y tablas basadas en disco.</span><span class="sxs-lookup"><span data-stu-id="14a42-117">The database with READ_COMMITTED_SNAPSHOT=ON does not support the transactions that access both memory-optimized tables and disk based tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14a42-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="14a42-118">User Action</span></span>  
 <span data-ttu-id="14a42-119">Establezca READ_COMMITTED_SNAPSHOT en OFF o proporcione un nivel de aislamiento admitido para la tabla optimizada en memoria mediante una sugerencia de nivela de tabla, como WITH (SNAPSHOT).</span><span class="sxs-lookup"><span data-stu-id="14a42-119">Set READ_COMMITTED_SNAPSHOT to OFF or supply a supported isolation level for the memory-optimized table using a table-level hint, such as WITH (SNAPSHOT).</span></span> <span data-ttu-id="14a42-120">Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="14a42-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a42-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14a42-121">See Also</span></span>  
 [<span data-ttu-id="14a42-122">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="14a42-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
