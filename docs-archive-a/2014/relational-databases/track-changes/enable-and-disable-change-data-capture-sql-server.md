---
title: Habilitar y deshabilitar la captura de datos modificados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change data capture [SQL Server], enabling tables
- change data capture [SQL Server], enabling databases
- change data capture [SQL Server], disabling databases
- change data capture [SQL Server], disabling tables
ms.assetid: b741894f-d267-4b10-adfe-cbc14aa6caeb
author: rothja
ms.author: jroth
ms.openlocfilehash: df0a2fd4a2c6ffb2de58d6b52360d1730d0fa7df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672857"
---
# <a name="enable-and-disable-change-data-capture-sql-server"></a><span data-ttu-id="15886-102">Habilitar y deshabilitar la captura de datos modificados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="15886-102">Enable and Disable Change Data Capture (SQL Server)</span></span>
  <span data-ttu-id="15886-103">Este tema describe cómo habilitar y deshabilitar la captura de datos modificados para una tabla y una base de datos.</span><span class="sxs-lookup"><span data-stu-id="15886-103">This topic describes how to enable and disable change data capture for a database and a table.</span></span>  
  
## <a name="enable-change-data-capture-for-a-database"></a><span data-ttu-id="15886-104">Habilitar la captura de datos modificados en una base de datos</span><span class="sxs-lookup"><span data-stu-id="15886-104">Enable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="15886-105">Para que pueda crearse una instancia de captura para tablas individuales, es preciso que un miembro del rol fijo de servidor `sysadmin` habilite previamente la base de datos para la captura de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="15886-105">Before a capture instance can be created for individual tables, a member of the `sysadmin` fixed server role must first enable the database for change data capture.</span></span> <span data-ttu-id="15886-106">Esto se hace ejecutando el procedimiento almacenado [sys.sp_cdc_enable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) en el contexto de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="15886-106">This is done by running the stored procedure [sys.sp_cdc_enable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql) in the database context.</span></span> <span data-ttu-id="15886-107">Para determinar si una base de datos ya está habilitada, consulte la columna `is_cdc_enabled` en la vista de catálogo `sys.databases`.</span><span class="sxs-lookup"><span data-stu-id="15886-107">To determine if a database is already enabled, query the `is_cdc_enabled` column in the `sys.databases` catalog view.</span></span>  
  
 <span data-ttu-id="15886-108">Al habilitar una base de datos para la captura de datos modificados, se crean para la base de datos el esquema `cdc`, el usuario `cdc`, las tablas de metadatos y otros objetos de sistema.</span><span class="sxs-lookup"><span data-stu-id="15886-108">When a database is enabled for change data capture, the `cdc` schema, `cdc` user, metadata tables, and other system objects are created for the database.</span></span> <span data-ttu-id="15886-109">El esquema `cdc` contiene las tablas de metadatos de la captura de datos modificados y, una vez que las tablas de origen han sido habilitadas para esta captura, también contiene las tablas de cambios individuales que sirven como repositorio de los datos de cambios.</span><span class="sxs-lookup"><span data-stu-id="15886-109">The `cdc` schema contains the change data capture metadata tables and, after source tables are enabled for change data capture, the individual change tables serve as a repository for change data.</span></span> <span data-ttu-id="15886-110">Este esquema `cdc` también contiene las funciones de sistema asociadas que se usan para consultar los datos modificados.</span><span class="sxs-lookup"><span data-stu-id="15886-110">The `cdc` schema also contains associated system functions used to query for change data.</span></span>  
  
 <span data-ttu-id="15886-111">La captura de datos modificados requiere el uso exclusivo del esquema `cdc` y del usuario `cdc`.</span><span class="sxs-lookup"><span data-stu-id="15886-111">Change data capture requires exclusive use of the `cdc` schema and `cdc` user.</span></span> <span data-ttu-id="15886-112">Si en una base de datos existe un esquema o un usuario de base de datos denominado *cdc* , dicha base de datos no se puede habilitar para la captura de datos modificados hasta que el esquema y/o el usuario se quiten o se cambie su nombre.</span><span class="sxs-lookup"><span data-stu-id="15886-112">If either a schema or a database user named *cdc* currently exists in a database, the database cannot be enabled for change data capture until the schema and or user are dropped or renamed.</span></span>  
  
 <span data-ttu-id="15886-113">Vea la plantilla Habilitar una base de datos para la captura de datos modificados si desea obtener un ejemplo de cómo habilitar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="15886-113">See the Enable Database for Change Data Capture template for an example of enabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15886-114">Para buscar las plantillas en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vaya a **Ver**, haga clic en **Explorador de plantillas**y, a continuación, seleccione **Plantillas de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="15886-114">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then select **SQL Server Templates**.</span></span> <span data-ttu-id="15886-115">**Captura de datos modificados** es una subcarpeta.</span><span class="sxs-lookup"><span data-stu-id="15886-115">**Change Data Capture** is a sub-folder.</span></span> <span data-ttu-id="15886-116">Bajo esta carpeta, encontrará todas las plantillas a las que se hace referencia en este tema.</span><span class="sxs-lookup"><span data-stu-id="15886-116">Under this folder, you will find all the templates referenced in this topic.</span></span> <span data-ttu-id="15886-117">También existe un icono **Explorador de plantillas** en la barra de herramientas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15886-117">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- ====  
-- Enable Database for CDC template   
-- ====  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_db  
GO  
```  
  
## <a name="disable-change-data-capture-for-a-database"></a><span data-ttu-id="15886-118">Deshabilitar la captura de datos modificados para una base de datos</span><span class="sxs-lookup"><span data-stu-id="15886-118">Disable Change Data Capture for a Database</span></span>  
 <span data-ttu-id="15886-119">Un miembro del `sysadmin` rol fijo de servidor puede ejecutar el procedimiento almacenado [sys. sp_cdc_disable_db &#40;&#41;de TRANSACT-SQL](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) en el contexto de la base de datos para deshabilitar la captura de datos modificados en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="15886-119">A member of the `sysadmin` fixed server role can run the stored procedure [sys.sp_cdc_disable_db &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql) in the database context to disable change data capture for a database.</span></span> <span data-ttu-id="15886-120">No es necesario deshabilitar tablas individuales antes de deshabilitar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="15886-120">It is not necessary to disable individual tables before you disable the database.</span></span> <span data-ttu-id="15886-121">Cuando se deshabilita la base de datos, se quitan todos los metadatos de la captura de datos modificados asociados, incluidos el esquema y el usuario de `cdc` y los trabajos de captura de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="15886-121">Disabling the database removes all associated change data capture metadata, including the `cdc` user and schema and the change data capture jobs.</span></span> <span data-ttu-id="15886-122">Sin embargo, los roles de acceso creados por la captura de datos modificados no se quitarán automáticamente y se deben eliminar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="15886-122">However, any gating roles created by change data capture will not be removed automatically and must be explicitly deleted.</span></span> <span data-ttu-id="15886-123">Para determinar si una base de datos está habilitada, consulte la columna `is_cdc_enabled` en la vista de catálogo sys.databases.</span><span class="sxs-lookup"><span data-stu-id="15886-123">To determine if a database is enabled, query the `is_cdc_enabled` column in the sys.databases catalog view.</span></span>  
  
 <span data-ttu-id="15886-124">Si se quita una base de datos habilitada para la captura de datos modificados, se quitarán automáticamente los trabajos de captura de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="15886-124">If a change data capture enabled database is dropped, change data capture jobs are automatically removed.</span></span>  
  
 <span data-ttu-id="15886-125">Vea la plantilla Deshabilitar una base de datos para la captura de datos modificados si desea obtener un ejemplo de deshabilitación de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="15886-125">See the Disable Database for Change Data Capture template for an example of disabling a database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="15886-126">Para buscar las plantillas en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vaya a **Ver**, haga clic en **Explorador de plantillas**y, a continuación, haga clic en **Plantillas de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="15886-126">To locate the templates in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], go to **View**, click **Template Explorer**, and then click **SQL Server Templates**.</span></span> <span data-ttu-id="15886-127">**Captura de datos modificados** es una subcarpeta donde se pueden buscar todas las plantillas a las que se hace referencia en este tema.</span><span class="sxs-lookup"><span data-stu-id="15886-127">**Change Data Capture** is a sub-folder where you will find all the templates that are referenced in this topic.</span></span> <span data-ttu-id="15886-128">También existe un icono **Explorador de plantillas** en la barra de herramientas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15886-128">There is also a **Template Explorer** icon on the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] toolbar.</span></span>  
  
```sql  
-- =======  
-- Disable Database for Change Data Capture template   
-- =======  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_db  
GO  
```  
  
## <a name="enable-change-data-capture-for-a-table"></a><span data-ttu-id="15886-129">Habilitar la captura de datos modificados para una tabla</span><span class="sxs-lookup"><span data-stu-id="15886-129">Enable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="15886-130">Una vez se haya habilitado una base de datos para la captura de datos modificados, los miembros del rol fijo de base de datos `db_owner` pueden crear una instancia de captura para tablas de origen individuales mediante el procedimiento almacenado `sys.sp_cdc_enable_table`.</span><span class="sxs-lookup"><span data-stu-id="15886-130">After a database has been enabled for change data capture, members of the `db_owner` fixed database role can create a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_enable_table`.</span></span> <span data-ttu-id="15886-131">Para determinar si una tabla de origen se ha habilitado ya para la captura de datos modificados, examine la columna is_tracked_by_cdc en la vista de catálogo `sys.tables`.</span><span class="sxs-lookup"><span data-stu-id="15886-131">To determine whether a source table has already been enabled for change data capture, examine the is_tracked_by_cdc column in the `sys.tables` catalog view.</span></span>  
  
 <span data-ttu-id="15886-132">Se pueden especificar las opciones siguientes al crear una instancia de captura:</span><span class="sxs-lookup"><span data-stu-id="15886-132">The following options can be specified when creating a capture instance:</span></span>  
  
 <span data-ttu-id="15886-133">`Columns in the source table to be captured`.</span><span class="sxs-lookup"><span data-stu-id="15886-133">`Columns in the source table to be captured`.</span></span>  
  
 <span data-ttu-id="15886-134">De forma predeterminada, todas las columnas de la tabla de origen se identifican como columnas capturadas.</span><span class="sxs-lookup"><span data-stu-id="15886-134">By default, all of the columns in the source table are identified as captured columns.</span></span> <span data-ttu-id="15886-135">Si solo es necesario realizar un seguimiento de un subconjunto de columnas, por ejemplo, por motivos de privacidad o de rendimiento, use el *@captured_column_list* parámetro para especificar el subconjunto de columnas.</span><span class="sxs-lookup"><span data-stu-id="15886-135">If only a subset of columns need to be tracked, such as for privacy or performance reasons, use the *@captured_column_list* parameter to specify the subset of columns.</span></span>  
  
 `A filegroup to contain the change table.`  
  
 <span data-ttu-id="15886-136">De forma predeterminada, la tabla de cambios se encuentra en el grupo de archivos predeterminado de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="15886-136">By default, the change table is located in the default filegroup of the database.</span></span> <span data-ttu-id="15886-137">Los propietarios de bases de datos que quieran controlar la ubicación de las tablas de cambios individuales pueden usar el *@filegroup_name* parámetro para especificar un grupo de archivos determinado para la tabla de cambios asociada a la instancia de captura.</span><span class="sxs-lookup"><span data-stu-id="15886-137">Database owners who want to control the placement of individual change tables can use the *@filegroup_name* parameter to specify a particular filegroup for the change table associated with the capture instance.</span></span> <span data-ttu-id="15886-138">El grupo de archivos con nombre debe existir previamente.</span><span class="sxs-lookup"><span data-stu-id="15886-138">The named filegroup must already exist.</span></span> <span data-ttu-id="15886-139">Generalmente, se recomienda que las tablas de cambios se coloquen en un grupo de archivos independiente de las tablas de origen.</span><span class="sxs-lookup"><span data-stu-id="15886-139">Generally, it is recommended that change tables be placed in a filegroup separate from source tables.</span></span> <span data-ttu-id="15886-140">Vea la `Enable a Table Specifying Filegroup Option` plantilla para obtener un ejemplo que muestra el uso del *@filegroup_name* parámetro.</span><span class="sxs-lookup"><span data-stu-id="15886-140">See the `Enable a Table Specifying Filegroup Option` template for an example showing use of the *@filegroup_name* parameter.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Specifying Filegroup Option Template  
-- =========  
USE MyDB  
GO  
  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@filegroup_name = N'MyDB_CT',  
@supports_net_changes = 1  
GO  
```  
  
 `A role for controlling access to a change table.`  
  
 <span data-ttu-id="15886-141">La finalidad del rol con nombre es controlar el acceso a los datos de cambios.</span><span class="sxs-lookup"><span data-stu-id="15886-141">The purpose of the named role is to control access to the change data.</span></span> <span data-ttu-id="15886-142">El rol especificado puede ser un rol fijo de servidor existente o un rol de base de datos.</span><span class="sxs-lookup"><span data-stu-id="15886-142">The specified role can be an existing fixed server role or a database role.</span></span> <span data-ttu-id="15886-143">Si el rol especificado aún no existe, se crea automáticamente un rol de base de datos con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="15886-143">If the specified role does not already exist, a database role of that name is created automatically.</span></span> <span data-ttu-id="15886-144">Los miembros del rol `sysadmin` o `db_owner` tienen acceso total a los datos de las tablas de cambios.</span><span class="sxs-lookup"><span data-stu-id="15886-144">Members of either the `sysadmin` or `db_owner` role have full access to the data in the change tables.</span></span> <span data-ttu-id="15886-145">Los demás usuarios deben tener el permiso SELECT en todas las columnas capturadas de la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="15886-145">All other users must have SELECT permission on all the captured columns of the source table.</span></span> <span data-ttu-id="15886-146">Además, cuando se especifica un rol, los usuarios que no sean miembros del rol `sysadmin` o `db_owner` también deben ser miembros del rol especificado.</span><span class="sxs-lookup"><span data-stu-id="15886-146">In addition, when a role is specified, users who are not members of either the `sysadmin` or `db_owner` role must also be members of the specified role.</span></span>  
  
 <span data-ttu-id="15886-147">Si no desea usar un rol de acceso, establezca explícitamente el *@role_name* parámetro en NULL.</span><span class="sxs-lookup"><span data-stu-id="15886-147">If you do not want to use a gating role, explicitly set the *@role_name* parameter to NULL.</span></span> <span data-ttu-id="15886-148">Vea la plantilla `Enable a Table Without Using a Gating Role` para obtener un ejemplo de cómo habilitar una tabla sin un rol de acceso.</span><span class="sxs-lookup"><span data-stu-id="15886-148">See the `Enable a Table Without Using a Gating Role` template for an example of enabling a table without a gating role.</span></span>  
  
```sql  
-- =========  
-- Enable a Table Without Using a Gating Role template   
-- =========  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = NULL,  
@supports_net_changes = 1  
GO  
  
```  
  
 `A function to query for net changes.`  
  
 <span data-ttu-id="15886-149">Una instancia de captura siempre incluirá una función con valores de tabla para devolver todas las entradas de la tabla de cambios que se produjeron dentro de un intervalo definido.</span><span class="sxs-lookup"><span data-stu-id="15886-149">A capture instance will always include a table valued function for returning all change table entries that occurred within a defined interval.</span></span> <span data-ttu-id="15886-150">Esta función se denomina anexando el nombre de la instancia de captura a "cdc.fn_cdc_get_all_changes_".</span><span class="sxs-lookup"><span data-stu-id="15886-150">This function is named by appending the capture instance name to "cdc.fn_cdc_get_all_changes_".</span></span> <span data-ttu-id="15886-151">Para obtener más información, vea [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15886-151">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="15886-152">Si el parámetro *@supports_net_changes* se establece en 1, también se genera una función net Changes para la instancia de captura.</span><span class="sxs-lookup"><span data-stu-id="15886-152">If the parameter *@supports_net_changes* is set to 1, a net changes function is also generated for the capture instance.</span></span> <span data-ttu-id="15886-153">Esta función devuelve solo un cambio por cada fila distinta que haya cambiado en el intervalo especificado en la llamada.</span><span class="sxs-lookup"><span data-stu-id="15886-153">This function returns only one change for each distinct row changed in the interval specified in the call.</span></span> <span data-ttu-id="15886-154">Para obtener más información, vea [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="15886-154">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="15886-155">Para poder usar las consultas net changes, la tabla de origen debe tener una clave principal o un índice único que identifique las filas de forma única.</span><span class="sxs-lookup"><span data-stu-id="15886-155">To support net changes queries, the source table must have a primary key or unique index to uniquely identify rows.</span></span> <span data-ttu-id="15886-156">Si se usa un índice único, el nombre del índice se debe especificar con el *@index_name* parámetro.</span><span class="sxs-lookup"><span data-stu-id="15886-156">If a unique index is used, the name of the index must be specified using the *@index_name* parameter.</span></span> <span data-ttu-id="15886-157">Las columnas definidas en la clave principal o índice único deben estar incluidas en la lista de columnas de origen que se van a capturar.</span><span class="sxs-lookup"><span data-stu-id="15886-157">The columns defined in the primary key or unique index must be included in the list of source columns to be captured.</span></span>  
  
 <span data-ttu-id="15886-158">Vea la plantilla `Enable a Table for All and Net Changes Queries` para obtener un ejemplo que muestre la creación de una instancia de captura con ambas funciones de consulta.</span><span class="sxs-lookup"><span data-stu-id="15886-158">See the `Enable a Table for All and Net Changes Queries` template for an example demonstrating the creation of a capture instance with both query functions.</span></span>  
  
```sql  
-- =============  
-- Enable a Table for All and Net Changes Queries template   
-- =============  
USE MyDB  
GO  
EXEC sys.sp_cdc_enable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@role_name     = N'MyRole',  
@supports_net_changes = 1  
GO  
```  
  
> [!NOTE]
>  <span data-ttu-id="15886-159">Si la captura de datos modificados está habilitada en una tabla con una clave principal existente y el *@index_name* parámetro no se usa para identificar un índice único alternativo, la característica de captura de datos modificados usará la clave principal.</span><span class="sxs-lookup"><span data-stu-id="15886-159">If change data capture is enabled on a table with an existing primary key, and the *@index_name* parameter is not used to identify an alternative unique index, the change data capture feature will use the primary key.</span></span> <span data-ttu-id="15886-160">Los cambios subsiguientes en la clave principal no se permitirán sin deshabilitar primero la captura de datos modificados para la tabla.</span><span class="sxs-lookup"><span data-stu-id="15886-160">Subsequent changes to the primary key will not be allowed without first disabling change data capture for the table.</span></span> <span data-ttu-id="15886-161">Esto es así independientemente de si se solicitó compatibilidad con las consultas net changes cuando se configuró la captura de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="15886-161">This is true regardless of whether support for net changes queries was requested when change data capture was configured.</span></span> <span data-ttu-id="15886-162">Si no hay ninguna clave principal en una tabla en el momento en que se habilita para la captura de datos modificados, la captura de datos modificados omite la incorporación posterior de una clave principal.</span><span class="sxs-lookup"><span data-stu-id="15886-162">If there is no primary key on a table at the time it is enabled for change data capture, the subsequent addition of a primary key is ignored by change data capture.</span></span> <span data-ttu-id="15886-163">Dado que la captura de datos modificados no utilizará ninguna clave principal que se cree una vez habilitada la tabla, las columnas de clave y la clave se pueden quitar sin restricciones.</span><span class="sxs-lookup"><span data-stu-id="15886-163">Because change data capture will not use a primary key that is created after the table was enabled, the key and key columns can be removed without restrictions.</span></span>  
  
## <a name="disable-change-data-capture-for-a-table"></a><span data-ttu-id="15886-164">Deshabilitar la captura de datos modificados para una tabla</span><span class="sxs-lookup"><span data-stu-id="15886-164">Disable Change Data Capture for a Table</span></span>  
 <span data-ttu-id="15886-165">Los miembros del rol fijo de base de datos `db_owner` pueden quitar una instancia de captura para las tablas de origen individuales utilizando el procedimiento almacenado `sys.sp_cdc_disable_table`.</span><span class="sxs-lookup"><span data-stu-id="15886-165">Members of the `db_owner` fixed database role can remove a capture instance for individual source tables by using the stored procedure `sys.sp_cdc_disable_table`.</span></span> <span data-ttu-id="15886-166">Para determinar si una tabla de origen está habilitada actualmente para la captura de datos modificados, examine la columna `is_tracked_by_cdc` en la vista de catálogo `sys.tables`.</span><span class="sxs-lookup"><span data-stu-id="15886-166">To determine whether a source table is currently enabled for change data capture, examine the `is_tracked_by_cdc` column in the `sys.tables` catalog view.</span></span> <span data-ttu-id="15886-167">Si no hay ninguna tabla habilitada para la base de datos después de que tenga lugar la deshabilitación, también se quitarán los trabajos de captura de datos modificados.</span><span class="sxs-lookup"><span data-stu-id="15886-167">If there are no tables enabled for the database after the disabling takes place, the change data capture jobs are also removed.</span></span>  
  
 <span data-ttu-id="15886-168">Si quita una tabla habilitada para la captura de datos modificados, se quitarán automáticamente los metadatos de la captura de datos modificados que están asociados a la tabla.</span><span class="sxs-lookup"><span data-stu-id="15886-168">If a change data capture-enabled table is dropped, change data capture metadata that is associated with the table is automatically removed.</span></span>  
  
 <span data-ttu-id="15886-169">Vea la plantilla Deshabilitar una instancia de captura para una tabla si desea obtener un ejemplo de deshabilitación de una tabla.</span><span class="sxs-lookup"><span data-stu-id="15886-169">See the Disable a Capture Instance for a Table template for an example of disabling a table.</span></span>  
  
```sql  
-- =====  
-- Disable a Capture Instance for a Table template   
-- =====  
USE MyDB  
GO  
EXEC sys.sp_cdc_disable_table  
@source_schema = N'dbo',  
@source_name   = N'MyTable',  
@capture_instance = N'dbo_MyTable'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="15886-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15886-170">See Also</span></span>  
 <span data-ttu-id="15886-171">[Seguimiento de cambios de datos &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15886-171">[Track Data Changes &#40;SQL Server&#41;](track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="15886-172">[Acerca de la captura de datos modificados &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15886-172">[About Change Data Capture &#40;SQL Server&#41;](../track-changes/about-change-data-capture-sql-server.md) </span></span>  
 <span data-ttu-id="15886-173">[Trabajar con datos modificados &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15886-173">[Work with Change Data &#40;SQL Server&#41;](work-with-change-data-sql-server.md) </span></span>  
 [<span data-ttu-id="15886-174">Administrar y supervisar la captura de datos modificados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="15886-174">Administer and Monitor Change Data Capture &#40;SQL Server&#41;</span></span>](../track-changes/administer-and-monitor-change-data-capture-sql-server.md)  
  
  
