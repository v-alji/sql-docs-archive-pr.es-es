---
title: Establecer o cambiar la intercalación de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- collations [SQL Server], database
- database collations [SQL Server]
ms.assetid: 1379605c-1242-4ac8-ab1b-e2a2b5b1f895
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6d7f7c3e3ddba7ba0ea9701993dbe0fad3a8d975
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677692"
---
# <a name="set-or-change-the-database-collation"></a><span data-ttu-id="48132-102">Establecer o cambiar la intercalación de base de datos</span><span class="sxs-lookup"><span data-stu-id="48132-102">Set or Change the Database Collation</span></span>
  <span data-ttu-id="48132-103">En este tema se describe cómo establecer y cambiar la intercalación de base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48132-103">This topic describes how set and change the database collation in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="48132-104">Si no se especifica ninguna intercalación, se utiliza la del servidor.</span><span class="sxs-lookup"><span data-stu-id="48132-104">If no collation is specified, the server collation is used.</span></span>  
  
 <span data-ttu-id="48132-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="48132-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="48132-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="48132-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="48132-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="48132-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="48132-108">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="48132-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="48132-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="48132-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="48132-110">**Para establecer o cambiar la intercalación de base de datos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="48132-110">**To set or change the database collation, using:**</span></span>  
  
     [<span data-ttu-id="48132-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="48132-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="48132-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="48132-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="48132-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="48132-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="48132-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="48132-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="48132-115">Las intercalaciones exclusivas de Unicode de Windows se pueden utilizar únicamente con la cláusula COLLATE para aplicar intercalaciones a los tipos de datos `nchar`, `nvarchar` y `ntext` de nivel de columna y de nivel de datos de expresión.</span><span class="sxs-lookup"><span data-stu-id="48132-115">Windows Unicode-only collations can only be used with the COLLATE clause to apply collations to the `nchar`, `nvarchar`, and `ntext` data types on column level and expression-level data.</span></span> <span data-ttu-id="48132-116">No se pueden utilizar con la cláusula COLLATE para cambiar la intercalación de una instancia de la base de datos o del servidor.</span><span class="sxs-lookup"><span data-stu-id="48132-116">They cannot be used with the COLLATE clause to change the collation of a database or server instance.</span></span>  
  
-   <span data-ttu-id="48132-117">Si la intercalación especificada o la intercalación usada por el objeto al que se hace referencia utiliza una página de códigos no admitida por Windows, el [!INCLUDE[ssDE](../../includes/ssde-md.md)] muestra un error.</span><span class="sxs-lookup"><span data-stu-id="48132-117">If the specified collation or the collation used by the referenced object uses a code page that is not supported by Windows, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] displays an error.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="48132-118">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="48132-118">Recommendations</span></span>  
  
-   <span data-ttu-id="48132-119">Puede buscar los nombres de intercalación admitidos en [Nombre de intercalación de Windows &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) y [Nombre de intercalación de SQL Server &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql), o puede usar la función del sistema [sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="48132-119">You can find the supported collation names in [Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) and [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql); or you can use the [sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) system function.</span></span>  
  
-   <span data-ttu-id="48132-120">Al modificar la intercalación de la base de datos también se cambian los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="48132-120">When you change the database collation, you change the following:</span></span>  
  
    -   <span data-ttu-id="48132-121">Todas las columnas `char`, `varchar`, `text`, `nchar`, `nvarchar` o `ntext` de las tablas del sistema se cambian a la nueva intercalación.</span><span class="sxs-lookup"><span data-stu-id="48132-121">Any `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` columns in system tables are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="48132-122">Todos los parámetros `char`, `varchar`, `text`, `nchar`, `nvarchar` o `ntext` y valores devueltos escalares existentes para los procedimientos almacenados y las funciones definidas por el usuario se cambian a la nueva intercalación.</span><span class="sxs-lookup"><span data-stu-id="48132-122">All existing `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` parameters and scalar return values for stored procedures and user-defined functions are changed to the new collation.</span></span>  
  
    -   <span data-ttu-id="48132-123">Los tipos de datos del sistema `char`, `varchar`, `text`, `nchar`, `nvarchar` o `ntext` y todos los tipos de datos definidos por el usuario basados en estos tipos de datos del sistema se cambian a la nueva intercalación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="48132-123">The `char`, `varchar`, `text`, `nchar`, `nvarchar`, or `ntext` system data types, and all user-defined data types based on these system data types, are changed to the new default collation.</span></span>  
  
-   <span data-ttu-id="48132-124">Para cambiar la intercalación de cualquier objeto nuevo creado en una base de datos de usuario, utilice la cláusula COLLATE de la instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="48132-124">You can change the collation of any new objects that are created in a user database by using the COLLATE clause of the [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement.</span></span> <span data-ttu-id="48132-125">Esta instrucción no modifica la intercalación de las columnas de ninguna de las tablas definidas por el usuario existentes.</span><span class="sxs-lookup"><span data-stu-id="48132-125">This statement does not change the collation of the columns in any existing user-defined tables.</span></span> <span data-ttu-id="48132-126">Para modificarlas, utilice la cláusula COLLATE de [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="48132-126">These can be changed by using the COLLATE clause of [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="48132-127">Seguridad</span><span class="sxs-lookup"><span data-stu-id="48132-127">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="48132-128">Permisos</span><span class="sxs-lookup"><span data-stu-id="48132-128">Permissions</span></span>  
 <span data-ttu-id="48132-129">CREATE DATABASE</span><span class="sxs-lookup"><span data-stu-id="48132-129">CREATE DATABASE</span></span>  
 <span data-ttu-id="48132-130">Requiere el permiso CREATE DATABASE en la base de datos **maestra** , o bien el permiso CREATE any Database o ALTER any Database.</span><span class="sxs-lookup"><span data-stu-id="48132-130">Requires CREATE DATABASE permission in the **master** database, or requires CREATE ANY DATABASE, or ALTER ANY DATABASE permission.</span></span>  
  
 <span data-ttu-id="48132-131">ALTER DATABASE</span><span class="sxs-lookup"><span data-stu-id="48132-131">ALTER DATABASE</span></span>  
 <span data-ttu-id="48132-132">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="48132-132">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="48132-133">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="48132-133">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-or-change-the-database-collation"></a><span data-ttu-id="48132-134">Para establecer o cambiar la intercalación de base de datos</span><span class="sxs-lookup"><span data-stu-id="48132-134">To set or change the database collation</span></span>  
  
1.  <span data-ttu-id="48132-135">En el **Explorador de objetos**, conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expándala y, a continuación, expanda **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="48132-135">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], expand that instance, and then expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="48132-136">Si está creando una base de datos, haga clic con el botón derecho en **Bases de datos** y haga clic en **Nueva base de datos**.</span><span class="sxs-lookup"><span data-stu-id="48132-136">If you are creating a new database, right-click **Databases** and then click **New Database**.</span></span> <span data-ttu-id="48132-137">Si no quiere la intercalación predeterminada, haga clic en la página **Opciones** y seleccione una intercalación en la lista desplegable **Intercalación** .</span><span class="sxs-lookup"><span data-stu-id="48132-137">If you do not want the default collation, click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
     <span data-ttu-id="48132-138">Como alternativa, si la base de datos ya existe, haga clic con el botón derecho en la base de datos que quiera y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="48132-138">Alternatively, if the database already exists, right-click the database that you want and click **Properties**.</span></span> <span data-ttu-id="48132-139">Haga clic en la página **Opciones** y seleccione una intercalación en la lista desplegable **Intercalación** .</span><span class="sxs-lookup"><span data-stu-id="48132-139">Click the **Options** page, and select a collation from the **Collation** drop-down list.</span></span>  
  
3.  <span data-ttu-id="48132-140">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="48132-140">After you are finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="48132-141">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="48132-141">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-database-collation"></a><span data-ttu-id="48132-142">Para establecer la intercalación de base de datos</span><span class="sxs-lookup"><span data-stu-id="48132-142">To set the database collation</span></span>  
  
1.  <span data-ttu-id="48132-143">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48132-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="48132-144">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="48132-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="48132-145">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="48132-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="48132-146">En este ejemplo se muestra cómo usar la cláusula [COLLATE](/sql/t-sql/statements/collations) para especificar un nombre de intercalación.</span><span class="sxs-lookup"><span data-stu-id="48132-146">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause to specify a collation name.</span></span> <span data-ttu-id="48132-147">En el ejemplo de crea la base de datos `MyOptionsTest` que utiliza la intercalación `Latin1_General_100_CS_AS_SC` .</span><span class="sxs-lookup"><span data-stu-id="48132-147">The example creates the database `MyOptionsTest` that uses the `Latin1_General_100_CS_AS_SC` collation.</span></span> <span data-ttu-id="48132-148">Después de crear la base de datos, ejecute la instrucción `SELECT` para comprobar la configuración.</span><span class="sxs-lookup"><span data-stu-id="48132-148">After you create the database, execute the `SELECT` statement to verify the setting.</span></span>  
  
```sql  
USE master;  
GO  
IF DB_ID (N'MyOptionsTest') IS NOT NULL  
DROP DATABASE MyOptionsTest;  
GO  
CREATE DATABASE MyOptionsTest  
COLLATE Latin1_General_100_CS_AS_SC;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
#### <a name="to-change-the-database-collation"></a><span data-ttu-id="48132-149">Para cambiar la intercalación de base de datos</span><span class="sxs-lookup"><span data-stu-id="48132-149">To change the database collation</span></span>  
  
1.  <span data-ttu-id="48132-150">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48132-150">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="48132-151">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="48132-151">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="48132-152">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="48132-152">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="48132-153">En este ejemplo se muestra cómo usar la cláusula [COLLATE](/sql/t-sql/statements/collations) en una instrucción [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) para cambiar el nombre de la intercalación.</span><span class="sxs-lookup"><span data-stu-id="48132-153">This example shows how to use the [COLLATE](/sql/t-sql/statements/collations) clause in an [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql) statement to change the collation name.</span></span> <span data-ttu-id="48132-154">Ejecute la instrucción `SELECT` para comprobar el cambio.</span><span class="sxs-lookup"><span data-stu-id="48132-154">Execute the `SELECT` statement to verify the change.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE MyOptionsTest  
COLLATE French_CI_AS ;  
GO  
  
--Verify the collation setting.  
SELECT name, collation_name  
FROM sys.databases  
WHERE name = N'MyOptionsTest';  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="48132-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48132-155">See Also</span></span>  
 <span data-ttu-id="48132-156">[Compatibilidad con la intercalación y Unicode](collation-and-unicode-support.md) </span><span class="sxs-lookup"><span data-stu-id="48132-156">[Collation and Unicode Support](collation-and-unicode-support.md) </span></span>  
 <span data-ttu-id="48132-157">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48132-157">[sys.fn_helpcollations &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-helpcollations-transact-sql) </span></span>  
 <span data-ttu-id="48132-158">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48132-158">[sys.databases &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) </span></span>  
 <span data-ttu-id="48132-159">[Nombre de intercalación de SQL Server &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48132-159">[SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="48132-160">[Nombre de intercalación de Windows &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48132-160">[Windows Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/windows-collation-name-transact-sql) </span></span>  
 <span data-ttu-id="48132-161">[COLLATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/collations) </span><span class="sxs-lookup"><span data-stu-id="48132-161">[COLLATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/collations) </span></span>  
 <span data-ttu-id="48132-162">[Prioridad de intercalación &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48132-162">[Collation Precedence &#40;Transact-SQL&#41;](/sql/t-sql/statements/collation-precedence-transact-sql) </span></span>  
 <span data-ttu-id="48132-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48132-163">[CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql) </span></span>  
 <span data-ttu-id="48132-164">[CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48132-164">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="48132-165">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="48132-165">[ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) </span></span>  
 [<span data-ttu-id="48132-166">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="48132-166">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
