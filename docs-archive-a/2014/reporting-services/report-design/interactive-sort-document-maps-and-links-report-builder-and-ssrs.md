---
title: Ordenación interactiva, mapas de documento y vínculos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: cc6ef408-4a76-408a-9d3f-033481fe21cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 35d88e89ed14a205153374d44562e6d3fda92e02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749095"
---
# <a name="interactive-sort-document-maps-and-links-report-builder-and-ssrs"></a><span data-ttu-id="c2a8f-102">Ordenación interactiva, mapas de documento y vínculos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="c2a8f-102">Interactive Sort, Document Maps, and Links (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c2a8f-103">En entornos basados en web, puede agregar varias características que permitan a los usuarios interactuar con los informes.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-103">In Web-based environments, you can add a number of features that let your users interact with reports.</span></span> <span data-ttu-id="c2a8f-104">Los usuarios pueden cambiar el criterio de ordenación de los valores del informe, mostrar u ocultar elementos del informe o hacer clic en vínculos que llevan a otros informes con páginas web.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-104">Your users can change the sort order of values in your report, show or hide items in the report, or click links that go to other reports or Web pages.</span></span> <span data-ttu-id="c2a8f-105">También puede agregar una tabla de contenido o mapa de documento.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-105">You can also add a table of contents or document map.</span></span> <span data-ttu-id="c2a8f-106">Los usuarios de los informes pueden hacer clic en los elementos de la tabla de contenido o el mapa de documento para desplazarse a las distintas áreas de un informe.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-106">Your report users can click items in the table of contents or document map to jump to areas within a report.</span></span>  
  
 <span data-ttu-id="c2a8f-107">El Generador de informes y el Diseñador de informes admiten tres tipos de vínculos con las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2a8f-107">Report Builder and Report Designer support three types of links with the following actions:</span></span>  
  
-   <span data-ttu-id="c2a8f-108">**Vínculos de marcador** : saltan a otras áreas del informe.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-108">**Bookmark links** Jump to other areas within the report.</span></span>  
  
-   <span data-ttu-id="c2a8f-109">**Hipervínculos** : saltan a direcciones URL que especifican la dirección de páginas web o informes de un servidor de informes usando el acceso URL.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-109">**Hyperlinks** Jump to URLs that specify the address of Web pages or reports on a report server by using URL access.</span></span>  
  
-   <span data-ttu-id="c2a8f-110">**Vínculos de informe detallado** : saltan a otros informes del mismo servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-110">**Drillthrough report links** Jump to other reports on the same report server.</span></span> <span data-ttu-id="c2a8f-111">Para más información, vea [Informes detallados &#40;Generador de informes y SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c2a8f-111">For more information, see [Drillthrough Reports &#40;Report Builder and SSRS&#41;](drillthrough-reports-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2a8f-112">Los vínculos que se enlazan a los campos de conjunto de datos pueden ser vulnerables a la alteración con fines malintencionados.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-112">Links that are bound to dataset fields can be vulnerable to tampering for malicious purposes.</span></span> <span data-ttu-id="c2a8f-113">Para más información, vea [Proteger informes y recursos](../security/secure-reports-and-resources.md) en los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Libros en pantalla](https://go.microsoft.com/fwlink/?LinkId=154888) en msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-113">For more information, see [Secure Reports and Resources](../security/secure-reports-and-resources.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][Books Online](https://go.microsoft.com/fwlink/?LinkId=154888) on msdn.microsoft.com.</span></span>  
  
 <span data-ttu-id="c2a8f-114">Si también desea permitir que los usuarios controlen la presentación y el contenido del informe, diseñe expresiones de ordenación, filtrado y visibilidad que incluyan referencias a los parámetros.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-114">You can also let your users control report display and content by designing expressions that include parameter references for sort, filter, and visibility.</span></span> <span data-ttu-id="c2a8f-115">Para más información, vea [Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-parameters-report-builder-and-report-designer.md), [Filtrar, agrupar y ordenar datos &#40;Generador de informes y SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) y [Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span><span class="sxs-lookup"><span data-stu-id="c2a8f-115">For more information, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md), [Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md), and [Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="c2a8f-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c2a8f-116">In This Section</span></span>  
 [<span data-ttu-id="c2a8f-117">Ordenación interactiva &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c2a8f-117">Interactive Sort &#40;Report Builder and SSRS&#41;</span></span>](interactive-sort-report-builder-and-ssrs.md)  
 <span data-ttu-id="c2a8f-118">Describe cómo agregar botones de ordenación interactiva a los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-118">Explains how to add interactive sort buttons to column headers.</span></span>  
  
 [<span data-ttu-id="c2a8f-119">Crear un mapa del documento &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c2a8f-119">Create a Document Map &#40;Report Builder and SSRS&#41;</span></span>](create-a-document-map-report-builder-and-ssrs.md)  
 <span data-ttu-id="c2a8f-120">Describe cómo agregar una tabla de contenido para poder navegar en informes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-120">Explains how to add a table of contents to support navigation in a large report.</span></span>  
  
 [<span data-ttu-id="c2a8f-121">Agregar un marcador a un informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c2a8f-121">Add a Bookmark to a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-bookmark-to-a-report-report-builder-and-ssrs.md)  
 <span data-ttu-id="c2a8f-122">Explica cómo agregar marcadores para crear vínculos dentro de un informe.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-122">Explains how to add bookmarks to create links within a report.</span></span>  
  
 [<span data-ttu-id="c2a8f-123">Agregar un hipervínculo a una dirección URL &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c2a8f-123">Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;</span></span>](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md)  
 <span data-ttu-id="c2a8f-124">Explica cómo agregar un vínculo del informe a una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="c2a8f-124">Explains how to add a link from your report to a URL</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a8f-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2a8f-125">See Also</span></span>  
 [<span data-ttu-id="c2a8f-126">Obtención de detalles, informes detallados, subinformes y regiones de datos anidadas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c2a8f-126">Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;</span></span>](drillthrough-drilldown-subreports-and-nested-data-regions.md)  
  
  
