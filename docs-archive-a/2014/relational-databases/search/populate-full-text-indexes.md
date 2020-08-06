---
title: Relleno de índices de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- index populations [full-text search]
- incremental populations [full-text search]
- populations [full-text search]
- full-text search [SQL Server], populations
- crawls [full-text search]
- automatic full-text index updates
- change tracking-based populations [full-text search]
- manual updates [full-text search]
- manual populations [full-text search]
- auto populations [full-text search]
- full-text indexes [SQL Server], key column
- full populations [full-text search]
- full-text indexes [SQL Server], populations
ms.assetid: 76767b20-ef55-49ce-8dc4-e77cb8ff618a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9ab93a3514fa260c8c3836da85c767da3c3051a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675782"
---
# <a name="populate-full-text-indexes"></a><span data-ttu-id="ba8a6-102">Rellenar índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="ba8a6-102">Populate Full-Text Indexes</span></span>
  <span data-ttu-id="ba8a6-103">La creación y el mantenimiento de un índice de texto completo implica el rellenado del índice mediante un proceso denominado *rellenado* (también se denomina *rastreo*).</span><span class="sxs-lookup"><span data-stu-id="ba8a6-103">Creating and maintaining a full-text index involves populating the index by using a process called a *population* (also known as a *crawl*).</span></span>  
  
##  <a name="types-of-population"></a><a name="types"></a><span data-ttu-id="ba8a6-104">Tipos de rellenado</span><span class="sxs-lookup"><span data-stu-id="ba8a6-104">Types of Population</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="ba8a6-105">admite los siguientes tipos de rellenado: rellenado completo, rellenado automático o manual basado en el seguimiento de cambios y rellenado incremental basado en la marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-105">supports the following types of population: full population, change tracking-based automatic or manual population, and incremental timestamp-based population.</span></span>  
  
### <a name="full-population"></a><span data-ttu-id="ba8a6-106">Rellenado completo</span><span class="sxs-lookup"><span data-stu-id="ba8a6-106">Full Population</span></span>  
 <span data-ttu-id="ba8a6-107">Durante un rellenado completo, se crean entradas de índice para todas las filas de una tabla o vista indizada.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-107">During a full population, index entries are built for all the rows of a table or indexed view.</span></span> <span data-ttu-id="ba8a6-108">Un rellenado completo de un índice de texto completo genera entradas de índice para todas las filas de la tabla base o vista indizada.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-108">A full population of a full-text index, builds index entries for all the rows of the base table or indexed view.</span></span>  
  
 <span data-ttu-id="ba8a6-109">De forma predeterminada, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rellena totalmente un nuevo índice de texto completo en cuanto se crea.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-109">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] populates a new full-text index fully as soon as it is created.</span></span> <span data-ttu-id="ba8a6-110">Sin embargo, un rellenado completo puede consumir una cantidad significativa de recursos.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-110">However, a full population can consume a significant amount of resources.</span></span> <span data-ttu-id="ba8a6-111">Por consiguiente, al crear un índice de texto completo durante los períodos de máxima actividad, suele ser aconsejable retrasar el rellenado completo hasta un momento de menor uso, particularmente si la tabla base de un índice de texto completo es grande.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-111">Therefore, when creating a full-text index during peak periods, it is often a best practice to delay the full population until an off-peak time, particularly if the base table of an full-text index is large.</span></span> <span data-ttu-id="ba8a6-112">Sin embargo, el catálogo de texto completo al que pertenece el índice no se puede usar hasta que se rellenan todos sus índices de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-112">However, the full-text catalog to which the index belongs is not usable until all of its full-text indexes are populated.</span></span> <span data-ttu-id="ba8a6-113">Para crear un índice de texto completo sin rellenarlo inmediatamente, especifique la cláusula CHANGE_TRACKING OFF, NO POPULATION en la instrucción CREATE FULLTEXT INDEX.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-113">To create a full-text index without populating it immediately, specify the CHANGE_TRACKING OFF, NO POPULATION clause in the CREATE FULLTEXT INDEX statement.</span></span> <span data-ttu-id="ba8a6-114">Si especifica CHANGE_TRACKING MANUAL, el motor de búsqueda de texto completo usa la instrucción.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-114">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses statement.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="ba8a6-115">no rellenará el nuevo índice de texto completo hasta que se ejecute una instrucción ALTER FULLTEXT INDEX mediante la cláusula START FULL POPULATION o START INCREMENTAl POPULATION.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-115">will not populate the new full-text index until you execute an ALTER FULLTEXT INDEX statement using the START FULL POPULATION or START INCREMENTAL POPULATION clause.</span></span> <span data-ttu-id="ba8a6-116">Para obtener más información, vea los ejemplos "A.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-116">For more information, see examples "A.</span></span> <span data-ttu-id="ba8a6-117">Crear un índice de texto completo sin ejecutar un rellenado completo" y "B.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-117">Creating a full-text index without running a full population" and "B.</span></span> <span data-ttu-id="ba8a6-118">Ejecutar un rellenado completo en la tabla", posteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-118">Running a full population on table," later in this topic.</span></span>  
  

  
### <a name="change-tracking-based-population"></a><span data-ttu-id="ba8a6-119">Rellenado basado en el seguimiento de cambios</span><span class="sxs-lookup"><span data-stu-id="ba8a6-119">Change Tracking-Based Population</span></span>  
 <span data-ttu-id="ba8a6-120">Si se desea, se puede usar el seguimiento de cambios para mantener un índice de texto completo después de su rellenado completo inicial.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-120">Optionally, you can use change tracking to maintain a full-text index after its initial full population.</span></span> <span data-ttu-id="ba8a6-121">El seguimiento de cambios provoca una pequeña sobrecarga de trabajo porque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mantiene una tabla en la que realiza el seguimiento de los cambios de la tabla base desde el último rellenado.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-121">There is a small overhead associated with change tracking because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a table in which it tracks changes to the base table since the last population.</span></span> <span data-ttu-id="ba8a6-122">Cuando se utiliza el seguimiento de cambios, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mantiene un registro de las filas de la tabla base o la vista indizada que se han modificado con las actualizaciones, eliminaciones o inserciones.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-122">When change tracking is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] maintains a record of the rows in the base table or indexed view that have been modified by updates, deletes, or inserts.</span></span> <span data-ttu-id="ba8a6-123">Los cambios realizados en los datos con WRITETEXT y UPDATETEXT no se reflejan en el índice de texto completo y no se recopilan con el seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-123">Data changes through WRITETEXT and UPDATETEXT are not reflected in the full-text index, and are not picked up with change tracking.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba8a6-124">Para las tablas que contienen una columna `timestamp`, puede utilizar los rellenados incrementales.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-124">For tables containing a `timestamp` column, you can use incremental populations.</span></span>  
  
 <span data-ttu-id="ba8a6-125">Cuando el seguimiento de cambios está habilitado durante la creación de índices, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rellena totalmente el nuevo índice de texto completo justo después de crearse.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-125">When change tracking is enabled during index creation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fully populates the new full-text index immediately after it is created.</span></span> <span data-ttu-id="ba8a6-126">Después de esto, los cambios se siguen y propagan al índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-126">Thereafter, changes are tracked and propagated to the full-text index.</span></span> <span data-ttu-id="ba8a6-127">Hay dos tipos de seguimiento de cambios: automático (opción CHANGE_TRACKING AUTO) y manual (opción CHANGE_TRACKING MANUAL).</span><span class="sxs-lookup"><span data-stu-id="ba8a6-127">There are two types of change tracking, automatic (CHANGE_TRACKING AUTO option) and manual (CHANGE_TRACKING MANUAL option).</span></span> <span data-ttu-id="ba8a6-128">El seguimiento de cambios automático es el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-128">Automatic change tracking is the default behavior.</span></span>  
  
 <span data-ttu-id="ba8a6-129">El tipo de seguimiento de cambios determina cómo se rellena el índice de texto completo, de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="ba8a6-129">The type of change tracking determines how the full-text index is populated, as follows:</span></span>  
  
-   <span data-ttu-id="ba8a6-130">Rellenado automático</span><span class="sxs-lookup"><span data-stu-id="ba8a6-130">Automatic population</span></span>  
  
     <span data-ttu-id="ba8a6-131">De forma predeterminada, o si especifica CHANGE_TRACKING AUTO, el motor de búsqueda de texto completo utiliza el rellenado automático en el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-131">By default, or if you specify CHANGE_TRACKING AUTO, the Full-Text Engine uses automatic population on the full-text index.</span></span> <span data-ttu-id="ba8a6-132">Una vez completado el rellenado total inicial, se realiza el seguimiento de los cambios cuando los datos se modifican en la tabla base y los cambios sometidos a seguimiento se propagan de forma automática.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-132">After the initial full population completes, changes are tracked as data is modified in the base table, and the tracked changes are propagated automatically.</span></span> <span data-ttu-id="ba8a6-133">Sin embargo, el índice de texto completo se actualiza en segundo plano, de modo que los cambios propagados podrían no reflejarse inmediatamente en el índice.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-133">The full-text index is updated in the background, however, so propagated changes might not be reflected immediately in the index.</span></span>  
  
     <span data-ttu-id="ba8a6-134">**Para configurar el seguimiento de los cambios con rellenado automático**</span><span class="sxs-lookup"><span data-stu-id="ba8a6-134">**To set up tracking changes with automatic population**</span></span>  
  
    -   <span data-ttu-id="ba8a6-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="ba8a6-135">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING AUTO</span></span>  
  
    -   <span data-ttu-id="ba8a6-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING AUTO</span><span class="sxs-lookup"><span data-stu-id="ba8a6-136">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING AUTO</span></span>  
  
     <span data-ttu-id="ba8a6-137">Para obtener más información, vea el ejemplo "E.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-137">For more information, see example "E.</span></span> <span data-ttu-id="ba8a6-138">Modificar un índice de texto completo para utilizar el seguimiento de cambios automático", posteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-138">Altering a full-text index to use automatic change tracking," later in this topic.</span></span>  
  
-   <span data-ttu-id="ba8a6-139">Rellenado manual</span><span class="sxs-lookup"><span data-stu-id="ba8a6-139">Manual population</span></span>  
  
     <span data-ttu-id="ba8a6-140">Si especifica CHANGE_TRACKING MANUAL, el motor de búsqueda de texto completo utiliza el rellenado manual en el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-140">If you specify CHANGE_TRACKING MANUAL, the Full-Text Engine uses manual population on the full-text index.</span></span> <span data-ttu-id="ba8a6-141">Una vez completado el rellenado total inicial, se realiza el seguimiento de los cambios a medida que los datos se modifiquen en la tabla base.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-141">After the initial full population completes, changes are tracked as data is modified in the base table.</span></span> <span data-ttu-id="ba8a6-142">Pero no se propagan al índice de texto completo hasta que se ejecuta una instrucción ALTER FULLTEXT INDEX ... START UPDATE POPULATION .</span><span class="sxs-lookup"><span data-stu-id="ba8a6-142">However, they are not propagated to the full-text index until you execute an ALTER FULLTEXT INDEX ... START UPDATE POPULATION statement.</span></span> <span data-ttu-id="ba8a6-143">Puede utilizar el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para llamar a esta instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] de forma periódica.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-143">You can use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to call this [!INCLUDE[tsql](../../includes/tsql-md.md)] statement periodically.</span></span>  
  
     <span data-ttu-id="ba8a6-144">**Para iniciar el seguimiento de cambios con rellenado manual**</span><span class="sxs-lookup"><span data-stu-id="ba8a6-144">**To start tracking changes with manual population**</span></span>  
  
    -   <span data-ttu-id="ba8a6-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="ba8a6-145">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING MANUAL</span></span>  
  
    -   <span data-ttu-id="ba8a6-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING MANUAL</span><span class="sxs-lookup"><span data-stu-id="ba8a6-146">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING MANUAL</span></span>  
  
     <span data-ttu-id="ba8a6-147">Para obtener más información, vea los ejemplos "C.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-147">For more information, see examples "C.</span></span> <span data-ttu-id="ba8a6-148">Crear un índice de texto completo con seguimiento de cambios manual" y "D.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-148">Creating a full-text index with manual change tracking" and "D.</span></span> <span data-ttu-id="ba8a6-149">Ejecutar un rellenado manual", posteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-149">Running a manual population," later in this topic.</span></span>  
  
 <span data-ttu-id="ba8a6-150">**Para desactivar el seguimiento de cambios**</span><span class="sxs-lookup"><span data-stu-id="ba8a6-150">**To turn off change tracking**</span></span>  
  
-   <span data-ttu-id="ba8a6-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="ba8a6-151">[CREATE FULLTEXT INDEX](/sql/t-sql/statements/create-fulltext-index-transact-sql) ... WITH CHANGE_TRACKING OFF</span></span>  
  
-   <span data-ttu-id="ba8a6-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING OFF</span><span class="sxs-lookup"><span data-stu-id="ba8a6-152">[ALTER FULLTEXT INDEX](/sql/t-sql/statements/alter-fulltext-index-transact-sql) ... SET CHANGE_TRACKING OFF</span></span>  
  

  
### <a name="incremental-timestamp-based-population"></a><span data-ttu-id="ba8a6-153">Rellenado basado en la marca de tiempo incremental</span><span class="sxs-lookup"><span data-stu-id="ba8a6-153">Incremental Timestamp-Based Population</span></span>  
 <span data-ttu-id="ba8a6-154">Un rellenado incremental es un mecanismo alternativo para rellenar un índice de texto completo manualmente.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-154">An incremental population is an alternative mechanism for manually populating a full-text index.</span></span> <span data-ttu-id="ba8a6-155">Puede ejecutar un llenado incremental de un índice de texto completo que tenga CHANGE_TRACKING configurado en MANUAL o en OFF.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-155">You can run an incremental population for a full-text index that has CHANGE_TRACKING set to MANUAL or OFF.</span></span> <span data-ttu-id="ba8a6-156">Si el primer llenado de un índice de texto completo es un llenado incremental, indiza todas las filas, lo que lo hace equivalente a un llenado completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-156">If the first population on a full-text index is an incremental population, it indexes all rows, making it equivalent to a full population.</span></span>  
  
 <span data-ttu-id="ba8a6-157">Para realizar un llenado incremental, es necesario que la tabla indizada tenga una columna del tipo de datos `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-157">The requirement for incremental population is that the indexed table must have a column of the `timestamp` data type.</span></span> <span data-ttu-id="ba8a6-158">Si no existe una columna de tipo `timestamp`, no puede llevarse a cabo un llenado incremental.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-158">If a `timestamp` column does not exist, incremental population cannot be performed.</span></span> <span data-ttu-id="ba8a6-159">Si se solicita un rellenado incremental en una tabla sin una columna de tipo `timestamp`, se llevará a cabo un rellenado completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-159">A request for incremental population on a table without a `timestamp` column results in a full population operation.</span></span> <span data-ttu-id="ba8a6-160">Además, si alguno de los metadatos que afectan al índice de texto completo de la tabla ha cambiado desde el último rellenado, las solicitudes de rellenado incremental se implementan como rellenados completos.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-160">Also, if any metadata that affects the full-text index for the table has changed since the last population, incremental population requests are implemented as full populations.</span></span> <span data-ttu-id="ba8a6-161">Esto incluye los cambios en los metadatos ocasionados al alterar la definición de una columna, índice o índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-161">This includes metadata changes caused by altering any column, index, or full-text index definitions.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="ba8a6-162">utiliza la columna `timestamp` para identificar las filas que han cambiado desde el último rellenado.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-162">uses the `timestamp` column to identify rows that have changed since the last population.</span></span> <span data-ttu-id="ba8a6-163">El rellenado incremental actualiza entonces el índice de texto completo de las filas que se hayan agregado, eliminado o modificado desde el último rellenado o en el curso del último rellenado.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-163">The incremental population then updates the full-text index for rows added, deleted, or modified after the last population, or while the last population was in progress.</span></span> <span data-ttu-id="ba8a6-164">Si una tabla experimenta un volumen alto de inserciones, el rellenado incremental puede ser más eficaz que el rellenado manual.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-164">If a table experiences a high volume of inserts, using incremental population can be more efficient that using manual population.</span></span>  
  
 <span data-ttu-id="ba8a6-165">Al final de un proceso de rellenado, el motor de texto completo registra un nuevo valor de tipo `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-165">At the end of a population, the Full-Text Engine records a new `timestamp` value.</span></span> <span data-ttu-id="ba8a6-166">Este valor es el valor de `timestamp` mayor que el recopilador de SQL ha encontrado.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-166">This value is the largest `timestamp` value that SQL Gatherer has encountered.</span></span> <span data-ttu-id="ba8a6-167">Se usará cuando se inicie un rellenado incremental posterior.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-167">This value will be used when a subsequent incremental population starts.</span></span>  
  
 <span data-ttu-id="ba8a6-168">Para ejecutar un rellenado incremental, ejecute una instrucción ALTER FULLTEXT INDEX con la cláusula START INCREMENTAL POPULATION.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-168">To run an incremental population, execute an ALTER FULLTEXT INDEX statement using the START INCREMENTAL POPULATION clause.</span></span>  
  

  
##  <a name="examples-of-populating-full-text-indexes"></a><a name="examples"></a><span data-ttu-id="ba8a6-169">Ejemplos de rellenar índices de texto completo</span><span class="sxs-lookup"><span data-stu-id="ba8a6-169">Examples of Populating Full-Text Indexes</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba8a6-170">En los ejemplos de esta sección se usa la tabla `Production.Document` o `HumanResources.JobCandidate` de la base de datos de ejemplo `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="ba8a6-170">The examples in this section use the `Production.Document` or `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
### <a name="a-creating-a-full-text-index-without-running-a-full-population"></a><span data-ttu-id="ba8a6-171">A.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-171">A.</span></span> <span data-ttu-id="ba8a6-172">Crear un índice de texto completo sin ejecutar un rellenado completo</span><span class="sxs-lookup"><span data-stu-id="ba8a6-172">Creating a full-text index without running a full population</span></span>  
 <span data-ttu-id="ba8a6-173">En el ejemplo siguiente se crea un índice de texto completo en la tabla `Production.Document` de la base de datos de ejemplo `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="ba8a6-173">The following example creates a full-text index on the `Production.Document` table of the `AdventureWorks` sample database.</span></span> <span data-ttu-id="ba8a6-174">En este ejemplo se usa WITH CHANGE_TRACKING OFF, NO POPULATION para retrasar el rellenado completo inicial.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-174">This example uses WITH CHANGE_TRACKING OFF, NO POPULATION to delay the initial full population.</span></span>  
  
```  
CREATE UNIQUE INDEX ui_ukDoc ON Production.Document(DocumentID);  
CREATE FULLTEXT CATALOG AW_Production_FTCat;  
CREATE FULLTEXT INDEX ON Production.Document  
(  
    Document                         --Full-text index column name   
        TYPE COLUMN FileExtension    --Name of column that contains file type information  
        Language 1033                 --1033 is LCID for the English language  
)  
    KEY INDEX ui_ukDoc  
    ON AW_Production_FTCat  
    WITH CHANGE_TRACKING OFF, NO POPULATION;  
GO  
  
```  
  
### <a name="b-running-a-full-population-on-table"></a><span data-ttu-id="ba8a6-175">B.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-175">B.</span></span> <span data-ttu-id="ba8a6-176">Ejecutar un rellenado completo en la tabla</span><span class="sxs-lookup"><span data-stu-id="ba8a6-176">Running a full population on table</span></span>  
 <span data-ttu-id="ba8a6-177">En el ejemplo siguiente se ejecuta un rellenado completo en la tabla `Production.Document` de la base de datos de ejemplo `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="ba8a6-177">The following example runs a full population on the `Production.Document` table of the `AdventureWorks` sample database.</span></span>  
  
```  
ALTER FULLTEXT INDEX ON Production.Document  
   START FULL POPULATION;  
```  
  
### <a name="c-creating-a-full-text-index-with-manual-change-tracking"></a><span data-ttu-id="ba8a6-178">C.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-178">C.</span></span> <span data-ttu-id="ba8a6-179">Crear un índice de texto completo con seguimiento de cambios manual</span><span class="sxs-lookup"><span data-stu-id="ba8a6-179">Creating a full-text index with manual change tracking</span></span>  
 <span data-ttu-id="ba8a6-180">En el ejemplo siguiente se crea un índice de texto completo que utilizará el seguimiento de cambios con rellenado manual en la tabla `HumanResources.JobCandidate` de la base de datos de ejemplo `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="ba8a6-180">The following example creates a full-text index that will use change tracking with manual population on the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE UNIQUE INDEX ui_ukJobCand ON HumanResources.JobCandidate(JobCandidateID);  
CREATE FULLTEXT CATALOG ft AS DEFAULT;  
CREATE FULLTEXT INDEX ON HumanResources.JobCandidate(Resume)   
   KEY INDEX ui_ukJobCand   
   WITH CHANGE_TRACKING=MANUAL;  
GO  
```  
  
### <a name="d-running-a-manual-population"></a><span data-ttu-id="ba8a6-181">D.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-181">D.</span></span> <span data-ttu-id="ba8a6-182">Ejecutar un rellenado manual</span><span class="sxs-lookup"><span data-stu-id="ba8a6-182">Running a manual population</span></span>  
 <span data-ttu-id="ba8a6-183">En el ejemplo siguiente se ejecuta un rellenado manual en el índice de texto completo sometido a seguimiento de la tabla `HumanResources.JobCandidate` de la base de datos de ejemplo `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="ba8a6-183">The following example runs a manual population on the change-tracked full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate START UPDATE POPULATION;  
GO  
```  
  
### <a name="e-altering-a-full-text-index-to-use-automatic-change-tracking"></a><span data-ttu-id="ba8a6-184">E.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-184">E.</span></span> <span data-ttu-id="ba8a6-185">Modificar un índice de texto completo para usar el seguimiento de cambios automático</span><span class="sxs-lookup"><span data-stu-id="ba8a6-185">Altering a full-text index to use automatic change tracking</span></span>  
 <span data-ttu-id="ba8a6-186">En el ejemplo siguiente se cambia el índice de texto completo de la tabla `HumanResources.JobCandidate` de la base de datos de ejemplo `AdventureWorks` para usar el seguimiento de cambios con rellenado automático.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-186">The following example changes the full-text index of the `HumanResources.JobCandidate` table of the `AdventureWorks` sample database to use change tracking with automatic population.</span></span>  
  
```  
USE AdventureWorks;  
GO  
ALTER FULLTEXT INDEX ON HumanResources.JobCandidate SET CHANGE_TRACKING AUTO;  
GO   
```  
  

  
##  <a name="creating-or-changing-a-schedule-for-incremental-population"></a><a name="create"></a><span data-ttu-id="ba8a6-187">Crear o cambiar una programación para el rellenado incremental</span><span class="sxs-lookup"><span data-stu-id="ba8a6-187">Creating or Changing a Schedule for Incremental Population</span></span>  
  
#### <a name="to-create-or-change-a-schedule-for-incremental-population-in-management-studio"></a><span data-ttu-id="ba8a6-188">Para crear o modificar una programación para el rellenado incremental en Management Studio</span><span class="sxs-lookup"><span data-stu-id="ba8a6-188">To create or change a schedule for incremental population in Management Studio</span></span>  
  
1.  <span data-ttu-id="ba8a6-189">En el Explorador de objetos, expanda el servidor.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-189">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="ba8a6-190">Expanda **Bases de datos**y, después, la base de datos que contiene el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-190">Expand **Databases**, and then expand the database that contains the full-text index.</span></span>  
  
3.  <span data-ttu-id="ba8a6-191">Expanda **Tablas**.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-191">Expand **Tables**.</span></span>  
  
 <span data-ttu-id="ba8a6-192">Haga clic con el botón derecho en la tabla en la que esté definido el índice de texto completo, seleccione **Índice de texto completo**y, en el menú contextual **Índice de texto completo** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-192">Right-click the table on which the full-text index is defined, select **Full-Text index**, and on the **Full-Text index** context menu, click **Properties**.</span></span> <span data-ttu-id="ba8a6-193">De esta forma se abre el cuadro de diálogo **Propiedades del índice de texto completo** .</span><span class="sxs-lookup"><span data-stu-id="ba8a6-193">This opens the **Full-text index Properties** dialog box.</span></span>  
  
1.  <span data-ttu-id="ba8a6-194">En el panel **seleccionar una página** , seleccione programaciones.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-194">In the **Select a page** pane, select Schedules.</span></span>  
  
     <span data-ttu-id="ba8a6-195">Utilice esta página para crear o administrar las programaciones para un trabajo del Agente SQL Server que inicia un rellenado de tabla incremental en la tabla base o vista indizada del índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-195">Use this page to create or manage schedules for a SQL Server Agent job that starts an incremental table population on the base table or indexed view of the full-text index.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="ba8a6-196">Si la tabla base o la vista no contienen ninguna columna del tipo de datos `timestamp`, se realiza un rellenado completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-196">If the base table or view does not contain a column of the `timestamp` data type, a full population is performed.</span></span>  
  
     <span data-ttu-id="ba8a6-197">Las opciones son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="ba8a6-197">The options are as follows:</span></span>  
  
    -   <span data-ttu-id="ba8a6-198">Para crear una nueva programación, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-198">To create a new schedule, click **New**.</span></span>  
  
         <span data-ttu-id="ba8a6-199">De esta forma se abre el cuadro de diálogo **Nueva programación de tabla de indexación de texto completo** , donde puede crear una programación.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-199">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can create a schedule.</span></span> <span data-ttu-id="ba8a6-200">Para guardar la programación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-200">To save the schedule, click **OK**.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="ba8a6-201">Un trabajo del Agente SQL Server (Iniciar rellenado de tabla incremental en *nombre_base_de_datos*.*nombre_tabla*) se asocia a una nueva programación después de salir del cuadro de diálogo **Propiedades del índice de texto completo** .</span><span class="sxs-lookup"><span data-stu-id="ba8a6-201">A SQL Server Agent job (Start Incremental Table Population on *database_name*.*table_name*) is associated with a new schedule after you exit the **Full-Text Index Properties** dialog box.</span></span> <span data-ttu-id="ba8a6-202">Si crea varias programaciones para el índice de texto completo, todas utilizan el mismo trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-202">If you create multiple schedules for the full-text index, they all use the same job.</span></span>  
  
    -   <span data-ttu-id="ba8a6-203">Para cambiar una programación, selecciónela y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-203">To change a schedule, select it and click **Edit**.</span></span>  
  
         <span data-ttu-id="ba8a6-204">De esta forma se abre el cuadro de diálogo **Nueva programación de tabla de indexación de texto completo** , donde puede modificar una programación.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-204">This opens the **New Full-Text Indexing Table Schedule** dialog box, where you can modify the schedule.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="ba8a6-205">Para obtener información sobre cómo modificar un trabajo, vea [Modificar un trabajo](../../ssms/agent/modify-a-job.md).</span><span class="sxs-lookup"><span data-stu-id="ba8a6-205">For information about modifying a job, see [Modify a Job](../../ssms/agent/modify-a-job.md).</span></span>  
  
    -   <span data-ttu-id="ba8a6-206">Para quitar una programación, selecciónela y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-206">To remove a schedule, select it and click **Delete**.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  

  
##  <a name="troubleshooting-errors-in-a-full-text-population-crawl"></a><a name="crawl"></a><span data-ttu-id="ba8a6-207">Solucionar errores en un rellenado de texto completo (rastreo)</span><span class="sxs-lookup"><span data-stu-id="ba8a6-207">Troubleshooting Errors in a Full-Text Population (Crawl)</span></span>  
 <span data-ttu-id="ba8a6-208">Cuando se produce un error durante un rastreo, la función de registro de rastreo de la búsqueda de texto completo crea y mantiene un registro de rastreo, que es un archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-208">When an error occurs during a crawl, the Full-Text Search crawl logging facility creates and maintains a crawl log, which is a plain text file.</span></span> <span data-ttu-id="ba8a6-209">Cada registro de rastreo se corresponde con un determinado catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-209">Each crawl log corresponds to a particular full-text catalog.</span></span> <span data-ttu-id="ba8a6-210">De forma predeterminada, los registros de rastreo de una instancia dada, en este caso la primera instancia, se ubican en la carpeta %Archivos de programa%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-210">By default crawl logs for a given instance, in this case, the first instance, are located in %ProgramFiles%\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\LOG folder.</span></span> <span data-ttu-id="ba8a6-211">El archivo de registro de rastreo sigue el siguiente esquema de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="ba8a6-211">The crawl log file follows the following naming scheme:</span></span>  
  
 <span data-ttu-id="ba8a6-212">SQLFT \<DatabaseID> \<FullTextCatalogID> . REGISTRO [ \<n> ]</span><span class="sxs-lookup"><span data-stu-id="ba8a6-212">SQLFT\<DatabaseID>\<FullTextCatalogID>.LOG[\<n>]</span></span>  
  
 <`DatabaseID`>  
 <span data-ttu-id="ba8a6-213">El identificador de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-213">The ID of a database.</span></span><span data-ttu-id="ba8a6-214"> <`dbid`> es un número de cinco dígitos con ceros a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-214"> <`dbid`> is a five digit number with leading zeros.</span></span>  
  
 <`FullTextCatalogID`>  
 <span data-ttu-id="ba8a6-215">Identificador de catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-215">Full-text catalog ID.</span></span><span data-ttu-id="ba8a6-216"> <`catid`> es un número de cinco dígitos con ceros a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-216"> <`catid`> is a five digit number with leading zeros.</span></span>  
  
 <`n`>  
 <span data-ttu-id="ba8a6-217">Es un entero que indica la existencia de uno o varios registros de rastreo del mismo catálogo de texto completo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-217">Is an integer that indicates one or more crawl logs of the same full-text catalog exist.</span></span>  
  
 <span data-ttu-id="ba8a6-218">Por ejemplo, SQLFT0000500008.2 es el archivo de registro de rastreo para un identificador de base de datos = 5 y un identificador de catálogo de texto completo = 8.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-218">For example, SQLFT0000500008.2 is the crawl log file for a database with database ID = 5, and full-text catalog ID = 8.</span></span> <span data-ttu-id="ba8a6-219">El 2 al final del nombre de archivo indica que existen dos archivos de registro de rastreo para esta pareja de base de datos y catálogo.</span><span class="sxs-lookup"><span data-stu-id="ba8a6-219">The 2 at the end of the file name indicates that there are two crawl log files for this database/catalog pair.</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="ba8a6-220">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba8a6-220">See Also</span></span>  
 <span data-ttu-id="ba8a6-221">[sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba8a6-221">[sys.dm_fts_index_population &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql) </span></span>  
 <span data-ttu-id="ba8a6-222">[Introducción a la búsqueda de texto completo](get-started-with-full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="ba8a6-222">[Get Started with Full-Text Search](get-started-with-full-text-search.md) </span></span>  
 <span data-ttu-id="ba8a6-223">[Crear y administrar índices de texto completo](create-and-manage-full-text-indexes.md) </span><span class="sxs-lookup"><span data-stu-id="ba8a6-223">[Create and Manage Full-Text Indexes](create-and-manage-full-text-indexes.md) </span></span>  
 <span data-ttu-id="ba8a6-224">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ba8a6-224">[CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-fulltext-index-transact-sql) </span></span>  
 [<span data-ttu-id="ba8a6-225">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ba8a6-225">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
  
