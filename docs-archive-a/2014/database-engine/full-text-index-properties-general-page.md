---
title: Propiedades del índice de texto completo (página general) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.general.f1
ms.assetid: f4dff61c-8c2f-4ff9-abe4-70a34421448f
author: rothja
ms.author: jroth
ms.openlocfilehash: 61b9f2948df138c39230cf6f5787c395a364c695
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677835"
---
# <a name="full-text-index-properties-general-page"></a><span data-ttu-id="898e8-102">Propiedades del índice de texto completo (página General)</span><span class="sxs-lookup"><span data-stu-id="898e8-102">Full-Text Index Properties (General Page)</span></span>
  <span data-ttu-id="898e8-103">**Para ver o cambiar las propiedades modificables de un índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="898e8-103">**To view or change the modifiable properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="898e8-104">Administrar índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="898e8-104">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="898e8-105">Lista de elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="898e8-105">UI element list</span></span>  
 <span data-ttu-id="898e8-106">**Catálogo de texto completo**</span><span class="sxs-lookup"><span data-stu-id="898e8-106">**Full-Text Catalog**</span></span>  
 <span data-ttu-id="898e8-107">Muestra el nombre del catálogo de texto completo al que se asocia el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="898e8-107">Displays the name of the full-text catalog with which the full-text index is associated.</span></span>  
  
 <span data-ttu-id="898e8-108">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="898e8-108">**Database**</span></span>  
 <span data-ttu-id="898e8-109">Muestra el nombre de la base de datos en la que el índice de texto completo reside.</span><span class="sxs-lookup"><span data-stu-id="898e8-109">Displays the name of the database in which the full-text index resides.</span></span>  
  
 <span data-ttu-id="898e8-110">**Tabla**</span><span class="sxs-lookup"><span data-stu-id="898e8-110">**Table**</span></span>  
 <span data-ttu-id="898e8-111">Muestra el nombre de la tabla en la que se define el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="898e8-111">Displays the name of the table on which the full-text index is defined.</span></span>  
  
 <span data-ttu-id="898e8-112">**Clave de índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="898e8-112">**Full-Text Index Key**</span></span>  
 <span data-ttu-id="898e8-113">Muestra el nombre de la clave de índice de texto completo, que es un índice único en una columna única de la tabla.</span><span class="sxs-lookup"><span data-stu-id="898e8-113">Displays the name of the full-text index key, which is a unique index on a single column of the table.</span></span>  
  
 <span data-ttu-id="898e8-114">**Estado de llenado de texto completo de tabla**</span><span class="sxs-lookup"><span data-stu-id="898e8-114">**Table Full-Text Populate Status**</span></span>  
 <span data-ttu-id="898e8-115">Muestra el estado de rellenado de una tabla con índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="898e8-115">Displays the population status of the full-text indexed table.</span></span>  
  
 <span data-ttu-id="898e8-116">Los valores posibles son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="898e8-116">The possible values are as follows:</span></span>  
  
 <span data-ttu-id="898e8-117">0 = Inactiva</span><span class="sxs-lookup"><span data-stu-id="898e8-117">0 = Idle.</span></span>  
  
 <span data-ttu-id="898e8-118">1 = Rellenado completo en curso.</span><span class="sxs-lookup"><span data-stu-id="898e8-118">1 = Full population is in progress.</span></span>  
  
 <span data-ttu-id="898e8-119">2 = Rellenado incremental en curso.</span><span class="sxs-lookup"><span data-stu-id="898e8-119">2 = Incremental population is in progress.</span></span>  
  
 <span data-ttu-id="898e8-120">3 = Propagación de cambios de seguimiento en curso.</span><span class="sxs-lookup"><span data-stu-id="898e8-120">3 = Propagation of tracked changes is in progress.</span></span>  
  
 <span data-ttu-id="898e8-121">4 = Actualización de índices en segundo plano en curso, como el seguimiento de cambios automáticos.</span><span class="sxs-lookup"><span data-stu-id="898e8-121">4 = Background update index is in progress, such as automatic change tracking.</span></span>  
  
 <span data-ttu-id="898e8-122">5 = Indización de texto completo acelerada o pausada.</span><span class="sxs-lookup"><span data-stu-id="898e8-122">5 = Full-text indexing is throttled or paused.</span></span>  
  
 <span data-ttu-id="898e8-123">**Índice de texto completo activo**</span><span class="sxs-lookup"><span data-stu-id="898e8-123">**Active Full-Text Index**</span></span>  
 <span data-ttu-id="898e8-124">Indica si la tabla tiene un índice de texto completo activo.</span><span class="sxs-lookup"><span data-stu-id="898e8-124">Indicates whether the table has an active full-text index.</span></span>  
  
 <span data-ttu-id="898e8-125">1 = True</span><span class="sxs-lookup"><span data-stu-id="898e8-125">1 = True</span></span>  
  
 <span data-ttu-id="898e8-126">0 = False</span><span class="sxs-lookup"><span data-stu-id="898e8-126">0 = False</span></span>  
  
 <span data-ttu-id="898e8-127">**Grupo de archivos de índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="898e8-127">**Full-Text Index Filegroup**</span></span>  
 <span data-ttu-id="898e8-128">Grupo de archivos al que pertenece el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="898e8-128">The filegroup to which the full-text index belongs.</span></span>  
  
 <span data-ttu-id="898e8-129">**Lista de palabras irrelevantes de índice de texto completo**</span><span class="sxs-lookup"><span data-stu-id="898e8-129">**Full-Text Index Stoplist**</span></span>  
 <span data-ttu-id="898e8-130">Lista de palabras irrelevantes asociada al índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="898e8-130">The stoplist that is currently associated with the full-text index.</span></span> <span data-ttu-id="898e8-131">Una lista de [palabras irrelevantes](../relational-databases/search/full-text-search.md)es sinónimo de una lista de palabras sin trascendencia.</span><span class="sxs-lookup"><span data-stu-id="898e8-131">A stoplist is a list of [stopwords](../relational-databases/search/full-text-search.md).</span></span> <span data-ttu-id="898e8-132">La lista de palabras irrelevantes asociada a un índice de texto completo, si existe, se aplica a las consultas de texto completo en ese índice.</span><span class="sxs-lookup"><span data-stu-id="898e8-132">The stoplist associated with a full-text index, if any, is applied to full-text queries on that index.</span></span> <span data-ttu-id="898e8-133">Puede quitar la lista de palabras irrelevantes del índice seleccionando **\<OFF>** en la lista, o puede seleccionar una lista de palabras irrelevantes diferente; **\<SYSTEM>** indica la lista de palabras irrelevantes del sistema.</span><span class="sxs-lookup"><span data-stu-id="898e8-133">You can remove the stoplist from the index by selecting **\<OFF>** from the list, or you can select a different stoplist; **\<SYSTEM>** indicates the system stoplist.</span></span>  
  
 <span data-ttu-id="898e8-134">**Para crear una lista de palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="898e8-134">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="898e8-135">Configurar y administrar palabras irrelevantes y listas de palabras irrelevantes para la búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="898e8-135">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>](../relational-databases/search/full-text-search.md)  
  
 <span data-ttu-id="898e8-136">**Lista de propiedades de búsqueda**</span><span class="sxs-lookup"><span data-stu-id="898e8-136">**Search Property List**</span></span>  
 <span data-ttu-id="898e8-137">La lista de propiedades de búsqueda asociada actualmente al índice de texto completo, si la hay.</span><span class="sxs-lookup"><span data-stu-id="898e8-137">The search property list that is currently associated with the full-text index, if any.</span></span> <span data-ttu-id="898e8-138">Una lista de propiedades de búsqueda especifica un conjunto de propiedades de documento que se incluyen en el índice de texto completo asociado cuando este se rellena.</span><span class="sxs-lookup"><span data-stu-id="898e8-138">A search property list specifies a set of document properties that are included in the associated full-text index when it is populated.</span></span> <span data-ttu-id="898e8-139">Para obtener más información, vea [Buscar propiedades de documento con listas de propiedades de búsqueda](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span><span class="sxs-lookup"><span data-stu-id="898e8-139">For more information, see [Search Document Properties with Search Property Lists](../relational-databases/search/search-document-properties-with-search-property-lists.md).</span></span>  
  
 <span data-ttu-id="898e8-140">**\<Off>** indica que actualmente no hay ninguna lista de propiedades de búsqueda asociada al índice.</span><span class="sxs-lookup"><span data-stu-id="898e8-140">**\<Off>** indicates that there is currently no search property list associated with the index.</span></span> <span data-ttu-id="898e8-141">Puede quitar la lista de propiedades de búsqueda actual del índice seleccionando **\<Off>** en la lista o puede seleccionar otra lista de propiedades de búsqueda en la lista.</span><span class="sxs-lookup"><span data-stu-id="898e8-141">You can remove the current search property list from the index by selecting **\<Off>** from the list, or you can select a different search property list from the list.</span></span> <span data-ttu-id="898e8-142">Esta lista solo contiene las listas de propiedades de búsqueda de la base de datos actual.</span><span class="sxs-lookup"><span data-stu-id="898e8-142">Only search property lists in the current database are listed here.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="898e8-143">Puede asociar una lista de propiedades de búsqueda a más de un índice de texto completo en la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="898e8-143">You can associate a given search property list with more than one full-text index in the same database.</span></span>  
  
 <span data-ttu-id="898e8-144">**Para crear una lista de propiedades de búsqueda**</span><span class="sxs-lookup"><span data-stu-id="898e8-144">**To create a search property list**</span></span>  
  
-   [<span data-ttu-id="898e8-145">Buscar propiedades de documento con listas de propiedades de búsqueda</span><span class="sxs-lookup"><span data-stu-id="898e8-145">Search Document Properties with Search Property Lists</span></span>](../relational-databases/search/search-document-properties-with-search-property-lists.md)  
  
 <span data-ttu-id="898e8-146">**Recuento de elementos de texto completo de tabla**</span><span class="sxs-lookup"><span data-stu-id="898e8-146">**Table Full-Text Item Count**</span></span>  
 <span data-ttu-id="898e8-147">Indica el número de filas que se han indizado con índice de texto completo correctamente.</span><span class="sxs-lookup"><span data-stu-id="898e8-147">Indicates the number of rows that were full-text indexed successfully.</span></span>  
  
 <span data-ttu-id="898e8-148">Esta propiedad corresponde a la propiedad `TableFulltextItemCount` devuelta por la función OBJECTPROPERTYEX de [!INCLUDE[tsql](../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="898e8-148">This property corresponds to the `TableFulltextItemCount` property returned by the OBJECTPROPERTYEX [!INCLUDE[tsql](../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="898e8-149">**Documentos de texto completo de tabla procesados**</span><span class="sxs-lookup"><span data-stu-id="898e8-149">**Table Full-Text Docs Processed**</span></span>  
 <span data-ttu-id="898e8-150">Muestra el número de filas que se han procesado desde el comienzo de la indización de texto completo.</span><span class="sxs-lookup"><span data-stu-id="898e8-150">Displays the number of rows that have been processed since the start of full-text indexing.</span></span> <span data-ttu-id="898e8-151">En una tabla que se indiza para búsquedas en texto completo, todas las columnas de una fila se consideran como parte de un documento que se va a indizar.</span><span class="sxs-lookup"><span data-stu-id="898e8-151">In a table that is being indexed for full-text search, all the columns of one row are considered as part of one document to be indexed.</span></span> <span data-ttu-id="898e8-152">No se cuentan las filas eliminadas.</span><span class="sxs-lookup"><span data-stu-id="898e8-152">Deleted rows are not counted.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="898e8-153">0</span><span class="sxs-lookup"><span data-stu-id="898e8-153">0</span></span>|<span data-ttu-id="898e8-154">Indica que la indización de texto completo se ha completado y no hay ningún rellenado activo.</span><span class="sxs-lookup"><span data-stu-id="898e8-154">Indicates that full-text indexing is completed and there is no active population.</span></span>|  
|<span data-ttu-id="898e8-155">>0</span><span class="sxs-lookup"><span data-stu-id="898e8-155">> 0</span></span>|<span data-ttu-id="898e8-156">Con un rellenado activo, indica el número de documentos procesados por las operaciones de inserción u actualización desde que se realizara alguna de las operaciones siguientes: un rellenado, la habilitación del seguimiento de cambios con rellenado de índices de actualización en segundo plano (como el seguimiento de cambios automático), el cambio del esquema de índice de texto completo, la regeneración del catálogo de texto completo, la reinicialización de la instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], etc.</span><span class="sxs-lookup"><span data-stu-id="898e8-156">For an active population, indicates the number of documents processed by insert or update operations since any of the following: a population, enabling of change tracking with background update index population (such as auto change tracking), changing the full-text index schema, rebuilding the full-text catalog, restarting the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and so forth.</span></span>|  
  
 <span data-ttu-id="898e8-157">**Cambios pendientes de texto completo de tabla**</span><span class="sxs-lookup"><span data-stu-id="898e8-157">**Table Full-Text Pending Changes**</span></span>  
 <span data-ttu-id="898e8-158">Número de entradas de seguimiento de cambios pendientes de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="898e8-158">Number of pending change tracking entries to process.</span></span>  
  
 <span data-ttu-id="898e8-159">0 = El seguimiento de cambios no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="898e8-159">0 = change tracking is not enabled.</span></span>  
  
 <span data-ttu-id="898e8-160">NULL = La tabla no tiene un índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="898e8-160">NULL = Table does not have a full-text index.</span></span>  
  
 <span data-ttu-id="898e8-161">**Recuento de errores de texto completo de tabla**</span><span class="sxs-lookup"><span data-stu-id="898e8-161">**Table Full-Text Fail Count**</span></span>  
 <span data-ttu-id="898e8-162">Número de filas que no ha indizado la búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="898e8-162">The number of rows that full-text search did not index.</span></span>  
  
 <span data-ttu-id="898e8-163">0 = El rellenado se ha completado.</span><span class="sxs-lookup"><span data-stu-id="898e8-163">0 = The population has completed.</span></span>  
  
 <span data-ttu-id="898e8-164">\>0 = uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="898e8-164">\>0 = One of the following:</span></span>  
  
-   <span data-ttu-id="898e8-165">Número de documentos no indizados desde el comienzo del rellenado de seguimiento de cambios de actualización completa, incremental o manual.</span><span class="sxs-lookup"><span data-stu-id="898e8-165">The number of documents that were not indexed since the start of full, incremental, or manual change tracking population.</span></span>  
  
-   <span data-ttu-id="898e8-166">Para el seguimiento de cambios con actualización de índices en segundo plano, el número de filas no indizadas desde el comienzo del rellenado o desde su reinicio.</span><span class="sxs-lookup"><span data-stu-id="898e8-166">For change tracking with background update index, the number of rows that were not indexed since the start of the population, or the restart of the population.</span></span> <span data-ttu-id="898e8-167">Esto podría ser debido a un cambio de esquema, una regeneración del catálogo, un reinicio del servidor, etc.</span><span class="sxs-lookup"><span data-stu-id="898e8-167">This could be caused by a schema change, rebuild of the catalog, server restart, and so on</span></span>  
  
 <span data-ttu-id="898e8-168">**Indexación de texto completo habilitada**</span><span class="sxs-lookup"><span data-stu-id="898e8-168">**Full-Text Indexing Enabled**</span></span>  
 <span data-ttu-id="898e8-169">Especifica si la indización de texto completo está habilitada.</span><span class="sxs-lookup"><span data-stu-id="898e8-169">Specifies whether full-text indexing is enabled.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="898e8-170">**True**</span><span class="sxs-lookup"><span data-stu-id="898e8-170">**True**</span></span>|<span data-ttu-id="898e8-171">habilitado</span><span class="sxs-lookup"><span data-stu-id="898e8-171">Enabled</span></span>|  
|<span data-ttu-id="898e8-172">**False**</span><span class="sxs-lookup"><span data-stu-id="898e8-172">**False**</span></span>|<span data-ttu-id="898e8-173">Disabled</span><span class="sxs-lookup"><span data-stu-id="898e8-173">Disabled</span></span>|  
  
 <span data-ttu-id="898e8-174">**Seguimiento de cambios**</span><span class="sxs-lookup"><span data-stu-id="898e8-174">**Change Tracking**</span></span>  
 <span data-ttu-id="898e8-175">Especifica si la tabla tiene el seguimiento de cambios de texto completo habilitado y, en ese caso, qué tipo.</span><span class="sxs-lookup"><span data-stu-id="898e8-175">Specifies whether the table has full-text change-tracking enabled, and if so, what kind.</span></span> <span data-ttu-id="898e8-176">El seguimiento de cambios de texto completo mantiene un registro de las filas que se han modificado en una tabla o vista indizada configurada para la indización de texto completo.</span><span class="sxs-lookup"><span data-stu-id="898e8-176">Full-text change tracking maintains a record of the rows that have been modified in a table or indexed view that has been set up for full-text indexing.</span></span> <span data-ttu-id="898e8-177">Estos cambios se pueden propagar al índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="898e8-177">These changes can be propagated to the full-text index.</span></span>  
  
 <span data-ttu-id="898e8-178">Los valores de **Seguimiento de cambios** son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="898e8-178">The **Change Tracking** values are as follows:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="898e8-179">**Desactivado**</span><span class="sxs-lookup"><span data-stu-id="898e8-179">**Off**</span></span>|<span data-ttu-id="898e8-180">El índice de texto completo no se actualiza con los cambios en los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="898e8-180">The full-text index is not updated with changes to the underlying data.</span></span>|  
|<span data-ttu-id="898e8-181">**Manual**</span><span class="sxs-lookup"><span data-stu-id="898e8-181">**Manual**</span></span>|<span data-ttu-id="898e8-182">El índice de texto completo no se actualiza automáticamente cuando se producen cambios en los datos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="898e8-182">The full-text index is not updated automatically as changes occur to the underlying data.</span></span> <span data-ttu-id="898e8-183">Sin embargo, estos cambios se mantienen y puede propagarlos al</span><span class="sxs-lookup"><span data-stu-id="898e8-183">However, changes to the underlying data are maintained, and you can propagate them to the .</span></span> <span data-ttu-id="898e8-184">índice de texto completo según una programación usando el Agente SQL Server o de forma manual.</span><span class="sxs-lookup"><span data-stu-id="898e8-184">full-text index either on a schedule using SQL Server Agent or manually.</span></span>|  
|<span data-ttu-id="898e8-185">**Automático**</span><span class="sxs-lookup"><span data-stu-id="898e8-185">**Automatic**</span></span>|<span data-ttu-id="898e8-186">El índice de texto completo se actualiza automáticamente cuando se producen cambios en los datos subyacentes de la tabla base.</span><span class="sxs-lookup"><span data-stu-id="898e8-186">The full-text index is updated automatically as changes occur to the underlying data in the base table.</span></span>|  
  
 <span data-ttu-id="898e8-187">**Volver a llenar el índice**</span><span class="sxs-lookup"><span data-stu-id="898e8-187">**Repopulate index**</span></span>  
 <span data-ttu-id="898e8-188">Haga clic para iniciar un rellenado en el índice de texto completo en salir del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="898e8-188">Click to start a population on the full-text index on exiting the dialog box.</span></span> <span data-ttu-id="898e8-189">Seleccione uno de los tipos de rellenado siguientes:</span><span class="sxs-lookup"><span data-stu-id="898e8-189">Select one of the following types of population:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="898e8-190">**Completa**</span><span class="sxs-lookup"><span data-stu-id="898e8-190">**Full**</span></span>|<span data-ttu-id="898e8-191">Durante el rellenado completo de una tabla, se crean entradas de índice para todas las filas.</span><span class="sxs-lookup"><span data-stu-id="898e8-191">During a full population of a table, index entries are built for all the rows.</span></span>|  
|<span data-ttu-id="898e8-192">**Incremental**</span><span class="sxs-lookup"><span data-stu-id="898e8-192">**Incremental**</span></span>|<span data-ttu-id="898e8-193">El rellenado incremental actualiza el índice de texto completo de las filas que se hayan agregado, eliminado o modificado desde el último rellenado o en su transcurso.</span><span class="sxs-lookup"><span data-stu-id="898e8-193">Incremental population updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="898e8-194">Realizar un rellenado incremental requiere que la tabla base contenga una columna del tipo de datos `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="898e8-194">Performing an incremental population requires that the base table contain a column of the `timestamp` data type.</span></span>|  
|<span data-ttu-id="898e8-195">**Actualizar**</span><span class="sxs-lookup"><span data-stu-id="898e8-195">**Update**</span></span>|<span data-ttu-id="898e8-196">El índice de texto completo se actualiza siempre que se modifican los datos de la tabla base.</span><span class="sxs-lookup"><span data-stu-id="898e8-196">The full-text index is updated whenever the data in the base table is modified.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="898e8-197">Consulte también</span><span class="sxs-lookup"><span data-stu-id="898e8-197">See Also</span></span>  
 [<span data-ttu-id="898e8-198">Introducción a la búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="898e8-198">Get Started with Full-Text Search</span></span>](../relational-databases/search/get-started-with-full-text-search.md)  
  
  
