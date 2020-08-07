---
title: Instrucciones para usar índices en tablas optimizadas para memoria | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
helpviewer_keywords:
- hash indexes
ms.assetid: 16ef63a4-367a-46ac-917d-9eebc81ab29b
author: stevestein
ms.author: sstein
ms.openlocfilehash: f00d643088634c918eb626917eae64a001ce3678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746416"
---
# <a name="guidelines-for-using-indexes-on-memory-optimized-tables"></a><span data-ttu-id="09674-102">Directrices para usar índices en las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="09674-102">Guidelines for Using Indexes on Memory-Optimized Tables</span></span>
  <span data-ttu-id="09674-103">Los índices se utilizan para tener acceso a los datos de forma eficaz en las tablas de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09674-103">Indexes are used for efficiently accessing data in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="09674-104">Especificar los índices adecuados puede mejorar drásticamente el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="09674-104">Specifying the right indexes can dramatically improve query performance.</span></span> <span data-ttu-id="09674-105">Considere, por ejemplo, la consulta:</span><span class="sxs-lookup"><span data-stu-id="09674-105">Consider, for example, the query:</span></span>  
  
```sql  
SELECT c1, c2 FROM t WHERE c1 = 1;  
```  
  
 <span data-ttu-id="09674-106">Si no hay ningún índice en la columna c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] necesitará examinar toda la tabla t y, a continuación, filtrar en las filas que cumplen la condición c1=1.</span><span class="sxs-lookup"><span data-stu-id="09674-106">If there is no index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will need to scan the entire table t, and then filter on the rows that satisfy the condition c1=1.</span></span> <span data-ttu-id="09674-107">Sin embargo, si tiene un índice en la columna c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] puede buscar directamente en el valor 1 y recuperar las filas.</span><span class="sxs-lookup"><span data-stu-id="09674-107">However, if t has an index on column c1, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can seek directly on the value 1 and retrieve the rows.</span></span>  
  
 <span data-ttu-id="09674-108">Para buscar los registros que tienen un valor específico o un intervalo de valores para una o varias columnas de la tabla, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] puede utilizar un índice en dichas columnas para buscar rápidamente los registros correspondientes.</span><span class="sxs-lookup"><span data-stu-id="09674-108">When searching for records that have a specific value, or range of values, for one or more columns in the table, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can use an index on those columns to quickly locate the corresponding records.</span></span> <span data-ttu-id="09674-109">Tanto las tablas optimizadas para memoria como las basadas en disco se benefician de los índices.</span><span class="sxs-lookup"><span data-stu-id="09674-109">Both disk-based and memory-optimized tables benefit from indexes.</span></span> <span data-ttu-id="09674-110">Sin embargo, hay algunas diferencias entre las estructuras de índice que deben tenerse en cuenta al utilizar las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="09674-110">There are, however, certain differences between index structures that need to be considered when using memory-optimized tables.</span></span> <span data-ttu-id="09674-111">(Los índices de las tablas optimizadas para memoria se conocen como índices optimizados para memoria). Algunas de las principales diferencias son:</span><span class="sxs-lookup"><span data-stu-id="09674-111">(Indexes on memory-optimized tables are referred to as memory-optimized indexes.) Some of the key differences are:</span></span>  
  
-   <span data-ttu-id="09674-112">Los índices con optimización para memoria deben crearse con [CREATE TABLE &#40;&#41;de Transact-SQL ](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09674-112">Memory-optimized indexes must be created with [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span> <span data-ttu-id="09674-113">Los índices basados en disco se pueden crear con `CREATE TABLE` y `CREATE INDEX`.</span><span class="sxs-lookup"><span data-stu-id="09674-113">Disk-based indexes can be created with `CREATE TABLE` and `CREATE INDEX`.</span></span>  
  
-   <span data-ttu-id="09674-114">Los índices con optimización para memoria solo existen en la memoria.</span><span class="sxs-lookup"><span data-stu-id="09674-114">Memory-optimized indexes exist only in memory.</span></span> <span data-ttu-id="09674-115">Las estructuras de índice no permanecen en el disco y las operaciones de índice no se graban en el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="09674-115">Index structures are not persisted to disk and index operations are not logged in the transaction log.</span></span> <span data-ttu-id="09674-116">Se crea la estructura de índice cuando la tabla optimizada para memoria se crea en la memoria, durante la operación CREATE TABLE y durante el inicio de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="09674-116">The index structure is created when the memory-optimized table is created in memory, both during CREATE TABLE and during database startup.</span></span>  
  
-   <span data-ttu-id="09674-117">Los índices con optimización para memoria tienen cobertura de forma intrínseca.</span><span class="sxs-lookup"><span data-stu-id="09674-117">Memory-optimized indexes are inherently covering.</span></span> <span data-ttu-id="09674-118">El alcance implica que todas las columnas se incluyen virtualmente en el índice y las búsquedas de marcadores no son necesarias en las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="09674-118">Covering means that all columns are virtually included in the index and bookmark lookups are not needed for memory-optimized tables.</span></span> <span data-ttu-id="09674-119">En lugar de una referencia a la clave principal, los índices optimizados para memoria simplemente contienen un puntero de memoria a la fila real en la estructura de datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="09674-119">Rather than a reference to the primary key, memory-optimized indexes simply contain a memory pointer to the actual row in the table data structure.</span></span>  
  
-   <span data-ttu-id="09674-120">La fragmentación y el factor de relleno no se aplican a los índices optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="09674-120">Fragmentation and fillfactor do not apply to memory-optimized indexes.</span></span> <span data-ttu-id="09674-121">En los índices basados en disco, la fragmentación hace referencia a las páginas del árbol B que se están escribiendo en el disco que no funciona.</span><span class="sxs-lookup"><span data-stu-id="09674-121">In disk-based indexes, fragmentation refers to pages in the B-tree being written to disk out-of-order.</span></span> <span data-ttu-id="09674-122">Los índices con optimización para memoria no se escriben ni se leen del disco.</span><span class="sxs-lookup"><span data-stu-id="09674-122">Memory-optimized indexes are not written to or read from disk.</span></span> <span data-ttu-id="09674-123">El factor de relleno en los índices de árbol b basado en disco hace referencia al grado en que las estructuras de páginas físicas se rellenan con datos reales.</span><span class="sxs-lookup"><span data-stu-id="09674-123">Fillfactor in disk-based B-tree indexes refers to the degree to which the physical page structures are filled with actual data.</span></span> <span data-ttu-id="09674-124">Las estructuras de índice optimizado para memoria no tienen páginas de tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="09674-124">The memory-optimized index structures do not have fixed-size pages.</span></span>  
  
 <span data-ttu-id="09674-125">Hay dos tipos de índices optimizados para memoria:</span><span class="sxs-lookup"><span data-stu-id="09674-125">There are two types of memory-optimized indexes:</span></span>  
  
-   <span data-ttu-id="09674-126">Los índices de hash no clúster, que son convenientes para las búsquedas de puntos.</span><span class="sxs-lookup"><span data-stu-id="09674-126">Nonclustered hash indexes, which are made for point lookups.</span></span> <span data-ttu-id="09674-127">Para obtener más información sobre los índices hash, vea [índices hash](hash-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="09674-127">For more information about hash indexes, see [Hash Indexes](hash-indexes.md).</span></span>  
  
-   <span data-ttu-id="09674-128">Los índices no clúster, que son para exámenes de intervalo y exámenes ordenados.</span><span class="sxs-lookup"><span data-stu-id="09674-128">Nonclustered indexes, which are made for range scans and ordered scans.</span></span>  
  
 <span data-ttu-id="09674-129">Con un índice hash, se accede a los datos a través de una tabla hash en memoria.</span><span class="sxs-lookup"><span data-stu-id="09674-129">With a hash index, data is accessed through an in-memory hash table.</span></span> <span data-ttu-id="09674-130">Los índices hash no tienen páginas y son siempre de un tamaño fijo.</span><span class="sxs-lookup"><span data-stu-id="09674-130">Hash indexes do not have pages and are always of a fixed size.</span></span> <span data-ttu-id="09674-131">Sin embargo, un índice hash puede tener cubos de hash vacíos, lo que da lugar a un espacio desaprovechado limitado.</span><span class="sxs-lookup"><span data-stu-id="09674-131">However, a hash index can have empty hash buckets, which result in limited wasted space.</span></span> <span data-ttu-id="09674-132">Los valores devueltos de una consulta con un índice hash no están ordenadas.</span><span class="sxs-lookup"><span data-stu-id="09674-132">The values returned from a query using a hash index are not sorted.</span></span> <span data-ttu-id="09674-133">Los índices hash se optimizan para las búsquedas de índice en predicados de igualdad y también admiten exploraciones de índice completas.</span><span class="sxs-lookup"><span data-stu-id="09674-133">Hash indexes are optimized for index seeks on equality predicates and also support full index scans.</span></span>  
  
 <span data-ttu-id="09674-134">Los índices no clúster (no los índices hash) admiten lo mismo que los índices hash, además de operaciones de búsqueda en predicados de desigualdad como mayor que o menor que, así como el criterio de ordenación.</span><span class="sxs-lookup"><span data-stu-id="09674-134">Nonclustered indexes (not hash indexes) support everything that hash indexes supports plus seek operations on inequality predicates such as greater than or less than, as well as sort order.</span></span> <span data-ttu-id="09674-135">Las filas se pueden recuperar en el orden especificado para la creación de los índices.</span><span class="sxs-lookup"><span data-stu-id="09674-135">Rows can be retrieved according to the order specified with index creation.</span></span> <span data-ttu-id="09674-136">Si el criterio de ordenación del índice coincide con el orden requerido para una consulta determinada, por ejemplo, si la clave del índice coincide con la cláusula ORDER BY, no es necesario ordenar las filas como parte de la ejecución de la consulta.</span><span class="sxs-lookup"><span data-stu-id="09674-136">If the sort order of the index matches the sort order required for a particular query, for example if the index key matches the ORDER BY clause, there is no need to sort the rows as part of query execution.</span></span> <span data-ttu-id="09674-137">Los índices no clúster con optimización para memoria son unidireccionales: no permiten recuperar filas con un criterio de ordenación inverso al del índice.</span><span class="sxs-lookup"><span data-stu-id="09674-137">Memory-optimized nonclustered indexes are unidirectional; they do not support retrieving rows in a sort order that is the reverse of the sort order of the index.</span></span> <span data-ttu-id="09674-138">Por ejemplo, para un índice especificado como (c1 ASC) no es posible examinar el índice en orden inverso, como (c1 DESC).</span><span class="sxs-lookup"><span data-stu-id="09674-138">For example, for an index specified as (c1 ASC), it is not possible to scan the index in reverse order, as (c1 DESC).</span></span>  
  
 <span data-ttu-id="09674-139">Cada índice utiliza memoria.</span><span class="sxs-lookup"><span data-stu-id="09674-139">Each index consumes memory.</span></span> <span data-ttu-id="09674-140">Los índices hash utilizan una cantidad fija de memoria, que es una función del número de cubos.</span><span class="sxs-lookup"><span data-stu-id="09674-140">Hash indexes consume a fixed amount of memory, which is a function of the bucket count.</span></span> <span data-ttu-id="09674-141">Para los índices no clúster, el consumo de memoria depende del número de filas y del tamaño de las columnas de clave de índice, con una sobrecarga adicional que depende de la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="09674-141">For nonclustered indexes, memory consumption is a function of the row count and the size of the index key columns, with some additional overhead depending on the workload.</span></span> <span data-ttu-id="09674-142">La memoria para los índices optimizados para memoria es adicional e independiente de la memoria usada para almacenar las filas de las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="09674-142">Memory for memory-optimized indexes is in addition to and separate from the memory used to store rows in memory-optimized tables.</span></span>  
  
 <span data-ttu-id="09674-143">Los valores de clave duplicados comparten siempre el mismo depósito de hash.</span><span class="sxs-lookup"><span data-stu-id="09674-143">Duplicate key values always share the same hash bucket.</span></span> <span data-ttu-id="09674-144">Si un índice hash contiene muchos valores clave duplicados, las cadenas para el hash largas resultantes repercutirán negativamente en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="09674-144">If a hash index contains many duplicate key values, the resulting long hash chains will harm performance.</span></span> <span data-ttu-id="09674-145">Las colisiones de hash, que se producen en los índices hash, reducirán aún más el rendimiento en este escenario.</span><span class="sxs-lookup"><span data-stu-id="09674-145">Hash collisions, which occur in any hash index, will further reduce performance in this scenario.</span></span> <span data-ttu-id="09674-146">Por ese motivo, si el número de claves de índice único es al menos 100 veces menor que el recuento de filas, puede reducir el riesgo de colisiones de hash haciendo que el número de depósitos sea mucho mayor (al menos ocho veces el número de claves de índice único; vea [determinar el número de depósitos correcto para los índices de hash](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) para obtener más información) o puede eliminar las colisiones de hash por completo mediante</span><span class="sxs-lookup"><span data-stu-id="09674-146">For that reason, if the number of unique index keys is at least 100 times smaller than the row count, you can reduce the risk of hash collisions by making the bucket count much larger (at least eight times the number of unique index keys; see [Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) for more information) or you can eliminate hash collisions entirely by using a nonclustered index.</span></span>  
  
## <a name="determining-which-indexes-to-use-for-a-memory-optimized-table"></a><span data-ttu-id="09674-147">Determinar qué índices se deben usar para una tabla con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="09674-147">Determining Which Indexes to Use for a Memory-Optimized Table</span></span>  
 <span data-ttu-id="09674-148">Cada tabla optimizada para memoria debe tener al menos un índice.</span><span class="sxs-lookup"><span data-stu-id="09674-148">Each memory-optimized table must have at least one index.</span></span> <span data-ttu-id="09674-149">Tenga en cuenta que cada restricción PRIMARY KEY crea implícitamente un índice.</span><span class="sxs-lookup"><span data-stu-id="09674-149">Note that each PRIMARY KEY constraint implicitly creates an index.</span></span> <span data-ttu-id="09674-150">Por consiguiente, si una tabla tiene una clave principal, tiene un índice.</span><span class="sxs-lookup"><span data-stu-id="09674-150">Therefore, if a table has a primary key, it has an index.</span></span> <span data-ttu-id="09674-151">Una clave principal es un requisito para una tabla optimizada para memoria perdurable.</span><span class="sxs-lookup"><span data-stu-id="09674-151">A primary key is a requirement for a durable memory-optimized table.</span></span>  
  
 <span data-ttu-id="09674-152">Al consultar una tabla optimizada para memoria, los índices hash funcionan mejor cuando la cláusula de predicado solo contiene predicados de igualdad.</span><span class="sxs-lookup"><span data-stu-id="09674-152">When querying a memory-optimized table, hash indexes perform better when the predicate clause contains only equality predicates.</span></span> <span data-ttu-id="09674-153">El predicado debe incluir todas las columnas de clave de índice hash.</span><span class="sxs-lookup"><span data-stu-id="09674-153">The predicate must include all columns in the hash index key.</span></span> <span data-ttu-id="09674-154">Un índice hash revertirá a un recorrido dado un predicado de desigualdad.</span><span class="sxs-lookup"><span data-stu-id="09674-154">A hash index will revert to a scan given an inequality predicate.</span></span>  
  
 <span data-ttu-id="09674-155">Una columna de una tabla optimizada para memoria puede formar parte de un índice hash y de un índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="09674-155">A column in a memory-optimized table can be part of both a hash index and a nonclustered index.</span></span>  
  
 <span data-ttu-id="09674-156">Al consultar una tabla optimizada para memoria con predicados de desigualdad, los índices no clúster se comportarán mejor que los índices de hash no clúster.</span><span class="sxs-lookup"><span data-stu-id="09674-156">When querying a memory-optimized table with inequality predicates, nonclustered indexes will perform better than nonclustered hash indexes.</span></span>  
  
 <span data-ttu-id="09674-157">El índice hash requiere una clave (de hash) para buscar en el índice.</span><span class="sxs-lookup"><span data-stu-id="09674-157">The hash index requires a key (to hash) to seek into the index.</span></span> <span data-ttu-id="09674-158">Si la clave de índice consta de dos columnas y solo proporciona la primera, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no tiene una clave completa para aplicar el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="09674-158">If an index key consists of two columns and you only provide the first column, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a complete key to hash.</span></span> <span data-ttu-id="09674-159">Esto generará un plan de consulta de examen de índice.</span><span class="sxs-lookup"><span data-stu-id="09674-159">This will result in an index scan query plan.</span></span> <span data-ttu-id="09674-160">El uso determina qué columnas deben ser indizadas.</span><span class="sxs-lookup"><span data-stu-id="09674-160">Usage determines which columns should be indexed.</span></span>  
  
 <span data-ttu-id="09674-161">Cuando una columna de un índice no clúster tiene el mismo valor en muchas filas (las columnas de clave de índice tienen muchos valores duplicados), el rendimiento puede reducirse para las actualizaciones, las inserciones y las eliminaciones.</span><span class="sxs-lookup"><span data-stu-id="09674-161">When a column in a nonclustered index has the same value in many rows (index key columns have a lot of duplicate values), performance can degrade for updates, inserts, and deletions.</span></span>  <span data-ttu-id="09674-162">Una manera de mejorar el rendimiento en este escenario es agregar otra columna al índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="09674-162">One way to improve performance in this situation is to add another column to the nonclustered index.</span></span>  
  
### <a name="operations-on-memory-optimized-and-disk-based-indexes"></a><span data-ttu-id="09674-163">Operaciones de índices basados en disco y optimizados para memoria.</span><span class="sxs-lookup"><span data-stu-id="09674-163">Operations on memory-optimized and disk-based indexes.</span></span>  
  
|<span data-ttu-id="09674-164">Operación</span><span class="sxs-lookup"><span data-stu-id="09674-164">Operation</span></span>|<span data-ttu-id="09674-165">Índice no clúster, hash, con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="09674-165">Memory-optimized, nonclustered hash, index</span></span>|<span data-ttu-id="09674-166">Índice no clúster con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="09674-166">Memory-optimized nonclustered index</span></span>|<span data-ttu-id="09674-167">Índice basado en disco</span><span class="sxs-lookup"><span data-stu-id="09674-167">Disk-based index</span></span>|  
|---------------|-------------------------------------------------|------------------------------------------|-----------------------|  
|<span data-ttu-id="09674-168">Index scan, recupera todas las filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="09674-168">Index Scan, retrieve all table rows.</span></span>|<span data-ttu-id="09674-169">Sí</span><span class="sxs-lookup"><span data-stu-id="09674-169">Yes</span></span>|<span data-ttu-id="09674-170">Sí</span><span class="sxs-lookup"><span data-stu-id="09674-170">Yes</span></span>|<span data-ttu-id="09674-171">Sí</span><span class="sxs-lookup"><span data-stu-id="09674-171">Yes</span></span>|  
|<span data-ttu-id="09674-172">Index seek en predicados de igualdad (=).</span><span class="sxs-lookup"><span data-stu-id="09674-172">Index seek on equality predicate(s) (=).</span></span>|<span data-ttu-id="09674-173">Sí</span><span class="sxs-lookup"><span data-stu-id="09674-173">Yes</span></span><br /><br /> <span data-ttu-id="09674-174">(Clave completa necesaria.)</span><span class="sxs-lookup"><span data-stu-id="09674-174">(Full key required.)</span></span>|<span data-ttu-id="09674-175">Sí <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="09674-175">Yes <sup>1</sup></span></span>|<span data-ttu-id="09674-176">Sí</span><span class="sxs-lookup"><span data-stu-id="09674-176">Yes</span></span>|  
|<span data-ttu-id="09674-177">Index Seek en predicados de desigualdad (>, <, \<=, > =, between).</span><span class="sxs-lookup"><span data-stu-id="09674-177">Index seek on inequality predicates (>, <, \<=, >=, BETWEEN).</span></span>|<span data-ttu-id="09674-178">No (resultados en un examen de índice)</span><span class="sxs-lookup"><span data-stu-id="09674-178">No (results in an index scan)</span></span>|<span data-ttu-id="09674-179">Sí <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="09674-179">Yes <sup>1</sup></span></span>|<span data-ttu-id="09674-180">Sí</span><span class="sxs-lookup"><span data-stu-id="09674-180">Yes</span></span>|  
|<span data-ttu-id="09674-181">Recupere las filas en un orden que coincida con la definición de índice.</span><span class="sxs-lookup"><span data-stu-id="09674-181">Retrieve rows in a sort-order matching the index definition.</span></span>|<span data-ttu-id="09674-182">No</span><span class="sxs-lookup"><span data-stu-id="09674-182">No</span></span>|<span data-ttu-id="09674-183">Sí</span><span class="sxs-lookup"><span data-stu-id="09674-183">Yes</span></span>|<span data-ttu-id="09674-184">Sí</span><span class="sxs-lookup"><span data-stu-id="09674-184">Yes</span></span>|  
|<span data-ttu-id="09674-185">Recupere las filas en un orden que coincida con el opuesto de la definición de índice.</span><span class="sxs-lookup"><span data-stu-id="09674-185">Retrieve rows in a sort-order matching the reverse of the index definition.</span></span>|<span data-ttu-id="09674-186">No</span><span class="sxs-lookup"><span data-stu-id="09674-186">No</span></span>|<span data-ttu-id="09674-187">No</span><span class="sxs-lookup"><span data-stu-id="09674-187">No</span></span>|<span data-ttu-id="09674-188">Sí</span><span class="sxs-lookup"><span data-stu-id="09674-188">Yes</span></span>|  
  
 <span data-ttu-id="09674-189">En la tabla, Sí se refiere a que el índice puede prestar servicio correctamente a la solicitud y No se refiere a que el índice no se puede usar correctamente para atender la solicitud.</span><span class="sxs-lookup"><span data-stu-id="09674-189">In the table, Yes means that the index can adequately service the request and No means that the index cannot be used successfully to satisfy the request.</span></span>  
  
 <span data-ttu-id="09674-190"><sup>1</sup> para un índice optimizado para memoria no agrupado, no se requiere la clave completa para realizar una búsqueda de índice.</span><span class="sxs-lookup"><span data-stu-id="09674-190"><sup>1</sup> For a nonclustered memory-optimized index, the full key is not required to perform an index seek.</span></span> <span data-ttu-id="09674-191">Sin embargo, dado el orden de las columnas de la clave de índice, se producirá un examen si el valor de una columna viene después de una columna que falta.</span><span class="sxs-lookup"><span data-stu-id="09674-191">Although, given the column order of the index key, a scan will occur if a value for a column comes after a missing column.</span></span>  
  
## <a name="index-count"></a><span data-ttu-id="09674-192">Contador de índice</span><span class="sxs-lookup"><span data-stu-id="09674-192">Index Count</span></span>  
 <span data-ttu-id="09674-193">Una tabla optimizada para memoria puede tener hasta ocho índices, incluido el creado con la clave principal.</span><span class="sxs-lookup"><span data-stu-id="09674-193">A memory-optimized table can have up to 8 indexes, including the index created with the primary key.</span></span>  
  
 <span data-ttu-id="09674-194">En relación con el número de índices creados en una tabla optimizada para memoria, considere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="09674-194">Regarding the number of indexes created on a memory-optimized table, consider the following:</span></span>  
  
-   <span data-ttu-id="09674-195">Especifique los índices que necesita al crear la tabla.</span><span class="sxs-lookup"><span data-stu-id="09674-195">Specify the indexes you need when you create the table.</span></span> <span data-ttu-id="09674-196">No puede crear un índice para una tabla optimizada para memoria después de crear la tabla.</span><span class="sxs-lookup"><span data-stu-id="09674-196">You cannot create an index for a memory-optimized table after the table is created.</span></span> <span data-ttu-id="09674-197">Si desea agregar un índice a una tabla optimizada para memoria, quite la tabla y vuelva a crearla.</span><span class="sxs-lookup"><span data-stu-id="09674-197">If you want to add an index to a memory-optimized table, drop and recreate that table.</span></span>  
  
-   <span data-ttu-id="09674-198">No cree un índice que use poco:</span><span class="sxs-lookup"><span data-stu-id="09674-198">Do not create an index that you rarely use:</span></span>  
  
     <span data-ttu-id="09674-199">La recolección de elementos no utilizados funciona mejor si todos los índices de la tabla se utilizan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="09674-199">Garbage collection works best if all indexes on the table are frequently used.</span></span> <span data-ttu-id="09674-200">Los índices que se usan poco pueden hacer que el sistema de recopilación de elementos no utilizados no se comporten de forma óptimo en las versiones de fila anteriores.</span><span class="sxs-lookup"><span data-stu-id="09674-200">Rarely-used indexes may cause the garbage collection system to not perform optimally for old row versions.</span></span>  
  
## <a name="creating-a-memory-optimized-index-code-samples"></a><span data-ttu-id="09674-201">Crear un índice con optimización para memoria: ejemplos de código</span><span class="sxs-lookup"><span data-stu-id="09674-201">Creating a Memory-Optimized Index: Code Samples</span></span>  
 <span data-ttu-id="09674-202">Índice hash de nivel de columna:</span><span class="sxs-lookup"><span data-stu-id="09674-202">Column level hash index:</span></span>  
  
```sql  
CREATE TABLE t1   
   (c1 INT NOT NULL INDEX idx HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="09674-203">Índice hash de nivel de tabla:</span><span class="sxs-lookup"><span data-stu-id="09674-203">Table level hash index:</span></span>  
  
```sql  
CREATE TABLE t1_1   
   (c1 INT NOT NULL,   
   INDEX IDX HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="09674-204">Índice hash de la clave principal de nivel de columna:</span><span class="sxs-lookup"><span data-stu-id="09674-204">Column level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED HASH WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="09674-205">Índice hash de la clave principal de nivel de tabla:</span><span class="sxs-lookup"><span data-stu-id="09674-205">Table level primary key hash index:</span></span>  
  
```sql  
CREATE TABLE t2_2   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED HASH (c1) WITH (BUCKET_COUNT = 100))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="09674-206">Índice no clúster de nivel de columna:</span><span class="sxs-lookup"><span data-stu-id="09674-206">Column level nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t3   
   (c1 INT NOT NULL INDEX ID)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="09674-207">Índice no clúster de nivel de tabla:</span><span class="sxs-lookup"><span data-stu-id="09674-207">Table level nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t3_3   
   (c1 INT NOT NULL,   
   INDEX IDX NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_ONLY)  
```  
  
 <span data-ttu-id="09674-208">Índice no clúster de la clave principal de nivel de columna:</span><span class="sxs-lookup"><span data-stu-id="09674-208">Column level primary key nonclustered  index:</span></span>  
  
```sql  
CREATE TABLE t4   
   (c1 INT NOT NULL PRIMARY KEY NONCLUSTERED)   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="09674-209">Índice no clúster de la clave principal de nivel de tabla:</span><span class="sxs-lookup"><span data-stu-id="09674-209">Table level primary key nonclustered index:</span></span>  
  
```sql  
CREATE TABLE t4_4   
   (c1 INT NOT NULL,   
   PRIMARY KEY NONCLUSTERED (c1))   
   WITH (MEMORY_OPTIMIZED = ON, DURABILITY = SCHEMA_AND_DATA)  
```  
  
 <span data-ttu-id="09674-210">Índice de varias columnas definido después de definir las columnas:</span><span class="sxs-lookup"><span data-stu-id="09674-210">Multicolumn index defined after columns are defined:</span></span>  
  
```sql  
create table t (  
       a int not null constraint ta primary key nonclustered,  
       b int not null,  
       c int not null,  
       d int not null,  
       index idx_t_b_c_d nonclustered (b, c asc, d desc)  
) with (memory_optimized = on, durability = SCHEMA_AND_DATA)  
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="09674-211">Consulte también</span><span class="sxs-lookup"><span data-stu-id="09674-211">See Also</span></span>  
 <span data-ttu-id="09674-212">[Índices en tablas optimizadas para memoria](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="09674-212">[Indexes on Memory-Optimized Tables](../relational-databases/in-memory-oltp/memory-optimized-tables.md) </span></span>  
 <span data-ttu-id="09674-213">[Determinar el número correcto de depósitos para los índices hash](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="09674-213">[Determining the Correct Bucket Count for Hash Indexes](../../2014/database-engine/determining-the-correct-bucket-count-for-hash-indexes.md) </span></span>  
 [<span data-ttu-id="09674-214">Índices hash</span><span class="sxs-lookup"><span data-stu-id="09674-214">Hash Indexes</span></span>](hash-indexes.md)  
  
  
