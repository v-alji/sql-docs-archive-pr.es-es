---
title: Registrar un nombre de entidad de seguridad de servicio (SPN) para un servidor de informes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dda91d4f-77cc-4898-ad03-810ece5f8e74
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 502170f16aad66757e8f44419ccbac3017072449
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677426"
---
# <a name="register-a-service-principal-name-spn-for-a-report-server"></a><span data-ttu-id="a1e6b-102">Registrar un nombre principal de servicio (SPN) para un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="a1e6b-102">Register a Service Principal Name (SPN) for a Report Server</span></span>
  <span data-ttu-id="a1e6b-103">Si está implementando [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en una red que usa el protocolo Kerberos para la autenticación mutua, debe crear un nombre principal de servicio (SPN) para el servicio Servidor de informes si lo configura para que se ejecute como una cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-103">If you are deploying [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in a network that uses the Kerberos protocol for mutual authentication, you must create a Service Principal Name (SPN) for the Report Server service if you configure it to run as a domain user account.</span></span>  
  
## <a name="about-spns"></a><span data-ttu-id="a1e6b-104">Acerca de los nombres principales de servicio</span><span class="sxs-lookup"><span data-stu-id="a1e6b-104">About SPNs</span></span>  
 <span data-ttu-id="a1e6b-105">Un SPN es un identificador único para un servicio en una red que utiliza la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-105">An SPN is a unique identifier for a service on a network that uses Kerberos authentication.</span></span> <span data-ttu-id="a1e6b-106">Está compuesto de una clase de servicio, un nombre de host y un puerto.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-106">It consists of a service class, a host name, and a port.</span></span> <span data-ttu-id="a1e6b-107">En una red que utiliza la autenticación Kerberos, un SPN para el servidor se debe registrar en una cuenta de equipo integrada (como NetworkService o LocalSystem) o en una cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-107">On a network that uses Kerberos authentication, an SPN for the server must be registered under either a built-in computer account (such as NetworkService or LocalSystem) or user account.</span></span> <span data-ttu-id="a1e6b-108">Los SPN se registran automáticamente para las cuentas integradas.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-108">SPNs are registered for built-in accounts automatically.</span></span> <span data-ttu-id="a1e6b-109">Sin embargo, al ejecutar un servicio en una cuenta de usuario de dominio, debe registrar manualmente el SPN para la cuenta que desea utilizar.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-109">However, when you run a service under a domain user account, you must manually register the SPN for the account you want to use.</span></span>  
  
 <span data-ttu-id="a1e6b-110">Para crear un SPN, puede emplear la utilidad de línea de comandos **SetSPN** .</span><span class="sxs-lookup"><span data-stu-id="a1e6b-110">To create an SPN, you can use the **SetSPN** command line utility.</span></span> <span data-ttu-id="a1e6b-111">Para obtener más información, vea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1e6b-111">For more information, see the following:</span></span>  
  
-   <span data-ttu-id="a1e6b-112">[Setspn](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) ( https://technet.microsoft.com/library/cc731241(WS.10).aspx) .</span><span class="sxs-lookup"><span data-stu-id="a1e6b-112">[Setspn](https://technet.microsoft.com/library/cc731241\(WS.10\).aspx) (https://technet.microsoft.com/library/cc731241(WS.10).aspx).</span></span>  
  
-   <span data-ttu-id="a1e6b-113">[Sintaxis de los nombres de entidad de seguridad de servicio (SPN) setspn (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) ( https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) .</span><span class="sxs-lookup"><span data-stu-id="a1e6b-113">[Service Principal Names (SPNs) SetSPN Syntax (Setspn.exe)](https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx) (https://social.technet.microsoft.com/wiki/contents/articles/717.service-principal-names-spns-setspn-syntax-setspn-exe.aspx).</span></span>  
  
 <span data-ttu-id="a1e6b-114">Debe ser administrador de dominio si desea ejecutar la utilidad en el controlador de dominio.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-114">You must be a domain administrator to run the utility on the domain controller.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1e6b-115">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1e6b-115">Syntax</span></span>  
 <span data-ttu-id="a1e6b-116">La sintaxis de comandos para utilizar la utilidad SetSPN con el fin de crear un SPN para el servidor de informes es similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="a1e6b-116">The command syntax for using SetSPN utility to create an SPN for the report server resembles the following:</span></span>  
  
```  
Setspn -s http/<computername>.<domainname>:<port> <domain-user-account>  
```  
  
 <span data-ttu-id="a1e6b-117">**SetSPN** está disponible con Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-117">**SetSPN** is available with Windows Server.</span></span> <span data-ttu-id="a1e6b-118">El argumento `-s` agrega un SPN después de validar que no existe ningún duplicado.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-118">The `-s` argument adds a SPN after validating no duplicate exists.</span></span> <span data-ttu-id="a1e6b-119">**NOTA: -s** está disponible en Windows Server a partir de Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-119">**NOTE:-s** is available in Windows Server starting with Windows Server 2008.</span></span>  
  
 <span data-ttu-id="a1e6b-120">`HTTP` es la clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-120">`HTTP` is the service class.</span></span> <span data-ttu-id="a1e6b-121">El servicio web del servidor de informes se ejecuta en HTTP.SYS.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-121">The Report Server Web service runs in HTTP.SYS.</span></span> <span data-ttu-id="a1e6b-122">Una consecuencia de la creación de un SPN para HTTP es que a todas las aplicaciones web del mismo equipo que se ejecutan en HTTP.SYS (incluidas las que se hospedan en IIS) se les concederán vales en función de la cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-122">A by-product of creating an SPN for HTTP is that all Web applications on the same computer that run in HTTP.SYS (including applications hosted in IIS) will be granted tickets based on the domain user account.</span></span> <span data-ttu-id="a1e6b-123">Si esos servicios se ejecutan en una cuenta diferente, se producirá un error en las solicitudes de autenticación.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-123">If those services run under a different account, the authentication requests will fail.</span></span> <span data-ttu-id="a1e6b-124">Para evitar este problema, asegúrese de configurar todas las aplicaciones HTTP para ejecutarse en la misma cuenta, o considere la posibilidad de crear los encabezados de host para cada aplicación y crear después SPN independientes para cada encabezado de host.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-124">To avoid this problem, be sure to configure all HTTP applications to run under the same account, or consider creating host headers for each application and then creating separate SPNs for each host header.</span></span> <span data-ttu-id="a1e6b-125">Al configurar los encabezados de host, se requieren cambios de DNS con independencia de la configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a1e6b-125">When you configure host headers, DNS changes are required regardless of the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration.</span></span>  
  
 <span data-ttu-id="a1e6b-126">Los valores que se especifican para \<*computername*> , \<*domainname*> e \<*port*> identifican la dirección de red única del equipo que hospeda el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-126">The values that you specify for \<*computername*>, \<*domainname*>, and \<*port*> identify the unique network address of the computer that hosts the report server.</span></span> <span data-ttu-id="a1e6b-127">Puede ser un nombre de host local o un nombre de dominio completo (FQDN).</span><span class="sxs-lookup"><span data-stu-id="a1e6b-127">This can be a local host name or a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="a1e6b-128">Si solo tiene un dominio y usa el puerto 80, puede omitir \<*domainname*> y \<*port*> desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-128">If you only have one domain and are using port 80, you can omit \<*domainname*> and \<*port*> from your command line.</span></span> <span data-ttu-id="a1e6b-129">\<*domain-user-account*>es la cuenta de usuario con la que se ejecuta el servicio del servidor de informes y para la que se debe registrar el SPN.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-129">\<*domain-user-account*> is the user account under which the Report Server service runs and for which the SPN must be registered.</span></span>  
  
## <a name="register-an-spn-for-domain-user-account"></a><span data-ttu-id="a1e6b-130">Registrar un nombre principal de servicio para la cuenta de usuario de dominio</span><span class="sxs-lookup"><span data-stu-id="a1e6b-130">Register an SPN for Domain User Account</span></span>  
  
#### <a name="to-register-an-spn-for-a-report-server-service-running-as-a-domain-user"></a><span data-ttu-id="a1e6b-131">Para registrar un SPN para un servicio Servidor de informes que se ejecute como un usuario de dominio</span><span class="sxs-lookup"><span data-stu-id="a1e6b-131">To register an SPN for a Report Server service running as a domain user</span></span>  
  
1.  <span data-ttu-id="a1e6b-132">Instale [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y configure el servicio Servidor de informes para ejecutarse como una cuenta de usuario de dominio.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-132">Install [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and configure the Report Server service to run as a domain user account.</span></span> <span data-ttu-id="a1e6b-133">Observe que los usuarios no podrán conectarse al servidor de informes hasta que complete los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-133">Note that users will not be able to connect to the report server until you complete the following steps.</span></span>  
  
2.  <span data-ttu-id="a1e6b-134">Inicie sesión en el controlador de dominio como administrador de dominio.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-134">Log on to the domain controller as domain administrator.</span></span>  
  
3.  <span data-ttu-id="a1e6b-135">Abra una ventana de símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-135">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="a1e6b-136">Copie el comando siguiente, reemplazando los valores de los marcadores de posición con valores reales que sean válidos para su red:</span><span class="sxs-lookup"><span data-stu-id="a1e6b-136">Copy the following command, replacing placeholder values with actual values that are valid for your network:</span></span>  
  
    ```  
    Setspn -s http/<computer-name>.<domain-name>:<port> <domain-user-account>  
    ```  
  
     <span data-ttu-id="a1e6b-137">Por ejemplo: `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span><span class="sxs-lookup"><span data-stu-id="a1e6b-137">For example: `Setspn -s http/MyReportServer.MyDomain.com:80 MyDomainUser`</span></span>  
  
5.  <span data-ttu-id="a1e6b-138">Ejecute el comando.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-138">Run the command.</span></span>  
  
6.  <span data-ttu-id="a1e6b-139">Abra el archivo **RsReportServer.config** y busque la sección `<AuthenticationTypes>` .</span><span class="sxs-lookup"><span data-stu-id="a1e6b-139">Open the **RsReportServer.config** file and locate the `<AuthenticationTypes>` section.</span></span>  
  
7.  <span data-ttu-id="a1e6b-140">Agregue `<RSWindowsNegotiate/>` como primera entrada en esta sección para habilitar NTLM.</span><span class="sxs-lookup"><span data-stu-id="a1e6b-140">Add `<RSWindowsNegotiate/>` as the first entry in this section to enable NTLM.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e6b-141">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1e6b-141">See Also</span></span>  
 <span data-ttu-id="a1e6b-142">[Configurar una cuenta de servicio &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a1e6b-142">[Configure a Service Account &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md) </span></span>  
 <span data-ttu-id="a1e6b-143">[Configurar la cuenta de servicio del servidor de informes &#40;Administrador de configuración de SSRS&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a1e6b-143">[Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md) </span></span>  
 [<span data-ttu-id="a1e6b-144">Administración de un servidor de informes en modo nativo de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a1e6b-144">Manage a Reporting Services Native Mode Report Server</span></span>](manage-a-reporting-services-native-mode-report-server.md)  
  
  
