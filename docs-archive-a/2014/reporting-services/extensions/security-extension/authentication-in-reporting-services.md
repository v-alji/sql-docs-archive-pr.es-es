---
title: Autenticación de Windows en Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], authentication
- forms-based authentication [Reporting Services]
- authentication [Reporting Services]
- custom authentication [Reporting Services]
ms.assetid: 103ce1f9-31d8-44bb-b540-2752e4dcf60b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59e97ba6ef849d8b4bfddfd6953c85826e351d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673520"
---
# <a name="authentication-in-reporting-services"></a><span data-ttu-id="be650-102">Autenticación de Windows en Reporting Services</span><span class="sxs-lookup"><span data-stu-id="be650-102">Authentication in Reporting Services</span></span>
  <span data-ttu-id="be650-103">La autenticación es el proceso de establecer el derecho de un usuario en una identidad.</span><span class="sxs-lookup"><span data-stu-id="be650-103">Authentication is the process of establishing a user's right to an identity.</span></span> <span data-ttu-id="be650-104">Hay muchas técnicas que puede utilizar para autenticar a un usuario.</span><span class="sxs-lookup"><span data-stu-id="be650-104">There are many techniques that you can use to authenticate a user.</span></span> <span data-ttu-id="be650-105">La manera más común es mediante contraseñas.</span><span class="sxs-lookup"><span data-stu-id="be650-105">The most common way is to use passwords.</span></span> <span data-ttu-id="be650-106">Por ejemplo, al implementar la autenticación de formularios, desea una implementación que consulte las credenciales (normalmente con alguna interfaz que solicita un nombre de inicio de sesión y una contraseña) de los usuarios y, a continuación, valida los usuarios con un almacén de datos, como una tabla de base de datos o un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="be650-106">When you implement Forms Authentication, for example, you want an implementation that queries users for credentials (usually by some interface that requests a login name and password) and then validates users against a data store, such as a database table or configuration file.</span></span> <span data-ttu-id="be650-107">Si no se pueden validar las credenciales, se produce un error en el proceso de autenticación y el usuario asumirá una identidad anónima.</span><span class="sxs-lookup"><span data-stu-id="be650-107">If the credentials can't be validated, the authentication process fails and the user will assume an anonymous identity.</span></span>  
  
## <a name="custom-authentication-in-reporting-services"></a><span data-ttu-id="be650-108">Autenticación personalizada en Reporting Services</span><span class="sxs-lookup"><span data-stu-id="be650-108">Custom Authentication in Reporting Services</span></span>  
 <span data-ttu-id="be650-109">En [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], el sistema operativo Windows administra la autenticación de los usuarios a través de la seguridad integrada o de la recepción explícita y la validación de las credenciales del usuario.</span><span class="sxs-lookup"><span data-stu-id="be650-109">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], the Windows operating system handles the authentication of users either through integrated security or through the explicit reception and validation of user credentials.</span></span> <span data-ttu-id="be650-110">La autenticación personalizada se puede desarrollar en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] para admitir esquemas de autenticación adicionales.</span><span class="sxs-lookup"><span data-stu-id="be650-110">Custom authentication can be developed in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to support additional authentication schemes.</span></span> <span data-ttu-id="be650-111">Esto se posibilita a través de la interfaz de extensión de la seguridad <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>.</span><span class="sxs-lookup"><span data-stu-id="be650-111">This is made possible through the security extension interface <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>.</span></span> <span data-ttu-id="be650-112">Todas las extensiones heredan de la interfaz base <xref:Microsoft.ReportingServices.Interfaces.IExtension> para cualquier extensión que implemente y use el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="be650-112">All extensions inherit from the <xref:Microsoft.ReportingServices.Interfaces.IExtension> base interface for any extension deployed and used by the report server.</span></span> <span data-ttu-id="be650-113"><xref:Microsoft.ReportingServices.Interfaces.IExtension>, así como <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>, son miembros del espacio de nombres <xref:Microsoft.ReportingServices.Interfaces>.</span><span class="sxs-lookup"><span data-stu-id="be650-113"><xref:Microsoft.ReportingServices.Interfaces.IExtension>, as well as <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>, are members of the <xref:Microsoft.ReportingServices.Interfaces> namespace.</span></span>  
  
 <span data-ttu-id="be650-114">Para autenticar con un servidor de informes en [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], se usa principalmente el método <xref:ReportService2010.ReportingService2010.LogonUser%2A>.</span><span class="sxs-lookup"><span data-stu-id="be650-114">The primary way to authenticate against a report server in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span> <span data-ttu-id="be650-115">Este miembro del servicio web de Reporting Services se puede utilizar con el objeto de pasar las credenciales del usuario a un servidor de informes para la validación.</span><span class="sxs-lookup"><span data-stu-id="be650-115">This member of the Reporting Services Web service can be used to pass user credentials to a report server for validation.</span></span> <span data-ttu-id="be650-116">La extensión de seguridad subyacente implementa **IAuthenticationExtension. LogonUser** , que contiene el código de autenticación personalizado.</span><span class="sxs-lookup"><span data-stu-id="be650-116">Your underlying security extension implements **IAuthenticationExtension.LogonUser** which contains your custom authentication code.</span></span> <span data-ttu-id="be650-117">En el ejemplo de autenticación de formularios, **LogonUser**, que realiza una comprobación de la autenticación contra las credenciales proporcionadas y un almacén de usuario personalizado en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="be650-117">In the Forms Authentication sample, **LogonUser**, which performs an authentication check against the supplied credentials and a custom user store in a database.</span></span> <span data-ttu-id="be650-118">Un ejemplo de implementación de **LogonUser** sería similar a:</span><span class="sxs-lookup"><span data-stu-id="be650-118">An example of an implementation of **LogonUser** looks like this:</span></span>  
  
```  
public bool LogonUser(string userName, string password, string authority)  
{  
   return AuthenticationUtilities.VerifyPassword(userName, password);  
}  
  
```  
  
 <span data-ttu-id="be650-119">La función de ejemplo siguiente se utiliza para comprobar las credenciales proporcionadas:</span><span class="sxs-lookup"><span data-stu-id="be650-119">The following sample function is used to verify the supplied credentials:</span></span>  
  
```  
  
internal static bool VerifyPassword(string suppliedUserName,  
   string suppliedPassword)  
{   
   bool passwordMatch = false;  
   // Get the salt and pwd from the database based on the user name.  
   // See "How To: Use DPAPI (Machine Store) from ASP.NET," "How To:  
   // Use DPAPI (User Store) from Enterprise Services," and "How To:  
   // Create a DPAPI Library" for more information about how to use  
   // DPAPI to securely store connection strings.  
   SqlConnection conn = new SqlConnection(  
      "Server=localhost;" +   
      "Integrated Security=SSPI;" +  
      "database=UserAccounts");  
   SqlCommand cmd = new SqlCommand("LookupUser", conn);  
   cmd.CommandType = CommandType.StoredProcedure;  
  
   SqlParameter sqlParam = cmd.Parameters.Add("@userName",  
       SqlDbType.VarChar,  
       255);  
   sqlParam.Value = suppliedUserName;  
   try  
   {  
      conn.Open();  
      SqlDataReader reader = cmd.ExecuteReader();  
      reader.Read(); // Advance to the one and only row  
      // Return output parameters from returned data stream  
      string dbPasswordHash = reader.GetString(0);  
      string salt = reader.GetString(1);  
      reader.Close();  
      // Now take the salt and the password entered by the user  
      // and concatenate them together.  
      string passwordAndSalt = String.Concat(suppliedPassword, salt);  
      // Now hash them  
      string hashedPasswordAndSalt =  
         FormsAuthentication.HashPasswordForStoringInConfigFile(  
         passwordAndSalt,  
         "SHA1");  
      // Now verify them. Returns true if they are equal.  
      passwordMatch = hashedPasswordAndSalt.Equals(dbPasswordHash);  
   }  
   catch (Exception ex)  
   {  
       throw new Exception("Exception verifying password. " +  
          ex.Message);  
   }  
   finally  
   {  
       conn.Close();  
   }  
   return passwordMatch;  
}  
```  
  
## <a name="authentication-flow"></a><span data-ttu-id="be650-120">Flujo de autenticación</span><span class="sxs-lookup"><span data-stu-id="be650-120">Authentication Flow</span></span>  
 <span data-ttu-id="be650-121">El servicio web de Reporting Services proporciona extensiones de autenticación personalizadas para habilitar la autenticación de formularios del Administrador de informes y el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="be650-121">The Reporting Services Web service provides custom authentication extensions to enable Forms Authentication by Report Manager and the report server.</span></span>  
  
 <span data-ttu-id="be650-122">El método <xref:ReportService2010.ReportingService2010.LogonUser%2A> del servicio web de Reporting Services se utiliza para enviar las credenciales al servidor de informes para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="be650-122">The <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of the Reporting Services Web service is used to submit credentials to the report server for authentication.</span></span> <span data-ttu-id="be650-123">El servicio web utiliza los encabezados HTTP para pasar un vale de autenticación (conocido como "cookie") del servidor al cliente para las solicitudes de inicio de sesión validadas.</span><span class="sxs-lookup"><span data-stu-id="be650-123">The Web service uses HTTP headers to pass an authentication ticket (known as a "cookie") from the server to the client for validated logon requests.</span></span>  
  
 <span data-ttu-id="be650-124">La ilustración siguiente describe el método para autenticar a los usuarios en el servicio web cuando la aplicación se implementa con un servidor de informes configurado para utilizar una extensión de autenticación personalizada.</span><span class="sxs-lookup"><span data-stu-id="be650-124">The following illustration depicts the method of authenticating users to the Web service when your application is deployed with a report server configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="be650-125">![Flujo de autenticación de seguridad de Reporting Services](../../media/rosettasecurityextensionauthenticationflow.gif "Flujo de autenticación de seguridad de Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="be650-125">![Reporting Services security authentication flow](../../media/rosettasecurityextensionauthenticationflow.gif "Reporting Services security authentication flow")</span></span>  
  
 <span data-ttu-id="be650-126">Como se muestra en la figura 2, el proceso de autenticación es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="be650-126">As shown in Figure 2, the authentication process is as follows:</span></span>  
  
1.  <span data-ttu-id="be650-127">Una aplicación cliente llama al método <xref:ReportService2010.ReportingService2010.LogonUser%2A> del servicio web para autenticar a un usuario.</span><span class="sxs-lookup"><span data-stu-id="be650-127">A client application calls the Web service <xref:ReportService2010.ReportingService2010.LogonUser%2A> method to authenticate a user.</span></span>  
  
2.  <span data-ttu-id="be650-128">El servicio Web realiza una llamada al <xref:ReportService2010.ReportingService2010.LogonUser%2A> método de la extensión de seguridad, específicamente, la clase que implementa **IAuthenticationExtension**.</span><span class="sxs-lookup"><span data-stu-id="be650-128">The Web service makes a call to the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of your security extension, specifically, the class that implements **IAuthenticationExtension**.</span></span>  
  
3.  <span data-ttu-id="be650-129">La implementación de <xref:ReportService2010.ReportingService2010.LogonUser%2A> valida el nombre de usuario y la contraseña en el almacén del usuario o la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="be650-129">Your implementation of <xref:ReportService2010.ReportingService2010.LogonUser%2A> validates the user name and password in the user store or security authority.</span></span>  
  
4.  <span data-ttu-id="be650-130">Tras una autenticación correcta, el servicio web crea una cookie y la administra para la sesión.</span><span class="sxs-lookup"><span data-stu-id="be650-130">Upon successful authentication, the Web service creates a cookie and manages it for the session.</span></span>  
  
5.  <span data-ttu-id="be650-131">El servicio web devuelve el vale de autenticación a la aplicación que realiza la llamada en el encabezado HTTP.</span><span class="sxs-lookup"><span data-stu-id="be650-131">The Web service returns the authentication ticket to the calling application on the HTTP header.</span></span>  
  
 <span data-ttu-id="be650-132">Cuando el servicio web autentica correctamente a un usuario a través de la extensión de seguridad, genera una cookie que se utiliza para las solicitudes subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="be650-132">When the Web service successfully authenticates a user through the security extension, it generates a cookie that is used for subsequent requests.</span></span> <span data-ttu-id="be650-133">La cookie puede no conservarse dentro de la entidad de seguridad personalizada porque el servidor de informes no posea la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="be650-133">The cookie may not persist within the custom security authority because the report server does not own the security authority.</span></span> <span data-ttu-id="be650-134">El método del servicio web <xref:ReportService2010.ReportingService2010.LogonUser%2A> devuelve la cookie y se utiliza en las siguientes llamadas al método de servicio web y en el acceso URL.</span><span class="sxs-lookup"><span data-stu-id="be650-134">The cookie is returned from the <xref:ReportService2010.ReportingService2010.LogonUser%2A> Web service method and is used in subsequent Web service method calls and in URL access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be650-135">Para evitar poner en peligro la cookie durante la transmisión, las cookies de autenticación que devuelve <xref:ReportService2010.ReportingService2010.LogonUser%2A> se deberían transmitir protegidas utilizando el cifrado de Capa de sockets seguros (SSL).</span><span class="sxs-lookup"><span data-stu-id="be650-135">In order to avoid compromising the cookie during transmission, authentication cookies returned from <xref:ReportService2010.ReportingService2010.LogonUser%2A> should be transmitted securely using Secure Sockets Layer (SSL) encryption.</span></span>  
  
 <span data-ttu-id="be650-136">Si tiene acceso al servidor de informes a través del acceso URL cuando se instala una extensión de seguridad personalizada, Internet Information Services (IIS) y [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] administran automáticamente la transmisión del vale de autenticación.</span><span class="sxs-lookup"><span data-stu-id="be650-136">If you access the report server through URL access when a custom security extension is installed, Internet Information Services (IIS) and [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] automatically manage the transmission of the authentication ticket.</span></span> <span data-ttu-id="be650-137">Si va a tener acceso al servidor de informes a través de la API SOAP, la implementación de la clase de proxy debe incluir compatibilidad adicional para administrar el vale de autenticación.</span><span class="sxs-lookup"><span data-stu-id="be650-137">If you are accessing the report server through the SOAP API, your implementation of the proxy class must include additional support for managing the authentication ticket.</span></span> <span data-ttu-id="be650-138">Para obtener más información sobre cómo utilizar la API SOAP y administrar el vale de autenticación, vea "Usar el servicio web con seguridad personalizada".</span><span class="sxs-lookup"><span data-stu-id="be650-138">For more information about using the SOAP API and managing the authentication ticket, see "Using the Web Service with Custom Security."</span></span>  
  
## <a name="forms-authentication"></a><span data-ttu-id="be650-139">Autenticación de formularios</span><span class="sxs-lookup"><span data-stu-id="be650-139">Forms Authentication</span></span>  
 <span data-ttu-id="be650-140">La autenticación de formularios es un tipo de autenticación de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] en la que un usuario no autenticado se dirige a un formulario HTML.</span><span class="sxs-lookup"><span data-stu-id="be650-140">Forms Authentication is a type of [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in which an unauthenticated user is directed to an HTML form.</span></span> <span data-ttu-id="be650-141">Cuando el usuario proporciona las credenciales, el sistema emite una cookie que contiene un vale de autenticación.</span><span class="sxs-lookup"><span data-stu-id="be650-141">Once the user provides credentials, the system issues a cookie containing an authentication ticket.</span></span> <span data-ttu-id="be650-142">En las solicitudes posteriores, el sistema comprueba primero la cookie para ver si el servidor de informes autenticó ya al usuario.</span><span class="sxs-lookup"><span data-stu-id="be650-142">On later requests, the system first checks the cookie to see if the user was already authenticated by the report server.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="be650-143">se puede extender para admitir la autenticación de formularios utilizando las interfaces de extensibilidad de seguridad disponibles a través de la API de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="be650-143">can be extended to support Forms Authentication using the security extensibility interfaces available through the Reporting Services API.</span></span> <span data-ttu-id="be650-144">Si extiende [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] para utilizar la autenticación de formularios, utilice Capa de sockets seguros (SSL) para todas las comunicaciones con el servidor de informes, con el fin de evitar que los usuarios malintencionados obtengan acceso a la cookie de otro usuario.</span><span class="sxs-lookup"><span data-stu-id="be650-144">If you extend [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to use Forms Authentication, use Secure Sockets Layer (SSL) for all communications with the report server to prevent malicious users from gaining access to another user's cookie.</span></span> <span data-ttu-id="be650-145">SSL permite que los clientes y un servidor de informes se autentiquen entre sí y asegurarse de que ningún otro equipo pueda leer el contenido de las comunicaciones entre los dos equipos.</span><span class="sxs-lookup"><span data-stu-id="be650-145">SSL enables clients and a report server to authenticate each other and to ensure that no other computers can read the contents of communications between the two computers.</span></span> <span data-ttu-id="be650-146">Todos los datos enviados desde un cliente a través de una conexión SSL se cifran para que los usuarios malintencionados no puedan interceptar las contraseñas o los datos que se envían a un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="be650-146">All data sent from a client through an SSL connection is encrypted so that malicious users cannot intercept passwords or data sent to a report server.</span></span>  
  
 <span data-ttu-id="be650-147">La autenticación de formularios se implementa generalmente para admitir cuentas y la autenticación para plataformas distintas de Windows.</span><span class="sxs-lookup"><span data-stu-id="be650-147">Forms Authentication is generally implemented to support accounts and authentication for platforms other than Windows.</span></span> <span data-ttu-id="be650-148">Cuando un usuario solicita acceso a un servidor de informes, se presenta una interfaz gráfica y las credenciales proporcionadas se envían a una entidad de seguridad para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="be650-148">A graphical interface is presented to a user who requests access to a report server, and the supplied credentials are submitted to a security authority for authentication.</span></span>  
  
 <span data-ttu-id="be650-149">La autenticación de formularios requiere que una persona esté presente para escribir las credenciales.</span><span class="sxs-lookup"><span data-stu-id="be650-149">Forms Authentication requires that a person is present to enter credentials.</span></span> <span data-ttu-id="be650-150">En las aplicaciones desatendidas que se comunican directamente con el servicio web de Reporting Services, la autenticación de formularios se debe combinar con un esquema de autenticación personalizada.</span><span class="sxs-lookup"><span data-stu-id="be650-150">For unattended applications that communicate directly with the Reporting Services Web service, Forms Authentication must be combined with a custom authentication scheme.</span></span>  
  
 <span data-ttu-id="be650-151">La autenticación de formularios es adecuada para [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] cuando:</span><span class="sxs-lookup"><span data-stu-id="be650-151">Forms Authentication is appropriate for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] when:</span></span>  
  
-   <span data-ttu-id="be650-152">Necesita almacenar y autenticar a los usuarios que no tienen cuentas de Windows de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] y</span><span class="sxs-lookup"><span data-stu-id="be650-152">You need to store and authenticate users that do not have [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows accounts, and</span></span>  
  
-   <span data-ttu-id="be650-153">Necesita proporcionar su propio formulario de interfaz de usuario como una página de inicio de sesión entre las diferentes páginas de un sitio web.</span><span class="sxs-lookup"><span data-stu-id="be650-153">You need to provide your own user interface form as a logon page between different pages on a Web site.</span></span>  
  
 <span data-ttu-id="be650-154">Considere lo siguiente al escribir una extensión de seguridad personalizada que admita la autenticación de formularios:</span><span class="sxs-lookup"><span data-stu-id="be650-154">Consider the following when writing a custom security extension that supports Forms Authentication:</span></span>  
  
-   <span data-ttu-id="be650-155">Si utiliza la autenticación de formularios, el acceso anónimo debe habilitarse en el directorio virtual del servidor de informes en Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="be650-155">If you use Forms Authentication, anonymous access must be enabled on the report server virtual directory in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="be650-156">La autenticación de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] debe establecerse en la autenticación de formularios.</span><span class="sxs-lookup"><span data-stu-id="be650-156">[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication must be set to Forms.</span></span> <span data-ttu-id="be650-157">La autenticación de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] se configura en el archivo Web.config para el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="be650-157">You configure [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in the Web.config file for the report server.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="be650-158">puede autenticar y autorizar a los usuarios con la autenticación de Windows o la autenticación personalizada, pero no con ambos.</span><span class="sxs-lookup"><span data-stu-id="be650-158">can authenticate and authorize users with either Windows Authentication or custom authentication, but not both.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="be650-159">no admite el uso simultáneo de varias extensiones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="be650-159">does not support simultaneous use of multiple security extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be650-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be650-160">See Also</span></span>  
 [<span data-ttu-id="be650-161">Implementación de una extensión de seguridad</span><span class="sxs-lookup"><span data-stu-id="be650-161">Implementing a Security Extension</span></span>](../security-extension/implementing-a-security-extension.md)  
  
  
