---
title: Agregar puntos vacíos al gráfico (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2b056119-439f-494f-83cf-ee0c05dc6487
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 53d891c58210bcd51cd4e49f2f9a691a7729c884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748650"
---
# <a name="add-empty-points-to-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="79002-102">Agregar puntos vacíos al gráfico (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="79002-102">Add Empty Points to the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="79002-103">Los valores NULL se muestran en el gráfico como espacios vacíos o como intervalos entre los puntos de datos de una serie.</span><span class="sxs-lookup"><span data-stu-id="79002-103">Null values are shown on the chart as empty spaces or gaps between data points in a series.</span></span> <span data-ttu-id="79002-104">Los puntos vacíos son los puntos de datos que se pueden insertar en el espacio vacío que crean los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="79002-104">Empty points are data points that can be inserted in the empty space created by null values.</span></span>  
  
 <span data-ttu-id="79002-105">De forma predeterminada, los puntos vacíos se calculan tomando el promedio de los puntos de datos anterior y siguiente que contienen un valor.</span><span class="sxs-lookup"><span data-stu-id="79002-105">By default, empty points are calculated by taking the average of the previous and next data points that contain a value.</span></span> <span data-ttu-id="79002-106">Puede cambiar esta circunstancia para que todos los puntos vacíos se inserten en la posición cero.</span><span class="sxs-lookup"><span data-stu-id="79002-106">You can change this so that all empty points are inserted at zero.</span></span>  
  
 <span data-ttu-id="79002-107">Para más información, vea [Puntos de datos vacíos y nulos en los gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="79002-107">For more information, see [Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-empty-points-on-a-chart"></a><span data-ttu-id="79002-108">Para especificar puntos vacíos en un gráfico</span><span class="sxs-lookup"><span data-stu-id="79002-108">To specify empty points on a chart</span></span>  
  
1.  <span data-ttu-id="79002-109">Abra el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="79002-109">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="79002-110">En la superficie de diseño, haga clic con el botón secundario en la serie que contiene los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="79002-110">On the design surface, right-click the series that contains null values.</span></span> <span data-ttu-id="79002-111">Las propiedades de la serie se muestran en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="79002-111">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="79002-112">Expanda el nodo **EmptyPoint** .</span><span class="sxs-lookup"><span data-stu-id="79002-112">Expand the **EmptyPoint** node.</span></span>  
  
4.  <span data-ttu-id="79002-113">Seleccione un valor de color para la propiedad Color.</span><span class="sxs-lookup"><span data-stu-id="79002-113">Select a color value for the Color property.</span></span>  
  
5.  <span data-ttu-id="79002-114">En el nodo **EmptyPoint** , expanda el nodo Marcador.</span><span class="sxs-lookup"><span data-stu-id="79002-114">In the **EmptyPoint** node, expand the Marker node.</span></span>  
  
6.  <span data-ttu-id="79002-115">Seleccione un tipo de marcador para la propiedad MarkerType.</span><span class="sxs-lookup"><span data-stu-id="79002-115">Select a marker type for the MarkerType property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="79002-116">Deberá seleccionar un tipo de marcador siempre que desee agregar puntos vacíos a un gráfico de barras, de columnas o de dispersión.</span><span class="sxs-lookup"><span data-stu-id="79002-116">You must select a marker type to add empty points to a bar, column or scatter chart.</span></span> <span data-ttu-id="79002-117">Sin embargo, para los gráficos de áreas, de líneas y radiales, la selección de un tipo de marcador es opcional porque el gráfico rellena el espacio vacío sin que sea necesario especificar un marcador.</span><span class="sxs-lookup"><span data-stu-id="79002-117">However, for area, line and radar charts, selecting a marker type is optional because the chart fills in the empty space or gap without requiring a marker to be specified.</span></span>  
  
7.  <span data-ttu-id="79002-118">Establezca el valor del punto vacío.</span><span class="sxs-lookup"><span data-stu-id="79002-118">Set the value of the empty point.</span></span>  
  
    1.  <span data-ttu-id="79002-119">En el panel de propiedades, expanda el nodo **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="79002-119">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
    2.  <span data-ttu-id="79002-120">Establezca la propiedad EmptyPointValue.</span><span class="sxs-lookup"><span data-stu-id="79002-120">Set the EmptyPointValue property.</span></span> <span data-ttu-id="79002-121">Para insertar puntos vacíos en el promedio de los puntos de datos anterior y siguiente, seleccione **Promedio**.</span><span class="sxs-lookup"><span data-stu-id="79002-121">To insert empty points at an average of the previous and next data points, select **Average**.</span></span> <span data-ttu-id="79002-122">Para insertar puntos vacíos en la posición cero, seleccione **Cero**.</span><span class="sxs-lookup"><span data-stu-id="79002-122">To insert empty points at zero, select **Zero**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79002-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79002-123">See Also</span></span>  
 <span data-ttu-id="79002-124">[Agregar filtros de conjunto de datos, filtros de región de datos y filtros de grupo &#40;Generador de informes y SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="79002-124">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="79002-125">[Tipos de gráficos &#40;Generador de informes y SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="79002-125">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="79002-126">[Agregar quiebres de escala a un gráfico &#40;Generador de informes y SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="79002-126">[Add Scale Breaks to a Chart &#40;Report Builder and SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="79002-127">Gráficos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="79002-127">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
