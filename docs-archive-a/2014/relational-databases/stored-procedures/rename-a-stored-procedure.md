---
title: Cambio de nombre de un procedimiento almacenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], renaming
- renaming stored procedures
ms.assetid: 5d2e4c68-7e0b-4405-8919-f5b203e46770
author: stevestein
ms.author: sstein
ms.openlocfilehash: 02e1acb528a32ef242e160e0ce5dd0267237c876
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678148"
---
# <a name="rename-a-stored-procedure"></a><span data-ttu-id="ed122-102">Cambiar el nombre de un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="ed122-102">Rename a Stored Procedure</span></span>
  <span data-ttu-id="ed122-103">En este tema se describe cómo cambiar el nombre de un procedimiento almacenado [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed122-103">This topic describes how to rename a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="ed122-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="ed122-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ed122-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="ed122-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ed122-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ed122-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ed122-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ed122-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ed122-108">**Para cambiar el nombre de un procedimiento almacenado, usando:**</span><span class="sxs-lookup"><span data-stu-id="ed122-108">**To rename a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="ed122-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed122-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ed122-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ed122-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ed122-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ed122-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ed122-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ed122-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ed122-113">Los nombres de los procedimientos se deben ajustar a las reglas para los [identificadores](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="ed122-113">Procedure names must comply with the rules for [identifiers](../databases/database-identifiers.md).</span></span>  
  
-   <span data-ttu-id="ed122-114">Al cambiar el nombre de un procedimiento almacenado no se cambiará el nombre del objeto correspondiente en la columna de definición de la vista de catálogo **sys.sql_modules** .</span><span class="sxs-lookup"><span data-stu-id="ed122-114">Renaming a stored procedure will not change the name of the corresponding object name in the definition column of the **sys.sql_modules** catalog view.</span></span> <span data-ttu-id="ed122-115">Por tanto, se recomienda no cambiar este tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="ed122-115">Therefore, we recommend that you do not rename this object type.</span></span> <span data-ttu-id="ed122-116">En su lugar, quite el procedimiento almacenado y vuelva a crearlo con su nuevo nombre.</span><span class="sxs-lookup"><span data-stu-id="ed122-116">Instead, drop and re-create the stored procedure with its new name.</span></span>  
  
-   <span data-ttu-id="ed122-117">El hecho de cambiar el nombre o la definición de un procedimiento puede provocar errores en los objetos dependientes si no se actualizan para reflejar los cambios realizados en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ed122-117">Changing the name or definition of a procedure can cause dependent objects to fail when the objects are not updated to reflect the changes that have been made to the procedure.</span></span> <span data-ttu-id="ed122-118">Para obtener más información, vea [Ver las dependencias de un procedimiento almacenado](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="ed122-118">For more information, see [View the Dependencies of a Stored Procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ed122-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ed122-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ed122-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="ed122-120">Permissions</span></span>  
 <span data-ttu-id="ed122-121">CREATE PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="ed122-121">CREATE PROCEDURE</span></span>  
 <span data-ttu-id="ed122-122">Necesita el permiso CREATE PROCEDURE en la base de datos y el permiso ALTER en el esquema en el que se va a crear el procedimiento o la pertenencia al rol fijo de base de datos **db_ddladmin**.</span><span class="sxs-lookup"><span data-stu-id="ed122-122">Requires CREATE PROCEDURE permission in the database and ALTER permission on the schema in which the procedure is being created, or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
 <span data-ttu-id="ed122-123">ALTER PROCEDURE</span><span class="sxs-lookup"><span data-stu-id="ed122-123">ALTER PROCEDURE</span></span>  
 <span data-ttu-id="ed122-124">Necesita el permiso ALTER en el procedimiento o la pertenencia al rol fijo de base de datos **db_ddladmin** .</span><span class="sxs-lookup"><span data-stu-id="ed122-124">Requires ALTER permission on the procedure or requires membership in the **db_ddladmin** fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ed122-125">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed122-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="ed122-126">Para cambiar el nombre de un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="ed122-126">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="ed122-127">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="ed122-127">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="ed122-128">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento y, a continuación, expanda **Programación**.</span><span class="sxs-lookup"><span data-stu-id="ed122-128">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="ed122-129">[Cómo ver las dependencias de un procedimiento almacenado (SQL Server Management Studio)](view-the-dependencies-of-a-stored-procedure.md).</span><span class="sxs-lookup"><span data-stu-id="ed122-129">[Determine the dependencies of the stored procedure](view-the-dependencies-of-a-stored-procedure.md).</span></span>  
  
4.  <span data-ttu-id="ed122-130">Expanda **Procedimientos almacenados**, haga clic con el botón derecho en el procedimiento cuyo nombre quiere cambiar y, después, haga clic en **Cambiar nombre**.</span><span class="sxs-lookup"><span data-stu-id="ed122-130">Expand **Stored Procedures**, right-click the procedure to rename, and then click **Rename**.</span></span>  
  
5.  <span data-ttu-id="ed122-131">Modifique el nombre del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ed122-131">Modify the procedure name.</span></span>  
  
6.  <span data-ttu-id="ed122-132">Modifique el nombre del procedimiento al que se hace referencia en cualquier objeto dependiente o script.</span><span class="sxs-lookup"><span data-stu-id="ed122-132">Modify the procedure name referenced in any dependent objects or scripts.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ed122-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ed122-133">Using Transact-SQL</span></span>  
  
#### <a name="to-rename-a-stored-procedure"></a><span data-ttu-id="ed122-134">Para cambiar el nombre de un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="ed122-134">To rename a stored procedure</span></span>  
  
1.  <span data-ttu-id="ed122-135">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed122-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ed122-136">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="ed122-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ed122-137">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ed122-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="ed122-138">En este ejemplo se muestra cómo cambiar el nombre de un procedimiento quitando el procedimiento y volviendo a crearlo con otro nombre.</span><span class="sxs-lookup"><span data-stu-id="ed122-138">This example shows how to rename a procedure by dropping the procedure and re-creating the procedure with a new name.</span></span> <span data-ttu-id="ed122-139">En el primer ejemplo se crea el procedimiento almacenado `'HumanResources.uspGetAllEmployeesTest`.</span><span class="sxs-lookup"><span data-stu-id="ed122-139">The first example creates the stored procedure `'HumanResources.uspGetAllEmployeesTest`.</span></span> <span data-ttu-id="ed122-140">En el segundo ejemplo se cambia el nombre del procedimiento almacenado a `HumanResources.uspEveryEmployeeTest`.</span><span class="sxs-lookup"><span data-stu-id="ed122-140">The second example renames the stored procedure to `HumanResources.uspEveryEmployeeTest`.</span></span>  
  
```sql  
--Create the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspGetAllEmployeesTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
  
--Rename the stored procedure.  
USE AdventureWorks2012;  
GO  
IF OBJECT_ID ( 'HumanResources.uspGetAllEmployeesTest', 'P' ) IS NOT NULL   
    DROP PROCEDURE HumanResources.uspGetAllEmployeesTest;  
GO  
CREATE PROCEDURE HumanResources.uspEveryEmployeeTest  
AS  
    SET NOCOUNT ON;  
    SELECT LastName, FirstName, Department  
    FROM HumanResources.vEmployeeDepartmentHistory;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed122-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed122-141">See Also</span></span>  
 <span data-ttu-id="ed122-142">[ALTER PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed122-142">[ALTER PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-procedure-transact-sql) </span></span>  
 <span data-ttu-id="ed122-143">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed122-143">[CREATE PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-procedure-transact-sql) </span></span>  
 <span data-ttu-id="ed122-144">[Crear un procedimiento almacenado](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ed122-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="ed122-145">[Modificar un procedimiento almacenado](../stored-procedures/modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ed122-145">[Modify a Stored Procedure](../stored-procedures/modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="ed122-146">[Eliminar un procedimiento almacenado](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ed122-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="ed122-147">[Ver la definición de un procedimiento almacenado](view-the-definition-of-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ed122-147">[View the Definition of a Stored Procedure](view-the-definition-of-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="ed122-148">Ver las dependencias de un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="ed122-148">View the Dependencies of a Stored Procedure</span></span>](view-the-dependencies-of-a-stored-procedure.md)  
  
  
