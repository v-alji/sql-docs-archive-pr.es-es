---
title: Buscar palabras cerca de otra palabra con NEAR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- word searches [full-text search]
- NEAR option [full-text search]
- phrase searches [full-text search]
- proximity searches [full-text search]
- full-text search [SQL Server], proximity searches
- full-text queries [SQL Server], proximity
- queries [full-text search], proximity
ms.assetid: 87520646-4865-49ae-8790-f766b80a41f3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8c2d187ea3ed951ac6f17eb4babc5f4f77451d4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747552"
---
# <a name="search-for-words-close-to-another-word-with-near"></a><span data-ttu-id="6b27f-102">Buscar palabras cerca de otra palabra con NEAR</span><span class="sxs-lookup"><span data-stu-id="6b27f-102">Search for Words Close to Another Word with NEAR</span></span>
  <span data-ttu-id="6b27f-103">Puede usar un término de proximidad (NEAR) en un predicado [CONTAINS](/sql/t-sql/queries/contains-transact-sql) o en una función [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) para buscar palabras o frases que están cerca unas de otras.</span><span class="sxs-lookup"><span data-stu-id="6b27f-103">You can use a proximity term (NEAR) in a [CONTAINS](/sql/t-sql/queries/contains-transact-sql) predicate or [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) function to search for words or phrases near one another.</span></span> <span data-ttu-id="6b27f-104">También puede especificar el número máximo de términos de no búsqueda que separan el primero y el último término de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6b27f-104">You can also specify the maximum number of non-search terms that separate the first and last search terms.</span></span> <span data-ttu-id="6b27f-105">Además, puede buscar palabras o frases en cualquier orden o puede buscar palabras y frases en el orden en el que las especifique.</span><span class="sxs-lookup"><span data-stu-id="6b27f-105">In addition, you can search for words or phrases in any order, or you can search for words and phrases in the order in which you specify them.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]<span data-ttu-id="6b27f-106">admite el anterior [término de proximidad genérico](#Generic_NEAR), que ahora está en desuso, y el [término de proximidad personalizado](#Custom_NEAR), que es nuevo en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6b27f-106">supports both the earlier [generic proximity term](#Generic_NEAR), which is now deprecated, and the [custom proximity term](#Custom_NEAR), which is new in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].</span></span>  
  
##  <a name="the-custom-proximity-term"></a><a name="Custom_NEAR"></a><span data-ttu-id="6b27f-107">El término de proximidad personalizado</span><span class="sxs-lookup"><span data-stu-id="6b27f-107">The Custom Proximity Term</span></span>  
 <span data-ttu-id="6b27f-108">El término de proximidad personalizado presenta las siguientes capacidades nuevas:</span><span class="sxs-lookup"><span data-stu-id="6b27f-108">The custom proximity term introduces the following new capabilities:</span></span>  
  
-   <span data-ttu-id="6b27f-109">Puede especificar el número máximo de términos de no búsqueda, o *distancia máxima*, que separa el primero y el último término de búsqueda para que haya una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="6b27f-109">You can specify the maximum number of non-search terms, or *maximum distance*, that separates the first and last search terms in order to constitute a match.</span></span>  
  
-   <span data-ttu-id="6b27f-110">Si especifica el número máximo de términos, también puede especificar que las coincidencias deben contener los términos de búsqueda en el orden especificado.</span><span class="sxs-lookup"><span data-stu-id="6b27f-110">If you specify the maximum number of terms, you can also specify that matches must contain the search terms in the specified order.</span></span>  
  
 <span data-ttu-id="6b27f-111">Para que se considere una coincidencia, una cadena de texto debe:</span><span class="sxs-lookup"><span data-stu-id="6b27f-111">To qualify as a match, a string of text must:</span></span>  
  
-   <span data-ttu-id="6b27f-112">Empezar con uno de los términos de búsqueda especificados y terminar con el otro término de búsqueda especificado.</span><span class="sxs-lookup"><span data-stu-id="6b27f-112">Start with one of the specified search terms and end with the one of the other specified search terms.</span></span>  
  
-   <span data-ttu-id="6b27f-113">Contener todos los términos de búsqueda especificados.</span><span class="sxs-lookup"><span data-stu-id="6b27f-113">Contain all of the specified search terms.</span></span>  
  
-   <span data-ttu-id="6b27f-114">El número de términos de no búsqueda, incluidas las palabras irrelevantes, que hay entre el primero y el último término de búsqueda debe ser menor o igual que la distancia máxima, si se especifica.</span><span class="sxs-lookup"><span data-stu-id="6b27f-114">The number of non-search terms, including stopwords, that occur between the first and last search terms must be less than or equal to the maximum distance, if specified.</span></span>  
  
 <span data-ttu-id="6b27f-115">La sintaxis básica es:</span><span class="sxs-lookup"><span data-stu-id="6b27f-115">The basic syntax is:</span></span>  
  
 <span data-ttu-id="6b27f-116">NEAR (</span><span class="sxs-lookup"><span data-stu-id="6b27f-116">NEAR (</span></span>  
  
 <span data-ttu-id="6b27f-117">{</span><span class="sxs-lookup"><span data-stu-id="6b27f-117">{</span></span>  
  
 <span data-ttu-id="6b27f-118">*search_term* [,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="6b27f-118">*search_term* [ ,...*n* ]</span></span>  
  
 |  
  
 <span data-ttu-id="6b27f-119">(*search_term* [,... *n* ]) [, <maximum_distance> [, <match_order>]]</span><span class="sxs-lookup"><span data-stu-id="6b27f-119">(*search_term* [ ,...*n* ] ) [, <maximum_distance> [, <match_order> ] ]</span></span>  
  
 <span data-ttu-id="6b27f-120">}</span><span class="sxs-lookup"><span data-stu-id="6b27f-120">}</span></span>  
  
 <span data-ttu-id="6b27f-121">)</span><span class="sxs-lookup"><span data-stu-id="6b27f-121">)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b27f-122">Para obtener más información sobre la sintaxis de <término_proximidad_personalizado>, vea [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6b27f-122">For more information about the <custom_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="6b27f-123">Por ejemplo, podría buscar 'John' a dos términos de 'Smith', de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="6b27f-123">For example, you could search for 'John' within two terms of 'Smith', as follows:</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((John, Smith), 2)')  
```  
  
 <span data-ttu-id="6b27f-124">Algunos ejemplos de cadenas que coinciden son "`John Jacob Smith`" y "`Smith, John`".</span><span class="sxs-lookup"><span data-stu-id="6b27f-124">Some examples of strings that match are "`John Jacob Smith`" and "`Smith, John`".</span></span> <span data-ttu-id="6b27f-125">La cadena "`John Jones knows Fred Smith`" contiene tres términos de no búsqueda activos, por lo que no es una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="6b27f-125">The string "`John Jones knows Fred Smith`" contains three intervening non-search terms, so it is not a match.</span></span>  
  
 <span data-ttu-id="6b27f-126">Para exigir que los términos se encuentren en el orden especificado, cambiaría el término de proximidad del ejemplo a `NEAR((John, Smith),2, TRUE).` Esto busca "`John`" a dos términos de "`Smith`" pero solo cuando "`John`" precede a "`Smith`".</span><span class="sxs-lookup"><span data-stu-id="6b27f-126">To require that the terms be found in the specified order, you would change the example proximity term to `NEAR((John, Smith),2, TRUE).` This searches for "`John`" within two terms of "`Smith`" but only when "`John`" precedes "`Smith`".</span></span> <span data-ttu-id="6b27f-127">En un idioma que se lee de izquierda a derecha, como el inglés, un ejemplo de cadena coincidente es "`John Jacob Smith`.</span><span class="sxs-lookup"><span data-stu-id="6b27f-127">In a language that reads from left to right, such as English, an example of a string that matches is "`John Jacob Smith`".</span></span>  
  
 <span data-ttu-id="6b27f-128">Tenga en cuenta que en un idioma que se lee de derecha a izquierda, como el árabe o el hebreo, el Motor de búsqueda de texto completo aplica en orden inverso los términos especificados.</span><span class="sxs-lookup"><span data-stu-id="6b27f-128">Note that for a language that reads from right to left, such as Arabic or Hebrew, the Full-Text Engine applies the specified terms in reverse order.</span></span> <span data-ttu-id="6b27f-129">Asimismo, el Explorador de objetos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] invierte automáticamente el orden de presentación de las palabras especificadas en los idiomas que se leen de derecha a izquierda.</span><span class="sxs-lookup"><span data-stu-id="6b27f-129">Also, Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] automatically reverses the display order of words specified in right-to-left languages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b27f-130">Para obtener más información, vea "[Consideraciones adicionales sobre las búsquedas de proximidad](#Additional_Considerations)," más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="6b27f-130">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="how-maximum-distance-is-measured"></a><span data-ttu-id="6b27f-131">Cómo se mide la distancia máxima</span><span class="sxs-lookup"><span data-stu-id="6b27f-131">How Maximum Distance Is Measured</span></span>  
 <span data-ttu-id="6b27f-132">Una distancia máxima concreta, como 10 ó 25, determina cuántos términos de no búsqueda, incluidas las palabras irrelevantes, puede haber entre el primero y el último término de búsqueda en una cadena determinada.</span><span class="sxs-lookup"><span data-stu-id="6b27f-132">A specific maximum distance, such as 10 or 25, determines how many non-search terms, including stopwords, can occur between the first and last search terms in a given string.</span></span> <span data-ttu-id="6b27f-133">Por ejemplo, `NEAR((dogs, cats, "hunting mice"), 3)` devolverían la siguiente fila, en la que el número total de términos de no búsqueda es tres ("`enjoy`", "`but`" y "`avoid`"):</span><span class="sxs-lookup"><span data-stu-id="6b27f-133">For example, `NEAR((dogs, cats, "hunting mice"), 3)` would return the following row, in which the total number of non-search terms is three ("`enjoy`", "`but`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="6b27f-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="6b27f-134">"`Cats` `enjoy` `hunting mice``, but avoid` `dogs``.`"</span></span>  
  
 <span data-ttu-id="6b27f-135">El mismo término de proximidad no devolvería la siguiente fila, ya que los cuatro términos de no búsqueda ("`enjoy`", "`but`", "`usually`" y "`avoid`") superan la distancia máxima:</span><span class="sxs-lookup"><span data-stu-id="6b27f-135">The same proximity term would not return the following row, because the maximum distance is exceeded by the four non-search terms ("`enjoy`", "`but`", "`usually`", and "`avoid`"):</span></span>  
  
 <span data-ttu-id="6b27f-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span><span class="sxs-lookup"><span data-stu-id="6b27f-136">"`Cats` `enjoy` `hunting mice``, but usually avoid` `dogs``.`"</span></span>  
  
### <a name="combining-a-custom-proximity-term-with-other-terms"></a><span data-ttu-id="6b27f-137">Combinar un término de proximidad personalizado con otros términos</span><span class="sxs-lookup"><span data-stu-id="6b27f-137">Combining a Custom Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="6b27f-138">Puede combinar un término de proximidad personalizado con algunos otros términos.</span><span class="sxs-lookup"><span data-stu-id="6b27f-138">You can combine a custom proximity term with some other terms.</span></span> <span data-ttu-id="6b27f-139">Puede usar AND (&), OR (|) o AND NOT (&!) para combinar un término de proximidad personalizado con otro término de proximidad personalizado, un término simple o un término de prefijo.</span><span class="sxs-lookup"><span data-stu-id="6b27f-139">You can use AND (&), OR (|), or AND NOT (&!) to combine a custom proximity term with another custom proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="6b27f-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6b27f-140">For example:</span></span>  
  
-   <span data-ttu-id="6b27f-141">CONTAINS('NEAR((*term1*,*term2*),5) AND *term3*')</span><span class="sxs-lookup"><span data-stu-id="6b27f-141">CONTAINS('NEAR((*term1*,*term2*),5) AND *term3*')</span></span>  
  
-   <span data-ttu-id="6b27f-142">CONTAINS('NEAR((*term1*,*term2*),5) OR *term3*')</span><span class="sxs-lookup"><span data-stu-id="6b27f-142">CONTAINS('NEAR((*term1*,*term2*),5) OR *term3*')</span></span>  
  
-   <span data-ttu-id="6b27f-143">CONTAINS('NEAR((*term1*,*term2*),5) AND NOT *term3*')</span><span class="sxs-lookup"><span data-stu-id="6b27f-143">CONTAINS('NEAR((*term1*,*term2*),5) AND NOT *term3*')</span></span>  
  
-   <span data-ttu-id="6b27f-144">CONTAINS('NEAR((*term1*,*term2*),5) AND NEAR((*term3*,*term4*),2)')</span><span class="sxs-lookup"><span data-stu-id="6b27f-144">CONTAINS('NEAR((*term1*,*term2*),5) AND NEAR((*term3*,*term4*),2)')</span></span>  
  
-   <span data-ttu-id="6b27f-145">CONTAINS('NEAR((*term1*,*term2*),5) OR NEAR((*term3*,*term4*),2, TRUE)')</span><span class="sxs-lookup"><span data-stu-id="6b27f-145">CONTAINS('NEAR((*term1*,*term2*),5) OR NEAR((*term3*,*term4*),2, TRUE)')</span></span>  
  
 <span data-ttu-id="6b27f-146">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="6b27f-146">For example,</span></span>  
  
```  
CONTAINS(column_name, 'NEAR((term1, term2), 5, TRUE) AND term3')  
```  
  
 <span data-ttu-id="6b27f-147">No se puede combinar un término de proximidad personalizado con un término de proximidad genérico (*term1* cerca de *term2*), un término de generación (isabout...) o un término ponderado (FORMSOF...).</span><span class="sxs-lookup"><span data-stu-id="6b27f-147">You cannot combine a custom proximity term with a generic proximity term (*term1* NEAR *term2*), a generation term (ISABOUT ...), or a weighted term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-custom-proximity-term"></a><span data-ttu-id="6b27f-148">Ejemplo: Usar el término de proximidad personalizado</span><span class="sxs-lookup"><span data-stu-id="6b27f-148">Example: Using the Custom Proximity Term</span></span>  
 <span data-ttu-id="6b27f-149">En el siguiente ejemplo se buscan todos los resúmenes de documento que contienen el palabra "reflector" en el mismo documento que la palabra "bracket" en la tabla `Production.Document` de la base de datos de ejemplo `AdventureWorks2012` .</span><span class="sxs-lookup"><span data-stu-id="6b27f-149">The following example searches the `Production.Document` table of the `AdventureWorks2012` sample database for all document summaries that contain the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable   
INNER JOIN CONTAINSTABLE(Production.Document, Document,  
  'NEAR(bracket, reflector)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
WHERE KEY_TBL.RANK > 50  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  

  
##  <a name="additional-considerations-for-proximity-searches"></a><a name="Additional_Considerations"></a><span data-ttu-id="6b27f-150">Consideraciones adicionales para las búsquedas de proximidad</span><span class="sxs-lookup"><span data-stu-id="6b27f-150">Additional Considerations for Proximity Searches</span></span>  
 <span data-ttu-id="6b27f-151">En esta sección se describen las consideraciones que afectan tanto a las búsquedas de proximidad genéricas como a las personalizadas:</span><span class="sxs-lookup"><span data-stu-id="6b27f-151">This section discusses consideration that affect both generic and custom proximity searches:</span></span>  
  
-   <span data-ttu-id="6b27f-152">Apariciones superpuestas de términos de búsqueda</span><span class="sxs-lookup"><span data-stu-id="6b27f-152">Overlapping occurrences of search terms</span></span>  
  
     <span data-ttu-id="6b27f-153">Todas las búsquedas de proximidad siempre buscan únicamente apariciones no superpuestas.</span><span class="sxs-lookup"><span data-stu-id="6b27f-153">All proximity searches always look for only non-overlapping occurrences.</span></span> <span data-ttu-id="6b27f-154">Las apariciones superpuestas de términos de búsqueda nunca se consideran coincidencias.</span><span class="sxs-lookup"><span data-stu-id="6b27f-154">Overlapping occurrences of search terms never qualify as matches.</span></span> <span data-ttu-id="6b27f-155">Por ejemplo, considere el siguiente término de proximidad, que busca "`A`" y "`AA`" en este orden con una distancia máxima de dos términos:</span><span class="sxs-lookup"><span data-stu-id="6b27f-155">For example, consider the following proximity term, which searches "`A`" and "`AA`" in this order with a maximum distance of two terms:</span></span>  
  
    ```  
    CONTAINS(column_name, 'NEAR((A,AA),2, TRUE')  
    ```  
  
     <span data-ttu-id="6b27f-156">Las posibles coincidencias son "`AAA`", "`A.AA`" y "`A..AA`".</span><span class="sxs-lookup"><span data-stu-id="6b27f-156">The possible matches are as "`AAA`", "`A.AA`", and "`A..AA`".</span></span> <span data-ttu-id="6b27f-157">Las filas que simplemente contienen "`AA`" no coincidirían.</span><span class="sxs-lookup"><span data-stu-id="6b27f-157">Rows containing just "`AA`" would not match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6b27f-158">Puede especificar términos que se superponen, por ejemplo `NEAR("mountain bike", "bike trails")` o `(NEAR(comfort*, comfortable), 5)`.</span><span class="sxs-lookup"><span data-stu-id="6b27f-158">You can specify terms that overlap, for example, `NEAR("mountain bike", "bike trails")` or `(NEAR(comfort*, comfortable), 5)`.</span></span> <span data-ttu-id="6b27f-159">La especificación de un término superpuesto aumenta la complejidad de la consulta incrementando las posibles permutaciones de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="6b27f-159">Specifying a overlapping terms increases the complexity of the query by increasing the possible match permutations.</span></span> <span data-ttu-id="6b27f-160">Si especifica un número grande de términos superpuestos, la consulta puede quedarse sin recursos y producir un error.</span><span class="sxs-lookup"><span data-stu-id="6b27f-160">If you specify a large number of such overlapping terms, the query can run out of resources and fail.</span></span> <span data-ttu-id="6b27f-161">En tal caso, simplifique la consulta e inténtelo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="6b27f-161">If this occurs, simplify the query and try again.</span></span>  
  
-   <span data-ttu-id="6b27f-162">Tanto NEAR genérico como NEAR personalizado (independientemente de que se especifique una distancia máxima o no) indican la distancia lógica entre los términos, no la distancia absoluta entre ellos.</span><span class="sxs-lookup"><span data-stu-id="6b27f-162">Both generic NEAR and custom NEAR (regardless of whether a maximum distance is specified) indicate the logical distance between terms, rather than the absolute distance between them.</span></span> <span data-ttu-id="6b27f-163">Por ejemplo, los términos dentro de frases diferentes o las sentencias dentro de un párrafo se tratan como más alejados que los términos de la misma frase o sentencia, sin tener en cuenta su proximidad real, suponiéndose que están menos relacionados.</span><span class="sxs-lookup"><span data-stu-id="6b27f-163">For example, terms within different phrases or sentences within a paragraph are treated as farther apart than terms in the same phrase or sentence, regardless of their actual proximity, on the assumption that they are less related.</span></span> <span data-ttu-id="6b27f-164">Igualmente, los términos en párrafos diferentes se consideran todavía más alejados.</span><span class="sxs-lookup"><span data-stu-id="6b27f-164">Likewise, terms in different paragraphs are treated as being even farther apart.</span></span> <span data-ttu-id="6b27f-165">Si una coincidencia abarca el final de una frase, un párrafo o un capítulo, el intervalo utilizado para clasificar un documento aumenta en 8, 128 ó 1024, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6b27f-165">If a match spans the end of a sentence, paragraph, or chapter, the gap used for ranking a document is increased by 8, 128, or 1024, respectively.</span></span>  
  
-   <span data-ttu-id="6b27f-166">Impacto de los términos de proximidad en la clasificación por la función CONTAINSTABLE</span><span class="sxs-lookup"><span data-stu-id="6b27f-166">Impact of proximity terms on ranking by the CONTAINSTABLE function</span></span>  
  
     <span data-ttu-id="6b27f-167">Cuando se utiliza NEAR en la función CONTAINSTABLE, el número de aciertos en un documento con respecto a su longitud, así como la distancia entre el primero y el último término de búsqueda de cada uno de los aciertos, afecta a la clasificación de cada documento.</span><span class="sxs-lookup"><span data-stu-id="6b27f-167">When NEAR is used in the CONTAINSTABLE function, the number of hits in a document relative to its length as well as the distance between the first and last search terms in each of the hits affects the ranking of each document.</span></span> <span data-ttu-id="6b27f-168">En el caso de un término de proximidad genérico, si los términos de búsqueda con coincidencia están a >50 términos lógicos, el rango devuelto de un documento es 0.</span><span class="sxs-lookup"><span data-stu-id="6b27f-168">For a generic proximity term, if the matched search terms are >50 logical terms apart, the rank returned on a document is 0.</span></span> <span data-ttu-id="6b27f-169">Si se trata de un término de proximidad personalizado que no especifica un entero como la distancia máxima, un documento que solo contenga aciertos cuyo intervalo sea >100 términos lógicos recibirá una clasificación de 0.</span><span class="sxs-lookup"><span data-stu-id="6b27f-169">For a custom proximity term that does not specify an integer as the maximum distance, a document that contains only hits whose gap is >100 logical terms will receive a ranking of 0.</span></span> <span data-ttu-id="6b27f-170">Para obtener más información acerca de la clasificación de búsquedas de proximidad personalizadas, vea [Limit Search Results with RANK](limit-search-results-with-rank.md).</span><span class="sxs-lookup"><span data-stu-id="6b27f-170">For more information about ranking of custom proximity searches, see [Limit Search Results with RANK](limit-search-results-with-rank.md).</span></span>  
  
-   <span data-ttu-id="6b27f-171">La opción de servidor **transformar palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="6b27f-171">The **transform noise words** server option</span></span>  
  
     <span data-ttu-id="6b27f-172">El valor de **transformar palabras irrelevantes** afecta a cómo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trata las palabras irrelevantes si se especifican en búsquedas por proximidad.</span><span class="sxs-lookup"><span data-stu-id="6b27f-172">The value of **transform noise words** impacts how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] treats stopwords if they are specified in proximity searches.</span></span> <span data-ttu-id="6b27f-173">Para más información, vea [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="6b27f-173">For more information, see [transform noise words Server Configuration Option](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md).</span></span>  
  

  
##  <a name="the-deprecated-generic-proximity-term"></a><a name="Generic_NEAR"></a><span data-ttu-id="6b27f-174">El término de proximidad genérico desusado</span><span class="sxs-lookup"><span data-stu-id="6b27f-174">The Deprecated Generic Proximity Term</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]<span data-ttu-id="6b27f-175">Se recomienda usar el término de [proximidad personalizado](#Custom_NEAR).</span><span class="sxs-lookup"><span data-stu-id="6b27f-175">We recommend that you use the [custom proximity term](#Custom_NEAR).</span></span>  
  
 <span data-ttu-id="6b27f-176">Un término de proximidad genérico indica que todos los términos de búsqueda especificados deben estar en un documento para que se devuelva una coincidencia, independientemente del número de términos de no búsqueda (la *distancia*) que haya entre los términos de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6b27f-176">A generic proximity term indicates that the specified search terms must all occur in a document for a match to be returned, regardless of the number of non-search terms (the *distance*) between the search terms.</span></span> <span data-ttu-id="6b27f-177">La sintaxis básica es:</span><span class="sxs-lookup"><span data-stu-id="6b27f-177">The basic syntax is:</span></span>  
  
 <span data-ttu-id="6b27f-178">{ *search_term* {Near | ~} *search_term* } [ ,... *n* ]</span><span class="sxs-lookup"><span data-stu-id="6b27f-178">{ *search_term* { NEAR | ~ } *search_term* } [ ,...*n* ]</span></span>  
  
 <span data-ttu-id="6b27f-179">Por ejemplo, en los ejemplos siguientes deben aparecer las palabras 'fox' y 'chicken', en cualquier orden, para que se genere una coincidencia:</span><span class="sxs-lookup"><span data-stu-id="6b27f-179">For example, in the following examples, the words 'fox' and 'chicken' must both appear, in either order, to produce a match:</span></span>  
  
-   `CONTAINS(column_name, 'fox NEAR chicken')`  
  
-   `CONTAINSTABLE(table_name, column_name, 'fox ~ chicken')`  
  
> [!NOTE]  
>  <span data-ttu-id="6b27f-180">Para obtener información sobre la sintaxis de <término_proximidad_genérico>, vea [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6b27f-180">For information about the <generic_proximity_term> syntax, see [CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql).</span></span>  
  
 <span data-ttu-id="6b27f-181">Para obtener más información, vea "[Consideraciones adicionales sobre las búsquedas de proximidad](#Additional_Considerations)," más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="6b27f-181">For more information, see "[Additional Considerations about Proximity Searches](#Additional_Considerations)," later in this topic.</span></span>  
  
### <a name="combining-a-generic-proximity-term-with-other-terms"></a><span data-ttu-id="6b27f-182">Combinar un término de proximidad genérico con otros términos</span><span class="sxs-lookup"><span data-stu-id="6b27f-182">Combining a Generic Proximity Term with Other Terms</span></span>  
 <span data-ttu-id="6b27f-183">Puede usar AND (&), OR (|) o AND NOT (&!) para combinar un término de proximidad genérico con otro término de proximidad genérico, un término simple o un término de prefijo.</span><span class="sxs-lookup"><span data-stu-id="6b27f-183">You can use AND (&), OR (|), or AND NOT (&!) to combine a generic proximity term with another generic proximity term, a simple term, or a prefix term.</span></span> <span data-ttu-id="6b27f-184">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6b27f-184">For example:</span></span>  
  
```  
CONTAINSTABLE (Production.ProductDescription,  
   Description,   
   '(light NEAR aluminum) OR  
   (lightweight NEAR aluminum)'  
)  
```  
  
 <span data-ttu-id="6b27f-185">No se puede combinar un término de proximidad genérico con un término de proximidad personalizado, como `NEAR((term1,term2),5)` , un término ponderado (isabout...) o un término de generación (FORMSOF...).</span><span class="sxs-lookup"><span data-stu-id="6b27f-185">You cannot combine a generic proximity term with a custom proximity term, such as `NEAR((term1,term2),5)`, a weighted term (ISABOUT ...), or a generational term (FORMSOF ...).</span></span>  
  
### <a name="example-using-the-generic-proximity-term"></a><span data-ttu-id="6b27f-186">Ejemplo: Usar el término de proximidad genérico</span><span class="sxs-lookup"><span data-stu-id="6b27f-186">Example: Using the Generic Proximity Term</span></span>  
 <span data-ttu-id="6b27f-187">En el siguiente ejemplo se utiliza el término de proximidad genérico para buscar la palabra "reflector" en el mismo documento que la palabra "bracket".</span><span class="sxs-lookup"><span data-stu-id="6b27f-187">The following example uses the generic proximity term to search for the word "reflector" in the same document as the word "bracket".</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
  
SELECT DocumentNode, Title, DocumentSummary  
FROM Production.Document AS DocTable INNER JOIN  
  CONTAINSTABLE(Production.Document, Document,  
  '(reflector NEAR bracket)' ) AS KEY_TBL  
  ON DocTable.DocumentNode = KEY_TBL.[KEY]  
ORDER BY KEY_TBL.RANK DESC;  
GO  
```  
  
 <span data-ttu-id="6b27f-188">Tenga en cuenta que también puede invertir los términos de CONTAINSTABLE para obtener el mismo resultado:</span><span class="sxs-lookup"><span data-stu-id="6b27f-188">Notice that you can also reverse the terms in CONTAINSTABLE to get the same result:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(bracket NEAR reflector)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="6b27f-189">Puede utilizar el carácter de tilde (~) en el lugar de la palabra clave NEAR de la consulta anterior y obtener el mismo resultado:</span><span class="sxs-lookup"><span data-stu-id="6b27f-189">You can use the tilde character (~) in place of the NEAR keyword in the earlier query, and get the same results:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="6b27f-190">En las condiciones de búsqueda se pueden especificar más de dos palabras o frases.</span><span class="sxs-lookup"><span data-stu-id="6b27f-190">More than two words or phrases can be specified in the search conditions.</span></span> <span data-ttu-id="6b27f-191">Por ejemplo, es posible escribir:</span><span class="sxs-lookup"><span data-stu-id="6b27f-191">For example, it is possible to write:</span></span>  
  
```  
CONTAINSTABLE(Production.Document, Document, '(reflector ~ bracket ~ installation)' ) AS KEY_TBL  
```  
  
 <span data-ttu-id="6b27f-192">Esto significa que "reflector" debe estar en el mismo documento que "bracket" y "bracket" debe estar en el mismo documento que "installation".</span><span class="sxs-lookup"><span data-stu-id="6b27f-192">This means that "reflector" must be in the same document as "bracket", and "bracket" must be in the same document as "installation".</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="6b27f-193">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b27f-193">See Also</span></span>  
 <span data-ttu-id="6b27f-194">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6b27f-194">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="6b27f-195">[Consultar con búsqueda de texto completo](query-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="6b27f-195">[Query with Full-Text Search](query-with-full-text-search.md) </span></span>  
 [<span data-ttu-id="6b27f-196">CONTAINS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6b27f-196">CONTAINS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/contains-transact-sql)  
  
  
