---
title: Activar la característica File Sync del servidor de informes en administración central de SharePoint | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/06/2017
ms.openlocfilehash: 55feac69da85c7287ea56f4b8245350dd7e69565
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674659"
---
# <a name="activate-the-report-server-file-sync-feature-in-sharepoint-central-administration"></a><span data-ttu-id="1fb04-102">Activar la característica de sincronización de archivos del servidor de informes en Administración central de SharePoint</span><span class="sxs-lookup"><span data-stu-id="1fb04-102">Activate the Report Server File Sync Feature in SharePoint Central Administration</span></span>

<span data-ttu-id="1fb04-103">La característica Sincronizar archivo del Servidor de informes de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] utiliza los controladores de eventos de SharePoint para sincronizar el catálogo del servidor de informes con los elementos de las bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="1fb04-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Report Server File Sync feature utilizes SharePoint event handlers to synchronize the report server catalog with items in document libraries.</span></span> <span data-ttu-id="1fb04-104">Esta característica es beneficiosa cuando los usuarios cargan con frecuencia los elementos de informe publicados directamente en las bibliotecas de documentos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1fb04-104">This feature is beneficial when users frequently upload published report items directly to SharePoint document libraries.</span></span> <span data-ttu-id="1fb04-105">Si la característica de sincronización de archivos no está activada, el contenido se seguirá sincronizando, pero no con tanta frecuencia.</span><span class="sxs-lookup"><span data-stu-id="1fb04-105">If the file Sync feature isn't activated, content will still be synchronized but not as frequently.</span></span>  
  
<span data-ttu-id="1fb04-106">La característica de sincronización de archivos se puede activar en Administración del sitio de SharePoint después de instalar el Complemento [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] para productos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1fb04-106">The File Sync feature can be activated in SharePoint Site Administration after you install the [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span>  
  
<span data-ttu-id="1fb04-107">Esta característica se puede activar y desactivar manualmente en cada sitio pero no en el nivel de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="1fb04-107">This feature can be manually activated and deactivated per site but not at the site collection level.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1fb04-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1fb04-108">Prerequisites</span></span>  
 <span data-ttu-id="1fb04-109">Debe estar instalado el Complemento [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1fb04-109">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in for SharePoint must be installed.</span></span> <span data-ttu-id="1fb04-110">Si el complemento no está instalado, la característica de sincronización de archivos no estará visible en la lista de características del sitio.</span><span class="sxs-lookup"><span data-stu-id="1fb04-110">If the add-in isn't installed, the file sync feature won't be visible in the site feature list.</span></span>  
  
 <span data-ttu-id="1fb04-111">Para comprobar la instalación, vea la lista de aplicaciones instaladas en el [!INCLUDE[msCoName](../includes/msconame-md.md)] Panel de control **de**Windows.</span><span class="sxs-lookup"><span data-stu-id="1fb04-111">To verify installation, view the list of installed applications in [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows **Control Panel**.</span></span> <span data-ttu-id="1fb04-112">Si el Complemento [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] está instalado, siga las instrucciones de este tema para activar la característica de sincronización del servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="1fb04-112">If the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Add-in is installed, follow the instructions in this topic to activate the report server file sync feature.</span></span>  
  
### <a name="to-activate-or-deactivate-the-reporting-services-file-sync-feature-on-a-site"></a><span data-ttu-id="1fb04-113">Activar o desactivar la característica de sincronización de archivos de Reporting Services en un sitio</span><span class="sxs-lookup"><span data-stu-id="1fb04-113">To activate or deactivate the Reporting Services File Sync feature on a Site</span></span>  
  
1.  <span data-ttu-id="1fb04-114">En la Página principal del sitio, haga clic en el menú **acciones del sitio** y en **configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="1fb04-114">From the main page of your site, click the **Site Actions** menu and click **Site Settings**.</span></span>  
  
2.  <span data-ttu-id="1fb04-115">En **acciones del sitio**, haga clic en **administrar características del sitio**.</span><span class="sxs-lookup"><span data-stu-id="1fb04-115">In the **Site Actions**, click **Manage Site Features**.</span></span>  
  
3.  <span data-ttu-id="1fb04-116">Busque **Sincronizar archivo del Servidor de informes** en la lista.</span><span class="sxs-lookup"><span data-stu-id="1fb04-116">Find **Report Server File Sync** in the list.</span></span>  
  
4.  <span data-ttu-id="1fb04-117">Haga clic en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="1fb04-117">Click **Activate**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1fb04-118">Para desactivar la característica de sincronización de archivos del servidor de informes, puede usar el mismo procedimiento, pero tiene que hacer clic en **Desactivar**.</span><span class="sxs-lookup"><span data-stu-id="1fb04-118">To deactivate the Report Server file sync feature, you can use the same procedure but click **Deactivate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fb04-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1fb04-119">See Also</span></span>  
 <span data-ttu-id="1fb04-120">[Solucionar problemas de elementos de informe &#40;Generador de informes y SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1fb04-120">[Troubleshoot Report Parts &#40;Report Builder and SSRS&#41;](report-parts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1fb04-121">[Activar el servidor de informes y Power View características de integración de SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="1fb04-121">[Activate the Report Server and Power View Integration Features in SharePoint](activate-the-report-server-and-power-view-integration-features-in-sharepoint.md) </span></span>  
 <span data-ttu-id="1fb04-122">[Instalar o desinstalar el complemento de Reporting Services para SharePoint &#40;SharePoint 2010 y SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span><span class="sxs-lookup"><span data-stu-id="1fb04-122">[Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md) </span></span>  
 [<span data-ttu-id="1fb04-123">Instalar o desinstalar el complemento de Reporting Services para SharePoint &#40;SharePoint 2010 y SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="1fb04-123">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
