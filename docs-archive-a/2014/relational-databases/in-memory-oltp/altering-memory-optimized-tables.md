---
title: Modificar tablas con optimización para memoria | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 690b70b7-5be1-4014-af97-54e531997839
author: rothja
ms.author: jroth
ms.openlocfilehash: 4eedc6fdb45efc6c87765cd2208ead90c1887c27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676501"
---
# <a name="altering-memory-optimized-tables"></a><span data-ttu-id="c4a56-102">Modificar tablas con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="c4a56-102">Altering Memory-Optimized Tables</span></span>
  <span data-ttu-id="c4a56-103">No se admite la realización de operaciones ALTER en las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="c4a56-103">Performing ALTER operations on memory-optimized tables is not supported.</span></span> <span data-ttu-id="c4a56-104">Esto incluye operaciones tales como cambiar el bucket_count, agregar o quitar un índice y agregar o quitar una columna.</span><span class="sxs-lookup"><span data-stu-id="c4a56-104">This includes such operations as changing the bucket_count, adding or removing an index, and adding or removing a column.</span></span> <span data-ttu-id="c4a56-105">En este tema se proporcionan instrucciones sobre cómo actualizar las tablas optimizadas para memoria.</span><span class="sxs-lookup"><span data-stu-id="c4a56-105">This topic provides guidelines on how to update memory-optimized tables.</span></span>  
  
## <a name="updating-the-definition-of-a-memory-optimized-table"></a><span data-ttu-id="c4a56-106">Actualizar la definición de una tabla con optimización para memoria</span><span class="sxs-lookup"><span data-stu-id="c4a56-106">Updating the Definition of a Memory-Optimized Table</span></span>  
 <span data-ttu-id="c4a56-107">Para actualizar la definición de una tabla optimizada para memoria es necesario crear una nueva tabla con la definición de tabla actualizada, copiar los datos en la nueva tabla y comenzar a usarla.</span><span class="sxs-lookup"><span data-stu-id="c4a56-107">Updating the definition of a memory-optimized table requires you to create a new table with the updated table definition, copy the data to the new table, and start using the new table.</span></span> <span data-ttu-id="c4a56-108">A menos que la tabla sea de solo lectura, esto requiere detener la carga de trabajo en la tabla, para asegurarse de que no se realiza ningún cambio en la tabla mientras se realiza la copia de datos.</span><span class="sxs-lookup"><span data-stu-id="c4a56-108">Unless the table is read-only, this requires stopping the workload on the table, to ensure no changes are made to the table while the data copy is performed.</span></span>  
  
 <span data-ttu-id="c4a56-109">En el procedimiento siguiente se describen los pasos necesarios para actualizar una tabla.</span><span class="sxs-lookup"><span data-stu-id="c4a56-109">The following procedure outlines the steps required to update a table.</span></span> <span data-ttu-id="c4a56-110">En este ejemplo, la actualización agrega un índice.</span><span class="sxs-lookup"><span data-stu-id="c4a56-110">In this example, the update adds an index.</span></span> <span data-ttu-id="c4a56-111">Este procedimiento conserva el nombre de la tabla y requiere dos operaciones de copia de datos: una en la tabla temporal y otra en la nueva tabla.</span><span class="sxs-lookup"><span data-stu-id="c4a56-111">This procedure preserves the name of the table and requires two data copy operations: once to a temporary table, and once to the new table.</span></span> <span data-ttu-id="c4a56-112">El cambio del bucket_count de un índice, así como la adición o eliminación de una columna, se realizan de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="c4a56-112">Changing the bucket_count of an index or adding or removing a column is performed the same way.</span></span>  
  
1.  <span data-ttu-id="c4a56-113">Detenga la carga de trabajo en la tabla.</span><span class="sxs-lookup"><span data-stu-id="c4a56-113">Stop the workload on the table.</span></span>  
  
2.  <span data-ttu-id="c4a56-114">Genere el script para la tabla y agregue el nuevo índice al script.</span><span class="sxs-lookup"><span data-stu-id="c4a56-114">Generate script for the table and add the new index to the script.</span></span>  
  
3.  <span data-ttu-id="c4a56-115">Genere el script para los objetos enlazados al esquema (principalmente procedimientos almacenados compilados de forma nativa) que hacen referencia a T y a sus permisos.</span><span class="sxs-lookup"><span data-stu-id="c4a56-115">Generate script for the schema-bound objects (mainly natively compiled stored procedures) referencing T and their permissions.</span></span>  
  
     <span data-ttu-id="c4a56-116">Para encontrar los objetos enlazados al esquema que hacen referencia a la tabla, utilice la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="c4a56-116">The schema-bound objects referencing the table can be found using the following query:</span></span>  
  
    ```sql  
    declare @t nvarchar(255) = N'<table name>'  
  
    select r.referencing_schema_name, r.referencing_entity_name  
    from sys.dm_sql_referencing_entities (@t, 'OBJECT') as r join sys.sql_modules m on r.referencing_id=m.object_id  
    where r.is_caller_dependent = 0 and m.is_schema_bound=1;  
    ```  
  
     <span data-ttu-id="c4a56-117">Los permisos de un procedimiento almacenado pueden incluirse en scripts mediante el [!INCLUDE[tsql](../../includes/tsql-md.md)] siguiente:</span><span class="sxs-lookup"><span data-stu-id="c4a56-117">The permissions of a stored procedure can be scripted using the following [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span></span>  
  
    ```sql  
    declare @sp nvarchar(255) = N'<procedure name>'  
    declare @permissions nvarchar(max) = N''  
  
    select @permissions += dp.state_desc + N' ' + dp.permission_name + N' ON ' +   
       quotename(schema_name(o.schema_id)) + N'.' + quotename(o.name) + N' TO ' +  
       quotename(u.name) + N'; ' + char(13)  
    from sys.database_permissions as dp  
  
    join sys.database_principals as u  
       on u.principal_id = dp.grantee_principal_id  
  
    join sys.objects as o  
       on o.object_id = dp.major_id  
    where dp.class = 1 /* object */  
       and dp.minor_id = 0 and o.object_id=object_id(@sp);  
  
    select @permissions  
    ```  
  
4.  <span data-ttu-id="c4a56-118">Cree una copia de la tabla y copie los datos de la tabla original en ella.</span><span class="sxs-lookup"><span data-stu-id="c4a56-118">Create a copy of the table and copy the data from the original table to the copy of the table.</span></span> <span data-ttu-id="c4a56-119">La copia se puede crear con el siguiente [!INCLUDE[tsql](../../includes/tsql-md.md)] <sup>1</sup>.</span><span class="sxs-lookup"><span data-stu-id="c4a56-119">The copy can be created using the following [!INCLUDE[tsql](../../includes/tsql-md.md)]<sup>1</sup>.</span></span>  
  
    ```sql  
    select * into dbo.T_copy from dbo.T  
    ```  
  
     <span data-ttu-id="c4a56-120">Si hay suficiente memoria disponible, `T_copy` puede ser una tabla optimizada para memoria, lo que hace que la copia de datos sea más rápida.<sup> 2</sup></span><span class="sxs-lookup"><span data-stu-id="c4a56-120">If there is enough available memory, `T_copy` could be a memory-optimized table, which makes the data copy faster.<sup>2</sup></span></span>  
  
5.  <span data-ttu-id="c4a56-121">Quite los objetos enlazados al esquema que hacen referencia a la tabla original.</span><span class="sxs-lookup"><span data-stu-id="c4a56-121">Drop the schema-bound objects referencing the original table.</span></span>  
  
6.  <span data-ttu-id="c4a56-122">Quite la tabla original.</span><span class="sxs-lookup"><span data-stu-id="c4a56-122">Drop the original table.</span></span>  
  
7.  <span data-ttu-id="c4a56-123">Cree la nueva tabla (`T`) con el script que contiene el nuevo índice.</span><span class="sxs-lookup"><span data-stu-id="c4a56-123">Create the new table (`T`) with the script containing the new index.</span></span>  
  
8.  <span data-ttu-id="c4a56-124">Copie los datos de `T_copy` en `T`.</span><span class="sxs-lookup"><span data-stu-id="c4a56-124">Copy the data from `T_copy` to `T`.</span></span>  
  
9. <span data-ttu-id="c4a56-125">Vuelva a crear los objetos enlazados al esquema que hacen la referencia a la tabla y aplique los permisos.</span><span class="sxs-lookup"><span data-stu-id="c4a56-125">Recreate the referencing schema-bound objects and apply the permissions.</span></span>  
  
10. <span data-ttu-id="c4a56-126">Inicie la carga de trabajo en `T`.</span><span class="sxs-lookup"><span data-stu-id="c4a56-126">Start the workload on `T`.</span></span>  
  
 <span data-ttu-id="c4a56-127"><sup>1</sup> tenga en cuenta que `T_copy` se conserva en el disco en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c4a56-127"><sup>1</sup> Note that `T_copy` is persisted to disk in this example.</span></span> <span data-ttu-id="c4a56-128">Si hay una copia de seguridad de `T` disponible, `T_copy` puede ser una tabla temporal o no perdurable.</span><span class="sxs-lookup"><span data-stu-id="c4a56-128">If a backup of `T` is available, `T_copy` could be a temporary or a non-durable table.</span></span>  
  
 <span data-ttu-id="c4a56-129"><sup>2</sup> debe haber suficiente memoria para `T_copy` .</span><span class="sxs-lookup"><span data-stu-id="c4a56-129"><sup>2</sup> There must be enough memory for `T_copy`.</span></span> <span data-ttu-id="c4a56-130">La memoria no se libera inmediatamente en `DROP TABLE`.</span><span class="sxs-lookup"><span data-stu-id="c4a56-130">Memory is not freed immediately on `DROP TABLE`.</span></span> <span data-ttu-id="c4a56-131">Si `T_copy` está con optimización para memoria, debe haber suficiente memoria para dos copias adicionales de `T`.</span><span class="sxs-lookup"><span data-stu-id="c4a56-131">If `T_copy` is memory optimized, there needs to be enough memory for two additional copies of `T`.</span></span> <span data-ttu-id="c4a56-132">Si `T_copy` está basada en disco, basta con que haya memoria suficiente para una copia adicional de `T`, debido a que el recolector de elementos no utilizados necesita ponerse al día después de anular la versión anterior de `T`.</span><span class="sxs-lookup"><span data-stu-id="c4a56-132">If `T_copy` is a disk-based table, there only needs to be enough memory for one additional copy of `T`, due to the garbage collector needing to catch up after dropping the old version of `T`.</span></span>  
  
## <a name="changing-schema-powershell"></a><span data-ttu-id="c4a56-133">Cambiar el esquema (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="c4a56-133">Changing Schema (PowerShell)</span></span>  
 <span data-ttu-id="c4a56-134">Los scripts de PowerShell siguientes elaboran y generan cambios en el esquema aplicando el script a la tabla y los permisos asociados.</span><span class="sxs-lookup"><span data-stu-id="c4a56-134">The following PowerShell scripts prepare and generate for schema changes by scripting the table and associated permissions.</span></span>  
  
```powershell
prepare_schema_change.ps1 <serverName> <databaseName> <schemaName> <tableName>
```
  
 <span data-ttu-id="c4a56-135">Este script toma como argumento una tabla, e incluye el objeto y sus permisos, así como los objetos enlazados al esquema que hacen la referencia y sus permisos en la carpeta actual.</span><span class="sxs-lookup"><span data-stu-id="c4a56-135">This script takes as arguments a table, and scripts the object and its permissions and referencing schema-bound objects and their permissions in the current folder.</span></span> <span data-ttu-id="c4a56-136">Se generan un total de 7 scripts para actualizar el esquema de la tabla de entrada:</span><span class="sxs-lookup"><span data-stu-id="c4a56-136">A total of 7 scripts are generated for updating the schema of the input table:</span></span>  
  
-   <span data-ttu-id="c4a56-137">Copie los datos en una tabla temporal (un montón).</span><span class="sxs-lookup"><span data-stu-id="c4a56-137">Copy data to a temporary table (a heap).</span></span>  
  
-   <span data-ttu-id="c4a56-138">Quite los objetos enlazados al esquema que hacen referencia a la tabla.</span><span class="sxs-lookup"><span data-stu-id="c4a56-138">Drop schema-bound objects referencing the table.</span></span>  
  
-   <span data-ttu-id="c4a56-139">Quite la tabla.</span><span class="sxs-lookup"><span data-stu-id="c4a56-139">Drop the table.</span></span>  
  
-   <span data-ttu-id="c4a56-140">Vuelva a crear la tabla con el nuevo esquema y aplique de nuevo los permisos.</span><span class="sxs-lookup"><span data-stu-id="c4a56-140">Recreate the table with the new schema and reapply permissions.</span></span>  
  
-   <span data-ttu-id="c4a56-141">Copie los datos de la tabla temporal en la tabla recién creada.</span><span class="sxs-lookup"><span data-stu-id="c4a56-141">Copy data from the temporary table to the recreated table.</span></span>  
  
-   <span data-ttu-id="c4a56-142">Vuelva a crear los objetos enlazados al esquema que hacen referencia a la tabla y sus permisos.</span><span class="sxs-lookup"><span data-stu-id="c4a56-142">Recreate schema-bound objects referencing the table and their permissions.</span></span>  
  
-   <span data-ttu-id="c4a56-143">Quite la tabla temporal.</span><span class="sxs-lookup"><span data-stu-id="c4a56-143">Drop the temporary table.</span></span>  
  
 <span data-ttu-id="c4a56-144">El script para el paso 4 debe actualizarse para reflejar los cambios deseados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="c4a56-144">The script for step 4 should be updated to reflect the desired schema changes.</span></span> <span data-ttu-id="c4a56-145">Si hay cambios en las columnas de la tabla, los scripts para los pasos 5 (copiar datos de la tabla temporal) y 6 (volver a crear los procedimientos almacenados) se deben actualizar según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c4a56-145">If there are any changes in the columns of the table, the scripts for steps 5 (copy data from temporary table) and 6 (recreate stored procedures) should be updated as necessary.</span></span>  
  
```powershell
# Prepare for schema changes by scripting out the table, as well as associated permissions
# Usage: prepare_schema_change.ps1 server_name db_name schema_name table_name  
# stop execution once an error occurs  
$ErrorActionPreference="Stop"  
  
if($args.Count -le 3)  
{  
   throw "Usage prepare_schema_change.ps1 server_name db_name schema_name table_name"  
}  
  
$servername = $args[0]  
$database = $args[1]  
$schema = $args[2]  
$object = $args[3]  
  
$object_heap = "$object$(Get-Random)"  
  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.SMO") | Out-Null  
  
$server =  New-Object ("Microsoft.SqlServer.Management.SMO.Server") ($servername)  
$scripter = New-Object ("Microsoft.SqlServer.Management.SMO.Scripter") ($server)  
  
## initialize table variable  
$tableUrn = $server.Databases[$database].Tables[$object, $schema]  
if($tableUrn.Count -eq 0)  
{  
   throw "Table or database not found"  
}  
  
## initialize scripting object  
$scriptingOptions = New-Object ("Microsoft.SqlServer.Management.SMO.ScriptingOptions")
$scriptingOptions.Permissions = $True  
$scriptingOptions.ScriptDrops = $True  
  
$scripter.Options = $scriptingOptions;  
  
Write-Host "(1) Scripting SELECT INTO $object_heap for table [$object] to 1_copy_to_heap_for_$schema`_$object.sql"  
Echo "SELECT * INTO $schema.$object_heap FROM $schema.$object WITH (SNAPSHOT)" | Out-File "1_copy_to_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(2) Scripting DROP for procs schema-bound to [$object] 2_drop_procs_$schema`_$object.sql"  
## query referencing schema-bound objects  
$dt = $server.Databases[$database].ExecuteWithResults("select r.referencing_schema_name, r.referencing_entity_name  
from sys.dm_sql_referencing_entities ('$schema.$object', 'OBJECT') as r join sys.sql_modules m on r.referencing_id=m.object_id  
where r.is_caller_dependent = 0 and m.is_schema_bound=1;")  
  
## initialize out file  
Echo "" | Out-File "2_drop_procs_$schema`_$object.sql"  
## loop through schema-bound objects  
ForEach ($t In $dt.Tables)  
{    
   ForEach ($r In $t.Rows)  
   {    
      ## script object   
      $so =  $server.Databases[$database].StoredProcedures[$r[1], $r[0]]  
      $scripter.Script($so) | Out-File -Append "2_drop_procs_$schema`_$object.sql"  
   }  
}  
Write-Host "--done--"  
Write-Host ""  
Write-Host "(3) Scripting DROP table for [$object] to 3_drop_table_$schema`_$object.sql"
$scripter.Script($tableUrn) | Out-File "3_drop_table_$schema`_$object.sql";
Write-Host "--done--"  
Write-Host ""  
  
## now script creates  
$scriptingOptions.ScriptDrops = $False  
  
Write-Host "(4) Scripting CREATE table and permissions for [$object] to !please_edit_4_create_table_$schema`_$object.sql"  
Write-Host "***** rename this script to 4_create_table.sql after completing the updates to the schema"
$scripter.Script($tableUrn) | Out-File "!please_edit_4_create_table_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(5) Scripting INSERT INTO table from heap and UPDATE STATISTICS for [$object] to 5_copy_from_heap_$schema`_$object.sql"  
Write-Host "[update this script if columns are added to or removed from the table]"  
Echo "INSERT INTO [$schema].[$object] SELECT * FROM [$schema].[$object_heap]; UPDATE STATISTICS [$schema].[$object] WITH FULLSCAN, NORECOMPUTE" | Out-File "5_copy_from_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(6) Scripting CREATE PROC and permissions for procedures schema-bound to [$object] to 6_create_procs_$schema`_$object.sql"  
Write-Host "[update the procedure definitions if columns are renamed or removed]"  
## initialize out file  
Echo "" | Out-File "6_create_procs_$schema`_$object.sql"  
## loop through schema-bound objects  
ForEach ($t In $dt.Tables)  
{    
   ForEach ($r In $t.Rows)  
   {    
      ## script the schema-bound object  
      $so =  $server.Databases[$database].StoredProcedures[$r[1], $r[0]]  
      ForEach($s In $scripter.Script($so))  
        {  
            Echo $s | Out-File -Append "6_create_procs_$schema`_$object.sql"  
            Echo "GO" | Out-File -Append "6_create_procs_$schema`_$object.sql"  
        }  
   }  
}  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(7) Scripting DROP $object_heap to 7_drop_heap_$schema`_$object.sql"  
Echo "DROP TABLE $schema.$object_heap" | Out-File "7_drop_heap_$schema`_$object.sql";  
Write-Host "--done--"  
Write-Host ""  
```  
  
 <span data-ttu-id="c4a56-146">El script de PowerShell siguiente ejecuta los cambios del esquema incluidos en el script del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="c4a56-146">The following PowerShell script executes the schema changes that were scripted in the previous sample.</span></span> <span data-ttu-id="c4a56-147">Este script toma como argumento una tabla, y ejecuta los scripts de cambio de esquema que se generaron para dicha tabla y los procedimientos almacenados asociados.</span><span class="sxs-lookup"><span data-stu-id="c4a56-147">This script takes as argument a table, and executes the schema change scripts that were generated for that table and the associated stored procedures.</span></span>  
  
 <span data-ttu-id="c4a56-148">Uso: execute_schema_change.ps1 *SERVER_NAME \* \* db_name `schema_name` TABLE_NAME*</span><span class="sxs-lookup"><span data-stu-id="c4a56-148">Usage: execute_schema_change.ps1 *server_name\*\*db_name`schema_name`table_name*</span></span>  
  
```powershell
# stop execution once an error occurs  
$ErrorActionPreference="Stop"  
  
if($args.Count -le 3)  
{  
   throw "Usage execute_schema_change.ps1 server_name db_name schema_name table_name"  
}  
  
$servername = $args[0]  
$database = $args[1]  
$schema = $args[2]  
$object = $args[3]  
  
[System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SqlServer.SMO") | Out-Null  
  
$server =  New-Object ("Microsoft.SqlServer.Management.SMO.Server") ($servername)  
$database = $server.Databases[$database]  
$table = $database.Tables[$object, $schema]  
if($table.Count -eq 0)  
{  
   throw "Table or database not found"  
}  
  
$1 = Get-Item "1_copy_to_heap_$schema`_$object.sql"  
$2 = Get-Item "2_drop_procs_$schema`_$object.sql"  
$3 = Get-Item "3_drop_table_$schema`_$object.sql"  
$4 = Get-Item "4_create_table_$schema`_$object.sql"  
$5 = Get-Item "5_copy_from_heap_$schema`_$object.sql"  
$6 = Get-Item "6_create_procs_$schema`_$object.sql"  
$7 = Get-Item "7_drop_heap_$schema`_$object.sql"  
  
Write-Host "(1) Running SELECT INTO heap for table [$object] from 1_copy_to_heap_for_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $1.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(2) Running DROP for procs schema-bound from [$object] 2_drop_procs_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $2.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(3) Running DROP table for [$object] to 4_drop_table_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $3.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(4) Running CREATE table and permissions for [$object] from 4_create_table_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $4.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(5) Running INSERT INTO table from heap for [$object] and UPDATE STATISTICS from 5_copy_from_heap_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $5.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(6) Running CREATE PROC and permissions for procedures schema-bound to [$object] from 6_create_procs_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $6.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
  
Write-Host "(7) Running DROP heap from 7_drop_heap_$schema`_$object.sql"  
$database.ExecuteNonQuery("$(Echo $7.OpenText().ReadToEnd())")  
Write-Host "--done--"  
Write-Host ""  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4a56-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c4a56-149">See Also</span></span>  
 [<span data-ttu-id="c4a56-150">Tablas optimizadas para la memoria</span><span class="sxs-lookup"><span data-stu-id="c4a56-150">Memory-Optimized Tables</span></span>](memory-optimized-tables.md)  
