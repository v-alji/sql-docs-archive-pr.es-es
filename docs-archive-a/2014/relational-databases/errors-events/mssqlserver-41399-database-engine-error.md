---
title: MSSQLSERVER_41399 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41399 (Database Engine error)
ms.assetid: 5e5acb07-16ca-4329-8210-cd2bab0c904f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e134cbc8b39a3c65d9c515183243f0b4caed434
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671568"
---
# <a name="mssqlserver_41399"></a><span data-ttu-id="95b8a-102">MSSQLSERVER_41399</span><span class="sxs-lookup"><span data-stu-id="95b8a-102">MSSQLSERVER_41399</span></span>
    
## <a name="details"></a><span data-ttu-id="95b8a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="95b8a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="95b8a-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="95b8a-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="95b8a-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="95b8a-105">Event ID</span></span>|<span data-ttu-id="95b8a-106">41399</span><span class="sxs-lookup"><span data-stu-id="95b8a-106">41399</span></span>|  
|<span data-ttu-id="95b8a-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="95b8a-107">Event Source</span></span>|<span data-ttu-id="95b8a-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="95b8a-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="95b8a-109">Componente</span><span class="sxs-lookup"><span data-stu-id="95b8a-109">Component</span></span>|<span data-ttu-id="95b8a-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="95b8a-110">SQLEngine</span></span>|  
|<span data-ttu-id="95b8a-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="95b8a-111">Symbolic Name</span></span>|<span data-ttu-id="95b8a-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="95b8a-112">MAX_SORT_ROW_WIDTH_EXCEEDED</span></span>|  
|<span data-ttu-id="95b8a-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="95b8a-113">Message Text</span></span>|<span data-ttu-id="95b8a-114">La operación de ordenación es demasiado compleja.</span><span class="sxs-lookup"><span data-stu-id="95b8a-114">The sort operation is too complex.</span></span> <span data-ttu-id="95b8a-115">Consulte los Libros en pantalla de SQL Server para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="95b8a-115">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="95b8a-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="95b8a-116">Explanation</span></span>  
 <span data-ttu-id="95b8a-117">Ordenar el resultado de las operaciones de combinación y agregación aumenta la complejidad de la operación de ordenación, ya que aumenta el tamaño de la fila en el búfer de ordenación.</span><span class="sxs-lookup"><span data-stu-id="95b8a-117">Sorting the result of join and aggregation operations increases the complexity of the sort operation by increasing the size of the row in the sort buffer.</span></span> <span data-ttu-id="95b8a-118">Este error indica que el tamaño de la fila es mayor que el tamaño máximo admitido por el operador sort en los procedimientos almacenados compilados de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="95b8a-118">This error means that the size of the row is larger than the maximum size supported by the sort operator in natively compiled stored procedures.</span></span> <span data-ttu-id="95b8a-119">Tenga en cuenta que el tamaño de una fila en el búfer de ordenación solo lo determinan el número de combinaciones y el número y el tipo de funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="95b8a-119">Note that the size of a row in the sort buffer is determined solely by the number of joins and the number and type of aggregate functions.</span></span> <span data-ttu-id="95b8a-120">El tamaño de las filas de las tablas base no afecta al tamaño de la fila en e búfer.</span><span class="sxs-lookup"><span data-stu-id="95b8a-120">The size of the rows in the base tables does not affect the size of the row in the buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="95b8a-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="95b8a-121">User Action</span></span>  
 <span data-ttu-id="95b8a-122">Reduzca la complejidad de la consulta quitando combinaciones o funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="95b8a-122">Decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95b8a-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95b8a-123">See Also</span></span>  
 [<span data-ttu-id="95b8a-124">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="95b8a-124">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
