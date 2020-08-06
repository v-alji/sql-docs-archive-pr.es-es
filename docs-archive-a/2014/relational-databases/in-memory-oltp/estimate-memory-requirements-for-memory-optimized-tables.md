---
title: Estimar los requisitos de memoria para las tablas con optimización para memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5c5cc1fc-1fdf-4562-9443-272ad9ab5ba8
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5c5218a96d3650cbae22501ab2794b1b553996b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748794"
---
# <a name="estimate-memory-requirements-for-memory-optimized-tables"></a><span data-ttu-id="4f826-102">Estimar los requisitos de memoria para las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="4f826-102">Estimate Memory Requirements for Memory-Optimized Tables</span></span>
  <span data-ttu-id="4f826-103">Si va a crear una nueva [!INCLUDE[hek_2](../../includes/hek-2-md.md)] tabla optimizada para memoria o migrar una tabla basada en disco existente a una tabla optimizada para memoria, es importante tener una estimación razonable de las necesidades de memoria de cada tabla para poder aprovisionar el servidor con memoria suficiente.</span><span class="sxs-lookup"><span data-stu-id="4f826-103">Whether you are creating a new [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized table or migrating an existing disk-based table to a memory-optimized table, it is important to have a reasonable estimate of each table's memory needs so you can provision the server with sufficient memory.</span></span> <span data-ttu-id="4f826-104">En esta sección se describe cómo calcular la cantidad de memoria necesaria para almacenar los datos de una tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="4f826-104">This section describes how to estimate the amount of memory that you need to hold data for a memory-optimized table.</span></span>  
  
 <span data-ttu-id="4f826-105">Si va a realizar la migración desde tablas basadas en disco a tablas optimizadas para memoria, antes de continuar en este tema, vea el tema [Determinar si una tabla o un procedimiento almacenado se debe pasar a OLTP en memoria](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) para obtener información sobre qué tablas son más adecuadas para la migración.</span><span class="sxs-lookup"><span data-stu-id="4f826-105">If you are contemplating migrating from disk-based tables to memory-optimized tables, before you proceed in this topic, see the topic [Determining if a Table or Stored Procedure Should Be Ported to In-Memory OLTP](determining-if-a-table-or-stored-procedure-should-be-ported-to-in-memory-oltp.md) for guidance on which tables are best to migrate.</span></span> <span data-ttu-id="4f826-106">Todos los temas de [Migrar a OLTP en memoria](migrating-to-in-memory-oltp.md) ofrecen instrucciones sobre la migración de tablas basadas en disco a tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="4f826-106">All the topics under [Migrating to In-Memory OLTP](migrating-to-in-memory-oltp.md) provide guidance on migrating from disk-based to memory-optimized tables.</span></span>  
  
## <a name="sections-in-this-topic"></a><span data-ttu-id="4f826-107">Secciones de este tema</span><span class="sxs-lookup"><span data-stu-id="4f826-107">Sections in this topic</span></span>  
  
-   [<span data-ttu-id="4f826-108">tabla optimizada para memoria de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f826-108">Example memory-optimized table</span></span>](#bkmk_ExampleTable)  
  
-   [<span data-ttu-id="4f826-109">Memoria para la tabla</span><span class="sxs-lookup"><span data-stu-id="4f826-109">Memory for the table</span></span>](#bkmk_MemoryForTable)  
  
-   [<span data-ttu-id="4f826-110">Memoria para índices</span><span class="sxs-lookup"><span data-stu-id="4f826-110">Memory for indexes</span></span>](#bkmk_IndexMeemory)  
  
-   [<span data-ttu-id="4f826-111">Memoria para versiones de fila</span><span class="sxs-lookup"><span data-stu-id="4f826-111">Memory for row versioning</span></span>](#bkmk_MemoryForRowVersions)  
  
-   [<span data-ttu-id="4f826-112">Memoria para variables de tabla</span><span class="sxs-lookup"><span data-stu-id="4f826-112">Memory for table variables</span></span>](#bkmk_TableVariables)  
  
-   [<span data-ttu-id="4f826-113">Memoria para el crecimiento</span><span class="sxs-lookup"><span data-stu-id="4f826-113">Memory for growth</span></span>](#bkmk_MemoryForGrowth)  
  
##  <a name="example-memory-optimized-table"></a><a name="bkmk_ExampleTable"></a> <span data-ttu-id="4f826-114">tabla optimizada para memoria de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f826-114">Example memory-optimized table</span></span>  
 <span data-ttu-id="4f826-115">Considere el esquema de tabla optimizada para memoria siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f826-115">Consider the following memory-optimized table schema:</span></span>  
  
```sql  
  
CREATE TABLE t_hk (  
col1 int NOT NULL PRIMARY KEY NONCLUSTERED,  
col2 int NOT NULL INDEX t1c2_index   
     HASH WITH (bucket_count = 5000000),  
col3 int NOT NULL INDEX t1c3_index   
     HASH WITH (bucket_count = 5000000),  
col4 int NOT NULL INDEX t1c4_index   
     HASH WITH (bucket_count = 5000000),  
col5 int NOT NULL INDEX t1c5_index NONCLUSTERED,  
col6 char (50) NOT NULL,  
col7 char (50) NOT NULL,   
col8 char (30) NOT NULL,   
col9 char (50) NOT NULL  
     WITH (memory_optimized = on)  
GO  
  
```  
  
 <span data-ttu-id="4f826-116">Con este esquema determinaremos la memoria mínima necesaria para esta tabla optimizada para memoria.</span><span class="sxs-lookup"><span data-stu-id="4f826-116">Using this schema we will determine the minimum memory needed for this memory-optimized table.</span></span>  
  
##  <a name="memory-for-the-table"></a><a name="bkmk_MemoryForTable"></a> <span data-ttu-id="4f826-117">Memoria para la tabla</span><span class="sxs-lookup"><span data-stu-id="4f826-117">Memory for the table</span></span>  
 <span data-ttu-id="4f826-118">Una fila de una tabla optimizada para memoria consta de tres partes:</span><span class="sxs-lookup"><span data-stu-id="4f826-118">A memory-optimized table row is comprised of three parts:</span></span>  
  
-   <span data-ttu-id="4f826-119">**Marcas de tiempo** </span><span class="sxs-lookup"><span data-stu-id="4f826-119">**Timestamps** </span></span>  
    <span data-ttu-id="4f826-120">Encabezado de fila/marcas de tiempo = 24 bytes.</span><span class="sxs-lookup"><span data-stu-id="4f826-120">Row header/timestamps = 24 bytes.</span></span>  
  
-   <span data-ttu-id="4f826-121">**Punteros de índice** </span><span class="sxs-lookup"><span data-stu-id="4f826-121">**Index pointers** </span></span>  
    <span data-ttu-id="4f826-122">Para cada índice hash de la tabla, cada fila tiene un puntero de direcciones de 8 bytes a la siguiente fila del índice.</span><span class="sxs-lookup"><span data-stu-id="4f826-122">For each hash index in the table, each row has an 8-byte address pointer to the next row in the index.</span></span>  <span data-ttu-id="4f826-123">Puesto que hay 4 índices, cada fila asignará 32 bytes para los punteros de índice (un puntero de 8 bytes para cada índice).</span><span class="sxs-lookup"><span data-stu-id="4f826-123">Since there are 4 indexes, each row will allocate 32 bytes for index pointers (an 8 byte pointer for each index).</span></span>  
  
-   <span data-ttu-id="4f826-124">**Datos** </span><span class="sxs-lookup"><span data-stu-id="4f826-124">**Data** </span></span>  
    <span data-ttu-id="4f826-125">El tamaño de la parte de datos de la fila se determina sumando el tamaño del tipo de cada columna de datos.</span><span class="sxs-lookup"><span data-stu-id="4f826-125">The size of the data portion of the row is determined by summing the type size for each data column.</span></span>  <span data-ttu-id="4f826-126">En nuestra tabla tenemos cinco enteros de 4 bytes, tres columnas de caracteres de 50 bytes y una columna de caracteres de 30 bytes.</span><span class="sxs-lookup"><span data-stu-id="4f826-126">In our table we have five 4-byte integers, three 50-byte character columns, and one 30-byte character column.</span></span>  <span data-ttu-id="4f826-127">Por tanto, la parte de datos de cada fila es 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50 o 200 bytes.</span><span class="sxs-lookup"><span data-stu-id="4f826-127">Therefore the data portion of each row is 4 + 4 + 4 + 4 + 4 + 50 + 50 + 30 + 50 or 200 bytes.</span></span>  
  
 <span data-ttu-id="4f826-128">A continuación se muestra un cálculo de tamaño para 5.000.000 filas (5 millones de filas) en una tabla optimizada para memoria:</span><span class="sxs-lookup"><span data-stu-id="4f826-128">The following is a size computation for 5,000,000 (5 million) rows in a memory-optimized table.</span></span> <span data-ttu-id="4f826-129">La memoria total utilizada por las filas de datos se calcula de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f826-129">The total memory used by data rows is estimated as follows:</span></span>  
  
 <span data-ttu-id="4f826-130">**Memoria para las filas de la tabla**</span><span class="sxs-lookup"><span data-stu-id="4f826-130">**Memory for the table's rows**</span></span>  
  
 <span data-ttu-id="4f826-131">Según se desprende de los cálculos anteriores, el tamaño de cada fila de la tabla optimizada para memoria es 24 + 32 + 200, o 256 bytes.</span><span class="sxs-lookup"><span data-stu-id="4f826-131">From the above calculations, the size of each row in the memory-optimized table is 24 + 32 + 200, or 256 bytes.</span></span>  <span data-ttu-id="4f826-132">Como tenemos 5 millones de filas, la tabla usará 5 000 000 \* 256 bytes, o 1 280 000 000 bytes, aproximadamente 1,28 GB.</span><span class="sxs-lookup"><span data-stu-id="4f826-132">Since we have 5 million rows, the table will consume 5,000,000 \* 256 bytes, or 1,280,000,000 bytes - approximately 1.28 GB.</span></span>  
  
##  <a name="memory-for-indexes"></a><a name="bkmk_IndexMeemory"></a> <span data-ttu-id="4f826-133">Memoria para índices</span><span class="sxs-lookup"><span data-stu-id="4f826-133">Memory for indexes</span></span>  
 <span data-ttu-id="4f826-134">**Memoria para cada índice hash**</span><span class="sxs-lookup"><span data-stu-id="4f826-134">**Memory for each hash index**</span></span>  
  
 <span data-ttu-id="4f826-135">Cada índice hash es una matriz hash de punteros de direcciones de 8 bytes.</span><span class="sxs-lookup"><span data-stu-id="4f826-135">Each hash index is a hash array of 8-byte address pointers.</span></span>  <span data-ttu-id="4f826-136">El tamaño de la matriz se determina mejor con el número de valores de índice único para ese índice; por ejemplo, el número de valores únicos Col2 es un buen punto de partida para el tamaño de matriz de t1c2_index.</span><span class="sxs-lookup"><span data-stu-id="4f826-136">The size of the array is best determined by the number of unique index values for that index - e.g., the number of unique Col2 values is a good starting point for the array size for the t1c2_index.</span></span> <span data-ttu-id="4f826-137">Una matriz hash que es demasiado grande desperdicia memoria.</span><span class="sxs-lookup"><span data-stu-id="4f826-137">A hash array that is too big wastes memory.</span></span>  <span data-ttu-id="4f826-138">Una matriz hash que es demasiado pequeña reduce el rendimiento, ya que habrá demasiadas colisiones de valores de índice que aplican el algoritmo hash al mismo índice.</span><span class="sxs-lookup"><span data-stu-id="4f826-138">A hash array that is too small slows performance since there will be too many collisions by index values that hash to the same index.</span></span>  
  
 <span data-ttu-id="4f826-139">Los índices hash consiguen búsquedas de igualdad muy rápidas, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4f826-139">Hash indexes achieve very fast equality lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 = 3  
  
```  
  
 <span data-ttu-id="4f826-140">Los índices no clúster son más rápidos para búsquedas de intervalo como:</span><span class="sxs-lookup"><span data-stu-id="4f826-140">Nonclustered indexes are faster for range lookups such as:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE Col2 >= 3  
  
```  
  
 <span data-ttu-id="4f826-141">Si va a migrar una tabla basada en disco, puede usar lo siguiente para determinar el número de valores únicos para el índice t1c2_index.</span><span class="sxs-lookup"><span data-stu-id="4f826-141">If you are migrating a disk-based table you can use the following to determine the number of unique values for the index t1c2_index.</span></span>  
  
```sql  
  
SELECT COUNT(DISTINCT [Col2])  
  FROM t_hk  
  
```  
  
 <span data-ttu-id="4f826-142">Si va a crear una tabla, tendrá que estimar el tamaño de la matriz o recopilar datos de la prueba antes de la implementación.</span><span class="sxs-lookup"><span data-stu-id="4f826-142">If you are creating a new table, you'll need to estimate the array size or gather data from your testing prior to deployment.</span></span>  
  
 <span data-ttu-id="4f826-143">Para obtener información sobre cómo funcionan los índices de hash en las tablas optimizadas para memoria de [!INCLUDE[hek_2](../../includes/hek-2-md.md)] , vea [Indexes for Memory-Optimized Tables (Índices para tablas optimizadas para memoria)](../../database-engine/hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="4f826-143">For information on how hash indexes work in [!INCLUDE[hek_2](../../includes/hek-2-md.md)] memory-optimized tables, see [Hash Indexes](../../database-engine/hash-indexes.md).</span></span>  
  
 <span data-ttu-id="4f826-144">**Nota:** No se puede cambiar el tamaño de la matriz de índices de hash sobre la marcha.</span><span class="sxs-lookup"><span data-stu-id="4f826-144">**Note:** You cannot change the hash index array size on the fly.</span></span> <span data-ttu-id="4f826-145">Para cambiar el tamaño de la matriz de índices hash debe quitar la tabla, cambiar el valor de bucket_count y volver a crear la tabla.</span><span class="sxs-lookup"><span data-stu-id="4f826-145">To change the hash index array size you must drop the table, change the bucket_count value and recreate the table.</span></span>  
  
 <span data-ttu-id="4f826-146">**Establecer el tamaño de la matriz de índices hash**</span><span class="sxs-lookup"><span data-stu-id="4f826-146">**Setting the hash index array size**</span></span>  
  
 <span data-ttu-id="4f826-147">El tamaño de la matriz hash se establece mediante `(bucket_count= <value>)` donde \<value> es un valor entero mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="4f826-147">The hash array size is set by `(bucket_count= <value>)` where \<value> is an integer value greater than zero.</span></span> <span data-ttu-id="4f826-148">Si \<value> no es una potencia de 2, el valor real de bucket_count se redondea a la siguiente potencia más cercana de 2.</span><span class="sxs-lookup"><span data-stu-id="4f826-148">If \<value> is not a power of 2, the actual bucket_count is rounded up to the next closest power of 2.</span></span>  <span data-ttu-id="4f826-149">En la tabla de ejemplo, (bucket_count = 5 millones), dado que 5 millones no es una potencia de 2, el número de depósitos real se redondea hasta 8.388.608 (2<sup>23</sup>).</span><span class="sxs-lookup"><span data-stu-id="4f826-149">In our example table, (bucket_count = 5000000), since 5,000,000 is not a power of 2, the actual bucket count rounds up to 8,388,608 (2<sup>23</sup>).</span></span>  <span data-ttu-id="4f826-150">Debe usar este número, no 5.000.000, al calcular la memoria necesaria para la matriz hash.</span><span class="sxs-lookup"><span data-stu-id="4f826-150">You must use this number, not 5,000,000 when calculating memory needed by the hash array.</span></span>  
  
 <span data-ttu-id="4f826-151">Así, en nuestro ejemplo, la memoria necesaria para cada matriz hash es:</span><span class="sxs-lookup"><span data-stu-id="4f826-151">Thus, in our example, the memory needed for each hash array is:</span></span>  
  
 <span data-ttu-id="4f826-152">8.388.608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67.108.864 o aproximadamente 64 MB.</span><span class="sxs-lookup"><span data-stu-id="4f826-152">8,388,608 \* 8 = 2<sup>23</sup> \* 8 = 2<sup>23</sup> \* 2<sup>3</sup> = 2<sup>26</sup> = 67,108,864 or approximately 64 MB.</span></span>  
  
 <span data-ttu-id="4f826-153">Puesto que tenemos tres índices hash, la memoria necesaria para los índices hash es 3 \* 64 MB = 192 MB.</span><span class="sxs-lookup"><span data-stu-id="4f826-153">Since we have three hash indexes, the memory needed for the hash indexes is 3 \* 64MB = 192MB.</span></span>  
  
 <span data-ttu-id="4f826-154">**Memoria para los índices no agrupados**</span><span class="sxs-lookup"><span data-stu-id="4f826-154">**Memory for nonclustered indexes**</span></span>  
  
 <span data-ttu-id="4f826-155">Los índices no agrupados se implementan como árboles b donde los nodos internos contienen el valor de índice y punteros a los nodos posteriores.</span><span class="sxs-lookup"><span data-stu-id="4f826-155">Nonclustered indexes are implemented as BTrees with the inner nodes containing the index value and pointers to subsequent nodes.</span></span>  <span data-ttu-id="4f826-156">Los nodos hoja contienen el valor de índice y un puntero a la fila de la tabla en memoria.</span><span class="sxs-lookup"><span data-stu-id="4f826-156">Leaf nodes contain the index value and a pointer to the table row in memory.</span></span>  
  
 <span data-ttu-id="4f826-157">A diferencia de los índices hash, los índices no agrupados no tienen un tamaño de cubo fijo.</span><span class="sxs-lookup"><span data-stu-id="4f826-157">Unlike hash indexes, nonclustered indexes do not have a fixed bucket size.</span></span> <span data-ttu-id="4f826-158">El índice aumenta y disminuye dinámicamente con los datos.</span><span class="sxs-lookup"><span data-stu-id="4f826-158">The index grows and shrinks dynamically with the data.</span></span>  
  
 <span data-ttu-id="4f826-159">La memoria que necesitan los índices no agrupados se puede calcular de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f826-159">Memory needed by nonclustered indexes can be computed as follows:</span></span>  
  
-   <span data-ttu-id="4f826-160">**Memoria asignada a los nodos no hoja** </span><span class="sxs-lookup"><span data-stu-id="4f826-160">**Memory allocated to non-leaf nodes** </span></span>  
    <span data-ttu-id="4f826-161">Para una configuración típica, la memoria asignada a los nodos no hoja es un porcentaje muy pequeño de la memoria total usada por el índice.</span><span class="sxs-lookup"><span data-stu-id="4f826-161">For a typical configuration, the memory allocated to non-leaf nodes is a small percentage of the overall memory taken by the index.</span></span> <span data-ttu-id="4f826-162">Es tan pequeña que se puede omitir de forma segura.</span><span class="sxs-lookup"><span data-stu-id="4f826-162">This is so small it can safely be ignored.</span></span>  
  
-   <span data-ttu-id="4f826-163">**Memoria para los nodos hoja** </span><span class="sxs-lookup"><span data-stu-id="4f826-163">**Memory for leaf nodes** </span></span>  
    <span data-ttu-id="4f826-164">Los nodos hoja tienen un fila por cada clave única de la tabla que apunta a las filas de datos con esa clave única.</span><span class="sxs-lookup"><span data-stu-id="4f826-164">The leaf nodes have one row for each unique key in the table that points to the data rows with that unique key.</span></span>  <span data-ttu-id="4f826-165">Si tiene varias filas con la misma clave (es decir, tiene un índice no agrupado que no es único), solo hay una fila en el nodo hoja del índice que apunta a una de las filas con las demás filas vinculadas entre sí.</span><span class="sxs-lookup"><span data-stu-id="4f826-165">If you have multiple rows with the same key (i.e., you have a non-unique nonclustered index), there is only one row in the index leaf node that points to one of the rows with the other rows linked to each other.</span></span>  <span data-ttu-id="4f826-166">Así, se puede calcular aproximadamente la memoria total necesaria de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4f826-166">Thus, the total memory required can be approximated by:</span></span>   
    <span data-ttu-id="4f826-167">memoryForNonClusteredIndex = (pointerSize + sum (keyColumnDataTypeSizes)) \* rowsWithUniqueKeys</span><span class="sxs-lookup"><span data-stu-id="4f826-167">memoryForNonClusteredIndex = (pointerSize + sum(keyColumnDataTypeSizes)) \* rowsWithUniqueKeys</span></span>  
  
 <span data-ttu-id="4f826-168">Los índices no agrupados son los más adecuados cuando se emplean para búsquedas de intervalo, como se ilustra en la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="4f826-168">Nonclustered indexes are best when used for range lookups, as exemplified by the following query:</span></span>  
  
```sql  
  
SELECT * FROM t_hk  
   WHERE c2 > 5  
```  
  
##  <a name="memory-for-row-versioning"></a><a name="bkmk_MemoryForRowVersions"></a> <span data-ttu-id="4f826-169">Memoria para versiones de fila</span><span class="sxs-lookup"><span data-stu-id="4f826-169">Memory for row versioning</span></span>  
 <span data-ttu-id="4f826-170">Para evitar bloqueos, OLTP en memoria emplea simultaneidad optimista al actualizar o eliminar filas.</span><span class="sxs-lookup"><span data-stu-id="4f826-170">To avoid locks, In-Memory OLTP uses optimistic concurrency when updating or deleting rows.</span></span> <span data-ttu-id="4f826-171">Esto significa que cuando se actualiza una fila, se crea una versión adicional de la fila.</span><span class="sxs-lookup"><span data-stu-id="4f826-171">This means that when a row is updated, an additional version of the row is created.</span></span> <span data-ttu-id="4f826-172">El sistema conserva las versiones anteriores disponibles hasta que finaliza la ejecución de todas las transacciones que podrían usar la versión.</span><span class="sxs-lookup"><span data-stu-id="4f826-172">The system keeps the previous versions available until all transactions that could possibly use the version have finished execution.</span></span> <span data-ttu-id="4f826-173">Cuando se elimina una fila, el sistema actúa de forma similar a una actualización, manteniendo la versión disponible hasta que ya no necesita.</span><span class="sxs-lookup"><span data-stu-id="4f826-173">When a row is deleted, the system acts in a similar way to an update, keeping the version available until it is no longer necessary.</span></span> <span data-ttu-id="4f826-174">Las lecturas y las inserciones no crean versiones adicionales de la fila.</span><span class="sxs-lookup"><span data-stu-id="4f826-174">Reads and inserts do not create additional row versions.</span></span>  
  
 <span data-ttu-id="4f826-175">Puesto que en cualquier momento puede haber varias filas adicionales en memoria que esperan que el ciclo de recopilación de elementos no utilizados libere su memoria, debe tener la memoria adecuada para admitir estas filas adicionales.</span><span class="sxs-lookup"><span data-stu-id="4f826-175">Because there may be a number of additional rows in memory at any time waiting for the garbage collection cycle to release their memory, you must have sufficient memory to accommodate these additional rows.</span></span>  
  
 <span data-ttu-id="4f826-176">Se puede estimar el número de filas adicionales calculando el número máximo de actualizaciones y eliminaciones de filas por segundo, y multiplicando después ese valor por el número de segundos que tarda la transacción más larga (mínimo de 1).</span><span class="sxs-lookup"><span data-stu-id="4f826-176">The number of additional rows can be estimated by computing the peak number of row updates and deletions per second, then multiplying that by the number of seconds the longest transaction takes (minimum of 1).</span></span>  
  
 <span data-ttu-id="4f826-177">A continuación, se multiplica ese valor por el tamaño de fila para obtener el número de bytes necesarios para las versiones de fila.</span><span class="sxs-lookup"><span data-stu-id="4f826-177">That value is then multiplied by the row size to get the number of bytes you need for row versioning.</span></span>  
  
 `rowVersions = durationOfLongestTransactionInSeconds * peakNumberOfRowUpdatesOrDeletesPerSecond`  
  
 <span data-ttu-id="4f826-178">Las necesidades de memoria para las filas obsoletas se calculan después multiplicando el número de filas obsoletas por el tamaño de una fila de la tabla optimizada para memoria (vea [la memoria de la tabla](#bkmk_MemoryForTable) anterior).</span><span class="sxs-lookup"><span data-stu-id="4f826-178">Memory needs for stale rows is then estimated by multiplying the number of stale rows by the size of a memory-optimized table row (see [Memory for the table](#bkmk_MemoryForTable) above).</span></span>  
  
 `memoryForRowVersions = rowVersions * rowSize`  
  
##  <a name="memory-for-table-variables"></a><a name="bkmk_TableVariables"></a> <span data-ttu-id="4f826-179">Memoria para variables de tabla</span><span class="sxs-lookup"><span data-stu-id="4f826-179">Memory for table variables</span></span>  
 <span data-ttu-id="4f826-180">La memoria usada para una variable de tabla solo se libera cuando la variable de tabla sale del ámbito.</span><span class="sxs-lookup"><span data-stu-id="4f826-180">Memory used for a table variable is released only when the table variable goes out of scope.</span></span> <span data-ttu-id="4f826-181">Las filas eliminadas, incluidas las filas eliminadas como parte de una actualización, de una variable de tabla no están sujetas a recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="4f826-181">Deleted rows, including rows deleted as part of an update, from a table variable are not subject to garbage collection.</span></span> <span data-ttu-id="4f826-182">No se libera memoria hasta que la variable de tabla no sale del ámbito.</span><span class="sxs-lookup"><span data-stu-id="4f826-182">No memory is released until the table variable exits scope.</span></span>  
  
 <span data-ttu-id="4f826-183">Las variables de tabla definidas en un lote de SQL de gran tamaño, en comparación con un ámbito de procedimiento, que se usan en muchas transacciones, pueden consumir mucha memoria.</span><span class="sxs-lookup"><span data-stu-id="4f826-183">Table variables defined in a large SQL batch, as opposed to a procedure scope, which are used in many transactions, can consume a lot of memory.</span></span> <span data-ttu-id="4f826-184">Como no se eliminan mediante el recolector de elementos no utilizados, las filas eliminadas de una variable de tabla pueden usar mucha memoria y disminuir el rendimiento porque las operaciones de lectura deben examinar más allá de las filas eliminadas.</span><span class="sxs-lookup"><span data-stu-id="4f826-184">Because they are not garbage collected, deleted rows in a table variable can consume a lot memory and degrade performance since read operations need to scan past the deleted rows.</span></span>  
  
##  <a name="memory-for-growth"></a><a name="bkmk_MemoryForGrowth"></a> <span data-ttu-id="4f826-185">Memoria para el crecimiento</span><span class="sxs-lookup"><span data-stu-id="4f826-185">Memory for growth</span></span>  
 <span data-ttu-id="4f826-186">Los cálculos anteriores estiman sus necesidades de memoria para la tabla tal y como es actualmente.</span><span class="sxs-lookup"><span data-stu-id="4f826-186">The above calculations estimate your memory needs for the table as it currently exists.</span></span> <span data-ttu-id="4f826-187">Además de esta memoria, debe calcular el crecimiento de la tabla y proporcionar la memoria adecuada para permitir ese crecimiento.</span><span class="sxs-lookup"><span data-stu-id="4f826-187">In addition to this memory, you need to estimate the growth of the table and provide sufficient memory to accommodate that growth.</span></span>  <span data-ttu-id="4f826-188">Por ejemplo, si prevé un crecimiento del 10 %, necesita multiplicar los resultados anteriores por 1,1 para obtener la memoria total necesaria para la tabla.</span><span class="sxs-lookup"><span data-stu-id="4f826-188">For example, if you anticipate 10% growth then you need to multiple the results from above by 1.1 to get the total memory needed for your table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f826-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4f826-189">See Also</span></span>  
 [<span data-ttu-id="4f826-190">Migrar a OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="4f826-190">Migrating to In-Memory OLTP</span></span>](migrating-to-in-memory-oltp.md)  
  
  
