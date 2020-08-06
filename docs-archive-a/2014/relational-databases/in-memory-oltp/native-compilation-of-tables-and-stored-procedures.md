---
title: Compilación nativa de tablas y procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 5880fbd9-a23e-464a-8b44-09750eeb2dad
author: rothja
ms.author: jroth
ms.openlocfilehash: 32c5b04610d894e06278fbeecdaf3bbebe850d60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674114"
---
# <a name="native-compilation-of-tables-and-stored-procedures"></a><span data-ttu-id="69aa3-102">Compilación nativa de tablas y procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="69aa3-102">Native Compilation of Tables and Stored Procedures</span></span>
  <span data-ttu-id="69aa3-103">OLTP en memoria introduce el concepto de compilación nativa.</span><span class="sxs-lookup"><span data-stu-id="69aa3-103">In-Memory OLTP introduces the concept of native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="69aa3-104">puede compilar de forma nativa procedimientos almacenados que acceden a tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="69aa3-104">can natively compile stored procedures that access memory-optimized tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="69aa3-105">también puede compilar de forma nativa las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="69aa3-105">is also able to natively compile memory-optimized tables.</span></span> <span data-ttu-id="69aa3-106">La compilación nativa permite un acceso más rápido a los datos y una ejecución de consultas más eficiente que el lenguaje [!INCLUDE[tsql](../../includes/tsql-md.md)]interpretado (tradicional).</span><span class="sxs-lookup"><span data-stu-id="69aa3-106">Native compilation allows faster data access and more efficient query execution than interpreted (traditional) [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="69aa3-107">La compilación nativa de tablas y procedimientos almacenados produce los archivos DLL.</span><span class="sxs-lookup"><span data-stu-id="69aa3-107">Native compilation of tables and stored procedures produce DLLs.</span></span>  
  
 <span data-ttu-id="69aa3-108">Se admite también la compilación nativa de los tipos de tabla con optimización para memoria.</span><span class="sxs-lookup"><span data-stu-id="69aa3-108">Native compilation of memory optimized table types is also supported.</span></span> <span data-ttu-id="69aa3-109">Para más información, consulte [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span><span class="sxs-lookup"><span data-stu-id="69aa3-109">For more information, see [Memory-Optimized Table Variables](../../database-engine/memory-optimized-table-variables.md).</span></span>  
  
 <span data-ttu-id="69aa3-110">La compilación nativa se refiere al proceso de convertir construcciones de programación a código nativo, que consta de instrucciones de procesador sin necesidad de compilación o interpretación adicional.</span><span class="sxs-lookup"><span data-stu-id="69aa3-110">Native compilation refers to the process of converting programming constructs to native code, consisting of processor instructions without the need for further compilation or interpretation.</span></span>  
  
 <span data-ttu-id="69aa3-111">OLTP en memoria compila las tablas optimizadas para memoria cuando se crean, y los procedimientos almacenados compilados de forma nativa cuando se cargan en archivos DLL nativos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-111">In-Memory OLTP compiles memory-optimized tables when they are created, and natively compiled stored procedures when they are loaded to native DLLs.</span></span> <span data-ttu-id="69aa3-112">Además, los archivos DLL se recompilan tras reiniciar una base de datos o un servidor.</span><span class="sxs-lookup"><span data-stu-id="69aa3-112">In addition, the DLLs are recompiled after a database or server restart.</span></span> <span data-ttu-id="69aa3-113">La información necesaria para volver a crear los archivos DLL se almacena en los metadatos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-113">The information necessary to recreate the DLLs is stored in the database metadata.</span></span> <span data-ttu-id="69aa3-114">Los archivos DLL no forman parte de la base de datos, aunque están asociados a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-114">The DLLs are not part of the database, though they are associated with the database.</span></span> <span data-ttu-id="69aa3-115">Por ejemplo, los archivos DLL no se incluyen en las copias de seguridad de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-115">For example, the DLLs are not included in database backups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69aa3-116">Las tablas con optimización para memoria se vuelven a compilar durante un reinicio del servidor.</span><span class="sxs-lookup"><span data-stu-id="69aa3-116">Memory-optimized tables are recompiled during a server restart.</span></span> <span data-ttu-id="69aa3-117">Para acelerar la recuperación de bases de datos, los procedimientos almacenados compilados de forma nativa no se vuelven a compilar durante un reinicio del servidor, sino que se compilan en el momento de la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="69aa3-117">To speed up database recovery, natively compiled stored procedures are not recompiled during a server restart, they are compiled at the time of first execution.</span></span> <span data-ttu-id="69aa3-118">Como consecuencia de esta compilación diferida, los procedimientos almacenados compilados de forma nativa solo aparecen al llamar a [sys.dm_os_loaded_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) tras la primera ejecución.</span><span class="sxs-lookup"><span data-stu-id="69aa3-118">As a result of this deferred compilation, natively compiled stored procedures only appear when calling [sys.dm_os_loaded_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-loaded-modules-transact-sql) after first execution.</span></span>  
  
## <a name="maintenance-of-in-memory-oltp-dlls"></a><span data-ttu-id="69aa3-119">Mantenimiento de los archivos DLL de OLTP en memoria</span><span class="sxs-lookup"><span data-stu-id="69aa3-119">Maintenance of In-Memory OLTP DLLs</span></span>  
 <span data-ttu-id="69aa3-120">La consulta siguiente muestra todos los archivos DLL de tablas y procedimientos almacenados cargados actualmente en la memoria del servidor:</span><span class="sxs-lookup"><span data-stu-id="69aa3-120">The following query shows all table and stored procedure DLLs currently loaded in memory on the server:</span></span>  
  
```sql  
SELECT name, description FROM sys.dm_os_loaded_modules  
where description = 'XTP Native DLL'  
```  
  
 <span data-ttu-id="69aa3-121">Los administradores de bases de datos no necesitan mantener los archivos generados por una compilación nativa.</span><span class="sxs-lookup"><span data-stu-id="69aa3-121">Database administrators do not need to maintain files that are generated by a native compilation.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="69aa3-122">quita automáticamente los archivos generados que ya no son necesarios.</span><span class="sxs-lookup"><span data-stu-id="69aa3-122">automatically removes generated files that are no longer needed.</span></span> <span data-ttu-id="69aa3-123">Por ejemplo, los archivos generados se eliminarán cuando se elimine una tabla o un procedimiento almacenado, o si se quita una base de datos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-123">For example, generated files will be deleted when a table and stored procedure is deleted, or if a database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69aa3-124">Si la compilación produce un error o se interrumpe, algunos archivos generados no se eliminan.</span><span class="sxs-lookup"><span data-stu-id="69aa3-124">If compilation fails or is interrupted, some generated files are not removed.</span></span> <span data-ttu-id="69aa3-125">Estos archivos se dejan intencionadamente por motivos de compatibilidad y se quitan cuando se quita la base de datos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-125">These files are intentionally left behind for supportability and are removed when the database is dropped.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69aa3-126">Durante el inicio de la base de datos, SQL Server compila los archivos DLL para todas las tablas necesarias para la recuperación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-126">During database startup, SQL Server compiles DLLs for all tables needed for database recovery.</span></span> <span data-ttu-id="69aa3-127">Si se quita una tabla justo antes de un reinicio de la base de datos, puede haber residuos de la tabla en los archivos de punto de control o en el registro de transacciones, de modo que puede volver a compilar el archivo DLL de la tabla durante el inicio de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-127">If a table was dropped just prior to a database restart there can still be remnants of the table in the checkpoint files or the transaction log so the DLL for the table might be recompiled during database startup.</span></span> <span data-ttu-id="69aa3-128">Después de reiniciar, el archivo DLL se descargará y se quitarán los archivos con el proceso de limpieza normal.</span><span class="sxs-lookup"><span data-stu-id="69aa3-128">After restart the DLL will be unloaded and the files will be removed by the normal cleanup process.</span></span>  
  
## <a name="native-compilation-of-tables"></a><span data-ttu-id="69aa3-129">Compilación nativa de tablas</span><span class="sxs-lookup"><span data-stu-id="69aa3-129">Native Compilation of Tables</span></span>  
 <span data-ttu-id="69aa3-130">Al crear una tabla optimizada para memoria mediante la instrucción `CREATE TABLE`, la información de la tabla se escribe en los metadatos de la base de datos y se crean las estructuras de tabla y de índice en la memoria.</span><span class="sxs-lookup"><span data-stu-id="69aa3-130">Creating a memory-optimized table using the `CREATE TABLE` statement results in the table information being written to the database metadata and the table and index structures created in memory.</span></span> <span data-ttu-id="69aa3-131">Además, la tabla se compila en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="69aa3-131">The table will also be compiled to a DLL.</span></span>  
  
 <span data-ttu-id="69aa3-132">Considere el script de ejemplo siguiente, que crea una base de datos y una tabla optimizada para memoria:</span><span class="sxs-lookup"><span data-stu-id="69aa3-132">Consider the following sample script, which creates a database and a memory-optimized table:</span></span>  
  
```sql  
use master  
go  
create database db1  
go  
alter database db1 add filegroup db1_mod contains memory_optimized_data  
go  
-- adapt filename as needed  
alter database db1 add file (name='db1_mod', filename='c:\data\db1_mod') to filegroup db1_mod  
go  
use db1  
go  
create table dbo.t1  
   (c1 int not null primary key nonclustered,  
    c2 INT)  
with (memory_optimized=on)  
go  
-- retrieve the path of the DLL for table t1  
select name, description FROM sys.dm_os_loaded_modules  
where name like '%xtp_t_' + cast(db_id() as varchar(10)) + '_' + cast(object_id('dbo.t1') as varchar(10)) + '.dll'  
go  
```  
  
 <span data-ttu-id="69aa3-133">Al crear la tabla, también se crea el archivo DLL de la tabla y se carga en memoria.</span><span class="sxs-lookup"><span data-stu-id="69aa3-133">Creating the table also creates the table DLL and loads the DLL in memory.</span></span> <span data-ttu-id="69aa3-134">La consulta DMV que aparece inmediatamente después de la instrucción CREATE TABLE recupera la ruta de acceso del archivo DLL de la tabla.</span><span class="sxs-lookup"><span data-stu-id="69aa3-134">The DMV query immediately after the CREATE TABLE statement retrieves the path of the table DLL.</span></span>  
  
 <span data-ttu-id="69aa3-135">El archivo DLL de la tabla entiende las estructuras de índice y el formato de fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="69aa3-135">The table DLL understands the index structures and row format of the table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="69aa3-136">utiliza el archivo DLL para recorrer índices, recuperar filas y almacenar el contenido de estas.</span><span class="sxs-lookup"><span data-stu-id="69aa3-136">uses the DLL for traversing indexes, retrieving rows, as well as storing the contents of the rows.</span></span>  
  
## <a name="native-compilation-of-stored-procedures"></a><span data-ttu-id="69aa3-137">Compilación nativa de procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="69aa3-137">Native Compilation of Stored Procedures</span></span>  
 <span data-ttu-id="69aa3-138">Los procedimientos almacenados marcados con NATIVE_COMPILATION se compilan de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="69aa3-138">Stored procedures that are marked with NATIVE_COMPILATION are natively compiled.</span></span> <span data-ttu-id="69aa3-139">Esto significa que todas las instrucciones [!INCLUDE[tsql](../../includes/tsql-md.md)] del procedimiento se compilan en código nativo para lograr una ejecución eficaz de la lógica de negocios de rendimiento crítico.</span><span class="sxs-lookup"><span data-stu-id="69aa3-139">This means the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the procedure are all compiled to native code for efficient execution of performance-critical business logic.</span></span>  
  
 <span data-ttu-id="69aa3-140">Para obtener más información acerca de los procedimientos almacenados compilados de forma nativa, vea [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="69aa3-140">For more information about natively compiled stored procedures, see [Natively Compiled Stored Procedures](natively-compiled-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="69aa3-141">Considere el procedimiento almacenado de ejemplo siguiente, que inserta filas en la tabla t1 del ejemplo anterior:</span><span class="sxs-lookup"><span data-stu-id="69aa3-141">Consider the following sample stored procedure, which inserts rows in the table t1 from the previous example:</span></span>  
  
```sql  
create procedure dbo.native_sp  
with native_compilation, schemabinding, execute as owner  
as  
begin atomic  
with (transaction isolation level=snapshot, language=N'us_english')  
  
  declare @i int = 1000000  
  while @i > 0  
  begin  
    insert dbo.t1 values (@i, @i+1)  
    set @i -= 1  
  end  
  
end  
go  
exec dbo.native_sp  
go  
-- reset  
delete from dbo.t1  
go  
```  
  
 <span data-ttu-id="69aa3-142">El archivo DLL de native_sp puede interactuar directamente con el archivo DLL de t1, así como con el motor de almacenamiento de OLTP en memoria, para insertar las filas a la mayor velocidad posible.</span><span class="sxs-lookup"><span data-stu-id="69aa3-142">The DLL for native_sp can interact directly with the DLL for t1, as well as the In-Memory OLTP storage engine, to insert the rows as fast as possible.</span></span>  
  
 <span data-ttu-id="69aa3-143">El compilador de OLTP en memoria utiliza el optimizador de consultas para crear un plan de ejecución eficaz para cada una de las consultas del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="69aa3-143">The In-Memory OLTP compiler leverages the query optimizer to create an efficient execution plan for each of the queries in the stored procedure.</span></span> <span data-ttu-id="69aa3-144">Tenga en cuenta que los procedimientos almacenados compilados de forma nativa no se recompilan automáticamente si cambian los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="69aa3-144">Note that natively compiled stored procedures are not automatically recompiled if the data in the table changes.</span></span> <span data-ttu-id="69aa3-145">Para obtener más información sobre el mantenimiento de estadísticas y procedimientos almacenados con OLTP en memoria, vea [Estadísticas para las tablas con optimización para memoria](memory-optimized-tables.md).</span><span class="sxs-lookup"><span data-stu-id="69aa3-145">For more information on maintaining statistics and stored procedures with In-Memory OLTP see [Statistics for Memory-Optimized Tables](memory-optimized-tables.md).</span></span>  
  
## <a name="security-considerations-for-native-compilation"></a><span data-ttu-id="69aa3-146">Consideraciones de seguridad para la compilación nativa</span><span class="sxs-lookup"><span data-stu-id="69aa3-146">Security Considerations for Native Compilation</span></span>  
 <span data-ttu-id="69aa3-147">La compilación nativa de tablas y procedimientos almacenados utiliza el compilador de OLTP en memoria.</span><span class="sxs-lookup"><span data-stu-id="69aa3-147">Native compilation of tables and stored procedures uses the In-Memory OLTP compiler.</span></span> <span data-ttu-id="69aa3-148">Este compilador genera archivos que se escriben en el disco y se cargan en la memoria.</span><span class="sxs-lookup"><span data-stu-id="69aa3-148">This compiler produces files that are written to disk and loaded into memory.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="69aa3-149">utiliza los siguientes mecanismos para restringir el acceso a estos archivos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-149">uses the following mechanisms to limit access to these files.</span></span>  
  
### <a name="native-compiler"></a><span data-ttu-id="69aa3-150">Compilador nativo</span><span class="sxs-lookup"><span data-stu-id="69aa3-150">Native Compiler</span></span>  
 <span data-ttu-id="69aa3-151">El archivo ejecutable del compilador, así como los archivos binarios y de encabezado necesarios para la compilación nativa, se instalan como parte de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la carpeta MSSQL\Binn\Xtp.</span><span class="sxs-lookup"><span data-stu-id="69aa3-151">The compiler executable, as well as binaries and header files required for native compilation are installed as part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance under the folder MSSQL\Binn\Xtp.</span></span> <span data-ttu-id="69aa3-152">Por lo tanto, si la instancia predeterminada se instala en c:\Archivos de programa, los archivos del compilador se instalan en c:\Archivos de programa \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \MSSQL12. MSSQLSERVER\MSSQL\Binn\Xtp.</span><span class="sxs-lookup"><span data-stu-id="69aa3-152">So, if the default instance is installed under C:\Program Files, the compiler files are installed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\Binn\Xtp.</span></span>  
  
 <span data-ttu-id="69aa3-153">Para limitar el acceso al compilador, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utiliza listas de control de acceso (ACL) para restringir el acceso a los archivos binarios.</span><span class="sxs-lookup"><span data-stu-id="69aa3-153">To limit access to the compiler, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses access control lists (ACLs) to restrict access to binary files.</span></span> <span data-ttu-id="69aa3-154">Todos los archivos binarios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] están protegidos frente a su modificación o alteración mediante ACL.</span><span class="sxs-lookup"><span data-stu-id="69aa3-154">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] binaries are protected against modification or tampering through ACLs.</span></span> <span data-ttu-id="69aa3-155">Las ACL del compilador nativo también limitan el uso del compilador; solo la cuenta de servicio y los administradores del sistema de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tienen permisos de ejecución y de lectura para los archivos del compilador nativo.</span><span class="sxs-lookup"><span data-stu-id="69aa3-155">The native compiler's ACLs also limit use of the compiler; only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators have read and execute permissions for native compiler files.</span></span>  
  
### <a name="files-generated-by-a-native-compilation"></a><span data-ttu-id="69aa3-156">Archivos generados por una compilación nativa</span><span class="sxs-lookup"><span data-stu-id="69aa3-156">Files Generated by a Native Compilation</span></span>  
 <span data-ttu-id="69aa3-157">Entre los archivos que se generan cuando se compila una tabla o un procedimiento almacenado se incluyen los archivos intermedios y DLL, incluidos aquellos que tienen las extensiones siguientes: .c, .obj, .xml y .pdb.</span><span class="sxs-lookup"><span data-stu-id="69aa3-157">The files produced when a table or stored procedure is compiled include the DLL and intermediate files including files with the following extensions: .c, .obj, .xml, and .pdb.</span></span> <span data-ttu-id="69aa3-158">Los archivos generados se guardan en una subcarpeta de la carpeta de datos predeterminada.</span><span class="sxs-lookup"><span data-stu-id="69aa3-158">The generated files are saved in a subfolder of the default data folder.</span></span> <span data-ttu-id="69aa3-159">La subcarpeta se denomina Xtp.</span><span class="sxs-lookup"><span data-stu-id="69aa3-159">The subfolder is called Xtp.</span></span> <span data-ttu-id="69aa3-160">Al instalar la instancia predeterminada con la carpeta de datos predeterminada, los archivos generados se colocan en c:\Archivos de programa \\ [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] \MSSQL12. MSSQLSERVER\MSSQL\DATA\Xtp.</span><span class="sxs-lookup"><span data-stu-id="69aa3-160">When installing the default instance with the default data folder, the generated files are placed in C:\Program Files\\[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\MSSQL12.MSSQLSERVER\MSSQL\DATA\Xtp.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="69aa3-161">evita la alteración con las DLL generadas de tres maneras:</span><span class="sxs-lookup"><span data-stu-id="69aa3-161">prevents tampering with the generated DLLs in three ways:</span></span>  
  
-   <span data-ttu-id="69aa3-162">Cuando una tabla o un procedimiento almacenado se compila en un archivo DLL, este archivo se carga en memoria y se vincula al proceso sqlserver.exe inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="69aa3-162">When a table or stored procedure is compiled to a DLL, this DLL is immediately loaded into memory and linked to the sqlserver.exe process.</span></span> <span data-ttu-id="69aa3-163">Un archivo DLL no se puede modificar mientras esté vinculado a un proceso.</span><span class="sxs-lookup"><span data-stu-id="69aa3-163">A DLL cannot be modified while it is linked to a process.</span></span>  
  
-   <span data-ttu-id="69aa3-164">Cuando se reinicia una base de datos, se recompilan todas las tablas y los procedimientos almacenados (se quitan y se vuelven a crear) según los metadatos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-164">When a database is restarted, all tables and stored procedures are recompiled (removed and recreated) based on the database metadata.</span></span> <span data-ttu-id="69aa3-165">De este modo, se quitará cualquier cambio realizado en un archivo generado por un agente malintencionado.</span><span class="sxs-lookup"><span data-stu-id="69aa3-165">This will remove any changes made to a generated file by a malicious agent.</span></span>  
  
-   <span data-ttu-id="69aa3-166">Los archivos generados se consideran parte de los datos de usuario y tienen las mismas restricciones de seguridad, mediante ACL, que los archivos de base de datos: solo los administradores del sistema y la cuenta de servicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueden tener acceso a estos archivos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-166">The generated files are considered part of user data, and have the same security restrictions, via ACLs, as database files: only the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account and system administrators can access these files.</span></span>  
  
 <span data-ttu-id="69aa3-167">No se necesita ninguna interacción del usuario para administrar estos archivos.</span><span class="sxs-lookup"><span data-stu-id="69aa3-167">No user interaction is needed to manage these files.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="69aa3-168">creará y quitará los archivos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="69aa3-168">will create and remove the files as necessary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69aa3-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69aa3-169">See Also</span></span>  
 <span data-ttu-id="69aa3-170">[Tablas con optimización para memoria](memory-optimized-tables.md) </span><span class="sxs-lookup"><span data-stu-id="69aa3-170">[Memory-Optimized Tables](memory-optimized-tables.md) </span></span>  
 [<span data-ttu-id="69aa3-171">Procedimientos almacenados compilados de forma nativa</span><span class="sxs-lookup"><span data-stu-id="69aa3-171">Natively Compiled Stored Procedures</span></span>](natively-compiled-stored-procedures.md)  
  
  
