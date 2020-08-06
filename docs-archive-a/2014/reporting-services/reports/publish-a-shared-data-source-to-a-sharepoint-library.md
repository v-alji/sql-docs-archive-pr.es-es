---
title: Publicar un origen de datos compartido en una biblioteca de SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data sources [Reporting Services], publishing to a SharePoint library
- SharePoint integration [Reporting Services], publishing to a library
- publishing reports [Reporting Services], to a SharePoint library
ms.assetid: 966ed425-3ce2-4e76-8237-3c1c977954ae
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77ee25535ccb98638ae02ca64e3bcbfc88291c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744479"
---
# <a name="publish-a-shared-data-source-to-a-sharepoint-library"></a><span data-ttu-id="41428-102">Publicar un origen de datos compartido en una biblioteca de SharePoint</span><span class="sxs-lookup"><span data-stu-id="41428-102">Publish a Shared Data Source to a SharePoint Library</span></span>
  <span data-ttu-id="41428-103">Para publicar un origen de datos compartido en un servidor de informes que se ejecuta en el modo integrado de SharePoint, debe establecer las propiedades de proyecto de informe en el Diseñador de informes.</span><span class="sxs-lookup"><span data-stu-id="41428-103">To publish a shared data source to a report server that is running in SharePoint integrated mode, you must set the report project properties in Report Designer.</span></span> <span data-ttu-id="41428-104">En las propiedades de proyecto, todas las referencias a servidores, informes y orígenes de datos compartidos deben ser direcciones URL completas.</span><span class="sxs-lookup"><span data-stu-id="41428-104">In the project properties, all references to servers, reports, and shared data sources must be fully qualified URLs.</span></span>  
  
 <span data-ttu-id="41428-105">Debe disponer del permiso **Miembro** o **Propietario** en el sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="41428-105">You must have **Member** or **Owner** permission on the SharePoint site.</span></span> <span data-ttu-id="41428-106">Para obtener más información, vea [Ejemplos de dirección URL para los elementos de informe publicados en un servidor de informes en modo de SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span><span class="sxs-lookup"><span data-stu-id="41428-106">For more information, see [URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md).</span></span>  
  
### <a name="to-publish-a-shared-data-source-to-a-sharepoint-site"></a><span data-ttu-id="41428-107">Para publicar un origen de datos compartido en un sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="41428-107">To publish a shared data source to a SharePoint site</span></span>  
  
1.  <span data-ttu-id="41428-108">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra un proyecto de servidor de informes nuevo o uno existente.</span><span class="sxs-lookup"><span data-stu-id="41428-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open your existing or new Report Server project.</span></span>  
  
2.  <span data-ttu-id="41428-109">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="41428-109">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="41428-110">_\<project>_ Se abrirá el cuadro de diálogo **páginas de propiedades** .</span><span class="sxs-lookup"><span data-stu-id="41428-110">The _\<project>_**Property Pages** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="41428-111">Elija la **Configuración** que utilice para publicar en un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="41428-111">Choose the **Configuration** you use to publish to a SharePoint site.</span></span>  
  
4.  <span data-ttu-id="41428-112">Si desea publicar los orígenes de datos compartidos del proyecto y sobrescribir los publicados anteriormente, establezca **OverwriteDataSources** en **True**.</span><span class="sxs-lookup"><span data-stu-id="41428-112">If you want to publish the shared data sources in your project and overwrite previously published shared data sources, set **OverwriteDataSources** to **True**.</span></span>  
  
5.  <span data-ttu-id="41428-113">(Opcional) Para **TargetDataSourceFolder**, escriba una dirección URL a una biblioteca de SharePoint o a una carpeta de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="41428-113">(Optional) For **TargetDataSourceFolder**, type a URL to a SharePoint library or library folder.</span></span> <span data-ttu-id="41428-114">Por ejemplo, *http://TestServer/TestSite/Documents/DataSources* .</span><span class="sxs-lookup"><span data-stu-id="41428-114">For example, *http://TestServer/TestSite/Documents/DataSources*.</span></span>  
  
     <span data-ttu-id="41428-115">Si no se especifica ningún valor, se usa el valor **TargetReportFolder** .</span><span class="sxs-lookup"><span data-stu-id="41428-115">If you do not specify a value, the **TargetReportFolder** value is used.</span></span>  
  
6.  <span data-ttu-id="41428-116">Para **TargetReportFolder**, escriba una dirección URL a una biblioteca o a una carpeta de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="41428-116">For **TargetReportFolder**, type a URL to a library or library folder.</span></span> <span data-ttu-id="41428-117">Por ejemplo, http:*//TestServer/TestSite/Documents/Reports*.</span><span class="sxs-lookup"><span data-stu-id="41428-117">For example, http:*//TestServer/TestSite/Documents/Reports*.</span></span>  
  
7.  <span data-ttu-id="41428-118">Para **TargetServerURL**, escriba una dirección URL a un sitio de nivel superior o a un subsitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="41428-118">For **TargetServerURL**, type a URL to a SharePoint top-level site or subsite.</span></span> <span data-ttu-id="41428-119">Si no especifica ningún sitio, se usa el sitio de nivel superior predeterminado.</span><span class="sxs-lookup"><span data-stu-id="41428-119">If you do not specify a site, the default top-level site is used.</span></span> <span data-ttu-id="41428-120">Por ejemplo, http://*nombreDeServidor*, http://*nombreDeServidor*/*sitio*o http://*nombreDeServidor*/*sitio*/*subsitio*.</span><span class="sxs-lookup"><span data-stu-id="41428-120">For example, http://*servername*, http://*servername*/*site*, or http://*servername*/*site*/*subsite*.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="41428-121">En el Explorador de soluciones, haga clic con el botón derecho en el origen de datos compartido que quiera publicar y, después, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="41428-121">In Solution Explorer, right-click the shared data source you want to publish, and click **Deploy**.</span></span> <span data-ttu-id="41428-122">El origen de datos se publicará en la ubicación especificada en **TargetDataSourceFolder**.</span><span class="sxs-lookup"><span data-stu-id="41428-122">The data source is published to the location specified in **TargetDataSourceFolder**.</span></span> <span data-ttu-id="41428-123">Los errores de implementación se mostrarán en la ventana de resultados.</span><span class="sxs-lookup"><span data-stu-id="41428-123">Deployment errors appear in the Output window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="41428-124">Después de publicar un origen de datos compartido en un sitio de SharePoint, se cambia la extensión de nombre de archivo a .rsds.</span><span class="sxs-lookup"><span data-stu-id="41428-124">After you publish a shared data source to a SharePoint site, the file name extension is changed to .rsds.</span></span> <span data-ttu-id="41428-125">Puede editar y administrar un origen de datos compartido directamente en el sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="41428-125">You can edit and manage a shared data source directly on the SharePoint site.</span></span> <span data-ttu-id="41428-126">Para más información, vea [Crear y administrar orígenes de datos compartidos &#40;Reporting Services en el modo integrado de SharePoint&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span><span class="sxs-lookup"><span data-stu-id="41428-126">For more information, see [Create and Manage Shared Data Sources &#40;Reporting Services in SharePoint Integrated Mode&#41;](../create-manage-shared-data-sources-reporting-services-sharepoint-integrated-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41428-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41428-127">See Also</span></span>  
 <span data-ttu-id="41428-128">[Publicar un informe en una biblioteca de SharePoint](publish-a-report-to-a-sharepoint-library.md) </span><span class="sxs-lookup"><span data-stu-id="41428-128">[Publish a Report to a SharePoint Library](publish-a-report-to-a-sharepoint-library.md) </span></span>  
 <span data-ttu-id="41428-129">[Ejemplos de dirección URL para los elementos de informe publicados en un servidor de informes en modo de SharePoint &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span><span class="sxs-lookup"><span data-stu-id="41428-129">[URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md) </span></span>  
 <span data-ttu-id="41428-130">[Cuadro de diálogo páginas de propiedades del proyecto](../tools/project-property-pages-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="41428-130">[Project Property Pages Dialog Box](../tools/project-property-pages-dialog-box.md) </span></span>  
 <span data-ttu-id="41428-131">[Establecer las propiedades de implementación &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="41428-131">[Set Deployment Properties &#40;Reporting Services&#41;](../tools/set-deployment-properties-reporting-services.md) </span></span>  
 <span data-ttu-id="41428-132">[Publicar informes en un servidor de informes](publishing-reports-to-a-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="41428-132">[Publishing Reports to a Report Server](publishing-reports-to-a-report-server.md) </span></span>  
 [<span data-ttu-id="41428-133">Usar una conexión de datos de Office &#40;.odc&#41; con informes &#40;Reporting Services en el modo integrado de SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="41428-133">Use an Office Data Connection &#40;.odc&#41; with Reports &#40;Reporting Services in SharePoint Integrated Mode&#41;</span></span>](../report-data/use-an-office-data-connection-odc-with-reports.md)  
  
  
