---
title: Administrar un servidor de informes en modo nativo de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- configuration options [Reporting Services]
- report servers [Reporting Services], configuring
ms.assetid: 6ca03a09-d6a8-4c93-ba12-1c99dcbfb618
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d44a9329074a20c04f878c055674ea563b297f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674572"
---
# <a name="manage-a-reporting-services-native-mode-report-server"></a><span data-ttu-id="8fba8-102">Administrar un servidor de informes en modo nativo de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8fba8-102">Manage a Reporting Services Native Mode Report Server</span></span>
  <span data-ttu-id="8fba8-103">Esta sección contiene procedimientos para configurar una instancia de servidor de informes en modo nativo utilizando el Administrador de configuración de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8fba8-103">This section contains procedures for configuring a native mode report server instance using the Reporting Services Configuration Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8fba8-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8fba8-104">In This Section</span></span>  
 <span data-ttu-id="8fba8-105">Los temas de esta sección se organizan en categorías para que pueda encontrar las instrucciones que desea más fácilmente.</span><span class="sxs-lookup"><span data-stu-id="8fba8-105">The topics in this section are organized into categories so that you can more easily find the instructions you want.</span></span> <span data-ttu-id="8fba8-106">La primera sección contiene los temas para las tareas de configuración básicas para un servidor de informes en modo nativo.</span><span class="sxs-lookup"><span data-stu-id="8fba8-106">The first section contains topics for basic configuration tasks for a native mode report server.</span></span> <span data-ttu-id="8fba8-107">La segunda sección contiene temas de configuración avanzados.</span><span class="sxs-lookup"><span data-stu-id="8fba8-107">The second section contains advanced configuration topics.</span></span> <span data-ttu-id="8fba8-108">La tercera sección contiene temas para configurar un servidor de informes de manera que se ejecute en modo integrado de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8fba8-108">The third section contains topics for configuring a report server to run in SharePoint integrated mode.</span></span>  
  
### <a name="basic-configuration"></a><span data-ttu-id="8fba8-109">Configuración básica</span><span class="sxs-lookup"><span data-stu-id="8fba8-109">Basic Configuration</span></span>  
 [<span data-ttu-id="8fba8-110">Administrador de configuración de Reporting Services &#40;modo nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="8fba8-110">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
 <span data-ttu-id="8fba8-111">Proporciona los pasos para iniciar la herramienta de configuración de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8fba8-111">Provides steps for starting the Reporting Services Configuration tool.</span></span>  
  
 [<span data-ttu-id="8fba8-112">Configurar una cuenta de servicio &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8fba8-112">Configure a Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="8fba8-113">Explica cómo especificar la información de cuenta y contraseña para el servicio Servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="8fba8-113">Explains how to specify account and password information for the Report Server service.</span></span>  
  
 [<span data-ttu-id="8fba8-114">Registrar un nombre principal de servicio &#40;SPN&#41; para un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="8fba8-114">Register a Service Principal Name &#40;SPN&#41; for a Report Server</span></span>](register-a-service-principal-name-spn-for-a-report-server.md)  
 <span data-ttu-id="8fba8-115">Explica cómo registrar manualmente un SPN para un servidor de informes que se ejecuta en una cuenta de usuario de dominio en una red que utiliza la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="8fba8-115">Explains how to manually register an SPN for a report server that runs under a domain user account on a network that uses Kerberos authentication.</span></span>  
  
 [<span data-ttu-id="8fba8-116">Configurar una dirección URL &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8fba8-116">Configure a URL  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-url-ssrs-configuration-manager.md)  
 <span data-ttu-id="8fba8-117">Explica cómo establecer una o varias direcciones URL que se usan para tener acceso al servicio web del servidor de informes y el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="8fba8-117">Explains how to establish one or more URLs used to access the Report Server Web service and Report Manager.</span></span>  
  
 [<span data-ttu-id="8fba8-118">Crear una base de datos del servidor de informes de modo nativo &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8fba8-118">Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md)  
 <span data-ttu-id="8fba8-119">Proporciona los pasos para crear una base de datos de servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="8fba8-119">Provides steps for creating a report server database.</span></span> <span data-ttu-id="8fba8-120">Este paso es necesario para implementar una instalación de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8fba8-120">This step is required for deploying a Reporting Services installation.</span></span>  
  
### <a name="advanced-or-optional-configuration"></a><span data-ttu-id="8fba8-121">Configuración avanzada u opcional</span><span class="sxs-lookup"><span data-stu-id="8fba8-121">Advanced or Optional Configuration</span></span>  
 [<span data-ttu-id="8fba8-122">Configurar una implementación escalada horizontalmente del servidor de informes en modo nativo &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8fba8-122">Configure a Native Mode Report Server Scale-Out Deployment &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-a-native-mode-report-server-scale-out-deployment.md)  
 <span data-ttu-id="8fba8-123">Proporciona los pasos para configurar varios servidores de informes para compartir una base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="8fba8-123">Provides steps for configuring multiple report servers to share a report server database.</span></span>  
  
 [<span data-ttu-id="8fba8-124">Configurar un servidor de informes para la entrega por correo electrónico &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="8fba8-124">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="8fba8-125">Ofrece pasos para configurar un servidor de informes para la distribución por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="8fba8-125">Provides steps for configuring a report server for e-mail distribution.</span></span>  
  
 [<span data-ttu-id="8fba8-126">Configurar un firewall para el acceso del Servidor de informes</span><span class="sxs-lookup"><span data-stu-id="8fba8-126">Configure a Firewall for Report Server Access</span></span>](configure-a-firewall-for-report-server-access.md)  
 <span data-ttu-id="8fba8-127">Explica cómo abrir los puertos que se usan para las solicitudes entrantes y las respuestas salientes desde un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="8fba8-127">Explains how to open ports used for inbound requests and outbound responses from a report server.</span></span>  
  
 [<span data-ttu-id="8fba8-128">Configurar un servidor de informes en modo nativo para la administración local &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="8fba8-128">Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;</span></span>](configure-a-native-mode-report-server-for-local-administration-ssrs.md)  
 <span data-ttu-id="8fba8-129">Describe los pasos adicionales necesarios para conectarse al Administrador de informes o a un servidor de informes mediante http://localhost.</span><span class="sxs-lookup"><span data-stu-id="8fba8-129">Describes additional steps required to connect to Report Manager or a report server using http://localhost.</span></span>  
  
 [<span data-ttu-id="8fba8-130">Configuración de un servidor de informes para la administración remota</span><span class="sxs-lookup"><span data-stu-id="8fba8-130">Configure a Report Server for Remote Administration</span></span>](configure-a-report-server-for-remote-administration.md)  
 <span data-ttu-id="8fba8-131">Explica cómo configurar una instancia del servidor de informes remota para que pueda conectarse y configurarla desde un equipo diferente.</span><span class="sxs-lookup"><span data-stu-id="8fba8-131">Explains how to configure a remote report server instance so that you can connect to and configure it from a different computer.</span></span>  
  
 [<span data-ttu-id="8fba8-132">Activación o desactivación de las características de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8fba8-132">Turn Reporting Services Features On or Off</span></span>](turn-reporting-services-features-on-or-off.md)  
 <span data-ttu-id="8fba8-133">Explica cómo quitar las características que no se usan en una instalación de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="8fba8-133">Explains how to remove unused features in a Reporting Services installation.</span></span>  
  
 [<span data-ttu-id="8fba8-134">Habilitar los errores remotos &#40;Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8fba8-134">Enable Remote Errors &#40;Reporting Services&#41;</span></span>](enable-remote-errors-reporting-services.md)  
 <span data-ttu-id="8fba8-135">Explica cómo establecer las propiedades de servidor en un servidor de informes para devolver información adicional sobre condiciones de error que se produzcan en servidores remotos.</span><span class="sxs-lookup"><span data-stu-id="8fba8-135">Explains how to set server properties on a report server to return additional information about error conditions that occur on remote servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fba8-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8fba8-136">See Also</span></span>  
 <span data-ttu-id="8fba8-137">[Configurar y administrar un servidor de informes &#40;modo nativo de SSRS&#41;](configure-and-administer-a-report-server-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="8fba8-137">[Configure and Administer a Report Server &#40;SSRS Native Mode&#41;](configure-and-administer-a-report-server-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="8fba8-138">Configuración y administración de un servidor de informes &#40;modo de SharePoint de Reporting Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8fba8-138">Configuration and Administration of a Report Server &#40;Reporting Services SharePoint Mode&#41;</span></span>](../configure-administer-report-server-reporting-services-sharepoint-mode.md)  
  
  
