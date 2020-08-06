---
title: Administración y supervisión de la búsqueda semántica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], managing
- semantic search [SQL Server], monitoring
ms.assetid: eb5c3b29-da70-42aa-aa97-7d35a3f1eb98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 16e3af1d37f177dfe6d4e0cb090e7b8b0a4988d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746839"
---
# <a name="manage-and-monitor-semantic-search"></a><span data-ttu-id="85c10-102">Administrar y supervisar la búsqueda semántica</span><span class="sxs-lookup"><span data-stu-id="85c10-102">Manage and Monitor Semantic Search</span></span>
  <span data-ttu-id="85c10-103">Describe el proceso de indización semántica y las tareas relacionadas con la administración y supervisión de los índices.</span><span class="sxs-lookup"><span data-stu-id="85c10-103">Describes the process of semantic indexing and the tasks related to managing and monitoring the indexes.</span></span>  
  
##  <a name="how-to-check-the-status-of-semantic-indexing"></a><a name="HowToMonitorStatus"></a><span data-ttu-id="85c10-104">Cómo: comprobar el estado de la indización semántica</span><span class="sxs-lookup"><span data-stu-id="85c10-104">How To: Check the Status of Semantic Indexing</span></span>  
 <span data-ttu-id="85c10-105">**¿Se ha completado la primera fase de la indización semántica?**</span><span class="sxs-lookup"><span data-stu-id="85c10-105">**Is the first phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="85c10-106">Consulte la vista de administración dinámica [sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) y compruebe las columnas **status** y **status_description**.</span><span class="sxs-lookup"><span data-stu-id="85c10-106">Query the dynamic management view, [sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql), and check the **status** and **status_description** columns.</span></span>  
  
 <span data-ttu-id="85c10-107">La primera fase de la indización incluye el rellenado del índice de palabras clave de texto completo y el índice semántico de frases clave, así como la extracción de datos de similitud de documentos.</span><span class="sxs-lookup"><span data-stu-id="85c10-107">The first phase of indexing includes the population of the full-text keyword index and the semantic key phrase index, as well as the extraction of document similarity data.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_index_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="85c10-108">**¿Se ha completado la segunda fase de la indización semántica?**</span><span class="sxs-lookup"><span data-stu-id="85c10-108">**Is the second phase of semantic indexing complete?**</span></span>  
 <span data-ttu-id="85c10-109">Consulte la vista de administración dinámica [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql) y compruebe las columnas **status** y **status_description**.</span><span class="sxs-lookup"><span data-stu-id="85c10-109">Query the dynamic management view, [sys.dm_fts_semantic_similarity_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-semantic-similarity-population-transact-sql), and check the **status** and **status_description** columns..</span></span>  
  
 <span data-ttu-id="85c10-110">La segunda fase de la indicación incluye el rellenado del índice semántico de similitud de documentos.</span><span class="sxs-lookup"><span data-stu-id="85c10-110">The second phase of indexing includes the population of the semantic document similarity index.</span></span>  
  
```wql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_fts_semantic_similarity_population WHERE table_id = OBJECT_ID('table_name')  
GO  
```  
  
##  <a name="how-to-check-the-size-of-the-semantic-indexes"></a><a name="HowToCheckSize"></a><span data-ttu-id="85c10-111">Cómo: comprobar el tamaño de los índices semánticos</span><span class="sxs-lookup"><span data-stu-id="85c10-111">How To: Check the Size of the Semantic Indexes</span></span>  
 <span data-ttu-id="85c10-112">**¿Cuál es el tamaño lógico de un índice semántico de frases clave o un índice semántico de similitud de documentos?**</span><span class="sxs-lookup"><span data-stu-id="85c10-112">**What is the logical size of a semantic key phrase index or a semantic document similarity index?**</span></span>  
 <span data-ttu-id="85c10-113">Consulte la vista de administración dinámica [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="85c10-113">Query the dynamic management view, [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql).</span></span>  
  
 <span data-ttu-id="85c10-114">El tamaño lógico se muestra en el número de páginas de índice.</span><span class="sxs-lookup"><span data-stu-id="85c10-114">The logical size is displayed in number of index pages.</span></span>  
  
```sql  
USE database_name  
GO  
  
SELECT * FROM sys.dm_db_fts_index_physical_stats WHERE object_id = OBJECT_ID('table_name')  
GO  
```  
  
 <span data-ttu-id="85c10-115">**¿Cuál es el tamaño total de los índices de texto completo y semántico de un catálogo de texto completo?**</span><span class="sxs-lookup"><span data-stu-id="85c10-115">**What is the total size of the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="85c10-116">Consulte la propiedad **IndexSize** de la función de metadatos [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="85c10-116">Query the **IndexSize** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'IndexSize')  
GO  
```  
  
 <span data-ttu-id="85c10-117">**¿Cuántos elementos se indizan en los índices de texto completo y semántico de un catálogo de texto completo?**</span><span class="sxs-lookup"><span data-stu-id="85c10-117">**How many items are indexed in the full-text and semantic indexes for a full-text catalog?**</span></span>  
 <span data-ttu-id="85c10-118">Consulte la propiedad **ItemCount** de la función de metadatos [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="85c10-118">Query the **ItemCount** property of the [FULLTEXTCATALOGPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/fulltextcatalogproperty-transact-sql) metadata function.</span></span>  
  
```sql  
SELECT FULLTEXTCATALOGPROPERTY('catalog_name', 'ItemCount')  
GO  
```  
  
##  <a name="how-to-force-the-population-of-the-semantic-indexes"></a><a name="HowToForcePopulation"></a><span data-ttu-id="85c10-119">Cómo: forzar el rellenado de los índices semánticos</span><span class="sxs-lookup"><span data-stu-id="85c10-119">How To: Force the Population of the Semantic Indexes</span></span>  
 <span data-ttu-id="85c10-120">Puede aplicar el rellenado de los índices de texto completo y de los índices semánticos usando las cláusulas START/STOP/PAUSE o RESUME POPULATION con la misma sintaxis y el mismo comportamiento descritos para los índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="85c10-120">You can force the population of full-text and semantic indexes by using the START/STOP/PAUSE or RESUME POPULATION clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="85c10-121">Para obtener más información, vea [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) y [Rellenar índices de texto completo](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="85c10-121">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql) and [Populate Full-Text Indexes](../indexes/indexes.md).</span></span>  
  
 <span data-ttu-id="85c10-122">Dado que la indización semántica depende de la indización de texto completo, los índices semánticos solo se rellenan cuando lo hacen los índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="85c10-122">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="85c10-123">**Ejemplo: iniciar el rellenado completo de los índices de texto completo y semántico**</span><span class="sxs-lookup"><span data-stu-id="85c10-123">**Example: Start a full population of full-text and semantic indexes**</span></span>  
  
 <span data-ttu-id="85c10-124">En el siguiente ejemplo se inicia el rellenado completo de los índices de texto completo y los índices semánticos modificando un índice de texto completo existente en la tabla **Production.Document** de la base de datos de ejemplo AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="85c10-124">The following example starts full population of both full-text and semantic indexes by altering an existing full-text index on the **Production.Document** table in the AdventureWorks2012 sample database.</span></span>  
  
```vb  
USE AdventureWorks2012  
GO  
  
ALTER FULLTEXT INDEX ON Production.Document  
    START FULL POPULATION  
GO  
```  
  
##  <a name="how-to-disable-or-re-enable-semantic-indexing"></a><a name="HowToDisableIndexing"></a><span data-ttu-id="85c10-125">Cómo: deshabilitar o volver a habilitar la indización semántica</span><span class="sxs-lookup"><span data-stu-id="85c10-125">How To: Disable or Re-enable Semantic Indexing</span></span>  
 <span data-ttu-id="85c10-126">Puede habilitar o deshabilitar la indización de texto completo o semántica usando la cláusula ENABLE/DISABLE con la misma sintaxis y el mismo comportamiento descritos para los índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="85c10-126">You can enable or disable full-text or semantic indexing by using the ENABLE/DISABLE clause with the same syntax and behavior that is described for full-text indexes.</span></span> <span data-ttu-id="85c10-127">Para obtener más información, vea [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="85c10-127">For more information, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="85c10-128">Cuando se deshabilita y se suspende la indización semántica, las consultas sobre datos semánticos siguen funcionando correctamente y devolviendo los datos indizados previamente.</span><span class="sxs-lookup"><span data-stu-id="85c10-128">When semantic indexing is disabled and suspended, queries over semantic data continue to work successfully and to return previously indexed data.</span></span> <span data-ttu-id="85c10-129">Este comportamiento no es coherente con el comportamiento de la búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="85c10-129">This behavior is not consistent with the behavior of Full-Text Search.</span></span>  
  
```sql  
-- To disable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name DISABLE  
GO  
  
-- To re-enable semantic indexing on a table  
USE database_name  
GO  
  
ALTER FULLTEXT INDEX ON table_name ENABLE  
GO  
```  
  
##  <a name="phases-of-semantic-indexing"></a><a name="SemanticIndexing"></a><span data-ttu-id="85c10-130">Fases de la indización semántica</span><span class="sxs-lookup"><span data-stu-id="85c10-130">Phases of Semantic Indexing</span></span>  
 <span data-ttu-id="85c10-131">La búsqueda semántica indiza dos tipos de datos para cada columna en la que esté habilitada:</span><span class="sxs-lookup"><span data-stu-id="85c10-131">Semantic Search indexes two kinds of data for each column on which it is enabled:</span></span>  
  
1.  <span data-ttu-id="85c10-132">**Frases clave**</span><span class="sxs-lookup"><span data-stu-id="85c10-132">**Key phrases**</span></span>  
  
2.  <span data-ttu-id="85c10-133">**Similitud de documentos**</span><span class="sxs-lookup"><span data-stu-id="85c10-133">**Document similarity**</span></span>  
  
 <span data-ttu-id="85c10-134">La indización semántica se produce en dos fases, junto con la indización de texto completo:</span><span class="sxs-lookup"><span data-stu-id="85c10-134">Semantic indexing occurs in two phases, in conjunction with full-text indexing:</span></span>  
  
1.  <span data-ttu-id="85c10-135">**Fase 1**.</span><span class="sxs-lookup"><span data-stu-id="85c10-135">**Phase 1**.</span></span> <span data-ttu-id="85c10-136">El índice de palabras clave de texto completo y el índice semántico de frases clave se rellenan en paralelo a la vez.</span><span class="sxs-lookup"><span data-stu-id="85c10-136">The full-text keyword index and the semantic key phrase index are populated in parallel at the same time.</span></span> <span data-ttu-id="85c10-137">Los datos necesarios para indizar la similitud de documentos también se extrae en este momento.</span><span class="sxs-lookup"><span data-stu-id="85c10-137">The data required to index document similarity is also extracted at this time.</span></span>  
  
2.  <span data-ttu-id="85c10-138">**Fase 2**.</span><span class="sxs-lookup"><span data-stu-id="85c10-138">**Phase 2**.</span></span> <span data-ttu-id="85c10-139">Después se rellena el índice semántico de similitud de documentos.</span><span class="sxs-lookup"><span data-stu-id="85c10-139">The semantic document similarity index is then populated.</span></span> <span data-ttu-id="85c10-140">Este índice depende de los dos índices que se rellenaron en la fase anterior.</span><span class="sxs-lookup"><span data-stu-id="85c10-140">This index depends on both indexes that were populated in the preceding phase.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-semantic-indexes-are-not-populated"></a><a name="ProblemNotPopulated"></a><span data-ttu-id="85c10-141">Problema: los índices semánticos no se rellenan</span><span class="sxs-lookup"><span data-stu-id="85c10-141">Problem: Semantic Indexes Are Not Populated</span></span>  
 <span data-ttu-id="85c10-142">**¿Se rellenan los índices de texto completo asociados?**</span><span class="sxs-lookup"><span data-stu-id="85c10-142">**Are the associated full-text indexes populated?**</span></span>  
 <span data-ttu-id="85c10-143">Dado que la indización semántica depende de la indización de texto completo, los índices semánticos solo se rellenan cuando lo hacen los índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="85c10-143">Since semantic indexing is dependent on full-text indexing, semantic indexes are only populated when the associated full-text indexes are populated.</span></span>  
  
 <span data-ttu-id="85c10-144">**¿La búsqueda de texto completo y la búsqueda semántica están instaladas y configuradas correctamente?**</span><span class="sxs-lookup"><span data-stu-id="85c10-144">**Are full-text search and semantic search properly installed and configured?**</span></span>  
 <span data-ttu-id="85c10-145">Para obtener más información, vea [Instalar y configurar la búsqueda semántica](install-and-configure-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="85c10-145">For more information, see [Install and Configure Semantic Search](install-and-configure-semantic-search.md).</span></span>  
  
 <span data-ttu-id="85c10-146">**¿El servicio FDHOST no está disponible o existe otra condición que provocaría un error de indización de texto completo?**</span><span class="sxs-lookup"><span data-stu-id="85c10-146">**Is the FDHOST service not available, or is there another condition that would cause full-text indexing to fail?**</span></span>  
 <span data-ttu-id="85c10-147">Para obtener más información, vea [Solucionar problemas de indexación de texto completo](troubleshoot-full-text-indexing.md).</span><span class="sxs-lookup"><span data-stu-id="85c10-147">For more information, see [Troubleshoot Full-Text Indexing](troubleshoot-full-text-indexing.md).</span></span>  
  
  
