---
title: Metodologías de autenticación admitidas por Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b7aee903-d33a-4c20-86c2-aa013a50949f
author: minewiskan
ms.author: owend
ms.openlocfilehash: e3ce8dfc47b2c57fcc8ae336160ff81f87a8a157
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673391"
---
# <a name="authentication-methodologies-supported-by-analysis-services"></a><span data-ttu-id="1e6ac-102">Metodologías de autenticación admitidas por Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1e6ac-102">Authentication methodologies supported by Analysis Services</span></span>
  <span data-ttu-id="1e6ac-103">Las conexiones desde una aplicación cliente a una instancia de Analysis Services requieren la autenticación de Windows (integrada).</span><span class="sxs-lookup"><span data-stu-id="1e6ac-103">Connections from a client application to an Analysis Services instance require Windows authentication (integrated).</span></span> <span data-ttu-id="1e6ac-104">Puede proporcionar una identidad de usuario de Windows mediante cualquiera de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1e6ac-104">You can provide a Windows user identity using any of the following methods:</span></span>  
  
-   <span data-ttu-id="1e6ac-105">NTLM</span><span class="sxs-lookup"><span data-stu-id="1e6ac-105">NTLM</span></span>  
  
-   <span data-ttu-id="1e6ac-106">Kerberos (vea [Configurar Analysis Services para la delegación restringida de Kerberos](configure-analysis-services-for-kerberos-constrained-delegation.md))</span><span class="sxs-lookup"><span data-stu-id="1e6ac-106">Kerberos (see [Configure Analysis Services for Kerberos constrained delegation](configure-analysis-services-for-kerberos-constrained-delegation.md))</span></span>  
  
-   <span data-ttu-id="1e6ac-107">EffectiveUserName en la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="1e6ac-107">EffectiveUserName on the connection string</span></span>  
  
-   <span data-ttu-id="1e6ac-108">Básica o Anónima (necesita la configuración para acceso HTTP)</span><span class="sxs-lookup"><span data-stu-id="1e6ac-108">Basic or Anonymous (requires configuration for HTTP access)</span></span>  
  
-   <span data-ttu-id="1e6ac-109">Credenciales almacenadas</span><span class="sxs-lookup"><span data-stu-id="1e6ac-109">Stored credentials</span></span>  
  
 <span data-ttu-id="1e6ac-110">Tenga en cuenta que la autenticación de notificaciones no se admite.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-110">Notice that Claims authentication is not supported.</span></span> <span data-ttu-id="1e6ac-111">No puede usar un token de notificaciones de Windows para tener acceso a Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-111">You cannot use a Windows Claims token to access Analysis Services.</span></span> <span data-ttu-id="1e6ac-112">Las bibliotecas de cliente de Analysis Services solo funcionan con entidades de seguridad de Windows.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-112">The Analysis Services client libraries only work with Windows security principles.</span></span> <span data-ttu-id="1e6ac-113">Si la solución de BI incluye identidades de notificaciones, necesitará cuentas sombra de identidad de Windows para cada usuario o tendrá que usar credenciales almacenadas para tener acceso a los datos de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-113">If your BI solution includes claims identities, you will need Windows identity shadow accounts for each user, or use stored credentials to access Analysis Services data.</span></span>  
  
 <span data-ttu-id="1e6ac-114">Para obtener más información sobre BI y los flujos de autenticación de Analysis Services, vea [Autenticación y delegación de identidad de Microsoft BI](https://go.microsoft.com/fwlink/?LinkID=286576).</span><span class="sxs-lookup"><span data-stu-id="1e6ac-114">For more information about BI and Analysis Services authentication flows, see [Microsoft BI Authentication and Identity Delegation](https://go.microsoft.com/fwlink/?LinkID=286576).</span></span>  
  
##  <a name="understanding-your-authentication-alternatives"></a><a name="bkmk_auth"></a> <span data-ttu-id="1e6ac-115">Descripción de las alternativas de autenticación</span><span class="sxs-lookup"><span data-stu-id="1e6ac-115">Understanding your authentication alternatives</span></span>  
 <span data-ttu-id="1e6ac-116">La conexión a una base de datos de Analysis Services requiere una identidad de usuario o grupo de Windows y permisos asociados.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-116">Connecting to an Analysis Services database requires a Windows user or group identity and associated permissions.</span></span> <span data-ttu-id="1e6ac-117">La identidad puede ser un inicio de sesión de propósito general usado por alguien que necesite consultar un informe, pero lo más probable es que incluya la identidad de usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-117">The identity might be a general purpose login used by anyone who needs to view a report, but a more likely scenario includes the identity of individual users.</span></span>  
  
 <span data-ttu-id="1e6ac-118">A menudo, los modelos multidimensionales o tabulares tendrán diferentes niveles de acceso a los datos, por objeto o bien dentro de los propios datos, en función de quién realice la solicitud.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-118">Often, a tabular or multidimensional model will have different levels of data access, by object or within the data itself, based on who is making the request.</span></span> <span data-ttu-id="1e6ac-119">Para satisfacer este requisito, puede usar la autenticación NTLM, Kerberos, EffectiveUserName o Básica.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-119">To meet this requirement, you can use NTLM, Kerberos, EffectiveUserName, or Basic authentication.</span></span> <span data-ttu-id="1e6ac-120">Todas estas técnicas ofrecen distintas posibilidades de pasar diferentes identidades de usuario con cada conexión.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-120">All of these techniques offer an approach for passing in different user identities with each connection.</span></span> <span data-ttu-id="1e6ac-121">Sin embargo, la mayoría de estas opciones están sujetas a la limitación de un solo salto.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-121">However, most of these choices are subject to a single hop limitation.</span></span> <span data-ttu-id="1e6ac-122">Solo Kerberos con delegación permite que la identidad de usuario original circule a través de conexiones entre varios equipos hasta un almacén de datos back-end en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-122">Only Kerberos with delegation allows the original user identity to flow across multiple computer connections to a backend data store on a remote server.</span></span>  
  
 <span data-ttu-id="1e6ac-123">**NTLM**</span><span class="sxs-lookup"><span data-stu-id="1e6ac-123">**NTLM**</span></span>  
  
 <span data-ttu-id="1e6ac-124">Para las conexiones que especifican `SSPI=Negotiate`, NTLM es el subsistema de autenticación de reserva que se usa cuando un controlador de dominio Kerberos no está disponible.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-124">For connections that specify `SSPI=Negotiate`, NTLM is the backup authentication subsystem used when a Kerberos domain controller is not available.</span></span> <span data-ttu-id="1e6ac-125">En NTLM, cualquier usuario o aplicación cliente puede obtener acceso a un recurso del servidor siempre y cuando la solicitud sea una conexión directa del cliente al servidor, la persona que solicita la conexión tenga permiso en el recurso, y los equipos cliente y servidor se encuentren en el mismo dominio.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-125">Under NTLM, any user or client application can access a server resource as long as the request is a direct connection from a client to the server, the person requesting the connection has permission to the resource, and the client and server computers are in the same domain.</span></span>  
  
 <span data-ttu-id="1e6ac-126">En las soluciones de varios niveles, la restricción de un solo salto de NLTM puede suponer un obstáculo importante.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-126">In multi-tier solutions, the single hop restriction of NLTM can be a major constraint.</span></span> <span data-ttu-id="1e6ac-127">La identidad del usuario que realiza la solicitud se puede suplantar en exactamente un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-127">The user identity making the request can be impersonated on exactly one remote server, but travels no further.</span></span> <span data-ttu-id="1e6ac-128">Si la operación actual requiere que los servicios se ejecuten en varios equipos, deberá configurar la delegación restringida de Kerberos de modo que reutilice el token de seguridad en servidores back-end.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-128">If the current operation requires services running on multiple computers, you will need to configure Kerberos constrained delegation to reuse the security token on backend servers.</span></span> <span data-ttu-id="1e6ac-129">Como alternativa puede usar las credenciales almacenadas o la autenticación básica para pasar nueva información de identidad a través de una conexión de un solo salto.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-129">Alternatively, you can use stored credentials or Basic authentication to pass in new identity information over a single hop connection.</span></span>  
  
 <span data-ttu-id="1e6ac-130">**Autenticación Kerberos y delegación restringida de Kerberos**</span><span class="sxs-lookup"><span data-stu-id="1e6ac-130">**Kerberos Authentication and Kerberos Constrained Delegation**</span></span>  
  
 <span data-ttu-id="1e6ac-131">La autenticación Kerberos es la base de la seguridad integrada de Windows en los dominios de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-131">Kerberos authentication is the basis of Windows integrated security in Active Directory domains.</span></span> <span data-ttu-id="1e6ac-132">Como con NTLM, la suplantación en Kerberos está limitada a un solo salto, a no ser se que habilite la delegación.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-132">As with NTLM, impersonation under Kerberos is limited to a single hop unless you enable delegation.</span></span>  
  
 <span data-ttu-id="1e6ac-133">Para admitir las conexiones de varios saltos, Kerberos proporciona la delegación restringida y no restringida, pero en la mayoría de los casos es preferible usar la delegación restringida porque es más segura.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-133">To support multi-hop connections, Kerberos provides both constrained and unconstrained delegation, but for most scenarios, constrained delegation is considered a security best practice.</span></span> <span data-ttu-id="1e6ac-134">La delegación restringida permite que un servicio pueda pasar el token de seguridad de la identidad del usuario a un servicio de nivel inferior en un servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-134">Constrained delegation allows a service to pass the security token of the user identity to a designated down-level service on a remote computer.</span></span> <span data-ttu-id="1e6ac-135">Para las aplicaciones de varios niveles, la delegación de la identidad de un usuario desde un servidor de aplicación de nivel intermedio a un servidor back-end como Analysis Services es un proceso habitual.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-135">For multi-tier applications, delegating a user identity from a middle tier application server to a backend database such as Analysis Services is a common requirement.</span></span> <span data-ttu-id="1e6ac-136">Por ejemplo, un modelo tabular o multidimensional que devuelve datos diferentes en función de la identidad del usuario necesitará la delegación de identidad de un servicio de nivel intermedio para evitar que el usuario tenga que volver a especificar las credenciales, u obtener credenciales de seguridad de algún otro modo.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-136">For example, a tabular or multidimensional model that returns different data based on user identity would require identity delegation from a middle tier service to avoid having the user re-enter credentials, or getting security credentials some other way.</span></span>  
  
 <span data-ttu-id="1e6ac-137">Para la delegación restringida es necesario realizar una configuración adicional en Active Directory, donde los servicios tanto en el lado emisor como en el receptor de la solicitud están explícitamente autorizados para la delegación.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-137">Constrained delegation requires additional configuration in Active Directory, where services on both the sending and receiving end of the request are explicitly authorized for delegation.</span></span> <span data-ttu-id="1e6ac-138">Aunque inicialmente la configuración puede resultar costosa, una vez que el servicio está configurado las actualizaciones de contraseña se administran de forma independiente en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-138">Although there are configuration costs up front, once the service is configured, password updates are managed independently in Active Directory.</span></span> <span data-ttu-id="1e6ac-139">No es necesario que actualice la información de cuenta almacenada en las aplicaciones, a diferencia de cuando se utiliza la opción de credenciales almacenadas que se describe más adelante.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-139">You do not need to update stored account information in applications, as you would if using the stored credentials option described further on.</span></span>  
  
 <span data-ttu-id="1e6ac-140">Para obtener más información acerca de la configuración de Analysis Services para la delegación restringida, vea [Configure Analysis Services for Kerberos constrained delegation](configure-analysis-services-for-kerberos-constrained-delegation.md).</span><span class="sxs-lookup"><span data-stu-id="1e6ac-140">For more information about configuring Analysis Services for constrained delegation, see [Configure Analysis Services for Kerberos constrained delegation](configure-analysis-services-for-kerberos-constrained-delegation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1e6ac-141">Windows Server 2012 admite la delegación restringida entre dominios.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-141">Windows Server 2012 supports constrained delegation across domains.</span></span> <span data-ttu-id="1e6ac-142">En cambio, para la configuración de la delegación restringida de Kerberos en dominios a niveles funcionales inferiores, como Windows Server 2008 o 2008 R2, es preciso que tanto los equipos cliente como servidor sean miembros del mismo dominio.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-142">In contrast, configuring Kerberos constrained delegation in domains at lower functional levels, such as Windows Server 2008 or 2008 R2, require both client and server computers to be members of the same domain.</span></span>  
  
 <span data-ttu-id="1e6ac-143">**EffectiveUserName**</span><span class="sxs-lookup"><span data-stu-id="1e6ac-143">**EffectiveUserName**</span></span>  
  
 <span data-ttu-id="1e6ac-144">EffectiveUserName es una propiedad de cadena de conexión usada para pasar la información de identidad a Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-144">EffectiveUserName is a connection string property used for passing identity information to Analysis Services.</span></span> <span data-ttu-id="1e6ac-145">PowerPivot para SharePoint la usa para registrar la actividad de los usuarios en los registros de uso.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-145">PowerPivot for SharePoint uses it to record user activity in the usage logs.</span></span> <span data-ttu-id="1e6ac-146">Excel Services y PerformancePoint Services la pueden usar para recuperar los datos empleados por los libros o paneles en SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-146">Excel Services and PerformancePoint Services can use it to retrieve data used by workbooks or dashboards in SharePoint.</span></span> <span data-ttu-id="1e6ac-147">También puede usarse en aplicaciones o scripts personalizados que ejecutan operaciones en una instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-147">It can also be used in custom applications or scripts that perform operations on an Analysis Services instance.</span></span>  
  
 <span data-ttu-id="1e6ac-148">Para obtener más información acerca del uso de EffectiveUserName en SharePoint, vea [Usar EffectiveUserName de Analysis Services en SharePoint Server 2010](https://go.microsoft.com/fwlink/?LinkId=311905).</span><span class="sxs-lookup"><span data-stu-id="1e6ac-148">For more information about using EffectiveUserName in SharePoint, see [Use Analysis Services EffectiveUserName in SharePoint Server 2010](https://go.microsoft.com/fwlink/?LinkId=311905).</span></span>  
  
 <span data-ttu-id="1e6ac-149">**Autenticación básica y usuario anónimo**</span><span class="sxs-lookup"><span data-stu-id="1e6ac-149">**Basic Authentication and Anonymous User**</span></span>  
  
 <span data-ttu-id="1e6ac-150">La autenticación básica ofrece una cuarta alternativa para la conexión a un servidor back-end como un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-150">Basic authentication provides yet a fourth alternative for connecting to a backend server as a specific user.</span></span> <span data-ttu-id="1e6ac-151">Con la autenticación básica, el nombre de usuario y la contraseña de Windows se pasan a la cadena de conexión, que incluye requisitos de cifrado de cable adicional para garantizar que la información confidencial está protegida durante el envío.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-151">Using Basic authentication, the Windows user name and password are passed on the connection string, introducing additional wire encryption requirements to ensure sensitive information is protected while in transit.</span></span> <span data-ttu-id="1e6ac-152">Una ventaja importante que ofrece la autenticación básica es que la solicitud de autenticación puede cruzar los límites de los dominios.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-152">An important advantage to using Basic authentication is that the authentication request can cross domain boundaries.</span></span>  
  
 <span data-ttu-id="1e6ac-153">Para la autenticación Anónima, puede establecer la identidad de usuario anónima en una cuenta de usuario de Windows concreta (IUSR_GUEST de forma predeterminada) o en una identidad de grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-153">For Anonymous authentication, you can set the anonymous user identity to a specific Windows user account (IUSR_GUEST by default) or an application pool identity.</span></span> <span data-ttu-id="1e6ac-154">La cuenta de usuario anónima se usará en la conexión de Analysis Services y debe tener permisos de acceso a datos en la instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-154">The anonymous user account will be used on the Analysis Services connection, and must have data access permissions on the Analysis Services instance.</span></span> <span data-ttu-id="1e6ac-155">Si utiliza este método, en la conexión solo se utiliza la identidad de usuario asociada a la cuenta anónima.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-155">When you use this approach, only the user identity associated with the Anonymous account is used on the connection.</span></span> <span data-ttu-id="1e6ac-156">Si su aplicación precisa de una administración de identidades adicional, deberá elegir uno de los otros métodos, o bien complementar la aplicación con una solución de administración de identidades propia.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-156">If your application requires additional identity management, you will need to choose one of the other approaches, or supplement with an identity management solution that you provide.</span></span>  
  
 <span data-ttu-id="1e6ac-157">Básica y Anónima solo están disponibles al configurar Analysis Services para acceso HTTP con el uso de IIS y msmdpump.dll para establecer la conexión.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-157">Basic and Anonymous are available only when you configure Analysis Services for HTTP access, using IIS and the msmdpump.dll to establish the connection.</span></span> <span data-ttu-id="1e6ac-158">Para obtener más información, vea [Configurar el acceso HTTP a Analysis Services en Internet Information Services &#40;IIS&#41; 8.0](configure-http-access-to-analysis-services-on-iis-8-0.md).</span><span class="sxs-lookup"><span data-stu-id="1e6ac-158">For more information, see [Configure HTTP Access to Analysis Services on Internet Information Services &#40;IIS&#41; 8.0](configure-http-access-to-analysis-services-on-iis-8-0.md).</span></span>  
  
 <span data-ttu-id="1e6ac-159">**Credenciales almacenadas**</span><span class="sxs-lookup"><span data-stu-id="1e6ac-159">**Stored Credentials**</span></span>  
  
 <span data-ttu-id="1e6ac-160">La mayoría de servicios de aplicación de nivel intermedio incluyen la funcionalidad para almacenar un nombre de usuario y una contraseña que posteriormente se usarán para recuperar datos de un almacén de datos de nivel inferior, como Analysis Services o el motor relacional de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-160">Most middle tier application services include functionality for storing a user name and password subsequently used to retrieve data from a down-level data store, such as Analysis Services or the SQL Server relational engine.</span></span> <span data-ttu-id="1e6ac-161">En sí, las credenciales almacenadas ofrecen una quinta alternativa para recuperar datos.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-161">As such, stored credentials provide a fifth alternative for retrieving data.</span></span> <span data-ttu-id="1e6ac-162">Entre las limitaciones inherentes a este método se incluye la sobrecarga de mantenimiento asociada con la actualización de los nombres de usuario y las contraseñas, y el uso de una sola identidad en la conexión.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-162">Limitations with this approach include maintenance overhead associated with keeping user names and passwords up to date, and the use of a single identity on the connection.</span></span> <span data-ttu-id="1e6ac-163">Si su solución precisa de la identidad del autor de la llamada original, las credenciales almacenadas no serían una alternativa viable.</span><span class="sxs-lookup"><span data-stu-id="1e6ac-163">If your solution requires the identity of the original caller, then stored credentials would not be a viable alternative.</span></span>  
  
 <span data-ttu-id="1e6ac-164">Para obtener más información sobre las credenciales almacenadas, vea [Crear, modificar y eliminar orígenes de datos compartidos &#40;SSRS&#41;](../../reporting-services/report-data/create-modify-and-delete-shared-data-sources-ssrs.md) y [Usar Servicios de Excel con el Servicio de almacenamiento seguro en SharePoint Server 2013](https://go.microsoft.com/fwlink/?LinkID=309869).</span><span class="sxs-lookup"><span data-stu-id="1e6ac-164">For more information about stored credentials, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](../../reporting-services/report-data/create-modify-and-delete-shared-data-sources-ssrs.md) and [Use Excel Services with Secure Store Service in SharePoint Server 2013](https://go.microsoft.com/fwlink/?LinkID=309869).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e6ac-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e6ac-165">See Also</span></span>  
 <span data-ttu-id="1e6ac-166">[Usar la suplantación con la seguridad de transporte](https://go.microsoft.com/fwlink/?LinkId=311727) </span><span class="sxs-lookup"><span data-stu-id="1e6ac-166">[Using Impersonation with Transport Security](https://go.microsoft.com/fwlink/?LinkId=311727) </span></span>  
 <span data-ttu-id="1e6ac-167">[Configurar el acceso HTTP a Analysis Services en Internet Information Services &#40;IIS&#41; 8,0](configure-http-access-to-analysis-services-on-iis-8-0.md) </span><span class="sxs-lookup"><span data-stu-id="1e6ac-167">[Configure HTTP Access to Analysis Services on Internet Information Services &#40;IIS&#41; 8.0](configure-http-access-to-analysis-services-on-iis-8-0.md) </span></span>  
 <span data-ttu-id="1e6ac-168">[Configurar Analysis Services para la delegación restringida de Kerberos](configure-analysis-services-for-kerberos-constrained-delegation.md) </span><span class="sxs-lookup"><span data-stu-id="1e6ac-168">[Configure Analysis Services for Kerberos constrained delegation](configure-analysis-services-for-kerberos-constrained-delegation.md) </span></span>  
 <span data-ttu-id="1e6ac-169">[Registro de SPN para una instancia de Analysis Services](spn-registration-for-an-analysis-services-instance.md) </span><span class="sxs-lookup"><span data-stu-id="1e6ac-169">[SPN registration for an Analysis Services instance](spn-registration-for-an-analysis-services-instance.md) </span></span>  
 [<span data-ttu-id="1e6ac-170">Conectar a Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1e6ac-170">Connect to Analysis Services</span></span>](connect-to-analysis-services.md)  
  
  