---
title: Acción de obtención de detalles (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10249"
- "10186"
- sql12.rtp.rptdesigner.calculatedseriesproperties.visibility.f1
- sql12.rtp.rptdesigner.seriesproperties.visibility.f1
- sql12.rtp.rptdesigner.chartareaproperties.visibility.f1
- "10092"
- sql12.rtp.rptdesigner.textboxproperties.visibility.f1
- sql12.rtp.rptdesigner.charttitleproperties.visibility.f1
- "10167"
- sql12.rtp.rptdesigner.rectangleproperties.visibility.f1
- "10174"
- sql12.rtp.rptdesigner.majorgridlineproperties.visibility.f1
- "10155"
- "10123"
- sql12.rtp.rptdesigner.subreportproperties.visibility.f1
- "10425"
- sql12.rtp.rptdesigner.minorgridlineproperties.visibility.f1
- "10217"
- sql12.rtp.rptdesigner.axisproperties.visibility.f1
- sql12.rtp.rptdesigner.serieslabelproperties.visibility.f1
- "10161"
- sql12.rtp.rptdesigner.chartproperties.visibility.f1
- sql12.rtp.rptdesigner.legendproperties.visibility.f1
- sql12.rtp.rptdesigner.pictureproperties.visibility.f1
- "10215"
- "10258"
- "10144"
- "10062"
- "10053"
ms.assetid: 1f8d1ef2-0daf-40c6-9ba7-3b391249bcd4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2fe3d55dc70a606df759c049b7b147820f0e3110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676351"
---
# <a name="drilldown-action-report-builder-and-ssrs"></a><span data-ttu-id="63e3a-102">Acción de obtención de detalles (generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="63e3a-102">Drilldown Action (Report Builder and SSRS)</span></span>
  <span data-ttu-id="63e3a-103">Si desea que los usuarios puedan ocultar y mostrar elementos de forma interactiva, incluya iconos más y menos en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="63e3a-103">B providing plus and minus icons on a text box, you can enable users to hide and display items interactively.</span></span> <span data-ttu-id="63e3a-104">Esto se denomina acción *de obtención de detalles* .</span><span class="sxs-lookup"><span data-stu-id="63e3a-104">This is called a *drilldown* action.</span></span> <span data-ttu-id="63e3a-105">En una tabla o matriz, puede mostrar u ocultar filas y columnas estáticas, o filas y columnas que están asociadas a grupos.</span><span class="sxs-lookup"><span data-stu-id="63e3a-105">For a table or matrix, you can show or hide static rows and columns, or rows and columns that are associated with groups.</span></span>  
  
 <span data-ttu-id="63e3a-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span><span class="sxs-lookup"><span data-stu-id="63e3a-106">![rs_drilldown](../media/rs-drilldown.gif "rs_drilldown")</span></span>  
  
 <span data-ttu-id="63e3a-107">En esta ilustración, el usuario hace clic en los signos más (+) del informe para mostrar datos detallados.</span><span class="sxs-lookup"><span data-stu-id="63e3a-107">In this illustration, the user clicks the plus signs (+) in the report to show detail data.</span></span>  
  
 <span data-ttu-id="63e3a-108">Por ejemplo, en una tabla con grupos de filas puede ocultar inicialmente todas las filas excepto la fila de resumen del grupo externo.</span><span class="sxs-lookup"><span data-stu-id="63e3a-108">For example, you can initially hide all the rows except the outer group summary row for a table with row groups.</span></span> <span data-ttu-id="63e3a-109">Para cada grupo interno (incluido el grupo de detalles), agregue un icono de expansión/contracción a la celda de agrupamiento del grupo contenedor.</span><span class="sxs-lookup"><span data-stu-id="63e3a-109">For each inner group (including the details group), add an expand/collapse icon to the grouping cell of the containing group.</span></span> <span data-ttu-id="63e3a-110">Cuando se representa el informe, el usuario puede hacer clic en el cuadro de texto para expandir y contraer los datos detallados.</span><span class="sxs-lookup"><span data-stu-id="63e3a-110">When the report is rendered, the user can click the text box to expand and collapse the detail data.</span></span> <span data-ttu-id="63e3a-111">Para más información, vea [Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="63e3a-111">For more information, see [Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="63e3a-112">Para permitir a los usuarios expandir o contraer un elemento, debe establecer las propiedades de visibilidad del elemento.</span><span class="sxs-lookup"><span data-stu-id="63e3a-112">To allow users to expand or collapse an item, you set the visibility properties for that item.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63e3a-113">Cuando se crea un informe con una acción de obtención de detalles, la información de visibilidad debe establecerse para el grupo, la columna o la fila que se desee ocultar, no para un único cuadro de texto de la fila o de la columna.</span><span class="sxs-lookup"><span data-stu-id="63e3a-113">When you create a report with a drilldown action, the visibility information must be set on the group, column, or row that you want to hide, not just a single text box in the row or column.</span></span> <span data-ttu-id="63e3a-114">Además, el cuadro de texto que se use para el control de alternancia debe estar en un ámbito contenedor que controle el elemento que se desee mostrar u ocultar.</span><span class="sxs-lookup"><span data-stu-id="63e3a-114">In addition, the text box that you use for the toggle must be in a containing scope that controls the item that you want to show or hide.</span></span>  
>   
>  <span data-ttu-id="63e3a-115">Por ejemplo, para ocultar una fila asociada a un grupo anidado, el cuadro de texto debe estar en una fila asociada con el grupo primario o uno superior en la jerarquía de inclusión.</span><span class="sxs-lookup"><span data-stu-id="63e3a-115">For example, to hide a row associated with a nested group, the text box must be in a row associated with the parent group or higher in the containment hierarchy.</span></span>  
>   
>  <span data-ttu-id="63e3a-116">Para más información sobre cómo configurar la información de visibilidad en el grupo, la columna o la fila, vea [Agregar una acción de expandir y contraer a un elemento &#40;Generador de informes y SSRS&#41;](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="63e3a-116">For information on setting visibility information on the group, column or row, see [Add an Expand or Collapse Action to an Item &#40;Report Builder and SSRS&#41;](add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md)</span></span>  
  
 <span data-ttu-id="63e3a-117">Para más información sobre cómo ocultar elementos de informes, vea [Ocultar un elemento &#40;Generador de informes y SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="63e3a-117">For more information about hiding report items, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="comparing-drilldown-and-drillthrough-reports"></a><span data-ttu-id="63e3a-118">Comparar informes de obtención de detalles con informes detallados</span><span class="sxs-lookup"><span data-stu-id="63e3a-118">Comparing Drilldown and Drillthrough Reports</span></span>  
 <span data-ttu-id="63e3a-119">En un informe de obtención de detalles, un usuario hace clic en un botón de más o menos para expandir o contraer una sección de un informe para mostrar los datos detallados.</span><span class="sxs-lookup"><span data-stu-id="63e3a-119">In a drilldown report, a user clicks a plus or minus button to expand or collapse a section of a report to show detail data in place.</span></span> <span data-ttu-id="63e3a-120">En un informe detallado, el usuario hace clic en un vínculo para obtener un valor de resumen y este abre un informe relacionado independiente con los datos detallados.</span><span class="sxs-lookup"><span data-stu-id="63e3a-120">In a drillthrough report, the user clicks a link for a summary value, and this opens a separate, related report to show detail data.</span></span> <span data-ttu-id="63e3a-121">Estos datos solo se recuperan al ejecutar el informe de detalles.</span><span class="sxs-lookup"><span data-stu-id="63e3a-121">The detail data is only retrieved when the detail report runs.</span></span> <span data-ttu-id="63e3a-122">Generalmente, los informes detallados requieren menos recursos que los informes de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="63e3a-122">Drillthrough reports typically require fewer resources than drilldown reports.</span></span> <span data-ttu-id="63e3a-123">Para obtener más información, vea [Obtención de detalles, informes detallados, subinformes y regiones de datos anidadas &#40;Generador de informes y SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span><span class="sxs-lookup"><span data-stu-id="63e3a-123">For more information, see [Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md).</span></span>  
  
## <a name="rendering-extension-support-for-hidden-report-items"></a><span data-ttu-id="63e3a-124">Compatibilidad con extensiones de representación para elementos de informe ocultos</span><span class="sxs-lookup"><span data-stu-id="63e3a-124">Rendering Extension Support for Hidden Report Items</span></span>  
 <span data-ttu-id="63e3a-125">La alternancia mostrar u ocultar en los elementos de informe solo es compatible con las extensiones de representación que admiten la interactividad del usuario como, por ejemplo, la extensión de representación en HTML que se utiliza cuando se ejecuta un informe en el Generador de informes o en el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="63e3a-125">The show-and-hide toggle on report items is supported only by rendering extensions that support user interactivity, such as the HTML rendering extension that is used when you run a report in Report Builder and in Report Manager, for example.</span></span> <span data-ttu-id="63e3a-126">Otras extensiones de representación muestran elementos ocultos.</span><span class="sxs-lookup"><span data-stu-id="63e3a-126">Other rendering extensions display hidden items.</span></span> <span data-ttu-id="63e3a-127">En la lista siguiente se describe la compatibilidad para los elementos de informe con visibilidad condicional:</span><span class="sxs-lookup"><span data-stu-id="63e3a-127">The following list describes support for report items with conditional visibility:</span></span>  
  
-   <span data-ttu-id="63e3a-128">En HTML, si los elementos están ocultos, no estarán visibles en el código fuente HTML.</span><span class="sxs-lookup"><span data-stu-id="63e3a-128">In HTML, if items are hidden, they are not visible in the HTML source.</span></span>  
  
-   <span data-ttu-id="63e3a-129">La extensión de representación en XML muestra todos los elementos de informe, independientemente de si están ocultos o no.</span><span class="sxs-lookup"><span data-stu-id="63e3a-129">The XML rendering extension displays all report items, regardless of whether they are hidden.</span></span>  
  
-   <span data-ttu-id="63e3a-130">La extensión de representación en Excel muestra y expande filas y columnas ocultas en una tabla, matriz o lista.</span><span class="sxs-lookup"><span data-stu-id="63e3a-130">The Excel rendering extension displays and expands hidden rows and columns for a table, matrix, or list.</span></span> <span data-ttu-id="63e3a-131">Todas las filas y columnas están visibles.</span><span class="sxs-lookup"><span data-stu-id="63e3a-131">All rows and columns are visible.</span></span>  
  
 <span data-ttu-id="63e3a-132">Para más información, vea [Comportamientos de la representación &#40;Generador de informes y SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="63e3a-132">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e3a-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63e3a-133">See Also</span></span>  
 <span data-ttu-id="63e3a-134">[Obtención de detalles, informes detallados, subinformes y regiones de datos anidadas &#40;Generador de informes y SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span><span class="sxs-lookup"><span data-stu-id="63e3a-134">[Drillthrough, Drilldown, Subreports, and Nested Data Regions &#40;Report Builder and SSRS&#41;](drillthrough-drilldown-subreports-and-nested-data-regions.md) </span></span>  
 <span data-ttu-id="63e3a-135">[Ordenación interactiva, mapas de documento y vínculos &#40;Generador de informes y SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="63e3a-135">[Interactive Sort, Document Maps, and Links &#40;Report Builder and SSRS&#41;](interactive-sort-document-maps-and-links-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="63e3a-136">Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="63e3a-136">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  
  
  
