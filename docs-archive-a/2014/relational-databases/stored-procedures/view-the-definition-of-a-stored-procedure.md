---
title: Ver la definición de un procedimiento almacenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], viewing
- definition of stored procedure
- viewing stored procedures
- displaying stored procedures
ms.assetid: 93318587-a0c5-4788-946f-3b5dc8372ea9
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4da455d38f984b08ee1f396f26cd4cc85411be92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672873"
---
# <a name="view-the-definition-of-a-stored-procedure"></a><span data-ttu-id="47c79-102">Ver la definición de un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="47c79-102">View the Definition of a Stored Procedure</span></span>
    
##  <a name="you-can-view-the-definition-of-a-stored-procedure-in-ssmanstudiofull-using-object-explorer-menu-options-or-in-the-query-editor-using-tsql-this-topic-describes-how-to-view-the-definition-of-procedure-in-object-explorer-and-by-using-a-system-stored-procedure-system-function-and-object-catalog-view-in-the-query-editor"></a><a name="Top"></a> <span data-ttu-id="47c79-103">Puede ver la definición de un procedimiento almacenado en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] mediante las opciones de menú del Explorador de objetos o en el Editor de consultas mediante [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47c79-103">You can view the definition of a stored procedure in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] using Object Explorer menu options or in the Query Editor using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="47c79-104">En este tema se describe cómo ver la definición del procedimiento en el Explorador de objetos y utilizar un procedimiento almacenado del sistema, una función del sistema y una vista de catálogo de objetos en el Editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="47c79-104">This topic describes how to view the definition of procedure in Object Explorer and by using a system stored procedure, system function, and object catalog view in the Query Editor.</span></span>  
  
-   <span data-ttu-id="47c79-105">**Antes de empezar:**  [Seguridad](#Security)</span><span class="sxs-lookup"><span data-stu-id="47c79-105">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="47c79-106">**Para ver la definición de un procedimiento con:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="47c79-106">**To view the definition of a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="47c79-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="47c79-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="47c79-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="47c79-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="47c79-109">Permisos</span><span class="sxs-lookup"><span data-stu-id="47c79-109">Permissions</span></span>  
 <span data-ttu-id="47c79-110">Procedimiento almacenado del sistema: `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="47c79-110">System Stored Procedure: `sp_helptext`</span></span>  
 <span data-ttu-id="47c79-111">Debe pertenecer al rol **public** .</span><span class="sxs-lookup"><span data-stu-id="47c79-111">Requires membership in the **public** role.</span></span> <span data-ttu-id="47c79-112">Las definiciones de los objetos del sistema están visibles públicamente.</span><span class="sxs-lookup"><span data-stu-id="47c79-112">System object definitions are publicly visible.</span></span> <span data-ttu-id="47c79-113">La definición de objetos de usuario está visible para el propietario del objeto o para los receptores que dispongan de uno de los siguientes permisos: ALTER, CONTROL, TAKE OWNERSHIP o VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="47c79-113">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span>  
  
 <span data-ttu-id="47c79-114">Función del sistema: `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="47c79-114">System Function: `OBJECT_DEFINITION`</span></span>  
 <span data-ttu-id="47c79-115">Las definiciones de los objetos del sistema están visibles públicamente.</span><span class="sxs-lookup"><span data-stu-id="47c79-115">System object definitions are publicly visible.</span></span> <span data-ttu-id="47c79-116">La definición de objetos de usuario está visible para el propietario del objeto o para los receptores que dispongan de uno de los siguientes permisos: ALTER, CONTROL, TAKE OWNERSHIP o VIEW DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="47c79-116">The definition of user objects is visible to the object owner or grantees that have any one of the following permissions: ALTER, CONTROL, TAKE OWNERSHIP, or VIEW DEFINITION.</span></span> <span data-ttu-id="47c79-117">Estos permisos corresponden implícitamente a los miembros de los roles fijos de base de datos **db_owner**, **db_ddladmin**y **db_securityadmin** .</span><span class="sxs-lookup"><span data-stu-id="47c79-117">These permissions are implicitly held by members of the **db_owner**, **db_ddladmin**, and **db_securityadmin** fixed database roles.</span></span>  
  
 <span data-ttu-id="47c79-118">Vista de catálogo de objetos: `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="47c79-118">Object Catalog View: `sys.sql_modules`</span></span>  
 <span data-ttu-id="47c79-119">La visibilidad de los metadatos en las vistas de catálogo se limita a los elementos protegibles y que son propiedad de un usuario o sobre los que el usuario tiene algún permiso.</span><span class="sxs-lookup"><span data-stu-id="47c79-119">The visibility of the metadata in catalog views is limited to securables that a user either owns or on which the user has been granted some permission.</span></span> <span data-ttu-id="47c79-120">Para obtener más información, consulte [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="47c79-120">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
##  <a name="how-to-view-the-definition-of-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="47c79-121">Ver la definición de un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="47c79-121">How to View the Definition of a Stored Procedure</span></span>  
 <span data-ttu-id="47c79-122">Puede usar cualquiera de los siguientes medios:</span><span class="sxs-lookup"><span data-stu-id="47c79-122">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="47c79-123">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="47c79-123">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="47c79-124">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="47c79-124">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="47c79-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="47c79-125">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="47c79-126">**Para ver la definición de un procedimiento en el Explorador de objetos**</span><span class="sxs-lookup"><span data-stu-id="47c79-126">**To view the definition a procedure in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="47c79-127">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="47c79-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="47c79-128">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento y, a continuación, expanda **Programación**.</span><span class="sxs-lookup"><span data-stu-id="47c79-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="47c79-129">Expanda **Procedimientos almacenados**, haga clic con el botón derecho en el procedimiento y luego en **Incluir procedimiento almacenado como**. A continuación, haga clic en uno de los siguientes: **Create To**, **Alter To** o **Drop and Create To**.</span><span class="sxs-lookup"><span data-stu-id="47c79-129">Expand **Stored Procedures**, right-click the procedure and then click **Script Stored Procedure as**, and then click one of the following: **Create To**, **Alter To**, or **Drop and Create To**.</span></span>  
  
4.  <span data-ttu-id="47c79-130">Seleccione **Nueva ventana del Editor de consultas**.</span><span class="sxs-lookup"><span data-stu-id="47c79-130">Select **New Query Editor Window**.</span></span> <span data-ttu-id="47c79-131">Se mostrará la definición del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="47c79-131">This will display the procedure definition.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="47c79-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="47c79-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="47c79-133">**Para ver la definición de un procedimiento en el Editor de consultas**</span><span class="sxs-lookup"><span data-stu-id="47c79-133">**To view the definition of a procedure in Query Editor**</span></span>  
  
 <span data-ttu-id="47c79-134">Procedimiento almacenado del sistema: `sp_helptext`</span><span class="sxs-lookup"><span data-stu-id="47c79-134">System Stored Procedure: `sp_helptext`</span></span>  
 1.  <span data-ttu-id="47c79-135">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47c79-135">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="47c79-136">En la barra de herramientas, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="47c79-136">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="47c79-137">En la ventana de consulta, escriba la siguiente instrucción que usa el procedimiento almacenado del sistema `sp_helptext`.</span><span class="sxs-lookup"><span data-stu-id="47c79-137">In the query window, enter the following statement that uses the `sp_helptext` system stored procedure.</span></span> <span data-ttu-id="47c79-138">Cambie el nombre de la base de datos y el nombre del procedimiento almacenado de forma que hagan referencia a la base de datos y al procedimiento almacenado que desee.</span><span class="sxs-lookup"><span data-stu-id="47c79-138">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_helptext N'AdventureWorks2012.dbo.uspLogError';  
    ```  
  
 <span data-ttu-id="47c79-139">Función del sistema: `OBJECT_DEFINITION`</span><span class="sxs-lookup"><span data-stu-id="47c79-139">System Function: `OBJECT_DEFINITION`</span></span>  
 1.  <span data-ttu-id="47c79-140">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47c79-140">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="47c79-141">En la barra de herramientas, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="47c79-141">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="47c79-142">En la ventana de consulta, escriba las siguientes instrucciones que usan la función del sistema `OBJECT_DEFINITION`.</span><span class="sxs-lookup"><span data-stu-id="47c79-142">In the query window, enter the following statements that use the `OBJECT_DEFINITION` system function.</span></span> <span data-ttu-id="47c79-143">Cambie el nombre de la base de datos y el nombre del procedimiento almacenado de forma que hagan referencia a la base de datos y al procedimiento almacenado que desee.</span><span class="sxs-lookup"><span data-stu-id="47c79-143">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT OBJECT_DEFINITION (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
 <span data-ttu-id="47c79-144">Vista de catálogo de objetos: `sys.sql_modules`</span><span class="sxs-lookup"><span data-stu-id="47c79-144">Object Catalog View: `sys.sql_modules`</span></span>  
 1.  <span data-ttu-id="47c79-145">En el Explorador de objetos, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="47c79-145">In Object Explorer, connect to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="47c79-146">En la barra de herramientas, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="47c79-146">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="47c79-147">En la ventana de consulta, escriba las siguientes instrucciones que usan la vista de catálogo `sys.sql_modules`.</span><span class="sxs-lookup"><span data-stu-id="47c79-147">In the query window, enter the following statements that use the `sys.sql_modules` catalog view.</span></span> <span data-ttu-id="47c79-148">Cambie el nombre de la base de datos y el nombre del procedimiento almacenado de forma que hagan referencia a la base de datos y al procedimiento almacenado que desee.</span><span class="sxs-lookup"><span data-stu-id="47c79-148">Change the database name and stored procedure name to reference the database and stored procedure that you want.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT definition  
    FROM sys.sql_modules  
    WHERE object_id = (OBJECT_ID(N'AdventureWorks2012.dbo.uspLogError'));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="47c79-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47c79-149">See Also</span></span>  
 <span data-ttu-id="47c79-150">[Crear un procedimiento almacenado](create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="47c79-150">[Create a Stored Procedure](create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="47c79-151">[Modificar un procedimiento almacenado](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="47c79-151">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="47c79-152">[Eliminar un procedimiento almacenado](delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="47c79-152">[Delete a Stored Procedure](delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="47c79-153">[Cambiar el nombre de un procedimiento almacenado](rename-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="47c79-153">[Rename a Stored Procedure](rename-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="47c79-154">[OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="47c79-154">[OBJECT_DEFINITION &#40;Transact-SQL&#41;](/sql/t-sql/functions/object-definition-transact-sql) </span></span>  
 <span data-ttu-id="47c79-155">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="47c79-155">[sys.sql_modules &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-modules-transact-sql) </span></span>  
 <span data-ttu-id="47c79-156">[sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="47c79-156">[sp_helptext &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helptext-transact-sql) </span></span>  
 [<span data-ttu-id="47c79-157">OBJECT_ID &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="47c79-157">OBJECT_ID &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-id-transact-sql)  
  
  
