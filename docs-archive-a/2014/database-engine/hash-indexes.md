---
title: Índices de hash | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: f4bdc9c1-7922-4fac-8183-d11ec58fec4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 05b8d1e3a5d92078cc2ec3fe7cd5b6d3fb5b47c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750126"
---
# <a name="hash-indexes"></a><span data-ttu-id="5350a-102">Índices hash</span><span class="sxs-lookup"><span data-stu-id="5350a-102">Hash Indexes</span></span>
  <span data-ttu-id="5350a-103">Los índices se utilizan como puntos de entrada para las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="5350a-103">Indexes are used as entry points for memory-optimized tables.</span></span> <span data-ttu-id="5350a-104">Leer filas de una tabla requiere un índice para buscar los datos en la memoria.</span><span class="sxs-lookup"><span data-stu-id="5350a-104">Reading rows from a table requires an index to locate the data in memory.</span></span>  
  
 <span data-ttu-id="5350a-105">Un índice hash consta de una colección de cubos organizados en una matriz.</span><span class="sxs-lookup"><span data-stu-id="5350a-105">A hash index consists of a collection of buckets organized in an array.</span></span> <span data-ttu-id="5350a-106">Una función hash asigna las claves de índice a los cubos correspondientes en el índice hash.</span><span class="sxs-lookup"><span data-stu-id="5350a-106">A hash function maps index keys to corresponding buckets in the hash index.</span></span> <span data-ttu-id="5350a-107">La ilustración siguiente muestra las tres claves de índice que se asignan a tres cubos distintos en el índice hash.</span><span class="sxs-lookup"><span data-stu-id="5350a-107">The following figure shows three index keys that are mapped to three different buckets in the hash index.</span></span> <span data-ttu-id="5350a-108">Con fines meramente ilustrativos, el nombre de función hash es f(x).</span><span class="sxs-lookup"><span data-stu-id="5350a-108">For illustration purposes the hash function name is f(x).</span></span>  
  
 <span data-ttu-id="5350a-109">![Claves de índice asignadas a diferentes cubos.](../../2014/database-engine/media/hekaton-tables-2.gif "Claves de índice asignadas a diferentes cubos.")</span><span class="sxs-lookup"><span data-stu-id="5350a-109">![Index keys mapped to different buckets.](../../2014/database-engine/media/hekaton-tables-2.gif "Index keys mapped to different buckets.")</span></span>  
  
 <span data-ttu-id="5350a-110">La función hash que se utiliza para los índices hash tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="5350a-110">The hashing function used for hash indexes has the following characteristics:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="5350a-111">tiene una función hash que se utiliza para todos los índices hash.</span><span class="sxs-lookup"><span data-stu-id="5350a-111">has one hash function that is used for all hash indexes.</span></span>  
  
-   <span data-ttu-id="5350a-112">La función hash es determinista.</span><span class="sxs-lookup"><span data-stu-id="5350a-112">The hash function is deterministic.</span></span> <span data-ttu-id="5350a-113">La misma clave de índice se asigna siempre al mismo cubo en el índice hash.</span><span class="sxs-lookup"><span data-stu-id="5350a-113">The same index key is always mapped to the same bucket in the hash index.</span></span>  
  
-   <span data-ttu-id="5350a-114">Se pueden asignar múltiples claves de índice al mismo depósito de hash.</span><span class="sxs-lookup"><span data-stu-id="5350a-114">Multiple index keys may be mapped to the same hash bucket.</span></span>  
  
-   <span data-ttu-id="5350a-115">La función hash está equilibrada, lo que significa que la distribución de los valores de clave de índice en los depósitos de hash sigue normalmente una distribución de Poisson.</span><span class="sxs-lookup"><span data-stu-id="5350a-115">The hash function is balanced, meaning that the distribution of index key values over hash buckets typically follows a Poisson distribution.</span></span>  
  
     <span data-ttu-id="5350a-116">La distribución de Poisson no es una distribución uniforme.</span><span class="sxs-lookup"><span data-stu-id="5350a-116">Poisson distribution is not an even distribution.</span></span> <span data-ttu-id="5350a-117">Los valores de clave de índice no se distribuyen uniformemente en cubos de hash.</span><span class="sxs-lookup"><span data-stu-id="5350a-117">Index key values are not evenly distributed in the hash buckets.</span></span> <span data-ttu-id="5350a-118">Por ejemplo, una distribución de Poisson de *n* claves de índice distintas sobre *n* depósitos de hash da como resultado aproximadamente un tercio de cubos vacíos, un tercio de cubos que contienen una clave de índice y el otro tercio que contiene dos claves de índice.</span><span class="sxs-lookup"><span data-stu-id="5350a-118">For example, a Poisson distribution of *n* distinct index keys over *n* hash buckets results in approximately one third empty buckets, one third of the buckets containing one index key, and the other third containing two index keys.</span></span> <span data-ttu-id="5350a-119">Un pequeño número de cubos contendrán más de dos claves.</span><span class="sxs-lookup"><span data-stu-id="5350a-119">A small number of buckets will contain more than two keys.</span></span>  
  
 <span data-ttu-id="5350a-120">Si dos claves de índice se asignan al mismo cubo de hash, hay un conflicto de hash.</span><span class="sxs-lookup"><span data-stu-id="5350a-120">If two index keys are mapped to the same hash bucket, there is a hash collision.</span></span> <span data-ttu-id="5350a-121">Un gran número de colisiones de valores hash puede tener un impacto en el rendimiento de las operaciones de lectura.</span><span class="sxs-lookup"><span data-stu-id="5350a-121">A large number of hash collisions can have a performance impact on read operations.</span></span>  
  
 <span data-ttu-id="5350a-122">La estructura de índice hash en memoria consta de una matriz de punteros de memoria.</span><span class="sxs-lookup"><span data-stu-id="5350a-122">The in-memory hash index structure consists of an array of memory pointers.</span></span> <span data-ttu-id="5350a-123">Cada cubo asigna un desplazamiento en esta matriz.</span><span class="sxs-lookup"><span data-stu-id="5350a-123">Each bucket maps to an offset in this array.</span></span> <span data-ttu-id="5350a-124">Cada cubo de la matriz señala a la primera fila del cubo de hash.</span><span class="sxs-lookup"><span data-stu-id="5350a-124">Each bucket in the array points to the first row in that hash bucket.</span></span> <span data-ttu-id="5350a-125">Cada fila del cubo señala a la siguiente fila, por lo que genera una cadena de filas para cada cubo de hash, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="5350a-125">Each row in the bucket points to the next row, thus resulting in a chain of rows for each hash bucket, as illustrated in the following figure.</span></span>  
  
 <span data-ttu-id="5350a-126">![Estructura de índice de hash en memoria.](../../2014/database-engine/media/hekaton-tables-3.gif "Estructura de índice de hash en memoria.")</span><span class="sxs-lookup"><span data-stu-id="5350a-126">![The in-memory hash index structure.](../../2014/database-engine/media/hekaton-tables-3.gif "The in-memory hash index structure.")</span></span>  
  
 <span data-ttu-id="5350a-127">La ilustración tiene tres cubos con filas.</span><span class="sxs-lookup"><span data-stu-id="5350a-127">The figure has three buckets with rows.</span></span> <span data-ttu-id="5350a-128">El segundo cubo de la parte superior contiene las tres filas rojas.</span><span class="sxs-lookup"><span data-stu-id="5350a-128">The second bucket from the top contains the three red rows.</span></span> <span data-ttu-id="5350a-129">El cuarto cubo contiene la única fila azul.</span><span class="sxs-lookup"><span data-stu-id="5350a-129">The fourth bucket contains the single blue row.</span></span> <span data-ttu-id="5350a-130">El cubo inferior contiene las dos filas verdes.</span><span class="sxs-lookup"><span data-stu-id="5350a-130">The bottom bucket contains the two green rows.</span></span> <span data-ttu-id="5350a-131">Estas podrían ser versiones diferentes de la misma fila.</span><span class="sxs-lookup"><span data-stu-id="5350a-131">These could be different versions of the same row.</span></span>  
  
 <span data-ttu-id="5350a-132">Para obtener más información acerca de los índices para tablas optimizadas para memoria, vea [Guidelines for Using Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md):</span><span class="sxs-lookup"><span data-stu-id="5350a-132">For more information about indexes for memory-optimized tables, see [Guidelines for Using Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5350a-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5350a-133">See Also</span></span>  
 [<span data-ttu-id="5350a-134">Índices de las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="5350a-134">Indexes on Memory-Optimized Tables</span></span>](../../2014/database-engine/indexes-on-memory-optimized-tables.md)  
  
  
