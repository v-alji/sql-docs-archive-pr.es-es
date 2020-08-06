---
title: Cambiar el alto de fila o el ancho de columna (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f061c204-5cd5-4467-9a9c-8a12803d93ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5d75a8101d07d7d6e81c624d08cd951277936eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675209"
---
# <a name="change-row-height-or-column-width-report-builder-and-ssrs"></a><span data-ttu-id="c69a8-102">Cambiar el alto de fila o el ancho de columna (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="c69a8-102">Change Row Height or Column Width (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c69a8-103">Cuando se establece un alto de fila, se está especificando el alto máximo para la fila en el informe representado.</span><span class="sxs-lookup"><span data-stu-id="c69a8-103">When you set a row height, you are specifying the maximum height for the row in the rendered report.</span></span> <span data-ttu-id="c69a8-104">Sin embargo, de forma predeterminada, los cuadros de texto de la fila están configurados para crecer verticalmente con objeto de dar cabida a sus datos en tiempo de ejecución, y esto puede ocasionar que una fila crezca más allá del alto especificado.</span><span class="sxs-lookup"><span data-stu-id="c69a8-104">However, by default, text boxes in the row are set to grow vertically to accommodate their data at run-time, and this can cause a row to expand beyond the height that you specify.</span></span> <span data-ttu-id="c69a8-105">Para establecer un alto de fila fijo, debe cambiar las propiedades del cuadro de texto de modo que no se expandan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c69a8-105">To set a fixed row height, you must change the text box properties so they do not automatically expand.</span></span>  
  
 <span data-ttu-id="c69a8-106">Cuando se establece un ancho de columna, se está especificando el ancho máximo para la columna en el informe representado.</span><span class="sxs-lookup"><span data-stu-id="c69a8-106">When you set a column width, you are specifying the maximum width for the column in the rendered report.</span></span> <span data-ttu-id="c69a8-107">Las columnas no se ajustan horizontalmente de forma automática para dar cabida al texto.</span><span class="sxs-lookup"><span data-stu-id="c69a8-107">Columns do not automatically adjust horizontally to accommodate text.</span></span>  
  
 <span data-ttu-id="c69a8-108">Si una celda de una fila o columna contiene un rectángulo o una región de datos, el alto y el ancho mínimos de la celda están determinados por el alto y el ancho del elemento contenido.</span><span class="sxs-lookup"><span data-stu-id="c69a8-108">If a cell in a row or column contains a rectangle or data region, the minimum height and width of the cell is determined by the height and width of the contained item.</span></span> <span data-ttu-id="c69a8-109">Para más información, vea [Comportamientos de la representación &#40;Generador de informes y SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c69a8-109">For more information, see [Rendering Behaviors &#40;Report Builder  and SSRS&#41;](rendering-behaviors-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-change-row-height-by-moving-row-handles"></a><span data-ttu-id="c69a8-110">Para cambiar la altura de la fila moviendo los identificadores de columna</span><span class="sxs-lookup"><span data-stu-id="c69a8-110">To change row height by moving row handles</span></span>  
  
1.  <span data-ttu-id="c69a8-111">En la vista Diseño, haga clic en cualquier punto de la región de datos Tablix para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="c69a8-111">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="c69a8-112">Aparecen identificadores de fila grises en el borde externo de la región de datos Tablix.</span><span class="sxs-lookup"><span data-stu-id="c69a8-112">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="c69a8-113">Mantenga el mouse sobre el borde del identificador de fila que desea expandir.</span><span class="sxs-lookup"><span data-stu-id="c69a8-113">Hover over the row handle edge that you want to expand.</span></span> <span data-ttu-id="c69a8-114">Aparece una flecha de dos puntas.</span><span class="sxs-lookup"><span data-stu-id="c69a8-114">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="c69a8-115">Haga clic para arrastrar el borde de la fila y muévalo más arriba o más abajo para ajustar el alto de fila.</span><span class="sxs-lookup"><span data-stu-id="c69a8-115">Click to grab the edge of the row and move it higher or lower to adjust the row height.</span></span>  
  
### <a name="to-change-row-height-by-setting-cell-properties"></a><span data-ttu-id="c69a8-116">Para cambiar la altura de la fila configurando las propiedades de la celda</span><span class="sxs-lookup"><span data-stu-id="c69a8-116">To change row height by setting cell properties</span></span>  
  
1.  <span data-ttu-id="c69a8-117">En la vista Diseño, haga clic en una celda de la fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c69a8-117">In Design view, click a cell in the table row.</span></span>  
  
     <span data-ttu-id="c69a8-118">![Celda seleccionada en una tabla](../media/table-selectcell.png "Celda seleccionada en una tabla")</span><span class="sxs-lookup"><span data-stu-id="c69a8-118">![Selected Cell in a Table](../media/table-selectcell.png "Selected Cell in a Table")</span></span>  
  
2.  <span data-ttu-id="c69a8-119">En el panel **Propiedades** que aparece, modifique la propiedad **Alto** y, después, haga clic en cualquier parte que no sea el panel **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="c69a8-119">In the **Properties** pane that displays, modify the **Height** property, and then click anywhere outside the **Properties** pane.</span></span>  
  
     <span data-ttu-id="c69a8-120">![Panel Propiedades para la celda de la tabla seleccionada](../media/cell-propertiespane.png "Panel Propiedades para la celda de la tabla seleccionada")</span><span class="sxs-lookup"><span data-stu-id="c69a8-120">![Properties Pane for selected table cell](../media/cell-propertiespane.png "Properties Pane for selected table cell")</span></span>  
  
### <a name="to-prevent-a-row-from-automatically-expanding-vertically"></a><span data-ttu-id="c69a8-121">Para evitar que una fila se expanda verticalmente de forma automática</span><span class="sxs-lookup"><span data-stu-id="c69a8-121">To prevent a row from automatically expanding vertically</span></span>  
  
1.  <span data-ttu-id="c69a8-122">En la vista Diseño, haga clic en cualquier punto de la región de datos Tablix para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="c69a8-122">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="c69a8-123">Aparecen identificadores de fila grises en el borde externo de la región de datos Tablix.</span><span class="sxs-lookup"><span data-stu-id="c69a8-123">Gray row handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="c69a8-124">Haga clic en el identificador de fila para seleccionar esta.</span><span class="sxs-lookup"><span data-stu-id="c69a8-124">Click the row handle to select the row.</span></span>  
  
3.  <span data-ttu-id="c69a8-125">En el panel de propiedades, establezca CanGrow en **False**.</span><span class="sxs-lookup"><span data-stu-id="c69a8-125">In the Properties pane, set CanGrow to **False**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c69a8-126">Si no puede ver el panel Propiedades, haga clic en **Propiedades** en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="c69a8-126">If you cannot see the Properties pane, from the **View** menu, click **Properties**.</span></span>  
  
### <a name="to-change-column-width"></a><span data-ttu-id="c69a8-127">Para cambiar el ancho de columna</span><span class="sxs-lookup"><span data-stu-id="c69a8-127">To change column width</span></span>  
  
1.  <span data-ttu-id="c69a8-128">En la vista Diseño, haga clic en cualquier punto de la región de datos Tablix para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="c69a8-128">In Design view, click anywhere in the tablix data region to select it.</span></span> <span data-ttu-id="c69a8-129">Aparecen identificadores de columna grises en el borde externo de la región de datos Tablix.</span><span class="sxs-lookup"><span data-stu-id="c69a8-129">Gray column handles appear on the outside border of the tablix data region.</span></span>  
  
2.  <span data-ttu-id="c69a8-130">Mantenga el mouse sobre el borde del identificador de columna que desea expandir.</span><span class="sxs-lookup"><span data-stu-id="c69a8-130">Hover over the column handle edge that you want to expand.</span></span> <span data-ttu-id="c69a8-131">Aparece una flecha de dos puntas.</span><span class="sxs-lookup"><span data-stu-id="c69a8-131">A double-headed arrow appears.</span></span>  
  
3.  <span data-ttu-id="c69a8-132">Haga clic para arrastrar el borde de la columna y muévalo hacia la derecha o hacia la izquierda para ajustar el ancho de columna.</span><span class="sxs-lookup"><span data-stu-id="c69a8-132">Click to grab the edge of the column and move it left or right to adjust the column width.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c69a8-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c69a8-133">See Also</span></span>  
 <span data-ttu-id="c69a8-134">[&#40;de la región de datos Tablix Generador de informes y SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c69a8-134">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c69a8-135">[Celdas, filas y columnas de la región de datos Tablix &#40;Generador de informes&#41; y SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c69a8-135">[Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c69a8-136">[Tablas &#40;Generador de informes y SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c69a8-136">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c69a8-137">[Matrices &#40;Generador de informes y SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c69a8-137">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c69a8-138">[Enumera &#40;Generador de informes y SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c69a8-138">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c69a8-139">Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c69a8-139">Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
