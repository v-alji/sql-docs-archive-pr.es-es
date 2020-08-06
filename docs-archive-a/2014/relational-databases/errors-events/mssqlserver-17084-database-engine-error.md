---
title: MSSQLSERVER_17084 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17084 (Database Engine error)
ms.assetid: e579d104-3307-4edd-8587-b14ecbc02ed9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59b0fc3e0884ddd89809767a068b937b5c145f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675925"
---
# <a name="mssqlserver_17084"></a><span data-ttu-id="7aa8c-102">MSSQLSERVER_17084</span><span class="sxs-lookup"><span data-stu-id="7aa8c-102">MSSQLSERVER_17084</span></span>
    
## <a name="details"></a><span data-ttu-id="7aa8c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7aa8c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7aa8c-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="7aa8c-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="7aa8c-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="7aa8c-105">Event ID</span></span>|<span data-ttu-id="7aa8c-106">17084</span><span class="sxs-lookup"><span data-stu-id="7aa8c-106">17084</span></span>|  
|<span data-ttu-id="7aa8c-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="7aa8c-107">Event Source</span></span>|<span data-ttu-id="7aa8c-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7aa8c-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7aa8c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="7aa8c-109">Component</span></span>|<span data-ttu-id="7aa8c-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7aa8c-110">SQLEngine</span></span>|  
|<span data-ttu-id="7aa8c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7aa8c-111">Symbolic Name</span></span>|<span data-ttu-id="7aa8c-112">P3_ATOMIC_WITH_MISSING_OPTION</span><span class="sxs-lookup"><span data-stu-id="7aa8c-112">P3_ATOMIC_WITH_MISSING_OPTION</span></span>|  
|<span data-ttu-id="7aa8c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7aa8c-113">Message Text</span></span>|<span data-ttu-id="7aa8c-114">La cláusula WITH de la instrucción BEGIN ATOMIC debe especificar un valor para la opción '%ls'.</span><span class="sxs-lookup"><span data-stu-id="7aa8c-114">The WITH clause of BEGIN ATOMIC statement must specify a value for the option '%ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7aa8c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="7aa8c-115">Explanation</span></span>  
 <span data-ttu-id="7aa8c-116">La cláusula WITH de la instrucción BEGIN ATOMIC no especificó un valor para una opción.</span><span class="sxs-lookup"><span data-stu-id="7aa8c-116">The WITH clause of BEGIN ATOMIC statement did not specify a value for an option.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7aa8c-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7aa8c-117">User Action</span></span>  
 <span data-ttu-id="7aa8c-118">Los bloques `ATOMIC` requieren valores de las opciones `WITH` y `TRANSACTION ISOLATION LEVEL`de `LANGUAGE`.</span><span class="sxs-lookup"><span data-stu-id="7aa8c-118">`ATOMIC` blocks require values for the `WITH` options `TRANSACTION ISOLATION LEVEL` and `LANGUAGE`.</span></span> <span data-ttu-id="7aa8c-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7aa8c-119">For example::</span></span>  
  
```  
BEGIN ATOMIC WITH (TRANSACTION ISOLATION LEVEL = SNAPSHOT, LANGUAGE= N'us_english')  
```  
  
 <span data-ttu-id="7aa8c-120">Para obtener más información, vea [OLTP en memoria &#40;optimización en memoria&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="7aa8c-120">For more information, see [In-Memory OLTP &#40;In-Memory Optimization&#41;](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa8c-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7aa8c-121">See Also</span></span>  
 [<span data-ttu-id="7aa8c-122">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="7aa8c-122">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
