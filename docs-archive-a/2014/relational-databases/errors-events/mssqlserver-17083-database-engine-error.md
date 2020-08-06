---
title: MSSQLSERVER_17083 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17083 (Database Engine error)
ms.assetid: 6c83737d-0531-4fd9-88f6-2da5a150532d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 598cf9b0182178aa13a6d8b965ac10bedaaf5d15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675930"
---
# <a name="mssqlserver_17083"></a><span data-ttu-id="39a13-102">MSSQLSERVER_17083</span><span class="sxs-lookup"><span data-stu-id="39a13-102">MSSQLSERVER_17083</span></span>
    
## <a name="details"></a><span data-ttu-id="39a13-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="39a13-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39a13-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="39a13-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="39a13-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="39a13-105">Event ID</span></span>|<span data-ttu-id="39a13-106">17083</span><span class="sxs-lookup"><span data-stu-id="39a13-106">17083</span></span>|  
|<span data-ttu-id="39a13-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="39a13-107">Event Source</span></span>|<span data-ttu-id="39a13-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="39a13-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="39a13-109">Componente</span><span class="sxs-lookup"><span data-stu-id="39a13-109">Component</span></span>|<span data-ttu-id="39a13-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="39a13-110">SQLEngine</span></span>|  
|<span data-ttu-id="39a13-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="39a13-111">Symbolic Name</span></span>|<span data-ttu-id="39a13-112">P3_HEKATON_NOT_ATOMIC</span><span class="sxs-lookup"><span data-stu-id="39a13-112">P3_HEKATON_NOT_ATOMIC</span></span>|  
|<span data-ttu-id="39a13-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="39a13-113">Message Text</span></span>|<span data-ttu-id="39a13-114">El cuerpo de un procedimiento almacenado compilado de forma nativa debe ser un bloque ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="39a13-114">The body of a natively compiled stored procedure must be an ATOMIC block.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="39a13-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="39a13-115">Explanation</span></span>  
 <span data-ttu-id="39a13-116">El cuerpo de un procedimiento almacenado compilado de forma nativa no tenía un bloque ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="39a13-116">The body of a natively compiled stored procedure did not have an ATOMIC block.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="39a13-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="39a13-117">User Action</span></span>  
 <span data-ttu-id="39a13-118">Un procedimiento almacenado compilado de forma nativa debe incluir un bloque ATOMIC.</span><span class="sxs-lookup"><span data-stu-id="39a13-118">A natively compiled stored procedure must contain an ATOMIC block.</span></span> <span data-ttu-id="39a13-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="39a13-119">For example:</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="39a13-120">Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="39a13-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a13-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39a13-121">See Also</span></span>  
 [<span data-ttu-id="39a13-122">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="39a13-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
