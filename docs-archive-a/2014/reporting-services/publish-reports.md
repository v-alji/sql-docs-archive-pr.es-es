---
title: Publicar informes | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- reports [Reporting Services], publishing
- publishing reports [Reporting Services]
ms.assetid: ef5a514e-e818-4041-a8b0-15835f9a046b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb54308a6b15260d4c336950f231d0ee40836430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662631"
---
# <a name="publish-reports"></a><span data-ttu-id="93300-102">Publicar informes</span><span class="sxs-lookup"><span data-stu-id="93300-102">Publish Reports</span></span>
  <span data-ttu-id="93300-103">Desde[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], puede publicar todos los informes y orígenes de datos compartidos de un proyecto de servidor de informes para un servidor de informes implementando el proyecto, o puede publicar un informe único.</span><span class="sxs-lookup"><span data-stu-id="93300-103">From[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can publish either all the reports and shared data sources in a Report Server project to a report server by deploying the project, or you can publish a single report.</span></span> <span data-ttu-id="93300-104">Para poder publicar un informe, debe especificar la dirección URL del servidor de informes de destino.</span><span class="sxs-lookup"><span data-stu-id="93300-104">Before you can publish a report you must specify the URL of the target report server.</span></span> <span data-ttu-id="93300-105">Para más información, vea [Establecer propiedades de implementación &#40;Reporting Services&#41;](tools/set-deployment-properties-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="93300-105">For more information, see [Set Deployment Properties &#40;Reporting Services&#41;](tools/set-deployment-properties-reporting-services.md).</span></span>  
  
 <span data-ttu-id="93300-106">Puede utilizar la versión [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para abrir los informes de [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] o [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] , modificarlos, obtener su vista previa, guardarlos y publicarlos.</span><span class="sxs-lookup"><span data-stu-id="93300-106">You can use the [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] version of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to open, modify, preview, save, and publish both [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] and [!INCLUDE[ssRSversion10](../includes/ssrsversion10-md.md)] reports.</span></span> <span data-ttu-id="93300-107">Para obtener más información, vea [Implementación y compatibilidad de versiones en las herramientas de datos de SQL Server &#40;SSRS&#41;](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="93300-107">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
### <a name="to-publish-all-reports-in-a-project"></a><span data-ttu-id="93300-108">Para publicar todos los informes de un proyecto</span><span class="sxs-lookup"><span data-stu-id="93300-108">To publish all reports in a project</span></span>  
  
-   <span data-ttu-id="93300-109">En el menú **compilar** , haga clic en \*\* \<report project name> implementar \*\*.</span><span class="sxs-lookup"><span data-stu-id="93300-109">On the **Build** menu, click **Deploy \<report project name>**.</span></span> <span data-ttu-id="93300-110">Como alternativa, en el Explorador de soluciones, haga clic con el botón derecho en el proyecto de informe y, después, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="93300-110">Alternatively, in Solution Explorer, right-click the report project and then click **Deploy**.</span></span> <span data-ttu-id="93300-111">El estado del proceso de publicación se puede ver en la ventana Resultados.</span><span class="sxs-lookup"><span data-stu-id="93300-111">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93300-112">Al implementar un proyecto del servidor de informes, también se implementan los orígenes de datos compartidos en el proyecto de informe.</span><span class="sxs-lookup"><span data-stu-id="93300-112">When you deploy a Report Server project, the shared data sources in the report project are also deployed.</span></span>  
  
### <a name="to-publish-a-single-report"></a><span data-ttu-id="93300-113">Para publicar solo un informe</span><span class="sxs-lookup"><span data-stu-id="93300-113">To publish a single report</span></span>  
  
-   <span data-ttu-id="93300-114">En el Explorador de soluciones, haga clic con el botón derecho en el informe y, después, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="93300-114">In Solution Explorer, right-click the report and then click **Deploy**.</span></span> <span data-ttu-id="93300-115">El estado del proceso de publicación se puede ver en la ventana Resultados.</span><span class="sxs-lookup"><span data-stu-id="93300-115">You can view the status of the publishing process in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93300-116">Al publicar un informe, también debe implementar los orígenes de datos compartidos que el informe utiliza.</span><span class="sxs-lookup"><span data-stu-id="93300-116">When you publish a report, you must also deploy the shared data sources that the report uses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93300-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93300-117">See Also</span></span>  
 <span data-ttu-id="93300-118">[Publicar orígenes de datos e informes](reports/publishing-data-sources-and-reports.md) </span><span class="sxs-lookup"><span data-stu-id="93300-118">[Publishing Data Sources and Reports](reports/publishing-data-sources-and-reports.md) </span></span>  
 <span data-ttu-id="93300-119">[Obtener una vista previa de informes](reports/previewing-reports.md) </span><span class="sxs-lookup"><span data-stu-id="93300-119">[Previewing Reports](reports/previewing-reports.md) </span></span>  
 <span data-ttu-id="93300-120">[Publicar informes en un servidor de informes](reports/publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="93300-120">[Publishing Reports to a Report Server](reports/publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="93300-121">[Buscar, ver y administrar informes &#40;Generador de informes y SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="93300-121">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="93300-122">Exportar informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="93300-122">Exporting Reports &#40;Report Builder and SSRS&#41;</span></span>](report-builder/export-reports-report-builder-and-ssrs.md)  
  
  
