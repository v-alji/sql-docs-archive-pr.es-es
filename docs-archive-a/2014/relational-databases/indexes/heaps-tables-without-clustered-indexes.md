---
title: Montones (tablas sin índices agrupados) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- heaps
ms.assetid: df5c4dfb-d372-4d0f-859a-a2d2533ee0d7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2a39bac2e0352f2adc7749e980d5cc91044f8ab2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677098"
---
# <a name="heaps-tables-without-clustered-indexes"></a><span data-ttu-id="9d5ba-102">Montones (tablas sin índices clúster)</span><span class="sxs-lookup"><span data-stu-id="9d5ba-102">Heaps (Tables without Clustered Indexes)</span></span>
  <span data-ttu-id="9d5ba-103">Un montón es una tabla que no tiene un índice clúster.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-103">A heap is a table without a clustered index.</span></span> <span data-ttu-id="9d5ba-104">En las tablas almacenadas, se pueden crear uno o varios índices no clúster como un montón.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-104">One or more nonclustered indexes can be created on tables stored as a heap.</span></span> <span data-ttu-id="9d5ba-105">Los datos se almacenan en el montón sin especificar un orden.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-105">Data is stored in the heap without specifying an order.</span></span> <span data-ttu-id="9d5ba-106">Normalmente, en un principio los datos se almacenan en el orden en el que las filas se insertan en la tabla, pero [!INCLUDE[ssDE](../../includes/ssde-md.md)] puede mover los datos en el montón para almacenar las filas de forma eficaz, de modo que no se puede predecir el orden de los datos.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-106">Usually data is initially stored in the order in which is the rows are inserted into the table, but the [!INCLUDE[ssDE](../../includes/ssde-md.md)] can move data around in the heap to store the rows efficiently; so the data order cannot be predicted.</span></span> <span data-ttu-id="9d5ba-107">Para garantizar el orden de las filas que se devuelven de un montón, debe usar la cláusula `ORDER BY`.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-107">To guarantee the order of rows returned from a heap, you must use the `ORDER BY` clause.</span></span> <span data-ttu-id="9d5ba-108">Para especificar el orden de almacenamiento de las filas, cree un índice clúster en la tabla, de modo que la tabla no sea un montón.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-108">To specify the order for storage of the rows, create a clustered index on the table, so that the table is not a heap.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9d5ba-109">A veces, hay buenos motivos para dejar una tabla como montón en lugar de crear un índice clúster, pero para usar los montones de forma eficaz se requieren conocimientos avanzados.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-109">There are sometimes good reasons to leave a table as a heap instead of creating a clustered index, but using heaps effectively is an advanced skill.</span></span> <span data-ttu-id="9d5ba-110">La mayoría de las tablas deben tener un índice clúster cuidadosamente elegido a menos que exista un buen motivo para dejar la tabla como un montón.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-110">Most tables should have a carefully chosen clustered index unless a good reason exists for leaving the table as a heap.</span></span>  
  
## <a name="when-to-use-a-heap"></a><span data-ttu-id="9d5ba-111">Cuándo se usa un montón</span><span class="sxs-lookup"><span data-stu-id="9d5ba-111">When to Use a Heap</span></span>  
 <span data-ttu-id="9d5ba-112">Si una tabla es un montón y no tiene ningún índice no clúster, debe examinarse la tabla completa (recorrido de tabla) cuando se busca una fila.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-112">If a table is a heap and does not have any nonclustered indexes, then the entire table must be examined (a table scan) to find any row.</span></span> <span data-ttu-id="9d5ba-113">Esto puede resultar aceptable si la tabla es pequeña, como una lista con las 12 oficinas regionales de una empresa.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-113">This can be acceptable when the table is tiny, such as a list of the 12 regional offices of a company.</span></span>  
  
 <span data-ttu-id="9d5ba-114">Cuando una tabla se almacena como un montón, las filas individuales se identifican mediante una referencia a un identificador de fila (RID) que se compone del número de archivo, el número de páginas de datos y el espacio de la página.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-114">When a table is stored as a heap, individual rows are identified by reference to a row identifier (RID) consisting of the file number, data page number, and slot on the page.</span></span> <span data-ttu-id="9d5ba-115">El identificador de fila es una estructura pequeña y eficaz.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-115">The row id is a small and efficient structure.</span></span> <span data-ttu-id="9d5ba-116">A veces, los arquitectos de datos usan montones cuando el acceso a los datos se realiza siempre a través de índices no clúster y el RID es menor que la clave de índice clúster.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-116">Sometimes data architects use heaps when data is always accessed through nonclustered indexes and the RID is smaller than a clustered index key.</span></span>  
  
## <a name="when-not-to-use-a-heap"></a><span data-ttu-id="9d5ba-117">Cuándo no se usa un montón</span><span class="sxs-lookup"><span data-stu-id="9d5ba-117">When Not to Use a Heap</span></span>  
 <span data-ttu-id="9d5ba-118">No use un montón cuando los datos se devuelvan con frecuencia ordenados.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-118">Do not use a heap when the data is frequently returned in a sorted order.</span></span> <span data-ttu-id="9d5ba-119">Un índice clúster en la columna de ordenación podría impedir la operación de ordenación.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-119">A clustered index on the sorting column could avoid the sorting operation.</span></span>  
  
 <span data-ttu-id="9d5ba-120">No use un montón cuando los datos se agrupan juntos a menudo.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-120">Do not use a heap when the data is frequently grouped together.</span></span> <span data-ttu-id="9d5ba-121">Los datos deben estar ordenados antes de que se agrupen y un índice clúster en la columna de ordenación podría impedir la operación de ordenación.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-121">Data must be sorted before it is grouped, and a clustered index on the sorting column could avoid the sorting operation.</span></span>  
  
 <span data-ttu-id="9d5ba-122">No use un montón cuando a menudo se consulten rangos de datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-122">Do not use a heap when ranges of data are frequently queried from the table.</span></span>  <span data-ttu-id="9d5ba-123">Un índice clúster en la columna de rango impedirá que se ordene el montón completo.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-123">A clustered index on the range column will avoid sorting the entire heap.</span></span>  
  
 <span data-ttu-id="9d5ba-124">No use un montón cuando no haya índices no clúster y la tabla sea grande.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-124">Do not use a heap when there are no nonclustered indexes and the table is large.</span></span> <span data-ttu-id="9d5ba-125">En un montón, deben leerse todas las filas del montón para buscar una fila.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-125">In a heap, all rows of the heap must be read to find any row.</span></span>  
  
## <a name="managing-heaps"></a><span data-ttu-id="9d5ba-126">Administrar montones</span><span class="sxs-lookup"><span data-stu-id="9d5ba-126">Managing Heaps</span></span>  
 <span data-ttu-id="9d5ba-127">Para crear un montón, cree una tabla sin un índice clúster.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-127">To create a heap, create a table without a clustered index.</span></span> <span data-ttu-id="9d5ba-128">Si la tabla ya tiene un índice clúster, quite el índice clúster para convertir de nuevo la tabla en un montón.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-128">If a table already has a clustered index, drop the clustered index to return the table to a heap.</span></span>  
  
 <span data-ttu-id="9d5ba-129">Para quitar un montón, cree un índice clúster en el montón.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-129">To remove a heap, create a clustered index on the heap.</span></span>  
  
 <span data-ttu-id="9d5ba-130">Para volver a crear un montón a fin de recuperar el espacio desaprovechado, cree un índice clúster en el montón y quítelo después.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-130">To rebuild a heap to reclaim wasted space, create a clustered index on the heap, and then drop that clustered index.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="9d5ba-131">Para crear o quitar índices clúster, es necesario volver a escribir toda la tabla.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-131">Creating or dropping clustered indexes requires rewriting the entire table.</span></span> <span data-ttu-id="9d5ba-132">Si la tabla tiene índices no clúster, todos los índices no clúster deberán volver a crearse cada vez que cambie el índice clúster.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-132">If the table has nonclustered indexes, all the nonclustered indexes must all be recreated whenever the clustered index is changed.</span></span> <span data-ttu-id="9d5ba-133">Por tanto, al convertir un montón en una estructura de índice agrupado o viceversa, puede necesitarse mucho tiempo y gran cantidad de espacio para reordenar los datos en tempdb.</span><span class="sxs-lookup"><span data-stu-id="9d5ba-133">Therefore, changing from a heap to a clustered index structure or back can take a lot of time and require disk space for reordering data in tempdb.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="9d5ba-134">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="9d5ba-134">Related Content</span></span>  
 [<span data-ttu-id="9d5ba-135">CREATE INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d5ba-135">CREATE INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-index-transact-sql)  
  
 [<span data-ttu-id="9d5ba-136">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d5ba-136">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
 [<span data-ttu-id="9d5ba-137">Índices agrupados y no agrupados descritos</span><span class="sxs-lookup"><span data-stu-id="9d5ba-137">Clustered and Nonclustered Indexes Described</span></span>](clustered-and-nonclustered-indexes-described.md)  
  
  
