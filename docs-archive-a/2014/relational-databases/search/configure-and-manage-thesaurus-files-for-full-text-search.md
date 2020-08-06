---
title: Configurar y administrar archivos de sinónimos para búsquedas de texto completo | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- full-text indexes [SQL Server], thesaurus files
- thesaurus [full-text search], configuring
- thesaurus [full-text search]
ms.assetid: 3ef96a63-8a52-45be-9a1f-265bff400e54
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67f0a5af7be4f41ce33692e5f28ad5adf676980c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752081"
---
# <a name="configure-and-manage-thesaurus-files-for-full-text-search"></a><span data-ttu-id="910d2-102">Configurar y administrar archivos de sinónimos para búsquedas de texto completo</span><span class="sxs-lookup"><span data-stu-id="910d2-102">Configure and Manage Thesaurus Files for Full-Text Search</span></span>
  <span data-ttu-id="910d2-103">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], las consultas de texto completo pueden buscar sinónimos de los términos especificados por el usuario usando un diccionario de sinónimos.</span><span class="sxs-lookup"><span data-stu-id="910d2-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], full-text queries can search for synonyms of user-specified terms through the use of a thesaurus.</span></span> <span data-ttu-id="910d2-104">Un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *de* define un conjunto de sinónimos para un idioma concreto.</span><span class="sxs-lookup"><span data-stu-id="910d2-104">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *thesaurus* defines a set of synonyms for a specific language.</span></span> <span data-ttu-id="910d2-105">Los administradores del sistema pueden definir dos formatos de sinónimos: conjuntos de expansión y conjuntos de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="910d2-105">System administrators can define two forms of synonyms: expansion sets and replacement sets.</span></span> <span data-ttu-id="910d2-106">Al desarrollar un diccionario de sinónimos personalizado para los datos de texto completo, puede ampliar de forma eficaz el ámbito de las consultas de texto completo en esos datos.</span><span class="sxs-lookup"><span data-stu-id="910d2-106">By developing a thesaurus tailored to your full-text data, you can effectively broaden the scope of full-text queries on that data.</span></span> <span data-ttu-id="910d2-107">La comprobación de coincidencia con el diccionario de sinónimos tiene lugar para todas las consultas [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) y [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) , y para las consultas [CONTAINS](/sql/t-sql/queries/contains-transact-sql) y [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) que especifican la cláusula FORMSOF THESAURUS.</span><span class="sxs-lookup"><span data-stu-id="910d2-107">Thesaurus matching occurs for all [FREETEXT](/sql/t-sql/queries/freetext-transact-sql) and [FREETEXTABLE](/sql/relational-databases/system-functions/freetexttable-transact-sql) queries and for any [CONTAINS](/sql/t-sql/queries/contains-transact-sql) and [CONTAINSTABLE](/sql/relational-databases/system-functions/containstable-transact-sql) queries that specify the FORMSOF THESAURUS clause.</span></span>  
  
##  <a name="basic-tasks-for-setting-up-a-thesaurus-file"></a><a name="tasks"></a><span data-ttu-id="910d2-108">Tareas básicas para configurar un archivo de sinónimos</span><span class="sxs-lookup"><span data-stu-id="910d2-108">Basic Tasks for Setting Up a Thesaurus File</span></span>  
 <span data-ttu-id="910d2-109">Para que las consultas de búsqueda de texto completo en la instancia de servidor puedan buscar sinónimos en un idioma determinado, debe definir las asignaciones del diccionario de sinónimos de ese idioma.</span><span class="sxs-lookup"><span data-stu-id="910d2-109">Before full-text search queries on your server instance can look for synonyms in a given language, you must define thesaurus mappings (synonyms) for that language.</span></span> <span data-ttu-id="910d2-110">Cada diccionario de sinónimos se debe configurar manualmente para definir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="910d2-110">Each thesaurus must be manually configured to define the following:</span></span>  
  
-   <span data-ttu-id="910d2-111">Configuración de signos diacríticos</span><span class="sxs-lookup"><span data-stu-id="910d2-111">Diacritics setting</span></span>  
  
     <span data-ttu-id="910d2-112">Para un diccionario de sinónimos determinado, todos los patrones de búsqueda son confidenciales o no distinguen entre marcas diacríticas como una tilde ( **~** ), acento agudo (**??**) o umlaut (**??**) (es decir, con *distinción de acentos* o sin *distinción de acentos*).</span><span class="sxs-lookup"><span data-stu-id="910d2-112">For a given thesaurus, all search patterns are either sensitive or insensitive to diacritical marks such as a tilde (**~**), acute accent mark (**??**), or umlaut (**??**) (that is, *accent sensitive* or *accent insensitive*).</span></span> <span data-ttu-id="910d2-113">Por ejemplo, supongamos que especifica el patrón "cafetería??".</span><span class="sxs-lookup"><span data-stu-id="910d2-113">For example, suppose you specify the pattern "caf??"</span></span> <span data-ttu-id="910d2-114">para que se reemplace por otros patrones en una consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="910d2-114">to be replaced by other patterns in a full-text query.</span></span> <span data-ttu-id="910d2-115">Si el Diccionario de sinónimos no distingue acentos, la búsqueda de texto completo reemplaza los patrones "cafetería??"</span><span class="sxs-lookup"><span data-stu-id="910d2-115">If the thesaurus is accent-insensitive, full-text search replaces the patterns "caf??"</span></span> <span data-ttu-id="910d2-116">y "cafe".</span><span class="sxs-lookup"><span data-stu-id="910d2-116">and "cafe".</span></span> <span data-ttu-id="910d2-117">Si el Diccionario de sinónimos distingue acentos, la búsqueda de texto completo solo reemplaza el patrón "cafetería??".</span><span class="sxs-lookup"><span data-stu-id="910d2-117">If the thesaurus is accent-sensitive, full-text search replaces only the pattern "caf??".</span></span> <span data-ttu-id="910d2-118">De forma predeterminada, un diccionario de sinónimos no distingue acentos.</span><span class="sxs-lookup"><span data-stu-id="910d2-118">By default, a thesaurus is accent-insensitive.</span></span>  
  
-   <span data-ttu-id="910d2-119">Conjunto de expansión</span><span class="sxs-lookup"><span data-stu-id="910d2-119">Expansion set</span></span>  
  
     <span data-ttu-id="910d2-120">Un conjunto de expansión contiene un grupo de sinónimos como "escritor", "autor" y "periodista" que se sustituyen entre si en una consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="910d2-120">An expansion set contains a group of synonyms such as "writer", "author", and "journalist" that are substituted for one another by a full-text query.</span></span> <span data-ttu-id="910d2-121">Las consultas que contienen una coincidencia para algún sinónimo en un conjunto de expansión se expanden para incluir uno de cada dos sinónimos en el conjunto de expansión.</span><span class="sxs-lookup"><span data-stu-id="910d2-121">Queries that contain a match for any synonym in an expansion set are expanded to include every other synonym in the expansion set.</span></span>  
  
     <span data-ttu-id="910d2-122">Para obtener más información, vea "Estructura XML de un conjunto de expansión", posteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="910d2-122">For more information, see "XML Structure of an Expansion Set," later in this topic.</span></span>  
  
-   <span data-ttu-id="910d2-123">Conjunto de reemplazo</span><span class="sxs-lookup"><span data-stu-id="910d2-123">Replacement set</span></span>  
  
     <span data-ttu-id="910d2-124">Un conjunto de reemplazo contiene un patrón de texto que se reemplazará por un conjunto de sustitución.</span><span class="sxs-lookup"><span data-stu-id="910d2-124">A replacement set contains a text pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="910d2-125">Para obtener un ejemplo, vea la sección "Estructura XML de un conjunto de reemplazo" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="910d2-125">For an example, see the section "XML Structure of a Replacement Set" later in this topic.</span></span>  
  
  
##  <a name="initial-content-of-the-thesaurus-files"></a><a name="initial_thesaurus_files"></a><span data-ttu-id="910d2-126">Contenido inicial de los archivos de sinónimos</span><span class="sxs-lookup"><span data-stu-id="910d2-126">Initial Content of the Thesaurus Files</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="910d2-127">proporciona un conjunto de archivos de sinónimos XML, uno para cada idioma admitido.</span><span class="sxs-lookup"><span data-stu-id="910d2-127">provides a set of XML thesaurus files, one for each supported language.</span></span> <span data-ttu-id="910d2-128">Estos archivos están esencialmente vacíos.</span><span class="sxs-lookup"><span data-stu-id="910d2-128">These files are essentially empty.</span></span> <span data-ttu-id="910d2-129">Contienen solo la estructura XML de nivel superior que es común a todos los diccionarios de sinónimos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y un diccionario de sinónimos de ejemplo como comentario.</span><span class="sxs-lookup"><span data-stu-id="910d2-129">They contain only the top-level XML structure that is common to all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] thesauruses and a commented-out sample thesaurus.</span></span>  
  
 <span data-ttu-id="910d2-130">Los archivos de sinónimos que se publican con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contienen el siguiente código XML:</span><span class="sxs-lookup"><span data-stu-id="910d2-130">The thesaurus files that are released with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] all contain the following XML code:</span></span>  
  
```  
<XML ID="Microsoft Search Thesaurus">  
  
<!--  Commented out  
  
    <thesaurus xmlns="x-schema:tsSchema.xml">  
<diacritics_sensitive>0</diacritics_sensitive>  
        <expansion>  
            <sub>Internet Explorer</sub>  
            <sub>IE</sub>  
            <sub>IE5</sub>  
        </expansion>  
        <replacement>  
            <pat>NT5</pat>  
            <pat>W2K</pat>  
            <sub>Windows 2012</sub>  
        </replacement>  
        <expansion>  
            <sub>run</sub>  
            <sub>jog</sub>  
        </expansion>  
    </thesaurus>  
-->  
</XML>  
```  
  
  
##  <a name="location-of-the-thesaurus-files"></a><a name="location"></a><span data-ttu-id="910d2-131">Ubicación de los archivos de sinónimos</span><span class="sxs-lookup"><span data-stu-id="910d2-131">Location of the Thesaurus Files</span></span>  
 <span data-ttu-id="910d2-132">La ubicación predeterminada de los archivos de sinónimos es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="910d2-132">The default location of the thesaurus files is:</span></span>  
  
 <span data-ttu-id="910d2-133">*<SQL_Server_data_files_path>* \MSSQL12. MSSQLSERVER\MSSQL\FTDATA</span><span class="sxs-lookup"><span data-stu-id="910d2-133">*<SQL_Server_data_files_path>* \MSSQL12.MSSQLSERVER\MSSQL\FTDATA</span></span>\  
  
 <span data-ttu-id="910d2-134">Esta ubicación predeterminada contiene los archivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="910d2-134">This default location contains the following files:</span></span>  
  
-   <span data-ttu-id="910d2-135">Archivos de sinónimos específicos del idioma</span><span class="sxs-lookup"><span data-stu-id="910d2-135">Language-specific thesaurus files</span></span>  
  
     <span data-ttu-id="910d2-136">Durante la instalación, los archivos de sinónimos vacíos se instalan en la ubicación anterior.</span><span class="sxs-lookup"><span data-stu-id="910d2-136">During setup, empty thesaurus files are installed in the above location.</span></span> <span data-ttu-id="910d2-137">Se proporciona un archivo independiente para cada idioma admitido.</span><span class="sxs-lookup"><span data-stu-id="910d2-137">A separate file is provided for each supported language.</span></span> <span data-ttu-id="910d2-138">Un administrador del sistema puede personalizar estos archivos.</span><span class="sxs-lookup"><span data-stu-id="910d2-138">A system administrator can customize these files.</span></span>  
  
     <span data-ttu-id="910d2-139">Los nombres de archivo predeterminados de los archivos de sinónimos usan el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="910d2-139">The default file names of the thesaurus files use following format:</span></span>  
  
     <span data-ttu-id="910d2-140">' ts ' + \<three-letter language-abbreviation> + '. xml '</span><span class="sxs-lookup"><span data-stu-id="910d2-140">'ts' + \<three-letter language-abbreviation> + '.xml'</span></span>  
  
     <span data-ttu-id="910d2-141">El nombre del archivo de diccionario de sinónimos para un idioma dado se especifica en el Registro en el valor siguiente: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<instance-name>\MSSearch\\<language-abbrev>.</span><span class="sxs-lookup"><span data-stu-id="910d2-141">The name of the thesaurus file for a given language is specified in the registry in the following value HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\<instance-name>\MSSearch\\<language-abbrev>.</span></span>  
  
-   <span data-ttu-id="910d2-142">El archivo de sinónimos global</span><span class="sxs-lookup"><span data-stu-id="910d2-142">The global thesaurus file</span></span>  
  
     <span data-ttu-id="910d2-143">Un archivo de sinónimos global y vacío, tsGlobal.xml.</span><span class="sxs-lookup"><span data-stu-id="910d2-143">An empty global thesaurus file, tsGlobal.xml.</span></span>  
  
 <span data-ttu-id="910d2-144">Puede cambiar la ubicación y los nombres de un archivo de sinónimos cambiando su clave del Registro.</span><span class="sxs-lookup"><span data-stu-id="910d2-144">You can change the location and names of a thesaurus file by changing its registry key.</span></span> <span data-ttu-id="910d2-145">Para cada idioma, la ubicación del archivo de sinónimos se especifica en el valor siguiente en el Registro:</span><span class="sxs-lookup"><span data-stu-id="910d2-145">For each language, the location of the thesaurus file is specified in the following value in the registry:</span></span>  
  
 <span data-ttu-id="910d2-146">HKLM/SOFTWARE/Microsoft/Microsoft SQL Server/ \<instance name> /MSSearch/Language/ \<language-abbreviation> /TsaurusFile</span><span class="sxs-lookup"><span data-stu-id="910d2-146">HKLM/SOFTWARE/Microsoft/Microsoft SQL Server/\<instance name>/MSSearch/Language/\<language-abbreviation>/TsaurusFile</span></span>  
  
 <span data-ttu-id="910d2-147">El archivo de sinónimos global corresponde al idioma neutro con el LCID 0.</span><span class="sxs-lookup"><span data-stu-id="910d2-147">The global thesaurus file corresponds to the Neutral language with LCID 0.</span></span> <span data-ttu-id="910d2-148">Solo los administradores pueden cambiar este valor.</span><span class="sxs-lookup"><span data-stu-id="910d2-148">This value can be changed by administrators only.</span></span>  
  
  
##  <a name="how-queries-use-thesaurus-files"></a><a name="how_queries_use_tf"></a><span data-ttu-id="910d2-149">Cómo usan los archivos de sinónimos las consultas</span><span class="sxs-lookup"><span data-stu-id="910d2-149">How Queries Use Thesaurus Files</span></span>  
 <span data-ttu-id="910d2-150">Una consulta del diccionario de sinónimos utiliza un diccionario de sinónimos específico del idioma y el diccionario de sinónimos global.</span><span class="sxs-lookup"><span data-stu-id="910d2-150">A thesaurus query uses both a language-specific thesaurus and the global thesaurus.</span></span> <span data-ttu-id="910d2-151">Primero, la consulta busca el archivo específico del idioma y lo carga para su procesamiento (a menos que ya esté cargado).</span><span class="sxs-lookup"><span data-stu-id="910d2-151">First, the query looks up the language-specific file and loads it for processing (unless it is already loaded).</span></span> <span data-ttu-id="910d2-152">La consulta se expande para incluir los sinónimos específicos del idioma especificados por las reglas de conjuntos de expansión y conjuntos de reemplazo en el archivo de diccionario de sinónimos.</span><span class="sxs-lookup"><span data-stu-id="910d2-152">The query is expanded to include the language-specific synonyms specified by the expansion set and replacement set rules in the thesaurus file.</span></span> <span data-ttu-id="910d2-153">Estos pasos se repiten después para el diccionario de sinónimos global.</span><span class="sxs-lookup"><span data-stu-id="910d2-153">These steps are then repeated for the global thesaurus.</span></span> <span data-ttu-id="910d2-154">Sin embargo, si un término ya forma parte de una coincidencia en el archivo de diccionario de sinónimos específico del idioma, el término es ilegible para coincidencias en el diccionario de sinónimos global.</span><span class="sxs-lookup"><span data-stu-id="910d2-154">However, if a term is already part of a match in the language specific thesaurus file, the term is ineligible for matching in the global thesaurus.</span></span>  
  
  
##  <a name="understanding-the-structure-of-a-thesaurus-file"></a><a name="structure"></a><span data-ttu-id="910d2-155">Descripción de la estructura de un archivo de Diccionario de sinónimos</span><span class="sxs-lookup"><span data-stu-id="910d2-155">Understanding the Structure of a Thesaurus File</span></span>  
 <span data-ttu-id="910d2-156">Cada archivo de sinónimos define un contenedor XML cuyo identificador es `Microsoft Search Thesaurus` y un comentario, `<!--` ... `-->`, que contiene un diccionario de sinónimos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="910d2-156">Each thesaurus file defines an XML container whose ID is `Microsoft Search Thesaurus`, and a comment, `<!--` ... `-->`, that contains a sample thesaurus.</span></span> <span data-ttu-id="910d2-157">El Diccionario de sinónimos se define en un \<thesaurus> elemento que contiene ejemplos de los elementos secundarios que definen la configuración de los signos diacríticos, los conjuntos de expansión y los conjuntos de reemplazo, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="910d2-157">The thesaurus is defined in a \<thesaurus> element that contains samples of the child elements that define the diacritics setting, expansion sets, and replacement sets, as follows:</span></span>  
  
-   <span data-ttu-id="910d2-158">Estructura XML de la configuración de signos diacríticos</span><span class="sxs-lookup"><span data-stu-id="910d2-158">XML Structure of the Diacritical Setting</span></span>  
  
     <span data-ttu-id="910d2-159">La configuración de signos diacríticos de un diccionario de sinónimos se especifica en un único elemento <diacritics_sensitive>.</span><span class="sxs-lookup"><span data-stu-id="910d2-159">The diacritics setting of a thesaurus is specified in a single <diacritics_sensitive> element.</span></span> <span data-ttu-id="910d2-160">Este elemento contiene un valor entero que controla la distinción de acentos, de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="910d2-160">This element contains an integer value that controls accent sensitivity, as follows:</span></span>  
  
    |<span data-ttu-id="910d2-161">Configuración de signos diacríticos</span><span class="sxs-lookup"><span data-stu-id="910d2-161">Diacritics Setting</span></span>|<span data-ttu-id="910d2-162">Value</span><span class="sxs-lookup"><span data-stu-id="910d2-162">Value</span></span>|<span data-ttu-id="910d2-163">XML</span><span class="sxs-lookup"><span data-stu-id="910d2-163">XML</span></span>|  
    |------------------------|-----------|---------|  
    |<span data-ttu-id="910d2-164">no distinguen acentos</span><span class="sxs-lookup"><span data-stu-id="910d2-164">Accent insensitive</span></span>|<span data-ttu-id="910d2-165">0</span><span class="sxs-lookup"><span data-stu-id="910d2-165">0</span></span>|`<diacritics_sensitive>0</diacritics_sensitive>`|  
    |<span data-ttu-id="910d2-166">distinguen acentos</span><span class="sxs-lookup"><span data-stu-id="910d2-166">Accent sensitive</span></span>|<span data-ttu-id="910d2-167">1</span><span class="sxs-lookup"><span data-stu-id="910d2-167">1</span></span>|`<diacritics_sensitive>1</diacritics_sensitive>`|  
  
    > [!NOTE]  
    >  <span data-ttu-id="910d2-168">Esta configuración solo se puede aplicar una vez en el archivo, y se aplica a todos los patrones de búsqueda del mismo.</span><span class="sxs-lookup"><span data-stu-id="910d2-168">This setting can only be applied one time in the file, and it applies to all search patterns in the file.</span></span> <span data-ttu-id="910d2-169">Esta configuración no se puede especificar para patrones individuales.</span><span class="sxs-lookup"><span data-stu-id="910d2-169">This setting cannot be specified for individual patterns.</span></span>  
  
-   <span data-ttu-id="910d2-170">Estructura XML de un conjunto de expansión</span><span class="sxs-lookup"><span data-stu-id="910d2-170">XML Structure of an Expansion Set</span></span>  
  
     <span data-ttu-id="910d2-171">Cada conjunto de expansión está delimitado por un elemento \<expansion>.</span><span class="sxs-lookup"><span data-stu-id="910d2-171">Each expansion set is enclosed within an \<expansion> element.</span></span> <span data-ttu-id="910d2-172">Dentro de este elemento, se especifican una o varias sustituciones en un elemento \<sub>.</span><span class="sxs-lookup"><span data-stu-id="910d2-172">Within this element, you specify one or more substitutions in a \<sub> element.</span></span> <span data-ttu-id="910d2-173">En el conjunto de expansión, puede especificar un grupo de sustituciones que sean sinónimas.</span><span class="sxs-lookup"><span data-stu-id="910d2-173">In the expansion set, you can specify a group of substitutions that are synonyms of each other.</span></span>  
  
     <span data-ttu-id="910d2-174">Por ejemplo, puede editar la sección de expansión para tratar las sustituciones "writer", "author" y "journalist" como sinónimos.</span><span class="sxs-lookup"><span data-stu-id="910d2-174">For example, you can edit the expansion section to treat the substitutions "writer", "author", and "journalist" as synonyms.</span></span> <span data-ttu-id="910d2-175">Las consultas de búsqueda de texto completo que contienen coincidencias en una sustitución se expanden para incluir todas las demás sustituciones especificadas en el conjunto de expansión.</span><span class="sxs-lookup"><span data-stu-id="910d2-175">full-text search queries that contain matches in one substitution are expanded to include all other substitutions specified in the expansion set.</span></span> <span data-ttu-id="910d2-176">Por tanto, en el ejemplo anterior, al emitir una consulta FORMS OF THESAURUS o FREETEXT para la palabra "autor", la búsqueda de texto completo también devuelve resultados que contienen las palabras "escritor" y "periodista".</span><span class="sxs-lookup"><span data-stu-id="910d2-176">Therefore, in the preceding example, when you issue a FORMS OF THESAURUS or a FREETEXT query for the word "author", full-text search also returns search results containing the words "writer" and "journalist".</span></span>  
  
     <span data-ttu-id="910d2-177">Esta es la apariencia que tendrá la sección del conjunto de expansión en el caso del ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="910d2-177">This is what the expansion set section would look like for the above example:</span></span>  
  
    ```  
    <expansion>  
            <sub>writer</sub>  
            <sub>author</sub>  
            <sub>journalist</sub>  
    </expansion>  
    ```  
  
-   <span data-ttu-id="910d2-178">Estructura XML de un conjunto de reemplazo</span><span class="sxs-lookup"><span data-stu-id="910d2-178">XML Structure of a Replacement Set</span></span>  
  
     <span data-ttu-id="910d2-179">Cada conjunto de reemplazo está delimitado por un elemento \<replacement>.</span><span class="sxs-lookup"><span data-stu-id="910d2-179">Each replacement set is enclosed within a \<replacement> element.</span></span> <span data-ttu-id="910d2-180">Dentro de este elemento, se pueden especificar uno o varios modelos en un elemento \<pat> y cero o más sustituciones en elementos \<sub>, una por cada sinónimo.</span><span class="sxs-lookup"><span data-stu-id="910d2-180">Within this element you can specify one or more patterns in a \<pat> element and zero or more substitutions in \<sub> elements, one per synonym.</span></span> <span data-ttu-id="910d2-181">Puede especificar un patrón para que sea reemplazado por un conjunto de sustitución.</span><span class="sxs-lookup"><span data-stu-id="910d2-181">You can specify a pattern to be replaced by a substitution set.</span></span> <span data-ttu-id="910d2-182">Los patrones y las sustituciones pueden contener una palabra o una secuencia de palabras.</span><span class="sxs-lookup"><span data-stu-id="910d2-182">Patterns and substitutions can contain a word, or a sequence of words.</span></span> <span data-ttu-id="910d2-183">Si no se especifica ninguna sustitución para un modelo, se quita el modelo de la consulta del usuario.</span><span class="sxs-lookup"><span data-stu-id="910d2-183">If there is no substitution specified for a pattern, it has the effect of removing the pattern from the user query.</span></span>  
  
     <span data-ttu-id="910d2-184">Por ejemplo, imagine que desea que las consultas de "Win8", el patrón, sean reemplazadas por "Windows Server 2012" o "Windows 8.0", las sustituciones.</span><span class="sxs-lookup"><span data-stu-id="910d2-184">For example, suppose you want queries for "Win8", the pattern, to be replaced by "Windows Server 2012" or "Windows 8.0", the substitutions.</span></span> <span data-ttu-id="910d2-185">Si ejecuta una búsqueda de texto completo de "Win8", solo devolverá los resultados que contengan "Windows Server 2012" o "Windows 8.0".</span><span class="sxs-lookup"><span data-stu-id="910d2-185">If you run a full-text query for "Win8", full-text search only returns search results containing "Windows Server 2012" or "Windows 8.0".</span></span> <span data-ttu-id="910d2-186">No devolverá resultados que contengan "Win8".</span><span class="sxs-lookup"><span data-stu-id="910d2-186">It does not return results containing "Win8".</span></span> <span data-ttu-id="910d2-187">Esto se debe a que el patrón "Win8" ha sido "reemplazado" por los patrones "Windows Server 2012" y "Windows 8.0".</span><span class="sxs-lookup"><span data-stu-id="910d2-187">This is because the pattern "Win8" has been "replaced" by the patterns "Windows Server 2012" and "Windows 8.0".</span></span>  
  
     <span data-ttu-id="910d2-188">Éste es el aspecto que tendrá la sección del conjunto de reemplazo en el caso del ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="910d2-188">This is what the replacement set section would look like for the above example:</span></span>  
  
    ```  
    <replacement>  
            <pat>Win8</pat>  
            <sub>Windows Server 2012</sub>  
            <sub>Windows 8.0</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="910d2-189">Si tiene dos conjuntos de reemplazo con patrones similares para los que se buscan coincidencias, prevalecerá el más largo de los dos.</span><span class="sxs-lookup"><span data-stu-id="910d2-189">If you have two replacement sets with similar patterns being matched, the longer of the two takes precedence.</span></span> <span data-ttu-id="910d2-190">Por ejemplo, si ejecuta una consulta FORMS OF THESAURUS para "Comunidad en línea de Internet Explorer" y tiene los siguientes conjuntos de reemplazo, el conjunto de reemplazo "Internet Explorer" tiene prioridad sobre el conjunto de reemplazo "Internet".</span><span class="sxs-lookup"><span data-stu-id="910d2-190">For example, if you run a FORMS OF THESAURUS query for "Internet Explorer online community" and you have the following replacement sets, the "Internet Explorer" replacement set takes precedence over the "Internet" replacement set.</span></span> <span data-ttu-id="910d2-191">Por tanto, la consulta se procesará como "Comunidad en línea de IE" o "Comunidad en línea de IE 9".</span><span class="sxs-lookup"><span data-stu-id="910d2-191">The query will therefore be processed as "IE online community" or "IE 9 online community".</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet</pat>  
             <sub>intranet</sub>  
    </replacement>  
    ```  
  
     <span data-ttu-id="910d2-192">y</span><span class="sxs-lookup"><span data-stu-id="910d2-192">and</span></span>  
  
    ```  
    <replacement>  
             <pat>Internet Explorer</pat>  
             <sub>IE</sub>  
             <sub>IE 9</sub>  
    </replacement>  
    ```  
  
  
##  <a name="working-with-thesaurus-files"></a><a name="working_with_thesaurus_files"></a><span data-ttu-id="910d2-193">Trabajar con archivos de sinónimos</span><span class="sxs-lookup"><span data-stu-id="910d2-193">Working with Thesaurus Files</span></span>  
 <span data-ttu-id="910d2-194">**Modificar un archivo de sinónimos**</span><span class="sxs-lookup"><span data-stu-id="910d2-194">**To edit a thesaurus file**</span></span>  
  
-   [<span data-ttu-id="910d2-195">Editar un archivo de sinónimos</span><span class="sxs-lookup"><span data-stu-id="910d2-195">Editing a Thesaurus File</span></span>](#editing)  
  
 <span data-ttu-id="910d2-196">**Cargar un archivo de sinónimos actualizado**</span><span class="sxs-lookup"><span data-stu-id="910d2-196">**To load an updated thesaurus file**</span></span>  
  
-   [<span data-ttu-id="910d2-197">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="910d2-197">sp_fulltext_load_thesaurus_file &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql)  
  
 <span data-ttu-id="910d2-198">**Para ver el resultado de la tokenización de una combinación entre un separador de palabras, un diccionario de sinónimos y una lista de palabras irrelevantes**</span><span class="sxs-lookup"><span data-stu-id="910d2-198">**To view the tokenization result of a word breaker, thesaurus, and stoplist combination**</span></span>  
  
-   [<span data-ttu-id="910d2-199">Sys. dm_fts_parser &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="910d2-199">sys.dm_fts_parser &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-fts-parser-transact-sql)  
  
  
##  <a name="editing-a-thesaurus-file"></a><a name="editing"></a><span data-ttu-id="910d2-200">Editar un archivo de Diccionario de sinónimos</span><span class="sxs-lookup"><span data-stu-id="910d2-200">Editing a Thesaurus File</span></span>  
 <span data-ttu-id="910d2-201">El diccionario de sinónimos de un idioma determinado se puede configurar modificando su archivo de diccionario de sinónimos (un archivo XML).</span><span class="sxs-lookup"><span data-stu-id="910d2-201">The thesaurus for a given language can be configured by editing its thesaurus file (an XML file).</span></span> <span data-ttu-id="910d2-202">Durante la instalación, se instalan los archivos de Diccionario de sinónimos vacíos que contienen solo el \<xml> contenedor y un elemento de ejemplo comentado como comentario \<thesaurus> .</span><span class="sxs-lookup"><span data-stu-id="910d2-202">During setup, empty thesaurus files that contain only the \<xml> container and a commented-out sample \<thesaurus> element are installed.</span></span> <span data-ttu-id="910d2-203">Para que las consultas de búsqueda de texto completo que buscan sinónimos funcionen correctamente, debe crear un elemento real \<thesaurus> que defina un conjunto de sinónimos.</span><span class="sxs-lookup"><span data-stu-id="910d2-203">In order for full-text search queries that look for synonyms to work properly, you must create an actual \<thesaurus> element that defines a set of synonyms.</span></span> <span data-ttu-id="910d2-204">Puede definir dos formatos de sinónimos: conjuntos de expansión y conjuntos de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="910d2-204">You can define two forms of synonyms, expansion sets and replacement sets.</span></span>  
  
 <span data-ttu-id="910d2-205">**Restricciones de los archivos de diccionarios de sinónimos**</span><span class="sxs-lookup"><span data-stu-id="910d2-205">**Restrictions for thesaurus files**</span></span>  
  
 <span data-ttu-id="910d2-206">Las restricciones siguientes se aplican al modificar un archivo de diccionario de sinónimos:</span><span class="sxs-lookup"><span data-stu-id="910d2-206">The following restrictions apply to editing a thesaurus file:</span></span>  
  
-   <span data-ttu-id="910d2-207">Solo los administradores del sistema pueden actualizar, modificar o eliminar archivos de diccionarios de sinónimos.</span><span class="sxs-lookup"><span data-stu-id="910d2-207">Only system administrators can update, modify, or delete thesaurus files.</span></span>  
  
-   <span data-ttu-id="910d2-208">Al modificar archivos de diccionarios de sinónimos con herramientas de edición de texto, los archivos deben guardarse en formato Unicode y deben especificarse marcas de orden de bytes.</span><span class="sxs-lookup"><span data-stu-id="910d2-208">When editing thesaurus files using text editor tools, the files must be saved in Unicode format, and Byte Order Marks must be specified.</span></span>  
  
-   <span data-ttu-id="910d2-209">Las entradas del diccionario de sinónimos no pueden estar vacías ni tener separación de palabras en una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="910d2-209">Thesaurus entries cannot be empty or word break to an empty string.</span></span>  
  
-   <span data-ttu-id="910d2-210">Las frases del archivo de diccionario de sinónimos no deben tener más de 512 caracteres.</span><span class="sxs-lookup"><span data-stu-id="910d2-210">Phrases in the thesaurus file must be no longer than 512 characters.</span></span>  
  
-   <span data-ttu-id="910d2-211">Un diccionario de sinónimos no debe contener ninguna entrada duplicada entre las entradas \<sub> de los conjuntos de expansión y los elementos \<pat> de los conjuntos de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="910d2-211">A thesaurus must not contain any duplicate entries among the \<sub> entries of expansion sets and the \<pat> elements of replacement sets.</span></span>  
  
 <span data-ttu-id="910d2-212">**Recomendaciones para los archivos de diccionarios de sinónimos**</span><span class="sxs-lookup"><span data-stu-id="910d2-212">**Recommendations for thesaurus files**</span></span>  
  
 <span data-ttu-id="910d2-213">Se recomienda que las entradas del archivo de diccionario de sinónimos no contengan ningún carácter especial.</span><span class="sxs-lookup"><span data-stu-id="910d2-213">We recommend that entries in the thesaurus file contain no special characters.</span></span> <span data-ttu-id="910d2-214">Esto se debe a que los separadores de palabras demuestran comportamientos sutiles con respecto a los caracteres especiales.</span><span class="sxs-lookup"><span data-stu-id="910d2-214">This is because word breakers have subtle behaviors with respect to special characters.</span></span> <span data-ttu-id="910d2-215">Si una entrada del diccionario de sinónimos contiene algún carácter especial, los separadores de palabras que se usan en combinación con esa entrada pueden tener implicaciones sutiles de comportamiento en una consulta de texto completo.</span><span class="sxs-lookup"><span data-stu-id="910d2-215">If a thesaurus entry contains any special characters, word breakers used in combination with that entry can have subtle behavioral implications for a full-text query.</span></span>  
  
 <span data-ttu-id="910d2-216">Se recomienda que las entradas \<sub> no contengan palabras irrelevantes porque estas se omiten en el índice de texto completo.</span><span class="sxs-lookup"><span data-stu-id="910d2-216">We recommend that \<sub> entries contain no stopwords since stopwords are omitted from the full-text index.</span></span> <span data-ttu-id="910d2-217">Las consultas se expanden para incluir las entradas \<sub> de un archivo de diccionario de sinónimos y, si una entrada \<sub> contiene palabras irrelevantes, el tamaño de la consulta aumenta innecesariamente.</span><span class="sxs-lookup"><span data-stu-id="910d2-217">Queries are expanded to include the \<sub> entries from a thesaurus file, and if a \<sub> entry contains stopwords, query size increases unnecessarily.</span></span>  
  
#### <a name="to-edit-a-thesaurus-file"></a><span data-ttu-id="910d2-218">Modificar un archivo de sinónimos</span><span class="sxs-lookup"><span data-stu-id="910d2-218">To edit a thesaurus file</span></span>  
  
1.  <span data-ttu-id="910d2-219">Abra el archivo de diccionario de sinónimos en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="910d2-219">Open the thesaurus file in Notepad.</span></span>  
  
2.  <span data-ttu-id="910d2-220">Si va a modificar el archivo de sinónimos por primera vez, quite las siguientes líneas de comentarios del principio y el final del archivo, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="910d2-220">If you are editing the thesaurus file for the first time, remove the following comment lines at the beginning and end of the file, respectively:</span></span>  
  
    ```  
    <!--Commented out  
    -->  
    ```  
  
3.  <span data-ttu-id="910d2-221">Agregue, modifique o elimine un conjunto de reemplazo o un conjunto de expansión.</span><span class="sxs-lookup"><span data-stu-id="910d2-221">Add, modify, or delete a replacement set, or expansion set.</span></span>  
  
4.  <span data-ttu-id="910d2-222">Guarde el archivo y cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="910d2-222">Save the file and close Notepad.</span></span>  
  
5.  <span data-ttu-id="910d2-223">Use [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) para cargar el contenido del archivo de diccionario de sinónimos en tempdb, especificando el identificador local (LCID) que corresponde al idioma del archivo de diccionario de sinónimos.</span><span class="sxs-lookup"><span data-stu-id="910d2-223">Use [sp_fulltext_load_thesaurus_file](/sql/relational-databases/system-stored-procedures/sp-fulltext-load-thesaurus-file-transact-sql) to load the content of the thesaurus file into tempdb, specifying the local identifier (LCID) that corresponds to the language of the thesaurus file.</span></span> <span data-ttu-id="910d2-224">Por ejemplo, para el archivo de diccionario de sinónimos en inglés, tsenu.xml, el LCID correspondiente es 1033.</span><span class="sxs-lookup"><span data-stu-id="910d2-224">For example, for the English thesaurus file, tsenu.xml, the corresponding LCID is 1033.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    EXEC sys.sp_fulltext_load_thesaurus_file 1033;  
    GO  
    ```  
  
  
## <a name="see-also"></a><span data-ttu-id="910d2-225">Consulte también</span><span class="sxs-lookup"><span data-stu-id="910d2-225">See Also</span></span>  
 <span data-ttu-id="910d2-226">[CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="910d2-226">[CONTAINS &#40;Transact-SQL&#41;](/sql/t-sql/queries/contains-transact-sql) </span></span>  
 <span data-ttu-id="910d2-227">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="910d2-227">[CONTAINSTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/containstable-transact-sql) </span></span>  
 <span data-ttu-id="910d2-228">[FREETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/freetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="910d2-228">[FREETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/freetext-transact-sql) </span></span>  
 <span data-ttu-id="910d2-229">[FREETEXTTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="910d2-229">[FREETEXTTABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/freetexttable-transact-sql) </span></span>  
 [<span data-ttu-id="910d2-230">Búsqueda de texto completo</span><span class="sxs-lookup"><span data-stu-id="910d2-230">Full-Text Search</span></span>](full-text-search.md)  
  
  
