---
title: Creación de un inicio de sesión | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.LOGIN.SERVERROLES.F1
- sql12.swb.login.databaseaccess.f1
- sql12.swb.login.general.f1
- sql12.swb.login.effectivepermissions.f1
- sql12.swb.login.status.f1
helpviewer_keywords:
- authentication [SQL Server], logins
- logins [SQL Server], creating
- creating logins with Management Studio
- Create login [SQL Server]
- SQL Server logins
ms.assetid: fb163e47-1546-4682-abaa-8c9494e9ddc7
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e476880103a69ae016c6720f36e26ef884db6f5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745147"
---
# <a name="create-a-login"></a><span data-ttu-id="5c0ca-102">Crear un inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="5c0ca-102">Create a Login</span></span>
  <span data-ttu-id="5c0ca-103">En este tema se describe cómo crear un inicio de sesión en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c0ca-103">This topic describes how to create a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5c0ca-104">Un inicio de sesión es la identidad de la persona o proceso que se está conectando a una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c0ca-104">A login is the identity of the person or process that is connecting to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="5c0ca-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5c0ca-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5c0ca-107">Fondo</span><span class="sxs-lookup"><span data-stu-id="5c0ca-107">Background</span></span>](#Background)  
  
     [<span data-ttu-id="5c0ca-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5c0ca-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5c0ca-109">**Para crear un inicio de sesión, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-109">**To create a login, using:**</span></span>  
  
     [<span data-ttu-id="5c0ca-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c0ca-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5c0ca-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c0ca-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="5c0ca-112">**Seguimiento:**  [Pasos que se deben realizar después de crear un inicio de sesión](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="5c0ca-112">**Follow Up:**  [Steps to take after you create a login](#FollowUp)</span></span>  
  
##  <a name="background"></a><a name="Background"></a> <span data-ttu-id="5c0ca-113">Información previa</span><span class="sxs-lookup"><span data-stu-id="5c0ca-113">Background</span></span>  
 <span data-ttu-id="5c0ca-114">Un inicio de sesión es una entidad de seguridad o una entidad que puede ser autenticada por un sistema seguro.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-114">A login is a security principal, or an entity that can be authenticated by a secure system.</span></span> <span data-ttu-id="5c0ca-115">Los usuarios necesitan iniciar sesión para conectarse a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c0ca-115">Users need a login to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5c0ca-116">Puede crear un inicio de sesión basado en una entidad de seguridad de Windows (como un usuario de dominio o un grupo de dominio de Windows) o puede crear un inicio de sesión que no lo esté (como un inicio de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="5c0ca-116">You can create a login based on a Windows principal (such as a domain user or a Windows domain group) or you can create a login that is not based on a Windows principal (such as an [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c0ca-117">Para usar la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], el [!INCLUDE[ssDE](../../../includes/ssde-md.md)] debe utilizar la autenticación de modo mixto.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-117">To use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication, the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must use mixed mode authentication.</span></span> <span data-ttu-id="5c0ca-118">Para obtener más información, vea [Elegir un modo de autenticación](../choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="5c0ca-118">For more information, see [Choose an Authentication Mode](../choose-an-authentication-mode.md).</span></span>  
  
 <span data-ttu-id="5c0ca-119">Como entidad de seguridad, se pueden conceder permisos a los inicios de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-119">As a security principal, permissions can be granted to logins.</span></span> <span data-ttu-id="5c0ca-120">El ámbito de un inicio de sesión es todo el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c0ca-120">The scope of a login is the whole [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span> <span data-ttu-id="5c0ca-121">Para establecer conexión con una base de datos concreta de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], un inicio de sesión debe estar asignado a un usuario de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-121">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="5c0ca-122">Los permisos dentro de la base de datos se conceden y deniegan al usuario de la base de datos, no al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-122">Permissions inside the database are granted and denied to the database user, not the login.</span></span> <span data-ttu-id="5c0ca-123">Los permisos que tienen como ámbito la instancia completa de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (por ejemplo, el permiso `CREATE ENDPOINT`) se pueden conceder a un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-123">Permissions that have the scope of the whole instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (for example, the `CREATE ENDPOINT` permission) can be granted to a login.</span></span>  
  
##  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5c0ca-124">Seguridad</span><span class="sxs-lookup"><span data-stu-id="5c0ca-124">Security</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="5c0ca-125">Permisos</span><span class="sxs-lookup"><span data-stu-id="5c0ca-125">Permissions</span></span>  
 <span data-ttu-id="5c0ca-126">Requiere el permiso `ALTER ANY LOGIN` o `ALTER LOGIN` del servidor.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-126">Requires `ALTER ANY LOGIN` or `ALTER LOGIN` permission on the server.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5c0ca-127">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c0ca-127">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-sql-server-login"></a><span data-ttu-id="5c0ca-128">Para crear un inicio de sesión de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c0ca-128">To create a SQL Server login</span></span>  
  
1.  <span data-ttu-id="5c0ca-129">En el Explorador de objetos, expanda la carpeta de la instancia de servidor en la que desea crear el nuevo inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-129">In Object Explorer, expand the folder of the server instance in which you want to create the new login.</span></span>  
  
2.  <span data-ttu-id="5c0ca-130">Haga clic con el botón derecho en la carpeta **Seguridad**, seleccione **Nuevo** y, después, haga clic en **Inicio de sesión...** .</span><span class="sxs-lookup"><span data-stu-id="5c0ca-130">Right-click the **Security** folder, point to **New**, and select **Login...**.</span></span>  
  
3.  <span data-ttu-id="5c0ca-131">En el cuadro de diálogo **Inicio de sesión - Nuevo**, en la página **General**, escriba el nombre de un usuario en el cuadro **Nombre de inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-131">In the **Login - New** dialog box, on the **General** page, enter the name of a user in the **Login name** box.</span></span> <span data-ttu-id="5c0ca-132">Como alternativa, haga clic en **Buscar...** para abrir el cuadro de diálogo **Seleccionar usuarios o grupos**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-132">Alternately, click **Search...** to open the **Select User or Group** dialog box.</span></span>  
  
     <span data-ttu-id="5c0ca-133">Si hace clic en **Buscar...** :</span><span class="sxs-lookup"><span data-stu-id="5c0ca-133">If you click **Search...**:</span></span>  
  
    1.  <span data-ttu-id="5c0ca-134">En **Seleccionar este tipo de objeto**, haga clic en **Tipos de objeto...** para abrir el cuadro de diálogo **Tipos de objetos** y seleccione alguna o todas las opciones siguientes: **Entidades de seguridad integradas**, **Grupos** y **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-134">Under **Select this object type**, click **Object Types...** to open the **Object Types** dialog box and select any or all of the following: **Built-in security principals**, **Groups**, and **Users**.</span></span> <span data-ttu-id="5c0ca-135">Las opciones**Entidades de seguridad integradas** y **Usuarios** están seleccionadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-135">**Built-in security principals** and **Users** are selected by default.</span></span> <span data-ttu-id="5c0ca-136">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-136">When finished, click **OK**.</span></span>  
  
    2.  <span data-ttu-id="5c0ca-137">En **Desde esta ubicación**, haga clic en **Ubicaciones...** para abrir el cuadro de diálogo **Ubicaciones** y seleccione una de las ubicaciones de servidor disponibles.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-137">Under **From this location**, click **Locations...** to open the **Locations** dialog box and select one of the available server locations.</span></span> <span data-ttu-id="5c0ca-138">Cuando termine, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-138">When finished, click **OK**.</span></span>  
  
    3.  <span data-ttu-id="5c0ca-139">En **Escribir los nombres de objeto para seleccionar (ejemplos)** , escriba el usuario o el nombre de grupo que quiere buscar.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-139">Under **Enter the object name to select (examples)**, enter the user or group name that you want to find.</span></span> <span data-ttu-id="5c0ca-140">Para obtener más información, vea [Seleccionar usuarios, equipos o grupos (cuadro de diálogo)](https://technet.microsoft.com/library/cc771712.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c0ca-140">For more information, see [Select Users, Computers, or Groups Dialog Box](https://technet.microsoft.com/library/cc771712.aspx).</span></span>  
  
    4.  <span data-ttu-id="5c0ca-141">Haga clic en **Avanzadas...** para obtener más opciones avanzadas de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-141">Click **Advanced...** for more advanced search options.</span></span> <span data-ttu-id="5c0ca-142">Para obtener más información, vea [Seleccionar usuarios, equipos o grupos (cuadro de diálogo): página Opciones avanzadas](https://technet.microsoft.com/library/cc733110.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c0ca-142">For more information, see [Select Users, Computers, or Groups Dialog Box - Advanced Page](https://technet.microsoft.com/library/cc733110.aspx).</span></span>  
  
    5.  <span data-ttu-id="5c0ca-143">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-143">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="5c0ca-144">Para crear un inicio de sesión basado en una entidad de seguridad de Windows, seleccione **Autenticación de Windows**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-144">To create a login based on a Windows principal, select **Windows authentication**.</span></span> <span data-ttu-id="5c0ca-145">Esta es la selección predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-145">This is the default selection.</span></span>  
  
5.  <span data-ttu-id="5c0ca-146">Para crear un inicio de sesión que se guarde en una base de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , seleccione **Autenticación de SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-146">To create a login that is saved on a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, select **SQL Server authentication**.</span></span>  
  
    1.  <span data-ttu-id="5c0ca-147">En el campo **Contraseña** , escriba una contraseña para el usuario nuevo.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-147">In the **Password** box, enter a password for the new user.</span></span> <span data-ttu-id="5c0ca-148">Vuelva a escribir esa contraseña en el cuadro **Confirmar contraseña** .</span><span class="sxs-lookup"><span data-stu-id="5c0ca-148">Enter that password again into the **Confirm Password** box.</span></span>  
  
    2.  <span data-ttu-id="5c0ca-149">Al cambiar una contraseña existente, seleccione **Especificar contraseña anterior**y escriba la contraseña anterior en el cuadro **Contraseña anterior** .</span><span class="sxs-lookup"><span data-stu-id="5c0ca-149">When changing an existing password, select **Specify old password**, and then type the old password in the **Old password** box.</span></span>  
  
    3.  <span data-ttu-id="5c0ca-150">Para aplicar las opciones de la directiva de contraseñas a efectos de complejidad y exigencia, seleccione **Exigir directivas de contraseñas**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-150">To enforce password policy options for complexity and enforcement, select **Enforce password policy**.</span></span> <span data-ttu-id="5c0ca-151">Para obtener más información, vea [Password Policy](../password-policy.md).</span><span class="sxs-lookup"><span data-stu-id="5c0ca-151">For more information, see [Password Policy](../password-policy.md).</span></span> <span data-ttu-id="5c0ca-152">Esta es una opción predeterminada cuando se selecciona **Autenticación de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="5c0ca-152">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    4.  <span data-ttu-id="5c0ca-153">Para aplicar las opciones de la directiva de contraseñas a efectos de expiración, seleccione **Exigir expiración de contraseña**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-153">To enforce password policy options for expiration, select **Enforce password expiration**.</span></span> <span data-ttu-id="5c0ca-154">Debe seleccionar la opción**Exigir directivas de contraseñas** para habilitar esta casilla.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-154">**Enforce password policy** must be selected to enable this checkbox.</span></span> <span data-ttu-id="5c0ca-155">Esta es una opción predeterminada cuando se selecciona **Autenticación de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="5c0ca-155">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
    5.  <span data-ttu-id="5c0ca-156">Para obligar al usuario a crear una nueva contraseña después de utilizarse el inicio de sesión por primera vez, seleccione **El usuario debe cambiar la contraseña en el siguiente inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-156">To force the user to create a new password after the first time the login is used, select **User must change password at next login**.</span></span> <span data-ttu-id="5c0ca-157">Debe seleccionar la opción**Exigir expiración de contraseña** para habilitar esta casilla.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-157">**Enforce password expiration** must be selected to enable this checkbox.</span></span> <span data-ttu-id="5c0ca-158">Esta es una opción predeterminada cuando se selecciona **Autenticación de SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="5c0ca-158">This is a default option when **SQL Server authentication** is selected.</span></span>  
  
6.  <span data-ttu-id="5c0ca-159">Para asociar el inicio de sesión a un certificado de seguridad independiente, seleccione **Asignado a certificado** y seleccione el nombre de un certificado existente de la lista.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-159">To associate the login with a stand-alone security certificate, select **Mapped to certificate** and then select the name of an existing certificate from the list.</span></span>  
  
7.  <span data-ttu-id="5c0ca-160">Para asociar el inicio de sesión a una clave asimétrica independiente, seleccione **Asignado a clave asimétrica** y seleccione el nombre de una clave existente de la lista.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-160">To associate the login with a stand-alone asymmetric key, select **Mapped to asymmetric key** to, and then select the name of an existing key from the list.</span></span>  
  
8.  <span data-ttu-id="5c0ca-161">Para asociar el inicio de sesión a una credencial de seguridad, active la casilla de **Asignado a credencial** y seleccione una credencial existente de la lista o haga clic en **Agregar** para crear una nueva credencial.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-161">To associate the login with a security credential, select the **Mapped to Credential** check box, and then either select an existing credential from the list or click **Add** to create a new credential.</span></span> <span data-ttu-id="5c0ca-162">Para quitar una asignación a una credencial de seguridad del inicio de sesión, seleccione la credencial en **Credenciales asignadas** y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-162">To remove a mapping to a security credential from the login, select the credential from **Mapped Credentials** and click **Remove**.</span></span> <span data-ttu-id="5c0ca-163">Para obtener más información sobre las credenciales en general, vea [Credenciales &#40;motor de base de datos&#41;](credentials-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="5c0ca-163">For more information about credentials in general, see [Credentials &#40;Database Engine&#41;](credentials-database-engine.md).</span></span>  
  
9. <span data-ttu-id="5c0ca-164">En la lista **Base de datos predeterminada** , seleccione una base de datos predeterminada para el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-164">From the **Default database** list, select a default database for the login.</span></span> <span data-ttu-id="5c0ca-165">**Maestra** es el valor predeterminado para esta opción.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-165">**Master** is the default for this option.</span></span>  
  
10. <span data-ttu-id="5c0ca-166">En la lista **Idioma predeterminado** , seleccione un idioma predeterminado para el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-166">From the **Default language** list, select a default language for the login.</span></span>  
  
11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="5c0ca-167">Opciones adicionales</span><span class="sxs-lookup"><span data-stu-id="5c0ca-167">Additional Options</span></span>  
 <span data-ttu-id="5c0ca-168">En el cuadro de diálogo **Inicio de sesión - Nuevo** también se ofrecen opciones en cuatro páginas adicionales: **Roles de servidor**, **Asignación de usuarios**, **Elementos protegibles** y **Estado**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-168">The **Login - New** dialog box also offers options on four additional pages: **Server Roles**, **User Mapping**, **Securables**, and **Status**.</span></span>  
  
### <a name="server-roles"></a><span data-ttu-id="5c0ca-169">Roles del servidor</span><span class="sxs-lookup"><span data-stu-id="5c0ca-169">Server Roles</span></span>  
 <span data-ttu-id="5c0ca-170">La página **Roles de servidor** enumera todos los roles posibles que se pueden asignar al nuevo inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-170">The **Server Roles** page lists all possible roles that can be assigned to the new login.</span></span> <span data-ttu-id="5c0ca-171">Están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="5c0ca-171">The following options are available:</span></span>  
  
 <span data-ttu-id="5c0ca-172">Casilla**bulkadmin**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-172">**bulkadmin** check box</span></span>  
 <span data-ttu-id="5c0ca-173">Los miembros del rol fijo de servidor **bulkadmin** pueden ejecutar la instrucción BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-173">Members of the **bulkadmin** fixed server role can run the BULK INSERT statement.</span></span>  
  
 <span data-ttu-id="5c0ca-174">Casilla**dbcreator**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-174">**dbcreator** check box</span></span>  
 <span data-ttu-id="5c0ca-175">Los miembros del rol fijo de servidor **dbcreator** pueden crear, modificar, quitar y restaurar cualquier base de datos.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-175">Members of the **dbcreator** fixed server role can create, alter, drop, and restore any database.</span></span>  
  
 <span data-ttu-id="5c0ca-176">Casilla**diskadmin**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-176">**diskadmin** check box</span></span>  
 <span data-ttu-id="5c0ca-177">Los miembros del rol fijo de servidor **diskadmin** pueden administrar archivos de disco.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-177">Members of the **diskadmin** fixed server role can manage disk files.</span></span>  
  
 <span data-ttu-id="5c0ca-178">Casilla**processadmin**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-178">**processadmin** check box</span></span>  
 <span data-ttu-id="5c0ca-179">Los miembros del rol fijo de servidor **processadmin** pueden finalizar procesos mediante la ejecución de una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c0ca-179">Members of the **processadmin** fixed server role can terminate processes running in an instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="5c0ca-180">Casilla**public**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-180">**public** check box</span></span>  
 <span data-ttu-id="5c0ca-181">Todos los usuarios, grupos y roles de SQL Server pertenecen al rol fijo de servidor **public** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-181">All SQL Server users, groups, and roles belong to the **public** fixed server role by default.</span></span>  
  
 <span data-ttu-id="5c0ca-182">Casilla**securityadmin**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-182">**securityadmin** check box</span></span>  
 <span data-ttu-id="5c0ca-183">Los miembros del rol fijo de servidor **securityadmin** administran los inicios de sesión y sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-183">Members of the **securityadmin** fixed server role manage logins and their properties.</span></span> <span data-ttu-id="5c0ca-184">Administran los permisos de servidor GRANT, DENY y REVOKE.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-184">They can GRANT, DENY, and REVOKE server-level permissions.</span></span> <span data-ttu-id="5c0ca-185">También administran los permisos de base de datos GRANT, DENY y REVOKE.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-185">They can also GRANT, DENY, and REVOKE database-level permissions.</span></span> <span data-ttu-id="5c0ca-186">Asimismo, pueden restablecer contraseñas para inicios de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c0ca-186">Additionally, they can reset passwords for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins.</span></span>  
  
 <span data-ttu-id="5c0ca-187">Casilla**serveradmin**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-187">**serveradmin** check box</span></span>  
 <span data-ttu-id="5c0ca-188">Los miembros del rol fijo de servidor **serveradmin** pueden cambiar opciones de configuración en el servidor y cerrar el servidor.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-188">Members of the **serveradmin** fixed server role can change server-wide configuration options and shut down the server.</span></span>  
  
 <span data-ttu-id="5c0ca-189">Casilla**setupadmin**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-189">**setupadmin** check box</span></span>  
 <span data-ttu-id="5c0ca-190">Los miembros del rol fijo de servidor **setupadmin** pueden agregar y quitar servidores vinculados, y ejecutar algunos procedimientos almacenados del sistema.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-190">Members of the **setupadmin** fixed server role can add and remove linked servers, and they can execute some system stored procedures.</span></span>  
  
 <span data-ttu-id="5c0ca-191">Casilla**sysadmin**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-191">**sysadmin** check box</span></span>  
 <span data-ttu-id="5c0ca-192">Los miembros del rol fijo de servidor **sysadmin** pueden realizar cualquier actividad en el [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c0ca-192">Members of the **sysadmin** fixed server role can perform any activity in the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
### <a name="user-mapping"></a><span data-ttu-id="5c0ca-193">Asignación de usuarios</span><span class="sxs-lookup"><span data-stu-id="5c0ca-193">User Mapping</span></span>  
 <span data-ttu-id="5c0ca-194">La página **Asignación de usuarios** enumera todas las bases de datos posibles y las pertenencias al rol de base de datos en esas bases de datos que se pueden aplicar al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-194">The **User Mapping** page lists all possible databases and the database role memberships on those databases that can be applied to the login.</span></span> <span data-ttu-id="5c0ca-195">Las bases de datos seleccionadas determinan las pertenencias a roles disponibles para el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-195">The databases selected determine the role memberships that are available for the login.</span></span> <span data-ttu-id="5c0ca-196">En esta página están disponibles las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c0ca-196">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="5c0ca-197">**Usuarios asignados a este inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-197">**Users mapped to this login**</span></span>  
 <span data-ttu-id="5c0ca-198">Selecciona las bases de datos a las que se puede obtener acceso con este inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-198">Select the databases that this login can access.</span></span> <span data-ttu-id="5c0ca-199">Cuando se seleccione una base de datos, sus roles de bases de datos válidos se mostrarán en el panel **Miembros del rol de base de datos para:** _nombre_baseDeDatos_ .</span><span class="sxs-lookup"><span data-stu-id="5c0ca-199">When you select a database, its valid database roles are displayed in the **Database role membership for:** _database_name_ pane.</span></span>  
  
 <span data-ttu-id="5c0ca-200">**Map**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-200">**Map**</span></span>  
 <span data-ttu-id="5c0ca-201">Permite que el inicio de sesión obtenga acceso a las bases de datos que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-201">Allow the login to access the databases listed below.</span></span>  
  
 <span data-ttu-id="5c0ca-202">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-202">**Database**</span></span>  
 <span data-ttu-id="5c0ca-203">Muestra las bases de datos disponibles en el servidor.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-203">Lists the databases available on the server.</span></span>  
  
 <span data-ttu-id="5c0ca-204">**User**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-204">**User**</span></span>  
 <span data-ttu-id="5c0ca-205">Especifica el usuario de base de datos que se va a asignar al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-205">Specify a database user to map to the login.</span></span> <span data-ttu-id="5c0ca-206">De forma predeterminada, el nombre del usuario de base de datos coincide con el inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-206">By default, the database user has the same name as the login.</span></span>  
  
 <span data-ttu-id="5c0ca-207">**Esquema predeterminado**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-207">**Default Schema**</span></span>  
 <span data-ttu-id="5c0ca-208">Especifica el esquema predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-208">Specifies the default schema of the user.</span></span> <span data-ttu-id="5c0ca-209">Cuando se crea un usuario por primera vez, el esquema predeterminado es **dbo**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-209">When a user is first created, its default schema is **dbo**.</span></span> <span data-ttu-id="5c0ca-210">Es posible especificar un esquema predeterminado que aún no existe.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-210">It is possible to specify a default schema that does not yet exist.</span></span> <span data-ttu-id="5c0ca-211">No puede especificar un esquema predeterminado para un usuario asignado a un grupo, un certificado o una clave asimétrica de Windows.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-211">You cannot specify a default schema for a user that is mapped to a Windows group, a certificate, or an asymmetric key.</span></span>  
  
 <span data-ttu-id="5c0ca-212">**Cuenta de invitado habilitada para:** _nombre_baseDeDatos_</span><span class="sxs-lookup"><span data-stu-id="5c0ca-212">**Guest account enabled for:**  _database_name_</span></span>  
 <span data-ttu-id="5c0ca-213">Atributo de solo lectura que indica si la cuenta de invitado está habilitada en la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-213">Read-only attribute indicating whether the Guest account is enabled on the selected database.</span></span> <span data-ttu-id="5c0ca-214">Utilice la página **Estado** del cuadro de diálogo **Propiedades de inicio de sesión** de la cuenta de invitado para habilitarla o deshabilitarla.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-214">Use the **Status** page of the **Login Properties** dialog box of the Guest account to enable or disable the Guest account.</span></span>  
  
 <span data-ttu-id="5c0ca-215">**Miembros del rol de base de datos para:** _nombre_baseDeDatos_</span><span class="sxs-lookup"><span data-stu-id="5c0ca-215">**Database role membership for:**  _database_name_</span></span>  
 <span data-ttu-id="5c0ca-216">Selecciona los roles para el usuario en la base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-216">Select the roles for the user in the specified database.</span></span> <span data-ttu-id="5c0ca-217">Todos los usuarios son miembros del rol **public** de todas las bases de datos, y no pueden eliminarse.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-217">All users are members of the **public** role in every database and cannot be removed.</span></span> <span data-ttu-id="5c0ca-218">Para obtener más información sobre los roles de base de datos, vea [Roles de nivel de base de datos](database-level-roles.md).</span><span class="sxs-lookup"><span data-stu-id="5c0ca-218">For more information about database roles, see [Database-Level Roles](database-level-roles.md).</span></span>  
  
### <a name="securables"></a><span data-ttu-id="5c0ca-219">Elementos protegibles</span><span class="sxs-lookup"><span data-stu-id="5c0ca-219">Securables</span></span>  
 <span data-ttu-id="5c0ca-220">La página **Elementos protegibles** muestra todos los elementos protegibles posibles y los permisos en esos elementos protegibles que se pueden conceder al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-220">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span> <span data-ttu-id="5c0ca-221">En esta página están disponibles las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c0ca-221">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="5c0ca-222">**Cuadrícula superior**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-222">**Upper Grid**</span></span>  
 <span data-ttu-id="5c0ca-223">Contiene uno o más elementos para los que se pueden establecer permisos.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-223">Contains one or more items for which permissions can be set.</span></span> <span data-ttu-id="5c0ca-224">Las columnas mostradas en la cuadrícula superior varían dependiendo de la entidad de seguridad o el elemento protegible.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-224">The columns that are displayed in the upper grid vary depending on the principal or securable.</span></span>  
  
 <span data-ttu-id="5c0ca-225">Para agregar elementos a la cuadrícula superior:</span><span class="sxs-lookup"><span data-stu-id="5c0ca-225">To add items to the upper grid:</span></span>  
  
1.  <span data-ttu-id="5c0ca-226">Haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-226">Click **Search**.</span></span>  
  
2.  <span data-ttu-id="5c0ca-227">En el cuadro de diálogo **agregar objetos** , seleccione una de las opciones siguientes: **objetos específicos...**, **todos los objetos de los tipos...** o **el servidor**_SERVER_NAME_.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-227">In the **Add Objects** dialog box, select one of the following options: **Specific objects...**, **All objects of the types...**, or **The server**_server_name_.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="5c0ca-228">Al seleccionar **el servidor**_SERVER_NAME_ se rellena automáticamente la cuadrícula superior con todos los objetos protegibles de los servidores.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-228">Selecting **The server**_server_name_ automatically fills the upper grid with all of that servers' securable objects.</span></span>  
  
3.  <span data-ttu-id="5c0ca-229">Si selecciona **Objetos específicos...** :</span><span class="sxs-lookup"><span data-stu-id="5c0ca-229">If you select **Specific objects...**:</span></span>  
  
    1.  <span data-ttu-id="5c0ca-230">En el cuadro de diálogo **Seleccionar objetos**, en **Seleccionar estos tipos de objeto**, haga clic en **Tipos de objeto...** .</span><span class="sxs-lookup"><span data-stu-id="5c0ca-230">In the **Select Objects** dialog box, under **Select these object types**, click **Object Types...**.</span></span>  
  
    2.  <span data-ttu-id="5c0ca-231">En el cuadro de diálogo **Seleccionar tipos de objeto**, seleccione alguno o todos los tipos de objeto siguientes: **Puntos de conexión**, **Inicios de sesión**, **Servidores**, **Grupos de disponibilidad** y **Roles de servidor**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-231">In the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    3.  <span data-ttu-id="5c0ca-232">En **Escribir los nombres de objeto para seleccionar (ejemplos)** , haga clic en **Examinar...** .</span><span class="sxs-lookup"><span data-stu-id="5c0ca-232">Under **Enter the object names to select (examples)**, click **Browse...**.</span></span>  
  
    4.  <span data-ttu-id="5c0ca-233">En el cuadro de diálogo **Buscar objetos** , seleccione cualquiera de los objetos disponibles del tipo que seleccionó en el cuadro de diálogo **Seleccionar tipos de objeto** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-233">In the **Browse for Objects** dialog box, select any of the available objects of the type that you selected in the **Select Object Types** dialog box, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="5c0ca-234">En el cuadro de diálogo **Seleccionar objetos** , haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-234">In the **Select Objects** dialog box, click **OK**.</span></span>  
  
4.  <span data-ttu-id="5c0ca-235">Si selecciona **Todos los objetos de los tipos...** , en el cuadro de diálogo **Seleccionar tipos de objeto**, seleccione alguno o todos los tipos de objeto siguientes: **Puntos de conexión**, **Inicios de sesión**, **Servidores**, **Grupos de disponibilidad** y **Roles de servidor**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-235">If you select **All objects of the types...**, in the **Select Object Types** dialog box, select any or all of the following object types: **Endpoints**, **Logins**, **Servers**, **Availability Groups**, and **Server roles**.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
 <span data-ttu-id="5c0ca-236">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-236">**Name**</span></span>  
 <span data-ttu-id="5c0ca-237">El nombre de cada entidad de seguridad o elemento protegible que se agrega a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-237">The name of each principal or securable that is added to the grid.</span></span>  
  
 <span data-ttu-id="5c0ca-238">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-238">**Type**</span></span>  
 <span data-ttu-id="5c0ca-239">Describe el tipo de cada elemento.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-239">Describes the type of each item.</span></span>  
  
 <span data-ttu-id="5c0ca-240">**Pestaña Explícito**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-240">**Explicit Tab**</span></span>  
 <span data-ttu-id="5c0ca-241">Enumere los posibles permisos del elemento protegible seleccionados en la cuadrícula superior.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-241">Lists the possible permissions for the securable that are selected in the upper grid.</span></span> <span data-ttu-id="5c0ca-242">No todas las opciones están disponibles para todos los permisos explícitos.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-242">Not all options are available for all explicit permissions.</span></span>  
  
 <span data-ttu-id="5c0ca-243">**Permisos**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-243">**Permissions**</span></span>  
 <span data-ttu-id="5c0ca-244">Nombre del permiso.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-244">The name of the permission.</span></span>  
  
 <span data-ttu-id="5c0ca-245">**Otorgante de permisos**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-245">**Grantor**</span></span>  
 <span data-ttu-id="5c0ca-246">La entidad de seguridad que concedió el permiso.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-246">The principal that granted the permission.</span></span>  
  
 <span data-ttu-id="5c0ca-247">**Conceder**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-247">**Grant**</span></span>  
 <span data-ttu-id="5c0ca-248">Active esta casilla para conceder el permiso al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-248">Select to grant this permission to the login.</span></span> <span data-ttu-id="5c0ca-249">Desactívela para revocar el permiso.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-249">Clear to revoke this permission.</span></span>  
  
 <span data-ttu-id="5c0ca-250">**WITH GRANT**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-250">**With Grant**</span></span>  
 <span data-ttu-id="5c0ca-251">Refleja el estado de la opción WITH GRANT para el permiso indicado.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-251">Reflects the state of the WITH GRANT option for the listed permission.</span></span> <span data-ttu-id="5c0ca-252">Este cuadro es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-252">This box is read-only.</span></span> <span data-ttu-id="5c0ca-253">Para aplicar este permiso, use la instrucción [GRANT](/sql/t-sql/statements/grant-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="5c0ca-253">To apply this permission, use the [GRANT](/sql/t-sql/statements/grant-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="5c0ca-254">**Deny**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-254">**Deny**</span></span>  
 <span data-ttu-id="5c0ca-255">Active esta casilla para denegar el permiso al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-255">Select to deny this permission to the login.</span></span> <span data-ttu-id="5c0ca-256">Desactívela para revocar el permiso.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-256">Clear to revoke this permission.</span></span>  
  
### <a name="status"></a><span data-ttu-id="5c0ca-257">Estado</span><span class="sxs-lookup"><span data-stu-id="5c0ca-257">Status</span></span>  
 <span data-ttu-id="5c0ca-258">La página **Estado** enumera algunas de las opciones de autenticación y autorización que se pueden configurar en el inicio de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-258">The **Status** page lists some of the authentication and authorization options that can be configured on the selected [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="5c0ca-259">En esta página están disponibles las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c0ca-259">The following options are available on this page:</span></span>  
  
 <span data-ttu-id="5c0ca-260">**Permiso para conectarse al motor de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-260">**Permission to connect to database engine**</span></span>  
 <span data-ttu-id="5c0ca-261">Cuando trabaje con esta configuración, debe pensar en el inicio de sesión seleccionado como una entidad de seguridad a la que se le puede otorgar o denegar un permiso para un elemento protegible.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-261">When you work with this setting, you should think of the selected login as a principal that can be granted or denied permission on a securable.</span></span>  
  
 <span data-ttu-id="5c0ca-262">Seleccione **Conceder** para conceder el permiso CONNECT SQL al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-262">Select **Grant** to grant CONNECT SQL permission to the login.</span></span> <span data-ttu-id="5c0ca-263">Seleccione **Denegar** para denegar el permiso CONNECT SQL al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-263">Select **Deny** to deny CONNECT SQL to the login.</span></span>  
  
 <span data-ttu-id="5c0ca-264">**Inicio de sesión**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-264">**Login**</span></span>  
 <span data-ttu-id="5c0ca-265">Cuando trabaje con esta configuración, debe pensar en el inicio de sesión seleccionado como un registro de una tabla.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-265">When you work with this setting, you should think of the selected login as a record in a table.</span></span> <span data-ttu-id="5c0ca-266">Los cambios que se realicen en los valores que se muestran aquí se aplicarán al registro.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-266">Changes to the values listed here will be applied to the record.</span></span>  
  
 <span data-ttu-id="5c0ca-267">Un inicio de sesión que se ha deshabilitado sigue existiendo en el registro.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-267">A login that has been disabled continues to exist as a record.</span></span> <span data-ttu-id="5c0ca-268">Pero si intenta conectarse a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], el inicio de sesión no se autenticará.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-268">But if it tries to connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the login will not be authenticated.</span></span>  
  
 <span data-ttu-id="5c0ca-269">Seleccione esta opción para habilitar o deshabilitar este inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-269">Select this option to enable or disable this login.</span></span> <span data-ttu-id="5c0ca-270">Esta opción utiliza la instrucción ALTER LOGIN con las opciones ENABLE o DISABLE.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-270">This option uses the ALTER LOGIN statement with the either ENABLE or DISABLE option.</span></span>  
  
 <span data-ttu-id="5c0ca-271">**Autenticación de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="5c0ca-271">**SQL Server Authentication**</span></span>  
 <span data-ttu-id="5c0ca-272">La casilla **Inicio de sesión bloqueado** solo está disponible si el inicio de sesión se conecta usando la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y si este se ha bloqueado. Este valor es solo de lectura.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-272">The check box **Login is locked out** is only available if the selected login connects using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication and the login has been locked out. This setting is read-only.</span></span> <span data-ttu-id="5c0ca-273">Para desbloquear un inicio de sesión fuera el que se bloquea, ejecute ALTER LOGIN con la opción de UNLOCK.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-273">To unlock a login that is locked out, execute ALTER LOGIN with the UNLOCK option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5c0ca-274">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5c0ca-274">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-login-using-windows-authentication"></a><span data-ttu-id="5c0ca-275">Para crear un inicio de sesión utilizando la autenticación de Windows</span><span class="sxs-lookup"><span data-stu-id="5c0ca-275">To create a login using Windows Authentication</span></span>  
  
1.  <span data-ttu-id="5c0ca-276">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c0ca-276">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5c0ca-277">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-277">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5c0ca-278">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-278">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Create a login for SQL Server by specifying a server name and a Windows domain account name.  
  
    CREATE LOGIN [<domainName>\<loginName>] FROM WINDOWS;  
    GO  
  
    ```  
  
#### <a name="to-create-a-login-using-sql-server-authentication"></a><span data-ttu-id="5c0ca-279">Para crear un inicio de sesión utilizando la autenticación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="5c0ca-279">To create a login using SQL Server Authentication</span></span>  
  
1.  <span data-ttu-id="5c0ca-280">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c0ca-280">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5c0ca-281">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-281">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5c0ca-282">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-282">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the user "shcooper" for SQL Server using the security credential "RestrictedFaculty"   
    -- The user login starts with the password "Baz1nga," but that password must be changed after the first login.  
  
    CREATE LOGIN shcooper   
       WITH PASSWORD = 'Baz1nga' MUST_CHANGE,  
       CREDENTIAL = RestrictedFaculty;  
    GO  
  
    ```  
  
 <span data-ttu-id="5c0ca-283">Para obtener más información, vea [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5c0ca-283">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
##  <a name="follow-up-steps-to-take-after-you-create-a-login"></a><a name="FollowUp"></a> <span data-ttu-id="5c0ca-284">Seguimiento: Pasos que se deben realizar después de crear un inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="5c0ca-284">Follow Up: Steps to take after you create a login</span></span>  
 <span data-ttu-id="5c0ca-285">Después de crear un inicio de sesión, este puede conectarse a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], pero no necesariamente tiene permisos suficientes para realizar ningún trabajo útil.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-285">After creating a login, the login can connect to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], but does not necessarily have sufficient permission to perform any useful work.</span></span> <span data-ttu-id="5c0ca-286">En la lista siguiente se proporcionan vínculos a las acciones de inicio de sesión comunes.</span><span class="sxs-lookup"><span data-stu-id="5c0ca-286">The following list provides links to common login actions.</span></span>  
  
-   <span data-ttu-id="5c0ca-287">Para combinar el inicio de sesión con un rol, vea [Combinar un rol](join-a-role.md).</span><span class="sxs-lookup"><span data-stu-id="5c0ca-287">To have the login join a role, see [Join a Role](join-a-role.md).</span></span>  
  
-   <span data-ttu-id="5c0ca-288">Para autorizar a un inicio de sesión para que use una base de datos, vea [Crear un usuario de base de datos](../authentication-access/create-a-database-user.md).</span><span class="sxs-lookup"><span data-stu-id="5c0ca-288">To authorize a login to use a database, see [Create a Database User](../authentication-access/create-a-database-user.md).</span></span>  
  
-   <span data-ttu-id="5c0ca-289">Para conceder un permiso a un inicio de sesión, vea [Conceder un permiso a una entidad de seguridad](grant-a-permission-to-a-principal.md).</span><span class="sxs-lookup"><span data-stu-id="5c0ca-289">To grant a permission to a login, see [Grant a Permission to a Principal](grant-a-permission-to-a-principal.md).</span></span>  
  
  
