---
title: Mostrar encabezados de fila y de columna en varias páginas (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2422b1e2-822f-4379-9d7f-9afebb350e3f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e3b38aa0faab267a0cd71feafe600829237b55c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748003"
---
# <a name="display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs"></a><span data-ttu-id="dc3a4-102">Mostrar encabezados de fila y de columna en varias páginas (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="dc3a4-102">Display Row and Column Headers on Multiple Pages (Report Builder and SSRS)</span></span>
  <span data-ttu-id="dc3a4-103">Puede controlar si se deben repetir los encabezados de fila y de columna en cada página de una región de datos Tablix que abarca varias páginas.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-103">You can control whether to repeat row and column headers on every page for a tablix data region that spans multiple pages.</span></span> <span data-ttu-id="dc3a4-104">Una región de datos Tablix puede ser una tabla, una matriz o una lista.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-104">A tablix data region can be a table, matrix, or list.</span></span>  
  
 <span data-ttu-id="dc3a4-105">El modo en que controle las filas y las columnas dependerá de si la región de datos Tablix tiene encabezados de grupo.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-105">How you control the rows and columns depends on whether the tablix data region has group headers.</span></span> <span data-ttu-id="dc3a4-106">Al hacer clic en una región de datos Tablix que tiene encabezados de grupo, una línea de puntos muestra las áreas Tablix, como se muestra en la figura siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc3a4-106">When you click in a tablix data region that has group headers, a dotted line shows the tablix areas, as shown in the following figure:</span></span>  
  
 <span data-ttu-id="dc3a4-107">![Descripción de las áreas de la región de datos Tablix](../media/rs-tablixareas.gif "Descripción de las áreas de la región de datos Tablix")</span><span class="sxs-lookup"><span data-stu-id="dc3a4-107">![Tablix data region areas](../media/rs-tablixareas.gif "Tablix data region areas")</span></span>  
  
 <span data-ttu-id="dc3a4-108">Los encabezados de grupo de filas y de columnas se crean automáticamente al agregar los grupos usando el asistente Nueva tabla o matriz o el asistente Nuevo gráfico, agregando los campos al Panel de agrupación o usando los menús contextuales.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-108">Row and column group headers are created automatically when you add groups by using the New Table or Matrix wizard or the New Chart wizard, by adding fields to the Grouping pane, or by using context menus.</span></span> <span data-ttu-id="dc3a4-109">Si la región de datos Tablix tiene solamente un área de cuerpo de Tablix y ningún encabezado de grupo, las filas y columnas son miembros de Tablix.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-109">If the tablix data region has only a tablix body area and no group headers, the rows and columns are tablix members.</span></span>  
  
 <span data-ttu-id="dc3a4-110">Para los miembros estáticos, puede mostrar la parte superior de las filas adyacentes o las columnas adyacentes las laterales en varias páginas.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-110">For static members, you can display the top adjacent rows or the side adjacent columns on multiple pages.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-row-headers-on-multiple-pages"></a><span data-ttu-id="dc3a4-111">Para mostrar encabezados de fila en varias páginas</span><span class="sxs-lookup"><span data-stu-id="dc3a4-111">To display row headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="dc3a4-112">Haga clic con el botón derecho en la fila o columna o en el controlador de tabla de una región de datos Tablix y, después, haga clic en **Propiedades de Tablix**.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-112">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="dc3a4-113">En **Encabezados de fila**, seleccione **Repetir filas de encabezado en todas las páginas**.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-113">In **Row Headers**, select **Repeat header rows on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-column-headers-on-multiple-pages"></a><span data-ttu-id="dc3a4-114">Para mostrar encabezados de columna en varias páginas</span><span class="sxs-lookup"><span data-stu-id="dc3a4-114">To display column headers on multiple pages</span></span>  
  
1.  <span data-ttu-id="dc3a4-115">Haga clic con el botón derecho en la fila o columna o en el controlador de tabla de una región de datos Tablix y, después, haga clic en **Propiedades de Tablix**.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-115">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="dc3a4-116">En **Encabezados de columna**, seleccione **Repetir columnas de encabezado en todas las páginas**.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-116">In **Column Headers**, select **Repeat header columns on each page**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-display-a-static-tablix-member-row-or-column-on-multiple-pages"></a><span data-ttu-id="dc3a4-117">Para mostrar un miembro de Tablix estático (fila o columna) en varias páginas</span><span class="sxs-lookup"><span data-stu-id="dc3a4-117">To display a static tablix member (row or column) on multiple pages</span></span>  
  
1.  <span data-ttu-id="dc3a4-118">En la superficie de diseño, haga clic en el controlador de fila o de columna de la región de datos Tablix para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-118">On the design surface, click the row or column handle of the tablix data region to select it.</span></span> <span data-ttu-id="dc3a4-119">El Panel de agrupación muestra los grupos de filas y de columnas.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-119">The Grouping pane displays the row and column groups.</span></span>  
  
2.  <span data-ttu-id="dc3a4-120">En el lado derecho del panel Agrupación, haga clic en la flecha abajo y, a continuación, haga clic en **Modo avanzado**.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-120">On the right side of the Grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span> <span data-ttu-id="dc3a4-121">El panel Grupos de filas muestra los miembros jerárquicos estáticos y dinámicos de la jerarquía de grupos de fila, mientras que el panel Grupos de columnas muestra una vista similar de la jerarquía de grupos de columna.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
3.  <span data-ttu-id="dc3a4-122">Haga clic en el miembro estático que corresponde al miembro estático (fila o columna) que desea que se mantenga visible durante el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-122">Click the static member that corresponds to the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="dc3a4-123">El panel de propiedades muestra las propiedades de **Miembro de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="dc3a4-123">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="dc3a4-124">Si no ve el panel Propiedades, haga clic en la pestaña **Ver** en la parte superior de la ventana del Generador de informes y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-124">If you don't see the Properties pane, click the **View** tab at the top of the Report Builder window and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="dc3a4-125">En el panel Propiedades, configure **RepeatOnNewPage** en True.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-125">In the Properties pane, set **RepeatOnNewPage** to True.</span></span>  
  
5.  <span data-ttu-id="dc3a4-126">Establezca **KeepWithGroup** en Después.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-126">Set **KeepWithGroup** to After.</span></span>  
  
6.  <span data-ttu-id="dc3a4-127">Repita este paso para todos los miembros adyacentes que desee repetir.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-127">Repeat this for as many adjacent members as you want to repeat.</span></span>  
  
7.  <span data-ttu-id="dc3a4-128">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-128">Preview the report.</span></span>  
  
 <span data-ttu-id="dc3a4-129">Cuando ve cada página del informe que abarca la región de datos Tablix, los miembros estáticos de Tablix se repiten en cada página.</span><span class="sxs-lookup"><span data-stu-id="dc3a4-129">As you view each page of the report that the tablix data region spans, the static tablix members repeat on each page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc3a4-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc3a4-130">See Also</span></span>  
 <span data-ttu-id="dc3a4-131">[Buscar, ver y administrar informes &#40;Generador de informes y SSRS&#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dc3a4-131">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dc3a4-132">[Exportar informes &#40;Generador de informes y SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dc3a4-132">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dc3a4-133">[Controlar saltos de página, encabezados, columnas y filas &#40;Generador de informes y SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dc3a4-133">[Controlling Page Breaks, Headings, Columns, and Rows &#40;Report Builder and SSRS&#41;](controlling-page-breaks-headings-columns-and-rows-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="dc3a4-134">[Mostrar encabezados y pies de página con un grupo &#40;Generador de informes y SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="dc3a4-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="dc3a4-135">Mantener visibles los encabezados al desplazarse a través de un informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="dc3a4-135">Keep Headers Visible When Scrolling Through a Report &#40;Report Builder and SSRS&#41;</span></span>](keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs.md)  
  
  
