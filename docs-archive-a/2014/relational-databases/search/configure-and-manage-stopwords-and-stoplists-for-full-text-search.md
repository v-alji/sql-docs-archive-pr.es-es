---
title: Configurar y administrar palabras irrelevantes y listas de palabras irrelevantes para la búsqueda de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- stoplists [full-text search]
- full-text search [SQL Server], stoplists
- full-text search [SQL Server], noise words
- noise words [full-text search]
- full-text search [SQL Server], stopwords
- stopwords [full-text search]
ms.assetid: 43b5ce7b-9f09-4443-8a5b-c3da6eb28bcc
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 103b5024368c5ca239856580e9b45473aabf6a92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750646"
---
# <a name="configure-and-manage-stopwords-and-stoplists-for-full-text-search"></a><span data-ttu-id="3d658-102">Configurar y administrar palabras irrelevantes y listas de palabras irrelevantes para la búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="3d658-102">Configure and Manage Stopwords and Stoplists for Full-Text Search</span></span>
  <span data-ttu-id="3d658-103">Para evitar que un índice de texto completo se llene demasiado, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dispone de un mecanismo que descarta las cadenas más frecuentes que no ayudan en la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3d658-103">To prevent a full-text index from becoming bloated, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has a mechanism that discards commonly occurring strings that do not help the search.</span></span> <span data-ttu-id="3d658-104">Estas cadenas descartadas se denominan *palabras irrelevantes*.</span><span class="sxs-lookup"><span data-stu-id="3d658-104">These discarded strings are called *stopwords*.</span></span> <span data-ttu-id="3d658-105">Durante la creación de índices, el motor de texto completo omite las palabras irrelevantes del índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="3d658-105">During index creation, the Full-Text Engine omits stopwords from the full-text index.</span></span> <span data-ttu-id="3d658-106">Eso significa que las consultas de texto completo no buscarán las palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="3d658-106">This means that full-text queries will not search on stopwords.</span></span>  
  
##  <a name="understanding-stopwords-and-stoplists"></a><a name="understand"></a><span data-ttu-id="3d658-107">Descripción de palabras irrelevantes y palabras irrelevantes</span><span class="sxs-lookup"><span data-stu-id="3d658-107">Understanding Stopwords and Stoplists</span></span>  
 <span data-ttu-id="3d658-108">Una palabra irrelevante puede ser una palabra con significado en un idioma determinado o un *token* sin significado lingüístico.</span><span class="sxs-lookup"><span data-stu-id="3d658-108">A stopword can be a word with meaning in a specific language, or it can be a *token* that does not have linguistic meaning.</span></span> <span data-ttu-id="3d658-109">Por ejemplo, en inglés, las palabras como "a", "and", "is" y "the" se omiten en el índice de texto completo porque se ha determinado que no son útiles en una búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3d658-109">For example, in the English language, words such as "a," "and," "is," and "the" are left out of the full-text index since they are known to be useless to a search.</span></span>  
  
 <span data-ttu-id="3d658-110">Aunque omite la inclusión de palabras irrelevantes, el índice de texto completo tiene en cuenta la posición de las mismas.</span><span class="sxs-lookup"><span data-stu-id="3d658-110">Although it ignores the inclusion of stopwords, the full-text index does take into account their position.</span></span> <span data-ttu-id="3d658-111">Tomemos como ejemplo la frase en inglés "Instructions are applicable to these Adventure Works Cycles models ".</span><span class="sxs-lookup"><span data-stu-id="3d658-111">For example, consider the phrase, "Instructions are applicable to these Adventure Works Cycles models".</span></span> <span data-ttu-id="3d658-112">La siguiente tabla muestra la posición de las palabras en la frase:</span><span class="sxs-lookup"><span data-stu-id="3d658-112">The following table depicts the position of the words in the phrase:</span></span>  
  
|<span data-ttu-id="3d658-113">Word</span><span class="sxs-lookup"><span data-stu-id="3d658-113">Word</span></span>|<span data-ttu-id="3d658-114">Posición</span><span class="sxs-lookup"><span data-stu-id="3d658-114">Position</span></span>|  
|----------|--------------|  
|<span data-ttu-id="3d658-115">Instructions</span><span class="sxs-lookup"><span data-stu-id="3d658-115">Instructions</span></span>|<span data-ttu-id="3d658-116">1</span><span class="sxs-lookup"><span data-stu-id="3d658-116">1</span></span>|  
|<span data-ttu-id="3d658-117">are</span><span class="sxs-lookup"><span data-stu-id="3d658-117">are</span></span>|<span data-ttu-id="3d658-118">2</span><span class="sxs-lookup"><span data-stu-id="3d658-118">2</span></span>|  
|<span data-ttu-id="3d658-119">applicable</span><span class="sxs-lookup"><span data-stu-id="3d658-119">applicable</span></span>|<span data-ttu-id="3d658-120">3</span><span class="sxs-lookup"><span data-stu-id="3d658-120">3</span></span>|  
|<span data-ttu-id="3d658-121">to</span><span class="sxs-lookup"><span data-stu-id="3d658-121">to</span></span>|<span data-ttu-id="3d658-122">4</span><span class="sxs-lookup"><span data-stu-id="3d658-122">4</span></span>|  
|<span data-ttu-id="3d658-123">these</span><span class="sxs-lookup"><span data-stu-id="3d658-123">these</span></span>|<span data-ttu-id="3d658-124">5</span><span class="sxs-lookup"><span data-stu-id="3d658-124">5</span></span>|  
|<span data-ttu-id="3d658-125">Adventure</span><span class="sxs-lookup"><span data-stu-id="3d658-125">Adventure</span></span>|<span data-ttu-id="3d658-126">6</span><span class="sxs-lookup"><span data-stu-id="3d658-126">6</span></span>|  
|<span data-ttu-id="3d658-127">Works</span><span class="sxs-lookup"><span data-stu-id="3d658-127">Works</span></span>|<span data-ttu-id="3d658-128">7</span><span class="sxs-lookup"><span data-stu-id="3d658-128">7</span></span>|  
|<span data-ttu-id="3d658-129">Cycles</span><span class="sxs-lookup"><span data-stu-id="3d658-129">Cycles</span></span>|<span data-ttu-id="3d658-130">8</span><span class="sxs-lookup"><span data-stu-id="3d658-130">8</span></span>|  
|<span data-ttu-id="3d658-131">modelos</span><span class="sxs-lookup"><span data-stu-id="3d658-131">models</span></span>|<span data-ttu-id="3d658-132">9</span><span class="sxs-lookup"><span data-stu-id="3d658-132">9</span></span>|  
  
 <span data-ttu-id="3d658-133">Las palabras irrelevantes "are", "to" y "these" que se encuentran en las posiciones 2, 4 y 5 quedan excluidas del índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="3d658-133">The stopwords "are", "to", and "these" that are in positions 2, 4, and 5 are left out of the full-text index.</span></span> <span data-ttu-id="3d658-134">Sin embargo, se mantiene la información de su posición y, de este modo, no se ve afectada la posición de las demás palabras de la frase.</span><span class="sxs-lookup"><span data-stu-id="3d658-134">However, their positional information is maintained, thereby leaving the position of the other words in the phrase unaffected.</span></span>  
  
 <span data-ttu-id="3d658-135">Las palabras irrelevantes se administran en bases de datos mediante objetos denominados listas de palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="3d658-135">Stopwords are managed in databases using objects called stoplists.</span></span> <span data-ttu-id="3d658-136">Una *lista de palabras irrelevantes* es una lista de palabras que, cuando se asocia a un índice de texto completo, se aplica a las consultas de texto completo en ese índice.</span><span class="sxs-lookup"><span data-stu-id="3d658-136">A *stoplist* is a list of stopwords that, when associated with a full-text index, is applied to full-text queries on that index.</span></span>  
  
  
##  <a name="creating-a-stoplist"></a><a name="creating"></a><span data-ttu-id="3d658-137">Crear una lista de palabras irrelevantes</span><span class="sxs-lookup"><span data-stu-id="3d658-137">Creating a Stoplist</span></span>  
 <span data-ttu-id="3d658-138">Puede crear una lista de palabras irrelevantes de cualquiera de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d658-138">You can create a stoplist in any of the following ways:</span></span>  
  
-   <span data-ttu-id="3d658-139">Usar la lista de palabras irrelevantes proporcionada por el sistema en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3d658-139">Using the system-supplied stoplist in the database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3d658-140">se distribuye con una lista de palabras irrelevantes del sistema que contiene las palabras irrelevantes usadas normalmente para cada idioma compatible; es decir, para cada idioma que está asociado de forma predeterminada a determinados separadores de palabras.</span><span class="sxs-lookup"><span data-stu-id="3d658-140">ships with a system stoplist that contains the most commonly used stopwords for each supported language, that is for every language that is associated with given word breakers by default.</span></span> <span data-ttu-id="3d658-141">La lista de palabras irrelevantes del sistema contiene palabras irrelevantes de uso común en todos los idiomas admitidos.</span><span class="sxs-lookup"><span data-stu-id="3d658-141">The system stoplist contains common stopwords for all supported languages.</span></span>  <span data-ttu-id="3d658-142">Puede copiar la lista de palabras irrelevantes del sistema y personalizar la copia agregando y quitando palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="3d658-142">You can copy the system stoplist, and customize your copy by adding and removing stopwords.</span></span>  
  
     <span data-ttu-id="3d658-143">La lista de palabras irrelevantes del sistema se instala en la base de datos [Resource](../databases/resource-database.md) .</span><span class="sxs-lookup"><span data-stu-id="3d658-143">The system stoplist is installed in the [Resource](../databases/resource-database.md) database.</span></span>  
  
-   <span data-ttu-id="3d658-144">Crear una lista propia de palabras irrelevantes y agregar a ella palabras irrelevantes para cualquier idioma que especifique.</span><span class="sxs-lookup"><span data-stu-id="3d658-144">Creating your own stoplist, and then adding stopwords to it for any language that you specify.</span></span> <span data-ttu-id="3d658-145">También puede quitar palabras de la lista de palabras irrelevantes cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3d658-145">You can also drop stopwords from your stoplist when necessary.</span></span>  
  
-   <span data-ttu-id="3d658-146">Usar una lista de palabras irrelevantes personalizada de cualquier otra base de datos en la instancia del servidor actual, y agregar y quitar palabras cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3d658-146">Using an existing custom stoplist from any other database in the current server instance and then adding and dropping stopwords as necessary.</span></span>  
  
 <span data-ttu-id="3d658-147">**Para crear una lista de palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="3d658-147">**To create a stoplist**</span></span>  
  
-   [<span data-ttu-id="3d658-148">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d658-148">CREATE FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-stoplist-transact-sql)  
  
#### <a name="to-create-a-full-text-stoplist-in-management-studio"></a><span data-ttu-id="3d658-149">Para crear una lista de palabras irrelevantes de texto completo en Management Studio</span><span class="sxs-lookup"><span data-stu-id="3d658-149">To create a full-text stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="3d658-150">En el Explorador de objetos, expanda el servidor.</span><span class="sxs-lookup"><span data-stu-id="3d658-150">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="3d658-151">Expanda **Bases de datos**y luego la base de datos en la que quiere crear la lista de palabras irrelevantes de texto completo.</span><span class="sxs-lookup"><span data-stu-id="3d658-151">Expand **Databases**, and then expand the database in which you want to create the full-text stoplist.</span></span>  
  
3.  <span data-ttu-id="3d658-152">Expanda **Almacenamiento** y, a continuación, haga clic con el botón secundario en **Listas de palabras irrelevantes de texto completo**.</span><span class="sxs-lookup"><span data-stu-id="3d658-152">Expand **Storage**, and then right-click **Full-Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="3d658-153">Seleccione **Nueva lista de palabras irrelevantes de texto completo**.</span><span class="sxs-lookup"><span data-stu-id="3d658-153">Select **New Full-Text Stoplist**.</span></span>  
  
5.  <span data-ttu-id="3d658-154">Especifique el nombre de la lista de palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="3d658-154">Specify the stoplist name.</span></span>  
  
6.  <span data-ttu-id="3d658-155">Opcionalmente, especifique a otra persona como propietario de la lista de palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="3d658-155">Optionally, specify someone else as the stoplist owner.</span></span>  
  
7.  <span data-ttu-id="3d658-156">Seleccione una de las opciones de creación de lista de palabras irrelevantes siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d658-156">Select one of the following create stoplist options:</span></span>  
  
    -   <span data-ttu-id="3d658-157">**Crear una lista de palabras irrelevantes vacía**</span><span class="sxs-lookup"><span data-stu-id="3d658-157">**Create an empty stoplist**</span></span>  
  
    -   <span data-ttu-id="3d658-158">**Crear a partir de la lista de palabras irrelevantes del sistema**</span><span class="sxs-lookup"><span data-stu-id="3d658-158">**Create from the system stoplist**</span></span>  
  
    -   <span data-ttu-id="3d658-159">**Crear a partir de una lista de palabras irrelevantes de texto completo existente**</span><span class="sxs-lookup"><span data-stu-id="3d658-159">**Create from an existing full-text stoplist**</span></span>  
  
     <span data-ttu-id="3d658-160">Para obtener más información, vea [Nueva lista de palabras irrelevantes de texto completo &#40;página General&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="3d658-160">For more information, see [New Full-Text Stoplist &#40;General Page&#41;](../../integration-services/general-page-of-integration-services-designers-options.md).</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="3d658-161">**Para quitar una lista de palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="3d658-161">**To drop a stoplist**</span></span>  
  
-   [<span data-ttu-id="3d658-162">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d658-162">DROP FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-fulltext-stoplist-transact-sql)  
  
  
##  <a name="using-a-stoplist-in-full-text-queries"></a><a name="queries"></a><span data-ttu-id="3d658-163">Usar una lista de palabras irrelevantes en consultas de texto completo</span><span class="sxs-lookup"><span data-stu-id="3d658-163">Using a Stoplist in Full-Text Queries</span></span>  
 <span data-ttu-id="3d658-164">Para usar una lista de palabras irrelevantes en consultas, es necesario asociarla a un índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="3d658-164">To make use of a stoplist in queries, you must associate it with a full-text index.</span></span> <span data-ttu-id="3d658-165">Puede asociar una lista de palabras irrelevantes a un índice de texto completo en el momento de crear el índice, o puede modificar el índice más adelante y agregarle una lista de palabras irrelevantes.</span><span class="sxs-lookup"><span data-stu-id="3d658-165">You can attach a stoplist to a full-text index when you create the index, or you can alter the index later to add a stoplist.</span></span>  
  
 <span data-ttu-id="3d658-166">**Para crear un índice de texto completo y asociarle una lista de palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="3d658-166">**To create a full-text index and associate a stoplist with it**</span></span>  
  
-   [<span data-ttu-id="3d658-167">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d658-167">CREATE FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-fulltext-index-transact-sql)  
  
 <span data-ttu-id="3d658-168">**Para asociar o desasociar una lista de palabras irrelevantes y un índice de texto completo existente**</span><span class="sxs-lookup"><span data-stu-id="3d658-168">**To associate or disassociate a stoplist with an existing full-text index**</span></span>  
  
-   [<span data-ttu-id="3d658-169">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d658-169">ALTER FULLTEXT INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-index-transact-sql)  
  
 <span data-ttu-id="3d658-170">**Para suprimir un mensaje de error si las palabras irrelevantes causan error en una operación booleana en una consulta de texto completo**</span><span class="sxs-lookup"><span data-stu-id="3d658-170">**To suppress an error message if stopwords cause a Boolean operation on a full-text query to fail**</span></span>  
  
-   [<span data-ttu-id="3d658-171">transform noise words (opción de configuración del servidor)</span><span class="sxs-lookup"><span data-stu-id="3d658-171">transform noise words Server Configuration Option</span></span>](../../database-engine/configure-windows/transform-noise-words-server-configuration-option.md)  
  
  
##  <a name="viewing-stoplists-and-stoplist-metadata"></a><a name="viewing"></a><span data-ttu-id="3d658-172">Ver metadatos de palabras irrelevantes y STOPLIST</span><span class="sxs-lookup"><span data-stu-id="3d658-172">Viewing Stoplists and Stoplist Metadata</span></span>  
 <span data-ttu-id="3d658-173">**Para ver todas las palabras de una lista de palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="3d658-173">**To view all the stopwords of a stoplist**</span></span>  
  
-   [<span data-ttu-id="3d658-174">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d658-174">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="3d658-175">**Para obtener información sobre todas las listas de palabras irrelevantes de la base de datos actual**</span><span class="sxs-lookup"><span data-stu-id="3d658-175">**To get information about all the stoplists in the current database**</span></span>  
  
-   [<span data-ttu-id="3d658-176">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d658-176">sys.fulltext_stoplists &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stoplists-transact-sql)  
  
-   [<span data-ttu-id="3d658-177">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d658-177">sys.fulltext_stopwords &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-fulltext-stopwords-transact-sql)  
  
 <span data-ttu-id="3d658-178">**Para ver el resultado de la tokenización de una combinación entre un separador de palabras, un diccionario de sinónimos y una lista de palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="3d658-178">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="3d658-179">Sys. dm_fts_parser &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d658-179">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="changing-the-stopwords-in-a-stoplist"></a><a name="change"></a><span data-ttu-id="3d658-180">Cambiar el palabras irrelevantes de una lista de palabras irrelevantes</span><span class="sxs-lookup"><span data-stu-id="3d658-180">Changing the Stopwords in a Stoplist</span></span>  
 <span data-ttu-id="3d658-181">**Para agregar o quitar palabras irrelevantes de una lista de palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="3d658-181">**To add or drop stopwords from a stoplist**</span></span>  
  
-   [<span data-ttu-id="3d658-182">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3d658-182">ALTER FULLTEXT STOPLIST &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-fulltext-stoplist-transact-sql)  
  
#### <a name="to-change-the-stopwords-in-a-stoplist-in-management-studio"></a><span data-ttu-id="3d658-183">Para cambiar las palabras irrelevantes de una lista de palabras irrelevantes en Management Studio</span><span class="sxs-lookup"><span data-stu-id="3d658-183">To change the stopwords in a stoplist in Management Studio</span></span>  
  
1.  <span data-ttu-id="3d658-184">En el Explorador de objetos, expanda el servidor.</span><span class="sxs-lookup"><span data-stu-id="3d658-184">In Object Explorer, expand the server.</span></span>  
  
2.  <span data-ttu-id="3d658-185">Expanda **Bases de datos**y, a continuación, expanda la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3d658-185">Expand **Databases**, and then expand the database.</span></span>  
  
3.  <span data-ttu-id="3d658-186">Expanda **Almacenamiento** y, a continuación, seleccione **Listas de palabras irrelevantes de texto completo**.</span><span class="sxs-lookup"><span data-stu-id="3d658-186">Expand **Storage**, and then select **Full Text Stoplists**.</span></span>  
  
4.  <span data-ttu-id="3d658-187">Haga clic con el botón derecho en la lista de palabras irrelevantes cuyas propiedades quiere cambiar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3d658-187">Right-click the stoplist whose properties you want to change, and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="3d658-188">En el cuadro de diálogo [Propiedades de lista de palabras irrelevantes de texto completo](../../database-engine/full-text-stoplist-properties.md) :</span><span class="sxs-lookup"><span data-stu-id="3d658-188">In the [Full-Text Stoplist Properties](../../database-engine/full-text-stoplist-properties.md) dialog box:</span></span>  
  
    1.  <span data-ttu-id="3d658-189">En el cuadro de lista **Acción** , seleccione una las acciones siguientes: **Agregar palabra irrelevante**, **Eliminar palabra irrelevante**, **Eliminar todas las palabras irrelevantes**o **Borrar lista de palabras irrelevantes**.</span><span class="sxs-lookup"><span data-stu-id="3d658-189">In the **Action** list box, select one of the following actions: **Add stopword**, **Delete stopword**, **Delete all stopwords**, or **Clear stoplist**.</span></span>  
  
    2.  <span data-ttu-id="3d658-190">Si el cuadro de texto **Palabra irrelevante** está habilitado para la acción seleccionada, escriba una única palabra irrelevante.</span><span class="sxs-lookup"><span data-stu-id="3d658-190">If the **Stopword** text box is enabled for the selected action, enter a single stopword.</span></span> <span data-ttu-id="3d658-191">Esta palabra irrelevante debe ser única; es decir, no debe estar todavía en esta lista de palabras irrelevantes para el idioma que seleccione.</span><span class="sxs-lookup"><span data-stu-id="3d658-191">This stopword must be unique; that is, not yet in this stoplist for the language that you select.</span></span>  
  
    3.  <span data-ttu-id="3d658-192">Si el cuadro de lista **Idioma de texto completo** está habilitado para la acción seleccionada, seleccione un idioma.</span><span class="sxs-lookup"><span data-stu-id="3d658-192">If the **Full-text language** list box is enabled for the selected action, select a language.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
##  <a name="upgrading-noise-words-from-sql-server-2005"></a><a name="upgrade"></a><span data-ttu-id="3d658-193">Actualización de palabras irrelevantes desde SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="3d658-193">Upgrading Noise Words from SQL Server 2005</span></span>  
 [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] <span data-ttu-id="3d658-194">.</span><span class="sxs-lookup"><span data-stu-id="3d658-194">noise words have been replaced by stopwords.</span></span> <span data-ttu-id="3d658-195">Cuando una base de datos se actualiza desde [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], los archivos de palabras irrelevantes de esa versión dejan de usarse.</span><span class="sxs-lookup"><span data-stu-id="3d658-195">When a database is upgraded from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the noise-word files are no longer used.</span></span> <span data-ttu-id="3d658-196">Sin embargo, los archivos de palabras irrelevantes están almacenados en la carpeta FTDATA\ FTNoiseThesaurusBak y se pueden usar posteriormente al actualizar o compilar las listas de palabras irrelevantes correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3d658-196">However, the noise-word files are stored in the FTDATA\ FTNoiseThesaurusBak folder, and you can use them later when updating or building the corresponding stoplists.</span></span> <span data-ttu-id="3d658-197">Para obtener información sobre cómo actualizar los archivos de palabras irrelevantes a listas de palabras irrelevantes, vea [Actualizar la búsqueda de texto completo](upgrade-full-text-search.md).</span><span class="sxs-lookup"><span data-stu-id="3d658-197">For information about upgrading noise-word files to stoplists, see [Upgrade Full-Text Search](upgrade-full-text-search.md).</span></span>  
  
  
  
