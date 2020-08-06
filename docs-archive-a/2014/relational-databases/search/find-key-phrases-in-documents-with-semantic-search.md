---
title: Buscar frases clave en documentos con la búsqueda semántica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], key phrase queries
ms.assetid: 6ee3676e-ed5d-43ec-aeca-1eed78967111
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8388fb704bf13f44d025e6e32a1450d537f61832
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745183"
---
# <a name="find-key-phrases-in-documents-with-semantic-search"></a><span data-ttu-id="5156b-102">Buscar frases clave en documentos con la búsqueda semántica</span><span class="sxs-lookup"><span data-stu-id="5156b-102">Find Key Phrases in Documents with Semantic Search</span></span>
  <span data-ttu-id="5156b-103">Describe cómo buscar las frases clave en documentos o columnas de texto configurados para la indización semántica estadística.</span><span class="sxs-lookup"><span data-stu-id="5156b-103">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
##  <a name="finding-key-phrases-in-documents"></a><a name="BasicsQueryKey"></a><span data-ttu-id="5156b-104">Buscar frases clave en documentos</span><span class="sxs-lookup"><span data-stu-id="5156b-104">Finding Key Phrases in Documents</span></span>  
  
###  <a name="how-to-find-the-key-phrases-in-documents-with-semantickeyphrasetable"></a><a name="howtofind"></a><span data-ttu-id="5156b-105">Cómo: buscar frases clave en documentos con SEMANTICKEYPHRASETABLE</span><span class="sxs-lookup"><span data-stu-id="5156b-105">How to: Find the Key Phrases in Documents with SEMANTICKEYPHRASETABLE</span></span>  
 <span data-ttu-id="5156b-106">Para identificar las frases clave de documentos específicos o para identificar documentos que contengan frases clave específicas, consulte la función [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5156b-106">To identify the key phrases in specific documents, or to identify documents that contain specific key phrases, query the function [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
 <span data-ttu-id="5156b-107">SEMANTICKEYPHRASETABLE devuelve una tabla con cero, una o más filas para las frases clave asociadas con las columnas de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="5156b-107">SEMANTICKEYPHRASETABLE returns a table with zero, one, or more rows for those key phrases associated with columns in the specified table.</span></span> <span data-ttu-id="5156b-108">Se puede hacer referencia a esta función de conjunto de filas en la cláusula FROM de una instrucción SELECT como si fuese un nombre de tabla normal.</span><span class="sxs-lookup"><span data-stu-id="5156b-108">This rowset function can be referenced in the FROM clause of a SELECT statement as if it were a regular table name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5156b-109">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], solo las palabras individuales se indizan para la búsqueda semánticas; las frases de múltiples palabras (ngrams) no se indizan.</span><span class="sxs-lookup"><span data-stu-id="5156b-109">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], only single words are indexed for semantic search; multi-word phrases (ngrams) are not indexed.</span></span> <span data-ttu-id="5156b-110">Además, las distintas formas de la misma palabra se indizan por separado; por ejemplo, "equipo" y "equipos" se indizan por independientemente.</span><span class="sxs-lookup"><span data-stu-id="5156b-110">Also, various forms of the same word are indexed separately; for example, "computer" and "computers" are indexed separately.</span></span>  
  
 <span data-ttu-id="5156b-111">Para obtener información detallada sobre los parámetros requeridos por la función SEMANTICKEYPHRASETABLE y sobre la tabla de resultados que devuelve, vea [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5156b-111">For detailed information about the parameters required by the SEMANTICKEYPHRASETABLE function, and about the table of results that it returns, see [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5156b-112">Las columnas de destino deben tener habilitada la indización de texto completo y semántica.</span><span class="sxs-lookup"><span data-stu-id="5156b-112">The columns that you target must have full-text and semantic indexing enabled.</span></span>  
  
###  <a name="example-1-find-the-top-key-phrases-in-a-specific-document"></a><a name="HowToTopPhrases"></a><span data-ttu-id="5156b-113">Ejemplo 1: buscar las frases clave principales de un documento específico</span><span class="sxs-lookup"><span data-stu-id="5156b-113">Example 1: Find the Top Key Phrases in a Specific Document</span></span>  
 <span data-ttu-id="5156b-114">En el ejemplo siguiente se recuperan las 10 frases clave principales del documento especificado por la variable @DocumentId en la columna Document de la tabla Production.Document de la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="5156b-114">The following example retrieves the top 10 key phrases from the document specified by the @DocumentId variable in the Document column of the Production.Document table of the AdventureWorks sample database.</span></span> <span data-ttu-id="5156b-115">La variable @DocumentId representa un valor de la columna de clave del índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="5156b-115">The @DocumentId variable represents a value from the key column of the full-text index.</span></span>  
  
```sql  
SELECT TOP(10) KEYP_TBL.keyphrase  
FROM SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document,  
    @DocumentId  
    ) AS KEYP_TBL  
ORDER BY KEYP_TBL.score DESC;  
GO  
```  
  
 <span data-ttu-id="5156b-116">La función **SEMANTICKEYPHRASETABLE** recupera estos resultados eficazmente mediante una búsqueda de índice en vez de un recorrido de tabla.</span><span class="sxs-lookup"><span data-stu-id="5156b-116">The **SEMANTICKEYPHRASETABLE** function retrieves these results efficiently by using an index seek instead of a table scan.</span></span>  
  
###  <a name="example-2-find-the-top-documents-that-contain-a-specific-key-phrase"></a><a name="HowToTopDocuments"></a><span data-ttu-id="5156b-117">Ejemplo 2: buscar los documentos principales que contienen una frase clave específica</span><span class="sxs-lookup"><span data-stu-id="5156b-117">Example 2: Find the Top Documents that Contain a Specific Key Phrase</span></span>  
 <span data-ttu-id="5156b-118">En el ejemplo siguiente se recuperan los 25 primeros documentos que contengan la palabra clave "Bracket" de la columna Document de la tabla Production.Document de la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="5156b-118">The following example retrieves the top 25 documents that contain the key phrase "Bracket" from the Document column of the Production.Document table of the AdventureWorks sample database.</span></span>  
  
```sql  
SELECT TOP (25) DOC_TBL.DocumentID, DOC_TBL.DocumentSummary  
FROM Production.Document AS DOC_TBL  
    INNER JOIN SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document  
    ) AS KEYP_TBL  
ON DOC_TBL.DocumentID = KEYP_TBL.document_key  
WHERE KEYP_TBL.keyphrase = 'Bracket'  
ORDER BY KEYP_TBL.Score DESC;  
GO  
```  
  
  
