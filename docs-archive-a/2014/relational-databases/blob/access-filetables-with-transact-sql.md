---
title: Obtener acceso a FileTables con Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], accessing files with T-SQL
ms.assetid: 3c4a5ffb-c521-4696-99cb-2b03cffc9c02
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2c47751ef34747e1b3742accf5040846ecde074f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748132"
---
# <a name="access-filetables-with-transact-sql"></a><span data-ttu-id="24c5b-102">Obtener acceso a FileTables con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="24c5b-102">Access FileTables with Transact-SQL</span></span>
  <span data-ttu-id="24c5b-103">Describe el funcionamiento de los comandos del lenguaje de manipulación de datos (DML) de [!INCLUDE[tsql](../../includes/tsql-md.md)] con FileTables.</span><span class="sxs-lookup"><span data-stu-id="24c5b-103">Describes how [!INCLUDE[tsql](../../includes/tsql-md.md)] data manipulation language (DML) commands work with FileTables.</span></span>  
  
##  <a name="insert-operations-on-filetables"></a><a name="BasicsInsert"></a> <span data-ttu-id="24c5b-104">Operaciones INSERT en FileTables</span><span class="sxs-lookup"><span data-stu-id="24c5b-104">INSERT Operations on FileTables</span></span>  
 <span data-ttu-id="24c5b-105">Las consideraciones siguientes se aplican a las operaciones **INSERT** en FileTables:</span><span class="sxs-lookup"><span data-stu-id="24c5b-105">The following considerations apply to **INSERT** Operations on FileTables:</span></span>  
  
-   <span data-ttu-id="24c5b-106">Todas las columnas de atributos de archivo tienen restricciones NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="24c5b-106">All the file attribute columns have NOT NULL constraints.</span></span> <span data-ttu-id="24c5b-107">Si los valores no se establecen de forma explícita, se proporcionan los valores predeterminados adecuados.</span><span class="sxs-lookup"><span data-stu-id="24c5b-107">If values are not explicitly set, then appropriate default values are supplied.</span></span>  
  
-   <span data-ttu-id="24c5b-108">Se aplican las restricciones definidas por el sistema si la instrucción INSERT establece los atributos **name**, **path_locator**, **parent_path_locator** o file.</span><span class="sxs-lookup"><span data-stu-id="24c5b-108">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="24c5b-109">La aplicación puede obtener el valor de **path_locator** de un archivo o un directorio si proporciona la ruta de acceso al sistema de archivos a la función [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="24c5b-109">The application can obtain the **path_locator** for a file or directory by providing the file system path to the [GetPathLocator &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/getpathlocator-transact-sql) function.</span></span>  
  
##  <a name="update-operations-on-filetables"></a><a name="BasicsUpdate"></a> <span data-ttu-id="24c5b-110">Operaciones UPDATE en FileTables</span><span class="sxs-lookup"><span data-stu-id="24c5b-110">UPDATE Operations on FileTables</span></span>  
 <span data-ttu-id="24c5b-111">Las consideraciones siguientes se aplican a las operaciones **UPDATE** en FileTables:</span><span class="sxs-lookup"><span data-stu-id="24c5b-111">The following considerations apply to **UPDATE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="24c5b-112">Se permiten actualizaciones en los datos definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="24c5b-112">Updates to any user-defined data are allowed.</span></span>  
  
-   <span data-ttu-id="24c5b-113">Se aplican las restricciones definidas por el sistema si la instrucción INSERT establece los atributos **name**, **path_locator**, **parent_path_locator** o file.</span><span class="sxs-lookup"><span data-stu-id="24c5b-113">System-defined constraints are enforced if the INSERT statement sets the **name**, **path_locator**, **parent_path_locator**, or file attributes.</span></span>  
  
-   <span data-ttu-id="24c5b-114">Las actualizaciones pueden realizarse en los datos FILESTREAM de la columna **file_stream** sin que se vea afectada ninguna de las demás columnas, incluidas las marcas de tiempo.</span><span class="sxs-lookup"><span data-stu-id="24c5b-114">Updates can be made to the FILESTREAM data in the **file_stream** column without affecting any of the other columns, including the timestamps.</span></span>  
  
##  <a name="delete-operations-on-filetables"></a><a name="BasicsDelete"></a> <span data-ttu-id="24c5b-115">Operaciones DELETE en FileTables</span><span class="sxs-lookup"><span data-stu-id="24c5b-115">DELETE Operations on FileTables</span></span>  
 <span data-ttu-id="24c5b-116">Las consideraciones siguientes se aplican a las operaciones **DELETE** en FileTables:</span><span class="sxs-lookup"><span data-stu-id="24c5b-116">The following considerations apply to **DELETE** operations on FileTables:</span></span>  
  
-   <span data-ttu-id="24c5b-117">Al eliminar una fila, también se quita el archivo o directorio correspondiente del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="24c5b-117">Deleting a row also removes the corresponding file or directory from the file system.</span></span>  
  
-   <span data-ttu-id="24c5b-118">Al eliminar una fila se produce un error si la fila corresponde a un directorio que contiene otros archivos o directorios.</span><span class="sxs-lookup"><span data-stu-id="24c5b-118">Deleting a row fails if the row corresponds to a directory that contains other files or directories.</span></span>  
  
##  <a name="constraints-that-are-enforced-for-dml-operations-on-filetables"></a><a name="BasicsConstraints"></a> <span data-ttu-id="24c5b-119">Restricciones que se aplican a operaciones DML en FileTables</span><span class="sxs-lookup"><span data-stu-id="24c5b-119">Constraints That Are Enforced for DML Operations on FileTables</span></span>  
 <span data-ttu-id="24c5b-120">Las restricciones definidas por el sistema garantizan que las acciones DML no comprometan la integridad de la jerarquía del espacio de nombres de archivo.</span><span class="sxs-lookup"><span data-stu-id="24c5b-120">System-defined constraints ensure that DML actions do not compromise the integrity of the file namespace hierarchy.</span></span> <span data-ttu-id="24c5b-121">Las restricciones que se aplican incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="24c5b-121">The constraints that are enforced include the following:</span></span>  
  
-   <span data-ttu-id="24c5b-122">Al establecer o cambiar el **nombre** del archivo o del directorio:</span><span class="sxs-lookup"><span data-stu-id="24c5b-122">When you set or change the **name** of the file or directory:</span></span>  
  
    -   <span data-ttu-id="24c5b-123">Se aplican las convenciones de nomenclatura de archivos y directorios de Windows.</span><span class="sxs-lookup"><span data-stu-id="24c5b-123">Windows file and directory naming conventions are enforced.</span></span>  
  
    -   <span data-ttu-id="24c5b-124">Se aplica la unicidad de nombres en el directorio primario.</span><span class="sxs-lookup"><span data-stu-id="24c5b-124">The uniqueness of the name in the parent directory is enforced.</span></span>  
  
-   <span data-ttu-id="24c5b-125">Al establecer o cambiar la ubicación de un archivo o un directorio mediante el establecimiento o el cambio de **path_locator** o **parent_path_locator**:</span><span class="sxs-lookup"><span data-stu-id="24c5b-125">When you set or change the location of a file or directory by setting or changing the **path_locator** or **parent_path_locator**:</span></span>  
  
    -   <span data-ttu-id="24c5b-126">Se aplica la unicidad.</span><span class="sxs-lookup"><span data-stu-id="24c5b-126">Uniqueness is enforced.</span></span>  
  
    -   <span data-ttu-id="24c5b-127">Se aplica la coherencia del árbol jerárquico de directorios y archivos, incluida la coherencia de los valores de **path_locator** y **parent_path_locator** .</span><span class="sxs-lookup"><span data-stu-id="24c5b-127">The consistency of the hierarchical tree of directories and files is enforced, including the consistency of **path_locator** and **parent_path_locator** values.</span></span>  
  
-   <span data-ttu-id="24c5b-128">El valor de **is_directory** no se puede establecer en true cuando la columna **file_stream** no es NULL.</span><span class="sxs-lookup"><span data-stu-id="24c5b-128">The value of **is_directory** cannot be set to true when the **file_stream** column is not null.</span></span> <span data-ttu-id="24c5b-129">Los datos de la columna **file_stream** indican que la fila representa un archivo y no un directorio.</span><span class="sxs-lookup"><span data-stu-id="24c5b-129">Data in the **file_stream** column indicates that the row represents a file and not a directory.</span></span>  
  
-   <span data-ttu-id="24c5b-130">Las columnas de atributos de archivo no pueden ser NULL.</span><span class="sxs-lookup"><span data-stu-id="24c5b-130">File attribute columns cannot be null.</span></span> <span data-ttu-id="24c5b-131">Las restricciones NOT NULL se aplican con valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="24c5b-131">NOT NULL constraints are enforced with default values.</span></span>  
  
-   <span data-ttu-id="24c5b-132">El valor de **last_access_time** no puede ser anterior a **last_write_time** y **creation_time**.</span><span class="sxs-lookup"><span data-stu-id="24c5b-132">The value of **last_access_time** cannot be earlier than **last_write_time** and **creation_time**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c5b-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="24c5b-133">See Also</span></span>  
 <span data-ttu-id="24c5b-134">[Cargar archivos en FileTables](load-files-into-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="24c5b-134">[Load Files into FileTables](load-files-into-filetables.md) </span></span>  
 <span data-ttu-id="24c5b-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span><span class="sxs-lookup"><span data-stu-id="24c5b-135">[Work with Directories and Paths in FileTables](work-with-directories-and-paths-in-filetables.md) </span></span>  
 <span data-ttu-id="24c5b-136">[Obtener acceso a FileTables con API de entrada-salida de archivo](access-filetables-with-file-input-output-apis.md) </span><span class="sxs-lookup"><span data-stu-id="24c5b-136">[Access FileTables with File Input-Output APIs](access-filetables-with-file-input-output-apis.md) </span></span>  
 [<span data-ttu-id="24c5b-137">DDL de FileTable, funciones, procedimientos almacenados y vistas</span><span class="sxs-lookup"><span data-stu-id="24c5b-137">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
