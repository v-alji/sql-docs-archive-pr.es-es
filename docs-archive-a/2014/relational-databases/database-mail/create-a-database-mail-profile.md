---
title: Creación de un perfil de correo electrónico de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], public profiles
- profiles [SQL Server], Database Mail
- public profiles [Database Mail]
ms.assetid: 58ae749d-6ada-4f9c-bf00-de7c7a992a2d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0453d495c90c1e599bfc7777b4899f30e6659c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671095"
---
# <a name="create-a-database-mail-profile"></a><span data-ttu-id="75883-102">Crear un perfil de correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="75883-102">Create a Database Mail Profile</span></span>
  <span data-ttu-id="75883-103">Para crear perfiles públicos y privados de Correo electrónico de base de datos, use el **Asistente para configuración de Correo electrónico de base de datos** o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75883-103">Use either the **Database Mail Configuration Wizard** or [!INCLUDE[tsql](../../includes/tsql-md.md)] to create Database Mail public and private profiles.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="75883-104">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="75883-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="75883-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="75883-105">Prerequisites</span></span>  
 <span data-ttu-id="75883-106">Cree una o varias cuentas de correo de base de datos para el perfil.</span><span class="sxs-lookup"><span data-stu-id="75883-106">Create one or more Database Mail accounts for the profile.</span></span> <span data-ttu-id="75883-107">Para obtener más información sobre la creación de cuentas de Correo electrónico de base de datos, vea [Crear una nueva cuenta de Correo electrónico de base de datos](create-a-database-mail-account.md).</span><span class="sxs-lookup"><span data-stu-id="75883-107">For more information about creating Database Mail accounts, see [Create a Database Mail Account](create-a-database-mail-account.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="75883-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="75883-108">Security</span></span>  
 <span data-ttu-id="75883-109">Los perfiles públicos permiten que cualquier usuario con acceso a la base de datos **msdb** envíe correo electrónico mediante ese perfil.</span><span class="sxs-lookup"><span data-stu-id="75883-109">A public profile allows any user with access to the **msdb** database to send e-mail using that profile.</span></span> <span data-ttu-id="75883-110">Un perfil privado puede ser usado por un usuario o por un rol.</span><span class="sxs-lookup"><span data-stu-id="75883-110">A private profile can be used by a user or by a role.</span></span> <span data-ttu-id="75883-111">Al conceder a los roles derechos de acceso a los perfiles, se crea una arquitectura más fácil de mantener.</span><span class="sxs-lookup"><span data-stu-id="75883-111">Granting roles access to profiles creates a more easily maintained architecture.</span></span> <span data-ttu-id="75883-112">Para enviar correo, debe ser un miembro de la función **DatabaseMailUserRole** en la base de datos **msdb** y tener acceso como mínimo a un perfil de Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="75883-112">To send mail you must be a member of the **DatabaseMailUserRole** in the **msdb** database, and have access to at least one Database Mail profile.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="75883-113">Permisos</span><span class="sxs-lookup"><span data-stu-id="75883-113">Permissions</span></span>  
 <span data-ttu-id="75883-114">El usuario que crea cuentas de perfil y ejecuta procedimientos almacenados debe ser miembro del rol fijo de servidor sysadmin.</span><span class="sxs-lookup"><span data-stu-id="75883-114">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  

  
##  <a name="using-database-mail-configuration-wizard"></a><a name="SSMSProcedure"></a> <span data-ttu-id="75883-115">Usar el asistente para configuración del Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="75883-115">Using Database Mail Configuration Wizard</span></span>  
 <span data-ttu-id="75883-116">**Para crear un perfil de correo electrónico de base de datos**</span><span class="sxs-lookup"><span data-stu-id="75883-116">**To Create a Database Mail profile**</span></span>  
  
-   <span data-ttu-id="75883-117">En el explorador de objetos, conecte a la instancia [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la que quiera configurar el Correo electrónico de base de datos y expanda el árbol del servidor.</span><span class="sxs-lookup"><span data-stu-id="75883-117">In Object Explorer, connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you want to configure Database Mail on, and expand the server tree.</span></span>  
  
-   <span data-ttu-id="75883-118">Expanda el nodo **Administración** .</span><span class="sxs-lookup"><span data-stu-id="75883-118">Expand the **Management** node</span></span>  
  
-   <span data-ttu-id="75883-119">Haga doble clic en el correo electrónico de base de datos para abrir el asistente de configuración del correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="75883-119">Double click Database Mail to open the Database Mail Configuration Wizard.</span></span>  
  
-   <span data-ttu-id="75883-120">En la página **seleccionar tarea de configuración** , seleccione la opción **administrar cuentas y perfiles de correo electrónico de base de datos** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75883-120">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option and click **Next**.</span></span>  
  
-   <span data-ttu-id="75883-121">En la página **Administrar perfiles y cuentas** , seleccione la opción **Crear nuevo perfil** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75883-121">On the **Manage Profiles and Accounts** page, select **Create a new profile** option, and click **Next**.</span></span>  
  
-   <span data-ttu-id="75883-122">En la página **Nuevo perfil**, especifique el nombre de perfil, la descripción y agregue las cuentas que se van a incluir en el perfil, y haga clic **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75883-122">On the **New Profile** page, specify the Profile name, Description and add accounts to be included in the profile, and click **Next**.</span></span>  
  
-   <span data-ttu-id="75883-123">En la página **Finalización del asistente** , revise las acciones que realizará y haga clic en **Finalizar** para completar crear el nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="75883-123">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete creating the new profile.</span></span>  
  
-   <span data-ttu-id="75883-124">**Para configurar un perfil privado de Correo electrónico de base de datos:**</span><span class="sxs-lookup"><span data-stu-id="75883-124">**To configure a Database Mail private profile:**</span></span>  
  
    -   <span data-ttu-id="75883-125">Abra el Asistente para configuración del Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="75883-125">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="75883-126">En la página **Seleccionar tarea de configuración** , seleccione la opción **Administrar cuentas y perfiles de Correo electrónico de base de datos** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75883-126">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="75883-127">En la página **Administrar perfiles y cuentas** , seleccione la opción **Administrar seguridad del perfil** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75883-127">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="75883-128">En la pestaña **Perfiles privados** , active la casilla correspondiente al perfil que desea configurar y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75883-128">In the **Private Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="75883-129">En la página **Finalización del asistente** , revise las acciones que realizará y haga clic en **Finalizar** para completar la configuración del perfil.</span><span class="sxs-lookup"><span data-stu-id="75883-129">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  
-   <span data-ttu-id="75883-130">**Para configurar un perfil público de Correo electrónico de base de datos:**</span><span class="sxs-lookup"><span data-stu-id="75883-130">**To configure a Database Mail public profile:**</span></span>  
  
    -   <span data-ttu-id="75883-131">Abra el Asistente para configuración del Correo electrónico de base de datos.</span><span class="sxs-lookup"><span data-stu-id="75883-131">Open the Database Mail Configuration Wizard.</span></span>  
  
    -   <span data-ttu-id="75883-132">En la página **Seleccionar tarea de configuración** , seleccione la opción **Administrar cuentas y perfiles de Correo electrónico de base de datos** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75883-132">On the **Select Configuration Task** page, select **Manage Database Mail accounts and profiles** option, and click **Next**.</span></span>  
  
    -   <span data-ttu-id="75883-133">En la página **Administrar perfiles y cuentas** , seleccione la opción **Administrar seguridad del perfil** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75883-133">On the **Manage Profiles and Accounts** page, select **Manage profile security** option and click **Next**.</span></span>  
  
    -   <span data-ttu-id="75883-134">En la pestaña **Perfiles públicos** , active la casilla correspondiente al perfil que desea configurar y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="75883-134">In the **Public Profiles** tab, select the check box for the profile you would like to configure and click **Next**.</span></span>  
  
    -   <span data-ttu-id="75883-135">En la página **Finalización del asistente** , revise las acciones que realizará y haga clic en **Finalizar** para completar la configuración del perfil.</span><span class="sxs-lookup"><span data-stu-id="75883-135">On the **Complete the Wizard** page, review the actions to be performed and click **Finish** to complete configuring the profile.</span></span>  
  

  
## <a name="using-transact-sql"></a><span data-ttu-id="75883-136">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="75883-136">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-database-mail-private-profile"></a><a name="PrivateProfile"></a><span data-ttu-id="75883-137">Para crear un perfil privado de Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="75883-137">To Create a Database Mail private profile</span></span>  
  
-   <span data-ttu-id="75883-138">Conéctese a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75883-138">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="75883-139">Para crear un nuevo perfil, ejecute el procedimiento almacenado del sistema [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) como sigue:</span><span class="sxs-lookup"><span data-stu-id="75883-139">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="75883-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="75883-140">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="75883-141">*@profile_name*= '*Nombre del perfil*'</span><span class="sxs-lookup"><span data-stu-id="75883-141">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="75883-142">*@description*= '*Descripción*'</span><span class="sxs-lookup"><span data-stu-id="75883-142">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="75883-143">donde *@profile_name* es el nombre del perfil y *@description* es la descripción del perfil.</span><span class="sxs-lookup"><span data-stu-id="75883-143">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="75883-144">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="75883-144">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="75883-145">Para cada cuenta, ejecute el procedimiento almacenado [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) como sigue:</span><span class="sxs-lookup"><span data-stu-id="75883-145">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="75883-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="75883-146">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="75883-147">*@profile_name*= '*Nombre del perfil*'</span><span class="sxs-lookup"><span data-stu-id="75883-147">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="75883-148">*@account_name*= '*Nombre de la cuenta*'</span><span class="sxs-lookup"><span data-stu-id="75883-148">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="75883-149">*@sequence_number*= '*número de secuencia de la cuenta en el perfil.*</span><span class="sxs-lookup"><span data-stu-id="75883-149">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="75883-150">'</span><span class="sxs-lookup"><span data-stu-id="75883-150">'</span></span>  
  
     <span data-ttu-id="75883-151">donde *@profile_name* es el nombre del perfil y *@account_name* es el nombre de la cuenta que se va a agregar al perfil, *@sequence_number* determina el orden en el que se usan las cuentas en el perfil.</span><span class="sxs-lookup"><span data-stu-id="75883-151">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="75883-152">Para cada rol o usuario de base de datos que vaya a enviar correo mediante este perfil, concédale acceso a dicho perfil.</span><span class="sxs-lookup"><span data-stu-id="75883-152">For each database role or user that will send mail using this profile, grant access to the profile.</span></span> <span data-ttu-id="75883-153">Para ello, ejecute el procedimiento almacenado [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) como sigue:</span><span class="sxs-lookup"><span data-stu-id="75883-153">To do this, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="75883-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="75883-154">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="75883-155">*@profile_name*= '*Nombre del perfil*'</span><span class="sxs-lookup"><span data-stu-id="75883-155">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="75883-156">*@ principal_name* = '*Nombre del usuario o rol de la base de datos*'</span><span class="sxs-lookup"><span data-stu-id="75883-156">*@ principal_name* = '*Name of the database user or role*'</span></span>  
  
     <span data-ttu-id="75883-157">*@is_default*= '*Estado de perfil predeterminado* '</span><span class="sxs-lookup"><span data-stu-id="75883-157">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="75883-158">donde *@profile_name* es el nombre del perfil y *@principal_name* es el nombre del usuario o rol de la base de datos, *@is_default* determina si este perfil es el predeterminado para el usuario o el rol de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="75883-158">where *@profile_name* is the name of the profile, and *@principal_name* is the name of the database user or role, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="75883-159">El siguiente ejemplo crea una cuenta de Correo electrónico de base de datos, crea un perfil privado de Correo de base de datos y, a continuación, agrega la cuenta al perfil y le concede acceso al rol de base de datos **DBMailUsers** en la base de datos **msdb** .</span><span class="sxs-lookup"><span data-stu-id="75883-159">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants access to the profile to the **DBMailUsers** database role in the **msdb** database.</span></span>  
  
```  
-- Create a Database Mail account  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Administrator',  
    @description = 'Mail account for administrative e-mail.',  
    @email_address = 'dba@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @account_name = 'AdventureWorks Administrator',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to the DBMailUsers role  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Administrator Profile',  
    @principal_name = 'ApplicationUser',  
    @is_default = 1 ;  
```  
  
 
  
###  <a name="to-create-a-database-mail-public-profile"></a><a name="PublicProfile"></a><span data-ttu-id="75883-160">Para crear un perfil público de Correo electrónico de base de datos</span><span class="sxs-lookup"><span data-stu-id="75883-160">To Create a Database Mail public profile</span></span>  
  
-   <span data-ttu-id="75883-161">Conéctese a la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75883-161">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="75883-162">Para crear un nuevo perfil, ejecute el procedimiento almacenado del sistema [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) como sigue:</span><span class="sxs-lookup"><span data-stu-id="75883-162">To create a new profile, run the system stored procedure [sysmail_add_profile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="75883-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span><span class="sxs-lookup"><span data-stu-id="75883-163">**EXECUTEmsdb.dbo.sysmail_add_profile_sp**</span></span>  
  
     <span data-ttu-id="75883-164">*@profile_name*= '*Nombre del perfil*'</span><span class="sxs-lookup"><span data-stu-id="75883-164">*@profile_name* = '*Profile Name*'</span></span>  
  
     <span data-ttu-id="75883-165">*@description*= '*Descripción*'</span><span class="sxs-lookup"><span data-stu-id="75883-165">*@description* = '*Desciption*'</span></span>  
  
     <span data-ttu-id="75883-166">donde *@profile_name* es el nombre del perfil y *@description* es la descripción del perfil.</span><span class="sxs-lookup"><span data-stu-id="75883-166">where *@profile_name* is the name of the profile, and *@description* is the description of the profile.</span></span> <span data-ttu-id="75883-167">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="75883-167">This parameter is optional.</span></span>  
  
-   <span data-ttu-id="75883-168">Para cada cuenta, ejecute el procedimiento almacenado [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) como sigue:</span><span class="sxs-lookup"><span data-stu-id="75883-168">For each account, run the stored procedure [sysmail_add_profileaccount_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-profileaccount-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="75883-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span><span class="sxs-lookup"><span data-stu-id="75883-169">**EXECUTEmsdb.dbo.sysmail_add_profileaccount_sp**</span></span>  
  
     <span data-ttu-id="75883-170">*@profile_name*= '*Nombre del perfil*'</span><span class="sxs-lookup"><span data-stu-id="75883-170">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="75883-171">*@account_name*= '*Nombre de la cuenta*'</span><span class="sxs-lookup"><span data-stu-id="75883-171">*@account_name* = '*Name of the account*'</span></span>  
  
     <span data-ttu-id="75883-172">*@sequence_number*= '*número de secuencia de la cuenta en el perfil.*</span><span class="sxs-lookup"><span data-stu-id="75883-172">*@sequence_number* = '*sequence number of the account within the profile.*</span></span> <span data-ttu-id="75883-173">'</span><span class="sxs-lookup"><span data-stu-id="75883-173">'</span></span>  
  
     <span data-ttu-id="75883-174">donde *@profile_name* es el nombre del perfil y *@account_name* es el nombre de la cuenta que se va a agregar al perfil, *@sequence_number* determina el orden en el que se usan las cuentas en el perfil.</span><span class="sxs-lookup"><span data-stu-id="75883-174">where *@profile_name* is the name of the profile, and *@account_name* is the name of the account to add to the profile, *@sequence_number* determines the order in which the accounts are used in the profile.</span></span>  
  
-   <span data-ttu-id="75883-175">Para conceder acceso público, ejecute el procedimiento almacenado [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) como sigue:</span><span class="sxs-lookup"><span data-stu-id="75883-175">To grant public access, run the stored procedure [sysmail_add_principalprofile_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-add-principalprofile-sp-transact-sql) as follows:</span></span>  
  
     <span data-ttu-id="75883-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span><span class="sxs-lookup"><span data-stu-id="75883-176">**EXECUTEmsdb.sysmail_add_principalprofile_sp**</span></span>  
  
     <span data-ttu-id="75883-177">*@profile_name*= '*Nombre del perfil*'</span><span class="sxs-lookup"><span data-stu-id="75883-177">*@profile_name* = '*Name of the profile*'</span></span>  
  
     <span data-ttu-id="75883-178">*@ principal_name* = '**público** o **0**'</span><span class="sxs-lookup"><span data-stu-id="75883-178">*@ principal_name* = '**public** or **0**'</span></span>  
  
     <span data-ttu-id="75883-179">*@is_default*= '*Estado de perfil predeterminado* '</span><span class="sxs-lookup"><span data-stu-id="75883-179">*@is_default* = '*Default Profile status* '</span></span>  
  
     <span data-ttu-id="75883-180">donde *@profile_name* es el nombre del perfil y, *@principal_name* para indicar que se trata de un perfil público, *@is_default* determina si este perfil es el predeterminado para el usuario o el rol de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="75883-180">where *@profile_name* is the name of the profile, and *@principal_name* to indicate this is a public profile, *@is_default* determines the whether this profile is the default for the database user or role.</span></span>  
  
 <span data-ttu-id="75883-181">El ejemplo siguiente se crea una cuenta de Correo electrónico de base de datos, crea un perfil privado de Correo electrónico de base de datos, agrega la cuenta al perfil y concede acceso público al perfil.</span><span class="sxs-lookup"><span data-stu-id="75883-181">The following example creates a Database Mail account, creates a Database Mail private profile, then adds the account to the profile and grants public access to the profile.</span></span>  
  
```  
-- Create a Database Mail account  
  
EXECUTE msdb.dbo.sysmail_add_account_sp  
    @account_name = 'AdventureWorks Public Account',  
    @description = 'Mail account for use by all database users.',  
    @email_address = 'db_users@Adventure-Works.com',  
    @replyto_address = 'danw@Adventure-Works.com',  
    @display_name = 'AdventureWorks Automated Mailer',  
    @mailserver_name = 'smtp.Adventure-Works.com' ;  
  
-- Create a Database Mail profile  
  
EXECUTE msdb.dbo.sysmail_add_profile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @description = 'Profile used for administrative mail.' ;  
  
-- Add the account to the profile  
  
EXECUTE msdb.dbo.sysmail_add_profileaccount_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @account_name = 'AdventureWorks Public Account',  
    @sequence_number =1 ;  
  
-- Grant access to the profile to all users in the msdb database  
  
EXECUTE msdb.dbo.sysmail_add_principalprofile_sp  
    @profile_name = 'AdventureWorks Public Profile',  
    @principal_name = 'public',  
    @is_default = 1 ;  
```  
  

  
  
