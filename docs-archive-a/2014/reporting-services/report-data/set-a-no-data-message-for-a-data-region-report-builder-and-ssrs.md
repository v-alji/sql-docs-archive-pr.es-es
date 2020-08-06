---
title: Establecer un mensaje para cuando no hay datos en una región de datos (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4b194714-46f7-4f0e-9632-7f89d9600762
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9ed38ef14eb8f89753b4b3d7af3324ef0e88fa52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745052"
---
# <a name="set-a-no-data-message-for-a-data-region-report-builder-and-ssrs"></a><span data-ttu-id="1ef50-102">Establecer un mensaje para cuando no hay datos en una región de datos (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="1ef50-102">Set a No Data Message for a Data Region (Report Builder and SSRS)</span></span>
  <span data-ttu-id="1ef50-103">Cuando quiera especificar el texto que se debe mostrar en el informe representado en lugar de una región de datos que no tiene datos, establezca la propiedad NoRowsMessage para una región de datos de tabla, matriz o lista, la propiedad NoDataMessage para una región de datos de gráfico y la propiedad NoDataText para la escala de colores de un mapa.</span><span class="sxs-lookup"><span data-stu-id="1ef50-103">When you want to specify text to show in the rendered report in place of a data region that has no data, set the NoRowsMessage property for a table, matrix, or list data region, the NoDataMessage for a chart data region, and the NoDataText for the color scale for a map.</span></span> <span data-ttu-id="1ef50-104">En tiempo de ejecución, el procesador de informes ejecuta la consulta para cada conjunto de datos de un informe y la consulta del conjunto de datos puede no generar ningún conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="1ef50-104">At run time, the report processor runs the query for each dataset in a report and the dataset query may produce no result set.</span></span> <span data-ttu-id="1ef50-105">En las regiones de datos enlazadas a conjuntos de datos vacíos, es posible especificar el texto que se debe mostrar en lugar de mostrar una región de datos vacía.</span><span class="sxs-lookup"><span data-stu-id="1ef50-105">For a data region bound to an empty dataset, you can specify text to display instead of displaying an empty data region.</span></span> <span data-ttu-id="1ef50-106">También se puede establecer la propiedad NoRowsMessage para un subinforme cuando ningún conjunto de datos de dicho subinforme tenga datos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ef50-106">You can also set the NoRowsMessage property for a subreport when no datasets in the subreport have data at run time.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-norowsmessage-property-for-a-table-matrix-or-list"></a><span data-ttu-id="1ef50-107">Para establecer la propiedad NoRowsMessage para una tabla, una matriz o una lista</span><span class="sxs-lookup"><span data-stu-id="1ef50-107">To set the NoRowsMessage property for a table, matrix, or list</span></span>  
  
1.  <span data-ttu-id="1ef50-108">En la vista Diseño, haga clic en la región de datos de tabla, matriz o lista o en el subinforme en la superficie de diseño para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="1ef50-108">In Design view, click the table, matrix, or list data region or subreport on the design surface to select it.</span></span> <span data-ttu-id="1ef50-109">Las propiedades del elemento seleccionado aparecen en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="1ef50-109">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="1ef50-110">En el panel Propiedades, escriba el texto que desea mostrar como mensaje en el campo de `NoRowsMessage` propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ef50-110">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="1ef50-111">Como alternativa, en la lista desplegable, haga clic en **Expresión** para abrir el cuadro de diálogo **Expresión** y crear una expresión.</span><span class="sxs-lookup"><span data-stu-id="1ef50-111">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatamessage-property-for-a-chart"></a><span data-ttu-id="1ef50-112">Para establecer la propiedad NoDataMessage para un gráfico</span><span class="sxs-lookup"><span data-stu-id="1ef50-112">To set the NoDataMessage property for a chart</span></span>  
  
1.  <span data-ttu-id="1ef50-113">En la vista Diseño, haga clic en el gráfico en la superficie de diseño para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="1ef50-113">In Design view, click the chart on the design surface to select it.</span></span> <span data-ttu-id="1ef50-114">Las propiedades del elemento seleccionado aparecen en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="1ef50-114">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="1ef50-115">En el panel Propiedades, expanda el nodo de `NoDataMessage` .</span><span class="sxs-lookup"><span data-stu-id="1ef50-115">In the Properties pane, expand the node for `NoDataMessage`.</span></span>  
  
3.  <span data-ttu-id="1ef50-116">En **título**, escriba el texto que desea mostrar como mensaje en el campo de `NoDataMessage` propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ef50-116">In **Caption**, type the text that you want to display as a message in `NoDataMessage` property field.</span></span>  
  
     <span data-ttu-id="1ef50-117">Como alternativa, en la lista desplegable, haga clic en **Expresión** para abrir el cuadro de diálogo **Expresión** y crear una expresión.</span><span class="sxs-lookup"><span data-stu-id="1ef50-117">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-norowsmessage-for-a-subreport"></a><span data-ttu-id="1ef50-118">Para establecer la propiedad NoRowsMessage para un subinforme</span><span class="sxs-lookup"><span data-stu-id="1ef50-118">To set the NoRowsMessage for a subreport</span></span>  
  
1.  <span data-ttu-id="1ef50-119">En la vista Diseño, haga clic en el subinforme en la superficie de diseño para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="1ef50-119">In Design view, click the subreport on the design surface to select it.</span></span> <span data-ttu-id="1ef50-120">Las propiedades del elemento seleccionado aparecen en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="1ef50-120">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="1ef50-121">En el panel Propiedades, escriba el texto que desea mostrar como mensaje en el campo de `NoRowsMessage` propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ef50-121">In the Properties pane, type the text that you want to display as a message in `NoRowsMessage` property field.</span></span>  
  
     <span data-ttu-id="1ef50-122">Como alternativa, en la lista desplegable, haga clic en **Expresión** para abrir el cuadro de diálogo **Expresión** y crear una expresión.</span><span class="sxs-lookup"><span data-stu-id="1ef50-122">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
### <a name="to-set-the-nodatatext-property-for-a-color-scale-for-a-map"></a><span data-ttu-id="1ef50-123">Para establecer la propiedad NoDataText para la escala de colores de un mapa</span><span class="sxs-lookup"><span data-stu-id="1ef50-123">To set the NoDataText property for a color scale for a map</span></span>  
  
1.  <span data-ttu-id="1ef50-124">En la vista Diseño, haga clic en la escala de colores del mapa para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="1ef50-124">In Design view, click the color scale on the map to select it.</span></span> <span data-ttu-id="1ef50-125">Las propiedades del elemento seleccionado aparecen en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="1ef50-125">The Properties pane displays the properties for the selected item.</span></span>  
  
2.  <span data-ttu-id="1ef50-126">En el panel Propiedades, en `NoDataText` , escriba el texto que desea mostrar como etiqueta para los colores sin valor de datos.</span><span class="sxs-lookup"><span data-stu-id="1ef50-126">In the Properties pane, in `NoDataText`, type the text that you want to display as a label for colors with no data value.</span></span>  
  
     <span data-ttu-id="1ef50-127">Como alternativa, en la lista desplegable, haga clic en **Expresión** para abrir el cuadro de diálogo **Expresión** y crear una expresión.</span><span class="sxs-lookup"><span data-stu-id="1ef50-127">Alternatively, from the drop-down list, click **Expression** to open the **Expression** dialog box and create an expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef50-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ef50-128">See Also</span></span>  
 <span data-ttu-id="1ef50-129">[Subinformes &#40;Generador de informes y SSRS&#41;](../report-design/subreports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1ef50-129">[Subreports &#40;Report Builder and SSRS&#41;](../report-design/subreports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1ef50-130">[Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1ef50-130">[Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](../report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1ef50-131">[Gráficos &#40;Generador de informes y SSRS&#41;](../report-design/charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1ef50-131">[Charts &#40;Report Builder and SSRS&#41;](../report-design/charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="1ef50-132">[Mapas &#40;Generador de informes y SSRS&#41;](../report-design/maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1ef50-132">[Maps &#40;Report Builder and SSRS&#41;](../report-design/maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="1ef50-133">Subinformes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1ef50-133">Subreports &#40;Report Builder and SSRS&#41;</span></span>](../report-design/subreports-report-builder-and-ssrs.md)  
  
  
