---
title: Ver las dependencias de un procedimiento almacenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], dependencies
- displaying stored procedure dependencies
- viewing stored procedure dependencies
ms.assetid: 6ae0a369-1bc7-4ae4-be89-2b483697cd1f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 790684035d2db3b697fb8b718c96182eda8f1186
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678143"
---
# <a name="view-the-dependencies-of-a-stored-procedure"></a><span data-ttu-id="0a7b9-102">Ver las dependencias de un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="0a7b9-102">View the Dependencies of a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-view-stored-procedure-dependencies-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="0a7b9-103">En este tema se describe cómo ver las dependencias de procedimiento almacenado en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a7b9-103">This topic describes how to view stored procedure dependencies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="0a7b9-104">**Antes de empezar:**  [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="0a7b9-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="0a7b9-105">**Para ver las dependencias de un procedimiento con:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="0a7b9-105">**To view the dependencies of a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0a7b9-106">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="0a7b9-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0a7b9-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0a7b9-107">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0a7b9-108">Permisos</span><span class="sxs-lookup"><span data-stu-id="0a7b9-108">Permissions</span></span>  
 <span data-ttu-id="0a7b9-109">Función del sistema: `sys.dm_sql_referencing_entities`</span><span class="sxs-lookup"><span data-stu-id="0a7b9-109">System Function: `sys.dm_sql_referencing_entities`</span></span>  
 <span data-ttu-id="0a7b9-110">Requiere el permiso CONTROL en la entidad a la que se hace referencia y el permiso SELECT en sys.dm_sql_referencing_entities.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-110">Requires CONTROL permission on the referenced entity and SELECT permission on sys.dm_sql_referencing_entities.</span></span> <span data-ttu-id="0a7b9-111">Cuando la entidad a la que se hace referencia es una función de partición, se requiere el permiso CONTROL en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-111">When the referenced entity is a partition function, CONTROL permission on the database is required.</span></span> <span data-ttu-id="0a7b9-112">De forma predeterminada, se concede el permiso SELECT a public.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-112">By default, SELECT permission is granted to public.</span></span>  
  
 <span data-ttu-id="0a7b9-113">Función del sistema: `sys.dm_sql_referenced_entities`</span><span class="sxs-lookup"><span data-stu-id="0a7b9-113">System Function: `sys.dm_sql_referenced_entities`</span></span>  
 <span data-ttu-id="0a7b9-114">Requiere el permiso SELECT en sys.dm_sql_referenced_entities y el permiso VIEW DEFINITION en la entidad de referencia.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-114">Requires SELECT permission on sys.dm_sql_referenced_entities and VIEW DEFINITION permission on the referencing entity.</span></span> <span data-ttu-id="0a7b9-115">De forma predeterminada, se concede el permiso SELECT a public.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-115">By default, SELECT permission is granted to public.</span></span> <span data-ttu-id="0a7b9-116">Requiere el permiso VIEW DEFINITION en la base de datos o el permiso ALTER DATABASE DDL TRIGGER en la base de datos si la entidad de referencia es un desencadenador DDL de base de datos.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-116">Requires VIEW DEFINITION permission on the database or ALTER DATABASE DDL TRIGGER permission on the database when the referencing entity is a database-level DDL trigger.</span></span> <span data-ttu-id="0a7b9-117">Requiere el permiso VIEW ANY DEFINITION en el servidor si la entidad de referencia es un desencadenador DDL de servidor.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-117">Requires VIEW ANY DEFINITION permission on the server when the referencing entity is a server-level DDL trigger.</span></span>  
  
 <span data-ttu-id="0a7b9-118">Vista de catálogo de objetos: `sys.sql_expression_dependencies`</span><span class="sxs-lookup"><span data-stu-id="0a7b9-118">Object Catalog View: `sys.sql_expression_dependencies`</span></span>  
 <span data-ttu-id="0a7b9-119">Necesita el permiso VIEW DEFINITION en la base de datos y el permiso SELECT en sys.sql_expression_dependencies para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-119">Requires VIEW DEFINITION permission on the database and SELECT permission on sys.sql_expression_dependencies for the database.</span></span> <span data-ttu-id="0a7b9-120">De forma predeterminada, solo se permite el permiso SELECT a los miembros del rol fijo de base de datos db_owner.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-120">By default, SELECT permission is granted only to members of the db_owner fixed database role.</span></span> <span data-ttu-id="0a7b9-121">Si se conceden los permisos SELECT y VIEW DEFINITION a otro usuario, el receptor puede ver todas las dependencias de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-121">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="how-to-view-the-dependencies-of-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="0a7b9-122">Cómo ver las dependencias de un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="0a7b9-122">How to View the Dependencies of a Stored Procedure</span></span>  
 <span data-ttu-id="0a7b9-123">Puede usar cualquiera de los siguientes medios:</span><span class="sxs-lookup"><span data-stu-id="0a7b9-123">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="0a7b9-124">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a7b9-124">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="0a7b9-125">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a7b9-125">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0a7b9-126">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a7b9-126">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="0a7b9-127">**Para ver las dependencias de un procedimiento en el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="0a7b9-127">**To view the dependencies of a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="0a7b9-128">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-128">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0a7b9-129">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento y, a continuación, expanda **Programación**.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-129">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="0a7b9-130">Expanda **Procedimientos almacenados**, haga clic con el botón derecho en el procedimiento y, luego, haga clic en **Ver dependencias**.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-130">Expand **Stored Procedures**, right-click the procedure and then click **View Dependencies**.</span></span>  
  
4.  <span data-ttu-id="0a7b9-131">Examine la lista de objetos que dependen del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-131">View the list of objects that depend on the procedure.</span></span>  
  
5.  <span data-ttu-id="0a7b9-132">Examine la lista de objetos de los cuales depende el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-132">View the list of objects on which the procedure depends.</span></span>  
  
6.  <span data-ttu-id="0a7b9-133">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-133">Click **OK**.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0a7b9-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a7b9-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="0a7b9-135">**Para ver las dependencias de un procedimiento en el Editor de consultas**</span><span class="sxs-lookup"><span data-stu-id="0a7b9-135">**To view the dependencies of a procedure in Query Editor**</span></span>  
  
 <span data-ttu-id="0a7b9-136">Función del sistema: `sys.dm_sql_referencing_entities`</span><span class="sxs-lookup"><span data-stu-id="0a7b9-136">System Function: `sys.dm_sql_referencing_entities`</span></span>  
 <span data-ttu-id="0a7b9-137">Esta función se usa para mostrar los objetos que dependen de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-137">This function is used to display the objects that depend on a procedure.</span></span>  
  
1.  <span data-ttu-id="0a7b9-138">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-138">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0a7b9-139">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-139">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="0a7b9-140">En el menú **Archivo** , haga clic en **Nueva consulta** .</span><span class="sxs-lookup"><span data-stu-id="0a7b9-140">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="0a7b9-141">Copie y pegue los ejemplos siguientes en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-141">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="0a7b9-142">El primer ejemplo crea el procedimiento `uspVendorAllInfo` , que devuelve los nombres de todos los proveedores en la base de datos [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , los productos que suministran, su solvencia y su disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-142">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="0a7b9-143">Después de crear el procedimiento, el segundo ejemplo usa la función sys.dm_sql_referencing_entities para mostrar los objetos que dependen del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-143">After the procedure is created, the second example uses the sys.dm_sql_referencing_entities function to display the objects that depend on the procedure.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referencing_schema_name, referencing_entity_name, referencing_id, referencing_class_desc, is_caller_dependent  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');   
    GO  
  
    ```  
  
 <span data-ttu-id="0a7b9-144">Función del sistema: `sys.dm_sql_referenced_entities`</span><span class="sxs-lookup"><span data-stu-id="0a7b9-144">System Function: `sys.dm_sql_referenced_entities`</span></span>  
 <span data-ttu-id="0a7b9-145">Esta función se usa para mostrar los objetos de los que depende un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-145">This function is used to display the objects a procedure depends on.</span></span>  
  
1.  <span data-ttu-id="0a7b9-146">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-146">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0a7b9-147">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-147">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="0a7b9-148">En el menú **Archivo** , haga clic en **Nueva consulta** .</span><span class="sxs-lookup"><span data-stu-id="0a7b9-148">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="0a7b9-149">Copie y pegue los ejemplos siguientes en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-149">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="0a7b9-150">El primer ejemplo crea el procedimiento `uspVendorAllInfo` , que devuelve los nombres de todos los proveedores en la base de datos [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , los productos que suministran, su solvencia y su disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-150">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="0a7b9-151">Después de crear el procedimiento, el segundo ejemplo usa la función sys.dm_sql_referenced_entities para mostrar los objetos de los que depende el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-151">After the procedure is created, the second example uses the sys.dm_sql_referenced_entities function to display the objects that the procedure depends on.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT referenced_schema_name, referenced_entity_name,  
    referenced_minor_name,referenced_minor_id, referenced_class_desc,  
    is_caller_dependent, is_ambiguous  
    FROM sys.dm_sql_referencing_entities ('Purchasing.uspVendorAllInfo', 'OBJECT');  
    GO  
    ```  
  
 <span data-ttu-id="0a7b9-152">Vista de catálogo de objetos: `sys.sql_expression_dependencies`</span><span class="sxs-lookup"><span data-stu-id="0a7b9-152">Object Catalog View: `sys.sql_expression_dependencies`</span></span>  
 <span data-ttu-id="0a7b9-153">Esta vista se puede usar para mostrar los objetos de los que depende un procedimiento o que dependen de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-153">This view can be used to display objects that a procedure depends on or that depend on a procedure.</span></span>  
  
 <span data-ttu-id="0a7b9-154">Mostrar los objetos que dependen de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-154">Displaying the objects that depend on a procedure.</span></span>  
 1.  <span data-ttu-id="0a7b9-155">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-155">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0a7b9-156">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-156">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="0a7b9-157">En el menú **Archivo** , haga clic en **Nueva consulta** .</span><span class="sxs-lookup"><span data-stu-id="0a7b9-157">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="0a7b9-158">Copie y pegue los ejemplos siguientes en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-158">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="0a7b9-159">El primer ejemplo crea el procedimiento `uspVendorAllInfo` , que devuelve los nombres de todos los proveedores en la base de datos [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , los productos que suministran, su solvencia y su disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-159">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="0a7b9-160">Después de crear el procedimiento, el segundo ejemplo usa la vista sys.sql_expression_dependencies para mostrar los objetos que dependen del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-160">After the procedure is created, the second example uses the sys.sql_expression_dependencies view to display the objects that depend on the procedure.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_SCHEMA_NAME ( referencing_id ) AS referencing_schema_name,  
        OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referenced_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
 <span data-ttu-id="0a7b9-161">Mostrar los objetos de los que depende un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-161">Displaying the objects a procedure depends on.</span></span>  
 1.  <span data-ttu-id="0a7b9-162">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-162">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0a7b9-163">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-163">Expand **Databases**, expand the database in which the procedure belongs.</span></span>  
  
3.  <span data-ttu-id="0a7b9-164">En el menú **Archivo** , haga clic en **Nueva consulta** .</span><span class="sxs-lookup"><span data-stu-id="0a7b9-164">Click on **New Query** under the **File** menu.</span></span>  
  
4.  <span data-ttu-id="0a7b9-165">Copie y pegue los ejemplos siguientes en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-165">Copy and paste the following examples into the query editor.</span></span> <span data-ttu-id="0a7b9-166">El primer ejemplo crea el procedimiento `uspVendorAllInfo` , que devuelve los nombres de todos los proveedores en la base de datos [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] , los productos que suministran, su solvencia y su disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-166">The first example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
     [!code-sql[ProcedureDDL#CreateProc8](../../snippets/tsql/SQL14/tsql/procedureddl/transact-sql/createproc.sql#createproc8)]  
  
5.  <span data-ttu-id="0a7b9-167">Después de crear el procedimiento, el segundo ejemplo usa la vista sys.sql_expression_dependencies para mostrar los objetos de los que depende el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a7b9-167">After the procedure is created, the second example uses the sys.sql_expression_dependencies view to display the objects the procedure depends on.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_NAME(referencing_id) AS referencing_entity_name,   
        o.type_desc AS referencing_desciption,   
        COALESCE(COL_NAME(referencing_id, referencing_minor_id), '(n/a)') AS referencing_minor_id,   
        referencing_class_desc, referenced_class_desc,  
        referenced_server_name, referenced_database_name, referenced_schema_name,  
        referenced_entity_name,   
        COALESCE(COL_NAME(referenced_id, referenced_minor_id), '(n/a)') AS referenced_column_name,  
        is_caller_dependent, is_ambiguous  
    FROM sys.sql_expression_dependencies AS sed  
    INNER JOIN sys.objects AS o ON sed.referencing_id = o.object_id  
    WHERE referencing_id = OBJECT_ID(N'Purchasing.uspVendorAllInfo')  
    GO  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0a7b9-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a7b9-168">See Also</span></span>  
 <span data-ttu-id="0a7b9-169">[Cambiar el nombre de un procedimiento almacenado](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="0a7b9-169">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="0a7b9-170">[sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0a7b9-170">[sys.dm_sql_referencing_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referencing-entities-transact-sql) </span></span>  
 <span data-ttu-id="0a7b9-171">[sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0a7b9-171">[sys.dm_sql_referenced_entities &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-sql-referenced-entities-transact-sql) </span></span>  
 [<span data-ttu-id="0a7b9-172">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0a7b9-172">sys.sql_expression_dependencies &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-sql-expression-dependencies-transact-sql)  
  
  
