---
title: Limitación de los resultados de la búsqueda con RANK | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- row ranking [full-text search]
- relevance ranking values [full-text search]
- full-text search [SQL Server], rankings
- index rankings [full-text search]
- ranked results [full-text search]
- rankings [full-text search]
- per-row rank values [full-text search]
ms.assetid: 06a776e6-296c-4ec7-9fa5-0794709ccb17
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ab1b930b3238cb541965e1984d1561f1a1c22d87
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746846"
---
# <a name="limit-search-results-with-rank"></a><span data-ttu-id="cfb40-102">Limitar los resultados de la búsqueda con RANK</span><span class="sxs-lookup"><span data-stu-id="cfb40-102">Limit Search Results with RANK</span></span>
  <span data-ttu-id="cfb40-103">Las funciones [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) y [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) devuelven una columna denominada RANK que contiene valores ordinales de 0 a 1000 (valores de intervalo).</span><span class="sxs-lookup"><span data-stu-id="cfb40-103">The [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) and [FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) functions return a column named RANK that contains ordinal values from 0 through 1000 (rank values).</span></span> <span data-ttu-id="cfb40-104">Estos valores se utilizan para clasificar las filas devueltas en función del grado de coincidencia con los criterios de selección.</span><span class="sxs-lookup"><span data-stu-id="cfb40-104">These values are used to rank the rows returned according to how well they match the selection criteria.</span></span> <span data-ttu-id="cfb40-105">Los valores de clasificación solo indican un orden relativo de relevancia de las filas en el conjunto de resultados, con un valor inferior que indica la relevancia menor.</span><span class="sxs-lookup"><span data-stu-id="cfb40-105">The rank values indicate only a relative order of relevance of the rows in the result set, with a lower value indicating lower relevance.</span></span> <span data-ttu-id="cfb40-106">Los valores reales carecen de relevancia y normalmente difieren cada vez que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="cfb40-106">The actual values are unimportant and typically differ each time the query is run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfb40-107">Los predicados CONTAINS y FREETEXT no devuelven ningún valor de clasificación.</span><span class="sxs-lookup"><span data-stu-id="cfb40-107">The CONTAINS and FREETEXT predicates do not return any rank values.</span></span>  
  
 <span data-ttu-id="cfb40-108">El número de elementos que coincide con una condición de búsqueda suele ser muy grande.</span><span class="sxs-lookup"><span data-stu-id="cfb40-108">The number of items matching a search condition is often very large.</span></span> <span data-ttu-id="cfb40-109">Para evitar que las consultas CONTAINSTABLE o FREETEXTTABLE devuelvan demasiadas coincidencias, use el parámetro opcional *top_n_by_rank* , que solo devuelve un subconjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="cfb40-109">To prevent CONTAINSTABLE or FREETEXTTABLE queries from returning too many matches, use the optional *top_n_by_rank* parameter, which returns only a subset of rows.</span></span> <span data-ttu-id="cfb40-110">*top_n_by_rank* es un valor entero, donde *n*especifica que solo se devuelvan las *n* coincidencias con la clasificación más alta, en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="cfb40-110">*top_n_by_rank* is an integer value, *n*, that specifies that only the *n* highest ranked matches are to be returned, in descending order.</span></span> <span data-ttu-id="cfb40-111">Si se combina *top_n_by_rank* con otros parámetros, es posible que la consulta devuelva menos filas de las que en realidad coinciden con todos los predicados.</span><span class="sxs-lookup"><span data-stu-id="cfb40-111">If *top_n_by_rank* is combined with other parameters, the query could return fewer rows than the number of rows that actually match all the predicates.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="cfb40-112">ordena las coincidencias por orden de clasificación y devuelve solo hasta el número especificado de filas.</span><span class="sxs-lookup"><span data-stu-id="cfb40-112">orders the matches by rank and returns only up to the specified number of rows.</span></span> <span data-ttu-id="cfb40-113">Esta opción puede aumentar significativamente el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="cfb40-113">This choice can result in a dramatic increase in performance.</span></span> <span data-ttu-id="cfb40-114">Por ejemplo, una consulta que por lo general devolvería 100.000 filas de una tabla de 1 millón se procesará de forma más rápida si solo se solicitan las 100 primeras filas.</span><span class="sxs-lookup"><span data-stu-id="cfb40-114">For example, a query that would normally return 100,000 rows from a table of one million rows are processed more quickly if only the top 100 rows are requested.</span></span>  
  
##  <a name="examples-of-using-rank-to-limit-search-results"></a><a name="examples"></a> <span data-ttu-id="cfb40-115">Ejemplos del uso de RANK para limitar los resultados de la búsqueda</span><span class="sxs-lookup"><span data-stu-id="cfb40-115">Examples of Using RANK to Limit Search Results</span></span>  
  
### <a name="example-a-searching-for-only-the-top-three-matches"></a><span data-ttu-id="cfb40-116">Ejemplo A: buscar solo las tres primeras coincidencias</span><span class="sxs-lookup"><span data-stu-id="cfb40-116">Example A: Searching for only the top three matches</span></span>  
 <span data-ttu-id="cfb40-117">En el ejemplo siguiente se usa CONTAINSTABLE para devolver las tres primeras coincidencias.</span><span class="sxs-lookup"><span data-stu-id="cfb40-117">The following example uses CONTAINSTABLE to return only the top three matches.</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT K.RANK, AddressLine1, City  
FROM Person.Address AS A  
  INNER JOIN  
  CONTAINSTABLE(Person.Address, AddressLine1, 'ISABOUT ("des*",  
    Rue WEIGHT(0.5),  
    Bouchers WEIGHT(0.9))',  
    3) AS K  
  ON A.AddressID = K.[KEY]  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
RANK        Address                          City  
----------- -------------------------------- ------------------------------  
172         9005, rue des Bouchers           Paris  
172         5, rue des Bouchers              Orleans  
172         5, rue des Bouchers              Metz  
  
(3 row(s) affected)  
```  
  
  
### <a name="example-b-searching-for-the-top-ten-matches"></a><span data-ttu-id="cfb40-118">Ejemplo B: buscar las diez primeras coincidencias</span><span class="sxs-lookup"><span data-stu-id="cfb40-118">Example B: Searching for the top ten matches</span></span>  
 <span data-ttu-id="cfb40-119">En el ejemplo siguiente se usa CONTAINSTABLE para devolver la descripción de los 5 productos más destacados, donde la columna `Description` contiene la palabra “aluminum” cerca de la palabra “light” o de la palabra “lightweight”.</span><span class="sxs-lookup"><span data-stu-id="cfb40-119">The following example uses CONTAINSTABLE to return the description of the top 5 products where the `Description` column contains the word "aluminum" near either the word "light" or the word "lightweight".</span></span>  
  
```  
USE AdventureWorks2012  
GO  
  
SELECT FT_TBL.ProductDescriptionID,  
   FT_TBL.Description,   
   KEY_TBL.RANK  
FROM Production.ProductDescription AS FT_TBL INNER JOIN  
   CONTAINSTABLE (Production.ProductDescription,  
      Description,   
      '(light NEAR aluminum) OR  
      (lightweight NEAR aluminum)',  
      5  
   ) AS KEY_TBL  
   ON FT_TBL.ProductDescriptionID = KEY_TBL.[KEY]  
GO  
```  
  
  
##  <a name="how-search-query-results-are-ranked"></a><a name="how"></a> <span data-ttu-id="cfb40-120">Cómo se clasifican los resultados de la consulta de búsqueda</span><span class="sxs-lookup"><span data-stu-id="cfb40-120">How Search Query Results Are Ranked</span></span>  
 <span data-ttu-id="cfb40-121">La búsqueda de texto completo de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] puede generar una puntuación (o valor de rango) opcional que indica la relevancia de los datos devueltos por una consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="cfb40-121">Full-text search in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] can generate an optional score (or rank value) that indicates the relevance of the data returned by a full-text query.</span></span> <span data-ttu-id="cfb40-122">Este valor de rango se calcula en cada fila y se puede utilizar como criterio de ordenación para ordenar el conjunto de resultados de una consulta determinada por relevancia.</span><span class="sxs-lookup"><span data-stu-id="cfb40-122">This rank value is calculated on every row and can be used as an ordering criteria to sort the result set of a given query by relevance.</span></span> <span data-ttu-id="cfb40-123">Los valores de clasificación solo indican un orden de importancia relativa de las filas en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="cfb40-123">The rank values indicate only a relative order of relevance of the rows in the result set.</span></span> <span data-ttu-id="cfb40-124">Los valores reales carecen de relevancia y normalmente difieren cada vez que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="cfb40-124">The actual values are unimportant and typically differ each time the query is run.</span></span> <span data-ttu-id="cfb40-125">El valor de rango no tiene importancia en las consultas.</span><span class="sxs-lookup"><span data-stu-id="cfb40-125">The rank value does not hold any significance across queries.</span></span>  
  
### <a name="statistics-for-ranking"></a><span data-ttu-id="cfb40-126">Estadísticas de clasificación</span><span class="sxs-lookup"><span data-stu-id="cfb40-126">Statistics for Ranking</span></span>  
 <span data-ttu-id="cfb40-127">Cuando se compila un índice, se recopilan estadísticas para usarlas en la clasificación.</span><span class="sxs-lookup"><span data-stu-id="cfb40-127">When an index is built, statistics are collected for use in ranking.</span></span> <span data-ttu-id="cfb40-128">El proceso de creación de un catálogo de texto completo no produce directamente una única estructura de índice.</span><span class="sxs-lookup"><span data-stu-id="cfb40-128">The process of building a full-text catalog does not directly result in a single index structure.</span></span> <span data-ttu-id="cfb40-129">En su lugar, el motor de búsqueda de texto completo para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] crea índices intermedios a medida que se indizan los datos.</span><span class="sxs-lookup"><span data-stu-id="cfb40-129">Instead, the Full-Text Engine for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] creates intermediate indexes as data is indexed.</span></span> <span data-ttu-id="cfb40-130">El motor de búsqueda de texto completo combina después dichos índices en un índice mayor, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="cfb40-130">The Full-Text Engine then merges these indexes into a larger index as needed.</span></span> <span data-ttu-id="cfb40-131">Este proceso puede repetirse muchas veces.</span><span class="sxs-lookup"><span data-stu-id="cfb40-131">This process can be repeated many times.</span></span> <span data-ttu-id="cfb40-132">A continuación, el motor de búsqueda de texto completo realiza una "mezcla maestra" que combina todos los índices intermedios en un gran índice maestro.</span><span class="sxs-lookup"><span data-stu-id="cfb40-132">The Full-Text Engine then conducts a "master merge" that combines all of the intermediate indexes into one large master index.</span></span>  
  
 <span data-ttu-id="cfb40-133">En cada índice intermedio se recopilan estadísticas,</span><span class="sxs-lookup"><span data-stu-id="cfb40-133">Statistics are collected at each intermediate index level.</span></span> <span data-ttu-id="cfb40-134">que se mezclan cuando se mezclan los índices.</span><span class="sxs-lookup"><span data-stu-id="cfb40-134">The statistics are merged when the indexes are merged.</span></span> <span data-ttu-id="cfb40-135">Algunos valores estadísticos solo pueden generarse durante el proceso de mezcla maestra.</span><span class="sxs-lookup"><span data-stu-id="cfb40-135">Some statistical values can only be generated during the master merging process.</span></span>  
  
 <span data-ttu-id="cfb40-136">Mientras se clasifica un conjunto de resultados de consulta, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utiliza las estadísticas del índice intermedio más grande.</span><span class="sxs-lookup"><span data-stu-id="cfb40-136">While ranking a query result set, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses statistics from the largest intermediate index.</span></span> <span data-ttu-id="cfb40-137">Dependerá de si se han mezclado o no los índices intermedios.</span><span class="sxs-lookup"><span data-stu-id="cfb40-137">This depends on whether intermediate indexes have been merged or not.</span></span> <span data-ttu-id="cfb40-138">Como resultado, las estadísticas de clasificación serán más o menos precisas si no se han mezclado los índices intermedios.</span><span class="sxs-lookup"><span data-stu-id="cfb40-138">As a result, ranking statistics can vary in accuracy if the intermediate indexes have not been merged.</span></span> <span data-ttu-id="cfb40-139">Por este motivo, una misma consulta puede devolver con el tiempo distintos resultados de rango, a medida que se agreguen, modifiquen y eliminen los datos de índices de texto completo, y se vayan combinando los índices de menor tamaño.</span><span class="sxs-lookup"><span data-stu-id="cfb40-139">This explains why the same query can return different rank results over time as full-text indexed data is added, modified, and deleted, and as the smaller indexes are merged.</span></span>  
  
 <span data-ttu-id="cfb40-140">Para minimizar el tamaño del índice y la complejidad del cálculo, se suelen redondear las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="cfb40-140">To minimize the size of the index and computational complexity, statistics are often rounded.</span></span>  
  
 <span data-ttu-id="cfb40-141">En la siguiente lista se mencionan algunos términos y valores estadísticos de uso frecuente que son importantes para calcular la clasificación.</span><span class="sxs-lookup"><span data-stu-id="cfb40-141">The list below includes some commonly used terms and statistical values that are important in calculating rank.</span></span>  
  
 <span data-ttu-id="cfb40-142">Propiedad</span><span class="sxs-lookup"><span data-stu-id="cfb40-142">Property</span></span>  
 <span data-ttu-id="cfb40-143">Una columna indizada de texto completo de la fila.</span><span class="sxs-lookup"><span data-stu-id="cfb40-143">A full-text indexed column of the row.</span></span>  
  
 <span data-ttu-id="cfb40-144">Documento</span><span class="sxs-lookup"><span data-stu-id="cfb40-144">Document</span></span>  
 <span data-ttu-id="cfb40-145">Entidad que se devuelve en las consultas.</span><span class="sxs-lookup"><span data-stu-id="cfb40-145">The entity that is returned in queries.</span></span> <span data-ttu-id="cfb40-146">En [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , se corresponde con una fila.</span><span class="sxs-lookup"><span data-stu-id="cfb40-146">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] this corresponds to a row.</span></span> <span data-ttu-id="cfb40-147">Un documento puede tener varias propiedades, de igual forma que una fila puede tener varias columnas indizadas de texto completo.</span><span class="sxs-lookup"><span data-stu-id="cfb40-147">A document can have multiple properties, just as a row can have multiple full-text indexed columns.</span></span>  
  
 <span data-ttu-id="cfb40-148">Índice</span><span class="sxs-lookup"><span data-stu-id="cfb40-148">Index</span></span>  
 <span data-ttu-id="cfb40-149">Un único índice invertido de uno o varios documentos.</span><span class="sxs-lookup"><span data-stu-id="cfb40-149">A single inverted index of one or more documents.</span></span> <span data-ttu-id="cfb40-150">Puede almacenarse completamente en la memoria o en disco.</span><span class="sxs-lookup"><span data-stu-id="cfb40-150">This may be entirely in memory or on disk.</span></span> <span data-ttu-id="cfb40-151">Muchas estadísticas de consultas son relativas al índice individual donde se produjo la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="cfb40-151">Many query statistics are relative to the individual index where the match occurred.</span></span>  
  
 <span data-ttu-id="cfb40-152">Catálogo de texto completo</span><span class="sxs-lookup"><span data-stu-id="cfb40-152">Full-Text Catalog</span></span>  
 <span data-ttu-id="cfb40-153">Colección de índices intermedios que se considera como una sola entidad en las consultas.</span><span class="sxs-lookup"><span data-stu-id="cfb40-153">A collection of intermediate indexes treated as one entity for queries.</span></span> <span data-ttu-id="cfb40-154">Los catálogos son la unidad de organización visible para el administrador de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cfb40-154">Catalogs are the unit of organization visible to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="cfb40-155">Palabra, token o elemento</span><span class="sxs-lookup"><span data-stu-id="cfb40-155">Word, token or item</span></span>  
 <span data-ttu-id="cfb40-156">Unidad coincidente en el motor de texto completo.</span><span class="sxs-lookup"><span data-stu-id="cfb40-156">The unit of matching in the full-text engine.</span></span> <span data-ttu-id="cfb40-157">Los flujos de texto de los documentos se acortan formando palabras o tokens, gracias a los separadores de palabras específicos del idioma.</span><span class="sxs-lookup"><span data-stu-id="cfb40-157">Streams of text from documents are tokenized into words, or tokens by language-specific word breakers.</span></span>  
  
 <span data-ttu-id="cfb40-158">Repetición</span><span class="sxs-lookup"><span data-stu-id="cfb40-158">Occurrence</span></span>  
 <span data-ttu-id="cfb40-159">Desplazamiento de las palabras en una propiedad de documento, tal y como lo determina el separador de palabras.</span><span class="sxs-lookup"><span data-stu-id="cfb40-159">The word offset in a document property as determined by the word breaker.</span></span> <span data-ttu-id="cfb40-160">La primera palabra se encuentra en la repetición 1, la siguiente en la 2 y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="cfb40-160">The first word is at occurrence 1, the next at 2, and so on.</span></span> <span data-ttu-id="cfb40-161">Para evitar falsos positivos en las consultas de frases y de proximidad, al final de las frases y de los párrafos se insertan mayores espacios de repetición.</span><span class="sxs-lookup"><span data-stu-id="cfb40-161">In order to avoid false positives in phrase and proximity queries, end-of-sentence and end-of-paragraph introduce larger occurrence gaps.</span></span>  
  
 <span data-ttu-id="cfb40-162">TermFrequency</span><span class="sxs-lookup"><span data-stu-id="cfb40-162">TermFrequency</span></span>  
 <span data-ttu-id="cfb40-163">Número de repeticiones del valor de clave en una fila.</span><span class="sxs-lookup"><span data-stu-id="cfb40-163">The number times the key value occurs in a row.</span></span>  
  
 <span data-ttu-id="cfb40-164">IndexedRowCount</span><span class="sxs-lookup"><span data-stu-id="cfb40-164">IndexedRowCount</span></span>  
 <span data-ttu-id="cfb40-165">Número total de filas indizadas.</span><span class="sxs-lookup"><span data-stu-id="cfb40-165">Total number of rows indexed.</span></span> <span data-ttu-id="cfb40-166">Se calcula a partir de los recuentos mantenidos en los índices intermedios.</span><span class="sxs-lookup"><span data-stu-id="cfb40-166">This is computed, based on counts maintained in the intermediate indexes.</span></span> <span data-ttu-id="cfb40-167">Este número puede ser más o menos preciso.</span><span class="sxs-lookup"><span data-stu-id="cfb40-167">This number can vary in accuracy.</span></span>  
  
 <span data-ttu-id="cfb40-168">KeyRowCount</span><span class="sxs-lookup"><span data-stu-id="cfb40-168">KeyRowCount</span></span>  
 <span data-ttu-id="cfb40-169">Número total de filas del catálogo de texto completo que contienen una determinada clave.</span><span class="sxs-lookup"><span data-stu-id="cfb40-169">Total number of rows in the full-text catalog that contain a given key.</span></span>  
  
 <span data-ttu-id="cfb40-170">MaxOccurrence</span><span class="sxs-lookup"><span data-stu-id="cfb40-170">MaxOccurrence</span></span>  
 <span data-ttu-id="cfb40-171">Número máximo de repeticiones de una determinada propiedad de una fila, almacenadas en un catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="cfb40-171">The largest occurrence stored in a full-text catalog for a given property in a row.</span></span>  
  
 <span data-ttu-id="cfb40-172">MaxQueryRank</span><span class="sxs-lookup"><span data-stu-id="cfb40-172">MaxQueryRank</span></span>  
 <span data-ttu-id="cfb40-173">El rango máximo, 1000, devuelto por el motor de búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="cfb40-173">The maximum rank, 1000, returned by the Full-Text Engine.</span></span>  
  
  
### <a name="rank-computation-issues"></a><span data-ttu-id="cfb40-174">Problemas de cálculo de rango</span><span class="sxs-lookup"><span data-stu-id="cfb40-174">Rank Computation Issues</span></span>  
 <span data-ttu-id="cfb40-175">El proceso de cálculo de rango depende de varios factores.</span><span class="sxs-lookup"><span data-stu-id="cfb40-175">The process of computing rank, depends on a number of factors.</span></span>  <span data-ttu-id="cfb40-176">Los separadores de palabras de cada uno de los idiomas acortan el texto de forma distinta.</span><span class="sxs-lookup"><span data-stu-id="cfb40-176">Different language word breakers tokenize text differently.</span></span> <span data-ttu-id="cfb40-177">Por ejemplo, un separador de palabras podría separar la cadena "dog-house" en "dog" "house" y otro en "dog-house".</span><span class="sxs-lookup"><span data-stu-id="cfb40-177">For example, the string "dog-house" could be broken into "dog" "house" by one word breaker and into "dog-house" by another.</span></span> <span data-ttu-id="cfb40-178">Por este motivo, las coincidencias y las categorías variarán en función del idioma especificado, ya que no solo son distintas las palabras sino también la longitud del documento.</span><span class="sxs-lookup"><span data-stu-id="cfb40-178">This means that matching and ranking will vary based on the language specified, because not only are the words different, but so is the document length.</span></span> <span data-ttu-id="cfb40-179">La diferencia de longitud del documento puede afectar a las categorías de todas las consultas.</span><span class="sxs-lookup"><span data-stu-id="cfb40-179">The document length difference can affect ranking for all queries.</span></span>  
  
 <span data-ttu-id="cfb40-180">Las estadísticas como `IndexRowCount` pueden variar enormemente.</span><span class="sxs-lookup"><span data-stu-id="cfb40-180">Statistics such as `IndexRowCount` can vary widely.</span></span> <span data-ttu-id="cfb40-181">Por ejemplo, si un catálogo tiene 2.000 millones de filas en el índice maestro, un nuevo documento se indizará en un índice intermedio de la memoria y los rangos de dicho documento basados en el número de documentos en el índice almacenado en la memoria podrían desviarse de los rangos de los documentos del índice maestro.</span><span class="sxs-lookup"><span data-stu-id="cfb40-181">For example, if a catalog has 2 billion rows in the master index, then one new document is indexed into an in-memory intermediate index, and ranks for that document based on the number of documents in the in-memory index could be skewed compared with ranks for documents from the master index.</span></span> <span data-ttu-id="cfb40-182">Por este motivo, tras realizar un llenado que dé como resultado la indización o reindización de un gran número de filas, se recomienda mezclar los índices en un índice maestro mediante la instrucción ALTER FULLTEXT CATALOG ... REORGANIZE de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cfb40-182">For this reason, it is recommended that after any population that results in large number of rows being indexed or re-indexed the indexes be merged into a master index using the ALTER FULLTEXT CATALOG ... REORGANIZE [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="cfb40-183">El motor de búsqueda de texto completo también mezclará automáticamente los índices basándose en parámetros como el número y el tamaño de los índices intermedios.</span><span class="sxs-lookup"><span data-stu-id="cfb40-183">The Full-Text Engine will also automatically merge the indexes based on parameters such as the number and size of intermediate indexes.</span></span>  
  
 <span data-ttu-id="cfb40-184">Los valores de `MaxOccurrence` se normalizan en 1 de 32 intervalos.</span><span class="sxs-lookup"><span data-stu-id="cfb40-184">`MaxOccurrence` values are normalized into 1 of 32 ranges.</span></span> <span data-ttu-id="cfb40-185">Esto significa que, por ejemplo, un documento de 50 palabras se trata igual que un documento de 100 palabras.</span><span class="sxs-lookup"><span data-stu-id="cfb40-185">This means, for example, that a document 50 words long is treated the same as a document 100 words long.</span></span> <span data-ttu-id="cfb40-186">A continuación se muestra la tabla utilizada para la normalización.</span><span class="sxs-lookup"><span data-stu-id="cfb40-186">Below is the table used for normalization.</span></span> <span data-ttu-id="cfb40-187">Dado que las longitudes del documento están en el intervalo entre los valores de tabla adyacentes 32 y 128, se tratan de forma eficaz como si tuvieran la misma longitud, 128 (32 < `docLength` <= 128).</span><span class="sxs-lookup"><span data-stu-id="cfb40-187">Because the document lengths are in the range between adjacent table values 32 and 128, they are effectively treated as having the same length, 128 (32 < `docLength` <= 128).</span></span>  
  
```  
{ 16, 32, 128, 256, 512, 725, 1024, 1450, 2048, 2896, 4096, 5792, 8192, 11585,   
16384, 23170, 28000, 32768, 39554, 46340, 55938, 65536, 92681, 131072, 185363,   
262144, 370727, 524288, 741455, 1048576, 2097152, 4194304 };  
  
```  
  
  
### <a name="ranking-of-containstable"></a><span data-ttu-id="cfb40-188">Categoría de CONTAINSTABLE</span><span class="sxs-lookup"><span data-stu-id="cfb40-188">Ranking of CONTAINSTABLE</span></span>  
 <span data-ttu-id="cfb40-189">La clasificación de[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) usa el algoritmo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cfb40-189">[CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) ranking uses the following algorithm:</span></span>  
  
```  
StatisticalWeight = Log2( ( 2 + IndexedRowCount ) / KeyRowCount )  
Rank = min( MaxQueryRank, HitCount * 16 * StatisticalWeight / MaxOccurrence )  
```  
  
 <span data-ttu-id="cfb40-190">Las coincidencias de frases se clasifican del mismo modo que las claves individuales, excepto en que `KeyRowCount` (número de filas que contienen la frase) se calcula y puede ser impreciso y superior al número real.</span><span class="sxs-lookup"><span data-stu-id="cfb40-190">Phrase matches are ranked just like individual keys except that `KeyRowCount` (the number of rows containing the phrase) is estimated and can be inaccurate and higher than the actual number.</span></span>  
  
 <span data-ttu-id="cfb40-191">**Categoría de NEAR**</span><span class="sxs-lookup"><span data-stu-id="cfb40-191">**Ranking of NEAR**</span></span>  
  
 <span data-ttu-id="cfb40-192">CONTAINSTABLE admite las consultas de dos o más términos de búsqueda que estén próximos, mediante la opción NEAR.</span><span class="sxs-lookup"><span data-stu-id="cfb40-192">CONTAINSTABLE supports querying for two or more search terms in proximity to each other by using the NEAR option.</span></span> <span data-ttu-id="cfb40-193">El valor de rango de cada fila devuelta se basa en varios parámetros.</span><span class="sxs-lookup"><span data-stu-id="cfb40-193">The rank value of each returned row is based on several parameters.</span></span> <span data-ttu-id="cfb40-194">Un factor de rango importante es el número total de coincidencias (o *aciertos*) en relación con la longitud del documento.</span><span class="sxs-lookup"><span data-stu-id="cfb40-194">One major ranking factor is the total number of matches (or *hits*) relative to the length of the document.</span></span> <span data-ttu-id="cfb40-195">Por ejemplo, si un documento de 100 palabras y un documento de 900 palabras contienen las mismas coincidencias, el de 100 palabras tiene un rango superior.</span><span class="sxs-lookup"><span data-stu-id="cfb40-195">Thus, for example, if a 100-word document and a 900-word document contain identical matches, the 100-word document is ranked higher.</span></span>  
  
 <span data-ttu-id="cfb40-196">La longitud total de cada acierto en una fila también contribuirá al rango de esa fila en función de la distancia entre los términos de búsqueda primero y último de ese acierto.</span><span class="sxs-lookup"><span data-stu-id="cfb40-196">The total length of each hit in a row will also contribute to the ranking of that row based on the distance between the first and last search terms of that hit.</span></span> <span data-ttu-id="cfb40-197">Cuanto menor sea la distancia, más contribuye el acierto al valor de rango de la fila.</span><span class="sxs-lookup"><span data-stu-id="cfb40-197">The smaller the distance, the more the hit contributes to the rank value of the row.</span></span> <span data-ttu-id="cfb40-198">Si en una consulta de texto completo no se especifica un entero como la distancia máxima, un documento que solo tenga aciertos cuyas distancias sean mayores de 100 términos lógicos tendrá un rango de 0.</span><span class="sxs-lookup"><span data-stu-id="cfb40-198">If a full-text query does not specify an integer as the maximum distance, a document that contains only hits whose distances are greater than 100 logical terms apart, will have a ranking of 0.</span></span>  
  
 <span data-ttu-id="cfb40-199">**Categoría de ISABOUT**</span><span class="sxs-lookup"><span data-stu-id="cfb40-199">**Ranking of ISABOUT**</span></span>  
  
 <span data-ttu-id="cfb40-200">CONTAINSTABLE permite consultar los términos ponderados utilizando la opción ISABOUT.</span><span class="sxs-lookup"><span data-stu-id="cfb40-200">CONTAINSTABLE supports querying for weighted terms by using the ISABOUT option.</span></span> <span data-ttu-id="cfb40-201">ISABOUT es lo que se denomina consulta de espacio vectorial en la terminología tradicional de recuperación de información.</span><span class="sxs-lookup"><span data-stu-id="cfb40-201">ISABOUT is a vector-space query in traditional information retrieval terminology.</span></span> <span data-ttu-id="cfb40-202">El algoritmo de clasificación predeterminado que se utiliza es Jaccard, una fórmula muy conocida.</span><span class="sxs-lookup"><span data-stu-id="cfb40-202">The default ranking algorithm used is Jaccard, a widely known formula.</span></span> <span data-ttu-id="cfb40-203">La clasificación se calcula para cada término de la consulta y se combina del modo que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="cfb40-203">The ranking is computed for each term in the query and then combined as described below.</span></span>  
  
```  
ContainsRank = same formula used for CONTAINSTABLE ranking of a single term (above).  
Weight = the weight specified in the query for each term. Default weight is 1.  
WeightedSum = ??[key=1 to n] ContainsRankKey * WeightKey  
Rank =  ( MaxQueryRank * WeightedSum ) / ( ( ??[key=1 to n] ContainsRankKey^2 )   
      + ( ??[key=1 to n] WeightKey^2 ) - ( WeightedSum ) )  
  
```  
  
  
### <a name="ranking-of-freetexttable"></a><span data-ttu-id="cfb40-204">Categoría de FREETEXTTABLE</span><span class="sxs-lookup"><span data-stu-id="cfb40-204">Ranking of FREETEXTTABLE</span></span>  
 <span data-ttu-id="cfb40-205">La clasificación de[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) se basa en la fórmula de clasificación OKAPI BM25.</span><span class="sxs-lookup"><span data-stu-id="cfb40-205">[FREETEXTTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) ranking is based on the OKAPI BM25 ranking formula.</span></span> <span data-ttu-id="cfb40-206">Las consultas FREETEXTTABLE agregarán palabras a la consulta a través de la generación de formas con inflexión de las palabras originales de la consulta; estas palabras se tratan como palabras independientes sin ninguna relación especial con las palabras a partir de las cuales se generan.</span><span class="sxs-lookup"><span data-stu-id="cfb40-206">FREETEXTTABLE queries will add words to the query via inflectional generation (inflected forms of the original query words); these words are treated as separate words with no special relationship to the words from which they were generated.</span></span> <span data-ttu-id="cfb40-207">Los sinónimos que se generan con la característica de diccionario de sinónimos se tratan como términos independientes del mismo peso.</span><span class="sxs-lookup"><span data-stu-id="cfb40-207">Synonyms generated from the Thesaurus feature are treated as separate, equally weighted terms.</span></span> <span data-ttu-id="cfb40-208">Cada palabra de la consulta contribuye al rango.</span><span class="sxs-lookup"><span data-stu-id="cfb40-208">Each word in the query contributes to the rank.</span></span>  
  
```  
Rank = ??[Terms in Query] w ( ( ( k1 + 1 ) tf ) / ( K + tf ) ) * ( ( k3 + 1 ) qtf / ( k3 + qtf ) ) )  
Where:   
w is the Robertson-Sparck Jones weight.   
In simplified form, w is defined as:   
w = log10 ( ( ( r + 0.5 ) * ( N - R + r + 0.5 ) ) / ( ( R - r + 0.5 ) * ( n - r + 0.5 ) )  
N is the number of indexed rows for the property being queried.   
n is the number of rows containing the word.   
K is ( k1 * ( ( 1 - b ) + ( b * dl / avdl ) ) ).   
dl is the property length, in word occurrences.   
avdl is the average length of the property being queried, in word occurrences.   
k1, b, and k3 are the constants 1.2, 0.75, and 8.0, respectively.   
tf is the frequency of the word in the queried property in a specific row.   
qtf is the frequency of the term in the query.   
```  
  
  
## <a name="see-also"></a><span data-ttu-id="cfb40-209">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cfb40-209">See Also</span></span>  
 [<span data-ttu-id="cfb40-210">Consultar con búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="cfb40-210">Query with Full-Text Search</span></span>](query-with-full-text-search.md)  
  
  
