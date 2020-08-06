---
title: MSSQLSERVER_18456 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18456 (Database Engine error)
ms.assetid: c417631d-be1f-42e0-8844-9f92c77e11f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5addb6bfb9d056d9f1796749ae629d4150102a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745793"
---
# <a name="mssqlserver_18456"></a><span data-ttu-id="02da8-102">MSSQLSERVER_18456</span><span class="sxs-lookup"><span data-stu-id="02da8-102">MSSQLSERVER_18456</span></span>
    
## <a name="details"></a><span data-ttu-id="02da8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="02da8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02da8-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="02da8-104">Product Name</span></span>|<span data-ttu-id="02da8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="02da8-105">SQL Server</span></span>|  
|<span data-ttu-id="02da8-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="02da8-106">Event ID</span></span>|<span data-ttu-id="02da8-107">18456</span><span class="sxs-lookup"><span data-stu-id="02da8-107">18456</span></span>|  
|<span data-ttu-id="02da8-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="02da8-108">Event Source</span></span>|<span data-ttu-id="02da8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="02da8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="02da8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="02da8-110">Component</span></span>|<span data-ttu-id="02da8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="02da8-111">SQLEngine</span></span>|  
|<span data-ttu-id="02da8-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="02da8-112">Symbolic Name</span></span>|<span data-ttu-id="02da8-113">LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="02da8-113">LOGON_FAILED</span></span>|  
|<span data-ttu-id="02da8-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="02da8-114">Message Text</span></span>|<span data-ttu-id="02da8-115">Error de inicio de sesión del usuario '%.\*ls'.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="02da8-115">Login failed for user '%.\*ls'.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="02da8-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="02da8-116">Explanation</span></span>  
 <span data-ttu-id="02da8-117">Si se rechaza un intento de conexión como consecuencia de un error de autenticación porque el nombre de usuario o la contraseña no son válidos, el cliente recibe el siguiente mensaje de error:  "Error de inicio de sesión del usuario '<nombreDeUsuario>'.</span><span class="sxs-lookup"><span data-stu-id="02da8-117">When a connection attempt is rejected because of an authentication failure that involves a bad password or user name, a message similar to the following is returned to the client:  "Login failed for user '<user_name>'.</span></span> <span data-ttu-id="02da8-118">(Microsoft SQL Server, Error: 18456)".</span><span class="sxs-lookup"><span data-stu-id="02da8-118">(Microsoft SQL Server, Error: 18456)".</span></span>  
  
 <span data-ttu-id="02da8-119">El cliente recibe la siguiente información adicional:</span><span class="sxs-lookup"><span data-stu-id="02da8-119">Additional information returned to the client includes the following:</span></span>  
  
 <span data-ttu-id="02da8-120">"Error de inicio de sesión del usuario '<nombreDeUsuario>'.</span><span class="sxs-lookup"><span data-stu-id="02da8-120">"Login failed for user '<user_name>'.</span></span> <span data-ttu-id="02da8-121">(Proveedor de datos .Net SqlClient)"</span><span class="sxs-lookup"><span data-stu-id="02da8-121">(.Net SqlClient Data Provider)"</span></span>  
  
 -----------------------------\-  
  
 <span data-ttu-id="02da8-122">"Nombre del servidor: <nombre_equipo>"</span><span class="sxs-lookup"><span data-stu-id="02da8-122">"Server Name: <computer_name>"</span></span>  
  
 <span data-ttu-id="02da8-123">"Número de error: 18456"</span><span class="sxs-lookup"><span data-stu-id="02da8-123">"Error Number: 18456"</span></span>  
  
 <span data-ttu-id="02da8-124">"Gravedad: 14"</span><span class="sxs-lookup"><span data-stu-id="02da8-124">"Severity: 14"</span></span>  
  
 <span data-ttu-id="02da8-125">"Estado: 1"</span><span class="sxs-lookup"><span data-stu-id="02da8-125">"State: 1"</span></span>  
  
 <span data-ttu-id="02da8-126">"Número de línea: 65536"</span><span class="sxs-lookup"><span data-stu-id="02da8-126">"Line Number: 65536"</span></span>  
  
 <span data-ttu-id="02da8-127">También podría mostrarse el error siguiente:</span><span class="sxs-lookup"><span data-stu-id="02da8-127">The following message might also be returned:</span></span>  
  
 <span data-ttu-id="02da8-128">"Mensaje 18456, nivel 14, estado 1, servidor <nombre_equipo>, línea 1"</span><span class="sxs-lookup"><span data-stu-id="02da8-128">"Msg 18456, Level 14, State 1, Server <computer_name>, Line 1"</span></span>  
  
 <span data-ttu-id="02da8-129">"Error de inicio de sesión del usuario '<nombreDeUsuario>'".</span><span class="sxs-lookup"><span data-stu-id="02da8-129">"Login failed for user '<user_name>'."</span></span>  
  
## <a name="additional-error-information"></a><span data-ttu-id="02da8-130">Información adicional sobre errores</span><span class="sxs-lookup"><span data-stu-id="02da8-130">Additional Error Information</span></span>  
 <span data-ttu-id="02da8-131">Para aumentar la seguridad, en el mensaje de error que se devuelve al cliente se oculta la naturaleza del error de autenticación.</span><span class="sxs-lookup"><span data-stu-id="02da8-131">To increase security, the error message that is returned to the client deliberately hides the nature of the authentication error.</span></span> <span data-ttu-id="02da8-132">Con todo, en el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el error correspondiente contiene el estado del error que indica la condición del error de autenticación</span><span class="sxs-lookup"><span data-stu-id="02da8-132">However, in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a corresponding error contains an error state that maps to an authentication failure condition.</span></span> <span data-ttu-id="02da8-133">Compare el estado del error en la lista siguiente para determinar la causa del error de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="02da8-133">Compare the error state to the following list to determine the reason for the login failure.</span></span>  
  
|<span data-ttu-id="02da8-134">State</span><span class="sxs-lookup"><span data-stu-id="02da8-134">State</span></span>|<span data-ttu-id="02da8-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="02da8-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="02da8-136">1</span><span class="sxs-lookup"><span data-stu-id="02da8-136">1</span></span>|<span data-ttu-id="02da8-137">La información sobre el error no está disponible.</span><span class="sxs-lookup"><span data-stu-id="02da8-137">Error information is not available.</span></span> <span data-ttu-id="02da8-138">Este estado significa normalmente que no se tiene el permiso necesario para recibir los detalles del error.</span><span class="sxs-lookup"><span data-stu-id="02da8-138">This state usually means you do not have permission to receive the error details.</span></span> <span data-ttu-id="02da8-139">Póngase en contacto con su administrador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="02da8-139">Contact your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator for more information.</span></span>|  
|<span data-ttu-id="02da8-140">2</span><span class="sxs-lookup"><span data-stu-id="02da8-140">2</span></span>|<span data-ttu-id="02da8-141">El identificador de usuario no es válido.</span><span class="sxs-lookup"><span data-stu-id="02da8-141">User ID is not valid.</span></span>|  
|<span data-ttu-id="02da8-142">5</span><span class="sxs-lookup"><span data-stu-id="02da8-142">5</span></span>|<span data-ttu-id="02da8-143">El identificador de usuario no es válido.</span><span class="sxs-lookup"><span data-stu-id="02da8-143">User ID is not valid.</span></span>|  
|<span data-ttu-id="02da8-144">6</span><span class="sxs-lookup"><span data-stu-id="02da8-144">6</span></span>|<span data-ttu-id="02da8-145">Se ha intentado usar un nombre de inicio de sesión de Windows con la autenticación de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="02da8-145">An attempt was made to use a Windows login name with SQL Server Authentication.</span></span>|  
|<span data-ttu-id="02da8-146">7</span><span class="sxs-lookup"><span data-stu-id="02da8-146">7</span></span>|<span data-ttu-id="02da8-147">El inicio de sesión está deshabilitado y la contraseña no es correcta.</span><span class="sxs-lookup"><span data-stu-id="02da8-147">Login is disabled, and the password is incorrect.</span></span>|  
|<span data-ttu-id="02da8-148">8</span><span class="sxs-lookup"><span data-stu-id="02da8-148">8</span></span>|<span data-ttu-id="02da8-149">La contraseña no es correcta.</span><span class="sxs-lookup"><span data-stu-id="02da8-149">The password is incorrect.</span></span>|  
|<span data-ttu-id="02da8-150">9</span><span class="sxs-lookup"><span data-stu-id="02da8-150">9</span></span>|<span data-ttu-id="02da8-151">La contraseña no es válida.</span><span class="sxs-lookup"><span data-stu-id="02da8-151">Password is not valid.</span></span>|  
|<span data-ttu-id="02da8-152">11</span><span class="sxs-lookup"><span data-stu-id="02da8-152">11</span></span>|<span data-ttu-id="02da8-153">El inicio de sesión es válido, pero se ha producido un error de acceso al servidor.</span><span class="sxs-lookup"><span data-stu-id="02da8-153">Login is valid, but server access failed.</span></span> <span data-ttu-id="02da8-154">Una causa posible de este error se produce cuando el usuario de Windows tiene acceso a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como miembro del grupo de administradores locales, pero Windows no proporciona las credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="02da8-154">One possible cause of this error is when the Windows user has access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a member of the local administrators group, but Windows is not providing administrator credentials.</span></span> <span data-ttu-id="02da8-155">Para conectarse, inicie el programa de conexión mediante la opción **Ejecutar como administrador** y, a continuación, agregue el usuario de Windows a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como inicio de sesión específico.</span><span class="sxs-lookup"><span data-stu-id="02da8-155">To connect, start the connecting program using the **Run as administrator** option, and then add the Windows user to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a specific login.</span></span>|  
|<span data-ttu-id="02da8-156">12</span><span class="sxs-lookup"><span data-stu-id="02da8-156">12</span></span>|<span data-ttu-id="02da8-157">El inicio de sesión es válido, pero se ha producido un error de acceso al servidor.</span><span class="sxs-lookup"><span data-stu-id="02da8-157">Login is valid login, but server access failed.</span></span>|  
|<span data-ttu-id="02da8-158">18</span><span class="sxs-lookup"><span data-stu-id="02da8-158">18</span></span>|<span data-ttu-id="02da8-159">Se debe cambiar la contraseña.</span><span class="sxs-lookup"><span data-stu-id="02da8-159">Password must be changed.</span></span>|  
  
 <span data-ttu-id="02da8-160">Hay otros estados de error e indican un error de procesamiento interno inesperado.</span><span class="sxs-lookup"><span data-stu-id="02da8-160">Other error states exist and signify an unexpected internal processing error.</span></span>  
  
 <span data-ttu-id="02da8-161">**Una causa posible inusual adicional**</span><span class="sxs-lookup"><span data-stu-id="02da8-161">**An additional unusual possible cause**</span></span>  
  
 <span data-ttu-id="02da8-162">El motivo del error: **se ha producido un error al intentar iniciar sesión mediante autenticación de SQL. El servidor está configurado solo para la autenticación de Windows.**</span><span class="sxs-lookup"><span data-stu-id="02da8-162">The error reason **An attempt to login using SQL authentication failed. Server is configured for Windows authentication only.**</span></span> <span data-ttu-id="02da8-163">Puede devolverse en las siguientes situaciones.</span><span class="sxs-lookup"><span data-stu-id="02da8-163">can be returned in the following situations.</span></span>  
  
-   <span data-ttu-id="02da8-164">Cuando el servidor está configurado para la autenticación de modo mixto y una conexión ODBC utiliza el protocolo TCP, pero esta no especifica explícitamente que se debe utilizar una conexión de confianza.</span><span class="sxs-lookup"><span data-stu-id="02da8-164">When the server is configured for mixed mode authentication, and an ODBC connection uses the TCP protocol, and the connection does not explicitly specify that the connection should use a trusted connection.</span></span>  
  
-   <span data-ttu-id="02da8-165">Cuando el servidor está configurado para la autenticación de modo mixto, una conexión ODBC utiliza canalizaciones con nombre, las credenciales utilizadas por el cliente para abrir la canalización con nombre se usan para suplantar automáticamente al usuario y la conexión no especifica de forma explícita que se debe utilizar una conexión de confianza.</span><span class="sxs-lookup"><span data-stu-id="02da8-165">When the server is configured for mixed mode authentication, and an ODBC connection uses named pipes, and the credentials the client used to open the named pipe are used to automatically impersonate the user, and the connection does not explicitly specify that the connection should use a trusted connection.</span></span>  
  
 <span data-ttu-id="02da8-166">Para solucionar este problema, incluya `TRUSTED_CONNECTION = TRUE` en la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="02da8-166">To resolve this issue, include `TRUSTED_CONNECTION = TRUE` in the connection string.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="02da8-167">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="02da8-167">Examples</span></span>  
 <span data-ttu-id="02da8-168">En este ejemplo, el estado de error de autenticación es 8.</span><span class="sxs-lookup"><span data-stu-id="02da8-168">In this example, the authentication error state is 8.</span></span> <span data-ttu-id="02da8-169">Esto indica que la contraseña no es correcta.</span><span class="sxs-lookup"><span data-stu-id="02da8-169">This indicates that the password is incorrect.</span></span>  
  
|<span data-ttu-id="02da8-170">Date</span><span class="sxs-lookup"><span data-stu-id="02da8-170">Date</span></span>|<span data-ttu-id="02da8-171">Source</span><span class="sxs-lookup"><span data-stu-id="02da8-171">Source</span></span>|<span data-ttu-id="02da8-172">Message</span><span class="sxs-lookup"><span data-stu-id="02da8-172">Message</span></span>|  
|----------|------------|-------------|  
|<span data-ttu-id="02da8-173">2007-12-05 20:12:56.34</span><span class="sxs-lookup"><span data-stu-id="02da8-173">2007-12-05 20:12:56.34</span></span>|<span data-ttu-id="02da8-174">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="02da8-174">Logon</span></span>|<span data-ttu-id="02da8-175">Error: 18456, Gravedad: 14, Estado: 8.</span><span class="sxs-lookup"><span data-stu-id="02da8-175">Error: 18456, Severity: 14, State: 8.</span></span>|  
|<span data-ttu-id="02da8-176">2007-12-05 20:12:56.34</span><span class="sxs-lookup"><span data-stu-id="02da8-176">2007-12-05 20:12:56.34</span></span>|<span data-ttu-id="02da8-177">Inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="02da8-177">Logon</span></span>|<span data-ttu-id="02da8-178">Error de inicio de sesión del usuario '<nombreDeUsuario>'</span><span class="sxs-lookup"><span data-stu-id="02da8-178">Login failed for user '<user_name>'.</span></span> <span data-ttu-id="02da8-179">[CLIENT: \<ip address>]</span><span class="sxs-lookup"><span data-stu-id="02da8-179">[CLIENT: \<ip address>]</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="02da8-180">Cuando se instala [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante el modo de autenticación de Windows y posteriormente se cambia al modo de autenticación de Windows y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], el inicio de sesión **sa** está deshabilitado inicialmente.</span><span class="sxs-lookup"><span data-stu-id="02da8-180">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed using Windows Authentication mode and is later changed to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows Authentication mode, the **sa** login is initially disabled.</span></span> <span data-ttu-id="02da8-181">Esto provoca el estado de error 7: "Error de inicio de sesión del usuario 'sa'". Para habilitar el inicio de sesión **sa**, vea [Cambiar el modo de autenticación del servidor](../../database-engine/configure-windows/change-server-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="02da8-181">This causes the state 7 error: "Login failed for user 'sa'." To enable the **sa** login, see [Change Server Authentication Mode](../../database-engine/configure-windows/change-server-authentication-mode.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="02da8-182">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="02da8-182">User Action</span></span>  
 <span data-ttu-id="02da8-183">Si intenta establecer conexión usando la Autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], compruebe que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está configurado en modo de autenticación mixto.</span><span class="sxs-lookup"><span data-stu-id="02da8-183">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured in Mixed Authentication Mode.</span></span>  
  
 <span data-ttu-id="02da8-184">Si intenta establecer conexión usando la Autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], compruebe que el inicio de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] existe y que lo ha escrito correctamente.</span><span class="sxs-lookup"><span data-stu-id="02da8-184">If you are trying to connect using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, verify that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login exists and that you have spelled it properly.</span></span>  
  
 <span data-ttu-id="02da8-185">Si intenta establecer conexión usando la Autenticación de Windows, compruebe que está registrado correctamente en el dominio correcto.</span><span class="sxs-lookup"><span data-stu-id="02da8-185">If you are trying to connect using Windows Authentication, verify that you are properly logged into the correct domain.</span></span>  
  
 <span data-ttu-id="02da8-186">Si el estado de su error es 1, póngase en contacto con su administrador de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02da8-186">If your error indicates state 1, contact your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] administrator.</span></span>  
  
 <span data-ttu-id="02da8-187">Si intenta conectarse con sus credenciales de administrador, inicie la aplicación mediante la opción **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="02da8-187">If you are trying to connect using your administrator credentials, start you application by using the **Run as Administrator** option.</span></span> <span data-ttu-id="02da8-188">Cuando se haya conectado, agregue el usuario de Windows como inicio de sesión individual.</span><span class="sxs-lookup"><span data-stu-id="02da8-188">When connected, add your Windows user as an individual login.</span></span>  
  
 <span data-ttu-id="02da8-189">Si el [!INCLUDE[ssDE](../../includes/ssde-md.md)] admite bases de datos independientes, confirme que el inicio de sesión no se eliminó tras la migración a un usuario de base de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="02da8-189">If the [!INCLUDE[ssDE](../../includes/ssde-md.md)] supports contained databases, confirm that the login was not deleted after migration to a contained database user.</span></span>  
  
 <span data-ttu-id="02da8-190">Al conectarse a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de forma local, las conexiones de los servicios que se ejecutan en **NT AUTHORITY\NETWORK SERVICE** deben autenticarse con el nombre de dominio completo del equipo.</span><span class="sxs-lookup"><span data-stu-id="02da8-190">When connecting locally to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], connections from services running under **NT AUTHORITY\NETWORK SERVICE** must authenticate using the computers fully qualified domain name.</span></span> <span data-ttu-id="02da8-191">Para obtener más información, consulte: [Procedimientos: Usar la cuenta de servicio de red para obtener acceso a recursos en ASP.NET](https://msdn.microsoft.com/library/ff647402.aspx)</span><span class="sxs-lookup"><span data-stu-id="02da8-191">For more information, see [How To: Use the Network Service Account to Access Resources in ASP.NET](https://msdn.microsoft.com/library/ff647402.aspx)</span></span>  
  
  
