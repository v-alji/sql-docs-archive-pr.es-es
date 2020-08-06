---
title: Publicar un informe en una biblioteca de SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- deploying [Reporting Services], reports in SharePoint integrated mode
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 3f6dfc28-50d8-4231-bd25-871b5f77cce6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23b74ffb04bf1e13523dcf6ec5d774089d80f73b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744481"
---
# <a name="publish-a-report-to-a-sharepoint-library"></a><span data-ttu-id="47a57-102">Publicar un informe en una biblioteca de SharePoint</span><span class="sxs-lookup"><span data-stu-id="47a57-102">Publish a Report to a SharePoint Library</span></span>
  <span data-ttu-id="47a57-103">Para publicar un informe en un sitio de SharePoint configurado para la integración de SharePoint, debe establecer las propiedades del proyecto en el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="47a57-103">To publish a report to a SharePoint site configured for SharePoint integration, you must set the project properties in Report Designer.</span></span> <span data-ttu-id="47a57-104">En las propiedades de proyecto, todas las referencias a servidores, informes y orígenes de datos compartidos deben ser direcciones URL completas.</span><span class="sxs-lookup"><span data-stu-id="47a57-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span> <span data-ttu-id="47a57-105">En la definición de informe, todas las referencias a subinformes, informes detallados y recursos, como imágenes basadas en web, deben ser direcciones URL completas.</span><span class="sxs-lookup"><span data-stu-id="47a57-105">In the report definition, all references to subreports, drillthrough reports, and resources such as Web-based images, must be fully qualified URLS.</span></span>  
  
 <span data-ttu-id="47a57-106">Debe disponer del permiso **Miembro** o **Propietario** en el sitio de SharePoint para establecer las propiedades en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="47a57-106">You must have **Member** or **Owner** permission on the SharePoint site to set the properties on the project.</span></span> <span data-ttu-id="47a57-107">Para obtener más información, vea [Ejemplos de dirección URL para los elementos de informe publicados en un servidor de informes en modo de SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="47a57-107">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-report-to-a-sharepoint-site"></a><span data-ttu-id="47a57-108">Para publicar un informe en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="47a57-108">To publish a report to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="47a57-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra un nuevo proyecto de servidor de informes o uno existente.</span><span class="sxs-lookup"><span data-stu-id="47a57-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open an existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="47a57-110">En el menú **Proyecto** , haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="47a57-110">From the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="47a57-111">_\<project>_ Se abrirá el cuadro de diálogo **páginas de propiedades** .</span><span class="sxs-lookup"><span data-stu-id="47a57-111">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="47a57-112">En la lista **Configuración** , seleccione el nombre de una configuración de generación de soluciones para usarla en la generación y publicación del informe.</span><span class="sxs-lookup"><span data-stu-id="47a57-112">In the **Configuration** list, select the name of a solution build configuration to use to build and publish your report.</span></span> <span data-ttu-id="47a57-113">La configuración actual aparece como **Active**( *\<configuration>* ).</span><span class="sxs-lookup"><span data-stu-id="47a57-113">The current configuration is listed as **Active**(*\<configuration>*).</span></span>  
  
4.  <span data-ttu-id="47a57-114">Si desea publicar los orígenes de datos compartidos del proyecto y sobrescribir los publicados anteriormente, establezca **OverwriteDataSources** en **True**.</span><span class="sxs-lookup"><span data-stu-id="47a57-114">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="47a57-115">Opta En el caso de **TargetDataSourceFolder**, escriba una dirección URL a una biblioteca de SharePoint o una carpeta de biblioteca (por ejemplo, *http://TestServer/TestSite/Documents/DataSources)* .</span><span class="sxs-lookup"><span data-stu-id="47a57-115">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder (for example, *http://TestServer/TestSite/Documents/DataSources)*.</span></span>  
  
     <span data-ttu-id="47a57-116">Si no se especifica ningún valor, se usa el valor **TargetReportFolder** .</span><span class="sxs-lookup"><span data-stu-id="47a57-116">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="47a57-117">En el caso de **TargetReportFolder**, escriba una dirección URL a una biblioteca o una carpeta de biblioteca (por ejemplo, *http://TestServer/TestSite/Documents/Reports)* .</span><span class="sxs-lookup"><span data-stu-id="47a57-117">For **TargetReportFolder**, type a URL to a library or library folder (for example, *http://TestServer/TestSite/Documents/Reports)*.</span></span>  
  
7.  <span data-ttu-id="47a57-118">Para **TargetServerURL**, escriba una dirección URL a un sitio de nivel superior o a un subsitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="47a57-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="47a57-119">Si no especifica un sitio, se usa el sitio de nivel superior predeterminado (por ejemplo,, *http://servername* *http://servername/site* o *http://servername/site/subsite* ).</span><span class="sxs-lookup"><span data-stu-id="47a57-119">If you do not specify a site, the default top-level site is used (for example, *http://servername*, *http://servername/site*, or *http://servername/site/subsite*).</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="47a57-120">En el Explorador de soluciones, haga clic con el botón derecho en el informe que quiera publicar y haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="47a57-120">In Solution Explorer, right-click the report you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="47a57-121">El informe se publicará en la ubicación especificada en **TargetReportFolder**.</span><span class="sxs-lookup"><span data-stu-id="47a57-121">The report is published to the location specified in **TargetReportFolder**.</span></span> <span data-ttu-id="47a57-122">Los errores de implementación se mostrarán en la ventana de resultados.</span><span class="sxs-lookup"><span data-stu-id="47a57-122">Deployment errors appear in the Output window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a57-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="47a57-123">See Also</span></span>  
 <span data-ttu-id="47a57-124">[Cuadro de diálogo páginas de propiedades del proyecto](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="47a57-124">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="47a57-125">[Establecer las propiedades de implementación &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="47a57-125">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="47a57-126">[Publicar informes en un servidor de informes](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="47a57-126">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 <span data-ttu-id="47a57-127">[Ejemplos de dirección URL para los elementos de informe publicados en un servidor de informes en modo de SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="47a57-127">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 [<span data-ttu-id="47a57-128">Usar una conexión de datos de Office &#40;.odc&#41; con informes &#40;Reporting Services en el modo integrado de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="47a57-128">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
