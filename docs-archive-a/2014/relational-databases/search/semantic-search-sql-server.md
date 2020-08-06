---
title: Búsqueda semántica (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server]
- semantic search [SQL Server], overview
- statistical semantic search [SQL Server]
- statistical semantic search [SQL Server], overview
ms.assetid: cd8faa9d-07db-420d-93f4-a2ea7c974b97
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 91062864b77ba3c62a87d66b8ff93068f9c10c8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747548"
---
# <a name="semantic-search-sql-server"></a><span data-ttu-id="a449d-102">Búsqueda semántica (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a449d-102">Semantic Search (SQL Server)</span></span>
  <span data-ttu-id="a449d-103">La búsqueda semántica estadística proporciona una visión general amplia de los documentos no estructurados almacenados en las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante la extracción e indización de *frases clave*estadísticamente pertinentes.</span><span class="sxs-lookup"><span data-stu-id="a449d-103">Statistical Semantic Search provides deep insight into unstructured documents stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases by extracting and indexing statistically relevant *key phrases*.</span></span> <span data-ttu-id="a449d-104">Entonces también usa las frases clave para identificar e indizar *documentos que son similares o están relacionados*.</span><span class="sxs-lookup"><span data-stu-id="a449d-104">Then it also uses these key phrases to identify and index *documents that are similar or related*.</span></span>  
  
 <span data-ttu-id="a449d-105">Estos índices semánticos se consultan usando tres funciones de conjuntos de filas de Transact-SQL para recuperar los resultados como datos estructurados.</span><span class="sxs-lookup"><span data-stu-id="a449d-105">You query these semantic indexes by using three Transact-SQL rowset functions to retrieve the results as structured data.</span></span>  
  
##  <a name="what-can-i-do-with-semantic-search"></a><a name="whatcanido"></a><span data-ttu-id="a449d-106">¿Qué puedo hacer con la búsqueda semántica?</span><span class="sxs-lookup"><span data-stu-id="a449d-106">What Can I Do with Semantic Search?</span></span>  
 <span data-ttu-id="a449d-107">La búsqueda semántica se basa en la características de búsqueda de texto completo existente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], pero habilita nuevos escenarios que van más allá de las búsquedas sintácticas de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="a449d-107">Semantic search builds upon the existing full-text search feature in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but enables new scenarios that extend beyond keyword searches.</span></span> <span data-ttu-id="a449d-108">Mientras que la búsqueda de texto completo permite consultar las *palabras* de un documento, la búsqueda semántica permite consultar el *significado* del documento.</span><span class="sxs-lookup"><span data-stu-id="a449d-108">While full-text search lets you query the *words* in a document, semantic search lets you query the *meaning* of the document.</span></span> <span data-ttu-id="a449d-109">Las soluciones que ahora son posibles incluyen la extracción automática de etiquetas, la detección de contenido relacionado y la navegación jerárquica en contenido similar.</span><span class="sxs-lookup"><span data-stu-id="a449d-109">Solutions that are now possible include automatic tag extraction, related content discovery, and hierarchical navigation across similar content.</span></span> <span data-ttu-id="a449d-110">Por ejemplo, puede consultar el índice de frases clave para compilar la taxonomía de una organización o un corpus de documentos.</span><span class="sxs-lookup"><span data-stu-id="a449d-110">For example, you can query the index of key phrases to build the taxonomy for an organization, or for a corpus of documents.</span></span> <span data-ttu-id="a449d-111">O bien, puede consultar el índice de similitud de documentos para identificar currículos que coincidan con la descripción de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="a449d-111">Or, you can query the document similarity index to identify resumes that match a job description.</span></span>  
  
 <span data-ttu-id="a449d-112">En los ejemplos siguientes se demuestran las capacidades de la búsqueda semántica.</span><span class="sxs-lookup"><span data-stu-id="a449d-112">The following examples demonstrate the capabilities of Semantic Search.</span></span>  
  
###  <a name="find-the-key-phrases-in-a-document"></a><a name="find1"></a><span data-ttu-id="a449d-113">Buscar las frases clave de un documento</span><span class="sxs-lookup"><span data-stu-id="a449d-113">Find the Key Phrases in a Document</span></span>  
 <span data-ttu-id="a449d-114">La consulta siguiente obtiene las frases clave que se identificaron en el documento de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a449d-114">The following query gets the key phrases that were identified in the sample document.</span></span> <span data-ttu-id="a449d-115">Muestra los resultados en orden descendente por la puntuación que clasifica la importancia estadística de cada frase clave.</span><span class="sxs-lookup"><span data-stu-id="a449d-115">It presents the results in descending order by the score that ranks the statistical significance of each key phrase.</span></span> <span data-ttu-id="a449d-116">Esta consulta llama a la función [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a449d-116">This query calls the [semantickeyphrasetable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semantickeyphrasetable-transact-sql) function.</span></span>  
  
```sql  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS Title, keyphrase, score  
    FROM SEMANTICKEYPHRASETABLE(Documents, *, @DocID)  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-similar-or-related-documents"></a><a name="find2"></a><span data-ttu-id="a449d-117">Buscar documentos similares o relacionados</span><span class="sxs-lookup"><span data-stu-id="a449d-117">Find Similar or Related Documents</span></span>  
 <span data-ttu-id="a449d-118">La consulta siguiente obtiene los documentos que se identificaron como similares al documento de ejemplo o relacionados con este.</span><span class="sxs-lookup"><span data-stu-id="a449d-118">The following query gets the documents that were identified as similar or related to the sample document.</span></span> <span data-ttu-id="a449d-119">Muestra los resultados en orden descendente por la puntuación que clasifica la similitud de los 2 documentos.</span><span class="sxs-lookup"><span data-stu-id="a449d-119">It presents the results in descending order by the score that ranks the similarity of the 2 documents.</span></span> <span data-ttu-id="a449d-120">Esta consulta llama a la función [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a449d-120">This query calls the [semanticsimilaritytable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritytable-transact-sql) function.</span></span>  
  
```vb  
SET @Title = 'Sample Document.docx'  
  
SELECT @DocID = DocumentID  
    FROM Documents  
    WHERE DocumentTitle = @Title  
  
SELECT @Title AS SourceTitle, DocumentTitle AS MatchedTitle,  
        DocumentID, score  
    FROM SEMANTICSIMILARITYTABLE(Documents, *, @DocID)  
    INNER JOIN Documents ON DocumentID = matched_document_key  
    ORDER BY score DESC  
  
```  
  
  
  
###  <a name="find-the-key-phrases-that-make-documents-similar-or-related"></a><a name="find3"></a><span data-ttu-id="a449d-121">Buscar las frases clave que hacen que los documentos sean similares o relacionados</span><span class="sxs-lookup"><span data-stu-id="a449d-121">Find the Key Phrases That Make Documents Similar or Related</span></span>  
 <span data-ttu-id="a449d-122">La consulta siguiente obtiene las frases clave que hacen a los 2 documentos de ejemplo similares o relacionados entre sí.</span><span class="sxs-lookup"><span data-stu-id="a449d-122">The following query gets the key phrases that make the 2 sample documents similar or related to one another.</span></span> <span data-ttu-id="a449d-123">Muestra los resultados en orden descendente por la puntuación que clasifica el peso de cada frase clave.</span><span class="sxs-lookup"><span data-stu-id="a449d-123">It presents the results in descending order by the score that ranks the weight of each key phrase.</span></span> <span data-ttu-id="a449d-124">Esta consulta llama a la función [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a449d-124">This query calls the [semanticsimilaritydetailstable &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/semanticsimilaritydetailstable-transact-sql) function.</span></span>  
  
```sql  
SET @SourceTitle = 'first.docx'  
SET @MatchedTitle = 'second.docx'  
  
SELECT @SourceDocID = DocumentID FROM Documents WHERE DocumentTitle = @SourceTitle  
SELECT @MatchedDocID = DocumentID FROM Documents WHERE DocumentTitle = @MatchedTitle  
  
SELECT @SourceTitle AS SourceTitle, @MatchedTitle AS MatchedTitle, keyphrase, score  
    FROM semanticsimilaritydetailstable(Documents, DocumentContent,  
        @SourceDocID, DocumentContent, @MatchedDocID)  
    ORDER BY score DESC  
  
```  
  
  
  
##  <a name="storing-documents-in-sql-server"></a><a name="store"></a><span data-ttu-id="a449d-125">Almacenar documentos en SQL Server</span><span class="sxs-lookup"><span data-stu-id="a449d-125">Storing Documents in SQL Server</span></span>  
 <span data-ttu-id="a449d-126">Antes de poder indizar documentos con búsqueda semántica, tiene que almacenar los documentos en una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a449d-126">Before you can index documents with Semantic Search, you have to store the documents in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="a449d-127">La característica FileTable de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , convierte los archivos y documentos no estructurados en objetos de primera clase de la base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="a449d-127">The FileTable feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] makes unstructured files and documents first-class citizens of the relational database.</span></span> <span data-ttu-id="a449d-128">Como resultado, los desarrolladores de bases de datos pueden manipular documentos junto con datos estructurados en operaciones basadas en conjuntos de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="a449d-128">As a result, database developers can manipulate documents together with structured data in Transact-SQL set-based operations.</span></span>  
  
 <span data-ttu-id="a449d-129">Para obtener más información sobre la característica FileTables, vea [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a449d-129">For more information about the FileTable feature, see [FileTables &#40;SQL Server&#41;](../blob/filetables-sql-server.md).</span></span> <span data-ttu-id="a449d-130">Para obtener más información sobre la característica FILESTREAM, que es la opción para almacenar documentos en la base de datos, vea [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a449d-130">For information about the FILESTREAM feature, which is another option for storing documents in the database, see [FILESTREAM &#40;SQL Server&#41;](../blob/filestream-sql-server.md).</span></span>  
  
  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="a449d-131">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a449d-131">Related Tasks</span></span>  
 [<span data-ttu-id="a449d-132">Instalar y configurar la búsqueda semántica</span><span class="sxs-lookup"><span data-stu-id="a449d-132">Install and Configure Semantic Search</span></span>](install-and-configure-semantic-search.md)  
 <span data-ttu-id="a449d-133">Describe los requisitos previos de la búsqueda semántica estadística y cómo instalarlos o comprobarlos.</span><span class="sxs-lookup"><span data-stu-id="a449d-133">Describes the prerequisites for statistical semantic search and how to install or check them.</span></span>  
  
 [<span data-ttu-id="a449d-134">Habilitar la búsqueda semántica en tablas y columnas</span><span class="sxs-lookup"><span data-stu-id="a449d-134">Enable Semantic Search on Tables and Columns</span></span>](enable-semantic-search-on-tables-and-columns.md)  
 <span data-ttu-id="a449d-135">Describe cómo habilitar o deshabilitar la indización semántica estadística de las columnas seleccionadas que contienen documentos o texto.</span><span class="sxs-lookup"><span data-stu-id="a449d-135">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 [<span data-ttu-id="a449d-136">Buscar frases clave en documentos con la búsqueda semántica</span><span class="sxs-lookup"><span data-stu-id="a449d-136">Find Key Phrases in Documents with Semantic Search</span></span>](find-key-phrases-in-documents-with-semantic-search.md)  
 <span data-ttu-id="a449d-137">Describe cómo buscar las frases clave en documentos o columnas de texto configurados para la indización semántica estadística.</span><span class="sxs-lookup"><span data-stu-id="a449d-137">Describes how to find the key phrases in documents or text columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="a449d-138">Buscar documentos similares y relacionados con la búsqueda semántica</span><span class="sxs-lookup"><span data-stu-id="a449d-138">Find Similar and Related Documents with Semantic Search</span></span>](find-similar-and-related-documents-with-semantic-search.md)  
 <span data-ttu-id="a449d-139">Describe cómo buscar documentos o valores de texto similares e información acerca de su similitud o relación en columnas configuradas para la indización semántica estadística.</span><span class="sxs-lookup"><span data-stu-id="a449d-139">Describes how to find similar or related documents or text values, and information about how they are similar or related, in columns that are configured for statistical semantic indexing.</span></span>  
  
 [<span data-ttu-id="a449d-140">Administrar y supervisar la búsqueda semántica</span><span class="sxs-lookup"><span data-stu-id="a449d-140">Manage and Monitor Semantic Search</span></span>](manage-and-monitor-semantic-search.md)  
 <span data-ttu-id="a449d-141">Describe el proceso de indización semántica y las tareas relacionadas con la supervisión y la administración de índices.</span><span class="sxs-lookup"><span data-stu-id="a449d-141">Describes the process of semantic indexing and the tasks related to monitoring and managing the indexes.</span></span>  
  
##  <a name="related-content"></a><a name="relcontent"></a> <span data-ttu-id="a449d-142">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="a449d-142">Related Content</span></span>  
 [<span data-ttu-id="a449d-143">DDL de búsqueda semántica, funciones, procedimientos almacenados y vistas</span><span class="sxs-lookup"><span data-stu-id="a449d-143">Semantic Search DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
 <span data-ttu-id="a449d-144">Enumera las instrucciones Transact-SQL y los objetos de base de datos de SQL Server agregados o cambiados para admitir la búsqueda semántica estadística.</span><span class="sxs-lookup"><span data-stu-id="a449d-144">Lists the Transact-SQL statements and the SQL Server database objects added or changed to support statistical semantic search.</span></span>  
  
  
