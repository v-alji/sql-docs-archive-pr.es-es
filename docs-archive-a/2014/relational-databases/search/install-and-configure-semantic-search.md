---
title: Instalar y configurar la búsqueda semántica | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
helpviewer_keywords:
- semantic search [SQL Server], installing
- semantic search [SQL Server], configuring
ms.assetid: 2cdd0568-7799-474b-82fb-65d79df3057c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8d95e0bb2adf3bacf7057b881ab2e85afd50feef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746854"
---
# <a name="install-and-configure-semantic-search"></a><span data-ttu-id="81e05-102">Instalar y configurar la búsqueda semántica</span><span class="sxs-lookup"><span data-stu-id="81e05-102">Install and Configure Semantic Search</span></span>
  <span data-ttu-id="81e05-103">Describe los requisitos previos de la búsqueda semántica estadística y cómo instalarlos o comprobarlos.</span><span class="sxs-lookup"><span data-stu-id="81e05-103">Describes the prerequisites for statistical semantic search and how to install or check them.</span></span>  
  
## <a name="installing-semantic-search"></a><span data-ttu-id="81e05-104">Instalar la búsqueda semántica</span><span class="sxs-lookup"><span data-stu-id="81e05-104">Installing Semantic Search</span></span>  
  
###  <a name="how-to-check-whether-semantic-search-is-installed"></a><a name="HowToCheckInstalled"></a><span data-ttu-id="81e05-105">Cómo: comprobar si la búsqueda semántica está instalada</span><span class="sxs-lookup"><span data-stu-id="81e05-105">How To: Check Whether Semantic Search Is Installed</span></span>  
 <span data-ttu-id="81e05-106">Consulte la propiedad **IsFullTextInstalled** de la función de metadatos [SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="81e05-106">Query the **IsFullTextInstalled** property of the [SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql) metadata function.</span></span>  
  
 <span data-ttu-id="81e05-107">Un valor devuelto de 1 indica que la búsqueda de texto completo y la búsqueda semántica están instaladas; un valor devuelto de 0 indica que no lo están.</span><span class="sxs-lookup"><span data-stu-id="81e05-107">A return value of 1 indicates that Full-Text Search and Semantic Search are installed; a return value of 0 indicates that they are not installed.</span></span>  
  
```sql  
SELECT SERVERPROPERTY('IsFullTextInstalled');  
GO  
```  
  
###  <a name="how-to-install-semantic-search"></a><a name="BasicsSemanticSearch"></a><span data-ttu-id="81e05-108">Cómo: instalar la búsqueda semántica</span><span class="sxs-lookup"><span data-stu-id="81e05-108">How To: Install Semantic Search</span></span>  
 <span data-ttu-id="81e05-109">Para instalar la búsqueda semántica, seleccione **Extracciones de texto completo y semánticas de búsqueda** en la página de **Características que se van a instalar** durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="81e05-109">To install Semantic Search, select **Full-Text and Semantic Extractions for Search** on the **Features to Install** page during setup.</span></span>  
  
 <span data-ttu-id="81e05-110">La búsqueda semántica estadística depende de la búsqueda de texto completo.</span><span class="sxs-lookup"><span data-stu-id="81e05-110">Statistical Semantic Search depends on Full-Text Search.</span></span> <span data-ttu-id="81e05-111">Estas dos características opcionales de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se instalan conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="81e05-111">These two optional features of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are installed together.</span></span>  
  
## <a name="installing-or-removing-the-semantic-language-statistics-database"></a><span data-ttu-id="81e05-112">Instalar o quitar la base de datos de estadísticas de lenguaje semántico</span><span class="sxs-lookup"><span data-stu-id="81e05-112">Installing or Removing the Semantic Language Statistics Database</span></span>  
 <span data-ttu-id="81e05-113">La búsqueda semántica tiene una dependencia externa adicional que se denomina base de datos de estadísticas semánticas de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="81e05-113">Semantic Search has an additional external dependency that is called the semantic language statistics database.</span></span> <span data-ttu-id="81e05-114">Esta base de datos contiene modelos estadísticos de idioma que requiere la búsqueda semántica.</span><span class="sxs-lookup"><span data-stu-id="81e05-114">This database contains the statistical language models required by semantic search.</span></span> <span data-ttu-id="81e05-115">Una sola base de datos de estadísticas semánticas de lenguaje contiene los modelos de idioma de todos los idiomas compatibles con la indización semántica.</span><span class="sxs-lookup"><span data-stu-id="81e05-115">A single semantic language statistics database contains the language models for all the languages that are supported for semantic indexing.</span></span>  
  
###  <a name="how-to-check-whether-the-semantic-language-statistics-database-is-installed"></a><a name="HowToCheckDatabase"></a><span data-ttu-id="81e05-116">Cómo: comprobar si la base de datos de Estadísticas de lenguaje semántico está instalada</span><span class="sxs-lookup"><span data-stu-id="81e05-116">How To: Check Whether the Semantic Language Statistics Database Is Installed</span></span>  
 <span data-ttu-id="81e05-117">Consulte la vista de catálogo [sys.fulltext_semantic_language_statistics_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-language-statistics-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="81e05-117">Query the catalog view [sys.fulltext_semantic_language_statistics_database &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-fulltext-semantic-language-statistics-database-transact-sql).</span></span>  
  
 <span data-ttu-id="81e05-118">Si la base de datos de estadísticas semánticas de lenguaje está instalada y registrada para la instancia, los resultados de la consulta contienen una sola fila de información acerca de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="81e05-118">If the semantic language statistics database is installed and registered for the instance, then the query results contain a single row of information about the database.</span></span>  
  
```vb  
SELECT * FROM sys.fulltext_semantic_language_statistics_database;  
GO  
```  
  
###  <a name="how-to-install-attach-and-register-the-semantic-language-statistics-database"></a><a name="HowToInstallModel"></a><span data-ttu-id="81e05-119">Cómo: instalar, adjuntar y registrar la base de datos de Estadísticas de lenguaje semántico</span><span class="sxs-lookup"><span data-stu-id="81e05-119">How To: Install, Attach, and Register the Semantic Language Statistics Database</span></span>  
 <span data-ttu-id="81e05-120">La base de datos de estadísticas de lenguaje semántico no se instala con el programa de instalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81e05-120">The semantic language statistics database is not installed by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] setup program.</span></span> <span data-ttu-id="81e05-121">Para configurar la base de datos de estadísticas semánticas de lenguaje como requisito previo para la indización semántica, haga las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="81e05-121">To set up the Semantic Language Statistics database as a prerequisite for semantic indexing, do the following tasks:</span></span>  
  
 <span data-ttu-id="81e05-122">**1. Instale la base de datos de estadísticas de lenguaje semántico.**</span><span class="sxs-lookup"><span data-stu-id="81e05-122">**1. Install the semantic language statistics database.**</span></span>  
 1.  <span data-ttu-id="81e05-123">Busque la base de datos semántica de estadísticas de idioma en el disco de instalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o descárguela de web.</span><span class="sxs-lookup"><span data-stu-id="81e05-123">Locate the semantic language statistics database on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation media or download it from the Web.</span></span>  
  
    -   <span data-ttu-id="81e05-124">Busque el paquete de Windows installer denominado **SemanticLanguageDatabase.msi** en el disco de instalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81e05-124">Locate the Windows installer package named **SemanticLanguageDatabase.msi** on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation media.</span></span> <span data-ttu-id="81e05-125">Busque la versión de 32 o 64 bits del paquete del instalador según el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="81e05-125">Locate the 32-bit or 64-bit version of the installer package depending on the target system.</span></span> <span data-ttu-id="81e05-126">El nombre de la carpeta contenedora identifica la versión de 32 o 64 bits del archivo. El nombre de archivo es el mismo para ambas versiones.</span><span class="sxs-lookup"><span data-stu-id="81e05-126">The name of the containing folder identifies the 32-bit or 64-bit version of the file; the file name itself is the same for both versions.</span></span>  
  
    -   <span data-ttu-id="81e05-127">Descargar el paquete del instalador de [Microsoft?? ¿¿SQL Server?? 2014 Estadísticas de lenguaje semántico](https://go.microsoft.com/fwlink/?LinkID=296743) página del [!INCLUDE[msCoName](../../../includes/msconame-md.md)] centro de descarga.</span><span class="sxs-lookup"><span data-stu-id="81e05-127">Download the installer package from the [Microsoft?? SQL Server?? 2014 Semantic Language Statistics](https://go.microsoft.com/fwlink/?LinkID=296743) page on the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Download Center.</span></span>  
  
2.  <span data-ttu-id="81e05-128">Ejecute el paquete de **SemanticLanguageDatabase.msi** Windows Installer para extraer la base de datos y el archivo de registro.</span><span class="sxs-lookup"><span data-stu-id="81e05-128">Run the **SemanticLanguageDatabase.msi** Windows installer package to extract the database and log file.</span></span>  
  
     <span data-ttu-id="81e05-129">También puede cambiar el directorio de destino.</span><span class="sxs-lookup"><span data-stu-id="81e05-129">You can optionally change the destination directory.</span></span> <span data-ttu-id="81e05-130">De forma predeterminada, el instalador extrae los archivos en una carpeta denominada **Base de datos de lenguaje semántico de Microsoft** en la carpeta Archivos de programa de 32 o de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="81e05-130">By default, the installer extracts the files to a folder named **Microsoft Semantic Language Database** in the 32-bit or 64-bit Program Files folder.</span></span> <span data-ttu-id="81e05-131">El archivo contiene MSI un archivo de base de datos y un archivo de registro comprimidos.</span><span class="sxs-lookup"><span data-stu-id="81e05-131">The MSI file contains a compressed database file and log file.</span></span>  
  
3.  <span data-ttu-id="81e05-132">Mueva el archivo de base de datos y el archivo de registro extraídos a una ubicación adecuada del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="81e05-132">Move the extracted database file and log file to a suitable location in the file system.</span></span>  
  
     <span data-ttu-id="81e05-133">Si deja los archivos en su ubicación predeterminada, no será posible extraer otra copia de la base de datos para otra instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81e05-133">If you leave the files in their default location, it will not be possible to extract another copy of the database for another instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="81e05-134">Cuando se extrae la base de datos de estadísticas semánticas de lenguaje, se asignan permisos restringidos al archivo de base de datos y al archivo de registro en la ubicación predeterminada del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="81e05-134">When the semantic language statistics database is extracted, restricted permissions are assigned to the database file and log file in the default location in the file system.</span></span> <span data-ttu-id="81e05-135">Como resultado, es posible que no tenga permiso para adjuntar la base de datos si la deja en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="81e05-135">As a result, you may not have permission to attach the database if you leave it in the default location.</span></span> <span data-ttu-id="81e05-136">Si se produce un error al intentar adjuntar la base de datos, mueva los archivos o compruebe y corrija los permisos del sistema de archivos según corresponda.</span><span class="sxs-lookup"><span data-stu-id="81e05-136">If an error is raised when you try to attach the database, move the files, or check and fix file system permissions as appropriate.</span></span>  
  
 <span data-ttu-id="81e05-137">**2. Adjunte la base de datos de estadísticas semánticas de lenguaje.**</span><span class="sxs-lookup"><span data-stu-id="81e05-137">**2. Attach the semantic language statistics database.**</span></span>  
 <span data-ttu-id="81e05-138">Adjunte la base de datos a la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] o puede llamar a [CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) con la sintaxis **FOR ATTACH**.</span><span class="sxs-lookup"><span data-stu-id="81e05-138">Attach the database to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] or by calling [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) with the **FOR ATTACH** syntax.</span></span> <span data-ttu-id="81e05-139">Para obtener más información, vea [Adjuntar y separar bases de datos &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="81e05-139">For more information, see [Database Detach and Attach &#40;SQL Server&#41;](../databases/database-detach-and-attach-sql-server.md).</span></span>  
  
 <span data-ttu-id="81e05-140">De forma predeterminada, el nombre de la base de datos es **semanticsdb**.</span><span class="sxs-lookup"><span data-stu-id="81e05-140">By default, the name of the database is **semanticsdb**.</span></span> <span data-ttu-id="81e05-141">También puede asignar a la base de datos un nombre distinto al adjuntarla.</span><span class="sxs-lookup"><span data-stu-id="81e05-141">You can optionally give the database a different name when you attach it.</span></span> <span data-ttu-id="81e05-142">Tiene que proporcionar este nombre al registrar la base de datos en el paso posterior.</span><span class="sxs-lookup"><span data-stu-id="81e05-142">You have to provide this name when you register the database in the subsequent step.</span></span>  
  
```sql  
CREATE DATABASE semanticsdb  
            ON ( FILENAME = 'C:\Microsoft Semantic Language Database\semanticsdb.mdf' )  
            LOG ON ( FILENAME = 'C:\Microsoft Semantic Language Database\semanticsdb_log.ldf' )  
            FOR ATTACH;  
GO  
```  
  
 <span data-ttu-id="81e05-143">En esta muestra de código se supone que la base de datos se ha movido desde su ubicación predeterminada a una nueva.</span><span class="sxs-lookup"><span data-stu-id="81e05-143">This code sample assumes that you have moved the database from its default location to a new location.</span></span>  
  
 <span data-ttu-id="81e05-144">**3. Registre la base de datos de estadísticas semánticas de lenguaje.**</span><span class="sxs-lookup"><span data-stu-id="81e05-144">**3. Register the semantic language statistics database.**</span></span>  
 <span data-ttu-id="81e05-145">Llame al procedimiento almacenado [sp_fulltext_semantic_register_language_statistics_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-register-language-statistics-db-transact-sql) y proporcione el nombre que asignó a la base de datos cuando la adjuntó.</span><span class="sxs-lookup"><span data-stu-id="81e05-145">Call the stored procedure [sp_fulltext_semantic_register_language_statistics_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-register-language-statistics-db-transact-sql) and provide the name that you gave to the database when you attached it.</span></span>  
  
```sql  
EXEC sp_fulltext_semantic_register_language_statistics_db @dbname = N'semanticsdb';  
GO  
```  
  
###  <a name="how-to-unregister-detach-and-remove-the-semantic-language-statistics-database"></a><a name="HowToUnregister"></a><span data-ttu-id="81e05-146">Cómo: anular el registro, desasociar y quitar la base de datos de Estadísticas de lenguaje semántico</span><span class="sxs-lookup"><span data-stu-id="81e05-146">How To: Unregister, Detach, and Remove the Semantic Language Statistics Database</span></span>  
 <span data-ttu-id="81e05-147">**Anular el registro de la base de datos de estadísticas semánticas de lenguaje.**</span><span class="sxs-lookup"><span data-stu-id="81e05-147">**Unregister the semantic language statistics database.**</span></span>  
 <span data-ttu-id="81e05-148">Llame al procedimiento almacenado [sp_fulltext_semantic_unregister_language_statistics_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-unregister-language-statistics-db-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="81e05-148">Call the stored procedure [sp_fulltext_semantic_unregister_language_statistics_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-fulltext-semantic-unregister-language-statistics-db-transact-sql).</span></span> <span data-ttu-id="81e05-149">No tiene que proporcionar el nombre de la base de datos ya que una instancia solo puede tener una base de datos de estadísticas semánticas de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="81e05-149">You do not have to provide the name of the database since an instance can have only one semantic language statistics database.</span></span>  
  
```sql  
EXEC sp_fulltext_semantic_unregister_language_statistics_db;  
GO  
```  
  
 <span data-ttu-id="81e05-150">**Desasocie la base de datos de estadísticas semánticas de lenguaje.**</span><span class="sxs-lookup"><span data-stu-id="81e05-150">**Detach the semantic language statistics database.**</span></span>  
 <span data-ttu-id="81e05-151">Llame al procedimiento almacenado [sp_detach_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql) y proporcione el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="81e05-151">Call the stored procedure [sp_detach_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql) and provide the name of the database.</span></span>  
  
```sql  
USE master;  
GO  
  
EXEC sp_detach_db @dbname = N'semanticsdb';  
GO  
```  
  
 <span data-ttu-id="81e05-152">**Quite la base de datos de estadísticas semánticas de lenguaje.**</span><span class="sxs-lookup"><span data-stu-id="81e05-152">**Remove the semantic language statistics database.**</span></span>  
 <span data-ttu-id="81e05-153">Después de cancelar el registro y de separar la base de datos, puede eliminar el archivo de base de datos.</span><span class="sxs-lookup"><span data-stu-id="81e05-153">After unregistering and detaching the database, you can simply delete the database file.</span></span> <span data-ttu-id="81e05-154">No existe ningún programa de desinstalación ni hay ninguna entrada en la opción **Programas y características** en el Panel de control.</span><span class="sxs-lookup"><span data-stu-id="81e05-154">There is no uninstall program and there is no entry in **Programs and Features** in the Control Panel.</span></span>  
  
###  <a name="requirements-and-restrictions-for-installing-and-removing-the-semantic-language-statistics-database"></a><a name="reqinstall"></a><span data-ttu-id="81e05-155">Requisitos y restricciones para instalar y quitar la base de datos de Estadísticas de lenguaje semántico</span><span class="sxs-lookup"><span data-stu-id="81e05-155">Requirements and Restrictions for Installing and Removing the Semantic Language Statistics Database</span></span>  
  
-   <span data-ttu-id="81e05-156">Solo puede adjuntar y registrar una base de datos de estadísticas de lenguaje semántico en una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="81e05-156">You can only attach and register one semantic language statistics database on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="81e05-157">Cada instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en un solo equipo requiere una copia física independiente de la base de datos de estadísticas semánticas de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="81e05-157">Each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on a single computer requires a separate physical copy of the semantic language statistics database.</span></span> <span data-ttu-id="81e05-158">Adjunte una copia en cada instancia.</span><span class="sxs-lookup"><span data-stu-id="81e05-158">Attach one copy to each instance.</span></span>  
  
-   <span data-ttu-id="81e05-159">No puede separar una base de datos de estadísticas semánticas de lenguaje válida y registrada, y reemplazarla por una base de datos arbitraria que tenga el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="81e05-159">You cannot detach a valid and registered semantic language statistics database and replace it with an arbitrary database that has the same name.</span></span> <span data-ttu-id="81e05-160">Si lo hace, se producirá un error de rellenado de índice activo o futuro.</span><span class="sxs-lookup"><span data-stu-id="81e05-160">Doing so will cause active or future index populations to fail.</span></span>  
  
-   <span data-ttu-id="81e05-161">La base de datos de estadísticas semánticas de lenguaje es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="81e05-161">The semantic language statistics database is read-only.</span></span> <span data-ttu-id="81e05-162">No puede personalizar esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="81e05-162">You cannot customize this database.</span></span> <span data-ttu-id="81e05-163">Si modifica el contenido de la base de datos de la manera que fuere, los resultados de las futuras indizaciones semánticas son indeterministas.</span><span class="sxs-lookup"><span data-stu-id="81e05-163">If you alter the content of the database in any way, the results for future semantic indexing are indeterministic.</span></span> <span data-ttu-id="81e05-164">Para restaurar estos datos a su estado original, puede quitar la base de datos modificada. Después puede descargar y adjuntar una nueva copia sin modificar de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="81e05-164">To restore the original state of this data, you can drop the altered database, and download and attach a new and unaltered copy of the database.</span></span>  
  
-   <span data-ttu-id="81e05-165">Es posible desasociar o quitar la base de datos de estadísticas semánticas de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="81e05-165">It is possible to detach or drop the semantic language statistics database.</span></span> <span data-ttu-id="81e05-166">Si hay alguna operación de indexación activa que tenga bloqueos de lectura en la base de datos, se producirá un error en la operación de desasociación o eliminación. Esto es coherente con el comportamiento existente.</span><span class="sxs-lookup"><span data-stu-id="81e05-166">If there are any active indexing operations that have read locks on the database, then the detach or drop operation will fail or time out. This is consistent with existing behavior.</span></span> <span data-ttu-id="81e05-167">Después de quitar la base de datos, se producirá un error en cualquier operación de indización semántica.</span><span class="sxs-lookup"><span data-stu-id="81e05-167">After the database is removed, semantic indexing operations will fail.</span></span>  
  
## <a name="installing-optional-support-for-newer-document-types"></a><span data-ttu-id="81e05-168">Instalar compatibilidad opcional para nuevos tipos de documento</span><span class="sxs-lookup"><span data-stu-id="81e05-168">Installing Optional Support for Newer Document Types</span></span>  
  
###  <a name="how-to-install-the-latest-filters-for-microsoft-office-and-other-microsoft-document-types"></a><a name="office"></a><span data-ttu-id="81e05-169">Cómo: instalar los filtros más recientes para Microsoft Office y otros tipos de documentos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="81e05-169">How to: Install the Latest Filters for Microsoft Office and other Microsoft Document Types</span></span>  
 <span data-ttu-id="81e05-170">Esta versión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instala los separadores de palabras y analizadores lingüísticos de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] más recientes, pero no instala los últimos filtros para los documentos de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office ni otros tipos de documento de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81e05-170">This release of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installs the latest [!INCLUDE[msCoName](../../../includes/msconame-md.md)] word breakers and stemmers, but does not install the latest filters for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office documents and other [!INCLUDE[msCoName](../../../includes/msconame-md.md)] document types.</span></span> <span data-ttu-id="81e05-171">Estos filtros son necesarios para indizar documentos creados con versiones recientes de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office y otras aplicaciones de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81e05-171">These filters are required for indexing documents created with recent versions of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office and other [!INCLUDE[msCoName](../../../includes/msconame-md.md)] applications.</span></span> <span data-ttu-id="81e05-172">Para descargar los filtros más recientes, vea [Paquetes de filtros de Microsoft Office 2010](https://www.microsoft.com/download/details.aspx?id=17062).</span><span class="sxs-lookup"><span data-stu-id="81e05-172">To download the latest filters, see [Microsoft Office 2010 Filter Packs](https://www.microsoft.com/download/details.aspx?id=17062).</span></span>  
  
  