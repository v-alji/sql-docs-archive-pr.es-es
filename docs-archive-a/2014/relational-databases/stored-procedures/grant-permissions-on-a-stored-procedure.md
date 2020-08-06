---
title: Conceder permisos para un procedimiento almacenado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- stored procedures [SQL Server], permissions
ms.assetid: a7d15816-a788-4099-ad91-dc4b26618299
author: stevestein
ms.author: sstein
ms.openlocfilehash: 23ea130b9d2033128adc99413c053d66936e3ccc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673563"
---
# <a name="grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="f05ad-102">Conceder permisos para un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="f05ad-102">Grant Permissions on a Stored Procedure</span></span>
  <span data-ttu-id="f05ad-103">En este tema se describe cómo conceder permisos para un procedimiento almacenado en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f05ad-103">This topic describes how to grant permissions on a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="f05ad-104">Se pueden conceder permisos a un usuario, un rol de base de datos o un rol de aplicación existentes en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f05ad-104">Permissions can be granted to an existing user, database role, or application role in the database.</span></span>  
  
 <span data-ttu-id="f05ad-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="f05ad-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f05ad-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="f05ad-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f05ad-107">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f05ad-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f05ad-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f05ad-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f05ad-109">**Para conceder permisos para un procedimiento almacenado, usando:**</span><span class="sxs-lookup"><span data-stu-id="f05ad-109">**To grant permissions on a stored procedure, using:**</span></span>  
  
     [<span data-ttu-id="f05ad-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f05ad-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f05ad-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f05ad-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f05ad-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="f05ad-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f05ad-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="f05ad-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="f05ad-114">No se puede usar [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para conceder permisos para procedimientos del sistema o funciones del sistema.</span><span class="sxs-lookup"><span data-stu-id="f05ad-114">You cannot use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to grant permissions on system procedures or system functions.</span></span> <span data-ttu-id="f05ad-115">En su lugar, use [GRANT (permisos de objeto de Transact-SQL)](/sql/t-sql/statements/grant-object-permissions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="f05ad-115">Use [GRANT Object Permissions](/sql/t-sql/statements/grant-object-permissions-transact-sql) instead.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f05ad-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f05ad-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f05ad-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="f05ad-117">Permissions</span></span>  
 <span data-ttu-id="f05ad-118">El otorgante del permiso (o la entidad de seguridad especificada con la opción AS) debe tener el permiso con GRANT OPTION, o un permiso superior que implique el permiso que se va a conceder.</span><span class="sxs-lookup"><span data-stu-id="f05ad-118">The grantor (or the principal specified with the AS option) must have either the permission itself with GRANT OPTION, or a higher permission that implies the permission being granted.</span></span> <span data-ttu-id="f05ad-119">Requiere el permiso ALTER en el esquema al que pertenece el procedimiento o el permiso CONTROL en el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f05ad-119">Requires ALTER permission on the schema to which the procedure belongs, or CONTROL permission on the procedure.</span></span> <span data-ttu-id="f05ad-120">Para obtener más información, vea [Permisos de objeto GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f05ad-120">For more information, see [GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f05ad-121">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f05ad-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="f05ad-122">Para conceder permisos para un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="f05ad-122">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="f05ad-123">En el Explorador de objetos, conéctese a una instancia de [!INCLUDE[ssDE](../../../includes/ssde-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="f05ad-123">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f05ad-124">Expanda **Bases de datos**, expanda la base de datos a la que pertenece el procedimiento y, a continuación, expanda **Programación**.</span><span class="sxs-lookup"><span data-stu-id="f05ad-124">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="f05ad-125">Expanda **Procedimientos almacenados**, haga clic con el botón derecho en el procedimiento en el que quiera conceder permisos y, luego, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f05ad-125">Expand **Stored Procedures**, right-click the procedure to grant permissions on, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f05ad-126">En **Propiedades del procedimiento almacenado**, seleccione la página **Permisos** .</span><span class="sxs-lookup"><span data-stu-id="f05ad-126">From **Stored Procedure Properties**, select the **Permissions** page.</span></span>  
  
5.  <span data-ttu-id="f05ad-127">Para conceder permisos a un usuario, un rol de base de datos o un rol de aplicación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="f05ad-127">To grant permissions to a user, database role, or application role, click **Search**.</span></span>  
  
6.  <span data-ttu-id="f05ad-128">En **Seleccionar usuarios o roles**, haga clic en **Tipos de objeto** para agregar o borrar los usuarios y los roles que desee.</span><span class="sxs-lookup"><span data-stu-id="f05ad-128">In **Select Users or Roles**, click **Object Types** to add or clear the users and roles you want.</span></span>  
  
7.  <span data-ttu-id="f05ad-129">Haga clic en **Examinar** para mostrar la lista de usuarios o de roles.</span><span class="sxs-lookup"><span data-stu-id="f05ad-129">Click **Browse** to display the list of users or roles.</span></span> <span data-ttu-id="f05ad-130">Seleccione los usuarios o los roles a los que deben concederse los permisos.</span><span class="sxs-lookup"><span data-stu-id="f05ad-130">Select the users or roles to whom permissions should be granted.</span></span>  
  
8.  <span data-ttu-id="f05ad-131">En la cuadrícula **Permisos explícitos** , seleccione los permisos que desea conceder al rol o al usuario especificados.</span><span class="sxs-lookup"><span data-stu-id="f05ad-131">In the **Explicit Permissions** grid, select the permissions to grant to the specified user or role.</span></span> <span data-ttu-id="f05ad-132">Para obtener una descripción de los permisos, vea [Permisos &#40;motor de base de datos&#41;](../security/permissions-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="f05ad-132">For a description of the permissions, see [Permissions &#40;Database Engine&#41;](../security/permissions-database-engine.md).</span></span>  
  
 <span data-ttu-id="f05ad-133">Al seleccionar **Conceder** , se indica que se concederá el permiso especificado al receptor.</span><span class="sxs-lookup"><span data-stu-id="f05ad-133">Selecting **Grant** indicates the grantee will be given the specified permission.</span></span> <span data-ttu-id="f05ad-134">Al seleccionar **Grant With** , se indica que el receptor también podrá conceder el permiso especificado a otras entidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f05ad-134">Selecting **Grant With** indicates that the grantee will also be able to grant the specified permission to other principals.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f05ad-135">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f05ad-135">Using Transact-SQL</span></span>  
  
#### <a name="to-grant-permissions-on-a-stored-procedure"></a><span data-ttu-id="f05ad-136">Para conceder permisos para un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="f05ad-136">To grant permissions on a stored procedure</span></span>  
  
1.  <span data-ttu-id="f05ad-137">Conéctese con el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f05ad-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f05ad-138">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="f05ad-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f05ad-139">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f05ad-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="f05ad-140">En este ejemplo se concede el permiso `EXECUTE` para el procedimiento almacenado `HumanResources.uspUpdateEmployeeHireInfo` a un rol de aplicación denominado `Recruiting11`.</span><span class="sxs-lookup"><span data-stu-id="f05ad-140">This example grants `EXECUTE` permission on the stored procedure `HumanResources.uspUpdateEmployeeHireInfo` to an application role named `Recruiting11`.</span></span>  
  
```sql  
USE AdventureWorks2012;   
GRANT EXECUTE ON OBJECT::HumanResources.uspUpdateEmployeeHireInfo  
    TO Recruiting11;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="f05ad-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f05ad-141">See Also</span></span>  
 <span data-ttu-id="f05ad-142">[sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f05ad-142">[sys.fn_builtin_permissions &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/sys-fn-builtin-permissions-transact-sql) </span></span>  
 <span data-ttu-id="f05ad-143">[Permisos de objeto GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f05ad-143">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="f05ad-144">[Crear un procedimiento almacenado](../stored-procedures/create-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f05ad-144">[Create a Stored Procedure](../stored-procedures/create-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="f05ad-145">[Modificar un procedimiento almacenado](modify-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f05ad-145">[Modify a Stored Procedure](modify-a-stored-procedure.md) </span></span>  
 <span data-ttu-id="f05ad-146">[Eliminar un procedimiento almacenado](../stored-procedures/delete-a-stored-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f05ad-146">[Delete a Stored Procedure](../stored-procedures/delete-a-stored-procedure.md) </span></span>  
 [<span data-ttu-id="f05ad-147">Cambiar el nombre de un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="f05ad-147">Rename a Stored Procedure</span></span>](rename-a-stored-procedure.md)  
  
  
