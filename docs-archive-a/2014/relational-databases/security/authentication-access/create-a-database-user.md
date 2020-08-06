---
title: Crear un usuario de base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- SQL12.SWB.DATABASEUSER.GENERAL.F1
- sql12.swb.user.securables.f1
helpviewer_keywords:
- database users, creating
- creating users with Management Studio
- mapping users
- users [SQL Server], creating
- database user additions [SQL Server]
- database users, mapping
- CREATE USER [Management Studio]
- users [SQL Server], adding
- mapping database users
ms.assetid: 782798d3-9552-4514-9f58-e87be4b264e4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 97fc758c754f5fc8803e988d55147670fc3ff45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745149"
---
# <a name="create-a-database-user"></a><span data-ttu-id="9082b-102">Crear un usuario de base de datos</span><span class="sxs-lookup"><span data-stu-id="9082b-102">Create a Database User</span></span>
  <span data-ttu-id="9082b-103">En este tema se describe cómo crear un usuario de base de datos asignado a un inicio de sesión en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9082b-103">This topic describes how to create a database user mapped to a login in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="9082b-104">El usuario de la base de datos es la identidad del inicio de sesión cuando está conectado a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-104">The database user is the identity of the login when it is connected to a database.</span></span> <span data-ttu-id="9082b-105">El usuario de la base de datos puede utilizar el mismo nombre que el inicio de sesión, pero no es necesario.</span><span class="sxs-lookup"><span data-stu-id="9082b-105">The database user can use the same name as the login, but that is not required.</span></span> <span data-ttu-id="9082b-106">En este tema se supone que ya existe un inicio de sesión en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9082b-106">This topic assumes that a login already exists in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9082b-107">Para obtener información sobre cómo crear un inicio de sesión, consulte [crear un inicio de sesión](create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="9082b-107">For information about how to create a login, see [Create a Login](create-a-login.md).</span></span>  
  
 <span data-ttu-id="9082b-108">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="9082b-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9082b-109">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="9082b-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9082b-110">Fondo</span><span class="sxs-lookup"><span data-stu-id="9082b-110">Background</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9082b-111">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9082b-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9082b-112">**Para crear un usuario de base de datos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="9082b-112">**To create a database user, using:**</span></span>  
  
     [<span data-ttu-id="9082b-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9082b-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9082b-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9082b-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9082b-115">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="9082b-115">Before You Begin</span></span>  
  
###  <a name="background"></a><a name="Restrictions"></a> <span data-ttu-id="9082b-116">Información previa</span><span class="sxs-lookup"><span data-stu-id="9082b-116">Background</span></span>  
 <span data-ttu-id="9082b-117">Un usuario es una entidad de seguridad de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-117">A user is a database level security principal.</span></span> <span data-ttu-id="9082b-118">Los inicios de sesión deben estar asignados a un usuario de base de datos para poder conectarse a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-118">Logins must be mapped to a database user to connect to a database.</span></span> <span data-ttu-id="9082b-119">Un inicio de sesión se puede asignar a bases de datos diferentes como usuarios diferentes pero solo se puede asignar como un usuario en cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-119">A login can be mapped to different databases as different users but can only be mapped as one user in each database.</span></span> <span data-ttu-id="9082b-120">En una base de datos parcialmente independiente, puede crearse un usuario que no tenga un inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="9082b-120">In a partially contained database, a user can be created that does not have a login.</span></span> <span data-ttu-id="9082b-121">Para obtener más información sobre los usuarios de la base de datos independiente, vea [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9082b-121">For more information about contained database users, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="9082b-122">Si el usuario invitado de una base de datos está habilitado, un inicio de sesión que no esté asignado a un usuario de la base de datos puede entrar en la base de datos como el usuario invitado.</span><span class="sxs-lookup"><span data-stu-id="9082b-122">If the guest user in a database is enabled, a login that is not mapped to a database user can enter the database as the guest user.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9082b-123">El usuario invitado suele estar deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="9082b-123">The guest user is ordinarily disabled.</span></span> <span data-ttu-id="9082b-124">No habilite al usuario invitado a menos que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9082b-124">Do not enable the guest user unless it is necessary.</span></span>  
  
 <span data-ttu-id="9082b-125">Como entidad de seguridad, se pueden conceder permisos a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="9082b-125">As a security principal, permissions can be granted to users.</span></span> <span data-ttu-id="9082b-126">El ámbito de un usuario es la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-126">The scope of a user is the database.</span></span> <span data-ttu-id="9082b-127">Para establecer conexión con una base de datos concreta de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], un inicio de sesión debe estar asignado a un usuario de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-127">To connect to a specific database on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], a login must be mapped to a database user.</span></span> <span data-ttu-id="9082b-128">Los permisos dentro de la base de datos se conceden y deniegan al usuario de la base de datos, no al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="9082b-128">Permissions inside the database are granted and denied to the database user, not the login.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9082b-129">Seguridad</span><span class="sxs-lookup"><span data-stu-id="9082b-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9082b-130">Permisos</span><span class="sxs-lookup"><span data-stu-id="9082b-130">Permissions</span></span>  
 <span data-ttu-id="9082b-131">Debe tener el permiso `ALTER ANY USER` para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-131">Requires `ALTER ANY USER` permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9082b-132">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9082b-132">Using SQL Server Management Studio</span></span>  
  
##### <a name="to-create-a-database-user"></a><span data-ttu-id="9082b-133">Para crear un usuario de base de datos</span><span class="sxs-lookup"><span data-stu-id="9082b-133">To create a database user</span></span>  
  
1.  <span data-ttu-id="9082b-134">En el Explorador de objetos, expanda la carpeta **Bases de datos** .</span><span class="sxs-lookup"><span data-stu-id="9082b-134">In Object Explorer, expand the **Databases** folder.</span></span>  
  
2.  <span data-ttu-id="9082b-135">Expanda la base de datos en la que se va a crear el usuario de la misma.</span><span class="sxs-lookup"><span data-stu-id="9082b-135">Expand the database in which to create the new database user.</span></span>  
  
3.  <span data-ttu-id="9082b-136">Haga clic con el botón derecho en la carpeta **Seguridad**, seleccione **Nuevo** y después **Usuario...** .</span><span class="sxs-lookup"><span data-stu-id="9082b-136">Right-click the **Security** folder, point to **New**, and select **User...**.</span></span>  
  
4.  <span data-ttu-id="9082b-137">En el cuadro de diálogo **usuario de base de datos-nuevo** , en la página **General** , seleccione uno de los siguientes tipos de usuario de la lista **tipo de usuario** : **usuario SQL con inicio de sesión**, **usuario SQL sin inicio de sesión**, **usuario asignado a un certificado**, **usuario asignado a una clave asimétrica**o **usuario de Windows**.</span><span class="sxs-lookup"><span data-stu-id="9082b-137">In the **Database User - New** dialog box, on the **General** page, select one of the following user types from the **User type** list: **SQL user with login**, **SQL user without login**, **User mapped to a certificate**, **User mapped to an asymmetric key**, or **Windows user**.</span></span>  
  
5.  <span data-ttu-id="9082b-138">En el cuadro **Nombre de usuario** , escriba un nombre para el nuevo usuario.</span><span class="sxs-lookup"><span data-stu-id="9082b-138">In the **User name** box, enter a name for the new user.</span></span> <span data-ttu-id="9082b-139">Si ha elegido **Usuario de Windows** en la lista **Tipo de usuario**, también puede hacer clic en los puntos suspensivos **(...)** para abrir el cuadro de diálogo **Seleccione Usuario o Grupo**.</span><span class="sxs-lookup"><span data-stu-id="9082b-139">If you have chosen **Windows user** from the **User type** list, you can also click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
6.  <span data-ttu-id="9082b-140">En el cuadro **Nombre de inicio de sesión** , escriba el inicio de sesión para el usuario.</span><span class="sxs-lookup"><span data-stu-id="9082b-140">In the **Login name** box, enter the login for the user.</span></span> <span data-ttu-id="9082b-141">Como alternativa, haga clic en los puntos suspensivos **(...)** para abrir el cuadro de diálogo **Seleccionar inicio de sesión**.</span><span class="sxs-lookup"><span data-stu-id="9082b-141">Alternately, click the ellipsis **(...)** to open the **Select Login** dialog box.</span></span> <span data-ttu-id="9082b-142">Si selecciona**Usuario SQL con inicio de sesión** o **Usuario de Windows** en la lista **Tipo de usuario** , estará disponible **Nombre de inicio de sesión** .</span><span class="sxs-lookup"><span data-stu-id="9082b-142">**Login name** is available if you select either **SQL user with login** or **Windows user** from the **User type** list.</span></span>  
  
7.  <span data-ttu-id="9082b-143">En el cuadro **Esquema predeterminado** , especifique el esquema al que pertenecerán los objetos creados por este usuario.</span><span class="sxs-lookup"><span data-stu-id="9082b-143">In the **Default schema** box, specifies the schema that will own objects created by this user.</span></span> <span data-ttu-id="9082b-144">Como alternativa, haga clic en los puntos suspensivos **(...)** para abrir el cuadro de diálogo **Seleccionar esquema**.</span><span class="sxs-lookup"><span data-stu-id="9082b-144">Alternately, click the ellipsis **(...)** to open the **Select Schema** dialog box.</span></span> <span data-ttu-id="9082b-145">Si selecciona**Usuario SQL con inicio de sesión** , **Usuario SQL sin inicio de sesión**, **Usuario de Windows**en la lista **Tipo de usuario** , estará disponible **Esquema predeterminado** .</span><span class="sxs-lookup"><span data-stu-id="9082b-145">**Default schema** is available if you select either **SQL user with login**, **SQL user without login**, or **Windows user** from the **User type** list.</span></span>  
  
8.  <span data-ttu-id="9082b-146">En el cuadro de **Nombre de certificado** , escriba el certificado que se utilizará para el usuario de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-146">In the **Certificate name** box, enter the certificate to be used for the database user.</span></span> <span data-ttu-id="9082b-147">Como alternativa, haga clic en los puntos suspensivos **(...)** para abrir el cuadro de diálogo **Seleccionar certificado**.</span><span class="sxs-lookup"><span data-stu-id="9082b-147">Alternately, click the ellipsis **(...)** to open the **Select Certificate** dialog box.</span></span> <span data-ttu-id="9082b-148">Si selecciona**Usuario asignado a un certificado** en la lista **Tipo de usuario** , estará disponible **Nombre de certificado** .</span><span class="sxs-lookup"><span data-stu-id="9082b-148">**Certificate name** is available if you select **User mapped to a certificate** from the **User type** list.</span></span>  
  
9. <span data-ttu-id="9082b-149">En el cuadro **Nombre de clave asimétrica**  , escriba la clave que se va a usar para el usuario de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-149">In the **Asymmetric key name**  box, enter the key to be used for the database user.</span></span> <span data-ttu-id="9082b-150">Como alternativa, haga clic en los puntos suspensivos **(...)** para abrir el cuadro de diálogo **Seleccionar clave asimétrica**.</span><span class="sxs-lookup"><span data-stu-id="9082b-150">Alternately, click the ellipsis **(...)** to open the **Select Asymmetric Key** dialog box.</span></span> <span data-ttu-id="9082b-151">Si selecciona**Usuario asignado a una clave asimétrica** en la lista **Tipo de usuario** , estará disponible **Nombre de clave asimétrica** .</span><span class="sxs-lookup"><span data-stu-id="9082b-151">**Asymmetric key name** is available if you select **User mapped to an asymmetric key** from the **User type** list.</span></span>  
  
10. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="additional-options"></a><span data-ttu-id="9082b-152">Opciones adicionales</span><span class="sxs-lookup"><span data-stu-id="9082b-152">Additional Options</span></span>  
 <span data-ttu-id="9082b-153">En el cuadro de diálogo **Usuario de la base de datos - Nuevo** también se proporcionan opciones en cuatro páginas adicionales: **Esquemas de propiedad**, **Pertenencia**, **Elementos protegibles** y **Propiedades extendidas**.</span><span class="sxs-lookup"><span data-stu-id="9082b-153">The **Database User - New** dialog box also offers options on four additional pages: **Owned Schemas**, **Membership**, **Securables**, and **Extended Properties**.</span></span>  
  
-   <span data-ttu-id="9082b-154">La página **Esquemas de propiedad** enumera todos los esquemas posibles que pueden ser propiedad del nuevo usuario de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-154">The **Owned Schemas** page lists all possible schemas that can be owned by the new database user.</span></span> <span data-ttu-id="9082b-155">Para agregar o quitar esquemas en un usuario de base de datos, en **Esquemas propiedad de este usuario**, active o desactive las casillas situadas junto a los esquemas.</span><span class="sxs-lookup"><span data-stu-id="9082b-155">To add schemas to or remove them from a database user, under **Schemas owned by this user**, select or clear the check boxes next to the schemas.</span></span>  
  
-   <span data-ttu-id="9082b-156">La página **Pertenencia** enumera todos los roles de pertenencia de base de datos posibles que pueden ser propiedad del nuevo usuario de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-156">The **Membership** page lists all possible database membership roles that can be owned by the new database user.</span></span> <span data-ttu-id="9082b-157">Para agregar o quitar roles en un usuario de base de datos, en **Pertenencia al rol de la base de datos**, active o desactive las casillas situadas junto a los roles.</span><span class="sxs-lookup"><span data-stu-id="9082b-157">To add roles to or remove them from a database user, under **Database role membership**, select or clear the check boxes next to the roles.</span></span>  
  
-   <span data-ttu-id="9082b-158">La página **Elementos protegibles** muestra todos los elementos protegibles posibles y los permisos en esos elementos protegibles que se pueden conceder al inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="9082b-158">The **Securables** page lists all possible securables and the permissions on those securables that can be granted to the login.</span></span>  
  
-   <span data-ttu-id="9082b-159">La página **Propiedades extendidas** permite agregar propiedades personalizadas a los usuarios de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9082b-159">The **Extended properties** page allows you to add custom properties to database users.</span></span> <span data-ttu-id="9082b-160">En esta página están disponibles las opciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="9082b-160">The following options are available on this page.</span></span>  
  
     <span data-ttu-id="9082b-161">**Base de datos**</span><span class="sxs-lookup"><span data-stu-id="9082b-161">**Database**</span></span>  
     <span data-ttu-id="9082b-162">Muestra el nombre de la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9082b-162">Displays the name of the selected database.</span></span> <span data-ttu-id="9082b-163">Este campo es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9082b-163">This field is read-only.</span></span>  
  
     <span data-ttu-id="9082b-164">**Intercalación**</span><span class="sxs-lookup"><span data-stu-id="9082b-164">**Collation**</span></span>  
     <span data-ttu-id="9082b-165">Muestra la intercalación utilizada para la base de datos seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9082b-165">Displays the collation used for the selected database.</span></span> <span data-ttu-id="9082b-166">Este campo es de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9082b-166">This field is read-only.</span></span>  
  
     <span data-ttu-id="9082b-167">**Propiedades**</span><span class="sxs-lookup"><span data-stu-id="9082b-167">**Properties**</span></span>  
     <span data-ttu-id="9082b-168">Muestra o especifica las propiedades extendidas del objeto.</span><span class="sxs-lookup"><span data-stu-id="9082b-168">View or specify the extended properties for the object.</span></span> <span data-ttu-id="9082b-169">Cada propiedad extendida está formada por un par nombre/valor de metadatos asociados al objeto.</span><span class="sxs-lookup"><span data-stu-id="9082b-169">Each extended property consists of a name/value pair of metadata associated with the object.</span></span>  
  
     <span data-ttu-id="9082b-170">**Puntos suspensivos (...)**</span><span class="sxs-lookup"><span data-stu-id="9082b-170">**Ellipsis (...)**</span></span>  
     <span data-ttu-id="9082b-171">Haga clic en los puntos suspensivos **(...)** situados detrás de **Valor** para abrir el cuadro de diálogo **Valor para propiedad extendida**.</span><span class="sxs-lookup"><span data-stu-id="9082b-171">Click the ellipsis **(...)** after **Value** to open the **Value for Extended Property** dialog box.</span></span> <span data-ttu-id="9082b-172">Escriba o muestre el valor de la propiedad extendida en esta ubicación mayor.</span><span class="sxs-lookup"><span data-stu-id="9082b-172">Type or view the value of the extended property in this larger location.</span></span> <span data-ttu-id="9082b-173">Para obtener más información, vea [Valor para propiedad extendida (cuadro de diálogo)](../../databases/value-for-extended-property-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="9082b-173">For more information, see [Value for Extended Property Dialog Box](../../databases/value-for-extended-property-dialog-box.md).</span></span>  
  
     <span data-ttu-id="9082b-174">**Eliminar**</span><span class="sxs-lookup"><span data-stu-id="9082b-174">**Delete**</span></span>  
     <span data-ttu-id="9082b-175">Elimina la propiedad extendida que se ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9082b-175">Removes the selected extended property.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9082b-176">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9082b-176">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-user"></a><span data-ttu-id="9082b-177">Para crear un usuario de base de datos</span><span class="sxs-lookup"><span data-stu-id="9082b-177">To create a database user</span></span>  
  
1.  <span data-ttu-id="9082b-178">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9082b-178">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9082b-179">En la barra de Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="9082b-179">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9082b-180">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="9082b-180">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the login AbolrousHazem with password '340$Uuxwp7Mcxo7Khy'.  
    CREATE LOGIN AbolrousHazem   
        WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
    GO  
  
    -- Creates a database user for the login created above.  
    CREATE USER AbolrousHazem FOR LOGIN AbolrousHazem;  
    GO  
    ```  
  
 <span data-ttu-id="9082b-181">Para obtener más información, vea [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9082b-181">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9082b-182">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9082b-182">See Also</span></span>  
 [<span data-ttu-id="9082b-183">Entidades de seguridad &#40;motor de base de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="9082b-183">Principals &#40;Database Engine&#41;</span></span>](principals-database-engine.md)  
  
  
