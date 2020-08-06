---
title: Administración de FileTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FileTables [SQL Server], security
- FileTables [SQL Server], managing access
ms.assetid: 93af982c-b4fe-4be0-8268-11f86dae27e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a15a914c243f1fafd3b913d98113e984bf533086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745821"
---
# <a name="manage-filetables"></a><span data-ttu-id="e02a6-102">Administrar FileTables</span><span class="sxs-lookup"><span data-stu-id="e02a6-102">Manage FileTables</span></span>
  <span data-ttu-id="e02a6-103">Describe las tareas administrativas comunes para administrar FileTables.</span><span class="sxs-lookup"><span data-stu-id="e02a6-103">Describes common administrative tasks for managing FileTables.</span></span>  
  
##  <a name="how-to-get-a-list-of-filetables-and-related-objects"></a><a name="HowToEnumerate"></a> <span data-ttu-id="e02a6-104">Procedimientos para: obtener una lista de FileTables y de objetos relacionados</span><span class="sxs-lookup"><span data-stu-id="e02a6-104">How To: Get a List of FileTables and Related Objects</span></span>  
 <span data-ttu-id="e02a6-105">Para obtener una lista de FileTables, consulte una de las siguientes vistas de catálogo:</span><span class="sxs-lookup"><span data-stu-id="e02a6-105">To get a list of FileTables, query one of the following catalog views:</span></span>  
  
-   [<span data-ttu-id="e02a6-106">sys.filetables &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e02a6-106">sys.filetables &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-filetables-transact-sql)  
  
-   <span data-ttu-id="e02a6-107">[sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (consultar el valor de la columna **is_filetable**).</span><span class="sxs-lookup"><span data-stu-id="e02a6-107">[sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql) (Check the value of the **is_filetable** column.)</span></span>  
  
```sql  
SELECT * FROM sys.filetables;  
GO  
  
SELECT * FROM sys.tables WHERE is_filetable = 1;  
GO  
```  
  
 <span data-ttu-id="e02a6-108">Para obtener una lista de los objetos definidos por el sistema que se crearon al mismo tiempo que las FileTables asociadas, vea la vista de catálogo [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e02a6-108">To get a list of the system-defined objects that were created when the associated FileTables were created, query the catalog view [sys.filetable_system_defined_objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-filetable-system-defined-objects-transact-sql).</span></span>  
  
```sql  
SELECT object_id, OBJECT_NAME(object_id) AS 'Object Name'  
    FROM sys.filetable_system_defined_objects  
    WHERE object_id = filetable_object_id;  
GO  
```  
  
##  <a name="disabling-and-re-enabling-non-transactional-access-at-the-database-level"></a><a name="BasicsDisabling"></a> <span data-ttu-id="e02a6-109">Deshabilitar o volver a habilitar el acceso no transaccional en el nivel de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e02a6-109">Disabling and Re-enabling Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="e02a6-110">Con el fin de adquirir el acceso exclusivo necesario para ciertas tareas administrativas, quizá deba deshabilitar el acceso no transaccional temporalmente.</span><span class="sxs-lookup"><span data-stu-id="e02a6-110">To acquire the exclusive access that is required for certain administrative tasks, you may have to disable non-transactional access temporarily.</span></span>  
  
 <span data-ttu-id="e02a6-111">**Comportamiento de la instrucción ALTER DATABASE cuando se cambia el nivel del acceso no transaccional**</span><span class="sxs-lookup"><span data-stu-id="e02a6-111">**Behavior of the ALTER DATABASE statement when changing the level of non-transactional access**</span></span>  
  
-   <span data-ttu-id="e02a6-112">Cuando se establece el acceso no transaccional en READ_ONLY u OFF, el comando ALTER DATABASE no devuelve el control al usuario si hay identificadores de archivos abiertos en conflicto con la operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="e02a6-112">When you set non-transactional access to READ_ONLY or OFF, the ALTER DATABASE command does not return control to the user as long as there are open file handles that conflict with the requested operation.</span></span> <span data-ttu-id="e02a6-113">Los identificadores de archivos que están en conflicto con esta operación incluyen:</span><span class="sxs-lookup"><span data-stu-id="e02a6-113">The file handles that conflict with this operation include the following:</span></span>  
  
    -   <span data-ttu-id="e02a6-114">Si está configurando el acceso en **NONE**, todos los identificadores de archivos abiertos.</span><span class="sxs-lookup"><span data-stu-id="e02a6-114">When you are setting access to **NONE**, all open file handles.</span></span>  
  
    -   <span data-ttu-id="e02a6-115">Si está estableciendo acceso en **READ_ONLY**, todos los identificadores de archivos abiertos para el acceso de escritura.</span><span class="sxs-lookup"><span data-stu-id="e02a6-115">When you are setting access to **READ_ONLY**, all file handles opened for write access.</span></span>  
  
     <span data-ttu-id="e02a6-116">Para obtener más información acerca de la eliminación de identificadores de archivos abiertos, vea la sección [Eliminar los identificadores de archivos abiertos asociados con FileTable](#BasicsKilling) de este tema.</span><span class="sxs-lookup"><span data-stu-id="e02a6-116">For information about killing open file handles, see [Killing Open File Handles Associated with a FileTable](#BasicsKilling) in this topic.</span></span>  
  
     <span data-ttu-id="e02a6-117">Si se cancela el comando ALTER DATABASE o finaliza con un tiempo de espera, no se cambia el nivel de acceso transaccional.</span><span class="sxs-lookup"><span data-stu-id="e02a6-117">If the ALTER DATABASE command is canceled or ends with a timeout, then the level of transactional access is not changed.</span></span>  
  
-   <span data-ttu-id="e02a6-118">Si llama a la instrucción ALTER DATABASE con una cláusula WITH \<termination> (ROLLBACK AFTER entero [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT), todos los identificadores de archivo no transaccionales abiertos se eliminan.</span><span class="sxs-lookup"><span data-stu-id="e02a6-118">If you call the ALTER DATABASE statement with a WITH \<termination> clause (ROLLBACK AFTER integer [ SECONDS ] | ROLLBACK IMMEDIATE | NO_WAIT), then all open non-transactional file handles are killed.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="e02a6-119">Eliminar los identificadores de archivos abiertos puede hacer que los usuarios pierdan los datos no guardados.</span><span class="sxs-lookup"><span data-stu-id="e02a6-119">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="e02a6-120">Este comportamiento es coherente con el comportamiento del propio sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="e02a6-120">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
 <span data-ttu-id="e02a6-121">**Efectos de deshabilitar el acceso no transaccional**</span><span class="sxs-lookup"><span data-stu-id="e02a6-121">**Effects of disabling non-transactional access**</span></span>  
  
 <span data-ttu-id="e02a6-122">La deshabilitación del acceso no transaccional tiene los siguientes efectos en la visibilidad de los directorios de FileTable del directorio de nivel de base de datos y al acceder a dichos directorios:</span><span class="sxs-lookup"><span data-stu-id="e02a6-122">Changing the level of non-transactional access at the database level has the following effects on the FileTable directories under the database-level directory:</span></span>  
  
-   <span data-ttu-id="e02a6-123">Cuando el acceso establece en **NONE**, entonces todos los directorios de FileTable y su contenido ha no son accesibles o visibles.</span><span class="sxs-lookup"><span data-stu-id="e02a6-123">When you set access to **NONE**, then all the FileTable directories and their contents are no longer accessible or visible.</span></span>  
  
-   <span data-ttu-id="e02a6-124">Cuando el acceso se establece en **READ_ONLY**, todos los directorios de FileTable y su contenido son también de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="e02a6-124">When you set access to **READ_ONLY**, then all the FileTable directories and their contents are also read-only.</span></span>  
  
 <span data-ttu-id="e02a6-125">Deshabilitar FILESTREAM en el nivel de instancia tiene los siguientes efectos de los directorios de nivel de base de datos en esa instancia, y en los directorios de FileTable incluidos en ellos:</span><span class="sxs-lookup"><span data-stu-id="e02a6-125">Disabling FILESTREAM at the instance level has the following effects on the database-level directories on that instance, and the FileTable directories under them:</span></span>  
  
-   <span data-ttu-id="e02a6-126">Ninguno de los directorios de nivel de base de datos de la instancia se ve si se deshabilita FILESTREAM en el nivel de instancia.</span><span class="sxs-lookup"><span data-stu-id="e02a6-126">None of the database-level directories on the instance are visible if FILESTREAM is disabled at the instance level.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-non-transactional-access-at-the-database-level"></a><a name="HowToDisable"></a> <span data-ttu-id="e02a6-127">Procedimientos para: deshabilitar o volver a habilitar el acceso no transaccional en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="e02a6-127">How To: Disable and Re-enable Non-Transactional Access at the Database Level</span></span>  
 <span data-ttu-id="e02a6-128">Para obtener más información, vea [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span><span class="sxs-lookup"><span data-stu-id="e02a6-128">For more information, see [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options).</span></span>  
  
 <span data-ttu-id="e02a6-129">**Para deshabilitar el acceso no transaccional total**</span><span class="sxs-lookup"><span data-stu-id="e02a6-129">**To disable full non-transactional access**</span></span>  
 <span data-ttu-id="e02a6-130">Llame a la instrucción **ALTER DATABASE** y establezca el valor de **NON_TRANSACTED_ACCESS** en **READ_ONLY** o en **OFF**.</span><span class="sxs-lookup"><span data-stu-id="e02a6-130">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **READ_ONLY** or **OFF**.</span></span>  
  
```sql  
-- Disable write access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = READ_ONLY );  
GO  
  
-- Disable non-transactional access.  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = OFF );  
GO  
```  
  
 <span data-ttu-id="e02a6-131">**Para volver a habilitar el acceso no transaccional total**</span><span class="sxs-lookup"><span data-stu-id="e02a6-131">**To re-enable full non-transactional access**</span></span>  
 <span data-ttu-id="e02a6-132">Llame a la instrucción **ALTER DATABASE** y establezca el valor de **NON_TRANSACTED_ACCESS** en **FULL**.</span><span class="sxs-lookup"><span data-stu-id="e02a6-132">Call the **ALTER DATABASE** statement and SET the value of **NON_TRANSACTED_ACCESS** to **FULL**.</span></span>  
  
```sql  
ALTER DATABASE database_name  
    SET FILESTREAM ( NON_TRANSACTED_ACCESS = FULL );  
GO  
```  
  
###  <a name="how-to-ensure-the-visibility-of-the-filetables-in-a-database"></a><a name="visible"></a> <span data-ttu-id="e02a6-133">Procedimientos para: asegurar la visibilidad de FileTables en una base de datos</span><span class="sxs-lookup"><span data-stu-id="e02a6-133">How to: Ensure the Visibility of the FileTables in a Database</span></span>  
 <span data-ttu-id="e02a6-134">Un directorio de nivel de base de datos y sus directorios FileTable cuando se cumplen todas las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e02a6-134">A database-level directory and the FileTable directories under it are visible when all of these conditions are true:</span></span>  
  
1.  <span data-ttu-id="e02a6-135">FILESTREAM se habilita en el nivel de instancia.</span><span class="sxs-lookup"><span data-stu-id="e02a6-135">FILESTREAM is enabled at the instance level.</span></span>  
  
2.  <span data-ttu-id="e02a6-136">El acceso no transaccional se habilita en el nivel de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e02a6-136">Non-transactional access is enabled at the database level.</span></span>  
  
3.  <span data-ttu-id="e02a6-137">Un directorio válido se ha especificado en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e02a6-137">A valid directory has been specified at the database level.</span></span>  
  
##  <a name="disabling-and-re-enabling-the-filetable-namespace-at-the-table-level"></a><a name="BasicsEnabling"></a> <span data-ttu-id="e02a6-138">Deshabilitar y volver a habilitar el espacio de nombres FileTable en el nivel de tabla</span><span class="sxs-lookup"><span data-stu-id="e02a6-138">Disabling and Re-enabling the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="e02a6-139">Si se deshabilita el espacio de nombres de FileTable, se deshabilitan todas las restricciones y los desencadenadores definidos por el sistema que se crearon con FileTable.</span><span class="sxs-lookup"><span data-stu-id="e02a6-139">Disabling the FileTable namespace disables all the system-defined constraints and triggers that were created with the FileTable.</span></span> <span data-ttu-id="e02a6-140">Esto es útil en los casos en los que FileTable necesite reorganizarse a gran escala mediante operaciones [!INCLUDE[tsql](../../includes/tsql-md.md)] sin tener que aplicar la semántica de FileTable.</span><span class="sxs-lookup"><span data-stu-id="e02a6-140">This is useful in cases where a FileTable has to be reorganized on a large scale by using [!INCLUDE[tsql](../../includes/tsql-md.md)] operations without incurring the expense of enforcing FileTable semantics.</span></span> <span data-ttu-id="e02a6-141">Aunque estas operaciones pueden dejar FileTable en un estado incoherente, y pueden impedir volver a habilitar el espacio de nombres de FileTable.</span><span class="sxs-lookup"><span data-stu-id="e02a6-141">However these operations can leave the FileTable in an inconsistent state, and can prevent the re-enabling of the FileTable namespace.</span></span>  
  
 <span data-ttu-id="e02a6-142">Deshabilitar un espacio de nombres FileTable tiene los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="e02a6-142">Disabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="e02a6-143">Las columnas y los datos de FileTable no se quitan físicamente de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e02a6-143">FileTable columns and data are not physically dropped from the table.</span></span>  
  
-   <span data-ttu-id="e02a6-144">El directorio de FileTable y los archivos y directorios que contiene desaparecen del sistema de archivos y no están disponibles para el acceso E/S de archivos.</span><span class="sxs-lookup"><span data-stu-id="e02a6-144">The FileTable directory and the files and directories that it contains disappear from the file system and are not available for file i/o access.</span></span>  
  
-   <span data-ttu-id="e02a6-145">Las columnas FileTable definidas por el sistema no se pueden quitar ni volver a crear, otramente, sin embargo, se comportan como columnas normales para operaciones DML.</span><span class="sxs-lookup"><span data-stu-id="e02a6-145">System-defined FileTable columns cannot be dropped and recreated; otherwise, however, they behave like ordinary columns for DML operations.</span></span>  
  
-   <span data-ttu-id="e02a6-146">Los identificadores de archivos abiertos impiden que las restricciones de FileTable se deshabiliten, puesto que esta operación requiere un bloqueo de esquema de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e02a6-146">Open file handles prevent the FileTable constraints from being disabled, since this operation requires a schema lock on the table.</span></span>  
  
-   <span data-ttu-id="e02a6-147">La aplicación de toda la semántica de FileTable, incluidas las restricciones y los desencadenadores definidos por el sistema, se detiene después de que se haya deshabilitado el espacio de nombres de FileTable.</span><span class="sxs-lookup"><span data-stu-id="e02a6-147">Enforcement of all the FileTable semantics, including system-defined constraints and triggers, stops after the FileTable namespace is disabled.</span></span>  
  
 <span data-ttu-id="e02a6-148">Volver a habilitar un espacio de nombres FileTable tiene los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="e02a6-148">Re-enabling a FileTable namespace has the following results:</span></span>  
  
-   <span data-ttu-id="e02a6-149">Se comprueba la coherencia de FileTable.</span><span class="sxs-lookup"><span data-stu-id="e02a6-149">The FileTable is checked for consistency.</span></span> <span data-ttu-id="e02a6-150">Si se detectan incoherencias, se produce un error y FileTable permanece deshabilitada; si no, se vuelve a habilitar FileTable.</span><span class="sxs-lookup"><span data-stu-id="e02a6-150">If inconsistencies are found, then an error is raised and the FileTable remains disabled; otherwise, the FileTable is re-enabled.</span></span>  
  
-   <span data-ttu-id="e02a6-151">La aplicación de la semántica de FileTable, incluidas las restricciones y los desencadenadores definidos por el sistema, se restaura.</span><span class="sxs-lookup"><span data-stu-id="e02a6-151">The enforcement of FileTable semantics, including system-defined constraints and triggers, is restored.</span></span>  
  
-   <span data-ttu-id="e02a6-152">El directorio de FileTable y los archivos y directorios que este contiene se vuelve visible en el sistema de archivos y están disponibles para el acceso E/S del archivo.</span><span class="sxs-lookup"><span data-stu-id="e02a6-152">The FileTable directory and the files and directories that it contains become visible in the file system and become available for file i/o access.</span></span>  
  
###  <a name="how-to-disable-and-re-enable-the-filetable-namespace-at-the-table-level"></a><a name="HowToEnableNS"></a> <span data-ttu-id="e02a6-153">Procedimientos para: deshabilitar y volver a habilitar el espacio de nombres FileTable en el nivel de tabla</span><span class="sxs-lookup"><span data-stu-id="e02a6-153">How To: Disable and Re-enable the FileTable Namespace at the Table Level</span></span>  
 <span data-ttu-id="e02a6-154">Se llama a la instrucción ALTER TABLE con la opción **{ ENABLE | DISABLE } FILETABLE_NAMESPACE** .</span><span class="sxs-lookup"><span data-stu-id="e02a6-154">Call the ALTER TABLE statement with the **{ ENABLE | DISABLE } FILETABLE_NAMESPACE** option.</span></span>  
  
 <span data-ttu-id="e02a6-155">**Para deshabilitar el espacio de nombres de FileTable**</span><span class="sxs-lookup"><span data-stu-id="e02a6-155">**To disable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    DISABLE FILETABLE_NAMESPACE;  
GO  
```  
  
 <span data-ttu-id="e02a6-156">**Para volver a habilitar el espacio de nombres de FileTable**</span><span class="sxs-lookup"><span data-stu-id="e02a6-156">**To re-enable the FileTable namespace**</span></span>  
 ```sql  
ALTER TABLE filetable_name  
    ENABLE FILETABLE_NAMESPACE;  
GO  
```  
  
##  <a name="killing-open-file-handles-associated-with-a-filetable"></a><a name="BasicsKilling"></a> <span data-ttu-id="e02a6-157">Eliminar los identificadores de archivos abiertos asociados con FileTable</span><span class="sxs-lookup"><span data-stu-id="e02a6-157">Killing Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="e02a6-158">Los identificadores abiertos en los archivos almacenados en FileTable pueden impedir el acceso exclusivo necesario para ciertas tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="e02a6-158">Open handles to the files stored in a FileTable can prevent the exclusive access that is required for certain administrative tasks.</span></span> <span data-ttu-id="e02a6-159">Para habilitar tareas urgentes, quizá deba eliminar los identificadores de archivos abiertos asociados con una o más FileTables.</span><span class="sxs-lookup"><span data-stu-id="e02a6-159">To enable urgent tasks, you may have to kill open file handles associated with one or more FileTables.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="e02a6-160">Eliminar los identificadores de archivos abiertos puede hacer que los usuarios pierdan los datos no guardados.</span><span class="sxs-lookup"><span data-stu-id="e02a6-160">Killing open file handles may cause users to lose unsaved data.</span></span> <span data-ttu-id="e02a6-161">Este comportamiento es coherente con el comportamiento del propio sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="e02a6-161">This behavior is consistent with the behavior of the file system itself.</span></span>  
  
###  <a name="how-to-get-a-list-of-open-file-handles-associated-with-a-filetable"></a><a name="HowToListOpen"></a> <span data-ttu-id="e02a6-162">Procedimientos para: obtener una lista de los identificadores de archivos abiertos asociados con FileTable</span><span class="sxs-lookup"><span data-stu-id="e02a6-162">How To: Get a List of Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="e02a6-163">Consulte la vista de catálogo [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e02a6-163">Query the catalog view [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span>  
  
```sql  
SELECT * FROM sys.dm_filestream_non_transacted_handles;  
GO  
```  
  
###  <a name="how-to-kill-open-file-handles-associated-with-a-filetable"></a><a name="HowToKill"></a> <span data-ttu-id="e02a6-164">Procedimientos para: eliminar los identificadores de archivos abiertos asociados con FileTable</span><span class="sxs-lookup"><span data-stu-id="e02a6-164">How To: Kill Open File Handles Associated with a FileTable</span></span>  
 <span data-ttu-id="e02a6-165">Llame al procedimiento almacenado [sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles) con los argumentos apropiados para eliminar todos los identificadores de archivo abiertos de la base de datos o de FileTable, o bien eliminar un identificador específico.</span><span class="sxs-lookup"><span data-stu-id="e02a6-165">Call the stored procedure [sp_kill_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/filestream-and-filetable-sp-kill-filestream-non-transacted-handles) with the appropriate arguments to kill all open file handles in the database or in the FileTable, or to kill a specific handle.</span></span>  
  
```  
USE database_name;  
  
-- Kill all open handles in all the filetables in the database.  
EXEC sp_kill_filestream_non_transacted_handles;  
GO  
  
-- Kill all open handles in a single filetable.  
EXEC sp_kill_filestream_non_transacted_handles @table_name = 'filetable_name';  
GO  
  
-- Kill a single handle.  
EXEC sp_kill_filestream_non_transacted_handles @handle_id = integer_handle_id;  
GO  
```  
  
###  <a name="how-to-identify-the-locks-held-by-filetables"></a><a name="HowToIdentifyLocks"></a> <span data-ttu-id="e02a6-166">Procedimientos para: identificar los bloqueos de FileTables</span><span class="sxs-lookup"><span data-stu-id="e02a6-166">How to: Identify the Locks Held by FileTables</span></span>  
 <span data-ttu-id="e02a6-167">La mayoría de los bloqueos de FileTables corresponden a archivos abiertos por aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e02a6-167">Most locks taken by FileTables correspond to files opened by applications.</span></span>  
  
 <span data-ttu-id="e02a6-168">**Para identificar los archivos abiertos y los bloqueos asociados**</span><span class="sxs-lookup"><span data-stu-id="e02a6-168">**To identify open files and the associated locks**</span></span>  
 <span data-ttu-id="e02a6-169">Combine el campo **request_owner_id** de la vista de administración dinámica [sys.dm_tran_locks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) con el campo **fcb_id** de [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e02a6-169">Join the **request_owner_id** field in the dynamic management view [sys.dm_tran_locks &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql) with the **fcb_id** field in [sys.dm_filestream_non_transacted_handles &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-filestream-non-transacted-handles-transact-sql).</span></span> <span data-ttu-id="e02a6-170">En algunos casos, el bloqueo no se corresponde con ningún identificador de archivos abierto.</span><span class="sxs-lookup"><span data-stu-id="e02a6-170">In some cases, the lock does not correspond to a single open file handle.</span></span>  
  
```sql  
SELECT opened_file_name  
    FROM sys.dm_filestream_non_transacted_handles  
    WHERE fcb_id IN  
        ( SELECT request_owner_id FROM sys.dm_tran_locks );  
GO  
```  
  
##  <a name="filetable-security"></a><a name="BasicsSecurity"></a> <span data-ttu-id="e02a6-171">Seguridad de FileTable</span><span class="sxs-lookup"><span data-stu-id="e02a6-171">FileTable Security</span></span>  
 <span data-ttu-id="e02a6-172">Los archivos y directorios almacenados en FileTables están protegidos solo por la seguridad de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e02a6-172">The files and directories stored in FileTables are secured by SQL Server security only.</span></span> <span data-ttu-id="e02a6-173">La seguridad basada en tabla y columna se aplica para el acceso al sistema de archivos así como para el acceso a [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e02a6-173">Table and column-based security is enforced for file system access as well as [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="e02a6-174">No se admiten las API de seguridad del sistema de archivo de Windows ni la configuración de ACL.</span><span class="sxs-lookup"><span data-stu-id="e02a6-174">Windows file system security APIs and ACL settings are not supported.</span></span>  
  
 <span data-ttu-id="e02a6-175">La seguridad y los permisos de acceso que son aplicables a los grupos de archivo y contenedores de FILESTREAM también son aplicables a FileTables, ya que los datos de archivos se almacenan como columna FILESTREAM en FileTable.</span><span class="sxs-lookup"><span data-stu-id="e02a6-175">The security and access permissions that are applicable to FILESTREAM filegroups and containers also apply to FileTables, since the file data is stored as a FILESTREAM column in the FileTable.</span></span>  
  
 <span data-ttu-id="e02a6-176">**Seguridad de FileTable y acceso a Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="e02a6-176">**FileTable Security and Transact-SQL Access**</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="e02a6-177">acceso a los datos de FileTables está protegido de la misma manera que en cualquier otra tabla.</span><span class="sxs-lookup"><span data-stu-id="e02a6-177">access to data in FileTables is secured in the same way as any other table.</span></span> <span data-ttu-id="e02a6-178">Se realizan comprobaciones de seguridad apropiadas en el nivel de tabla y de columna para cada operación que tenga acceso a los datos o que los modifique.</span><span class="sxs-lookup"><span data-stu-id="e02a6-178">Appropriate table and column-level security checks are done for every operation that accesses or changes the data.</span></span>  
  
 <span data-ttu-id="e02a6-179">**Seguridad de FileTable y acceso al sistema de archivos**</span><span class="sxs-lookup"><span data-stu-id="e02a6-179">**FileTable Security and File System Access**</span></span>  
 <span data-ttu-id="e02a6-180">Las API del sistema de archivos requieren los permisos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] apropiados para toda la fila de FileTable (es decir, permiso en el nivel de tabla) para abrir un identificador de un archivo o directorio almacenado en FileTable.</span><span class="sxs-lookup"><span data-stu-id="e02a6-180">File system APIs require appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions on the entire row in the FileTable (that is, table-level permission) to open a handle to a file or directory stored in the FileTable.</span></span> <span data-ttu-id="e02a6-181">Si el usuario no tiene el permiso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adecuado en alguna columna de FileTable, se deniega el acceso al sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="e02a6-181">If the user does not have the appropriate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission on any column in the FileTable, then file system access is denied.</span></span>  
  
##  <a name="backup-and-filetables"></a><a name="OtherBackup"></a> <span data-ttu-id="e02a6-182">Copia de seguridad y FileTables</span><span class="sxs-lookup"><span data-stu-id="e02a6-182">Backup and FileTables</span></span>  
 <span data-ttu-id="e02a6-183">Cuando se utiliza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para realizar una copia de seguridad en FileTable, se realiza una copia de seguridad de los datos de FILESTREAM con los datos estructurados en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e02a6-183">When you use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to back up a FileTable, the FILESTREAM data is backed up with the structured data in the database.</span></span> <span data-ttu-id="e02a6-184">Si no desea realizar una copia de seguridad de los datos FILESTREAM con datos relacionales, puede usar una copia de seguridad parcial para excluir los grupos de archivos FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e02a6-184">If you do not want to back up FILESTREAM data with relational data, you can use a partial backup to exclude FILESTREAM filegroups.</span></span>  
  
 <span data-ttu-id="e02a6-185">**Coherencia transaccional de copias de seguridad de FileTable**</span><span class="sxs-lookup"><span data-stu-id="e02a6-185">**Transactional Consistency of FileTable Backups**</span></span>  
  
 <span data-ttu-id="e02a6-186">Muchas herramientas y operaciones administrativas, (incluidas la copia de seguridad, la copia de seguridad de registros y la replicación transaccional) leen datos coherentes transaccionalmente leyendo los registros de transacciones.</span><span class="sxs-lookup"><span data-stu-id="e02a6-186">Many administrative tools and operations, (including backup, log backup, and transactional replication) read transactionally consistent data by reading the transaction logs.</span></span> <span data-ttu-id="e02a6-187">En este momento, leen los datos FILESTREAM actualizados como parte de una transacción.</span><span class="sxs-lookup"><span data-stu-id="e02a6-187">At this time, they read any FILESTREAM data updated as part of a transaction.</span></span> <span data-ttu-id="e02a6-188">Cuando no se habilita el acceso no transaccional en el nivel de base de datos, estas herramientas y operaciones funcionan con toda la coherencia transaccional.</span><span class="sxs-lookup"><span data-stu-id="e02a6-188">When non-transactional access is not enabled at the database level, these tools and operations work with full transactional consistency.</span></span>  
  
 <span data-ttu-id="e02a6-189">No obstante, cuando se habilita el acceso no transaccional total, una FileTable podría contener datos actualizados más recientemente (a través de una actualización no transaccional) que la transacción que la herramienta o el proceso están leyendo desde el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="e02a6-189">However, when full non-transactional access is enabled, then a FileTable could contain data that was updated more recently (through a non-transactional update) than the transaction that the tool or process is reading from the transaction log.</span></span> <span data-ttu-id="e02a6-190">Es decir, una operación de restauración "a un momento dado" en una transacción específica puede contener datos de FILESTREAM más recientes que los de esa transacción.</span><span class="sxs-lookup"><span data-stu-id="e02a6-190">This means that a "point in time" restore operation to a specific transaction may contain FILESTREAM data that is more recent than that transaction.</span></span> <span data-ttu-id="e02a6-191">Este es el comportamiento esperado cuando se permiten actualizaciones no transaccionales en las FileTables.</span><span class="sxs-lookup"><span data-stu-id="e02a6-191">This is the expected behavior when non-transactional updates are allowed on FileTables.</span></span>  
  
##  <a name="sql-server-profiler-and-filetables"></a><a name="Monitor"></a> <span data-ttu-id="e02a6-192">SQL Server Profiler y FileTables</span><span class="sxs-lookup"><span data-stu-id="e02a6-192">SQL Server Profiler and FileTables</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e02a6-193">Profiler puede capturar las operaciones de apertura y de cierre del archivo de Windows en el resultado de seguimiento de los archivos almacenados en una FileTable.</span><span class="sxs-lookup"><span data-stu-id="e02a6-193">Profiler can capture the Windows File Open and File Close operations in trace output for files that are stored in a FileTable.</span></span>  
  
##  <a name="auditing-and-filetables"></a><a name="OtherAuditing"></a> <span data-ttu-id="e02a6-194">Auditoría y FileTables</span><span class="sxs-lookup"><span data-stu-id="e02a6-194">Auditing and FileTables</span></span>  
 <span data-ttu-id="e02a6-195">La FileTable se puede auditar como cualquier otra tabla.</span><span class="sxs-lookup"><span data-stu-id="e02a6-195">FileTable can be audited just like any other table.</span></span> <span data-ttu-id="e02a6-196">Sin embargo, los modelos de acceso de Win32 no son operaciones basadas en conjunto.</span><span class="sxs-lookup"><span data-stu-id="e02a6-196">Howerver, Win32 access patterns are not set based operations.</span></span> <span data-ttu-id="e02a6-197">Una sola acción del sistema de archivos se traduce en varias operaciones DML de Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="e02a6-197">A single action in the file system translates into multiple Transact-SQL DML operations.</span></span> <span data-ttu-id="e02a6-198">Por ejemplo, la apertura de un archivo en Microsoft Word se traduce en varias operaciones de apertura, cierre, creación, cambio de nombre o eliminación, así como en las actividades DML de Transact-SQL correspondientes.</span><span class="sxs-lookup"><span data-stu-id="e02a6-198">For example, opening a file in Microsoft Word translates into multiple open/close/create/rename/delete operations and corresponding Transact-SQL DML activities.</span></span> <span data-ttu-id="e02a6-199">El resultado son registros de auditoría detallados en los que es difícil poner en correlación los registros entre las acciones del sistema de archivos y los registros de auditoría de DML de Transact-SQL correspondientes.</span><span class="sxs-lookup"><span data-stu-id="e02a6-199">This results in verbose audit records where it is hard to correlate records between file system actions and corresponding Transact-SQL DML audit records.</span></span>  
  
##  <a name="dbcc-and-filetables"></a><a name="OtherDBCC"></a> <span data-ttu-id="e02a6-200">DBCC y FileTables</span><span class="sxs-lookup"><span data-stu-id="e02a6-200">DBCC and FileTables</span></span>  
 <span data-ttu-id="e02a6-201">Puede usar DBCC CHECKCONSTRAINTS para validar las restricciones de una FileTable, incluidas las restricciones definidas por el sistema.</span><span class="sxs-lookup"><span data-stu-id="e02a6-201">You can use DBCC CHECKCONSTRAINTS to validate the constraints on a FileTable including system-defined constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e02a6-202">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e02a6-202">See Also</span></span>  
 <span data-ttu-id="e02a6-203">[Compatibilidad de FileTable con otras características de SQL Server](filetable-compatibility-with-other-sql-server-features.md) </span><span class="sxs-lookup"><span data-stu-id="e02a6-203">[FileTable Compatibility with Other SQL Server Features](filetable-compatibility-with-other-sql-server-features.md) </span></span>  
 [<span data-ttu-id="e02a6-204">DDL de FileTable, funciones, procedimientos almacenados y vistas</span><span class="sxs-lookup"><span data-stu-id="e02a6-204">FileTable DDL, Functions, Stored Procedures, and Views</span></span>](../views/views.md)  
  
  
