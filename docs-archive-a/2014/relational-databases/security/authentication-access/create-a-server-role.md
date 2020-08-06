---
title: Creación de un rol de servidor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverrole.members.f1
- SQL12.SWB.SERVERROLE.GENERAL.F1
- sql12.swb.serverrole.memberships.f1
helpviewer_keywords:
- SERVER ROLE, creating
ms.assetid: 74f19992-8082-4ed7-92a1-04fe676ee82d
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45c3d5bb9c9c7fdae9abe18ab3cb808cae4c1fa1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675779"
---
# <a name="create-a-server-role"></a><span data-ttu-id="69bc5-102">Crear un rol de servidor</span><span class="sxs-lookup"><span data-stu-id="69bc5-102">Create a Server Role</span></span>
  <span data-ttu-id="69bc5-103">En este tema se describe cómo crear un nuevo rol de servidor en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69bc5-103">This topic describes how to create a new server role in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="69bc5-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="69bc5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="69bc5-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="69bc5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="69bc5-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="69bc5-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="69bc5-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="69bc5-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="69bc5-108">**Para crear un nuevo rol de servidor, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="69bc5-108">**To create a new server role, using:**</span></span>  
  
     [<span data-ttu-id="69bc5-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69bc5-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="69bc5-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69bc5-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="69bc5-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="69bc5-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="69bc5-112">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="69bc5-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="69bc5-113">No se puede conceder permisos a los roles de servidor en elementos protegibles de nivel de base de datos.</span><span class="sxs-lookup"><span data-stu-id="69bc5-113">Server roles cannot be granted permission on database-level securables.</span></span> <span data-ttu-id="69bc5-114">Para crear roles de base de datos, vea [CREATE ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="69bc5-114">To create database roles, see [CREATE ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-role-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="69bc5-115">Seguridad</span><span class="sxs-lookup"><span data-stu-id="69bc5-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="69bc5-116">Permisos</span><span class="sxs-lookup"><span data-stu-id="69bc5-116">Permissions</span></span>  
  
-   <span data-ttu-id="69bc5-117">Se debe disponer del permiso CREATE SERVER CONTROL o pertenecer al rol fijo de servidor sysadmin.</span><span class="sxs-lookup"><span data-stu-id="69bc5-117">Requires CREATE SERVER ROLE permission or membership in the sysadmin fixed server role.</span></span>  
  
-   <span data-ttu-id="69bc5-118">También se requiere el permiso IMPERSONATE en *server_principal* para los inicios de sesión, el permiso ALTER para los roles de servidor que se han usado como *server_principal*o la pertenencia a un grupo de Windows que se ha usado como server_principal.</span><span class="sxs-lookup"><span data-stu-id="69bc5-118">Also requires IMPERSONATE on the *server_principal* for logins, ALTER permission for server roles used as the *server_principal*, or membership in a Windows group that is used as the server_principal.</span></span>  
  
-   <span data-ttu-id="69bc5-119">Cuando se utiliza la opción AUTHORIZATION para asignar la propiedad de roles de servidor, también se requieren los siguientes permisos:</span><span class="sxs-lookup"><span data-stu-id="69bc5-119">When you use the AUTHORIZATION option to assign server role ownership, the following permissions are also required:</span></span>  
  
    -   <span data-ttu-id="69bc5-120">La asignación de la propiedad de un rol de servidor a otro inicio de sesión requiere el permiso IMPERSONATE para ese inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="69bc5-120">To assign ownership of a server role to another login, requires IMPERSONATE permission on that login.</span></span>  
  
    -   <span data-ttu-id="69bc5-121">La asignación de la propiedad de un rol de servidor a otro rol de servidor requiere la pertenencia al rol de servidor receptor o el permiso ALTER para ese rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="69bc5-121">To assign ownership of a server role to another server role, requires membership in the recipient server role or ALTER permission on that server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="69bc5-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="69bc5-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="69bc5-123">Para crear un nuevo rol de servidor</span><span class="sxs-lookup"><span data-stu-id="69bc5-123">To create a new server role</span></span>  
  
1.  <span data-ttu-id="69bc5-124">En el Explorador de objetos, expanda el servidor donde desea crear el nuevo rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="69bc5-124">In Object Explorer, expand the server where you want to create the new server role.</span></span>  
  
2.  <span data-ttu-id="69bc5-125">Expanda la carpeta **Seguridad** .</span><span class="sxs-lookup"><span data-stu-id="69bc5-125">Expand the **Security** folder.</span></span>  
  
3.  <span data-ttu-id="69bc5-126">Haga clic con el botón derecho en la carpeta **Roles del servidor** y seleccione **Nuevo rol de servidor...** .</span><span class="sxs-lookup"><span data-stu-id="69bc5-126">Right-click the **Server Roles** folder and select **New Server Role...**.</span></span>  
  
4.  <span data-ttu-id="69bc5-127">En el cuadro de diálogo **nuevo rol de servidor-**_server_role_name_ , en la página **General** , escriba un nombre para el nuevo rol de servidor en el cuadro **nombre del rol de servidor** .</span><span class="sxs-lookup"><span data-stu-id="69bc5-127">In the **New Server Role -**_server_role_name_ dialog box, on the **General** page, enter a name for the new server role in the **Server role name** box.</span></span>  
  
5.  <span data-ttu-id="69bc5-128">En el cuadro **Propietario** , escriba el nombre de la entidad de seguridad del servidor que poseerá el nuevo rol.</span><span class="sxs-lookup"><span data-stu-id="69bc5-128">In the **Owner** box, enter the name of the server principal that will own the new role.</span></span> <span data-ttu-id="69bc5-129">Como alternativa, haga clic en los puntos suspensivos **(...)** para abrir el cuadro de diálogo **Seleccionar inicio de sesión o rol de servidor**.</span><span class="sxs-lookup"><span data-stu-id="69bc5-129">Alternately, click the ellipsis **(...)** to open the **Select Server Login or Role** dialog box.</span></span>  
  
6.  <span data-ttu-id="69bc5-130">En **Elementos protegibles**, seleccione uno o más elementos protegibles de nivel de servidor.</span><span class="sxs-lookup"><span data-stu-id="69bc5-130">Under **Securables**, select one or more server-level securables.</span></span> <span data-ttu-id="69bc5-131">Cuando se selecciona un elemento protegible, se pueden permitir o denegar permisos a este rol de servidor en dicho elemento protegible.</span><span class="sxs-lookup"><span data-stu-id="69bc5-131">When a securable is selected, this server role can be granted or denied permissions on that securable.</span></span>  
  
7.  <span data-ttu-id="69bc5-132">En el cuadro **Permisos: Explícitos**, active la casilla para conceder, conceder por concesión o denegar el permiso a este rol de servidor para los elementos protegibles seleccionados.</span><span class="sxs-lookup"><span data-stu-id="69bc5-132">In the **Permissions: Explicit** box, select the check box to grant, grant with grant, or deny permission to this server role for the selected securables.</span></span> <span data-ttu-id="69bc5-133">Si un permiso no se puede conceder o denegar a todos los elementos protegibles seleccionados, el permiso se representará como una selección parcial.</span><span class="sxs-lookup"><span data-stu-id="69bc5-133">If a permission cannot be granted or denied to all of the selected securables, the permission is represented as a partial select.</span></span>  
  
8.  <span data-ttu-id="69bc5-134">En la página **Miembros** , utilice el botón **Agregar** para agregar inicio de sesión que representan individuos o grupos al nuevo rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="69bc5-134">On the **Members** page, use the **Add** button to add logins that represent individuals or groups to the new server role.</span></span>  
  
9. <span data-ttu-id="69bc5-135">Un rol de servidor definido por el usuario puede ser miembro de otro rol de servidor.</span><span class="sxs-lookup"><span data-stu-id="69bc5-135">A user-defined server role can be a member of another server role.</span></span> <span data-ttu-id="69bc5-136">En la página **Pertenencias** , active una casilla para convertir el rol de servidor actual definido por el usuario en miembro de un rol de servidor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="69bc5-136">On the **Memberships** page, select a check box to make the current user-defined server role a member of a selected server role.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="69bc5-137">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="69bc5-137">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-new-server-role"></a><span data-ttu-id="69bc5-138">Para crear un nuevo rol de servidor</span><span class="sxs-lookup"><span data-stu-id="69bc5-138">To create a new server role</span></span>  
  
1.  <span data-ttu-id="69bc5-139">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69bc5-139">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="69bc5-140">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="69bc5-140">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="69bc5-141">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="69bc5-141">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    --Creates the server role auditors that is owned the securityadmin fixed server role.  
    USE master;  
    CREATE SERVER ROLE auditors AUTHORIZATION securityadmin;  
    GO  
    ```  
  
 <span data-ttu-id="69bc5-142">Para obtener más información, vea [CREATE SERVER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-role-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="69bc5-142">For more information, see [CREATE SERVER ROLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-server-role-transact-sql).</span></span>  
  
  
