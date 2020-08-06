---
title: Obtener acceso a datos FILESTREAM con Transact-SQL | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], Transact-SQL
ms.assetid: a6bf0ce7-7e5e-4a07-8917-ee526c9d0a05
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 06d395f1acc3723fc6b45fdfa08efbae354d8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747042"
---
# <a name="access-filestream-data-with-transact-sql"></a><span data-ttu-id="edc0b-102">Obtener acceso a datos FILESTREAM con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="edc0b-102">Access FILESTREAM Data with Transact-SQL</span></span>
  <span data-ttu-id="edc0b-103">En este tema se describe cómo utilizar las instrucciones INSERT, DELETE y UPDATE de [!INCLUDE[tsql](../../includes/tsql-md.md)] para administrar los datos de FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="edc0b-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT, UPDATE, and DELETE statements to manage FILESTREAM data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="edc0b-104">Los ejemplos de este tema requieren la tabla y la base de datos habilitada para FILESTREAM que se crean en [Crear una base de datos habilitada para FILESTREAM](create-a-filestream-enabled-database.md) y [Crear una tabla para almacenar datos FILESTREAM](create-a-table-for-storing-filestream-data.md).</span><span class="sxs-lookup"><span data-stu-id="edc0b-104">The examples in this topic require the FILESTREAM-enabled database and table that are created in [Create a FILESTREAM-Enabled Database](create-a-filestream-enabled-database.md) and [Create a Table for Storing FILESTREAM Data](create-a-table-for-storing-filestream-data.md).</span></span>  
  
##  <a name="inserting-a-row-that-contains-filestream-data"></a><a name="ins"></a> <span data-ttu-id="edc0b-105">Insertar una fila que contiene datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="edc0b-105">Inserting a Row That Contains FILESTREAM Data</span></span>  
 <span data-ttu-id="edc0b-106">Para agregar una fila a una tabla que admite datos FILESTREAM, use la instrucción de [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT.</span><span class="sxs-lookup"><span data-stu-id="edc0b-106">To add a row to a table that supports FILESTREAM data, use the [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span> <span data-ttu-id="edc0b-107">Al insertar datos en una columna FILESTREAM, se puede insertar NULL o un valor `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="edc0b-107">When you insert data into a FILESTREAM column, you can insert NULL or a `varbinary(max)` value.</span></span>  
  
### <a name="inserting-null"></a><span data-ttu-id="edc0b-108">Insertar NULL</span><span class="sxs-lookup"><span data-stu-id="edc0b-108">Inserting NULL</span></span>  
 <span data-ttu-id="edc0b-109">El ejemplo siguiente muestra la forma de utilizar el valor `NULL`.</span><span class="sxs-lookup"><span data-stu-id="edc0b-109">The following example shows how to insert `NULL`.</span></span> <span data-ttu-id="edc0b-110">Cuando el valor FILESTREAM es `NULL`, [!INCLUDE[ssDE](../../includes/ssde-md.md)] no crea un archivo en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="edc0b-110">When the FILESTREAM value is `NULL`, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not create a file in the file system.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertNULL](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertnull)]  
  
### <a name="inserting-a-zero-length-record"></a><span data-ttu-id="edc0b-111">Insertar un registro de longitud cero</span><span class="sxs-lookup"><span data-stu-id="edc0b-111">Inserting a Zero-Length Record</span></span>  
 <span data-ttu-id="edc0b-112">En el siguiente ejemplo se muestra cómo utilizar `INSERT` para crear un registro de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="edc0b-112">The following example shows how to use `INSERT` to create a zero-length record.</span></span> <span data-ttu-id="edc0b-113">Esto es útil cuando se desea obtener un identificador de archivo, pero el archivo se va a tratar con las API de Win32.</span><span class="sxs-lookup"><span data-stu-id="edc0b-113">This is useful for when you want to obtain a file handle, but will be manipulating the file by using Win32 APIs.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertZero](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertzero)]  
  
### <a name="creating-a-data-file"></a><span data-ttu-id="edc0b-114">Crear un archivo de datos</span><span class="sxs-lookup"><span data-stu-id="edc0b-114">Creating a Data File</span></span>  
 <span data-ttu-id="edc0b-115">En el siguiente ejemplo se muestra cómo utilizar `INSERT` para crear un archivo que contiene datos.</span><span class="sxs-lookup"><span data-stu-id="edc0b-115">The following example shows how to use `INSERT` to create a file that contains data.</span></span> <span data-ttu-id="edc0b-116">[!INCLUDE[ssDE](../../includes/ssde-md.md)] convierte la cadena `Seismic Data` en un valor `varbinary(max)` .</span><span class="sxs-lookup"><span data-stu-id="edc0b-116">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] converts the string `Seismic Data` to a `varbinary(max)` value.</span></span> <span data-ttu-id="edc0b-117">FILESTREAM crea el archivo de Windows si aún no existe. A continuación, los datos se agregan al archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="edc0b-117">FILESTREAM creates the Windows file if it does not already exist.The data is then added to the data file.</span></span>  
  
 [!code-sql[FILESTREAM#FS_InsertData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_insertdata)]  
  
 <span data-ttu-id="edc0b-118">Cuando selecciona todos los datos de la tabla `Archive`.`dbo.Records`</span><span class="sxs-lookup"><span data-stu-id="edc0b-118">When you select all data from the `Archive`.`dbo.Records`</span></span> <span data-ttu-id="edc0b-119">, los resultados son similares a los que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="edc0b-119">table, the results are similar to the results that are shown in the following table.</span></span> <span data-ttu-id="edc0b-120">Sin embargo, la columna `Id` contendrá GUID diferentes.</span><span class="sxs-lookup"><span data-stu-id="edc0b-120">However, the `Id` column will contain different GUIDs.</span></span>  
  
|<span data-ttu-id="edc0b-121">Identificador</span><span class="sxs-lookup"><span data-stu-id="edc0b-121">Id</span></span>|<span data-ttu-id="edc0b-122">SerialNumber</span><span class="sxs-lookup"><span data-stu-id="edc0b-122">SerialNumber</span></span>|<span data-ttu-id="edc0b-123">Reanudar</span><span class="sxs-lookup"><span data-stu-id="edc0b-123">Resume</span></span>|  
|--------|------------------|------------|  
|`C871B90F-D25E-47B3-A560-7CC0CA405DAC`|`1`|`NULL`|  
|`F8F5C314-0559-4927-8FA9-1535EE0BDF50`|`2`|`0x`|  
|`7F680840-B7A4-45D4-8CD5-527C44D35B3F`|`3`|`0x536569736D69632044617461`|  
  
##  <a name="updating-filestream-data"></a><a name="upd"></a> <span data-ttu-id="edc0b-124">Actualizar datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="edc0b-124">Updating FILESTREAM Data</span></span>  
 <span data-ttu-id="edc0b-125">Puede usar [!INCLUDE[tsql](../../includes/tsql-md.md)] para actualizar los datos del archivo del sistema de archivos; sin embargo, puede no ser conveniente si hay que transmitir grandes cantidades de datos a un archivo.</span><span class="sxs-lookup"><span data-stu-id="edc0b-125">You can use [!INCLUDE[tsql](../../includes/tsql-md.md)] to update the data in the file system file; although, you might not want to do this when you have to stream large amounts of data to a file.</span></span>  
  
 <span data-ttu-id="edc0b-126">En el ejemplo siguiente se reemplaza cualquier texto del registro del archivo por el texto `Xray 1`.</span><span class="sxs-lookup"><span data-stu-id="edc0b-126">The following example replaces any text in the file record with the text `Xray 1`.</span></span>  
  
 [!code-sql[FILESTREAM#FS_UpdateData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_updatedata)]  
  
##  <a name="deleting-filestream-data"></a><a name="del"></a> <span data-ttu-id="edc0b-127">Eliminar datos FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="edc0b-127">Deleting FILESTREAM Data</span></span>  
 <span data-ttu-id="edc0b-128">Al eliminar una fila que contiene un campo FILESTREAM, también elimina sus archivos de sistema de archivos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="edc0b-128">When you delete a row that contains a FILESTREAM field, you also delete its underlying file system files.</span></span> <span data-ttu-id="edc0b-129">La única manera de eliminar una fila y por consiguiente el archivo, es utilizar la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE.</span><span class="sxs-lookup"><span data-stu-id="edc0b-129">The only way to delete a row, and therefore the file, is to use the [!INCLUDE[tsql](../../includes/tsql-md.md)] DELETE statement.</span></span>  
  
 <span data-ttu-id="edc0b-130">El ejemplo siguiente muestra cómo eliminar una fila y sus archivos de sistema de archivo asociados.</span><span class="sxs-lookup"><span data-stu-id="edc0b-130">The following example shows how to delete a row and its associated file system files.</span></span>  
  
 [!code-sql[FILESTREAM#FS_DeleteData](../../snippets/tsql/SQL15/tsql/filestream/transact-sql/filestream.sql#fs_deletedata)]  
  
 <span data-ttu-id="edc0b-131">Al seleccionar todos los datos de la tabla `dbo.Archive` , la fila ya no está.</span><span class="sxs-lookup"><span data-stu-id="edc0b-131">When you select all data from the `dbo.Archive` table, the row is gone.</span></span> <span data-ttu-id="edc0b-132">Ya no puede utilizar el archivo asociado.</span><span class="sxs-lookup"><span data-stu-id="edc0b-132">You can no longer use the associated file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="edc0b-133">El recolector de elementos no utilizados de FILESTREAM quita los archivos subyacentes.</span><span class="sxs-lookup"><span data-stu-id="edc0b-133">The underlying files are removed by the FILESTREAM garbage collector.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edc0b-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="edc0b-134">See Also</span></span>  
 <span data-ttu-id="edc0b-135">[Habilitar y configurar FILESTREAM](enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="edc0b-135">[Enable and Configure FILESTREAM](enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="edc0b-136">Evitar conflictos con operaciones de base de datos en aplicaciones FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="edc0b-136">Avoid Conflicts with Database Operations in FILESTREAM Applications</span></span>](avoid-conflicts-with-database-operations-in-filestream-applications.md)  
  
  
