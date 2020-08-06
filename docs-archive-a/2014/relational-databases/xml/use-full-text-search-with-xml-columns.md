---
title: Usar la búsqueda de texto completo con columnas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml columns [full-text search]
- indexes [full-text search]
ms.assetid: 8096cfc6-1836-4ed5-a769-a5d63b137171
author: rothja
ms.author: jroth
ms.openlocfilehash: 2b6b23933fde6a09d043c7055b0daa7c07035cdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745071"
---
# <a name="use-full-text-search-with-xml-columns"></a><span data-ttu-id="889c2-102">Usar la búsqueda de texto completo con columnas XML</span><span class="sxs-lookup"><span data-stu-id="889c2-102">Use Full-Text Search with XML Columns</span></span>
  <span data-ttu-id="889c2-103">Puede crear un índice de texto completo en columnas XML para indizar el contenido de los valores XML, pero omitiendo el marcado XML.</span><span class="sxs-lookup"><span data-stu-id="889c2-103">You can create a full-text index on XML columns that indexes the content of the XML values, but ignores the XML markup.</span></span> <span data-ttu-id="889c2-104">Las etiquetas de elemento se usan como límites de token.</span><span class="sxs-lookup"><span data-stu-id="889c2-104">Element tags are used as token boundaries.</span></span> <span data-ttu-id="889c2-105">Los siguientes elementos se indizan:</span><span class="sxs-lookup"><span data-stu-id="889c2-105">The following items are indexed:</span></span>  
  
-   <span data-ttu-id="889c2-106">Contenido de los elementos XML.</span><span class="sxs-lookup"><span data-stu-id="889c2-106">The content of XML elements.</span></span>  
  
-   <span data-ttu-id="889c2-107">Contenido de los atributos XML del elemento de nivel superior únicamente, a menos que esos valores sean numéricos.</span><span class="sxs-lookup"><span data-stu-id="889c2-107">The content of XML attributes of the top-level element only, unless those values are numeric values.</span></span>  
  
 <span data-ttu-id="889c2-108">Si es posible, puede combinar una búsqueda de texto completo con un índice XML como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="889c2-108">When possible, you can combine full-text search with XML index in the following way:</span></span>  
  
1.  <span data-ttu-id="889c2-109">En primer lugar, filtre los valores XML que resulten de interés mediante una búsqueda de texto completo SQL.</span><span class="sxs-lookup"><span data-stu-id="889c2-109">First, filter the XML values of interest by using SQL full-text search.</span></span>  
  
2.  <span data-ttu-id="889c2-110">A continuación, realice una consulta en los valores XML que usen índice XML en la columna XML.</span><span class="sxs-lookup"><span data-stu-id="889c2-110">Next, query those XML values that use XML index on the XML column.</span></span>  
  
## <a name="example-combining-full-text-search-with-xml-querying"></a><span data-ttu-id="889c2-111">Ejemplo: Combinación de una búsqueda de texto completo con consultas XML</span><span class="sxs-lookup"><span data-stu-id="889c2-111">Example: Combining Full-text Search with XML Querying</span></span>  
 <span data-ttu-id="889c2-112">Una vez creado un índice de texto completo en la columna XML, la siguiente consulta comprueba que un valor XML contiene la palabra "custom" en el título de un libro:</span><span class="sxs-lookup"><span data-stu-id="889c2-112">After the full-text index has been created on the XML column, the following query checks that an XML value contains the word "custom" in the title of a book:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'custom')   
AND    xCol.exist('/book/title/text()[contains(.,"custom")]') =1  
```  
  
 <span data-ttu-id="889c2-113">El método **contains()** usa el índice de texto completo para crear un subconjunto con los valores XML que contienen la palabra "custom" en algún lugar del documento.</span><span class="sxs-lookup"><span data-stu-id="889c2-113">The **contains()** method uses the full-text index to subset the XML values that contain the word "custom" anywhere in the document.</span></span> <span data-ttu-id="889c2-114">La cláusula **exist()** se asegura de que la palabra "custom" aparezca en el título de un libro.</span><span class="sxs-lookup"><span data-stu-id="889c2-114">The **exist()** clause ensures that the word "custom" occurs in the title of a book.</span></span>  
  
 <span data-ttu-id="889c2-115">Una búsqueda de texto completo que usa **contains()** y la función **contains()** de XQuery tiene semánticas distintas.</span><span class="sxs-lookup"><span data-stu-id="889c2-115">A full-text search that uses **contains()** and XQuery **contains()** has different semantics.</span></span> <span data-ttu-id="889c2-116">La última busca una coincidencia de subcadena y la primera busca una coincidencia de token que utilice lematización.</span><span class="sxs-lookup"><span data-stu-id="889c2-116">The latter is a substring match and the former is a token match that uses stemming.</span></span> <span data-ttu-id="889c2-117">Es decir, si se busca la cadena que contiene "run" en el título, las coincidencias incluirán "run", "runs" y "running", puesto que se cumplen los criterios tanto de **contains()** de texto completo como los de la función **contains()** de XQuery.</span><span class="sxs-lookup"><span data-stu-id="889c2-117">Therefore, if the search is for the string that has "run" in the title, the matches will include "run", "runs", and "running", because both the full-text **contains()** and the Xquery **contains()** are satisfied.</span></span> <span data-ttu-id="889c2-118">Pero la consulta no coincide con la palabra "customizable" del título, ya que la función **contains()** para la búsqueda de texto completo genera un error, pero la función **contains()** de Xquery sí se cumple.</span><span class="sxs-lookup"><span data-stu-id="889c2-118">However, the query does not match the word "customizable" in the title in that the full-text **contains()** fails, but the Xquery **contains()** is satisfied.</span></span> <span data-ttu-id="889c2-119">Por lo general, para una coincidencia de subcadena pura, debe quitarse la cláusula **contains()** de la búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="889c2-119">Generally, for pure substring match, the full-text **contains()** clause should be removed.</span></span>  
  
 <span data-ttu-id="889c2-120">Además, la búsqueda de texto completo usa lematización de palabras, pero la función **contains()** de XQuery busca una coincidencia literal.</span><span class="sxs-lookup"><span data-stu-id="889c2-120">Additionally, full-text search uses word stemming, but XQuery **contains()** is a literal match.</span></span> <span data-ttu-id="889c2-121">Esta diferencia se describe en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="889c2-121">This difference is illustrated in the next example.</span></span>  
  
## <a name="example-full-text-search-on-xml-values-using-stemming"></a><span data-ttu-id="889c2-122">Ejemplo: Búsqueda de texto completo en valores XML mediante lematización</span><span class="sxs-lookup"><span data-stu-id="889c2-122">Example: Full-text Search on XML Values Using Stemming</span></span>  
 <span data-ttu-id="889c2-123">Por lo general, la comprobación de la función **contains()** de XQuery que se ha efectuado en el ejemplo anterior no se puede eliminar.</span><span class="sxs-lookup"><span data-stu-id="889c2-123">The XQuery **contains()** check that was performed in the previous example generally cannot be eliminated.</span></span> <span data-ttu-id="889c2-124">Considere esta consulta:</span><span class="sxs-lookup"><span data-stu-id="889c2-124">Consider this query:</span></span>  
  
```  
SELECT *   
FROM   T   
WHERE  CONTAINS(xCol,'run')   
```  
  
 <span data-ttu-id="889c2-125">La palabra "ran" en el documento cumple la condición de búsqueda debido a la lematización.</span><span class="sxs-lookup"><span data-stu-id="889c2-125">The word "ran" in the document matches the search condition because of stemming.</span></span> <span data-ttu-id="889c2-126">Además, el contexto de búsqueda no se comprueba mediante XQuery.</span><span class="sxs-lookup"><span data-stu-id="889c2-126">Additionally, the search context is not checked by using XQuery.</span></span>  
  
 <span data-ttu-id="889c2-127">Cuando el XML se descompone en columnas relacionales utilizando AXSD y las columnas se incluyen en el índice de texto completo, las consultas XPath que se ejecutan en la vista XML no efectúan búsquedas de texto completo en las tablas subyacentes.</span><span class="sxs-lookup"><span data-stu-id="889c2-127">When XML is decomposed into relational columns by using AXSD that are full-text indexed, XPath queries that occur over the XML view do not perform full-text search on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="889c2-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="889c2-128">See Also</span></span>  
 [<span data-ttu-id="889c2-129">Índices XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="889c2-129">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
