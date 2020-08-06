---
title: Scripting y PowerShell con Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services]
- Reporting Services, scripting
- scripting [Reporting Services]
ms.assetid: 1ac2646d-ed5a-4436-b18f-2150c33f3d87
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a7a8dc805351897c11202467ed8bcb0373ef77c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674011"
---
# <a name="scripting-and-powershell-with-reporting-services"></a><span data-ttu-id="10cb9-102">Secuencias de comandos y PowerShell con Reporting Services</span><span class="sxs-lookup"><span data-stu-id="10cb9-102">Scripting and PowerShell with Reporting Services</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="10cb9-103">admite una amplia gama de escenarios de desarrollo y administración a través de script, incluida la utilidad de línea de comandos rs.exe, cmdlets de PowerShell para servidores de informes de modo de SharePoint y aprovechando el [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] modelo de objetos de PowerShell para los modos nativo y SharePoint.</span><span class="sxs-lookup"><span data-stu-id="10cb9-103">supports a wide range of development and management scenarios through script, including the rs.exe command line utility, PowerShell cmdlets for SharePoint mode report servers, and leveraging the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] object model from PowerShell for both Native and SharePoint mode.</span></span>

-   <span data-ttu-id="10cb9-104">Los administradores pueden escribir el script en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] para automatizar la manera de implementar y administrar una instalación del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="10cb9-104">Administrators can write script in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] to automate how they deploy and manage a report server installation.</span></span> <span data-ttu-id="10cb9-105">Los administradores también pueden generar y ejecutar scripts de [!INCLUDE[tsql](../../includes/tsql-md.md)] que crean, configurar y actualizan una base de datos del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="10cb9-105">Administrators can also generate and run [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that create, configure, and update a report server database.</span></span> <span data-ttu-id="10cb9-106">Los administradores también pueden usar las características de script de reproducción y registro en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] para automatizar las tareas de mantenimiento rutinarias.</span><span class="sxs-lookup"><span data-stu-id="10cb9-106">Administrators can also use the record and playback script features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to automate routine maintenance tasks.</span></span>

-   <span data-ttu-id="10cb9-107">Los programadores pueden crear aplicaciones personalizadas que incluyen el script.</span><span class="sxs-lookup"><span data-stu-id="10cb9-107">Developers can create custom applications that include script.</span></span> <span data-ttu-id="10cb9-108">Puede ejecutar un script que realiza llamadas al servicio web del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="10cb9-108">You can run script that makes calls to the Report Server Web service.</span></span> <span data-ttu-id="10cb9-109">Casi cualquier operación que puede escribir en código administrado también se puede escribir en script.</span><span class="sxs-lookup"><span data-stu-id="10cb9-109">Almost any operation that you can write in managed code can also be written in script.</span></span>

-   [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="10cb9-110">admite [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] script de .NET como lenguaje de script que puede procesar la utilidad RS.exe, un host de scripts que se ejecuta en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="10cb9-110">supports [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET script as the script language that can be processed by the RS.exe utility, a script host that runs on the report server.</span></span>

## <a name="reporting-services-sharepoint-mode-powershell-cmdlets-and-samples"></a><span data-ttu-id="10cb9-111">Ejemplos y cmdlets de PowerShell del modo SharePoint de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="10cb9-111">Reporting Services SharePoint mode PowerShell cmdlets and samples</span></span>
 <span data-ttu-id="10cb9-112">![Contenido relacionado con PowerShell](../media/rs-powershellicon.jpg "Contenido relacionado con PowerShell")</span><span class="sxs-lookup"><span data-stu-id="10cb9-112">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="10cb9-113">El modo SharePoint incluye [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] cmdlets para la administración del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="10cb9-113">SharePoint mode includes [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] cmdlets for report server administration.</span></span>

-   <span data-ttu-id="10cb9-114">[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) Incluye los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="10cb9-114">[PowerShell cmdlets for Reporting Services SharePoint Mode](../powershell-cmdlets-for-reporting-services-sharepoint-mode.md) Includes the following examples:</span></span>

    -   <span data-ttu-id="10cb9-115">Crear una aplicación de servicio y un proxy</span><span class="sxs-lookup"><span data-stu-id="10cb9-115">Create a service application and proxy</span></span>

    -   <span data-ttu-id="10cb9-116">Revisar y actualizar una extensión de entrega</span><span class="sxs-lookup"><span data-stu-id="10cb9-116">Review and update a delivery extension</span></span>

    -   <span data-ttu-id="10cb9-117">Obtener y establecer propiedades de la base de datos de la aplicación Reporting Services; por ejemplo, el tiempo de espera de la base de datos</span><span class="sxs-lookup"><span data-stu-id="10cb9-117">Get and set Properties of the Reporting Service Application Database, for example database timeout</span></span>

    -   <span data-ttu-id="10cb9-118">Extensiones de datos de lista</span><span class="sxs-lookup"><span data-stu-id="10cb9-118">List Data Extensions</span></span>

## <a name="reporting-services-object-model-and-powershell-samples"></a><span data-ttu-id="10cb9-119">Ejemplos de Powershell y modelo de objetos de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="10cb9-119">Reporting Services Object model and Powershell samples</span></span>
 <span data-ttu-id="10cb9-120">![Contenido relacionado con PowerShell](../media/rs-powershellicon.jpg "Contenido relacionado con PowerShell")</span><span class="sxs-lookup"><span data-stu-id="10cb9-120">![PowerShell related content](../media/rs-powershellicon.jpg "PowerShell related content")</span></span>

 <span data-ttu-id="10cb9-121">PowerShell realiza la llamada al núcleo del modelo de objetos y para la mayor parte válida para los modos SharePoint y nativo; por ejemplo, el trabajo de migración, el trabajo de suscripción y más ejemplos relacionados para las suscripciones funcionan en SQL15.</span><span class="sxs-lookup"><span data-stu-id="10cb9-121">PowerShell calling the core object model and for the most part valid for SharePoint and native mode, for example the migration work, subscription work, and more related samples for subscriptions work in SQL15.</span></span>

-   <span data-ttu-id="10cb9-122">[Use PowerShell para cambiar y enumerar los propietarios de una suscripción de Reporting Services y ejecutar una suscripción](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="10cb9-122">[Use PowerShell to Change and List Reporting Services Subscription Owners and Run a Subscription](../subscriptions/manage-subscription-owners-and-run-subscription-powershell.md).</span></span>

-   <span data-ttu-id="10cb9-123">[Usar PowerShell para crear una máquina virtual de Azure con un servidor de informes en modo nativo](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span><span class="sxs-lookup"><span data-stu-id="10cb9-123">[Use PowerShell to Create an Azure VM With a Native Mode Report Server](https://msdn.microsoft.com/library/azure/dn449661.aspx).</span></span>

-   <span data-ttu-id="10cb9-124">Vea la sección "Obtener acceso a las clases WMI mediante PowerShell" en [Obtener acceso al proveedor WMI de Reporting Services](access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="10cb9-124">See the section "Access the WMI classes using PowerShell" in [Access the Reporting Services WMI Provider](access-the-reporting-services-wmi-provider.md).</span></span>

-   <span data-ttu-id="10cb9-125">[Cómo administrar SSRS con PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/).scriptin</span><span class="sxs-lookup"><span data-stu-id="10cb9-125">[How to Administer SSRS using PowerShell](https://www.sqlshack.com/how-to-administer-sql-server-reporting-services-ssrs-subscriptions-using-powershell/).scriptin</span></span>

## <a name="rsexe-scripting-samples"></a><span data-ttu-id="10cb9-126">Ejemplos de secuencias de comandos de RS.exe</span><span class="sxs-lookup"><span data-stu-id="10cb9-126">RS.exe scripting samples</span></span>

-   <span data-ttu-id="10cb9-127">[Reporting Services de ejemplo rs.exe script para migrar contenido entre servidores de informes](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="10cb9-127">[Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>

-   <span data-ttu-id="10cb9-128">Consulte [Muestras de producto de SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889)para obtener más ejemplos de secuencias de comandos, aplicaciones y extensiones.</span><span class="sxs-lookup"><span data-stu-id="10cb9-128">For additional script, application, and extension examples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>

## <a name="see-also"></a><span data-ttu-id="10cb9-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10cb9-129">See Also</span></span>
 <span data-ttu-id="10cb9-130">[RS.exe utilidad &#40;](rs-exe-utility-ssrs.md) script de la [implementación de scripts de SSRS&#41;y tareas administrativas](script-deployment-and-administrative-tasks.md) [con la utilidad de rs.exe y el servicio Web](script-with-the-rs-exe-utility-and-the-web-service.md)</span><span class="sxs-lookup"><span data-stu-id="10cb9-130">[RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md) [Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) [Script with the rs.exe Utility and the Web Service](script-with-the-rs-exe-utility-and-the-web-service.md)</span></span>


