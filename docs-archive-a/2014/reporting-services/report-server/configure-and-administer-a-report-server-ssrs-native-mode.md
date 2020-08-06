---
title: Configurar y administrar un servidor de informes (modo nativo de SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 08/10/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, components
- deploying [Reporting Services], component options
- report servers [Reporting Services], component options
- configuration options [Reporting Services]
- administering Reporting Services
- components [Reporting Services], configuring
- configuring servers [Reporting Services]
ms.assetid: cfec012b-56f1-4346-9814-247acf22351c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5164fd2f9170cb092a45394f64f06d7622253f2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674592"
---
# <a name="configure-and-administer-a-report-server-ssrs-native-mode"></a><span data-ttu-id="65b16-102">Configurar y administrar un servidor de informes (modo nativo de SSRS)</span><span class="sxs-lookup"><span data-stu-id="65b16-102">Configure and Administer a Report Server (SSRS Native Mode)</span></span>
  <span data-ttu-id="65b16-103">En este tema se resumen los métodos que se pueden usar para configurar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65b16-103">This topic summarizes the approaches that you can use to configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="65b16-104">También se incluye una lista de temas en los que se explica cómo configurar determinados componentes, características o funciones del servidor.</span><span class="sxs-lookup"><span data-stu-id="65b16-104">It also includes a list of topics that explain how to configure specific components, features, or server capabilities.</span></span> <span data-ttu-id="65b16-105">Para configurar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], puede:</span><span class="sxs-lookup"><span data-stu-id="65b16-105">To configure [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can:</span></span>  
  
-   <span data-ttu-id="65b16-106">Usar el Administrador de configuración de Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="65b16-106">Use the Reporting Services Configuration Manager.</span></span> <span data-ttu-id="65b16-107">En muchos de los temas de esta sección se proporciona información acerca de la configuración de determinadas características mediante esta herramienta.</span><span class="sxs-lookup"><span data-stu-id="65b16-107">Many of the topics in this section contain information about how to configure specific features through this tool.</span></span>  
  
-   <span data-ttu-id="65b16-108">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para personalizar las propiedades del servidor, habilitar Mis informes, habilitar los registros de seguimiento y establecer los valores predeterminados de todo el sitio.</span><span class="sxs-lookup"><span data-stu-id="65b16-108">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to customize server properties, enable My Reports, enable trace logs, and set site-wide defaults.</span></span> <span data-ttu-id="65b16-109">Para más información sobre la configuración del sitio, vea [Servidor de informes de Reporting Services &#40;modo nativo&#41;](reporting-services-report-server-native-mode.md) para Management Studio.</span><span class="sxs-lookup"><span data-stu-id="65b16-109">For more information about site settings, see [Reporting Services Report Server &#40;Native Mode&#41;](reporting-services-report-server-native-mode.md) for Management Studio.</span></span> <span data-ttu-id="65b16-110">Tenga en cuenta que se puede crear y ejecutar un script que establece las propiedades del servidor mediante programación.</span><span class="sxs-lookup"><span data-stu-id="65b16-110">Note that you can create and run script that sets server properties programmatically.</span></span> <span data-ttu-id="65b16-111">Para más información, vea [Script para tareas administrativas y de implementación](../tools/script-deployment-and-administrative-tasks.md) y [Propiedades del sistema del servidor de informes](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span><span class="sxs-lookup"><span data-stu-id="65b16-111">For more information, see [Script Deployment and Administrative Tasks](../tools/script-deployment-and-administrative-tasks.md) and [Report Server System Properties](../report-server-web-service/net-framework/reporting-services-properties-report-server-system-properties.md).</span></span>  
  
-   <span data-ttu-id="65b16-112">Use el Administrador de informes para conceder permisos para tener acceso al servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="65b16-112">Use Report Manager to grant permissions to access the report server.</span></span> <span data-ttu-id="65b16-113">Los permisos se conceden a través de las asignaciones de roles que define para cada cuenta de grupo o usuario.</span><span class="sxs-lookup"><span data-stu-id="65b16-113">Permissions are conveyed through role assignments that you define for each user or group account.</span></span> <span data-ttu-id="65b16-114">Para obtener más información, vea [Roles y permisos &#40;Reporting Services&#41;](../security/roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="65b16-114">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](../security/roles-and-permissions-reporting-services.md).</span></span>  
  
-   <span data-ttu-id="65b16-115">También puede modificar archivos de configuración para cambiar la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="65b16-115">Optionally, modify configuration files to change application settings.</span></span> <span data-ttu-id="65b16-116">Para obtener más información acerca de cada archivo así como directrices para modificarlos, vea [Reporting Services Configuration Files](reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="65b16-116">For more information about each file and guidelines for modifying them, see [Reporting Services Configuration Files](reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="65b16-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="65b16-117">In This Section</span></span>  
 [<span data-ttu-id="65b16-118">Configurar las direcciones URL del servidor de informes &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="65b16-118">Configure Report Server URLs  &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
 <span data-ttu-id="65b16-119">Describe cómo definir las direcciones URL que se usan para tener acceso al servidor de informes y al Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="65b16-119">Describes how to define the URLs used to access the report server and Report Manager.</span></span>  
  
 [<span data-ttu-id="65b16-120">Configurar la cuenta de servicio del servidor de informes &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="65b16-120">Configure the Report Server Service Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="65b16-121">Proporciona recomendaciones y pasos sobre cómo modificar la contraseña y la cuenta de servicio.</span><span class="sxs-lookup"><span data-stu-id="65b16-121">Provides recommendations and steps on how to modify service account and password.</span></span>  
  
 [<span data-ttu-id="65b16-122">Crear una base de datos del servidor de informes &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="65b16-122">Create a Report Server Database  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/create-a-report-server-database-ssrs-configuration-manager.md)  
 <span data-ttu-id="65b16-123">Describe cómo crear una base de datos del servidor de informes, necesaria para almacenar objetos y metadatos de servidor.</span><span class="sxs-lookup"><span data-stu-id="65b16-123">Describes how to create a report server database, required for storing server metadata and objects.</span></span>  
  
 [<span data-ttu-id="65b16-124">Configurar una conexión a la base de datos del servidor de informes &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="65b16-124">Configure a Report Server Database Connection  &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-database-connection-ssrs-configuration-manager.md)  
 <span data-ttu-id="65b16-125">Describe cómo modificar la cadena de conexión que utiliza el servidor de informes para conectarse a la base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="65b16-125">Describes how to modify the connection string used by the report server to connect to the report server database.</span></span>  
  
 [<span data-ttu-id="65b16-126">Configurar un servidor de informes para la entrega por correo electrónico &#40;SSRS Configuration Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="65b16-126">Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;</span></span>](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)  
 <span data-ttu-id="65b16-127">Describe cómo configurar un servidor de informes para permitir la distribución de informes por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="65b16-127">Describes how to configure a report server to support e-mail report distribution.</span></span>  
  
 [<span data-ttu-id="65b16-128">Configurar la cuenta de ejecución desatendida &#40;Administrador de configuración de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="65b16-128">Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;</span></span>](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md)  
 <span data-ttu-id="65b16-129">Describe cómo configurar una cuenta de usuario para procesar informes en modo desatendido.</span><span class="sxs-lookup"><span data-stu-id="65b16-129">Describes how to configure a user account to process reports in unattended mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b16-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="65b16-130">See Also</span></span>  
 <span data-ttu-id="65b16-131">[Configurar el acceso a Generador de informes](configure-report-builder-access.md) </span><span class="sxs-lookup"><span data-stu-id="65b16-131">[Configure Report Builder Access](configure-report-builder-access.md) </span></span>  
 <span data-ttu-id="65b16-132">[Archivos de configuración de Reporting Services](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="65b16-132">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="65b16-133">[Administrador de configuración de Reporting Services &#40;modo nativo&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="65b16-133">[Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) </span></span>  
 <span data-ttu-id="65b16-134">[Seguridad y protección de Reporting Services](../security/reporting-services-security-and-protection.md) </span><span class="sxs-lookup"><span data-stu-id="65b16-134">[Reporting Services Security and Protection](../security/reporting-services-security-and-protection.md) </span></span>  
 [<span data-ttu-id="65b16-135">Servidor de informes de Reporting Services &#40;modo nativo&#41;</span><span class="sxs-lookup"><span data-stu-id="65b16-135">Reporting Services Report Server &#40;Native Mode&#41;</span></span>](reporting-services-report-server-native-mode.md)  
  
  
