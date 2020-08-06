---
title: Desinstalar Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 5c764a00-d4bc-465d-b32e-e4efce052ce4
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 2870f7f84ea626b96560af586602996de3657276
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672428"
---
# <a name="uninstall-reporting-services"></a><span data-ttu-id="27aa6-102">Desinstalar Reporting Services</span><span class="sxs-lookup"><span data-stu-id="27aa6-102">Uninstall Reporting Services</span></span>
  <span data-ttu-id="27aa6-103">Al desinstalar [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no se quita el contenido que ha creado ni la configuración que ha modificado.</span><span class="sxs-lookup"><span data-stu-id="27aa6-103">Uninstalling [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] does not remove the content you have created or configuration you have modified.</span></span> <span data-ttu-id="27aa6-104">No obstante, si hay contenido que necesita una vez completada la desinstalación, se recomienda hacer copias del contenido antes de comenzar el proceso de desinstalación.</span><span class="sxs-lookup"><span data-stu-id="27aa6-104">However, if there is content you need after the uninstall is complete, it is recommended you make copies of content before you begin the uninstallation process.</span></span>

## <a name="uninstall-sharepoint-mode"></a><span data-ttu-id="27aa6-105">Desinstalar el modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="27aa6-105">Uninstall SharePoint Mode</span></span>
 <span data-ttu-id="27aa6-106">Al desinstalar el modo de SharePoint de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , se quita lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27aa6-106">When you uninstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint mode, the following are removed:</span></span>

-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="27aa6-107">y proxy del servicio.</span><span class="sxs-lookup"><span data-stu-id="27aa6-107">service and service proxy.</span></span>

-   <span data-ttu-id="27aa6-108">Archivos usados para la instalación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27aa6-108">Files used for the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span>

 <span data-ttu-id="27aa6-109">Las aplicaciones del servicio [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] no se quitan.</span><span class="sxs-lookup"><span data-stu-id="27aa6-109">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service applications are not removed.</span></span> <span data-ttu-id="27aa6-110">Si ya no desea las aplicaciones de servicio, puede eliminarlas mediante Windows PowerShell o Administración central de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="27aa6-110">If you no longer want the service applications, delete them by using Windows PowerShell or SharePoint Central Administration.</span></span>

 <span data-ttu-id="27aa6-111">Los elementos de informe y los metadatos relacionados no se quitan.</span><span class="sxs-lookup"><span data-stu-id="27aa6-111">The report items and related meta data are not removed.</span></span> <span data-ttu-id="27aa6-112">Esta información se encuentra en las bases de datos de contenido y configuración relacionadas con aplicaciones de servicio de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27aa6-112">This information is contained in the content and configuration databases related to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] service applications.</span></span> <span data-ttu-id="27aa6-113">Las bases de datos no se quitan y puede migrarlas manualmente a otra instalación de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en modo de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="27aa6-113">The databases are not removed and you can manually migrate the databases to another installation of [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="27aa6-114">Si ya no desea la información, elimine las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="27aa6-114">If you no longer want the information, delete the databases.</span></span> <span data-ttu-id="27aa6-115">Para obtener más información, vea [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="27aa6-115">For more information, see [Upgrade and Migrate Reporting Services](../../reporting-services/install-windows/upgrade-and-migrate-reporting-services.md).</span></span>

 <span data-ttu-id="27aa6-116">Los siguientes son nombres de ejemplo de las tres bases de datos de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] que no se quitan.</span><span class="sxs-lookup"><span data-stu-id="27aa6-116">The following are example names of the three [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] databases that are not removed.</span></span>

-   <span data-ttu-id="27aa6-117">**Base de datos del servidor de informes:** ReportingService_7f616e2d253040e8ab5653b3c09a065e</span><span class="sxs-lookup"><span data-stu-id="27aa6-117">**Report server database:** ReportingService_7f616e2d253040e8ab5653b3c09a065e</span></span>

-   <span data-ttu-id="27aa6-118">**Base de datos temporal del servidor de informes:** ReportingService_7f616e2d253040e8ab5653b3c09a065eTempDB</span><span class="sxs-lookup"><span data-stu-id="27aa6-118">**Report server temp database:** ReportingService_7f616e2d253040e8ab5653b3c09a065eTempDB</span></span>

-   <span data-ttu-id="27aa6-119">**Base de datos de alertas del servidor de informes:** ReportingService_7f616e2d253040e8ab5653b3c09a065e_Alerting</span><span class="sxs-lookup"><span data-stu-id="27aa6-119">**Report server alerting database:** ReportingService_7f616e2d253040e8ab5653b3c09a065e_Alerting</span></span>

### <a name="uninstall-the-add-in-for-sharepoint-products"></a><span data-ttu-id="27aa6-120">Desinstalar el complemento para Productos de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="27aa6-120">Uninstall the Add-in for SharePoint Products.</span></span>
 <span data-ttu-id="27aa6-121">Al desinstalar el complemento de un equipo, puede decidir solo la desinstalación de los archivos o también quitar la característica [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] de la granja.</span><span class="sxs-lookup"><span data-stu-id="27aa6-121">When you uninstall the add-in from a computer, you can choose to only uninstall the files or to also remove the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] feature from the farm.</span></span> <span data-ttu-id="27aa6-122">Para obtener información sobre cómo desinstalar el [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] complemento para productos de SharePoint, vea [instalar o desinstalar el complemento de Reporting Services para SharePoint &#40;SharePoint 2010 y sharepoint 2013&#41;](../../reporting-services/install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span><span class="sxs-lookup"><span data-stu-id="27aa6-122">For information on uninstalling the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] add-in for SharePoint products, see [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](../../reporting-services/install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md).</span></span>

## <a name="uninstall-native-mode"></a><span data-ttu-id="27aa6-123">Desinstalar el modo nativo</span><span class="sxs-lookup"><span data-stu-id="27aa6-123">Uninstall Native Mode</span></span>
 <span data-ttu-id="27aa6-124">Al desinstalar el modo nativo de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , cualquier elemento **creado** o **modificado** después de la instalación se deja en su lugar.</span><span class="sxs-lookup"><span data-stu-id="27aa6-124">When you uninstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] native mode, anything that was **created** or **modified** after the installation is left in place.</span></span> <span data-ttu-id="27aa6-125">Para obtener archivos de base de datos, archivos de registro, archivos de configuración de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] y elementos de contenido de ejemplo como archivos de origen de datos e informes.</span><span class="sxs-lookup"><span data-stu-id="27aa6-125">For example database files, log files, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] configuration files, and content items such as reports and datasource files.</span></span>

 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="27aa6-126">es una característica de una instancia y, por lo tanto, no se muestra en el Panel de control de Windows, Programas y Características.</span><span class="sxs-lookup"><span data-stu-id="27aa6-126">is an instance feature and therefore is not listed in Windows Control Panel, Programs and Features.</span></span> <span data-ttu-id="27aa6-127">Para desinstalar el modo nativo de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="27aa6-127">To uninstall [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Native mode:</span></span>

1.  <span data-ttu-id="27aa6-128">En el Panel de control de Windows, haga clic en **Programas y características**.</span><span class="sxs-lookup"><span data-stu-id="27aa6-128">In Windows Control Panel, click **Programs and Features**.</span></span>

2.  <span data-ttu-id="27aa6-129">En **Programas y características** , seleccione **Microsoft SQL Server 2012**.</span><span class="sxs-lookup"><span data-stu-id="27aa6-129">In **Programs and Features** select **Microsoft SQL Server 2012**.</span></span>

3.  <span data-ttu-id="27aa6-130">En el asistente para desinstalación, seleccione la instancia que incluye la característica de instancia de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]**RS**.</span><span class="sxs-lookup"><span data-stu-id="27aa6-130">In the uninstall wizard, select the instance that includes the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance feature **RS**.</span></span>

     <span data-ttu-id="27aa6-131">![rs_nativemode_uninstall_selectinstance](../../../2014/sql-server/install/media/rs-nativemode-uninstall-selectinstance.gif "rs_nativemode_uninstall_selectinstance")</span><span class="sxs-lookup"><span data-stu-id="27aa6-131">![rs_nativemode_uninstall_selectinstance](../../../2014/sql-server/install/media/rs-nativemode-uninstall-selectinstance.gif "rs_nativemode_uninstall_selectinstance")</span></span>

4.  <span data-ttu-id="27aa6-132">Tras seleccionar la instancia, seleccione la característica [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27aa6-132">After you select the instance, select the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] feature.</span></span>

     <span data-ttu-id="27aa6-133">![rs_nativemode_uninstall_selectfeatures](../../../2014/sql-server/install/media/rs-nativemode-uninstall-selectfeatures.gif "rs_nativemode_uninstall_selectfeatures")</span><span class="sxs-lookup"><span data-stu-id="27aa6-133">![rs_nativemode_uninstall_selectfeatures](../../../2014/sql-server/install/media/rs-nativemode-uninstall-selectfeatures.gif "rs_nativemode_uninstall_selectfeatures")</span></span>

5.  <span data-ttu-id="27aa6-134">Finalice el asistente.</span><span class="sxs-lookup"><span data-stu-id="27aa6-134">Complete the wizard.</span></span>

## <a name="see-also"></a><span data-ttu-id="27aa6-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27aa6-135">See Also</span></span>
 <span data-ttu-id="27aa6-136">[Desinstalar una instancia existente de SQL Server &#40;instalación&#41;](../../../2014/sql-server/install/uninstall-an-existing-instance-of-sql-server-setup.md) [instalar o desinstalar el complemento de PowerPivot para SharePoint &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/install-or-uninstall-the-power-pivot-for-sharepoint-add-in-sharepoint-2013) [instalar o desinstalar el complemento Reporting Services para SharePoint &#40;sharepoint 2010 y SharePoint 2013&#41;](../../reporting-services/install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)</span><span class="sxs-lookup"><span data-stu-id="27aa6-136">[Uninstall an Existing Instance of SQL Server &#40;Setup&#41;](../../../2014/sql-server/install/uninstall-an-existing-instance-of-sql-server-setup.md) [Install or Uninstall the PowerPivot for SharePoint Add-in &#40;SharePoint 2013&#41;](https://docs.microsoft.com/analysis-services/instances/install-windows/install-or-uninstall-the-power-pivot-for-sharepoint-add-in-sharepoint-2013) [Install or Uninstall the Reporting Services Add-in for SharePoint &#40;SharePoint 2010 and SharePoint 2013&#41;](../../reporting-services/install-windows/install-or-uninstall-the-reporting-services-add-in-for-sharepoint.md)</span></span>

