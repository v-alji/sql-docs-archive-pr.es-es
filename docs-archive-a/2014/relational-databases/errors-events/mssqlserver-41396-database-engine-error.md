---
title: MSSQLSERVER_41396 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 41396 (Database Engine error)
ms.assetid: 4ff04042-8367-46f3-8a16-c94682d6eedb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2386c805b61631c9b843753d74ba6616e7344223
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745768"
---
# <a name="mssqlserver_41396"></a><span data-ttu-id="e89de-102">MSSQLSERVER_41396</span><span class="sxs-lookup"><span data-stu-id="e89de-102">MSSQLSERVER_41396</span></span>
    
## <a name="details"></a><span data-ttu-id="e89de-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="e89de-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e89de-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="e89de-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="e89de-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="e89de-105">Event ID</span></span>|<span data-ttu-id="e89de-106">41396</span><span class="sxs-lookup"><span data-stu-id="e89de-106">41396</span></span>|  
|<span data-ttu-id="e89de-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="e89de-107">Event Source</span></span>|<span data-ttu-id="e89de-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e89de-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e89de-109">Componente</span><span class="sxs-lookup"><span data-stu-id="e89de-109">Component</span></span>|<span data-ttu-id="e89de-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e89de-110">SQLEngine</span></span>|  
|<span data-ttu-id="e89de-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="e89de-111">Symbolic Name</span></span>|<span data-ttu-id="e89de-112">MAX_SORT_ROWS_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="e89de-112">MAX_SORT_ROWS_EXCEEDED</span></span>|  
|<span data-ttu-id="e89de-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="e89de-113">Message Text</span></span>|<span data-ttu-id="e89de-114">La operación de ordenación ha superado el límite del búfer.</span><span class="sxs-lookup"><span data-stu-id="e89de-114">The sort operation exceeded the buffer limit.</span></span> <span data-ttu-id="e89de-115">La ejecución del procedimiento almacenado se anuló.</span><span class="sxs-lookup"><span data-stu-id="e89de-115">The stored procedure execution was aborted.</span></span> <span data-ttu-id="e89de-116">Consulte los Libros en pantalla de SQL Server para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e89de-116">Consult SQL Server Books Online for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e89de-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="e89de-117">Explanation</span></span>  
 <span data-ttu-id="e89de-118">Los procedimientos almacenados compilados de forma nativa realizan operaciones de ordenación en memoria.</span><span class="sxs-lookup"><span data-stu-id="e89de-118">Natively compiled stored procedures perform sort operations in memory.</span></span> <span data-ttu-id="e89de-119">Hay un límite en cuanto al tamaño del búfer de ordenación.</span><span class="sxs-lookup"><span data-stu-id="e89de-119">There is a limit on the size of the sort buffer.</span></span> <span data-ttu-id="e89de-120">Este error indica que el tamaño del búfer de ordenación supera este límite.</span><span class="sxs-lookup"><span data-stu-id="e89de-120">This error means that the size of the sort buffer exceeds this limit.</span></span> <span data-ttu-id="e89de-121">La operación de ordenación y la ejecución del procedimiento almacenado se han anulado.</span><span class="sxs-lookup"><span data-stu-id="e89de-121">The sort operation and the stored procedure execution aborted.</span></span>  
  
 <span data-ttu-id="e89de-122">El tamaño de cada fila o entrada del búfer de ordenación lo determinan el número de filas ordenadas junto con el número de combinaciones y el número y el tipo de funciones de agregado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="e89de-122">The size of each row or entry in the sort buffer is determined by the number of rows sorted as well as the number of joins and the number and type of aggregate functions in the query.</span></span> <span data-ttu-id="e89de-123">Si simplifica la consulta, puede reducir el tamaño de cada fila, con lo que cabrán más filas en el búfer de ordenación.</span><span class="sxs-lookup"><span data-stu-id="e89de-123">By simplifying the query, you can reduce the size of each row thereby fitting more rows in the sort buffer.</span></span> <span data-ttu-id="e89de-124">El tamaño de las filas de las tablas base no afecta al tamaño de cada fila o entrada del búfer de ordenación.</span><span class="sxs-lookup"><span data-stu-id="e89de-124">The size of the rows in the base tables does not affect the size of each row or entry in the sort buffer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e89de-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="e89de-125">User Action</span></span>  
 <span data-ttu-id="e89de-126">Seleccione menos filas o reduzca la complejidad de la consulta quitando combinaciones o funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="e89de-126">Select fewer rows or decrease the complexity of the query by removing joins or aggregate functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e89de-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e89de-127">See Also</span></span>  
 [<span data-ttu-id="e89de-128">OLTP en memoria &#40;optimización en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="e89de-128">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
