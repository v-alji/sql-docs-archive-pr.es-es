---
title: Prácticas recomendadas de seguridad con bases de datos independientes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- contained database, threats
ms.assetid: 026ca5fc-95da-46b6-b882-fa20f765b51d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8a4a933b99090d29f38156c56c9efa56b73af5a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744127"
---
# <a name="security-best-practices-with-contained-databases"></a><span data-ttu-id="183ec-102">Prácticas recomendadas de seguridad con bases de datos independientes</span><span class="sxs-lookup"><span data-stu-id="183ec-102">Security Best Practices with Contained Databases</span></span>
  <span data-ttu-id="183ec-103">Las bases de datos independientes tienen algunas amenazas únicas que los administradores de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] deben comprender y mitigar.</span><span class="sxs-lookup"><span data-stu-id="183ec-103">Contained databases have some unique threats that should be understood and mitigated by [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] administrators.</span></span> <span data-ttu-id="183ec-104">La mayoría de ellas están relacionadas con el proceso de autenticación de `USER WITH PASSWORD`, que traslada el límite de autenticación del nivel de [!INCLUDE[ssDE](../../includes/ssde-md.md)] al de base de datos.</span><span class="sxs-lookup"><span data-stu-id="183ec-104">Most of the threats are related to the `USER WITH PASSWORD` authentication process, which moves the authentication boundary from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] level to the database level.</span></span>  
  
## <a name="threats-related-to-users"></a><span data-ttu-id="183ec-105">Amenazas relacionadas con usuarios</span><span class="sxs-lookup"><span data-stu-id="183ec-105">Threats Related to Users</span></span>  
 <span data-ttu-id="183ec-106">Los usuarios de una base de datos independiente que tengan el `ALTER ANY USER` permiso, como los miembros de los roles fijos de base de datos **db_owner** y **db_securityadmin** , pueden conceder acceso a la base de datos sin el conocimiento ni el permiso si el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Administrador.</span><span class="sxs-lookup"><span data-stu-id="183ec-106">Users in a contained database that have the `ALTER ANY USER` permission, such as members of the **db_owner** and **db_securityadmin** fixed database roles, can grant access to the database without the knowledge or permission if the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span> <span data-ttu-id="183ec-107">La concesión de acceso a usuarios en una base de datos independiente incrementa el área expuesta al ataque potencial en toda la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="183ec-107">Granting users access to a contained database increases the potential attack surface area against the whole [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="183ec-108">Los administradores deben comprender esta delegación de control de acceso y ser sumamente cuidadosos cuando conceden el permiso `ALTER ANY USER` a los usuarios de base de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="183ec-108">Administrators should understand this delegation of access control, and be very careful about granting users in the contained database the `ALTER ANY USER` permission.</span></span> <span data-ttu-id="183ec-109">Todos los propietarios de bases de datos tienen el permiso `ALTER ANY USER`.</span><span class="sxs-lookup"><span data-stu-id="183ec-109">All database owners have the `ALTER ANY USER` permission.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="183ec-110">deben auditar periódicamente a los usuarios de una base de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="183ec-110">administrators should periodically audit the users in a contained database.</span></span>  
  
### <a name="accessing-other-databases-using-the-guest-account"></a><span data-ttu-id="183ec-111">Acceder a otras bases de datos mediante la cuenta Invitado</span><span class="sxs-lookup"><span data-stu-id="183ec-111">Accessing Other Databases Using the guest Account</span></span>  
 <span data-ttu-id="183ec-112">Los propietarios y los usuarios de bases de datos con el permiso `ALTER ANY USER` pueden crear usuarios de bases de datos independientes.</span><span class="sxs-lookup"><span data-stu-id="183ec-112">Database owners and database users with the `ALTER ANY USER` permission can create contained database users.</span></span> <span data-ttu-id="183ec-113">Después de conectarse a una base de datos independiente en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un usuario de base de datos independiente puede obtener acceso a otras bases de datos en [!INCLUDE[ssDE](../../includes/ssde-md.md)], si en estas bases de datos se ha habilitado la cuenta **Invitado** .</span><span class="sxs-lookup"><span data-stu-id="183ec-113">After connecting to a contained database on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a contained database user can access other databases on the [!INCLUDE[ssDE](../../includes/ssde-md.md)], if the other databases have enabled the **guest** account.</span></span>  
  
### <a name="creating-a-duplicate-user-in-another-database"></a><span data-ttu-id="183ec-114">Crear un usuario duplicado en otra base de datos</span><span class="sxs-lookup"><span data-stu-id="183ec-114">Creating a Duplicate User in Another Database</span></span>  
 <span data-ttu-id="183ec-115">Algunas aplicaciones pueden solicitar que un usuario tenga acceso a más de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="183ec-115">Some applications might require that a user to have access to more than one database.</span></span> <span data-ttu-id="183ec-116">Se puede hacer creando usuarios de bases de datos independientes idénticos en cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="183ec-116">This can be done by creating identical contained database users in each database.</span></span> <span data-ttu-id="183ec-117">Use la opción SID al crear el segundo usuario con contraseña.</span><span class="sxs-lookup"><span data-stu-id="183ec-117">Use the SID option when creating the second user with password.</span></span> <span data-ttu-id="183ec-118">En el ejemplo siguiente se crean dos usuarios idénticos en dos bases de datos.</span><span class="sxs-lookup"><span data-stu-id="183ec-118">The following example creates two identical users in two databases.</span></span>  
  
```  
USE DB1;  
GO  
CREATE USER Carlo WITH PASSWORD = '<strong password>';   
-- Return the SID of the user  
SELECT SID FROM sys.database_principals WHERE name = 'Carlo';  
  
-- Change to the second database  
USE DB2;  
GO  
CREATE USER Carlo WITH PASSWORD = '<same password>', SID = <SID from DB1>;  
GO  
```  
  
 <span data-ttu-id="183ec-119">Para ejecutar una consulta entre bases de datos, debe establecer la opción `TRUSTWORTHY` en la base de datos que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="183ec-119">To execute a cross-database query, you must set the `TRUSTWORTHY` option on the calling database.</span></span> <span data-ttu-id="183ec-120">Por ejemplo, si el usuario (Carlo) definido anteriormente está en DB1, para ejecutar `SELECT * FROM db2.dbo.Table1;` el valor de `TRUSTWORTHY` debe estar activado para la base de datos DB1.</span><span class="sxs-lookup"><span data-stu-id="183ec-120">For example if the user (Carlo) defined above is in DB1, to execute `SELECT * FROM db2.dbo.Table1;` then the `TRUSTWORTHY` setting must be on for database DB1.</span></span> <span data-ttu-id="183ec-121">Ejecute el código siguiente para activar la configuración `TRUSTWORHTY`.</span><span class="sxs-lookup"><span data-stu-id="183ec-121">Execute the following code to set the `TRUSTWORHTY` setting on.</span></span>  
  
```  
ALTER DATABASE DB1 SET TRUSTWORTHY ON;  
```  
  
### <a name="creating-a-user-that-duplicates-a-login"></a><span data-ttu-id="183ec-122">Crear un usuario que duplica un inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="183ec-122">Creating a User that Duplicates a Login</span></span>  
 <span data-ttu-id="183ec-123">Si se crea un usuario de base de datos independiente con contraseña, con el mismo nombre que un inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y si el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se conecta especificando la base de datos independiente como el catálogo inicial, el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no podrá conectarse.</span><span class="sxs-lookup"><span data-stu-id="183ec-123">If a contained database user with password is created, using the same name as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login, and if the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login connects specifying the contained database as the initial catalog, then the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login will be unable to connect.</span></span> <span data-ttu-id="183ec-124">La conexión se evaluará como el usuario de base de datos independiente con entidad de seguridad con contraseña en la base de datos independiente en vez de como usuario basado en el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="183ec-124">The connection will be evaluated as the contained database user with password principal on the contained database instead of as a user based on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span> <span data-ttu-id="183ec-125">Esto podría ocasionar una denegación de servicio intencional o accidental para el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="183ec-125">This could cause an intentional or accidental denial of service for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
-   <span data-ttu-id="183ec-126">Como práctica recomendada, los miembros del rol fijo de servidor **sysadmin** siempre deben considerar realizar la conexión sin usar la opción de catálogo inicial.</span><span class="sxs-lookup"><span data-stu-id="183ec-126">As a best practice, members of the **sysadmin** fixed server role should consider always connecting without using the initial catalog option.</span></span> <span data-ttu-id="183ec-127">De esta forma, se conecta el inicio de sesión a la base de datos maestra y se evita que un propietario de base de datos use incorrectamente el intento de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="183ec-127">This connects the login to the master database and avoids any attempts by a database owner to misuse the login attempt.</span></span> <span data-ttu-id="183ec-128">Después, el administrador puede cambiar a la base de datos independiente mediante la `USE` *\<database>* instrucción.</span><span class="sxs-lookup"><span data-stu-id="183ec-128">Then the administrator can change to the contained database by using the `USE`*\<database>* statement.</span></span> <span data-ttu-id="183ec-129">Además, puede establecer la base de datos predeterminada del inicio de sesión en la base de datos independiente, que completa el inicio de sesión en la base de datos **maestra**y, a continuación, transfiere el inicio de sesión a la base de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="183ec-129">You can also set the default database of the login to the contained database, which completes the login to **master**, and then transfers the login to the contained database.</span></span>  
  
-   <span data-ttu-id="183ec-130">Como práctica recomendada, no cree usuarios de bases de datos independientes con contraseñas que tengan el mismo nombre que los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="183ec-130">As a best practice, do not create contained database users with passwords who have the same name as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins.</span></span>  
  
-   <span data-ttu-id="183ec-131">Si existe el inicio de sesión duplicado, conéctese a la base de datos **maestra** sin especificar ningún catálogo inicial y, a continuación, ejecute el `USE` comando para cambiar a la base de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="183ec-131">If the duplicate login exists, connect to the **master** database without specifying an initial catalog, and then execute the `USE` command to change to the contained database.</span></span>  
  
-   <span data-ttu-id="183ec-132">Cuando estén presentes bases de datos independientes, los usuarios de base de datos que no sean bases de datos independientes deben conectarse al [!INCLUDE[ssDE](../../includes/ssde-md.md)] sin usar ningún catálogo inicial ni especificar el nombre de una base de datos dependiente como el catálogo inicial.</span><span class="sxs-lookup"><span data-stu-id="183ec-132">When contained databases are present, users of databases that are not contained databases should connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] without using an initial catalog or by specifying the database name of a non-contained database as the initial catalog.</span></span> <span data-ttu-id="183ec-133">De esta forma, se evita la conexión a la base de datos independiente bajo un control menos directo por parte de los administradores de [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="183ec-133">This avoids connecting to the contained database which is under less direct control by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] administrators.</span></span>  
  
### <a name="increasing-access-by-changing-the-containment-status-of-a-database"></a><span data-ttu-id="183ec-134">Incrementar el acceso cambiando el estado de contención de una base de datos</span><span class="sxs-lookup"><span data-stu-id="183ec-134">Increasing Access by Changing the Containment Status of a Database</span></span>  
 <span data-ttu-id="183ec-135">Los inicios de sesión que tienen el `ALTER ANY DATABASE` permiso, como los miembros del rol fijo de servidor **dbcreator** , y los usuarios de una base de datos dependiente que tienen el `CONTROL DATABASE` permiso, como los miembros del rol fijo de base de datos **db_owner** , pueden cambiar la configuración de contención de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="183ec-135">Logins that have the `ALTER ANY DATABASE` permission, such as members of the **dbcreator** fixed server role, and users in a non-contained database that have the `CONTROL DATABASE` permission, such as members of the **db_owner** fixed database role, can change the containment setting of a database.</span></span> <span data-ttu-id="183ec-136">Si la configuración de contención de una base de datos se cambia de `NONE` a `PARTIAL` o `FULL`, se puede conceder acceso de usuario mediante la creación de usuarios de bases de datos independientes con contraseñas.</span><span class="sxs-lookup"><span data-stu-id="183ec-136">If the containment setting of a database is changed from `NONE` to either `PARTIAL` or `FULL`, then user access can be granted by creating contained database users with passwords.</span></span> <span data-ttu-id="183ec-137">De esta forma, se podría proporcionar acceso sin el conocimiento ni el consentimiento de los administradores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="183ec-137">This could provide access without the knowledge or consent of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrators.</span></span> <span data-ttu-id="183ec-138">Para evitar que se contengan bases de datos, establezca la [!INCLUDE[ssDE](../../includes/ssde-md.md)] `contained database authentication` opción en 0.</span><span class="sxs-lookup"><span data-stu-id="183ec-138">To prevent any databases from being contained, set the [!INCLUDE[ssDE](../../includes/ssde-md.md)]`contained database authentication` option to 0.</span></span> <span data-ttu-id="183ec-139">Para evitar que se conecten los usuarios de bases de datos independientes con contraseñas en las bases de datos independientes seleccionadas, use desencadenadores de inicio de sesión para cancelar los intentos de inicios de sesión de los usuarios de bases de datos independientes con contraseñas.</span><span class="sxs-lookup"><span data-stu-id="183ec-139">To prevent connections by contained database users with passwords on selected contained databases, use login triggers to cancel login attempts by contained database users with passwords.</span></span>  
  
### <a name="attaching-a-contained-database"></a><span data-ttu-id="183ec-140">Adjuntar una base de datos independiente</span><span class="sxs-lookup"><span data-stu-id="183ec-140">Attaching a Contained Database</span></span>  
 <span data-ttu-id="183ec-141">Si se adjunta una base de datos independiente, un administrador podría dar acceso a usuarios no deseados a la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="183ec-141">By attaching a contained database, an administrator could give unwanted users access to the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="183ec-142">Un administrador al que le preocupe este riesgo puede poner en línea la base de datos en el modo `RESTRICTED_USER`, que evita la autenticación de usuarios de bases de datos independientes con contraseñas.</span><span class="sxs-lookup"><span data-stu-id="183ec-142">An administrator concerned about this risk can bring the database online in `RESTRICTED_USER` mode, which prevents authentication for contained database users with passwords.</span></span> <span data-ttu-id="183ec-143">Solo las entidades de seguridad autorizadas mediante inicios de sesión podrán acceder a [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="183ec-143">Only principals authorized through logins will be able to access the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="183ec-144">Los usuarios se crean con los requisitos de contraseña en vigor en el momento de su creación y las contraseñas no se vuelven a comprobar cuando se adjunte una base de datos.</span><span class="sxs-lookup"><span data-stu-id="183ec-144">Users are created using the password requirements in effect at the time that they are created and passwords are not rechecked when a database is attached.</span></span> <span data-ttu-id="183ec-145">Si se adjunta una base de datos independiente que permitía contraseñas no seguras en un sistema con una directiva de contraseñas más estricta, un administrador podría permitir contraseñas que no cumplan la directiva de contraseñas actual en el [!INCLUDE[ssDE](../../includes/ssde-md.md)]que se adjunta.</span><span class="sxs-lookup"><span data-stu-id="183ec-145">By attaching a contained database which allowed weak passwords to a system with a stricter password policy, an administrator could permit passwords that do not meet the current password policy on the attaching [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="183ec-146">Los administradores pueden evitar la conservación de contraseñas no seguras exigiendo que todas las contraseñas se restablezcan para la base de datos adjunta.</span><span class="sxs-lookup"><span data-stu-id="183ec-146">Administrators can avoid retaining the weak passwords by requiring that all passwords be reset for the attached database.</span></span>  
  
### <a name="password-policies"></a><span data-ttu-id="183ec-147">Directivas de contraseñas</span><span class="sxs-lookup"><span data-stu-id="183ec-147">Password Policies</span></span>  
 <span data-ttu-id="183ec-148">Se puede requerir que las contraseñas de una base de datos sean contraseñas seguras, pero no se pueden proteger mediante directivas de contraseñas sólidas.</span><span class="sxs-lookup"><span data-stu-id="183ec-148">Passwords in a database can be required to be strong passwords, but cannot be protected by robust password policies.</span></span> <span data-ttu-id="183ec-149">Use la autenticación de Windows siempre que sea posible para aprovechar las directivas de contraseñas más amplias disponibles de Windows.</span><span class="sxs-lookup"><span data-stu-id="183ec-149">Use Windows Authentication whenever possible to take advantage of the more extensive password policies available from Windows.</span></span>  
  
### <a name="kerberos-authentication"></a><span data-ttu-id="183ec-150">Autenticación Kerberos</span><span class="sxs-lookup"><span data-stu-id="183ec-150">Kerberos Authentication</span></span>  
 <span data-ttu-id="183ec-151">Los usuarios de bases de datos independientes con contraseñas usan la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="183ec-151">Contained database users with passwords cannot use Kerberos Authentication.</span></span> <span data-ttu-id="183ec-152">Siempre que sea posible, use la autenticación de Windows para aprovechar características de Windows como Kerberos.</span><span class="sxs-lookup"><span data-stu-id="183ec-152">When possible, use Windows Authentication to take advantage of Windows features such as Kerberos.</span></span>  
  
### <a name="offline-dictionary-attack"></a><span data-ttu-id="183ec-153">Ataque por diccionario sin conexión</span><span class="sxs-lookup"><span data-stu-id="183ec-153">Offline Dictionary Attack</span></span>  
 <span data-ttu-id="183ec-154">Los valores hash de contraseña de los usuarios de bases de datos independientes se almacenan en la base de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="183ec-154">The password hashes for contained database users with passwords are stored in the contained database.</span></span> <span data-ttu-id="183ec-155">Cualquiera que tenga acceso a los archivos de la base de datos podría realizar un ataque por diccionario contra los usuarios de bases de datos independientes con contraseña de un sistema no auditado.</span><span class="sxs-lookup"><span data-stu-id="183ec-155">Anyone with access to the database files could perform a dictionary attack against the contained database users with passwords on an unaudited system.</span></span> <span data-ttu-id="183ec-156">Para mitigar esta amenaza, restrinja el acceso a los archivos de base de datos o solo permita conexiones a bases de datos independientes mediante la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="183ec-156">To mitigate this threat, restrict access to the database files, or only permit connections to contained databases by using Windows Authentication.</span></span>  
  
## <a name="escaping-a-contained-database"></a><span data-ttu-id="183ec-157">Establecer secuencias de escape en una base de datos independiente</span><span class="sxs-lookup"><span data-stu-id="183ec-157">Escaping a Contained Database</span></span>  
 <span data-ttu-id="183ec-158">Si una base de datos es independiente parcialmente, los administradores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deben auditar periódicamente las capacidades de los usuarios y de los módulos de bases de datos independientes.</span><span class="sxs-lookup"><span data-stu-id="183ec-158">If a database is partially contained, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrators should periodically audit the capabilities of the users and modules in contained databases.</span></span>  
  
## <a name="denial-of-service-through-auto_close"></a><span data-ttu-id="183ec-159">Denegación de servicio mediante AUTO_CLOSE</span><span class="sxs-lookup"><span data-stu-id="183ec-159">Denial of Service Through AUTO_CLOSE</span></span>  
 <span data-ttu-id="183ec-160">No configure bases de datos independientes para que se cierren automáticamente.</span><span class="sxs-lookup"><span data-stu-id="183ec-160">Do not configure contained databases to auto close.</span></span> <span data-ttu-id="183ec-161">Si se cierra la base de datos, su apertura para autenticar un usuario consume recursos adicionales y podría contribuir a un ataque de denegación de servicio.</span><span class="sxs-lookup"><span data-stu-id="183ec-161">If closed, opening the database to authenticate a user consumes additional resources and could contribute to a denial of service attack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="183ec-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="183ec-162">See Also</span></span>  
 <span data-ttu-id="183ec-163">[Bases de datos independientes](contained-databases.md) </span><span class="sxs-lookup"><span data-stu-id="183ec-163">[Contained Databases](contained-databases.md) </span></span>  
 [<span data-ttu-id="183ec-164">Migrar a una base de datos parcialmente independiente</span><span class="sxs-lookup"><span data-stu-id="183ec-164">Migrate to a Partially Contained Database</span></span>](migrate-to-a-partially-contained-database.md)  
  
  