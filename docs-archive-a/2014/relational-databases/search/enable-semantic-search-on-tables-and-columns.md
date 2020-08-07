---
title: Habilitar la búsqueda semántica en tablas y columnas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], enabling
ms.assetid: 895d220c-6749-4954-9dd3-2ea4c6a321ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f11ba654f7cc34f521990e8c420d41885d3c55b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746864"
---
# <a name="enable-semantic-search-on-tables-and-columns"></a><span data-ttu-id="dfb38-102">Habilitar la búsqueda semántica en tablas y columnas</span><span class="sxs-lookup"><span data-stu-id="dfb38-102">Enable Semantic Search on Tables and Columns</span></span>
  <span data-ttu-id="dfb38-103">Describe cómo habilitar o deshabilitar la indización semántica estadística de las columnas seleccionadas que contienen documentos o texto.</span><span class="sxs-lookup"><span data-stu-id="dfb38-103">Describes how to enable or disable statistical semantic indexing on selected columns that contain documents or text.</span></span>  
  
 <span data-ttu-id="dfb38-104">La búsqueda semántica estadística usa los datos que indiza la búsqueda de texto completo y crea índices adicionales.</span><span class="sxs-lookup"><span data-stu-id="dfb38-104">Statistical Semantic Search uses the indexes that are created by Full-Text Search, and creates additional indexes.</span></span> <span data-ttu-id="dfb38-105">Como resultado de esta dependencia en la búsqueda de texto completo, se crea un nuevo índice semántico al definir un nuevo índice de texto completo o al modificar un índice de texto completo existente.</span><span class="sxs-lookup"><span data-stu-id="dfb38-105">As a result of this dependency on full-text search, you create a new semantic index when you define a new full-text index, or when you alter an existing full-text index.</span></span> <span data-ttu-id="dfb38-106">Puede crear un nuevo índice semántico mediante instrucciones de [!INCLUDE[tsql](../../includes/tsql-md.md)] o mediante el Asistente para indización de texto completo y otros cuadros de diálogo de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], como se describe en este tema.</span><span class="sxs-lookup"><span data-stu-id="dfb38-106">You can create a new semantic index by using [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or by using the Full-Text Indexing Wizard and other dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], as described in this topic.</span></span>  
  
##  <a name="creating-a-semantic-index"></a><a name="BasicEnabling"></a><span data-ttu-id="dfb38-107">Crear un índice semántico</span><span class="sxs-lookup"><span data-stu-id="dfb38-107">Creating a Semantic Index</span></span>  
  
###  <a name="requirements-and-restrictions-for-creating-a-semantic-index"></a><a name="reqenable"></a><span data-ttu-id="dfb38-108">Requisitos y restricciones para crear un índice semántico</span><span class="sxs-lookup"><span data-stu-id="dfb38-108">Requirements and Restrictions for Creating a Semantic Index</span></span>  
  
-   <span data-ttu-id="dfb38-109">Puede crear un índice en cualquiera de los objetos de base de datos admitidos para la indización de texto completo, incluidas las tablas y las vistas indizadas.</span><span class="sxs-lookup"><span data-stu-id="dfb38-109">You can create an index on any of the database objects that are supported for full-text indexing, including tables and indexed views.</span></span>  
  
-   <span data-ttu-id="dfb38-110">Para poder habilitar la indización semántica de columnas específicas, deben existir los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="dfb38-110">Before you can enable semantic indexing for specific columns, the following prerequisites must exist:</span></span>  
  
    -   <span data-ttu-id="dfb38-111">Establece el catálogo de texto completo predeterminado para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dfb38-111">A full-text catalog must exist for the database.</span></span>  
  
    -   <span data-ttu-id="dfb38-112">La tabla debe tener un índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-112">The table must have a full-text index.</span></span>  
  
    -   <span data-ttu-id="dfb38-113">Las columnas seleccionadas deben participar en el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-113">The selected columns must participate in the full-text index.</span></span>  
  
     <span data-ttu-id="dfb38-114">Puede crear y habilitar todas estos requisitos a la vez.</span><span class="sxs-lookup"><span data-stu-id="dfb38-114">You can create and enable all these requirements at the same time.</span></span>  
  
-   <span data-ttu-id="dfb38-115">Puede crear un índice en columnas que contenga cualquiera de los tipos de datos admitidos para la indización de texto completo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-115">You can create a semantic index on columns that have any of the data types that are supported for full-text indexing.</span></span> <span data-ttu-id="dfb38-116">Para obtener más información, vea [Crear y administrar índices de texto completo](create-and-manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="dfb38-116">For more information, see [Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md).</span></span>  
  
-   <span data-ttu-id="dfb38-117">Puede especificar cualquier tipo de documento admitido para la indización de texto completo para las columnas `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="dfb38-117">You can specify any document type that is supported for full-text indexing for `varbinary(max)` columns.</span></span> <span data-ttu-id="dfb38-118">Para obtener más información, vea [Cómo: determinar qué tipos de documento se pueden indizar](#doctypes) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="dfb38-118">For more information, see [How To: Determine Which Document Types Can Be Indexed](#doctypes) in this topic.</span></span>  
  
-   <span data-ttu-id="dfb38-119">La indexación semántica crea dos tipos de índices para las columnas que seleccione: un índice de frases clave y un índice de similitud de documentos.</span><span class="sxs-lookup"><span data-stu-id="dfb38-119">Semantic indexing creates two types of indexes for the columns that you select - an index of key phrases, and an index of document similarity.</span></span> <span data-ttu-id="dfb38-120">No puede seleccionar solo uno de los tipos de índice o el otro cuando habilite la indización semántica.</span><span class="sxs-lookup"><span data-stu-id="dfb38-120">You cannot select only one type of index or the other when you enable semantic indexing.</span></span> <span data-ttu-id="dfb38-121">Sin embargo, puede consultar estos dos índices por separado.</span><span class="sxs-lookup"><span data-stu-id="dfb38-121">However you can query these two indexes independently.</span></span> <span data-ttu-id="dfb38-122">Para obtener más información, vea [Buscar frases clave en documentos con la búsqueda semántica](find-key-phrases-in-documents-with-semantic-search.md) y [Buscar documentos similares y relacionados con la búsqueda semántica](find-similar-and-related-documents-with-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="dfb38-122">For more information, see [Find Key Phrases in Documents with Semantic Search](find-key-phrases-in-documents-with-semantic-search.md) and [Find Similar and Related Documents with Semantic Search](find-similar-and-related-documents-with-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="dfb38-123">Si no especifica explícitamente ningún LCID para un índice semántico, solo se usan las estadísticas del idioma principal y de su idioma asociado para la indización semántica.</span><span class="sxs-lookup"><span data-stu-id="dfb38-123">If you do not explicitly specify an LCID for a semantic index, then only the primary language and its associated language statistics are used for semantic indexing.</span></span>  
  
-   <span data-ttu-id="dfb38-124">Si especifica un idioma para una columna para la que no está disponible el idioma, se produce un error de creación del índice y se devuelve un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="dfb38-124">If you specify a language for a column for which the language model is not available, the creation of the index fails and returns an error message.</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-no-full-text-index"></a><a name="HowToEnableCreate"></a><span data-ttu-id="dfb38-125">Cómo: crear un índice semántico cuando no hay ningún índice de texto completo</span><span class="sxs-lookup"><span data-stu-id="dfb38-125">How To: Create a Semantic Index When There Is No Full-Text Index</span></span>  
 <span data-ttu-id="dfb38-126">Cuando cree un nuevo índice de texto completo con la instrucción **CREATE FULLTEXT INDEX** , puede habilitar la indexación semántica en el nivel de columna especificando la palabra clave **STATISTICAL_SEMANTICS** como parte de la definición de columna.</span><span class="sxs-lookup"><span data-stu-id="dfb38-126">When you create a new full-text index with the **CREATE FULLTEXT INDEX** statement, you can enable semantic indexing at the column level by specifying the keyword **STATISTICAL_SEMANTICS** as part of the column definition.</span></span> <span data-ttu-id="dfb38-127">Asimismo, puede habilitar la indización semántica cuando use el Asistente para indización de texto completo con el fin de crear un nuevo índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-127">You can also enable semantic indexing when you use the Full-Text Indexing Wizard to create a new full-text index.</span></span>  
  
 <span data-ttu-id="dfb38-128">**Crear un nuevo índice semántico con Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="dfb38-128">**Create a new semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="dfb38-129">Llame a la instrucción **CREATE FULLTEXT INDEX** y especifique **STATISTICAL_SEMANTICS** para cada columna en la que quiera crear un índice semántico.</span><span class="sxs-lookup"><span data-stu-id="dfb38-129">Call the **CREATE FULLTEXT INDEX** statement and specify **STATISTICAL_SEMANTICS** for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="dfb38-130">Para obtener más información sobre todas las opciones de esta instrucción, vea [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfb38-130">For more information about all the options for this statement, see [CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="dfb38-131">**Ejemplo 1: crear un índice único, un índice de texto completo y un índice semántico**</span><span class="sxs-lookup"><span data-stu-id="dfb38-131">**Example 1: Create a unique index, full-text index, and semantic index**</span></span>  
  
 <span data-ttu-id="dfb38-132">En el ejemplo siguiente, se crea un catálogo de texto completo predeterminado, **ft**. Después, se crea un índice único en la columna **JobCandidateID** de la tabla **HumanResources.JobCandidate** de la base de datos de ejemplo AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="dfb38-132">The following example creates a default full-text catalog, **ft**. The example then creates a unique index on the **JobCandidateID** column of the **HumanResources.JobCandidate** table of the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="dfb38-133">Este índice único se requiere como columna de clave de un índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-133">This unique index is required as the key column for a full-text index.</span></span> <span data-ttu-id="dfb38-134">Después, en el ejemplo se crea un índice de texto completo y un índice semántico en la columna **Resume** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-134">The example then creates a full-text index and a semantic index on the **Resume** column.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG ft AS DEFAULT  
GO  
  
CREATE UNIQUE INDEX ui_ukJobCand  
    ON HumanResources.JobCandidate(JobCandidateID)  
GO  
  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate  
    (Resume  
        Language 1033  
        Statistical_Semantics  
    )   
    KEY INDEX JobCandidateID   
    WITH STOPLIST = SYSTEM  
GO  
```  
  
 <span data-ttu-id="dfb38-135">**Ejemplo 2: Crear un índice de texto completo y semántico en varias columnas con rellenado de índice retrasado**</span><span class="sxs-lookup"><span data-stu-id="dfb38-135">**Example 2: Create a full-text and semantic index on several columns with delayed index population**</span></span>  
  
 <span data-ttu-id="dfb38-136">En el ejemplo siguiente se crea un catálogo de texto completo, **documents_catalog**, en la base de datos de ejemplo AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="dfb38-136">The following example creates a full-text catalog, **documents_catalog**, in the AdventureWorks2012 sample database.</span></span> <span data-ttu-id="dfb38-137">A continuación, se crea un índice de texto completo que usa este nuevo catálogo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-137">The example then creates a full-text index that uses this new catalog.</span></span> <span data-ttu-id="dfb38-138">El índice de texto completo se crea en las columnas **Title**, **DocumentSummary**y **Document** de la tabla **Production.Document** , mientras que el índice semántico se crea únicamente en la columna **Document** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-138">The full-text index is created on the **Title**, **DocumentSummary**, and **Document** columns of the **Production.Document** table, while the semantic index is only created on the **Document** column.</span></span> <span data-ttu-id="dfb38-139">Este índice de texto completo usa el catálogo de texto completo recién creado y un índice de clave única existente, **PK_Document_DocumentID**.</span><span class="sxs-lookup"><span data-stu-id="dfb38-139">This full-text index uses the newly-created full-text catalog and an existing unique key index, **PK_Document_DocumentID**.</span></span> <span data-ttu-id="dfb38-140">Tal como se recomienda, esta clave de índice se crea en una columna de enteros, **DocumentID**.</span><span class="sxs-lookup"><span data-stu-id="dfb38-140">As recommended, this index key is created on an integer column, **DocumentID**.</span></span> <span data-ttu-id="dfb38-141">En el ejemplo se especifica el LCID de inglés, 1033, que es el idioma de los datos de las columnas.</span><span class="sxs-lookup"><span data-stu-id="dfb38-141">The example specifies the LCID for English, 1033, which is the language of the data in the columns.</span></span>  
  
 <span data-ttu-id="dfb38-142">En este ejemplo también se especifica que el seguimiento de cambios está desactivado sin rellenado.</span><span class="sxs-lookup"><span data-stu-id="dfb38-142">This example also specifies that change tracking is off with no population.</span></span> <span data-ttu-id="dfb38-143">Posteriormente, durante las horas de menor actividad, en el ejemplo se usa una instrucción **ALTER FULLTEXT INDEX** para iniciar un rellenado completo en el nuevo índice y habilitar el seguimiento automático de cambios.</span><span class="sxs-lookup"><span data-stu-id="dfb38-143">Later, during off-peak hours, the example uses an **ALTER FULLTEXT INDEX** statement to start a full population on the new index and enable automatic change tracking.</span></span>  
  
```sql  
CREATE FULLTEXT CATALOG documents_catalog  
GO  
  
CREATE FULLTEXT INDEX ON Production.Document  
    (   
    Title  
        Language 1033,   
    DocumentSummary  
        Language 1033,   
    Document   
        TYPE COLUMN FileExtension  
        Language 1033  
        Statistical_Semantics  
    )  
    KEY INDEX PK_Document_DocumentID  
        ON documents_catalog  
        WITH CHANGE_TRACKING OFF, NO POPULATION  
GO  
```  
  
 <span data-ttu-id="dfb38-144">Posteriormente, durante horas de menor actividad, el índice se rellena:</span><span class="sxs-lookup"><span data-stu-id="dfb38-144">Later, at an off-peak time, the index is populated:</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document SET CHANGE_TRACKING AUTO  
GO  
```  
  
 <span data-ttu-id="dfb38-145">**Crear un nuevo índice semántico con SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="dfb38-145">**Create a new semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="dfb38-146">Ejecute el Asistente para indexación de texto completo y habilite **Semántica estadística** en la página **Seleccionar columnas de la tabla** para cada columna en la que quiera crear un índice semántico.</span><span class="sxs-lookup"><span data-stu-id="dfb38-146">Run the Full-Text Indexing Wizard and enable **Statistical Semantics** on the **Select Table Columns** page for each column on which you want to create a semantic index.</span></span> <span data-ttu-id="dfb38-147">Para obtener más información, incluida la información sobre cómo iniciar el Asistente para indexación de texto completo, vea [Usar el Asistente para indexación de texto completo](use-the-full-text-indexing-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="dfb38-147">For more information, including information about how to start the Full-Text Indexing Wizard, see [Use the Full-Text Indexing Wizard](use-the-full-text-indexing-wizard.md).</span></span>  
  
###  <a name="how-to-create-a-semantic-index-when-there-is-an-existing-full-text-index"></a><a name="HowToEnableAlter"></a><span data-ttu-id="dfb38-148">Cómo: crear un índice semántico cuando hay un índice de texto completo existente</span><span class="sxs-lookup"><span data-stu-id="dfb38-148">How To: Create a Semantic Index When There Is an Existing Full-Text Index</span></span>  
 <span data-ttu-id="dfb38-149">Puede agregar la indexación semántica cuando modifique un índice de texto completo existente con la instrucción **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-149">You can add semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="dfb38-150">También puede agregar la semántica con varios cuadros de diálogo de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfb38-150">You can also add semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="dfb38-151">**Agregar un índice semántico con Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="dfb38-151">**Add a semantic index by using Transact-SQL**</span></span>  
 <span data-ttu-id="dfb38-152">Llame a la instrucción **ALTER FULLTEXT INDEX** con las opciones descritas más adelante para cada columna en la que quiera agregar un índice semántico.</span><span class="sxs-lookup"><span data-stu-id="dfb38-152">Call the **ALTER FULLTEXT INDEX** statement with the options described below for each column on which you want to add a semantic index.</span></span> <span data-ttu-id="dfb38-153">Para obtener más información sobre todas las opciones de esta instrucción, vea [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfb38-153">For more information about all the options for this statement, see [ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-fulltext-index-transact-sql).</span></span>  
  
 <span data-ttu-id="dfb38-154">Tanto el índice de texto completo como el índice semántico se vuelven a rellenar después de llamar a **ALTER**, a menos que se especifique lo contrario.</span><span class="sxs-lookup"><span data-stu-id="dfb38-154">Both full-text and semantic indexes are repopulated after a call to **ALTER**, unless you specify otherwise.</span></span>  
  
-   <span data-ttu-id="dfb38-155">Para agregar una indexación de texto completo solo a una columna, use la sintaxis **ADD** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-155">To add full-text indexing only to a column, use the **ADD** syntax.</span></span>  
  
-   <span data-ttu-id="dfb38-156">Para agregar tanto una indexación de texto completo como una indexación semántica a una columna, use la sintaxis **ADD** con la opción **STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-156">To add both full-text and semantic indexing to a column, use the **ADD** syntax with the **STATISTICAL_SEMANTICS** option.</span></span>  
  
-   <span data-ttu-id="dfb38-157">Para agregar una indexación semántica a una columna que ya esté habilitada para la indexación de texto completo, use la opción **ADD STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-157">To add semantic indexing to a column that is already enabled for full-text indexing, use the **ADD STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="dfb38-158">Solo puede agregar una indización semántica a una columna en una única instrucción **ALTER** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-158">You can only add semantic indexing to one column in a single **ALTER** statement.</span></span>  
  
 <span data-ttu-id="dfb38-159">**Ejemplo: agregar una indización semántica a una columna que ya tenga indización de texto completo**</span><span class="sxs-lookup"><span data-stu-id="dfb38-159">**Example: Add semantic indexing to a column that already has full-text indexing**</span></span>  
  
 <span data-ttu-id="dfb38-160">En el ejemplo siguiente se modifica un índice de texto completo existente en la tabla **Production.Document** de la base de datos de ejemplo AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="dfb38-160">The following example alters an existing full-text index on **Production.Document** table in AdventureWorks2012 sample database.</span></span> <span data-ttu-id="dfb38-161">En el ejemplo se agrega un índice semántico en la columna **Document** de la tabla **Production.Document** , que ya tiene un índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-161">The example adds a semantic index on the **Document** column of the **Production.Document** table, which already has a full-text index.</span></span> <span data-ttu-id="dfb38-162">En el ejemplo se especifica que el índice no se volverá a rellenar automáticamente.</span><span class="sxs-lookup"><span data-stu-id="dfb38-162">The example specifies that the index will not be repopulated automatically.</span></span>  
  
```sql  
ALTER FULLTEXT INDEX ON Production.Document  
    ALTER COLUMN Document  
        ADD Statistical_Semantics  
    WITH NO POPULATION  
GO  
```  
  
 <span data-ttu-id="dfb38-163">**Agregar un índice semántico con SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="dfb38-163">**Add a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="dfb38-164">Puede cambiar las columnas habilitadas para la indexación semántica y de texto completo en la página **Columnas de índice de texto completo** del cuadro de diálogo **Propiedades del índice de texto completo** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-164">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="dfb38-165">Para obtener más información, vea [Administrar índices de texto completo](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="dfb38-165">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-altering-an-existing-index"></a><a name="addreq"></a><span data-ttu-id="dfb38-166">Requisitos y restricciones para modificar un índice existente</span><span class="sxs-lookup"><span data-stu-id="dfb38-166">Requirements and Restrictions for Altering an Existing Index</span></span>  
  
-   <span data-ttu-id="dfb38-167">No puede modificar ningún índice existente mientras el rellenado del mismo esté en curso.</span><span class="sxs-lookup"><span data-stu-id="dfb38-167">You cannot alter an existing index while population of the index is in progress.</span></span> <span data-ttu-id="dfb38-168">Para obtener más información sobre cómo supervisar el progreso del rellenado de índices, vea [Administrar y supervisar la búsqueda semántica](manage-and-monitor-semantic-search.md).</span><span class="sxs-lookup"><span data-stu-id="dfb38-168">For more information on monitoring the progress of index population, see [Manage and Monitor Semantic Search](manage-and-monitor-semantic-search.md).</span></span>  
  
-   <span data-ttu-id="dfb38-169">No puede agregar indización a una columna ni modificar o quitar la indización de la misma columna en una sola llamada a la instrucción **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-169">You cannot add indexing to a column, and alter or drop indexing for the same column, in a single call to the **ALTER FULLTEXT INDEX** statement.</span></span>  
  
##  <a name="dropping-a-semantic-index"></a><a name="dropping"></a><span data-ttu-id="dfb38-170">Quitar un índice semántico</span><span class="sxs-lookup"><span data-stu-id="dfb38-170">Dropping a Semantic Index</span></span>  
  
###  <a name="how-to-drop-a-semantic-index"></a><a name="drophow"></a><span data-ttu-id="dfb38-171">Cómo: quitar un índice semántico</span><span class="sxs-lookup"><span data-stu-id="dfb38-171">How to: Drop a Semantic Index</span></span>  
 <span data-ttu-id="dfb38-172">Puede quitar la indexación semántica cuando modifique un índice de texto completo existente con la instrucción **ALTER FULLTEXT INDEX** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-172">You can drop semantic indexing when you alter an existing full-text index with the **ALTER FULLTEXT INDEX** statement.</span></span> <span data-ttu-id="dfb38-173">También puede quitar la indización semántica con varios cuadros de diálogo de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dfb38-173">You can also drop semantic indexing by using various dialog boxes in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="dfb38-174">**Agregar o quitar un índice semántico con Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="dfb38-174">**Drop a semantic index by using Transact-SQL**</span></span>  
 -   <span data-ttu-id="dfb38-175">Para quitar la indexación semántica solo de una columna o de algunas columnas, se debe llamar a la instrucción **ALTER FULLTEXT INDEX** con la opción **ALTER COLUMN***nombre_columna***DROP STATISTICAL_SEMANTICS** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-175">To drop semantic indexing only from a column or columns, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP STATISTICAL_SEMANTICS** option.</span></span> <span data-ttu-id="dfb38-176">Puede quitar la indización de varias columnas en una sola instrucción **ALTER** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-176">You can drop the indexing from multiple columns in a single **ALTER** statement.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP STATISTICAL_SEMANTICS  
    GO  
    ```  
  
-   <span data-ttu-id="dfb38-177">Para quitar la indización de texto completo y semántica de una columna, llame a la instrucción **ALTER fulltext index** con la opción **ALTER Column***column_name***Drop** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-177">To drop both full-text and semantic indexing from a column, call the **ALTER FULLTEXT INDEX** statement with the **ALTER COLUMN***column_name***DROP** option.</span></span>  
  
    ```sql  
    USE database_name  
    GO  
  
    ALTER FULLTEXT INDEX  
        ALTER COLUMN column_name  
        DROP  
    GO  
    ```  
  
 <span data-ttu-id="dfb38-178">**Agregar o quitar un índice semántico con SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="dfb38-178">**Drop a semantic index by using SQL Server Management Studio**</span></span>  
 <span data-ttu-id="dfb38-179">Puede cambiar las columnas habilitadas para la indexación semántica y de texto completo en la página **Columnas de índice de texto completo** del cuadro de diálogo **Propiedades del índice de texto completo** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-179">You can change the columns that are enabled for semantic and full-text indexing on the **Full-Text Index Columns** page of the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="dfb38-180">Para obtener más información, vea [Administrar índices de texto completo](../../database-engine/manage-full-text-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="dfb38-180">For more information, see [Manage Full-Text Indexes](../../database-engine/manage-full-text-indexes.md).</span></span>  
  
###  <a name="requirements-and-restrictions-for-dropping-a-semantic-index"></a><a name="dropreq"></a><span data-ttu-id="dfb38-181">Requisitos y restricciones para quitar un índice semántico</span><span class="sxs-lookup"><span data-stu-id="dfb38-181">Requirements and Restrictions for Dropping a Semantic Index</span></span>  
  
-   <span data-ttu-id="dfb38-182">No puede quitar la indización de texto completo de ninguna columna mientras se conserve la indización semántica.</span><span class="sxs-lookup"><span data-stu-id="dfb38-182">You cannot drop full-text indexing from a column while retaining semantic indexing.</span></span> <span data-ttu-id="dfb38-183">La indización semántica depende de la indización de texto completo para los resultados de similitud de documentos.</span><span class="sxs-lookup"><span data-stu-id="dfb38-183">Semantic indexing depends on full-text indexing for document similarity results.</span></span>  
  
-   <span data-ttu-id="dfb38-184">No puede especificar la opción **NO POPULATION** cuando quite la indización semántica de la última columna de una tabla para la que se habilitó la indización semántica.</span><span class="sxs-lookup"><span data-stu-id="dfb38-184">You cannot specify the **NO POPULATION** option when you drop semantic indexing from the last column in a table for which semantic indexing was enabled.</span></span> <span data-ttu-id="dfb38-185">Se requiere un ciclo de rellenado para quitar los resultados que se indizaron previamente.</span><span class="sxs-lookup"><span data-stu-id="dfb38-185">A population cycle is required to remove the results that were indexed previously.</span></span>  
  
## <a name="checking-whether-semantic-search-is-enabled-on-database-objects"></a><span data-ttu-id="dfb38-186">Comprobar si la búsqueda semántica está habilitada en objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="dfb38-186">Checking Whether Semantic Search Is Enabled on Database Objects</span></span>  
  
###  <a name="how-to-check-whether-semantic-search-is-enabled-on-database-objects"></a><a name="HowToCheckEnabled"></a><span data-ttu-id="dfb38-187">Cómo: comprobar si la búsqueda semántica está habilitada en objetos de base de datos</span><span class="sxs-lookup"><span data-stu-id="dfb38-187">How To: Check Whether Semantic Search Is Enabled on Database Objects</span></span>  
 <span data-ttu-id="dfb38-188">**¿La búsqueda semántica está habilitada para una base de datos?**</span><span class="sxs-lookup"><span data-stu-id="dfb38-188">**Is semantic search enabled for a database?**</span></span>  
 <span data-ttu-id="dfb38-189">Consulte la propiedad **IsFullTextEnabled** de la función de metadatos [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfb38-189">Query the **IsFullTextEnabled** property of the [DATABASEPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/databasepropertyex-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="dfb38-190">Un valor devuelto de 1 indica que la búsqueda de texto completo y la búsqueda semántica están habilitadas para la base de datos; un valor devuelto de 0 indica lo contrario.</span><span class="sxs-lookup"><span data-stu-id="dfb38-190">A return value of 1 indicates that full-text search and semantic search are enabled for the database; a return value of 0 indicates that they are not enabled.</span></span>  
  
```sql  
SELECT DATABASEPROPERTYEX('database_name', 'IsFullTextEnabled')  
GO  
```  
  
 <span data-ttu-id="dfb38-191">**¿La búsqueda semántica está habilitada para una tabla?**</span><span class="sxs-lookup"><span data-stu-id="dfb38-191">**Is semantic search enabled for a table?**</span></span>  
 <span data-ttu-id="dfb38-192">Consulte la propiedad **TableFullTextSemanticExtraction** de la función de metadatos [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfb38-192">Query the **TableFullTextSemanticExtraction** property of the [OBJECTPROPERTYEX &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectproperty-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="dfb38-193">Un valor devuelto de 1 indica que la búsqueda semántica está habilitada para la tabla; un valor devuelto de 0 indica lo contrario.</span><span class="sxs-lookup"><span data-stu-id="dfb38-193">A return value of 1 indicates that semantic search is enabled for the table; a return value of 0 indicates that it is not enabled.</span></span>  
  
```scr  
SELECT OBJECTPROPERTYEX(OBJECT_ID('table_name'), 'TableFullTextSemanticExtraction')  
GO  
```  
  
 <span data-ttu-id="dfb38-194">**¿La búsqueda semántica está habilitada para una columna?**</span><span class="sxs-lookup"><span data-stu-id="dfb38-194">**Is semantic search enabled for a column?**</span></span>  
 <span data-ttu-id="dfb38-195">Para determinar si la búsqueda semántica está habilitada para una columna específica:</span><span class="sxs-lookup"><span data-stu-id="dfb38-195">To determine whether semantic search is enabled for a specific column:</span></span>  
  
-   <span data-ttu-id="dfb38-196">Consulte la propiedad **StatisticalSemantics** de la función de metadatos [COLUMNPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/columnproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfb38-196">Query the **StatisticalSemantics** property of the [COLUMNPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/columnproperty-transact-sql) metadata function.</span></span>  
  
     <span data-ttu-id="dfb38-197">Un valor devuelto de 1 indica que la búsqueda semántica está habilitada para la columna; un valor devuelto de 0 indica lo contrario.</span><span class="sxs-lookup"><span data-stu-id="dfb38-197">A return value of 1 indicates that semantic search is enabled for the column; a return value of 0 indicates that it is not enabled.</span></span>  
  
    ```sql  
    SELECT COLUMNPROPERTY(OBJECT_ID('table_name'), 'column_name', 'StatisticalSemantics')  
    GO  
    ```  
  
-   <span data-ttu-id="dfb38-198">Consulte la vista de catálogo [sys.fulltext_index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) para el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-198">Query the catalog view [sys.fulltext_index_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-index-columns-transact-sql) for the full-text index.</span></span>  
  
     <span data-ttu-id="dfb38-199">Un valor de 1 en la columna **statistical_semantics** indica que la columna especificada está habilitada para la indexación semántica además de la indexación de texto completo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-199">A value of 1 in the **statistical_semantics** column indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
    ```sql  
    SELECT * FROM sys.fulltext_index_columns WHERE object_id = OBJECT_ID('table_name')  
    GO  
    ```  
  
-   <span data-ttu-id="dfb38-200">En el Explorador de objetos de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], haga clic con el botón derecho en una columna y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="dfb38-200">In Object Explorer in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click on a column and select **Properties**.</span></span> <span data-ttu-id="dfb38-201">En la página **General** del cuadro de diálogo **Propiedades de columna** , compruebe el valor de la propiedad **Semántica estadística** .</span><span class="sxs-lookup"><span data-stu-id="dfb38-201">On the **General** page of the **Column Properties** dialog box, check the value of the **Statistical Semantics** property.</span></span>  
  
     <span data-ttu-id="dfb38-202">Un valor True indica que la columna especificada está habilitada para la indización semántica además de la indización de texto completo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-202">A value of True indicates that the specified column is enabled for semantic indexing in addition to full-text indexing.</span></span>  
  
## <a name="determining-what-can-be-indexed-for-semantic-search"></a><span data-ttu-id="dfb38-203">Determinar qué se puede indizar para la búsqueda semántica</span><span class="sxs-lookup"><span data-stu-id="dfb38-203">Determining What Can Be Indexed for Semantic Search</span></span>  
  
###  <a name="how-to-check-which-languages-are-supported-for-semantic-search"></a><a name="HowToCheckLanguages"></a><span data-ttu-id="dfb38-204">Cómo: comprobar qué idiomas se admiten para la búsqueda semántica</span><span class="sxs-lookup"><span data-stu-id="dfb38-204">How To: Check Which Languages Are Supported for Semantic Search</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dfb38-205">Hay menos idiomas que sean compatibles con la indización semántica que con la indización de texto completo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-205">Fewer languages are supported for semantic indexing than for full-text indexing.</span></span> <span data-ttu-id="dfb38-206">Como resultado, puede haber columnas que pueda indizar para la búsqueda de texto completo, pero que no para la búsqueda semántica.</span><span class="sxs-lookup"><span data-stu-id="dfb38-206">As a result, there may be columns that you can index for full-text search, but not for semantic search.</span></span>  
  
 <span data-ttu-id="dfb38-207">Consulte la vista de catálogo [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfb38-207">Query the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.fulltext_semantic_languages  
GO  
```  
  
 <span data-ttu-id="dfb38-208">Los siguientes idiomas se admiten para la indización semántica.</span><span class="sxs-lookup"><span data-stu-id="dfb38-208">The following languages are supported for semantic indexing.</span></span> <span data-ttu-id="dfb38-209">En esta lista se representa la salida de la vista de catálogo [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql), ordenada por LCID.</span><span class="sxs-lookup"><span data-stu-id="dfb38-209">This list represents the output of the catalog view [sys.fulltext_semantic_languages &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-languages-transact-sql), ordered by LCID.</span></span>  
  
|<span data-ttu-id="dfb38-210">Idioma</span><span class="sxs-lookup"><span data-stu-id="dfb38-210">Language</span></span>|<span data-ttu-id="dfb38-211">LCID</span><span class="sxs-lookup"><span data-stu-id="dfb38-211">LCID</span></span>|  
|--------------|----------|  
|<span data-ttu-id="dfb38-212">Alemán</span><span class="sxs-lookup"><span data-stu-id="dfb38-212">German</span></span>|<span data-ttu-id="dfb38-213">1031</span><span class="sxs-lookup"><span data-stu-id="dfb38-213">1031</span></span>|  
|<span data-ttu-id="dfb38-214">Inglés (EE. UU.)</span><span class="sxs-lookup"><span data-stu-id="dfb38-214">English (US)</span></span>|<span data-ttu-id="dfb38-215">3082</span><span class="sxs-lookup"><span data-stu-id="dfb38-215">1033</span></span>|  
|<span data-ttu-id="dfb38-216">Francés</span><span class="sxs-lookup"><span data-stu-id="dfb38-216">French</span></span>|<span data-ttu-id="dfb38-217">1036</span><span class="sxs-lookup"><span data-stu-id="dfb38-217">1036</span></span>|  
|<span data-ttu-id="dfb38-218">Italiano</span><span class="sxs-lookup"><span data-stu-id="dfb38-218">Italian</span></span>|<span data-ttu-id="dfb38-219">1040</span><span class="sxs-lookup"><span data-stu-id="dfb38-219">1040</span></span>|  
|<span data-ttu-id="dfb38-220">Portugués (Brasil)</span><span class="sxs-lookup"><span data-stu-id="dfb38-220">Portuguese (Brazil)</span></span>|<span data-ttu-id="dfb38-221">1046</span><span class="sxs-lookup"><span data-stu-id="dfb38-221">1046</span></span>|  
|<span data-ttu-id="dfb38-222">Ruso</span><span class="sxs-lookup"><span data-stu-id="dfb38-222">Russian</span></span>|<span data-ttu-id="dfb38-223">1049</span><span class="sxs-lookup"><span data-stu-id="dfb38-223">1049</span></span>|  
|<span data-ttu-id="dfb38-224">Sueco</span><span class="sxs-lookup"><span data-stu-id="dfb38-224">Swedish</span></span>|<span data-ttu-id="dfb38-225">1053</span><span class="sxs-lookup"><span data-stu-id="dfb38-225">1053</span></span>|  
|<span data-ttu-id="dfb38-226">English (Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="dfb38-226">English (UK)</span></span>|<span data-ttu-id="dfb38-227">2057</span><span class="sxs-lookup"><span data-stu-id="dfb38-227">2057</span></span>|  
|<span data-ttu-id="dfb38-228">Portugués (Portugal)</span><span class="sxs-lookup"><span data-stu-id="dfb38-228">Portuguese (Portugal)</span></span>|<span data-ttu-id="dfb38-229">2070</span><span class="sxs-lookup"><span data-stu-id="dfb38-229">2070</span></span>|  
|<span data-ttu-id="dfb38-230">Español</span><span class="sxs-lookup"><span data-stu-id="dfb38-230">Spanish</span></span>|<span data-ttu-id="dfb38-231">3082</span><span class="sxs-lookup"><span data-stu-id="dfb38-231">3082</span></span>|  
  
###  <a name="how-to-determine-which-document-types-can-be-indexed"></a><a name="doctypes"></a><span data-ttu-id="dfb38-232">Cómo: determinar qué tipos de documento se pueden indizar</span><span class="sxs-lookup"><span data-stu-id="dfb38-232">How To: Determine Which Document Types Can Be Indexed</span></span>  
 <span data-ttu-id="dfb38-233">Consulte la vista de catálogo [sys.fulltext_document_types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="dfb38-233">Query the catalog view [sys.fulltext_document_types &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-document-types-transact-sql).</span></span>  
  
 <span data-ttu-id="dfb38-234">Si el tipo de documento que desea indizar no está en la lista de tipos compatibles, puede tener que buscar, descargar, e instalar filtros adicionales.</span><span class="sxs-lookup"><span data-stu-id="dfb38-234">If the document type that you want to index is not in the list of supported types, then you may have to locate, download, and install additional filters.</span></span> <span data-ttu-id="dfb38-235">Para obtener más información, consulte [ver o cambiar los filtros registrados y separadores de palabras](view-or-change-registered-filters-and-word-breakers.md).</span><span class="sxs-lookup"><span data-stu-id="dfb38-235">For more information, see [View or Change Registered Filters and Word Breakers](view-or-change-registered-filters-and-word-breakers.md).</span></span>  
  
##  <a name="best-practice-consider-creating-a-separate-filegroup-for-the-full-text-and-semantic-indexes"></a><a name="BestPracticeFilegroup"></a><span data-ttu-id="dfb38-236">Procedimiento recomendado: considere la posibilidad de crear un grupo de archivos independiente para los índices de texto completo y semánticos.</span><span class="sxs-lookup"><span data-stu-id="dfb38-236">Best Practice: Consider Creating a Separate Filegroup for the Full-Text and Semantic Indexes</span></span>  
 <span data-ttu-id="dfb38-237">Plantéese crear un grupo de archivos independiente para los índices de texto completo y semántico si la asignación de espacio en disco es un problema.</span><span class="sxs-lookup"><span data-stu-id="dfb38-237">Consider creating a separate filegroup for the full-text and semantic indexes if disk space allocation is a concern.</span></span> <span data-ttu-id="dfb38-238">Los índices semánticos se crean en el mismo grupo de archivos que el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="dfb38-238">The semantic indexes are created in the same filegroup as the full-text index.</span></span> <span data-ttu-id="dfb38-239">Un índice semántico totalmente rellenado puede contener una gran cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="dfb38-239">A fully populated semantic index may contain large amount of data.</span></span>  
  
##  <a name="BestPracticeUnderstand"></a>   
##  <a name="problem-searching-on-specific-column-returns-no-results"></a><a name="IssueNoResults"></a><span data-ttu-id="dfb38-240">Problema: la búsqueda en una columna específica no devuelve resultados</span><span class="sxs-lookup"><span data-stu-id="dfb38-240">Problem: Searching on Specific Column Returns No Results</span></span>  
 <span data-ttu-id="dfb38-241">**¿Se especificó un LCID que no sea Unicode para un idioma Unicode?**</span><span class="sxs-lookup"><span data-stu-id="dfb38-241">**Was a non-Unicode LCID specified for a Unicode language?**</span></span>  
 <span data-ttu-id="dfb38-242">Se puede habilitar la indización semántica en un tipo de columna que no sea Unicode con un LCID para un idioma que solo tenga palabras Unicode, como LCID 1049 para ruso.</span><span class="sxs-lookup"><span data-stu-id="dfb38-242">It is possible to enable semantic indexing on a non-Unicode column type with an LCID for a language that only has Unicode words, such as LCID 1049 for Russian.</span></span> <span data-ttu-id="dfb38-243">En este caso, nunca se obtendrán resultados de los índices semánticos de esta columna.</span><span class="sxs-lookup"><span data-stu-id="dfb38-243">In this case, no results will ever be returned from the semantic indexes on this column.</span></span>  
  
  
