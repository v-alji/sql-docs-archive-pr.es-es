---
title: Publicar orígenes de datos e informes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing data sources [Reporting Services]
- publishing reports [Reporting Services]
- data sources [Reporting Services], managing
ms.assetid: 3a740f8a-1060-4ec3-938b-2305b6887ebd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 941362afde1cfe5dd3d235c9f243fb17875adadc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744476"
---
# <a name="publishing-data-sources-and-reports"></a><span data-ttu-id="7f39d-102">Publicar orígenes de datos e informes</span><span class="sxs-lookup"><span data-stu-id="7f39d-102">Publishing Data Sources and Reports</span></span>
  <span data-ttu-id="7f39d-103">Antes de publicar el informe, conviene que muestre una vista previa del mismo para comprobar el aspecto que tendrá cuando se ejecute.</span><span class="sxs-lookup"><span data-stu-id="7f39d-103">Before publishing your report, you should preview the report to see how it will look when it is run.</span></span> <span data-ttu-id="7f39d-104">Puede continuar perfeccionando el diseño hasta que esté satisfecho con los resultados.</span><span class="sxs-lookup"><span data-stu-id="7f39d-104">You can continue to refine the design until you are satisfied with the results.</span></span>  
  
 <span data-ttu-id="7f39d-105">Cuando haya terminado de diseñar y de probar el informe, podrá compartirlo con otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="7f39d-105">After you design and test your report, you may want to share it with other individuals.</span></span> <span data-ttu-id="7f39d-106">Para compartir el informe, necesita publicarlo, o *implementarlo*, en un servidor de informes o en un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7f39d-106">To share your report, you need to publish, or *deploy*, it to a report server or SharePoint site.</span></span> <span data-ttu-id="7f39d-107">Una vez publicado el informe, los usuarios que tengan permisos para el servidor de informes o en sitio de SharePoint podrán ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="7f39d-107">After it has been published, individuals who have permissions to the report server or the SharePoint site can run your report.</span></span> <span data-ttu-id="7f39d-108">Además, una persona que disponga de permisos de administrador para el servidor de informes puede crear suscripciones al informe para que éste se pueda actualizar y enviar a los usuarios de manera periódica.</span><span class="sxs-lookup"><span data-stu-id="7f39d-108">In addition, a person with administrator permissions on the report server can create subscriptions to your report so that the report can be updated and sent to users on a regular schedule.</span></span>  
  
 <span data-ttu-id="7f39d-109">Si usó un origen de datos compartido para crear el informe, debe publicarlo en la misma ubicación que el informe.</span><span class="sxs-lookup"><span data-stu-id="7f39d-109">If you used a shared data source to create your report, you need to publish it to the same location as the report.</span></span> <span data-ttu-id="7f39d-110">Al igual que los informes, los orígenes de datos compartidos se pueden administrar de forma independiente en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7f39d-110">Like reports, shared data sources can be managed separately on the report server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f39d-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7f39d-111">In This Section</span></span>  
 [<span data-ttu-id="7f39d-112">Obtener una vista previa de informes</span><span class="sxs-lookup"><span data-stu-id="7f39d-112">Previewing Reports</span></span>](previewing-reports.md)  
 <span data-ttu-id="7f39d-113">Describe cómo obtener una vista previa de un informe antes de publicarlo.</span><span class="sxs-lookup"><span data-stu-id="7f39d-113">Describes how to preview a report before you publish it.</span></span>  
  
 [<span data-ttu-id="7f39d-114">Publicar informes en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="7f39d-114">Publishing Reports to a Report Server</span></span>](publishing-reports-to-a-report-server.md)  
 <span data-ttu-id="7f39d-115">Describe cómo publicar un informe en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="7f39d-115">Describes how to publish a report to a report server.</span></span>  
  
 [<span data-ttu-id="7f39d-116">Ejemplos de dirección URL para los elementos de informe publicados en un servidor de informes en modo de SharePoint &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7f39d-116">URL Examples for Published Report Items on a Report Server in SharePoint Mode &#40;SSRS&#41;</span></span>](../tools/url-examples-for-items-on-a-report-server-sharepoint-mode.md)  
 <span data-ttu-id="7f39d-117">Describe cómo publicar un informe en un sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7f39d-117">Describes how to publish a report to a SharePoint site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f39d-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f39d-118">See Also</span></span>  
 <span data-ttu-id="7f39d-119">[Conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="7f39d-119">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="7f39d-120">[Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](../report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f39d-120">[Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="7f39d-121">[Diseño y representación de páginas &#40;Generador de informes y SSRS&#41;](../report-design/page-layout-and-rendering-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f39d-121">[Page Layout and Rendering &#40;Report Builder and SSRS&#41;](../report-design/page-layout-and-rendering-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7f39d-122">[Agregar datos a un informe &#40;Generador de informes y SSRS&#41;](../report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f39d-122">[Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="7f39d-123">[Buscar, ver y administrar informes &#40;Generador de informes y SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f39d-123">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7f39d-124">[Exportar informes &#40;Generador de informes y SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7f39d-124">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7f39d-125">Imprimir informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7f39d-125">Print Reports &#40;Report Builder and SSRS&#41;</span></span>](../report-builder/print-reports-report-builder-and-ssrs.md)  
  
  
