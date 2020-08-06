---
title: Mantener visibles los encabezados al desplazarse a través de un informe (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 6d9192a4-fd5c-41ad-b9ef-f88f9496afed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d37fcd38a402dc0f88ac002c679c1046d5b0b583
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749090"
---
# <a name="keep-headers-visible-when-scrolling-through-a-report-report-builder-and-ssrs"></a><span data-ttu-id="38b3e-102">Mantener visibles los encabezados al desplazarse a través de un informe (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="38b3e-102">Keep Headers Visible When Scrolling Through a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="38b3e-103">Para evitar que las etiquetas de fila y de columna se desplacen fuera de la vista después de representar un informe, puede inmovilizar los encabezados de fila o de columna.</span><span class="sxs-lookup"><span data-stu-id="38b3e-103">To prevent row and column labels from scrolling out of view after rendering a report, you can freeze the row or column headings.</span></span>  
  
 <span data-ttu-id="38b3e-104">La forma de controlar las filas y las columnas depende de si tiene una tabla o una matriz.</span><span class="sxs-lookup"><span data-stu-id="38b3e-104">How you control the rows and columns depends on whether you have a table or a matrix.</span></span> <span data-ttu-id="38b3e-105">Si tiene una tabla, configure los miembros estáticos (encabezados de fila y columna) para que sigan siendo visibles.</span><span class="sxs-lookup"><span data-stu-id="38b3e-105">If you have a table, you configure static members (row and column headings) to remain visible.</span></span> <span data-ttu-id="38b3e-106">Si tiene una matriz, configure los encabezados de grupos de filas y columnas para que sigan siendo visibles.</span><span class="sxs-lookup"><span data-stu-id="38b3e-106">If you have a matrix, you configure row and column group headers to remain visible.</span></span>  
  
 <span data-ttu-id="38b3e-107">Si exporta el informe a Excel, el encabezado no se inmovilizará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="38b3e-107">If you export the report to Excel, the header will not be frozen automatically.</span></span> <span data-ttu-id="38b3e-108">Puede inmovilizar el panel en Excel.</span><span class="sxs-lookup"><span data-stu-id="38b3e-108">You can freeze the pane in Excel.</span></span> <span data-ttu-id="38b3e-109">Para más información, vea la sección **Encabezados y pies de página** de [Exportar a Microsoft Excel &#40;Generador de informes y SSRS&#41;](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="38b3e-109">For more information see the **Page Headers and Footers** section of [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](../report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="38b3e-110">Aunque una tabla tenga grupos de filas y columnas, no puede mantener esos encabezados de grupo visible durante el desplazamiento</span><span class="sxs-lookup"><span data-stu-id="38b3e-110">Even if a table has row and column groups, you cannot keep those group headers visible while scrolling</span></span>  
  
 <span data-ttu-id="38b3e-111">En la ilustración siguiente se muestra una tabla.</span><span class="sxs-lookup"><span data-stu-id="38b3e-111">The following image shows a table.</span></span>  
  
 <span data-ttu-id="38b3e-112">![Table](../media/table.png "Tabla")</span><span class="sxs-lookup"><span data-stu-id="38b3e-112">![Table](../media/table.png "Table")</span></span>  
  
 <span data-ttu-id="38b3e-113">En la ilustración siguiente se muestra una matriz.</span><span class="sxs-lookup"><span data-stu-id="38b3e-113">The following image shows a matrix.</span></span>  
  
 <span data-ttu-id="38b3e-114">![Matriz](../media/matrix.png "Matrix")</span><span class="sxs-lookup"><span data-stu-id="38b3e-114">![Matrix](../media/matrix.png "Matrix")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-keep-matrix-group-headers-visible-while-scrolling"></a><span data-ttu-id="38b3e-115">Para mantener visibles los encabezados de grupo de matrices al desplazarse</span><span class="sxs-lookup"><span data-stu-id="38b3e-115">To keep matrix group headers visible while scrolling</span></span>  
  
1.  <span data-ttu-id="38b3e-116">Haga clic con el botón derecho en la fila o columna o en el controlador de tabla de una región de datos Tablix y, después, haga clic en **Propiedades de Tablix**.</span><span class="sxs-lookup"><span data-stu-id="38b3e-116">Right-click the row, column, or corner handle of a tablix data region, and then click **Tablix Properties**.</span></span>  
  
2.  <span data-ttu-id="38b3e-117">En la pestaña **General** , bajo **Encabezados de fila** o **Encabezados de columna**, seleccione **El encabezado debe permanecer visible durante el desplazamiento**.</span><span class="sxs-lookup"><span data-stu-id="38b3e-117">On the **General** tab, under **Row Headers** or **Column Headers**, select **Header should remain visible while scrolling**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-keep-a-static-tablix-member-row-or-column-visible-while-scrolling"></a><span data-ttu-id="38b3e-118">Para mantener visible mientras se desplaza un miembro de Tablix estático (fila o columna)</span><span class="sxs-lookup"><span data-stu-id="38b3e-118">To keep a static tablix member (row or column) visible while scrolling</span></span>  
  
1.  <span data-ttu-id="38b3e-119">En la superficie de diseño, haga clic en cualquier lugar de la tabla para mostrar los miembros estáticos, así como los grupos, en el panel agrupación.</span><span class="sxs-lookup"><span data-stu-id="38b3e-119">On the design surface, click anywhere in the table to display static members, as well as groups, in the grouping pane.</span></span>  
  
     <span data-ttu-id="38b3e-120">![Panel de agrupación](../media/grouppane-updated.png "Panel de agrupación")</span><span class="sxs-lookup"><span data-stu-id="38b3e-120">![Grouping pane](../media/grouppane-updated.png "Grouping pane")</span></span>  
  
     <span data-ttu-id="38b3e-121">El panel Grupos de filas muestra los miembros jerárquicos estáticos y dinámicos de la jerarquía de grupos de fila, mientras que el panel Grupos de columnas muestra una vista similar de la jerarquía de grupos de columna.</span><span class="sxs-lookup"><span data-stu-id="38b3e-121">The Row Groups pane displays the hierarchical static and dynamic members for the row groups hierarchy, and the Column groups pane shows a similar display for the column groups hierarchy.</span></span>  
  
2.  <span data-ttu-id="38b3e-122">En el lado derecho del panel de agrupación, haga clic en la flecha abajo y, a continuación, haga clic en **Modo avanzado**.</span><span class="sxs-lookup"><span data-stu-id="38b3e-122">On the right side of the grouping pane, click the down arrow, and then click **Advanced Mode**.</span></span>  
  
3.  <span data-ttu-id="38b3e-123">Haga clic en el miembro estático (fila o columna) que desea que siga siendo visible durante el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="38b3e-123">Click the static member (row or column) that you want to remain visible while scrolling.</span></span> <span data-ttu-id="38b3e-124">El panel de propiedades muestra las propiedades de **Miembro de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="38b3e-124">The Properties pane displays the **Tablix Member** properties.</span></span>  
  
     <span data-ttu-id="38b3e-125">![Propiedades de Miembro de Tablix](../media/grouppane-tablixmember-updated.png "Propiedades de Miembro de Tablix")</span><span class="sxs-lookup"><span data-stu-id="38b3e-125">![Tablix Member properties](../media/grouppane-tablixmember-updated.png "Tablix Member properties")</span></span>  
  
4.  <span data-ttu-id="38b3e-126">En el panel Propiedades, establezca **FixedData** en `True` .</span><span class="sxs-lookup"><span data-stu-id="38b3e-126">In the Properties pane, set **FixedData** to `True`.</span></span>  
  
5.  <span data-ttu-id="38b3e-127">Repita esto con tantos miembros adyacentes como desee que sean visibles durante el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="38b3e-127">Repeat this for as many adjacent members as you want to keep visible while scrolling.</span></span>  
  
6.  <span data-ttu-id="38b3e-128">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="38b3e-128">Preview the report.</span></span>  
  
 <span data-ttu-id="38b3e-129">Cuando recorra el informe, los miembros de Tablix estáticos permanecerán visibles.</span><span class="sxs-lookup"><span data-stu-id="38b3e-129">As you page down or across the report, the static tablix members remain in view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38b3e-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38b3e-130">See Also</span></span>  
 <span data-ttu-id="38b3e-131">[Región de datos Tablix &#40;Generador de informes y SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="38b3e-131">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="38b3e-132">[Buscar, ver y administrar informes &#40;Generador de informes y SSRS&#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="38b3e-132">[Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="38b3e-133">[Exportar informes &#40;Generador de informes y SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="38b3e-133">[Exporting Reports &#40;Report Builder and SSRS&#41;](../report-builder/export-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="38b3e-134">[Mostrar encabezados y pies de página con un grupo &#40;Generador de informes y SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="38b3e-134">[Display Headers and Footers with a Group &#40;Report Builder and SSRS&#41;](display-headers-and-footers-with-a-group-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="38b3e-135">[Mostrar encabezados de fila y de columna en varias páginas &#40;Generador de informes y SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="38b3e-135">[Display Row and Column Headers on Multiple Pages &#40;Report Builder and SSRS&#41;](display-row-and-column-headers-on-multiple-pages-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="38b3e-136">Panel de agrupación &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="38b3e-136">Grouping Pane &#40;Report Builder&#41;</span></span>](grouping-pane-report-builder.md)  
  
  
