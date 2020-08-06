---
title: Solucionar problemas comunes de rendimiento con índices de hash optimizados para memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 1954a997-7585-4713-81fd-76d429b8d095
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3cef98571edd7736bc45ba8caf17451007a74cf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744293"
---
# <a name="troubleshooting-common-performance-problems-with-memory-optimized-hash-indexes"></a><span data-ttu-id="b3155-102">Solucionar problemas habituales de rendimiento con los índices hash con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="b3155-102">Troubleshooting Common Performance Problems with Memory-Optimized Hash Indexes</span></span>
  <span data-ttu-id="b3155-103">Este tema se centrará en la solución de problemas y soluciones alternativas a los problemas comunes con índices de hash.</span><span class="sxs-lookup"><span data-stu-id="b3155-103">This topic will focus on troubleshooting and working around common issues with hash indexes.</span></span>  
  
## <a name="search-requires-a-subset-of-hash-index-key-columns"></a><span data-ttu-id="b3155-104">La búsqueda requiere un subconjunto de columnas de clave de índice de hash</span><span class="sxs-lookup"><span data-stu-id="b3155-104">Search Requires a Subset of Hash Index Key Columns</span></span>  
 <span data-ttu-id="b3155-105">**Problema:** Los índices hash requieren valores para todas las columnas de clave de índice para calcular el valor hash y buscar las filas correspondientes en la tabla hash.</span><span class="sxs-lookup"><span data-stu-id="b3155-105">**Issue:** Hash indexes require values for all index key columns in order to compute the hash value, and locate the corresponding rows in the hash table.</span></span> <span data-ttu-id="b3155-106">Por consiguiente, si una consulta incluye predicados de igualdad únicamente para un subconjunto de las claves de índice en la cláusula WHERE, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no puede utilizar una operación INDEX SEEK para ubicar las filas correspondientes a los predicados de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="b3155-106">Therefore, if a query includes equality predicates for only a subset of the index keys in the WHERE clause, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot use an index seek to locate the rows corresponding to the predicates in the WHERE clause.</span></span>  
  
 <span data-ttu-id="b3155-107">En cambio, los índices ordenados como los índices no clúster basados en disco y los índices no clúster optimizados para memoria admiten INDEX SEEK en un subconjunto de las columnas de clave de índice, siempre y cuando sean las columnas iniciales del índice.</span><span class="sxs-lookup"><span data-stu-id="b3155-107">In contrast, ordered indexes like the disk-based nonclustered indexes and the memory-optimized nonclustered indexes support index seek on a subset of the index key columns, as long as they are the leading columns in the index.</span></span>  
  
 <span data-ttu-id="b3155-108">**Síntoma:** Esto produce una degradación del rendimiento, ya que [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] es necesario ejecutar recorridos de tabla completos en lugar de una búsqueda de índice, lo que suele ser una operación más rápida.</span><span class="sxs-lookup"><span data-stu-id="b3155-108">**Symptom:** This results in a performance degradation, as [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] needs to execute full table scans rather than an index seek, which is typically a faster operation.</span></span>  
  
 <span data-ttu-id="b3155-109">**Cómo solucionar problemas:** Además de la degradación del rendimiento, la inspección de los planes de consulta mostrará un examen en lugar de un índice de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b3155-109">**How to troubleshoot:** Besides the performance degradation, inspection of the query plans will show a scan instead of an index seek.</span></span> <span data-ttu-id="b3155-110">Si la consulta es bastante simple, la inspección del texto de la consulta y de la definición de índice también mostrará si la búsqueda requiere un subconjunto de las columnas de clave de índice.</span><span class="sxs-lookup"><span data-stu-id="b3155-110">If the query is fairly simple, inspection of the query text and index definition will also show whether the search requires a subset of the index key columns.</span></span>  
  
 <span data-ttu-id="b3155-111">Considere la consulta y la tabla siguientes:</span><span class="sxs-lookup"><span data-stu-id="b3155-111">Consider the following table and query:</span></span>  
  
```sql  
CREATE TABLE [dbo].[od]  
(  
     o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
     CONSTRAINT PK_od PRIMARY KEY NONCLUSTERED HASH (o_id, od_id) WITH (BUCKET_COUNT = 10000)  
)  
WITH (MEMORY_OPTIMIZED = ON)  
  
 SELECT p_id  
 FROM dbo.od  
 WHERE o_id=1  
```  
  
 <span data-ttu-id="b3155-112">La tabla tiene un índice de hash en las dos columnas (o_id, od_id), mientras que la consulta tiene un predicado de igualdad en (o_id).</span><span class="sxs-lookup"><span data-stu-id="b3155-112">The table has a hash index on the two columns (o_id, od_id), while the query has an equality predicate on (o_id).</span></span> <span data-ttu-id="b3155-113">Como la consulta tiene predicados de igualdad en un solo subconjunto de las columnas de clave de índice, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] no puede realizar una operación INDEX SEEK con PK_od; en su lugar, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] tiene que volver a un recorrido del índice completo.</span><span class="sxs-lookup"><span data-stu-id="b3155-113">As the query has equality predicates on only a subset of the index key columns, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cannot perform an index seek operation using PK_od; instead, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] has to revert to a full index scan.</span></span>  
  
 <span data-ttu-id="b3155-114">**Soluciones alternativas:** Hay varias soluciones posibles.</span><span class="sxs-lookup"><span data-stu-id="b3155-114">**Workarounds:** There are a number of possible workarounds.</span></span> <span data-ttu-id="b3155-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b3155-115">For example:</span></span>  
  
-   <span data-ttu-id="b3155-116">Vuelva a crear el índice que sea de tipo no clúster en lugar de hash no clúster.</span><span class="sxs-lookup"><span data-stu-id="b3155-116">Recreate the index as type nonclustered instead of nonclustered hash.</span></span> <span data-ttu-id="b3155-117">El índice no clúster optimizado para memoria está ordenado y así [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] puede realizar una búsqueda de índice en las columnas iniciales de clave de índice.</span><span class="sxs-lookup"><span data-stu-id="b3155-117">The memory-optimized nonclustered index is ordered, and thus [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] can perform an index seek on the leading index key columns.</span></span> <span data-ttu-id="b3155-118">La definición resultante de clave principal del ejemplo sería `constraint PK_od primary key nonclustered`.</span><span class="sxs-lookup"><span data-stu-id="b3155-118">The resulting primary key definition for the example would be `constraint PK_od primary key nonclustered`.</span></span>  
  
-   <span data-ttu-id="b3155-119">Cambie la clave de índice actual para que coincida con las columnas de la cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="b3155-119">Change the current index key to match the columns in the WHERE clause.</span></span>  
  
-   <span data-ttu-id="b3155-120">Agregue un nuevo índice de hash que coincida con las columnas de la cláusula WHERE de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b3155-120">Add a new hash index that matches with the columns in the WHERE clause of the query.</span></span> <span data-ttu-id="b3155-121">En el ejemplo, la definición de tabla resultante se parecería a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3155-121">In the example, the resulting table definition would look at follows:</span></span>  
  
    ```sql  
    CREATE TABLE dbo.od  
     ( o_id INT NOT NULL,  
     od_id INT NOT NULL,  
     p_id INT NOT NULL,  
  
     CONSTRAINT PK_od PRIMARY KEY   
     NONCLUSTERED HASH (o_id,od_id) WITH (BUCKET_COUNT=10000),  
  
     INDEX ix_o_id NONCLUSTERED HASH (o_id) WITH (BUCKET_COUNT=10000)  
  
     ) WITH (MEMORY_OPTIMIZED=ON)  
    ```  
  
 <span data-ttu-id="b3155-122">Observe que un índice de hash optimizada para memoria no se ejecuta óptimamente si hay muchas filas duplicadas para un valor de clave de índice determinado: en el ejemplo, si el número de valores únicos para la columna o_id es mucho menor que el número de filas de la tabla, no sería óptimo agregar un índice en (o_id); en su lugar, la mejor solución sería cambiar el tipo del índice PK_od de hash a no clúster.</span><span class="sxs-lookup"><span data-stu-id="b3155-122">Note that a memory-optimized hash index does not perform optimally if there are a lot of duplicate rows for a given index key value: in the example, if the number of unique values for the column o_id is much smaller than the number of rows in the table, it would not be optimal to add an index on (o_id); instead, changing the type of the index PK_od from hash to nonclustered would be the better solution.</span></span> <span data-ttu-id="b3155-123">Para obtener más información, vea [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="b3155-123">For more information, see [Determining the Correct Bucket Count for Hash Indexes](../relational-databases/indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3155-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b3155-124">See Also</span></span>  
 [<span data-ttu-id="b3155-125">Índices de las tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="b3155-125">Indexes on Memory-Optimized Tables</span></span>](../relational-databases/in-memory-oltp/memory-optimized-tables.md)  
  
  
