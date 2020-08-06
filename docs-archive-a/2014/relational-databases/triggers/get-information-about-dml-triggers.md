---
title: Obtener información sobre los desencadenadores DML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- metadata [SQL Server], triggers
- viewing DML triggers
- DML triggers, metadata
- displaying DML triggers
- status information [SQL Server], triggers
- DML triggers, viewing
ms.assetid: 37574aac-181d-4aca-a2cc-8abff64237dc
author: rothja
ms.author: jroth
ms.openlocfilehash: 2f65976d2f517137e23bd9e5e1c98cc76324bc49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676924"
---
# <a name="get-information-about-dml-triggers"></a><span data-ttu-id="c39c6-102">Obtener información acerca de los desencadenadores DML</span><span class="sxs-lookup"><span data-stu-id="c39c6-102">Get Information About DML Triggers</span></span>
  <span data-ttu-id="c39c6-103">En este tema se describe cómo obtener información acerca de los desencadenadores DML en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c39c6-103">This topic describes how to get information about DML triggers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c39c6-104">Esta información puede incluir los tipos de desencadenadores de una tabla, el nombre de un desencadenador, su propietario y la fecha en que se creó o modificó.</span><span class="sxs-lookup"><span data-stu-id="c39c6-104">This information can include the types of triggers on a table, the name of a trigger, its owner and the date it was created or modified.</span></span> <span data-ttu-id="c39c6-105">Si el desencadenador no se cifró cuando se creó, se obtiene la definición del desencadenador.</span><span class="sxs-lookup"><span data-stu-id="c39c6-105">If the trigger was not encrypted when it was created, you obtain the definition of the trigger.</span></span> <span data-ttu-id="c39c6-106">Puede usar la definición para entender cómo un desencadenador afecta a la tabla en la que se define.</span><span class="sxs-lookup"><span data-stu-id="c39c6-106">You can use the definition to help you understand how a trigger affects the table up on which it is defined.</span></span> <span data-ttu-id="c39c6-107">También puede averiguar los objetos que usa un desencadenador específico.</span><span class="sxs-lookup"><span data-stu-id="c39c6-107">Also, you can find out the objects that a specific trigger uses.</span></span> <span data-ttu-id="c39c6-108">Con esta información, puede identificar los objetos que afectan al desencadenador, en el caso de que se modifiquen o se eliminen de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-108">With this information, you can identify the objects that affect the trigger if they are changed or deleted in the database.</span></span>  
  
 <span data-ttu-id="c39c6-109">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="c39c6-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c39c6-110">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="c39c6-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c39c6-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c39c6-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c39c6-112">**Para obtener información acerca de los desencadenadores DML, usando:**</span><span class="sxs-lookup"><span data-stu-id="c39c6-112">**To get information about DML triggers, using:**</span></span>  
  
     [<span data-ttu-id="c39c6-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c39c6-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c39c6-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c39c6-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c39c6-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="c39c6-115">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c39c6-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c39c6-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c39c6-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="c39c6-117">Permissions</span></span>  
 <span data-ttu-id="c39c6-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span><span class="sxs-lookup"><span data-stu-id="c39c6-118">**sys.sql.modules**, **sys.object**, **sys.triggers**, **sys.events**, **sys.trigger_events**</span></span>  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] <span data-ttu-id="c39c6-119">Para obtener más información, consulte [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="c39c6-119">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
 <span data-ttu-id="c39c6-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span><span class="sxs-lookup"><span data-stu-id="c39c6-120">OBJECT_DEFINITION, OBJECTPROPERTY, **sp_helptext**</span></span>  
 <span data-ttu-id="c39c6-121">Debe pertenecer al rol **public** .</span><span class="sxs-lookup"><span data-stu-id="c39c6-121">Requires membership in the **public** role.</span></span> <span data-ttu-id="c39c6-122">La definición de objetos de usuario está visible para el propietario del objeto o para los receptores que dispongan de uno de los siguientes permisos: ALTER, CONTROL, TAKE OWNERSHIP o VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="c39c6-122">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="c39c6-123">Estos permisos corresponden implícitamente a los miembros de los roles fijos de base de datos **db_owner**, **db_ddladmin**y **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="c39c6-123">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="c39c6-124">**sys.sql_expression_dependencies**</span><span class="sxs-lookup"><span data-stu-id="c39c6-124">**sys.sql_expression_dependencies**</span></span>  
 <span data-ttu-id="c39c6-125">Necesita el permiso VIEW DEFINITION en la base de datos y el permiso SELECT en **sys.sql_expression_dependencies** para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-125">Requires VIEW DEFINITION permission on the database and SELECT permission on **sys.sql_expression_dependencies** for the database.</span></span> <span data-ttu-id="c39c6-126">De forma predeterminada, solo se concede el permiso SELECT a los miembros del rol fijo de base de datos **db_owner** .</span><span class="sxs-lookup"><span data-stu-id="c39c6-126">By default, SELECT permission is granted only to members of the **db_owner** fixed database role.</span></span> <span data-ttu-id="c39c6-127">Si se conceden los permisos SELECT y VIEW DEFINITION a otro usuario, el receptor puede ver todas las dependencias de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-127">When SELECT and VIEW DEFINITION permissions are granted to another user, the grantee can view all dependencies in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c39c6-128">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c39c6-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="c39c6-129">Para ver la definición de un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="c39c6-129">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="c39c6-130">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="c39c6-130">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c39c6-131">Expanda la base de datos que desee, expanda **Tablas**y, a continuación, expanda la tabla que contiene el desencadenador cuya definición desea ver.</span><span class="sxs-lookup"><span data-stu-id="c39c6-131">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger for which you want to view the definition.</span></span>  
  
3.  <span data-ttu-id="c39c6-132">Expanda **Desencadenadores**, haga clic con el botón derecho en el desencadenador que quiera y, luego, haga clic en **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="c39c6-132">Expand **Triggers**, right-click the trigger you want, and then click **Modify**.</span></span> <span data-ttu-id="c39c6-133">La definición del desencadenador DML aparecerá en la ventana de consulta.</span><span class="sxs-lookup"><span data-stu-id="c39c6-133">The definition of the DML trigger appears in the query window.</span></span>  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="c39c6-134">Para ver las dependencias de un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="c39c6-134">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="c39c6-135">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="c39c6-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="c39c6-136">Expanda la base de datos que desee, expanda **Tablas**y, a continuación, expanda la tabla que contiene el desencadenador y sus dependencias que desea ver.</span><span class="sxs-lookup"><span data-stu-id="c39c6-136">Expand the database that you want, expand **Tables**, and then expand the table that contains the trigger and its dependencies that you want to view.</span></span>  
  
3.  <span data-ttu-id="c39c6-137">Expanda **Desencadenadores**, haga clic con el botón derecho en el desencadenador que quiere y, luego, haga clic en **Ver dependencias**.</span><span class="sxs-lookup"><span data-stu-id="c39c6-137">Expand **Triggers**, right-click the trigger you want, and then click **View Dependencies**.</span></span>  
  
4.  <span data-ttu-id="c39c6-138">En la ventana **Dependencias del objeto**, para ver los objetos que dependen del desencadenador DML, seleccione **Objetos que dependen de \<DML trigger name>** .</span><span class="sxs-lookup"><span data-stu-id="c39c6-138">In the **Object Dependencies** window, to view the objects that depend on the DML trigger, select **Objects that depend on \<DML trigger name>**.</span></span> <span data-ttu-id="c39c6-139">Los objetos aparecerán en el área **Dependencias** .</span><span class="sxs-lookup"><span data-stu-id="c39c6-139">The objects appear in the **Dependencies** area.</span></span>  
  
     <span data-ttu-id="c39c6-140">Para ver los objetos de los que depende el DML, seleccione **Objetos de los que depende \<DML trigger name>** .</span><span class="sxs-lookup"><span data-stu-id="c39c6-140">To view the objects on which the DML depends, select **Objects on which \<DML trigger name> depends**.</span></span> <span data-ttu-id="c39c6-141">Los objetos aparecerán en el área **Dependencias** .</span><span class="sxs-lookup"><span data-stu-id="c39c6-141">The objects appear in the **Dependencies** area.</span></span> <span data-ttu-id="c39c6-142">Expanda cada nodo para ver todos los objetos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-142">Expand each node to see all the objects.</span></span>  
  
5.  <span data-ttu-id="c39c6-143">Para obtener información sobre un objeto que aparece en el área **Dependencias** , haga clic en el objeto.</span><span class="sxs-lookup"><span data-stu-id="c39c6-143">To obtain information about an object that appears in the **Dependencies** area, click the object.</span></span> <span data-ttu-id="c39c6-144">En el campo **Objeto seleccionado** , la información se proporciona en los cuadros **Nombre**, **Tipo**y **Tipo de dependencia** .</span><span class="sxs-lookup"><span data-stu-id="c39c6-144">In the **Selected object** field, information is provided in the **Name**, **Type**, and **Dependency type** boxes.</span></span>  
  
6.  <span data-ttu-id="c39c6-145">Para cerrar la ventana **Dependencias del objeto** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c39c6-145">To close the **Object Dependencies** window, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c39c6-146">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c39c6-146">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-definition-of-a-dml-trigger"></a><span data-ttu-id="c39c6-147">Para ver la definición de un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="c39c6-147">To view the definition of a DML trigger</span></span>  
  
1.  <span data-ttu-id="c39c6-148">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c39c6-148">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c39c6-149">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="c39c6-149">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c39c6-150">Copie y pegue uno de los ejemplos siguientes en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c39c6-150">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="c39c6-151">En cada ejemplo se muestra cómo puede ver la definición del desencadenador `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="c39c6-151">Each example shows how you can view the definition of the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT definition   
FROM sys.sql_modules  
WHERE object_id = OBJECT_ID(N'Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECT_DEFINITION (OBJECT_ID(N'Person.iuPerson')) AS ObjectDefinition;   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
EXEC sp_helptext 'Person.iuPerson'  
GO  
  
```  
  
#### <a name="to-view-the-dependencies-of-a-dml-trigger"></a><span data-ttu-id="c39c6-152">Para ver las dependencias de un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="c39c6-152">To view the dependencies of a DML trigger</span></span>  
  
1.  <span data-ttu-id="c39c6-153">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c39c6-153">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c39c6-154">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="c39c6-154">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c39c6-155">Copie y pegue uno de los ejemplos siguientes en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c39c6-155">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="c39c6-156">En cada ejemplo se muestra cómo puede ver las dependencias del desencadenador `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="c39c6-156">Each example shows how you can view the dependencies of `iuPerson` trigger.</span></span>  
  
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
WHERE referencing_id = OBJECT_ID(N'Person.iuPerson');   
GO  
  
```  
  
#### <a name="to-view-information-about-dml-triggers-in-the-database"></a><span data-ttu-id="c39c6-157">Para ver información acerca de los desencadenadores DML de la base de datos</span><span class="sxs-lookup"><span data-stu-id="c39c6-157">To view information about DML triggers in the database</span></span>  
  
1.  <span data-ttu-id="c39c6-158">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c39c6-158">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c39c6-159">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="c39c6-159">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c39c6-160">Copie y pegue uno de los ejemplos siguientes en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c39c6-160">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="c39c6-161">En cada ejemplo se muestra cómo puede ver la información acerca de los desencadenadores DML (`TR`) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c39c6-161">Each example shows how you can view information about DML triggers (`TR`) in the database.</span></span>  
  
```  
USE AdventureWorks2012;   
GO  
SELECT  name, parent_id, create_date, modify_date, is_instead_of_trigger  
FROM sys.triggers  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT  name, object_id, schema_id, parent_object_id, type_desc, create_date, modify_date, is_published  
FROM sys.objects  
WHERE type = 'TR';   
GO  
  
```  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT OBJECTPROPERTY(OBJECT_ID(N'Person.iuPerson'), 'ExecIsInsteadOfTrigger');   
GO  
  
```  
  
#### <a name="to-view-information-about-events-that-fire-a-dml-trigger"></a><span data-ttu-id="c39c6-162">Para ver información acerca de los eventos que activan un desencadenador DML</span><span class="sxs-lookup"><span data-stu-id="c39c6-162">To view information about events that fire a DML trigger</span></span>  
  
1.  <span data-ttu-id="c39c6-163">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c39c6-163">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c39c6-164">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="c39c6-164">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c39c6-165">Copie y pegue uno de los ejemplos siguientes en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c39c6-165">Copy and paste one of the following examples into the query window and click **Execute**.</span></span> <span data-ttu-id="c39c6-166">En cada ejemplo se muestra cómo puede ver los eventos que activan el desencadenador `iuPerson` .</span><span class="sxs-lookup"><span data-stu-id="c39c6-166">Each example shows how you can view the events that fire the `iuPerson` trigger.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GO  
SELECT object_id, type, type_desc, is_trigger_event, event_group_type, event_group_type_desc   
FROM sys.events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
```sql  
USE AdventureWorks2012;   
GO   
SELECT object_id, type,is_first, is_last  
FROM sys.trigger_events  
WHERE object_id = OBJECT_ID('Person.iuPerson');   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="c39c6-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c39c6-167">See Also</span></span>  
 <span data-ttu-id="c39c6-168">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-168">[CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-169">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-169">[DROP TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-trigger-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-170">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-170">[ENABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/enable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-171">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-171">[DISABLE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/disable-trigger-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-172">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-172">[EVENTDATA &#40;Transact-SQL&#41;](/sql/t-sql/functions/eventdata-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-173">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-173">[sp_rename &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-rename-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-174">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-174">[ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-175">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-175">[sp_help &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-176">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-176">[sp_helptrigger &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptrigger-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-177">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-177">[sys.triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-triggers-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-178">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-178">[sys.trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-179">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-179">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-180">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-180">[sys.assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-181">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-181">[sys.server_triggers &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-triggers-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-182">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-182">[sys.server_trigger_events &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-trigger-events-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-183">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-183">[sys.server_sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-184">[sys.server_assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-184">[sys.server_assembly_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-assembly-modules-transact-sql) </span></span>  
 <span data-ttu-id="c39c6-185">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c39c6-185">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="c39c6-186">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c39c6-186">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
  
