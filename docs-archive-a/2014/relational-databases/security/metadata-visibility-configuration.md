---
title: Configuración de visibilidad de los metadatos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- subcomponents visibility [SQL Server]
- metadata [SQL Server], visibility
- permissions [SQL Server], metadata access
- viewing metadata
- objects [SQL Server], metadata
- displaying metadata
- database metadata [SQL Server]
- metadata [SQL Server], permissions
ms.assetid: 50d2e015-05ae-4014-a1cd-4de7866ad651
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 5198dc4ba4e81bc1d7a8dd2411da59da81596102
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673602"
---
# <a name="metadata-visibility-configuration"></a><span data-ttu-id="3f7f7-102">Configuración de visibilidad de los metadatos</span><span class="sxs-lookup"><span data-stu-id="3f7f7-102">Metadata Visibility Configuration</span></span>
  <span data-ttu-id="3f7f7-103">La visibilidad de los metadatos se limita a los elementos protegibles que son propiedad de un usuario o sobre los que el usuario tienen algún permiso.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-103">The visibility of metadata is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="3f7f7-104">Por ejemplo, la siguiente consulta devuelve una fila si se ha concedido al usuario un permiso como SELECT o INSERT sobre la tabla `myTable`.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-104">For example, the following query returns a row if the user has been granted a permission such as SELECT or INSERT on the table `myTable`.</span></span>  
  
```  
SELECT name, object_id  
FROM sys.tables  
WHERE name = 'myTable';  
GO  
```  
  
 <span data-ttu-id="3f7f7-105">Sin embargo, si el usuario no dispone de ningún permiso sobre `myTable`, la consulta devuelve un conjunto de resultados vacío.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-105">However, if the user does not have any permission on `myTable`, the query returns an empty result set.</span></span>  
  
## <a name="scope-and-impact-of-metadata-visibility-configuration"></a><span data-ttu-id="3f7f7-106">Ámbito e impacto de la configuración de visibilidad de los metadatos</span><span class="sxs-lookup"><span data-stu-id="3f7f7-106">Scope and Impact of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="3f7f7-107">La configuración de visibilidad de los metadatos solo se aplica a los siguientes elementos protegibles:</span><span class="sxs-lookup"><span data-stu-id="3f7f7-107">Metadata visibility configuration only applies to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f7f7-108">Vistas de catálogo</span><span class="sxs-lookup"><span data-stu-id="3f7f7-108">Catalog views</span></span>|<span data-ttu-id="3f7f7-109">Procedimientos almacenados **sp_help** de [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f7f7-109">[!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures</span></span>|  
|<span data-ttu-id="3f7f7-110">Funciones integradas que exponen metadatos</span><span class="sxs-lookup"><span data-stu-id="3f7f7-110">Metadata exposing built-in functions</span></span>|<span data-ttu-id="3f7f7-111">Vistas de esquema de información</span><span class="sxs-lookup"><span data-stu-id="3f7f7-111">Information schema views</span></span>|  
|<span data-ttu-id="3f7f7-112">Vistas de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="3f7f7-112">Compatibility views</span></span>|<span data-ttu-id="3f7f7-113">Propiedades extendidas</span><span class="sxs-lookup"><span data-stu-id="3f7f7-113">Extended properties</span></span>|  
  
 <span data-ttu-id="3f7f7-114">La configuración de visibilidad de los metadatos no se aplica a los siguientes elementos protegibles:</span><span class="sxs-lookup"><span data-stu-id="3f7f7-114">Metadata visibility configuration does not apply to the following securables.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f7f7-115">Tablas de sistema de trasvase de registros</span><span class="sxs-lookup"><span data-stu-id="3f7f7-115">Log shipping system tables</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3f7f7-116">Tablas de sistema del Agente</span><span class="sxs-lookup"><span data-stu-id="3f7f7-116">Agent system tables</span></span>|  
|<span data-ttu-id="3f7f7-117">Tablas de sistema de planes de mantenimiento de bases de datos</span><span class="sxs-lookup"><span data-stu-id="3f7f7-117">Database maintenance plan system tables</span></span>|<span data-ttu-id="3f7f7-118">Tablas de sistema de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="3f7f7-118">Backup system tables</span></span>|  
|<span data-ttu-id="3f7f7-119">Tablas de sistema de replicación</span><span class="sxs-lookup"><span data-stu-id="3f7f7-119">Replication system tables</span></span>|<span data-ttu-id="3f7f7-120">Procedimientos almacenados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sp_help **de replicación y del Agente**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-120">Replication and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent **sp_help** stored procedures</span></span>|  
  
 <span data-ttu-id="3f7f7-121">Una accesibilidad limitada a los metadatos significa lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3f7f7-121">Limited metadata accessibility means the following:</span></span>  
  
-   <span data-ttu-id="3f7f7-122">Las aplicaciones que asuman un acceso **public** a los metadatos se interrumpirán.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-122">Applications that assume **public** metadata access will break.</span></span>  
  
-   <span data-ttu-id="3f7f7-123">Las consultas que se realicen en vistas del sistema puede que solo devuelvan un subconjunto de filas o, en ocasiones, un conjunto de resultados vacío.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-123">Queries on system views might only return a subset of rows, or sometimes an empty result set.</span></span>  
  
-   <span data-ttu-id="3f7f7-124">Las funciones integradas que emiten metadatos, como OBJECTPROPERTYEX, pueden devolver NULL.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-124">Metadata-emitting, built-in functions such as OBJECTPROPERTYEX may return NULL.</span></span>  
  
-   <span data-ttu-id="3f7f7-125">Los procedimientos almacenados **sp_help** de [!INCLUDE[ssDE](../../includes/ssde-md.md)] pueden devolver únicamente un subconjunto de filas, o NULL.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-125">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] **sp_help** stored procedures might return only a subset of rows, or NULL.</span></span>  
  
 <span data-ttu-id="3f7f7-126">Los módulos SQL, como procedimientos almacenados y desencadenadores, se ejecutan en el contexto de seguridad del autor de la llamada y, por tanto, tienen un acceso limitado a los metadatos.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-126">SQL modules, such as stored procedures and triggers, run under the security context of the caller and, therefore, have limited metadata accessibility.</span></span> <span data-ttu-id="3f7f7-127">Por ejemplo, en el siguiente código, cuando el procedimiento almacenado intenta obtener acceso a los metadatos de la tabla `myTable` sobre la que el autor de la llamada no tienen ningún derecho, se devuelve un conjunto de resultados vacío.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-127">For example, in the following code, when the stored procedure tries to access metadata for the table `myTable` on which the caller has no rights, an empty result set is returned.</span></span> <span data-ttu-id="3f7f7-128">En versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]se devuelve una fila.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-128">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a row is returned.</span></span>  
  
```  
CREATE PROCEDURE assumes_caller_can_access_metadata  
BEGIN  
SELECT name, id   
FROM sysobjects   
WHERE name = 'myTable';  
END;  
GO  
```  
  
 <span data-ttu-id="3f7f7-129">Para permitir que los autores de la llamada vean los metadatos, puede concederles un permiso VIEW DEFINITION en un ámbito adecuado: nivel de objeto, base de datos o servidor.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-129">To allow callers to view metadata, you can grant the callers VIEW DEFINITION permission at an appropriate scope: object level, database level or server level.</span></span> <span data-ttu-id="3f7f7-130">Por lo tanto, en el ejemplo anterior, si el autor de la llamada dispone de permiso VIEW DEFINITION sobre `myTable`, el procedimiento almacenado devuelve una fila.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-130">Therefore, in the previous example, if the caller has VIEW DEFINITION permission on `myTable`, the stored procedure returns a row.</span></span> <span data-ttu-id="3f7f7-131">Para obtener más información, vea [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) y [GRANT &#40;permisos de base de datos de Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3f7f7-131">For more information, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) and [GRANT Database Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-database-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="3f7f7-132">También puede modificar el procedimiento almacenado para que se ejecute bajo las credenciales del propietario.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-132">You can also modify the stored procedure so that it executes under the credentials of the owner.</span></span> <span data-ttu-id="3f7f7-133">Cuando el propietario del procedimiento y el propietario de la tabla son el mismo, se aplica el encadenamiento de propiedad, y el contexto de seguridad del propietario del procedimiento permite el acceso a los metadatos de `myTable`.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-133">When the procedure owner and the table owner are the same owner, ownership chaining applies, and the security context of the procedure owner enables access to the metadata for `myTable`.</span></span> <span data-ttu-id="3f7f7-134">En un escenario de este tipo, el siguiente código devuelve una fila de metadatos al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-134">Under this scenario, the following code returns a row of metadata to the caller.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f7f7-135">En el siguiente ejemplo se usa la vista de catálogo [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) en lugar de la vista de compatibilidad [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="3f7f7-135">The following example uses the [sys.objects](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql) catalog view instead of the [sys.sysobjects](/sql/relational-databases/system-compatibility-views/sys-sysobjects-transact-sql) compatibility view.</span></span>  
  
```  
CREATE PROCEDURE does_not_assume_caller_can_access_metadata  
WITH EXECUTE AS OWNER  
AS  
BEGIN  
SELECT name, id  
FROM sys.objects   
WHERE name = 'myTable'   
END;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3f7f7-136">Puede utilizar EXECUTE AS para cambiar temporalmente al contexto de seguridad del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-136">You can use EXECUTE AS to temporarily switch to the security context of the caller.</span></span> <span data-ttu-id="3f7f7-137">Para obtener más información, vea [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3f7f7-137">For more information, see [EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-transact-sql).</span></span>  
  
## <a name="benefits-and-limits-of-metadata-visibility-configuration"></a><span data-ttu-id="3f7f7-138">Beneficios y límites de la configuración de visibilidad de los metadatos</span><span class="sxs-lookup"><span data-stu-id="3f7f7-138">Benefits and Limits of Metadata Visibility Configuration</span></span>  
 <span data-ttu-id="3f7f7-139">La configuración de visibilidad de los metadatos puede desempeñar un rol importante en el plan de seguridad global.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-139">Metadata visibility configuration can play an important role in your overall security plan.</span></span> <span data-ttu-id="3f7f7-140">Sin embargo, hay casos en los que un usuario con conocimientos y determinación puede forzar la divulgación de algunos metadatos.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-140">However, there are cases in which a skilled and determined user can force the disclosure of some metadata.</span></span> <span data-ttu-id="3f7f7-141">Es recomendable implementar permisos sobre los metadatos como una de las distintas medidas de defensa más completa.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-141">We recommend that you deploy metadata permissions as one of many defenses-in-depth.</span></span>  
  
 <span data-ttu-id="3f7f7-142">Teóricamente, es posible forzar la emisión de metadatos en los mensajes de error mediante la manipulación del orden de evaluación de predicados en las consultas.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-142">It is theoretically possible to force the emission of metadata in error messages by manipulating the order of predicate evaluation in queries.</span></span> <span data-ttu-id="3f7f7-143">La posibilidad de estos *ataques de prueba y error* no es específica de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3f7f7-143">The possibility of such *trial-and-error attacks* is not specific to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3f7f7-144">Es una implicación de las transformaciones asociativas y conmutativas que admite el álgebra relacional.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-144">It is implied by the associative and commutative transformations permitted in relational algebra.</span></span> <span data-ttu-id="3f7f7-145">Puede mitigar este riesgo mediante la limitación de la información que se devuelve en los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-145">You can mitigate this risk by limiting the information returned in error messages.</span></span> <span data-ttu-id="3f7f7-146">Para restringir más la visibilidad de metadatos de esta manera, puede iniciar el servidor con la marca de seguimiento 3625.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-146">To further restrict the visibility of metadata in this way, you can start the server with trace flag 3625.</span></span> <span data-ttu-id="3f7f7-147">Esta marca de seguimiento limita la cantidad de información que se muestra en los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-147">This trace flag limits the amount of information shown in error messages.</span></span> <span data-ttu-id="3f7f7-148">A su vez, ayuda a evitar divulgaciones forzadas.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-148">In turn, this helps to prevent forced disclosures.</span></span> <span data-ttu-id="3f7f7-149">La contrapartida es que los mensajes de error se simplificarán y puede resultar difícil su uso para fines de depuración.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-149">The tradeoff is that error messages will be terse and might be difficult to use for debugging purposes.</span></span> <span data-ttu-id="3f7f7-150">Para obtener más información, vea [Opciones de inicio del servicio de motor de base de datos](../../database-engine/configure-windows/database-engine-service-startup-options.md) y [Marcas de seguimiento &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3f7f7-150">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md) and [Trace Flags &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-traceon-trace-flags-transact-sql).</span></span>  
  
 <span data-ttu-id="3f7f7-151">Los metadatos que se muestran a continuación no están sujetos a una divulgación forzada:</span><span class="sxs-lookup"><span data-stu-id="3f7f7-151">The following metadata is not subject to forced disclosure:</span></span>  
  
-   <span data-ttu-id="3f7f7-152">El valor almacenado en la columna **provider_string** de **sys.servers**.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-152">The value stored in the **provider_string** column of **sys.servers**.</span></span> <span data-ttu-id="3f7f7-153">Un usuario que no disponga de permiso ALTER ANY LINKED SERVER verá un valor NULL en esta columna.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-153">A user that does not have ALTER ANY LINKED SERVER permission will see a NULL value in this column.</span></span>  
  
-   <span data-ttu-id="3f7f7-154">La definición de origen de un objeto especificado por el usuario, como un procedimiento almacenado o desencadenador.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-154">Source definition of a user-defined object such as a stored procedure or trigger.</span></span> <span data-ttu-id="3f7f7-155">El código fuente solo es visible cuando una de las siguientes afirmaciones es cierta:</span><span class="sxs-lookup"><span data-stu-id="3f7f7-155">The source code is visible only when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="3f7f7-156">El usuario dispone de permiso VIEW DEFINITION sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-156">The user has VIEW DEFINITION permission on the object.</span></span>  
  
    -   <span data-ttu-id="3f7f7-157">No se ha denegado al usuario el permiso VIEW DEFINITION sobre el objeto y dispone de permiso CONTROL, ALTER o TAKE OWNERSHIP sobre el objeto.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-157">The user has not been denied VIEW DEFINITION permission on the object and has CONTROL, ALTER, or TAKE OWNERSHIP permission on the object.</span></span> <span data-ttu-id="3f7f7-158">El resto de usuarios verán NULL.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-158">All other users will see NULL.</span></span>  
  
-   <span data-ttu-id="3f7f7-159">Las columnas de definición de las siguientes vistas de catálogo:</span><span class="sxs-lookup"><span data-stu-id="3f7f7-159">The definition columns found in the following catalog views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="3f7f7-160">**sys.all_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-160">**sys.all_sql_modules**</span></span>|<span data-ttu-id="3f7f7-161">**sys.sql_modules**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-161">**sys.sql_modules**</span></span>|  
    |<span data-ttu-id="3f7f7-162">**sys.server_sql_modules**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-162">**sys.server_sql_modules**</span></span>|<span data-ttu-id="3f7f7-163">**sys.check_constraints**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-163">**sys.check_constraints**</span></span>|  
    |<span data-ttu-id="3f7f7-164">**sys.default_constraints**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-164">**sys.default_constraints**</span></span>|<span data-ttu-id="3f7f7-165">**sys.computed_columns**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-165">**sys.computed_columns**</span></span>|  
    |<span data-ttu-id="3f7f7-166">**sys.numbered_procedures**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-166">**sys.numbered_procedures**</span></span>||  
  
-   <span data-ttu-id="3f7f7-167">La columna **ctext** de la vista de compatibilidad **syscomments** .</span><span class="sxs-lookup"><span data-stu-id="3f7f7-167">The **ctext** column in the **syscomments** compatibility view.</span></span>  
  
-   <span data-ttu-id="3f7f7-168">El resultado del procedimiento **sp_helptext** .</span><span class="sxs-lookup"><span data-stu-id="3f7f7-168">The output of the **sp_helptext** procedure.</span></span>  
  
-   <span data-ttu-id="3f7f7-169">Las siguientes columnas de las vistas de esquema de información:</span><span class="sxs-lookup"><span data-stu-id="3f7f7-169">The following columns in the information schema views:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="3f7f7-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span><span class="sxs-lookup"><span data-stu-id="3f7f7-170">INFORMATION_SCHEMA.CHECK_CONSTRAINTS.CHECK_CLAUSE</span></span>|<span data-ttu-id="3f7f7-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="3f7f7-171">INFORMATION_SCHEMA.COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="3f7f7-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="3f7f7-172">INFORMATION_SCHEMA.DOMAINS.DOMAIN_DEFAULT</span></span>|<span data-ttu-id="3f7f7-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="3f7f7-173">INFORMATION_SCHEMA.ROUTINE_COLUMNS.COLUMN_DEFAULT</span></span>|  
    |<span data-ttu-id="3f7f7-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="3f7f7-174">INFORMATION_SCHEMA.ROUTINES.ROUTINE_DEFINITION</span></span>|<span data-ttu-id="3f7f7-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="3f7f7-175">INFORMATION_SCHEMA.VIEWS.VIEW_DEFINITION</span></span>|  
  
-   <span data-ttu-id="3f7f7-176">La función OBJECT_DEFINITION()</span><span class="sxs-lookup"><span data-stu-id="3f7f7-176">OBJECT_DEFINITION() function</span></span>  
  
-   <span data-ttu-id="3f7f7-177">El valor almacenado en la columna password_hash de **sys.sql_logins**.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-177">The value stored in the password_hash column of **sys.sql_logins**.</span></span>  <span data-ttu-id="3f7f7-178">Un usuario que no tenga un permiso CONTROL SERVER verá un valor NULL en esta columna.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-178">A user that does not have CONTROL SERVER permission will see a NULL value in this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3f7f7-179">Las definiciones SQL de procedimientos y funciones del sistema integrados son visibles de forma pública a través de la vista de catálogo **sys.system_sql_modules** , el procedimiento almacenado **sp_helptext** y la función OBJECT_DEFINITION().</span><span class="sxs-lookup"><span data-stu-id="3f7f7-179">The SQL definitions of built-in system procedures and functions are publicly visible through the **sys.system_sql_modules** catalog view, the **sp_helptext** stored procedure, and the OBJECT_DEFINITION() function.</span></span>  
  
## <a name="general-principles-of-metadata-visibility"></a><span data-ttu-id="3f7f7-180">Principios generales de visibilidad de los metadatos</span><span class="sxs-lookup"><span data-stu-id="3f7f7-180">General Principles of Metadata Visibility</span></span>  
 <span data-ttu-id="3f7f7-181">A continuación, se muestran algunos de los principios generales que hay que tener en cuenta de cara a la visibilidad de los metadatos:</span><span class="sxs-lookup"><span data-stu-id="3f7f7-181">The following are some general principles to consider regarding metadata visibility:</span></span>  
  
-   <span data-ttu-id="3f7f7-182">Permisos implícitos de roles fijos</span><span class="sxs-lookup"><span data-stu-id="3f7f7-182">Fixed roles implicit permissions</span></span>  
  
-   <span data-ttu-id="3f7f7-183">Ámbito de los permisos</span><span class="sxs-lookup"><span data-stu-id="3f7f7-183">Scope of permissions</span></span>  
  
-   <span data-ttu-id="3f7f7-184">Prioridad de DENY</span><span class="sxs-lookup"><span data-stu-id="3f7f7-184">Precedence of DENY</span></span>  
  
-   <span data-ttu-id="3f7f7-185">Visibilidad de los metadatos de subcomponentes</span><span class="sxs-lookup"><span data-stu-id="3f7f7-185">Visibility of subcomponent metadata</span></span>  
  
### <a name="fixed-roles-and-implicit-permissions"></a><span data-ttu-id="3f7f7-186">Roles fijos y permisos implícitos</span><span class="sxs-lookup"><span data-stu-id="3f7f7-186">Fixed Roles and Implicit Permissions</span></span>  
 <span data-ttu-id="3f7f7-187">Los metadatos a los que pueden obtener acceso los roles fijos dependen de sus permisos implícitos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-187">Metadata that can be accessed by fixed roles depends upon their corresponding implicit permissions.</span></span>  
  
### <a name="scope-of-permissions"></a><span data-ttu-id="3f7f7-188">Ámbito de los permisos</span><span class="sxs-lookup"><span data-stu-id="3f7f7-188">Scope of Permissions</span></span>  
 <span data-ttu-id="3f7f7-189">Los permisos de un ámbito implican la posibilidad de ver los metadatos en dicho ámbito y en todos los ámbitos incluidos en el mismo.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-189">Permissions at one scope imply the ability to see metadata at that scope and at all enclosed scopes.</span></span> <span data-ttu-id="3f7f7-190">Por ejemplo, el permiso SELECT sobre un esquema implica que el receptor dispone del permiso SELECT sobre todos los elementos protegibles incluidos en dicho esquema.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-190">For example, SELECT permission on a schema implies that the grantee has SELECT permission on all securables that are contained by that schema.</span></span> <span data-ttu-id="3f7f7-191">Por tanto, la concesión del permiso SELECT sobre un esquema permite al usuario ver los metadatos del esquema y todas las tablas, vistas, funciones, procedimientos, colas, sinónimos, tipos y colecciones de esquemas XML que estén incluidos en el mismo.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-191">The granting of SELECT permission on a schema therefore enables a user to see the metadata of the schema and also all tables, views, functions, procedures, queues, synonyms, types, and XML schema collections within it.</span></span> <span data-ttu-id="3f7f7-192">Para obtener más información sobre ámbitos, vea [Jerarquía de permisos &#40;motor de base de datos&#41;](permissions-hierarchy-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="3f7f7-192">For more information about scopes, see [Permissions Hierarchy &#40;Database Engine&#41;](permissions-hierarchy-database-engine.md).</span></span>  
  
### <a name="precedence-of-deny"></a><span data-ttu-id="3f7f7-193">Prioridad de DENY</span><span class="sxs-lookup"><span data-stu-id="3f7f7-193">Precedence of DENY</span></span>  
 <span data-ttu-id="3f7f7-194">Normalmente, DENY tiene prioridad sobre otros permisos.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-194">DENY typically takes precedence over other permissions.</span></span> <span data-ttu-id="3f7f7-195">Por ejemplo, si se concede a un usuario de la base de datos el permiso EXECUTE sobre un esquema, pero se le deniega el permiso EXECUTE sobre un procedimiento almacenado de dicho esquema, el usuario no podrá ver los metadatos de dicho procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-195">For example, if a database user is granted EXECUTE permission on a schema but has been denied EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="3f7f7-196">Además, si a un usuario se le deniega el permiso EXECUTE sobre un esquema pero se le concede el permiso EXECUTE sobre un procedimiento almacenado de dicho esquema, el usuario no podrá ver los metadatos de dicho procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-196">Additionally, if a user is denied EXECUTE permission on a schema but has been granted EXECUTE permission on a stored procedure in that schema, the user cannot view the metadata for that stored procedure.</span></span>  
  
 <span data-ttu-id="3f7f7-197">Otro ejemplo sería que a un usuario se le concediese y denegase a la vez el permiso EXECUTE sobre un procedimiento almacenado (esto es posible a través de la pertenencia a distintos roles); en este caso, DENY tendría prioridad y el usuario no podría ver los metadatos del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-197">For another example, if a user has been granted and denied EXECUTE permission on a stored procedure, which is possible through your various role memberships, DENY takes precedence and the user cannot view the metadata of the stored procedure.</span></span>  
  
### <a name="visibility-of-subcomponent-metadata"></a><span data-ttu-id="3f7f7-198">Visibilidad de los metadatos de subcomponentes</span><span class="sxs-lookup"><span data-stu-id="3f7f7-198">Visibility of Subcomponent Metadata</span></span>  
 <span data-ttu-id="3f7f7-199">La visibilidad de subcomponentes, como índices, restricciones CHECK y desencadenadores, viene determinada por los permisos del elemento principal.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-199">The visibility of subcomponents, such as indexes, check constraints, and triggers is determined by permissions on the parent.</span></span> <span data-ttu-id="3f7f7-200">Estos subcomponentes no disponen de permisos que puedan concederse.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-200">These subcomponents do not have grantable permissions.</span></span> <span data-ttu-id="3f7f7-201">Por ejemplo, si a un usuario se le concede algún permiso sobre una tabla, el usuario podrá ver los metadatos de las tablas, columnas, índices, restricciones CHECK, desencadenadores y otros subcomponentes de este tipo.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-201">For example, if a user has been granted some permission on a table, the user can view the metadata for the tables, columns, indexes, check constraints, triggers, and other such subcomponents.</span></span>  
  
#### <a name="metadata-that-is-accessible-to-all-database-users"></a><span data-ttu-id="3f7f7-202">Metadatos a los que pueden obtener acceso todos los usuarios de la base de datos</span><span class="sxs-lookup"><span data-stu-id="3f7f7-202">Metadata That Is Accessible to All Database Users</span></span>  
 <span data-ttu-id="3f7f7-203">Algunos metadatos están disponibles para todos los usuarios de una base de datos específica.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-203">Some metadata must be accessible to all users in a specific database.</span></span> <span data-ttu-id="3f7f7-204">Por ejemplo, los grupos de archivos no disponen de permisos que puedan concederse; por lo tanto, no se puede conceder permiso a un usuario para ver los metadatos de un grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-204">For example, filegroups do not have conferrable permissions; therefore, a user cannot be granted permission to view the metadata of a filegroup.</span></span> <span data-ttu-id="3f7f7-205">Pero cualquier usuario que pueda crear una tabla deberá poder acceder a los metadatos de un grupo de archivos para usar las cláusulas ON *filegroup* o TEXTIMAGE_ON *filegroup* de la instrucción CREATE TABLE.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-205">However, any user that can create a table must be able to access filegroup metadata to use the ON *filegroup* or TEXTIMAGE_ON *filegroup* clauses of the CREATE TABLE statement.</span></span>  
  
 <span data-ttu-id="3f7f7-206">Los metadatos devueltos por las funciones DB_ID() y DB_NAME() se encuentran visibles para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3f7f7-206">The metadata that is returned by the DB_ID() and DB_NAME() functions is visible to all users.</span></span>  
  
 <span data-ttu-id="3f7f7-207">En la siguiente tabla se muestran las vistas de catálogo que se encuentran visibles para el rol **public** .</span><span class="sxs-lookup"><span data-stu-id="3f7f7-207">The following table lists the catalog views that are visible to the **public** role.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f7f7-208">**sys.partition_functions**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-208">**sys.partition_functions**</span></span>|<span data-ttu-id="3f7f7-209">**sys.partition_range_values**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-209">**sys.partition_range_values**</span></span>|  
|<span data-ttu-id="3f7f7-210">**sys.partition_schemes**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-210">**sys.partition_schemes**</span></span>|<span data-ttu-id="3f7f7-211">**sys.data_spaces**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-211">**sys.data_spaces**</span></span>|  
|<span data-ttu-id="3f7f7-212">**sys.filegroups**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-212">**sys.filegroups**</span></span>|<span data-ttu-id="3f7f7-213">**sys.destination_data_spaces**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-213">**sys.destination_data_spaces**</span></span>|  
|<span data-ttu-id="3f7f7-214">**sys.database_files**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-214">**sys.database_files**</span></span>|<span data-ttu-id="3f7f7-215">**sys.allocation_units**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-215">**sys.allocation_units**</span></span>|  
|<span data-ttu-id="3f7f7-216">**sys.partitions**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-216">**sys.partitions**</span></span>|<span data-ttu-id="3f7f7-217">**sys.messages**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-217">**sys.messages**</span></span>|  
|<span data-ttu-id="3f7f7-218">**sys.schemas**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-218">**sys.schemas**</span></span>|<span data-ttu-id="3f7f7-219">**sys.configurations**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-219">**sys.configurations**</span></span>|  
|<span data-ttu-id="3f7f7-220">**sys.sql_dependencies**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-220">**sys.sql_dependencies**</span></span>|<span data-ttu-id="3f7f7-221">**sys.type_assembly_usages**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-221">**sys.type_assembly_usages**</span></span>|  
|<span data-ttu-id="3f7f7-222">**sys.parameter_type_usages**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-222">**sys.parameter_type_usages**</span></span>|<span data-ttu-id="3f7f7-223">**sys.column_type_usages**</span><span class="sxs-lookup"><span data-stu-id="3f7f7-223">**sys.column_type_usages**</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f7f7-224">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f7f7-224">See Also</span></span>  
 <span data-ttu-id="3f7f7-225">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3f7f7-225">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 <span data-ttu-id="3f7f7-226">[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3f7f7-226">[DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-transact-sql) </span></span>  
 <span data-ttu-id="3f7f7-227">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3f7f7-227">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="3f7f7-228">[EXECUTE AS &#40;cláusula de Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3f7f7-228">[EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql) </span></span>  
 <span data-ttu-id="3f7f7-229">[Vistas de catálogo &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3f7f7-229">[Catalog Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql) </span></span>  
 [<span data-ttu-id="3f7f7-230">Vistas de compatibilidad &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3f7f7-230">Compatibility Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql)  
  
  
