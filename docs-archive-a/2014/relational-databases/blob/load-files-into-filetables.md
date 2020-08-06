---
title: Carga de archivos en FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], migrating files
- FileTables [SQL Server], bulk loading
- FileTables [SQL Server], loading files
ms.assetid: dc842a10-0586-4b0f-9775-5ca0ecc761d9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 43ea31523da2dfa8b387f68ce4f7c7f07868dd6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749349"
---
# <a name="load-files-into-filetables"></a><span data-ttu-id="8ef70-102">Cargar archivos en FileTables</span><span class="sxs-lookup"><span data-stu-id="8ef70-102">Load Files into FileTables</span></span>
  <span data-ttu-id="8ef70-103">Describe cómo se cargan o migran archivos en las FileTables.</span><span class="sxs-lookup"><span data-stu-id="8ef70-103">Describes how to load or migrate files into FileTables.</span></span>  
  
##  <a name="loading-or-migrating-files-into-a-filetable"></a><a name="BasicsLoadNew"></a> <span data-ttu-id="8ef70-104">Cargar o migrar archivos en una FileTable</span><span class="sxs-lookup"><span data-stu-id="8ef70-104">Loading or Migrating Files into a FileTable</span></span>  
 <span data-ttu-id="8ef70-105">El método que elija para cargar o migrar archivos en una FileTable dependerá del lugar en el que estén almacenados actualmente los archivos.</span><span class="sxs-lookup"><span data-stu-id="8ef70-105">The method that you choose for loading or migrating files into a FileTable depends on where the files are currently stored.</span></span>  
  
|<span data-ttu-id="8ef70-106">Ubicación actual de los archivos</span><span class="sxs-lookup"><span data-stu-id="8ef70-106">Current location of files</span></span>|<span data-ttu-id="8ef70-107">Opciones de migración</span><span class="sxs-lookup"><span data-stu-id="8ef70-107">Options for migration</span></span>|  
|-------------------------------|---------------------------|  
|<span data-ttu-id="8ef70-108">Los archivos están almacenados actualmente en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="8ef70-108">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8ef70-109">no tiene información de los archivos.</span><span class="sxs-lookup"><span data-stu-id="8ef70-109">has no knowledge of the files.</span></span>|<span data-ttu-id="8ef70-110">Dado que una FileTable aparece como carpeta en el sistema de archivos de Windows, puede cargar archivos fácilmente en una nueva FileTable mediante cualquiera de los métodos disponibles para mover o copiar archivos.</span><span class="sxs-lookup"><span data-stu-id="8ef70-110">Since a FileTable appears as a folder in the Windows file system, you can easily load files into a new FileTable by using any of the available methods for moving or copying files.</span></span> <span data-ttu-id="8ef70-111">Estos métodos incluyen el Explorador de Windows, las opciones de la línea de comandos (incluidas xcopy y robocopy), así como aplicaciones o scripts personalizados.</span><span class="sxs-lookup"><span data-stu-id="8ef70-111">These methods include Windows Explorer, command line options including xcopy and robocopy, and custom scripts or applications.</span></span><br /><br /> <span data-ttu-id="8ef70-112">No puede convertir una carpeta existente en una FileTable.</span><span class="sxs-lookup"><span data-stu-id="8ef70-112">You cannot convert an existing folder to a FileTable.</span></span>|  
|<span data-ttu-id="8ef70-113">Los archivos están almacenados actualmente en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="8ef70-113">Files are currently stored in the file system.</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8ef70-114">incluye una tabla de metadatos que contiene punteros a los archivos.</span><span class="sxs-lookup"><span data-stu-id="8ef70-114">contains a table of metadata that contains pointers to the files.</span></span>|<span data-ttu-id="8ef70-115">El primer paso es mover o copiar los archivos mediante uno de los métodos mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8ef70-115">The first step is to move or copy the files by using one of the methods mentioned above.</span></span><br /><br /> <span data-ttu-id="8ef70-116">El segundo paso es actualizar la tabla de metadatos existente para que señale a la nueva ubicación de los archivos.</span><span class="sxs-lookup"><span data-stu-id="8ef70-116">The second step is to update the existing table of metadata to point to the new location of the files.</span></span><br /><br /> <span data-ttu-id="8ef70-117">Para obtener más información, vea [Migrar archivos desde el sistema de archivos a una FileTable](#HowToMigrateFiles) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="8ef70-117">For more information, see [Example: Migrating Files from the File System into a FileTable](#HowToMigrateFiles) in this topic.</span></span>|  
  
###  <a name="how-to-load-files-into-a-filetable"></a><a name="HowToLoadNew"></a> <span data-ttu-id="8ef70-118">Procedimientos para: cargar archivos en una FileTable</span><span class="sxs-lookup"><span data-stu-id="8ef70-118">How To: Load Files into a FileTable</span></span>  
 <span data-ttu-id="8ef70-119">Los métodos que puede usar para cargar archivos en una FileTable son:</span><span class="sxs-lookup"><span data-stu-id="8ef70-119">The methods that you can use to load files into a FileTable include the following:</span></span>  
  
-   <span data-ttu-id="8ef70-120">Arrastrar y colocar los archivos desde las carpetas de origen hasta la nueva carpeta de FileTable del Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="8ef70-120">Drag and drop files from the source folders to the new FileTable folder in Windows Explorer.</span></span>  
  
-   <span data-ttu-id="8ef70-121">Usar opciones de la línea de comando como MOVE, COPY, XCOPY o ROBOCOPY desde el símbolo del sistema o en un archivo o un script por lotes.</span><span class="sxs-lookup"><span data-stu-id="8ef70-121">Use command line options such as MOVE, COPY, XCOPY, or ROBOCOPY from the command prompt or in a batch file or script.</span></span>  
  
-   <span data-ttu-id="8ef70-122">Escribir una aplicación personalizada en C# o Visual Basic.NET que use los métodos del espacio de nombres **System.IO** para mover o copiar los archivos.</span><span class="sxs-lookup"><span data-stu-id="8ef70-122">Write a custom application in C# or Visual Basic.NET that uses methods from the **System.IO** namespace to move or copy the files.</span></span>  
  
###  <a name="example-migrating-files-from-the-file-system-into-a-filetable"></a><a name="HowToMigrateFiles"></a> <span data-ttu-id="8ef70-123">Ejemplo: Migrar archivos desde el sistema de archivos a una FileTable</span><span class="sxs-lookup"><span data-stu-id="8ef70-123">Example: Migrating Files from the File System into a FileTable</span></span>  
 <span data-ttu-id="8ef70-124">En este escenario, los archivos se almacenan en el sistema de archivos y dispone de una tabla de metadatos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que contiene punteros a los archivos.</span><span class="sxs-lookup"><span data-stu-id="8ef70-124">In this scenario, your files are stored in the file system, and you have a table of metadata in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that contains pointers to the files.</span></span> <span data-ttu-id="8ef70-125">Puede mover los archivos a una FileTable y reemplazar después la ruta de acceso UNC original de cada archivo de los metadatos por la ruta de acceso UNC de la FileTable.</span><span class="sxs-lookup"><span data-stu-id="8ef70-125">You want to move the files into a FileTable, and then replace the original UNC path for each file in the metadata with the FileTable UNC path.</span></span> <span data-ttu-id="8ef70-126">La función [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) sirve para lograr este propósito.</span><span class="sxs-lookup"><span data-stu-id="8ef70-126">The [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function helps you to achieve this goal.</span></span>  
  
 <span data-ttu-id="8ef70-127">En este ejemplo, suponga que hay una tabla de base de datos existente, `PhotoMetadata` , que contiene datos sobre fotografías.</span><span class="sxs-lookup"><span data-stu-id="8ef70-127">For this example, assume that there is an existing database table, `PhotoMetadata`, which contains data about photographs.</span></span> <span data-ttu-id="8ef70-128">Esta tabla tiene una columna `UNCPath` de tipo `varchar`(512) que contienen la ruta de acceso UNC real de un archivo .jpg.</span><span class="sxs-lookup"><span data-stu-id="8ef70-128">This table has a column `UNCPath` of type `varchar`(512) which contains the actual UNC path to a .jpg file.</span></span>  
  
 <span data-ttu-id="8ef70-129">Debe emprender las siguientes acciones para migrar los archivos de imagen desde el sistema de archivos a una FileTable:</span><span class="sxs-lookup"><span data-stu-id="8ef70-129">To migrate the image files from the file system into a FileTable, you have to do the following:</span></span>  
  
1.  <span data-ttu-id="8ef70-130">Cree una nueva FileTable para almacenar los archivos.</span><span class="sxs-lookup"><span data-stu-id="8ef70-130">Create a new FileTable to hold the files.</span></span> <span data-ttu-id="8ef70-131">En este ejemplo se usa el nombre de tabla, `dbo.PhotoTable`, pero no se muestra el código para crearla.</span><span class="sxs-lookup"><span data-stu-id="8ef70-131">This example uses the table name, `dbo.PhotoTable`, but does not show the code to create the table.</span></span>  
  
2.  <span data-ttu-id="8ef70-132">Usar xcopy o una herramienta similar para copiar los archivos .jpg, con su estructura de directorio, en el directorio raíz de la FileTable.</span><span class="sxs-lookup"><span data-stu-id="8ef70-132">Use xcopy or a similar tool to copy the .jpg files, with their directory structure, into the root directory of the FileTable.</span></span>  
  
3.  <span data-ttu-id="8ef70-133">Corregir los metadatos de la tabla `PhotoMetadata`, mediante el uso de código parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ef70-133">Fix the metadata in the `PhotoMetadata` table, by using code similar to the following:</span></span>  
  
```sql  
--  Add a path locator column to the PhotoMetadata table.  
ALTER TABLE PhotoMetadata ADD pathlocator hierarchyid;  
  
-- Get the root path of the Photo directory on the File Server.  
DECLARE @UNCPathRoot varchar(100) = '\\RemoteShare\Photographs';  
  
-- Get the root path of the FileTable.  
DECLARE @FileTableRoot varchar(1000);  
SELECT @FileTableRoot = FileTableRootPath('dbo.PhotoTable');  
  
-- Update the PhotoMetadata table.  
  
-- Replace the File Server UNC path with the FileTable path.  
UPDATE PhotoMetadata  
    SET UNCPath = REPLACE(UNCPath, @UNCPathRoot, @FileTableRoot);  
  
-- Update the pathlocator column to contain the pathlocator IDs from the FileTable.  
UPDATE PhotoMetadata  
    SET pathlocator = GetPathLocator(UNCPath);  
```  
  
##  <a name="bulk-loading-files-into-a-filetable"></a><a name="BasicsBulkLoad"></a> <span data-ttu-id="8ef70-134">Cargar de forma masiva archivos en una FileTable</span><span class="sxs-lookup"><span data-stu-id="8ef70-134">Bulk Loading Files into a FileTable</span></span>  
 <span data-ttu-id="8ef70-135">Una FileTable se comporta como una tabla normal en las operaciones masivas, con los requisitos siguientes.</span><span class="sxs-lookup"><span data-stu-id="8ef70-135">A FileTable behaves like a normal table for bulk operations, with the following qualifications.</span></span>  
  
 <span data-ttu-id="8ef70-136">Una FileTable tiene restricciones definidas por el sistema que garantizan que se mantiene la integridad del espacio de nombres de archivo o de directorio.</span><span class="sxs-lookup"><span data-stu-id="8ef70-136">A FileTable has system-defined constraints which ensure that the integrity of the file and directory namespace is maintained.</span></span> <span data-ttu-id="8ef70-137">Estas restricciones deben comprobarse en los datos cargados de forma masiva en la FileTable.</span><span class="sxs-lookup"><span data-stu-id="8ef70-137">These constraints have to be verified on the data bulk loaded into the FileTable.</span></span> <span data-ttu-id="8ef70-138">Como algunas operaciones de inserción masiva permiten omitir las restricciones de tabla, se aplicarán los siguientes requisitos.</span><span class="sxs-lookup"><span data-stu-id="8ef70-138">Since some bulk insert operations allow table constraints to be ignored, the following requirements are enforced.</span></span>  
  
-   <span data-ttu-id="8ef70-139">Las operaciones de carga masiva que aplican restricciones pueden ejecutarse en una FileTable exactamente igual que en cualquier otra tabla.</span><span class="sxs-lookup"><span data-stu-id="8ef70-139">Bulk loading operations that enforce constraints can be run against a FileTable as against any other table.</span></span> <span data-ttu-id="8ef70-140">Esta categoría incluye las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="8ef70-140">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="8ef70-141">bcp con la cláusula CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="8ef70-141">bcp with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="8ef70-142">BULK INSERT con la cláusula CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="8ef70-142">BULK INSERT with CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="8ef70-143">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) sin la cláusula IGNORE_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="8ef70-143">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) without IGNORE_CONSTRAINTS clause.</span></span>  
  
-   <span data-ttu-id="8ef70-144">Las operaciones de carga masiva que no aplican restricciones no se ejecutarán correctamente a menos que se deshabiliten las restricciones definidas por el sistema para la FileTable.</span><span class="sxs-lookup"><span data-stu-id="8ef70-144">Bulk loading operations that do not enforce constraints fail unless the FileTable system-defined constraints have been disabled.</span></span> <span data-ttu-id="8ef70-145">Esta categoría incluye las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="8ef70-145">This category includes the following operations:</span></span>  
  
    -   <span data-ttu-id="8ef70-146">bcp sin la cláusula CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="8ef70-146">bcp without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="8ef70-147">BULK INSERT sin la cláusula CHECK_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="8ef70-147">BULK INSERT without CHECK_CONSTRAINTS clause.</span></span>  
  
    -   <span data-ttu-id="8ef70-148">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) con la cláusula IGNORE_CONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="8ef70-148">INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...) with IGNORE_CONSTRAINTS clause.</span></span>  
  
###  <a name="how-to-bulk-load-files-into-a-filetable"></a><a name="HowToBulkLoad"></a> <span data-ttu-id="8ef70-149">Procedimientos para: cargar archivos de forma masiva en una FileTable</span><span class="sxs-lookup"><span data-stu-id="8ef70-149">How To: Bulk Load Files into a FileTable</span></span>  
 <span data-ttu-id="8ef70-150">Puede usar varios métodos para cargar de forma masiva archivos en una FileTable:</span><span class="sxs-lookup"><span data-stu-id="8ef70-150">You can use various methods to bulk load files into a FileTable:</span></span>  
  
-   <span data-ttu-id="8ef70-151">**bcp**</span><span class="sxs-lookup"><span data-stu-id="8ef70-151">**bcp**</span></span>  
  
    -   <span data-ttu-id="8ef70-152">Se llama con la cláusula **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="8ef70-152">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="8ef70-153">Se deshabilita el espacio de nombres de FileTable y se llama sin la cláusula **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="8ef70-153">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="8ef70-154">A continuación, se vuelve a habilitar el espacio de nombres de la FileTable.</span><span class="sxs-lookup"><span data-stu-id="8ef70-154">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="8ef70-155">**BULK INSERT**</span><span class="sxs-lookup"><span data-stu-id="8ef70-155">**BULK INSERT**</span></span>  
  
    -   <span data-ttu-id="8ef70-156">Se llama con la cláusula **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="8ef70-156">Call with the **CHECK_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="8ef70-157">Se deshabilita el espacio de nombres de FileTable y se llama sin la cláusula **CHECK_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="8ef70-157">Disable the FileTable namespace and call without the **CHECK_CONSTRAINTS** clause.</span></span> <span data-ttu-id="8ef70-158">A continuación, se vuelve a habilitar el espacio de nombres de la FileTable.</span><span class="sxs-lookup"><span data-stu-id="8ef70-158">Then re-enable the FileTable namespace.</span></span>  
  
-   <span data-ttu-id="8ef70-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...)**</span><span class="sxs-lookup"><span data-stu-id="8ef70-159">**INSERT INTO ... SELECT \* FROM OPENROWSET(BULK ...)**</span></span>  
  
    -   <span data-ttu-id="8ef70-160">Se llama con la cláusula **IGNORE_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="8ef70-160">Call with the **IGNORE_CONSTRAINTS** clause.</span></span>  
  
    -   <span data-ttu-id="8ef70-161">Se deshabilita el espacio de nombres de FileTable y se llama sin la cláusula **IGNORE_CONSTRAINTS** .</span><span class="sxs-lookup"><span data-stu-id="8ef70-161">Disable the FileTable namespace and call without the **IGNORE_CONSTRAINTS** clause.</span></span> <span data-ttu-id="8ef70-162">A continuación, se vuelve a habilitar el espacio de nombres de la FileTable.</span><span class="sxs-lookup"><span data-stu-id="8ef70-162">Then re-enable the FileTable namespace.</span></span>  
  
 <span data-ttu-id="8ef70-163">Para obtener más información sobre cómo deshabilitar las restricciones de FileTable, vea [Administrar FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="8ef70-163">For information about disabling the FileTable constraints, see [Manage FileTables](manage-filetables.md).</span></span>  
  
###  <a name="how-to-disable-filetable-constraints-for-bulk-loading"></a><a name="disabling"></a> <span data-ttu-id="8ef70-164">Procedimientos para: deshabilitar restricciones de FileTable para carga masiva</span><span class="sxs-lookup"><span data-stu-id="8ef70-164">How To: Disable FileTable Constraints for Bulk Loading</span></span>  
 <span data-ttu-id="8ef70-165">Para realizar la carga masiva de datos en una FileTable sin la sobrecarga que supone la aplicación de restricciones definidas por el sistema, puede deshabilitar temporalmente estas restricciones.</span><span class="sxs-lookup"><span data-stu-id="8ef70-165">To bulk load files into a FileTable without the overhead of enforcing the system-defined constraints, you can temporarily disable the constraints.</span></span> <span data-ttu-id="8ef70-166">Para obtener más información, vea [Administrar FileTables](manage-filetables.md).</span><span class="sxs-lookup"><span data-stu-id="8ef70-166">For more information, see [Manage FileTables](manage-filetables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef70-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ef70-167">See Also</span></span>  
 <span data-ttu-id="8ef70-168">[Obtener acceso a FileTables con Transact-SQL](access-filetables-with-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="8ef70-168">[Access FileTables with Transact-SQL](access-filetables-with-transact-sql.md) </span></span>  
 [<span data-ttu-id="8ef70-169">Obtener acceso a FileTables con API de entrada-salida de archivo</span><span class="sxs-lookup"><span data-stu-id="8ef70-169">Access FileTables with File Input-Output APIs</span></span>](access-filetables-with-file-input-output-apis.md)  
  
  
