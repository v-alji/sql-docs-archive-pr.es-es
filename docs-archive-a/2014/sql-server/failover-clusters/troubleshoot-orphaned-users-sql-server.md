---
title: Solucionar problemas de usuarios huérfanos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- orphaned users [SQL Server]
- logins [SQL Server], orphaned users
- troubleshooting [SQL Server], user accounts
- user accounts [SQL Server], orphaned users
- failover [SQL Server], managing metadata
- database mirroring [SQL Server], metadata
- users [SQL Server], orphaned
ms.assetid: 11eefa97-a31f-4359-ba5b-e92328224133
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5df714d818949b921ff2236e50d58913eab0e0db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672573"
---
# <a name="troubleshoot-orphaned-users-sql-server"></a><span data-ttu-id="b6142-102">Solucionar problemas de usuarios huérfanos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b6142-102">Troubleshoot Orphaned Users (SQL Server)</span></span>
  <span data-ttu-id="b6142-103">Para iniciar sesión en una instancia de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], una entidad de seguridad debe tener un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] válido.</span><span class="sxs-lookup"><span data-stu-id="b6142-103">To log into an instance of Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a principal must have a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="b6142-104">Este inicio de sesión se utiliza en el proceso de autenticación que comprueba si la entidad de seguridad tiene permiso para conectarse a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6142-104">This login is used in the authentication process that verifies whether the principal is allowed to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b6142-105">Los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inicios de sesión de una instancia de servidor son visibles en la vista de catálogo **sys. server_principals** y en la vista de compatibilidad **inicios de sesiónsys.sys** .</span><span class="sxs-lookup"><span data-stu-id="b6142-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins on a server instance are visible in the **sys.server_principals** catalog view and the **sys.syslogins** compatibility view.</span></span>  
  
 <span data-ttu-id="b6142-106">Los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tienen acceso a bases de datos individuales mediante un usuario de base de datos que está asignado al inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6142-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins access individual databases using a database user that is mapped to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="b6142-107">Esta regla tiene dos excepciones:</span><span class="sxs-lookup"><span data-stu-id="b6142-107">There are two exceptions to this rule:</span></span>  
  
-   <span data-ttu-id="b6142-108">La cuenta de invitado.</span><span class="sxs-lookup"><span data-stu-id="b6142-108">The guest account.</span></span>  
  
     <span data-ttu-id="b6142-109">Al habilitar esta cuenta en la base de datos, se habilitan todos los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que no estén asignados a un usuario de base de datos para entrar en la base de datos como usuario invitado.</span><span class="sxs-lookup"><span data-stu-id="b6142-109">This is an account that, when enabled in the database, enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are not mapped to a database user to enter the database as the guest user.</span></span>  
  
-   <span data-ttu-id="b6142-110">La pertenencia a grupos de Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="b6142-110">Microsoft Windows group memberships.</span></span>  
  
     <span data-ttu-id="b6142-111">Un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creado desde un usuario de Windows puede entrar en una base de datos si este usuario es miembro de un grupo de Windows que también sea usuario en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b6142-111">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login created from a Windows user can enter a database if the Windows user is a member of a Windows group that is also a user in the database.</span></span>  
  
 <span data-ttu-id="b6142-112">La información sobre la asignación de un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un usuario de la base de datos se almacena en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b6142-112">Information about the mapping of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to a database user is stored within the database.</span></span> <span data-ttu-id="b6142-113">Incluye el nombre del usuario de la base de datos y el SID del inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b6142-113">It includes the name of the database user and the SID of the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="b6142-114">Los permisos de este usuario de la base de datos se utilizan para otorgar autorizaciones en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b6142-114">The permissions of this database user are used for authorization in the database.</span></span>  
  
 <span data-ttu-id="b6142-115">Un usuario de base de datos cuyo inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondiente está sin definir o se ha definido de forma incorrecta en una instancia de servidor no podrá iniciar una sesión en la instancia.</span><span class="sxs-lookup"><span data-stu-id="b6142-115">A database user for which the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is undefined or is incorrectly defined on a server instance cannot log in to the instance.</span></span> <span data-ttu-id="b6142-116">Es lo que se denomina un *usuario huérfano* de la base de datos en esa instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="b6142-116">Such a user is said to be an *orphaned user* of the database on that server instance.</span></span> <span data-ttu-id="b6142-117">Un usuario de base de datos puede convertirse en huérfano si se quita el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b6142-117">A database user can become orphaned if the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is dropped.</span></span> <span data-ttu-id="b6142-118">También puede convertirse en huérfano si una base de datos se restaura o se conecta a otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6142-118">Also, a database user can become orphaned after a database is restored or attached to a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b6142-119">Otra manera de convertirse en huérfano es que el SID al que se asigna el usuario de la base de datos no esté presente en la nueva instancia de servidor.</span><span class="sxs-lookup"><span data-stu-id="b6142-119">Orphaning can happen if the database user is mapped to a SID that is not present in the new server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6142-120">Un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Inicio de sesión no puede tener acceso a una base de datos en la que falta un usuario de base de datos correspondiente a menos que el **invitado** esté habilitado en esa base de datos.</span><span class="sxs-lookup"><span data-stu-id="b6142-120">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login cannot access a database in which it lacks a corresponding database user unless **guest** is enabled in that database.</span></span> <span data-ttu-id="b6142-121">Para obtener información sobre cómo crear una cuenta de usuario de base de datos, vea [Create user &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b6142-121">For information about creating a database user account, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="to-detect-orphaned-users"></a><span data-ttu-id="b6142-122">Para detectar usuarios huérfanos</span><span class="sxs-lookup"><span data-stu-id="b6142-122">To Detect Orphaned Users</span></span>  
 <span data-ttu-id="b6142-123">Ejecute las instrucciones de Transact-SQL siguientes: </span><span class="sxs-lookup"><span data-stu-id="b6142-123">To detect orphaned users, execute the following Transact-SQL statements:</span></span>  
  
```  
USE <database_name>;  
GO;   
sp_change_users_login @Action='Report';  
GO;  
```  
  
 <span data-ttu-id="b6142-124">En los resultados se enumeran los usuarios y sus identificadores de seguridad (SID) correspondientes, que se encuentran en la base de datos actual y no están vinculados a ningún inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6142-124">The output lists the users and corresponding security identifiers (SID) in the current database that are not linked to any [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="b6142-125">Para obtener más información, vea [sp_change_users_login &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b6142-125">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6142-126">no se puede usar **sp_change_users_login** con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inicios de sesión creados desde Windows.</span><span class="sxs-lookup"><span data-stu-id="b6142-126">**sp_change_users_login** cannot be used with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins that are created from Windows.</span></span>  
  
## <a name="to-resolve-an-orphaned-user"></a><span data-ttu-id="b6142-127">Para resolver un usuario huérfano</span><span class="sxs-lookup"><span data-stu-id="b6142-127">To Resolve an Orphaned User</span></span>  
 <span data-ttu-id="b6142-128">Utilice el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="b6142-128">To resolve an orphaned user, use the following procedure:</span></span>  
  
1.  <span data-ttu-id="b6142-129">El siguiente comando volver a vincular la cuenta de inicio de sesión del servidor especificada por *<login_name>* con el usuario de base de datos especificado por \*<database_user \*>.</span><span class="sxs-lookup"><span data-stu-id="b6142-129">The following command relinks the server login account specified by *<login_name>* with the database user specified by *<database_user>*.</span></span>  
  
    ```  
    USE <database_name>;  
    GO  
    sp_change_users_login @Action='update_one', @UserNamePattern='<database_user>', @LoginName='<login_name>';  
    GO  
  
    ```  
  
     <span data-ttu-id="b6142-130">Para obtener más información, vea [sp_change_users_login &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b6142-130">For more information, see [sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql).</span></span>  
  
2.  <span data-ttu-id="b6142-131">Una vez ejecutado el código del paso anterior, el usuario podrá obtener acceso a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b6142-131">After you run the code in the preceding step, the user can access the database.</span></span> <span data-ttu-id="b6142-132">A continuación, el usuario puede modificar la contraseña de la *<login_name>* cuenta de inicio de sesión mediante el procedimiento almacenado **sp_password** , como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b6142-132">The user then can alter the password of the *<login_name>* login account by using the **sp_password** stored procedure, as follows:</span></span>  
  
    ```  
    USE master   
    GO  
    sp_password @old=NULL, @new='password', @loginame='<login_name>';  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b6142-133">Solo los inicios de sesión con el permiso ALTER ANY LOGIN pueden cambiar la contraseña de inicio de sesión de otro usuario.</span><span class="sxs-lookup"><span data-stu-id="b6142-133">Only logins with the ALTER ANY LOGIN permission can change the password of another user's login.</span></span> <span data-ttu-id="b6142-134">Sin embargo, solo los miembros del rol **sysadmin** pueden modificar las contraseñas de los miembros del rol **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="b6142-134">However, only members of the **sysadmin** role can modify passwords of **sysadmin** role members.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b6142-135">no se puede usar **sp_password** para [!INCLUDE[msCoName](../../includes/msconame-md.md)] las cuentas de Windows.</span><span class="sxs-lookup"><span data-stu-id="b6142-135">**sp_password** cannot be used for [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows accounts.</span></span> <span data-ttu-id="b6142-136">Windows autentica los usuarios que se conectan a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a través de su cuenta de red de Windows y, por tanto, sus contraseñas solo se pueden cambiar en Windows.</span><span class="sxs-lookup"><span data-stu-id="b6142-136">Users connecting to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through their Windows network account are authenticated by Windows; therefore, their passwords can only be changed in Windows.</span></span>  
  
     <span data-ttu-id="b6142-137">Para obtener más información, vea [sp_password &#40;&#41;de Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b6142-137">For more information, see [sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6142-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6142-138">See Also</span></span>  
 <span data-ttu-id="b6142-139">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6142-139">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="b6142-140">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6142-140">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="b6142-141">[sp_change_users_login &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6142-141">[sp_change_users_login &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-users-login-transact-sql) </span></span>  
 <span data-ttu-id="b6142-142">[sp_addlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6142-142">[sp_addlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addlogin-transact-sql) </span></span>  
 <span data-ttu-id="b6142-143">[sp_grantlogin &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6142-143">[sp_grantlogin &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-grantlogin-transact-sql) </span></span>  
 <span data-ttu-id="b6142-144">[sp_password &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6142-144">[sp_password &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-password-transact-sql) </span></span>  
 <span data-ttu-id="b6142-145">[sys.sysusuarios &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b6142-145">[sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql) </span></span>  
 [<span data-ttu-id="b6142-146">Inicios de sesión desys.sys&#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b6142-146">sys.syslogins &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-compatibility-views/sys-syslogins-transact-sql)  
  
  
