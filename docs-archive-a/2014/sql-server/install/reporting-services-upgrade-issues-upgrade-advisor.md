---
title: Problemas de actualización de Reporting Services (Asesor de actualizaciones) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], upgrade issues
- Reporting Services, upgrades
- upgrading Reporting Services
- report servers [Reporting Services], upgrade issues
ms.assetid: d9663f25-98d7-4508-ae3c-55a7277211bd
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 569afe735d68a724c0b4cc61ad2b7767088c2b30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677387"
---
# <a name="reporting-services-upgrade-issues-upgrade-advisor"></a><span data-ttu-id="4adb6-102">Problemas de actualización de Reporting Services (Asesor de actualizaciones)</span><span class="sxs-lookup"><span data-stu-id="4adb6-102">Reporting Services Upgrade Issues (Upgrade Advisor)</span></span>
  <span data-ttu-id="4adb6-103">En los temas siguientes se describen los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] problemas que pueden afectar a la actualización a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4adb6-103">The following topics describe the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] issues that might affect your upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4adb6-104">Los temas describen acciones que se pueden llevar a cabo para mitigar el efecto de estos cambios en el entorno.</span><span class="sxs-lookup"><span data-stu-id="4adb6-104">The topics describe actions that you can take to mitigate the effect of these changes on your environment.</span></span>  
  
 <span data-ttu-id="4adb6-105">El Asesor de actualizaciones analiza una instalación del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="4adb6-105">Upgrade Advisor analyzes a report server installation.</span></span> <span data-ttu-id="4adb6-106">Si solo se instalan componentes de cliente (por ejemplo, si el Diseñador de informes es el único componente de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instalado en el equipo), no se notificará ningún problema.</span><span class="sxs-lookup"><span data-stu-id="4adb6-106">If only client components are installed (for example, if Report Designer is the only [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] component installed on the computer), no issues will be reported.</span></span>  
  
 <span data-ttu-id="4adb6-107">Dependiendo de cómo configuró la instalación, puede encontrarse con problemas adicionales que el Asesor de actualizaciones no notificará.</span><span class="sxs-lookup"><span data-stu-id="4adb6-107">Depending on how you configured your installation, you may encounter additional issues that are not reported by Upgrade Advisor.</span></span> <span data-ttu-id="4adb6-108">Estos problemas no impiden que se realice correctamente una actualización de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], pero pueden afectar a la forma en la que se ejecutan los informes y las aplicaciones una vez finalizada la actualización.</span><span class="sxs-lookup"><span data-stu-id="4adb6-108">These issues do not prevent a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] upgrade from succeeding, but they may affect how reports and applications run after an upgrade is finished.</span></span> <span data-ttu-id="4adb6-109">Para obtener información sobre estos problemas, vea "Compatibilidad con versiones anteriores de Reporting Services" en los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4adb6-109">To learn about these issues, see "Reporting Services Backward Compatibility" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="4adb6-110">Si no puede utilizar el programa de instalación para actualizar una instalación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], puede instalar una instancia nueva de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y migrar la instalación existente a la nueva instancia.</span><span class="sxs-lookup"><span data-stu-id="4adb6-110">If you cannot use Setup to upgrade a [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation, you can install a new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance and migrate your existing installation to the new instance.</span></span> <span data-ttu-id="4adb6-111">Para obtener más información, vea "actualizar y migrar Reporting Services" en los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] libros en pantalla de, [actualizar y migrar Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="4adb6-111">For more information, see "Upgrade and Migrate Reporting Services" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online, [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
 <span data-ttu-id="4adb6-112">Los temas siguientes describen problemas conocidos que son notificados por el Asesor de actualizaciones y que explican cómo puede modificar la instalación existente para permitir que se lleve a cabo correctamente la actualización.</span><span class="sxs-lookup"><span data-stu-id="4adb6-112">The following topics describe known issues that are reported by Upgrade Advisor, and explain how you can modify your existing installation to allow an upgrade to occur.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4adb6-113">El asesor de actualizaciones debe estar instalado en el servidor de informes para analizar una instancia de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4adb6-113">Upgrade Advisor must be installed on the report server to analyze an instance of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="4adb6-114">no admite el análisis remoto.</span><span class="sxs-lookup"><span data-stu-id="4adb6-114">does not support remote analysis.</span></span>  
>   
>  <span data-ttu-id="4adb6-115">Para obtener más información, vea [instalar el asesor de actualizaciones](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="4adb6-115">For more information, see [Installing Upgrade Advisor](../../../2014/sql-server/install/installing-upgrade-advisor.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4adb6-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4adb6-116">In This Section</span></span>  
  
-   [<span data-ttu-id="4adb6-117">Certificados de cliente en el sitio web del servidor de informes &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-117">Client certificates on the report server web site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/client-certificates-on-the-report-server-web-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-118">Se han detectado extensiones personalizadas en el &#40;del Asesor de actualizaciones del servidor de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-118">Custom extensions were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-extensions-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-119">Se detectaron elementos de informe personalizados en el &#40;del Asesor de actualizaciones del servidor de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-119">Custom report items were detected on the report server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/custom-report-items-were-detected-on-the-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-120">No se detectaron componentes de compatibilidad con versiones anteriores de IIS &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-120">IIS backward compatibility components were not detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/iis-backward-compatibility-components-were-not-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-121">Restricción de dirección IP detectada &#40;Asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-121">IP address restriction detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/ip-address-restriction-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-122">Filtros ISAPI detectados en el sitio del servidor de informes &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-122">ISAPI filters detected on the report server site &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/isapi-filters-detected-on-the-report-server-site-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-123">Se detectaron extensiones obsoletas en el equipo del servidor de informes &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-123">Obsolete extensions were detected on the report server computer &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/obsolete-extensions-were-detected-on-the-report-server-computer-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-124">La base de datos del servidor de informes no está configurada &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-124">Report server database is not configured &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/report-server-database-is-not-configured-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-125">SQL Server grupo de servicios web del servidor de informes 2005 detectado &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-125">SQL Server 2005 Report Server Web Service group detected &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-2005-report-server-web-service-group-detected-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-126">Los directorios virtuales no están especificados &#40;Asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-126">Virtual directories are unspecified &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directories-are-unspecified-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-127">El directorio virtual tiene un método de autenticación no admitido &#40;Asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-127">Virtual directory has unsupported authentication method &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/virtual-directory-has-unsupported-authentication-method-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-128">Cambios en los límites de CPU y memoria para SQL Server Standard y Enterprise &#40;Asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-128">Changes to CPU and memory limits for SQL Server Standard and Enterprise &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/cpu-memory-limits-changes-sql-server-standard-enterprise-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-129">Cuentas de dominio necesarias para el asesor de actualizaciones de &#40;de granja de servidores de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-129">Domain accounts required for SharePoint farm &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/domain-accounts-required-for-sharepoint-farm-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-130">Exploración directa del Asesor de actualizaciones del servidor de informes &#40;&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-130">Direct Browsing to Report Server &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/direct-browsing-to-report-server-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-131">Microsoft SharePoint 2007 está instalado &#40;Asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-131">Microsoft SharePoint 2007 is Installed &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/microsoft-sharepoint-2007-is-installed-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-132">Microsoft SQL Server Reporting Services el servicio compartido de SharePoint está instalado en paralelo &#40;el asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-132">Microsoft SQL Server Reporting Services SharePoint Shared Service is Installed Side by Side &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/sql-server-reporting-services-sharepoint-shared-service-side-by-side-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-133">Intercalación de servidor Motor de base de datos incompatible &#40;Asesor de actualizaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="4adb6-133">Incompatible Database Engine Server Collation &#40;Upgrade Advisor&#41;</span></span>](../../../2014/sql-server/install/incompatible-database-engine-server-collation-upgrade-advisor.md)  
  
-   [<span data-ttu-id="4adb6-134">Otros problemas de actualización de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="4adb6-134">Other Reporting Services Upgrade Issues</span></span>](../../../2014/sql-server/install/other-reporting-services-upgrade-issues.md)  
  
  
