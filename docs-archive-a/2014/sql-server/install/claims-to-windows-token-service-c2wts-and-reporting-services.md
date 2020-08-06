---
title: Notificaciones del servicio de token de Windows (C2WTS) y Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/25/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- c2wts.exe.config
- SharePoint mode
- C2WTS
- WSS_WPG
ms.assetid: 4d380509-deed-4b4b-a9c1-a9134cc40641
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: cf2e245dfae17556bdb906c134ba0d53898a8631
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672504"
---
# <a name="claims-to-windows-token-service-c2wts-and-reporting-services"></a><span data-ttu-id="6869e-102">Notificaciones del servicio de token de Windows (C2WTS) y Reporting Services</span><span class="sxs-lookup"><span data-stu-id="6869e-102">Claims to Windows Token Service (C2WTS) and Reporting Services</span></span>
  <span data-ttu-id="6869e-103">Las notificaciones del servicio de token de Windows (c2WTS) de SharePoint son necesarias con el [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] modo de SharePoint si desea usar la autenticación de Windows para los orígenes de datos que están fuera de la granja de servidores de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6869e-103">The SharePoint Claims to Windows Token Service (c2WTS) is required with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode if you want to use windows authentication for Data Sources that are outside the SharePoint farm.</span></span> <span data-ttu-id="6869e-104">Esto es cierto incluso si el usuario accede a los orígenes de datos con la autenticación de Windows porque la comunicación entre el servicio front-end web (WFE) y el servicio compartido de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] se realizará siempre con autenticación de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="6869e-104">This is true even if the user accesses the data sources with Windows Authentication because the communication between the web front-end (WFE) and the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service will always be Claims authentication.</span></span>  
  
 <span data-ttu-id="6869e-105">c2WTS es necesario aunque los orígenes de datos estén en el mismo equipo que el servicio compartido.</span><span class="sxs-lookup"><span data-stu-id="6869e-105">c2WTS is needed even if your data source(s) are on the same computer as the shared service.</span></span> <span data-ttu-id="6869e-106">Sin embargo, en este escenario no es necesaria la delegación restringida.</span><span class="sxs-lookup"><span data-stu-id="6869e-106">However in this scenario, constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="6869e-107">Los tokens creados por c2WTS funcionarán solo con delegación restringida (limitaciones a servicios concretos) y la opción de configuración "Usar cualquier protocolo de autenticación".</span><span class="sxs-lookup"><span data-stu-id="6869e-107">The tokens created by c2WTS will only work with constrained delegation (constrains to specific services) and the configuration option "using any authentication protocol".</span></span> <span data-ttu-id="6869e-108">Como se indicaba anteriormente, si los orígenes de datos están en el mismo equipo que el servicio compartido, la delegación restringida no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="6869e-108">As noted earlier, if your data sources are on the same computer as the shared service, then constrained delegation is not needed.</span></span>  
  
 <span data-ttu-id="6869e-109">Si en su entorno se usa la delegación limitada de Kerberos, el servicio SharePoint Server y los orígenes de datos externos deben residir en el mismo dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="6869e-109">If your environment will use Kerberos constrained delegation, then the SharePoint Server service and external data sources need to reside in the same Windows domain.</span></span> <span data-ttu-id="6869e-110">Cualquier servicio que use Notificaciones del servicio de token de Windows (c2WTS) debe emplear la delegación **restringida** de Kerberos para permitir que c2WTS use la transición del protocolo Kerberos para traducir las notificaciones en credenciales de Windows.</span><span class="sxs-lookup"><span data-stu-id="6869e-110">Any service that relies on the Claims to Windows token service (c2WTS) must use Kerberos **constrained** delegation to allow c2WTS to use Kerberos protocol transition to translate claims into Windows credentials.</span></span> <span data-ttu-id="6869e-111">Estos requisitos son verdaderos para todos los servicios compartidos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6869e-111">These requirements are true for all SharePoint Shared Services.</span></span> <span data-ttu-id="6869e-112">Para obtener más información, vea [información general sobre la autenticación Kerberos para productos de https://technet.microsoft.com/library/gg502594.aspx) Microsoft SharePoint 2010 (](https://technet.microsoft.com/library/gg502594.aspx).</span><span class="sxs-lookup"><span data-stu-id="6869e-112">For more information, see [Overview of Kerberos authentication for Microsoft SharePoint 2010 Products  (https://technet.microsoft.com/library/gg502594.aspx)](https://technet.microsoft.com/library/gg502594.aspx).</span></span>  
  
 <span data-ttu-id="6869e-113">El procedimiento se resume en este tema.</span><span class="sxs-lookup"><span data-stu-id="6869e-113">The procedure is summarized in this topic.</span></span>  
  
||  
|-|  
|<span data-ttu-id="6869e-114">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="6869e-114">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="6869e-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6869e-115">Prerequisites</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6869e-116">Nota: algunos pasos de configuración pueden cambiar o no funcionar en algunas topologías de granja.</span><span class="sxs-lookup"><span data-stu-id="6869e-116">Note: Some of the configuration steps may change, or may not work in certain farm topologies.</span></span> <span data-ttu-id="6869e-117">Por ejemplo, una instalación de un solo servidor no admite los servicios c2WTS de Windows Identity Foundation, por lo que las notificaciones a los escenarios de delegación de token de Windows no son posibles con esta configuración de granja.</span><span class="sxs-lookup"><span data-stu-id="6869e-117">For instance, a single server install does not support the Windows Identity Foundation c2WTS services so claims to windows token delegation scenarios are not possible with this farm configuration.</span></span>  
  
### <a name="basic-steps-needed-to-configure-c2wts"></a><span data-ttu-id="6869e-118">Pasos básicos necesarios para configurar c2WTS</span><span class="sxs-lookup"><span data-stu-id="6869e-118">Basic steps needed to configure c2WTS</span></span>  
  
1.  <span data-ttu-id="6869e-119">Configure la cuenta de servicio c2WTS.</span><span class="sxs-lookup"><span data-stu-id="6869e-119">Configure the c2WTS service account.</span></span> <span data-ttu-id="6869e-120">Agregue la cuenta de servicio al grupo de administradores local en cada servidor de aplicaciones ejecuta c2WTS.</span><span class="sxs-lookup"><span data-stu-id="6869e-120">Add the service account to the local Administrators group on each application server running c2WTS.</span></span> <span data-ttu-id="6869e-121">Además, compruebe que la cuenta tiene los siguientes derechos de directiva de seguridad local:</span><span class="sxs-lookup"><span data-stu-id="6869e-121">In addition, verify that the account has the following local security policy rights:</span></span>  
  
    -   <span data-ttu-id="6869e-122">Actuar como parte del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="6869e-122">Act as part of the operating system</span></span>  
  
    -   <span data-ttu-id="6869e-123">Suplantar un cliente después de autenticación</span><span class="sxs-lookup"><span data-stu-id="6869e-123">Impersonate a client after authentication</span></span>  
  
    -   <span data-ttu-id="6869e-124">Iniciar sesión como servicio</span><span class="sxs-lookup"><span data-stu-id="6869e-124">Log on as a service</span></span>  
  
     <span data-ttu-id="6869e-125">La cuenta que use para c2WTS también debe configurarse para la delegación restringida con transición de protocolo y necesita permisos para delegar en los servicios con los que es necesario comunicarse (es decir, SQL Server motor SQL Server Analysis Services). Para configurar la delegación puede usar el complemento usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6869e-125">The account you use for c2WTS also needs to be configured for Constrained Delegation with Protocol Transitioning and needs permissions to delegate to the Services it is required to communicate with (i.e. SQL Server Engine, SQL Server Analysis Services).To configure delegation you can use the Active Directory Users and Computer snap-in.</span></span>  
  
    1.  <span data-ttu-id="6869e-126">Haga clic con el botón secundario en cada cuenta de servicio y abra el cuadro de diálogo de propiedades.</span><span class="sxs-lookup"><span data-stu-id="6869e-126">Right-click each service account and open the properties dialog.</span></span> <span data-ttu-id="6869e-127">En el cuadro de diálogo, haga clic en la pestaña **Delegación** .</span><span class="sxs-lookup"><span data-stu-id="6869e-127">In the dialog click the **Delegation** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="6869e-128">Nota: la pestaña de delegación solo está visible si el objeto tiene asignado un SPN.</span><span class="sxs-lookup"><span data-stu-id="6869e-128">Note: the delegation tab is only visible if the object has an SPN assigned to it.</span></span> <span data-ttu-id="6869e-129">c2WTS no requiere un SPN en la cuenta de c2WTS; sin embargo, sin un SPN, la pestaña de **delegación** no estará visible.</span><span class="sxs-lookup"><span data-stu-id="6869e-129">c2WTS does not require an SPN on the c2WTS Account, however, without an SPN, the **Delegation** tab will not be visible.</span></span> <span data-ttu-id="6869e-130">Una manera alternativa de configurar la delegación restringida es utilizar una herramienta como **ADSIEdit**.</span><span class="sxs-lookup"><span data-stu-id="6869e-130">An alternative way to configure constrained delegation is to use a utility such as **ADSIEdit**.</span></span>  
  
    2.  <span data-ttu-id="6869e-131">Las opciones de configuración clave en la pestaña de delegación son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="6869e-131">Key configuration options on the delegation tab are the following:</span></span>  
  
        -   <span data-ttu-id="6869e-132">Seleccione "confiar en este usuario para la delegación solo a los servicios especificados"</span><span class="sxs-lookup"><span data-stu-id="6869e-132">Select "Trust this user for delegation to specified services only"</span></span>  
  
        -   <span data-ttu-id="6869e-133">Seleccione "usar cualquier protocolo de autenticación".</span><span class="sxs-lookup"><span data-stu-id="6869e-133">Select "Use any authentication protocol"</span></span>  
  
         <span data-ttu-id="6869e-134">Para obtener más información, vea la sección "configurar la delegación restringida de Kerberos para equipos y cuentas de servicio" de las notas del producto siguientes, [configurar la autenticación Kerberos para los productos de SharePoint 2010 y SQL Server 2008 R2](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products) .</span><span class="sxs-lookup"><span data-stu-id="6869e-134">For more information, see the "configure Kerberos constrained delegation for computers and service accounts" section of the following white paper, [Configuring Kerberos authentication for SharePoint 2010 and SQL Server 2008 R2 products](https://docs.microsoft.com/archive/blogs/tothesharepoint/white-paper-configuring-kerberos-authentication-for-sharepoint-2010-and-sql-server-2008-r2-products)</span></span>  
  
2.  <span data-ttu-id="6869e-135">Configurar c2WTS ' AllowedCallers '</span><span class="sxs-lookup"><span data-stu-id="6869e-135">Configure c2WTS 'AllowedCallers'</span></span>  
  
     <span data-ttu-id="6869e-136">c2WTS requiere que las identidades de los "autores de llamadas" se muestren explícitamente en el archivo de configuración, **c2wtshost.exe.config**. c2WTS no acepta solicitudes de todos los usuarios autenticados en el sistema a menos que esté configurado para ello.</span><span class="sxs-lookup"><span data-stu-id="6869e-136">c2WTS requires the 'callers' identities explicitly listed in the configuration file, **c2wtshost.exe.config**. c2WTS does not accept requests from all authenticated users in the system unless it is configured to do so.</span></span> <span data-ttu-id="6869e-137">En este caso el "autor de la llamada" es el grupo de Windows WSS_WPG.</span><span class="sxs-lookup"><span data-stu-id="6869e-137">In this case the 'caller' is the WSS_WPG Windows group.</span></span> <span data-ttu-id="6869e-138">El archivo c2wtshost.exe.confi se guarda en la ubicación siguiente:</span><span class="sxs-lookup"><span data-stu-id="6869e-138">The c2wtshost.exe.confi file is saved in the following location:</span></span>  
  
     <span data-ttu-id="6869e-139">**\Archivos de Programa\windows Identity Foundation\v3.5\c2wtshost.exe.config**</span><span class="sxs-lookup"><span data-stu-id="6869e-139">**\Program Files\Windows Identity Foundation\v3.5\c2wtshost.exe.config**</span></span>  
  
     <span data-ttu-id="6869e-140">A continuación se muestra un ejemplo del archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="6869e-140">The following is an example of the configuration file:</span></span>  
  
    ```  
    <configuration>  
      <windowsTokenService>  
        <!--  
            By default no callers are allowed to use the Windows Identity Foundation Claims To NT Token Service.  
            Add the identities you wish to allow below.  
          -->  
        <allowedCallers>  
          <clear/>  
          <add value="WSS_WPG" />  
        </allowedCallers>  
      </windowsTokenService>  
    </configuration>  
    ```  
  
3.  <span data-ttu-id="6869e-141">Iniciar el servicio c2WTS del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="6869e-141">Start the operating system c2WTS service:</span></span>  
  
    1.  <span data-ttu-id="6869e-142">Configure el servicio para usar la cuenta de servicio que configuró en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="6869e-142">Configure the service to use the service account you configured in the previous step.</span></span>  
  
    2.  <span data-ttu-id="6869e-143">Cambie el tipo de inicio a "**automático**" e inicie el servicio.</span><span class="sxs-lookup"><span data-stu-id="6869e-143">Change the Startup type to "**Automatic**" and start the service.</span></span>  
  
4.  <span data-ttu-id="6869e-144">Iniciar las notificaciones del servicio de token de Windows de SharePoint: inicie las notificaciones del servicio de token de Windows a través de administración central de SharePoint en la página **administrar servicios en el servidor** .</span><span class="sxs-lookup"><span data-stu-id="6869e-144">Start the SharePoint 'Claims to Windows Token Service': Start the Claims to Windows Token Service through SharePoint Central Administration on the **Manage Services on Server** page.</span></span> <span data-ttu-id="6869e-145">El servicio se debe iniciar en el servidor que realizará la acción.</span><span class="sxs-lookup"><span data-stu-id="6869e-145">The service should be started on the server that will be performing the action.</span></span> <span data-ttu-id="6869e-146">Por ejemplo, si tiene un servidor que es un servidor web front-end (WFE) y otro servidor que es un servidor de aplicaciones que tiene la ejecución del servicio compartido de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , solo tiene que iniciar c2WTS en el servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6869e-146">For example if you have a server that is a WFE and another server that is an Application Server that has the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] shared service running, you only need to start c2WTS on the Application Server.</span></span> <span data-ttu-id="6869e-147">c2WTS no es necesario en el servidor web front-end (WFE).</span><span class="sxs-lookup"><span data-stu-id="6869e-147">c2WTS is not needed on the WFE.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6869e-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6869e-148">See Also</span></span>  
 <span data-ttu-id="6869e-149">[Información general de notificaciones al servicio de token de Windows (c2WTS) (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span><span class="sxs-lookup"><span data-stu-id="6869e-149">[Claims to Windows Token Service (c2WTS) Overview (https://msdn.microsoft.com/library/ee517278.aspx)](https://msdn.microsoft.com/library/ee517278.aspx) </span></span>  
 [<span data-ttu-id="6869e-150">Información general sobre la autenticación Kerberos para productos de Microsoft SharePoint 2010 (https://technet.microsoft.com/library/gg502594.aspx)</span><span class="sxs-lookup"><span data-stu-id="6869e-150">Overview of Kerberos authentication for Microsoft SharePoint 2010 Products (https://technet.microsoft.com/library/gg502594.aspx)</span></span>](https://technet.microsoft.com/library/gg502594.aspx)  
  
