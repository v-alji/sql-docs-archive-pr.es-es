---
title: Combinación de un rol | Microsoft Docs
ms.custom: ''
ms.date: 07/14/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.MEMBERSHIP.F1
helpviewer_keywords:
- adding a member to a role
- join a role
ms.assetid: 05c8d10d-5823-46c6-8b1a-81722da6a42b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 58e8c071672c8c3afba8d6c424488899dcf76be7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669560"
---
# <a name="join-a-role"></a><span data-ttu-id="ecd4c-102">combinar un rol</span><span class="sxs-lookup"><span data-stu-id="ecd4c-102">Join a Role</span></span>
  <span data-ttu-id="ecd4c-103">En este tema se describe cómo asignar roles a inicios de sesión y a usuarios de base de datos en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecd4c-103">This topic describes how to assign roles to logins and database users in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ecd4c-104">Use los roles de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para administrar eficazmente los permisos.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-104">Use roles in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to efficiently manage permissions.</span></span> <span data-ttu-id="ecd4c-105">Asigne permisos a roles y, a continuación, agregue o quite usuarios e inicios de sesión a los roles.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-105">Assign permissions to roles, and then add and remove users and logins to the roles.</span></span> <span data-ttu-id="ecd4c-106">Mediante el uso de roles, los permisos no se tienen que mantener individualmente para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-106">By using roles, permissions do not have to be individually maintained for each user.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="ecd4c-107">admite cuatro tipos de roles.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-107">supports four types of roles.</span></span>  
  
-   <span data-ttu-id="ecd4c-108">Roles fijos de servidor</span><span class="sxs-lookup"><span data-stu-id="ecd4c-108">Fixed server roles</span></span>  
  
-   <span data-ttu-id="ecd4c-109">Roles de servidor definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="ecd4c-109">User-defined server roles</span></span>  
  
-   <span data-ttu-id="ecd4c-110">Roles fijos de base de datos</span><span class="sxs-lookup"><span data-stu-id="ecd4c-110">Fixed database roles</span></span>  
  
-   <span data-ttu-id="ecd4c-111">Roles de base de datos definidos por el usuario</span><span class="sxs-lookup"><span data-stu-id="ecd4c-111">User-defined database roles</span></span>  
  
 <span data-ttu-id="ecd4c-112">Los roles fijos están disponibles automáticamente en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecd4c-112">The fixed roles are automatically available in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ecd4c-113">Estos roles disponen de los permisos necesarios para realizar las tareas habituales.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-113">Fixed roles have the necessary permissions to accomplish common tasks.</span></span> <span data-ttu-id="ecd4c-114">Para obtener más información sobre los roles fijos, vea los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="ecd4c-114">For more information about fixed roles, see the following links.</span></span> <span data-ttu-id="ecd4c-115">El usuario crea los roles definidos por el usuario y se pueden personalizar con los permisos que se seleccionen.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-115">User-defined roles are created by you, and can be customized with the permissions that you select.</span></span> <span data-ttu-id="ecd4c-116">Para obtener más información sobre los roles definidos por el usuario, vea los siguientes vínculos:</span><span class="sxs-lookup"><span data-stu-id="ecd4c-116">For more information about user-defined roles, see the following links.</span></span>  
  
 <span data-ttu-id="ecd4c-117">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="ecd4c-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ecd4c-118">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="ecd4c-118">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ecd4c-119">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ecd4c-119">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ecd4c-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ecd4c-120">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ecd4c-121">**Para asignar roles a inicios de sesión y a usuarios de base de datos, usando:**</span><span class="sxs-lookup"><span data-stu-id="ecd4c-121">**To assign roles to logins and database users, using:**</span></span>  
  
     [<span data-ttu-id="ecd4c-122">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ecd4c-122">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ecd4c-123">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ecd4c-123">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ecd4c-124">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ecd4c-124">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ecd4c-125">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ecd4c-125">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ecd4c-126">El cambio de nombre de un rol de base de datos no modifica el número de identificación, el propietario, ni los permisos del rol.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-126">Changing the name of a database role does not change ID number, owner, or permissions of the role.</span></span>  
  
-   <span data-ttu-id="ecd4c-127">Los roles de base de datos se pueden ver en las vistas de catálogos sys.database_role_members y sys.database_principals.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-127">Database roles are visible in the sys.database_role_members and sys.database_principals catalog views.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ecd4c-128">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ecd4c-128">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ecd4c-129">Permisos</span><span class="sxs-lookup"><span data-stu-id="ecd4c-129">Permissions</span></span>  
 <span data-ttu-id="ecd4c-130">Requiere `ALTER ANY ROLE` el permiso en la base de datos, `ALTER` el permiso en el rol o la pertenencia a **db_securityadmin**.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-130">Requires `ALTER ANY ROLE` permission on the database, `ALTER` permission on the role, or membership in **db_securityadmin**.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ecd4c-131">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ecd4c-131">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="ecd4c-132">Para agregar un miembro a un rol fijo de servidor</span><span class="sxs-lookup"><span data-stu-id="ecd4c-132">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="ecd4c-133">En el Explorador de objetos, expanda el servidor en el que desea modificar un rol fijo de servidor.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-133">In Object Explorer, expand the server in which you want to edit a fixed server role.</span></span>  
  
2.  <span data-ttu-id="ecd4c-134">Expanda la carpeta **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="ecd4c-134">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="ecd4c-135">Expanda la carpeta **Roles de servidor** .</span><span class="sxs-lookup"><span data-stu-id="ecd4c-135">Expand the **Server Roles** folder</span></span>  
  
4.  <span data-ttu-id="ecd4c-136">Haga clic con el botón derecho en el rol que quiere editar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-136">Right-click the role you want to edit and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="ecd4c-137">En el cuadro de diálogo **propiedades de rol de servidor-**_server_role_name_ , en la página **miembros** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-137">In the **Server Role Properties -**_server_role_name_ dialog box, on the **Members** page, click **Add**.</span></span>  
  
6.  <span data-ttu-id="ecd4c-138">En el cuadro de diálogo **Seleccionar inicio de sesión o rol de servidor** , en **Escribir los nombres de objeto para seleccionar (ejemplos)** , especifique el inicio de sesión o el rol de servidor que quiere agregar a este rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-138">In the **Select Server Login or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or server role to add to this server role.</span></span> <span data-ttu-id="ecd4c-139">O bien, haga clic en **Examinar...** y seleccione cualquier objeto disponible en el cuadro de diálogo **Buscar objetos** o todos ellos.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-139">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="ecd4c-140">Haga clic en **Aceptar** para volver al cuadro **de diálogo Propiedades del rol de servidor-**_server_role_name_ .</span><span class="sxs-lookup"><span data-stu-id="ecd4c-140">Click **OK** to return to the **Server Role Properties -**_server_role_name_ dialog box.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="ecd4c-141">Para agregar un miembro a un rol de base de datos definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="ecd4c-141">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="ecd4c-142">En el Explorador de objetos, expanda el servidor en el que desea editar un rol de base de datos definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-142">In Object Explorer, expand the server in which you want to edit a user-defined database role.</span></span>  
  
2.  <span data-ttu-id="ecd4c-143">Expanda la carpeta **Bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="ecd4c-143">Expand the **Databases** folder.</span></span>  
  
3.  <span data-ttu-id="ecd4c-144">Expanda la base de datos en la que desea editar un rol de base de datos definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-144">Expand the database in which you want to edit a user-defined database role.</span></span>  
  
4.  <span data-ttu-id="ecd4c-145">Expanda la carpeta **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="ecd4c-145">Expand the **Security** folder.</span></span>  
  
5.  <span data-ttu-id="ecd4c-146">Expanda la carpeta **Roles** .</span><span class="sxs-lookup"><span data-stu-id="ecd4c-146">Expand the **Roles** folder.</span></span>  
  
6.  <span data-ttu-id="ecd4c-147">Expanda la carpeta **Roles de servidor** .</span><span class="sxs-lookup"><span data-stu-id="ecd4c-147">Expand the **Server Roles** folder.</span></span>  
  
7.  <span data-ttu-id="ecd4c-148">Haga clic con el botón derecho en el rol que quiere editar y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-148">Right-click the role you want to edit and select **Properties**.</span></span>  
  
8.  <span data-ttu-id="ecd4c-149">En el cuadro de diálogo **propiedades del rol de la base de datos-**_database_role_name_ , en la página **General** , haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-149">In the **Database Role Properties -**_database_role_name_ dialog box, in the **General** page, click **Add**.</span></span>  
  
9. <span data-ttu-id="ecd4c-150">En el cuadro de diálogo **Seleccionar usuario o rol de base de datos** , en **Escribir los nombres de objeto para seleccionar (ejemplos)** , especifique el inicio de sesión o el rol de la base de datos que quiere agregar a este rol de base de datos.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-150">In the **Select Database User or Role** dialog box, under **Enter the object names to select (examples)**, enter the login or database role to add to this database role.</span></span> <span data-ttu-id="ecd4c-151">O bien, haga clic en **Examinar...** y seleccione cualquier objeto disponible en el cuadro de diálogo **Buscar objetos** o todos ellos.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-151">Alternately, click **Browse...** and select any or all of the available objects in the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="ecd4c-152">Haga clic en **Aceptar** para volver al cuadro **de diálogo Propiedades del rol de la base de datos-**_database_role_name_ .</span><span class="sxs-lookup"><span data-stu-id="ecd4c-152">Click **OK** to return to the **Database Role Properties -**_database_role_name_ dialog box.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ecd4c-153">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ecd4c-153">Using Transact-SQL</span></span>  
  
#### <a name="to-add-a-member-to-a-fixed-server-role"></a><span data-ttu-id="ecd4c-154">Para agregar un miembro a un rol fijo de servidor</span><span class="sxs-lookup"><span data-stu-id="ecd4c-154">To add a member to a fixed server role</span></span>  
  
1.  <span data-ttu-id="ecd4c-155">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecd4c-155">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ecd4c-156">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-156">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ecd4c-157">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-157">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER SERVER ROLE diskadmin ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="ecd4c-158">Para obtener más información, vea [ALTER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ecd4c-158">For more information, see [ALTER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-role-transact-sql).</span></span>  
  
#### <a name="to-add-a-member-to-a-user-defined-database-role"></a><span data-ttu-id="ecd4c-159">Para agregar un miembro a un rol de base de datos definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="ecd4c-159">To add a member to a user-defined database role</span></span>  
  
1.  <span data-ttu-id="ecd4c-160">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecd4c-160">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ecd4c-161">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-161">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ecd4c-162">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="ecd4c-162">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER ROLE Marketing ADD MEMBER [Domain\Juan] ;  
    GO  
    ```  
  
 <span data-ttu-id="ecd4c-163">Para obtener más información, vea [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ecd4c-163">For more information, see [sp_addrolemember &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addrolemember-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecd4c-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ecd4c-164">See Also</span></span>  
 <span data-ttu-id="ecd4c-165">[Roles de nivel de servidor](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="ecd4c-165">[Server-Level Roles](server-level-roles.md) </span></span>  
 <span data-ttu-id="ecd4c-166">[Roles de nivel de base de datos](../authentication-access/database-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="ecd4c-166">[Database-Level Roles](../authentication-access/database-level-roles.md) </span></span>  
 [<span data-ttu-id="ecd4c-167">Roles de aplicación</span><span class="sxs-lookup"><span data-stu-id="ecd4c-167">Application Roles</span></span>](../authentication-access/application-roles.md)  
  
  
