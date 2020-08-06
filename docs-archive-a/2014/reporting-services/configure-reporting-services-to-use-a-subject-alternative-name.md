---
title: Configurar Reporting Services para usar un nombre alternativo del firmante | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ce458f9f-4b4f-4a58-aa75-9a90dda1e622
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0312d2d1fff8f854eb2ffb8d0dad2563212ee23b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749176"
---
# <a name="configure-reporting-services-to-use-a-subject-alternative-name"></a><span data-ttu-id="7ca25-102">Configuración de Reporting Services para utilizar un nombre alternativo del asunto</span><span class="sxs-lookup"><span data-stu-id="7ca25-102">Configure Reporting Services to Use a Subject Alternative Name</span></span>
  <span data-ttu-id="7ca25-103">En este tema se explica cómo configurar [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS) para usar un nombre alternativo del asunto (SAN) modificando el archivo rsreportserver.config y usando la herramienta Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="7ca25-103">This topic explains how to configure [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS) to use a subject alternative name (SAN) by modifying the rsreportserver.config file and using the Netsh.exe tool.</span></span>

||
|-|
|<span data-ttu-id="7ca25-104">**[!INCLUDE[applies](../includes/applies-md.md)]** Modo nativo de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ca25-104">**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Native mode</span></span>|

 <span data-ttu-id="7ca25-105">Las instrucciones son válidas para la dirección URL del servicio de generación de informes y para la dirección URL del servicio web.</span><span class="sxs-lookup"><span data-stu-id="7ca25-105">The instructions apply to the Reporting Service URL as well as a Web Service URL.</span></span>

 <span data-ttu-id="7ca25-106">Para utilizar el SAN, el certificado SSL debe estar registrado en el servidor, firmado y tener la clave privada.</span><span class="sxs-lookup"><span data-stu-id="7ca25-106">To use a SAN, the SSL certificate must be registered on the server, signed, and have the private key.</span></span> <span data-ttu-id="7ca25-107">No puede utilizar un certificado autofirmado</span><span class="sxs-lookup"><span data-stu-id="7ca25-107">You cannot use a self-signed certificate</span></span>

 <span data-ttu-id="7ca25-108">Las direcciones URL en [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] se pueden configurar para utilizar un certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="7ca25-108">URLs in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] can be configured to use an SSL certificate.</span></span> <span data-ttu-id="7ca25-109">Normalmente, un certificado solo tiene un nombre de asunto, lo que permite solo una dirección URL para una sesión SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="7ca25-109">A certificate normally has just a subject name, which allows only one URL for an SSL (Secure Sockets Layer) session.</span></span> <span data-ttu-id="7ca25-110">El SAN es un campo adicional del certificado que permite a un servicio SSL escuchar y ser válido para varias direcciones URL, y compartir el puerto SSL con otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7ca25-110">The SAN is an additional field in the certificate that allows an SSL service to listen and be valid for many URLs, and to share the SSL port with other applications.</span></span> <span data-ttu-id="7ca25-111">El SAN es tiene un aspecto parecido a lo siguiente: www.s2.com.</span><span class="sxs-lookup"><span data-stu-id="7ca25-111">The SAN looks something like the following: www.s2.com.</span></span>

 <span data-ttu-id="7ca25-112">Para más información sobre la configuración de SSL para [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], vea [Configurar conexiones SSL en un servidor de informes en modo nativo](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="7ca25-112">For more information about SSL settings for [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], see [Configure SSL Connections on a Native Mode Report Server](security/configure-ssl-connections-on-a-native-mode-report-server.md).</span></span>

### <a name="configure-ssrs-to-use-a-subject-alternative-name-for-web-service-url"></a><span data-ttu-id="7ca25-113">Configure SSRS para utilizar un nombre alternativo del asunto para la dirección URL del servicio web</span><span class="sxs-lookup"><span data-stu-id="7ca25-113">Configure SSRS to use a subject alternative name for Web Service URL</span></span>

1.  <span data-ttu-id="7ca25-114">Inicie el Administrador de configuración de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7ca25-114">Start Reporting Services Configuration Manager.</span></span>

     <span data-ttu-id="7ca25-115">Para obtener más información, vea [Administrador de configuración de Reporting Services &#40;modo nativo&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="7ca25-115">For more information, see [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md).</span></span>

2.  <span data-ttu-id="7ca25-116">En la página **Dirección URL del servicio web** , seleccione un puerto SSL y un certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="7ca25-116">On the **Web Service URL** page, select an SSL port and SSL Certificate.</span></span>

     <span data-ttu-id="7ca25-117">![Administrador de configuración de Reporting Services](media/reportingservices-configurationmanager.png "Administrador de configuración de Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="7ca25-117">![Reporting Services Configuration Manager](media/reportingservices-configurationmanager.png "Reporting Services Configuration Manager")</span></span>

     <span data-ttu-id="7ca25-118">El administrador de configuración registra el certificado SSL para el puerto.</span><span class="sxs-lookup"><span data-stu-id="7ca25-118">The configuration manager registers the SSL certificate for the port.</span></span>

3.  <span data-ttu-id="7ca25-119">Abra el archivo rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="7ca25-119">Open the rsreportserver.config file.</span></span>

     <span data-ttu-id="7ca25-120">Para SSRS en el modo nativo, el archivo se encuentra predeterminadamente en la carpeta siguiente.</span><span class="sxs-lookup"><span data-stu-id="7ca25-120">For SSRS Native mode, the file is located by default in the following folder.</span></span>

    ```
    \Program Files\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer
    ```

4.  <span data-ttu-id="7ca25-121">Copie la sección de la URL para la aplicación de servicios web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7ca25-121">Copy the URL section for the Report Server Web Service application.</span></span>

     <span data-ttu-id="7ca25-122">Por ejemplo, la siguiente es la sección URL original.</span><span class="sxs-lookup"><span data-stu-id="7ca25-122">For example, the following is the original URL section.</span></span>

    ```
        <URL>
         <UrlString>https://localhost:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

     <span data-ttu-id="7ca25-123">El siguiente es la sección URL modificada.</span><span class="sxs-lookup"><span data-stu-id="7ca25-123">The following is the modified URL section.</span></span>

    ```
    <URL>
         <UrlString>https://www.s1.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>
        <URL>
         <UrlString>https://www.s2.com:443</UrlString>
         <AccountSid>S-1-5-20</AccountSid>
         <AccountName>NT Authority\NetworkService</AccountName>
        </URL>

    ```

5.  <span data-ttu-id="7ca25-124">Guarde el archivo rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="7ca25-124">Save the rsreportserver.config file.</span></span>

6.  <span data-ttu-id="7ca25-125">Inicie un símbolo del sistema como administrador y ejecute la herramienta Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="7ca25-125">Start a command prompt as an administrator, and run the Netsh.exe tool.</span></span>

    ```
    C:\windows\system32\netsh
    ```

7.  <span data-ttu-id="7ca25-126">Cambie al contexto http escribiendo lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7ca25-126">Switch to the http context by typing the following.</span></span>

    ```
    Netsh>http
    ```

8.  <span data-ttu-id="7ca25-127">Muestre las urlacls existentes escribiendo lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7ca25-127">Show the existing urlacls by typing the following.</span></span>

    ```
    Netsh http>show urlacl
    ```

     <span data-ttu-id="7ca25-128">Aparece una entrada como la siguiente.</span><span class="sxs-lookup"><span data-stu-id="7ca25-128">An entry such as the following appears.</span></span>

    ```
    Reserved URL            : https:// www.s1.com:443/ReportServer/
        User: NT SERVICE\ReportServer
            Listen: Yes
            Delegate: No
            SDDL: D:(A;;GX;;;S-1-5-80-1234567890-123456789-123456789-123456789-1234567890)
    ```

     <span data-ttu-id="7ca25-129">Una urlacl es una DACL (lista de control de acceso discrecional) para una dirección URL reservada.</span><span class="sxs-lookup"><span data-stu-id="7ca25-129">An urlacl is a DACL (Discretionary Access Control List) for a reserved URL.</span></span>

9. <span data-ttu-id="7ca25-130">Cree una nueva entrada para el nombre alternativo del asunto, con el mismo usuario y SDDL que la entrada existente, escribiendo lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7ca25-130">Create a new entry for the subject alternative name, with the same user and SDDL as the existing entry, by typing the following.</span></span>

    ```
    netsh http>add urlacl  url=https://www.s2.com:443/ReportServer  
    user="NT Service\ReportServer" sddl=D:(A;;GX;;;S-1-5-80-1234567980-12346579-123456789-123456789-1234567890)

    ```

10. <span data-ttu-id="7ca25-131">En la página **Estado del servidor de informes** del Administrador de configuración de Reporting Services, haga clic en **Detener** y, a continuación, haga clic en **Iniciar** para reiniciar el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7ca25-131">On the **Report Server Status** page of the Reporting Services Configuration Manager, Click **Stop** and then click **Start** to restart the report server.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ca25-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ca25-132">See Also</span></span>
 <span data-ttu-id="7ca25-133">El [archivo de configuración RSReportServer](report-server/rsreportserver-config-configuration-file.md) [Administrador de configuración de Reporting Services &#40;modo nativo&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [modificar un archivo de configuración de Reporting Services &#40;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) RSreportserver.config&#41;[configurar las direcciones url del servidor de informes &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)</span><span class="sxs-lookup"><span data-stu-id="7ca25-133">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md) [Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)</span></span>


