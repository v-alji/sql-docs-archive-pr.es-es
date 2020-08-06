---
title: Entidades de seguridad (motor de base de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.roleproperties.selectroll.f1
- sql12.swb.databaseuser.permissions.user.f1--May use common.permissions
helpviewer_keywords:
- certificates [SQL Server], principals
- roles [SQL Server], principals
- permissions [SQL Server], principals
- '##MS_SQLAuthenticatorCertificate##'
- principals [SQL Server]
- '##MS_SQLResourceSigningCertificate##'
- groups [SQL Server], principals
- '##MS_AgentSigningCertificate##'
- authentication [SQL Server], principals
- schemas [SQL Server], principals
- principals [SQL Server], about principals
- security [SQL Server], principals
- users [SQL Server], principals
- '##MS_SQLReplicationSigningCertificate##'
ms.assetid: 3f7adbf7-6e40-4396-a8ca-71cbb843b5c2
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 808c8516b3ed9e95ea4c724736461cb00923a7fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677505"
---
# <a name="principals-database-engine"></a><span data-ttu-id="4dd18-102">Entidades de seguridad (motor de base de datos)</span><span class="sxs-lookup"><span data-stu-id="4dd18-102">Principals (Database Engine)</span></span>
  <span data-ttu-id="4dd18-103">Las*entidades de seguridad* son entidades que pueden solicitar recursos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4dd18-103">*Principals* are entities that can request [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] resources.</span></span> <span data-ttu-id="4dd18-104">Igual que otros componentes del modelo de autorización de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , las entidades de seguridad se pueden organizar en jerarquías.</span><span class="sxs-lookup"><span data-stu-id="4dd18-104">Like other components of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authorization model, principals can be arranged in a hierarchy.</span></span> <span data-ttu-id="4dd18-105">El ámbito de influencia de una entidad de seguridad depende del ámbito de la definición de la entidad de seguridad: Windows, servidor, base de datos; y si la entidad de seguridad es indivisible o es una colección.</span><span class="sxs-lookup"><span data-stu-id="4dd18-105">The scope of influence of a principal depends on the scope of the definition of the principal: Windows, server, database; and whether the principal is indivisible or a collection.</span></span> <span data-ttu-id="4dd18-106">Un Inicio de sesión de Windows es un ejemplo de entidad de seguridad indivisible y un Grupo de Windows es un ejemplo de una del tipo colección.</span><span class="sxs-lookup"><span data-stu-id="4dd18-106">A Windows Login is an example of an indivisible principal, and a Windows Group is an example of a principal that is a collection.</span></span> <span data-ttu-id="4dd18-107">Toda entidad de seguridad tiene un identificador de seguridad (SID).</span><span class="sxs-lookup"><span data-stu-id="4dd18-107">Every principal has a security identifier (SID).</span></span>  
  
 <span data-ttu-id="4dd18-108">**Entidades de seguridad a nivel de Windows**</span><span class="sxs-lookup"><span data-stu-id="4dd18-108">**Windows-level principals**</span></span>  
  
-   <span data-ttu-id="4dd18-109">Inicio de sesión del dominio de Windows</span><span class="sxs-lookup"><span data-stu-id="4dd18-109">Windows Domain Login</span></span>  
  
-   <span data-ttu-id="4dd18-110">Inicio de sesión local de Windows</span><span class="sxs-lookup"><span data-stu-id="4dd18-110">Windows Local Login</span></span>  
  
 <span data-ttu-id="4dd18-111">**SQL Server** - **level** **entidades** de seguridad de nivel</span><span class="sxs-lookup"><span data-stu-id="4dd18-111">**SQL Server**-**level** **principals**</span></span>  
  
-   <span data-ttu-id="4dd18-112">Inicio de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dd18-112">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Login</span></span>  
  
-   <span data-ttu-id="4dd18-113">Rol del servidor</span><span class="sxs-lookup"><span data-stu-id="4dd18-113">Server Role</span></span>  
  
 <span data-ttu-id="4dd18-114">**Entidades de seguridad de nivel de bases de datos**</span><span class="sxs-lookup"><span data-stu-id="4dd18-114">**Database-level principals**</span></span>  
  
-   <span data-ttu-id="4dd18-115">Usuario de la base de datos</span><span class="sxs-lookup"><span data-stu-id="4dd18-115">Database User</span></span>  
  
-   <span data-ttu-id="4dd18-116">Rol de base de datos</span><span class="sxs-lookup"><span data-stu-id="4dd18-116">Database Role</span></span>  
  
-   <span data-ttu-id="4dd18-117">Rol de aplicación</span><span class="sxs-lookup"><span data-stu-id="4dd18-117">Application Role</span></span>  
  
## <a name="the-sql-server-sa-login"></a><span data-ttu-id="4dd18-118">Inicio de sesión sa de SQL Server</span><span class="sxs-lookup"><span data-stu-id="4dd18-118">The SQL Server sa Login</span></span>  
 <span data-ttu-id="4dd18-119">El inicio de sesión sa de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] es una entidad de seguridad de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="4dd18-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sa log in is a server-level principal.</span></span> <span data-ttu-id="4dd18-120">Se crea de forma predeterminada cuando se instala una instancia.</span><span class="sxs-lookup"><span data-stu-id="4dd18-120">By default, it is created when an instance is installed.</span></span> <span data-ttu-id="4dd18-121">A partir de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], la base de datos predeterminada de sa es master.</span><span class="sxs-lookup"><span data-stu-id="4dd18-121">Beginning in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the default database of sa is master.</span></span> <span data-ttu-id="4dd18-122">Es un cambio de comportamiento con respecto a versiones anteriores de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4dd18-122">This is a change of behavior from earlier versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="public-database-role"></a><span data-ttu-id="4dd18-123">Rol de base de datos public</span><span class="sxs-lookup"><span data-stu-id="4dd18-123">public Database Role</span></span>  
 <span data-ttu-id="4dd18-124">Todos los usuarios de una base de datos pertenecen al rol de base de datos public.</span><span class="sxs-lookup"><span data-stu-id="4dd18-124">Every database user belongs to the public database role.</span></span> <span data-ttu-id="4dd18-125">Cuando a un usuario no se le han concedido ni denegado permisos concretos para un elemento protegible, hereda los permisos para ese elemento concedidos a public.</span><span class="sxs-lookup"><span data-stu-id="4dd18-125">When a user has not been granted or denied specific permissions on a securable, the user inherits the permissions granted to public on that securable.</span></span>  
  
## <a name="information_schema-and-sys"></a><span data-ttu-id="4dd18-126">INFORMATION_SCHEMA y sys</span><span class="sxs-lookup"><span data-stu-id="4dd18-126">INFORMATION_SCHEMA and sys</span></span>  
 <span data-ttu-id="4dd18-127">Todas las bases de datos incluyen dos entidades que aparecen como usuarios en las vistas de catálogo: INFORMATION_SCHEMA y sys.</span><span class="sxs-lookup"><span data-stu-id="4dd18-127">Every database includes two entities that appear as users in catalog views: INFORMATION_SCHEMA and sys.</span></span> <span data-ttu-id="4dd18-128">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]necesita estas dos entidades.</span><span class="sxs-lookup"><span data-stu-id="4dd18-128">These entities are required by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4dd18-129">No son entidades de seguridad y no se pueden modificar ni quitar.</span><span class="sxs-lookup"><span data-stu-id="4dd18-129">They are not principals, and they cannot be modified or dropped.</span></span>  
  
## <a name="certificate-based-sql-server-logins"></a><span data-ttu-id="4dd18-130">Inicios de sesión de SQL Server basados en certificados</span><span class="sxs-lookup"><span data-stu-id="4dd18-130">Certificate-based SQL Server Logins</span></span>  
 <span data-ttu-id="4dd18-131">Las entidades de seguridad de servidor con nombres incluidos entre signos de número dobles (##) son exclusivamente para uso interno del sistema.</span><span class="sxs-lookup"><span data-stu-id="4dd18-131">Server principals with names enclosed by double hash marks (##) are for internal system use only.</span></span> <span data-ttu-id="4dd18-132">Las siguientes entidades de seguridad se crean a partir de certificados cuando se instala [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y no deben eliminarse.</span><span class="sxs-lookup"><span data-stu-id="4dd18-132">The following principals are created from certificates when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is installed, and should not be deleted.</span></span>  
  
-   <span data-ttu-id="4dd18-133">\##MS_SQLResourceSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="4dd18-133">\##MS_SQLResourceSigningCertificate##</span></span>  
  
-   <span data-ttu-id="4dd18-134">\##MS_SQLReplicationSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="4dd18-134">\##MS_SQLReplicationSigningCertificate##</span></span>  
  
-   <span data-ttu-id="4dd18-135">\##MS_SQLAuthenticatorCertificate##</span><span class="sxs-lookup"><span data-stu-id="4dd18-135">\##MS_SQLAuthenticatorCertificate##</span></span>  
  
-   <span data-ttu-id="4dd18-136">\##MS_AgentSigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="4dd18-136">\##MS_AgentSigningCertificate##</span></span>  
  
-   <span data-ttu-id="4dd18-137">\##MS_PolicyEventProcessingLogin##</span><span class="sxs-lookup"><span data-stu-id="4dd18-137">\##MS_PolicyEventProcessingLogin##</span></span>  
  
-   <span data-ttu-id="4dd18-138">\##MS_PolicySigningCertificate##</span><span class="sxs-lookup"><span data-stu-id="4dd18-138">\##MS_PolicySigningCertificate##</span></span>  
  
-   <span data-ttu-id="4dd18-139">\##MS_PolicyTsqlExecutionLogin##</span><span class="sxs-lookup"><span data-stu-id="4dd18-139">\##MS_PolicyTsqlExecutionLogin##</span></span>  
  
## <a name="the-guest-user"></a><span data-ttu-id="4dd18-140">Usuario guest</span><span class="sxs-lookup"><span data-stu-id="4dd18-140">The guest User</span></span>  
 <span data-ttu-id="4dd18-141">Cada base de datos incluye un usuario **guest**.</span><span class="sxs-lookup"><span data-stu-id="4dd18-141">Each database includes a **guest**.</span></span> <span data-ttu-id="4dd18-142">Los permisos concedidos al usuario **guest** se aplican a todos los usuarios que tienen acceso a la base de datos, pero no disponen de una cuenta en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4dd18-142">Permissions granted to the **guest** user are inherited by users who have access to the database, but who do not have a user account in the database.</span></span> <span data-ttu-id="4dd18-143">No se puede quitar el usuario **Guest** , pero se puede deshabilitar si se revoca su `CONNECT` permiso.</span><span class="sxs-lookup"><span data-stu-id="4dd18-143">The **guest** user cannot be dropped, but it can be disabled by revoking it's `CONNECT` permission.</span></span> <span data-ttu-id="4dd18-144">El `CONNECT` permiso se puede revocar si se ejecuta `REVOKE CONNECT FROM GUEST` en cualquier base de datos que no sea Master o tempdb.</span><span class="sxs-lookup"><span data-stu-id="4dd18-144">The `CONNECT` permission can be revoked by executing `REVOKE CONNECT FROM GUEST` within any database other than master or tempdb.</span></span>  
  
## <a name="client-and-database-server"></a><span data-ttu-id="4dd18-145">Cliente y servidor de base de datos</span><span class="sxs-lookup"><span data-stu-id="4dd18-145">Client and Database Server</span></span>  
 <span data-ttu-id="4dd18-146">Por definición, un cliente y un servidor de base de datos son entidades de seguridad y se pueden proteger.</span><span class="sxs-lookup"><span data-stu-id="4dd18-146">By definition, a client and a database server are security principals and can be secured.</span></span> <span data-ttu-id="4dd18-147">Estas entidades se pueden autenticar mutuamente antes de establecer una conexión de red segura.</span><span class="sxs-lookup"><span data-stu-id="4dd18-147">These entities can be mutually authenticated before a secure network connection is established.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="4dd18-148">admite el protocolo de autenticación [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) , que define cómo interactúan los clientes con un servicio de autenticación de red.</span><span class="sxs-lookup"><span data-stu-id="4dd18-148">supports the [Kerberos](https://go.microsoft.com/fwlink/?LinkId=100758) authentication protocol, which defines how clients interact with a network authentication service.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="4dd18-149">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="4dd18-149">Related Tasks</span></span>  
 <span data-ttu-id="4dd18-150">Los temas siguientes se incluyen en esta sección de Libros en pantalla de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4dd18-150">The following topics are included in this section of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online:</span></span>  
  
-   [<span data-ttu-id="4dd18-151">Temas de procedimientos de la administración de inicios de sesión, usuarios y esquemas</span><span class="sxs-lookup"><span data-stu-id="4dd18-151">Managing Logins, Users, and Schemas How-to Topics</span></span>](managing-logins-users-and-schemas-how-to-topics.md)  
  
-   [<span data-ttu-id="4dd18-152">Roles de nivel de servidor</span><span class="sxs-lookup"><span data-stu-id="4dd18-152">Server-Level Roles</span></span>](server-level-roles.md)  
  
-   [<span data-ttu-id="4dd18-153">Roles de nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="4dd18-153">Database-Level Roles</span></span>](database-level-roles.md)  
  
-   [<span data-ttu-id="4dd18-154">Roles de aplicación</span><span class="sxs-lookup"><span data-stu-id="4dd18-154">Application Roles</span></span>](application-roles.md)  
  
## <a name="see-also"></a><span data-ttu-id="4dd18-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4dd18-155">See Also</span></span>  
 <span data-ttu-id="4dd18-156">[Proteger SQL Server](../securing-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4dd18-156">[Securing SQL Server](../securing-sql-server.md) </span></span>  
 <span data-ttu-id="4dd18-157">[sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4dd18-157">[sys.database_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-principals-transact-sql) </span></span>  
 <span data-ttu-id="4dd18-158">[sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4dd18-158">[sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) </span></span>  
 <span data-ttu-id="4dd18-159">[sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4dd18-159">[sys.sql_logins &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) </span></span>  
 <span data-ttu-id="4dd18-160">[sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4dd18-160">[sys.database_role_members &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-role-members-transact-sql) </span></span>  
 <span data-ttu-id="4dd18-161">[Roles de nivel de servidor](server-level-roles.md) </span><span class="sxs-lookup"><span data-stu-id="4dd18-161">[Server-Level Roles](server-level-roles.md) </span></span>  
 [<span data-ttu-id="4dd18-162">Roles de nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="4dd18-162">Database-Level Roles</span></span>](database-level-roles.md)  
  
  
