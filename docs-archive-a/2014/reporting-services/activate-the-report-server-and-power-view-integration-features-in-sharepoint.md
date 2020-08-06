---
title: Activar el servidor de informes y Power View características de integración de SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c7f64a54-c555-4d31-bf99-3abe57dc8626
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af5f544e959c039b0bdb85d63d0b94917254d78a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676378"
---
# <a name="activate-the-report-server-and-power-view-integration-features-in-sharepoint"></a><span data-ttu-id="7a474-102">Activar las características de integración del servidor de informes y Power View en SharePoint</span><span class="sxs-lookup"><span data-stu-id="7a474-102">Activate the Report Server and Power View Integration Features in SharePoint</span></span>
  <span data-ttu-id="7a474-103">Las [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] características de la colección de sitios normalmente se activan de forma predeterminada después de instalar el [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] complemento para productos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7a474-103">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features are usually activated by default after you install the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssRSCurrent](../includes/ssrscurrent-md.md)] Add-in for SharePoint products.</span></span> <span data-ttu-id="7a474-104">En algunas situaciones, tendrá que activar las características de forma manual.</span><span class="sxs-lookup"><span data-stu-id="7a474-104">In some situations you will need to manually activate the features.</span></span>  
  
 <span data-ttu-id="7a474-105">Si instala el complemento de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] para productos de SharePoint 2010 después de instalar el producto de SharePoint, la característica de integración del servidor de informes y la característica de integración de la vista avanzada se activarán únicamente para colecciones de sitios raíz.</span><span class="sxs-lookup"><span data-stu-id="7a474-105">If you install the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in for SharePoint 2010 Products after the installation of the SharePoint product, then the Report Server integration feature and the Power View integration feature will only be activated for root site collections.</span></span> <span data-ttu-id="7a474-106">Para las demás colecciones de sitios, deberá activar manualmente las características.</span><span class="sxs-lookup"><span data-stu-id="7a474-106">For other site collections, you will need to manually activate the features.</span></span> <span data-ttu-id="7a474-107">Por ejemplo, si tiene una colección de sitios de **http://[nombre de mi servidor]/sites/[nombre de colección de sitios]** deberá activar manualmente las características de la colección de sitios de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a474-107">For example if you have a site collection of **http://[my server name]/sites/[site collection name]** you will need to manually activate the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] site collection features.</span></span>  
  
 <span data-ttu-id="7a474-108">Cuando no hay colecciones de sitios raíz, el complemento de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] registrará un mensaje similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="7a474-108">When there is no root site collection, the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] add-in will log a message similar to the following.</span></span>  
  
 <span data-ttu-id="7a474-109">“La aplicación web 80 de Sharepoint no tiene colección de sitios raíz”</span><span class="sxs-lookup"><span data-stu-id="7a474-109">"SharePoint web app 80 does not have root site collection"</span></span>  
  
 <span data-ttu-id="7a474-110">El mensaje se encontrará en el registro de instalación del complemento, denominado "RS_SP_ #. log", donde # es un número que se incrementa.</span><span class="sxs-lookup"><span data-stu-id="7a474-110">The message will be found in the add-in installation log, named "RS_SP_#.log" where # is an incrementing number.</span></span> <span data-ttu-id="7a474-111">El archivo de registro se encontrará en la carpeta Temp de los usuarios actuales, por ejemplo, C:\Users \\ [nombre de usuario] \AppData\Local\Temp. Para obtener más información sobre las opciones de registro con el complemento, vea [instalar o desinstalar el complemento de Reporting Services para sharepoint &#40;sharepoint 2010 y sharepoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="7a474-111">The log file will be found in the current users Temp folder, for example C:\Users\\[user name]\AppData\Local\Temp. For more information on logging options with the add-in, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span>  
  
 <span data-ttu-id="7a474-112">En este tema:</span><span class="sxs-lookup"><span data-stu-id="7a474-112">In this topic:</span></span>  
  
-   [<span data-ttu-id="7a474-113">Para activar las características de colección de sitios de integración del servidor de informes y de la vista avanzada:</span><span class="sxs-lookup"><span data-stu-id="7a474-113">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>](#bkmk_features)  
  
-   [<span data-ttu-id="7a474-114">Para activar o desactivar la característica de colección de sitios de Administración central de Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="7a474-114">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>](#bkmk_centraladmin)  
  
##  <a name="to-activate-the-report-server-and-power-view-integration-site-collection-features"></a><a name="bkmk_features"></a><span data-ttu-id="7a474-115">Para activar el servidor de informes y Power View características de colección de sitios de integración:</span><span class="sxs-lookup"><span data-stu-id="7a474-115">To Activate the Report Server and Power View Integration Site Collection Features:</span></span>  
  
1.  <span data-ttu-id="7a474-116">Abra el explorador en el sitio donde desea que estén activas las características de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7a474-116">Open your browser to the site where you want the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features active.</span></span>  
  
2.  <span data-ttu-id="7a474-117">Haga clic en **Acciones del sitio**.</span><span class="sxs-lookup"><span data-stu-id="7a474-117">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="7a474-118">Haga clic en **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="7a474-118">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="7a474-119">Haga clic en **Características de la colección de sitios** en el grupo Administración de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="7a474-119">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="7a474-120">Busque **Característica de integración del servidor de informes** o **Característica de integración de Power View** en la lista.</span><span class="sxs-lookup"><span data-stu-id="7a474-120">Find **Report Server Integration Feature** or **Power View Integration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="7a474-121">Haga clic en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="7a474-121">Click **Activate**.</span></span>  
  
 <span data-ttu-id="7a474-122">Para desactivar las características, puede usar el mismo procedimiento y hacer clic en **Desactivar** en lugar de en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="7a474-122">To deactivate the features, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
##  <a name="to-activate-or-deactivate-reporting-services-central-administration-site-collection-feature"></a><a name="bkmk_centraladmin"></a><span data-ttu-id="7a474-123">Para activar o desactivar la característica de colección de sitios de administración central de Reporting Services:</span><span class="sxs-lookup"><span data-stu-id="7a474-123">To Activate or Deactivate Reporting Services Central Administration Site Collection Feature:</span></span>  
  
1.  <span data-ttu-id="7a474-124">Abra el explorador en Administración central de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7a474-124">Open your browser to SharePoint Central Administration.</span></span>  
  
2.  <span data-ttu-id="7a474-125">Haga clic en **Acciones del sitio**.</span><span class="sxs-lookup"><span data-stu-id="7a474-125">Click **Site Actions**.</span></span>  
  
3.  <span data-ttu-id="7a474-126">Haga clic en **Configuración del sitio**.</span><span class="sxs-lookup"><span data-stu-id="7a474-126">Click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="7a474-127">Haga clic en **Características de la colección de sitios** en el grupo Administración de la colección de sitios.</span><span class="sxs-lookup"><span data-stu-id="7a474-127">Click **Site Collection Features** in the Site Collection Administration Group.</span></span>  
  
5.  <span data-ttu-id="7a474-128">Busque la **Característica de administración central del servidor de informes** en la lista.</span><span class="sxs-lookup"><span data-stu-id="7a474-128">Find **Report Server Central Administration Feature** in the list.</span></span>  
  
6.  <span data-ttu-id="7a474-129">Haga clic en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="7a474-129">Click **Activate**.</span></span>  
  
 <span data-ttu-id="7a474-130">Para desactivar la característica, puede usar el mismo procedimiento y hacer clic en **Desactivar** en lugar de en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="7a474-130">To deactivate the feature, you can use the same procedure, but click **Deactivate** rather than **Activate.**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7a474-131">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7a474-131">Next Steps</span></span>  
 <span data-ttu-id="7a474-132">Una vez activada la característica, puede continuar con la integración del servidor.</span><span class="sxs-lookup"><span data-stu-id="7a474-132">After the feature is activated, you can continue with server integration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a474-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a474-133">See Also</span></span>  
 [<span data-ttu-id="7a474-134">Instalar o desinstalar el complemento de Reporting Services para SharePoint &#40;SharePoint 2010 y SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="7a474-134">Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;</span></span>](install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)  
  
  
