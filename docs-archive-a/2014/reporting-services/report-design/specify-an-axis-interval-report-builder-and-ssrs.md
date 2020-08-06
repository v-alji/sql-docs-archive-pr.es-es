---
title: Especificar un intervalo de eje (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ae46712d-a5bf-44c0-9929-e30ccc1e7e33
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 70b64b824933753a8482360f193ca4ccf71e8d52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662534"
---
# <a name="specify-an-axis-interval-report-builder-and-ssrs"></a><span data-ttu-id="85bd6-102">Especificar un intervalo de eje (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="85bd6-102">Specify an Axis Interval (Report Builder and SSRS)</span></span>
  <span data-ttu-id="85bd6-103">El intervalo de eje define el número de etiquetas y marcas de graduación asociadas que aparecen en un eje.</span><span class="sxs-lookup"><span data-stu-id="85bd6-103">The axis interval defines the number of labels and accompanying tick marks on an axis.</span></span> <span data-ttu-id="85bd6-104">En el eje de valores, los intervalos de eje proporcionan una medida coherente de los puntos de datos representados en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="85bd6-104">On the value axis, axis intervals provide a consistent measure of the data points on the chart.</span></span> <span data-ttu-id="85bd6-105">Sin embargo, en el eje de categorías, esta funcionalidad puede provocar que las categorías aparezcan sin etiquetas en los ejes.</span><span class="sxs-lookup"><span data-stu-id="85bd6-105">However, on the category axis, this functionality can cause categories to appear without axis labels.</span></span> <span data-ttu-id="85bd6-106">Puede especificar el número de intervalos que quiere en la propiedad Intervalo del eje.</span><span class="sxs-lookup"><span data-stu-id="85bd6-106">You can specify the number of intervals you want in the axis Interval property.</span></span> [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="85bd6-107">calcula el número de intervalos en tiempo de ejecución, según los datos del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="85bd6-107">calculates the number of intervals at run time, based on the data in the result set.</span></span> <span data-ttu-id="85bd6-108">Para más información sobre cómo se calculan los intervalos de los ejes, vea [Aplicar formato a las etiquetas de los ejes de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="85bd6-108">For more information about how axis intervals are calculated, see [Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="85bd6-109">Este tema no se aplica a los valores de fecha u hora del eje de categorías.</span><span class="sxs-lookup"><span data-stu-id="85bd6-109">This topic is not applicable for date or time values on the category axis.</span></span> <span data-ttu-id="85bd6-110">De forma predeterminada, los valores de tipo `DateTime` aparecen como días.</span><span class="sxs-lookup"><span data-stu-id="85bd6-110">Be default, `DateTime` values appear as days.</span></span> <span data-ttu-id="85bd6-111">Para especificar otro intervalo de fechas u horas, como un mes o un intervalo de horas, debe dar formato a las etiquetas del eje y establecer este para que muestre instancias de los tipos `DateTime` y no de los tipos `String`.</span><span class="sxs-lookup"><span data-stu-id="85bd6-111">To specify a different date or time interval, such as a month or time interval, you must format the axis labels and set the axis to display instances of `DateTime` types instead of `String` types.</span></span> <span data-ttu-id="85bd6-112">Además, necesita establecer la propiedad Intervalo.</span><span class="sxs-lookup"><span data-stu-id="85bd6-112">In addition, you must set the Interval property.</span></span> <span data-ttu-id="85bd6-113">Para más información, vea [Aplicar formato de fecha o de moneda a las etiquetas de los ejes &#40;Generador de informes y SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="85bd6-113">For more information, see [Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="85bd6-114">Este tema no se aplica a los gráficos circulares, de anillo, de embudo ni piramidales, ya que carecen de ejes.</span><span class="sxs-lookup"><span data-stu-id="85bd6-114">This topic does not apply to pie, doughnut, funnel or pyramid charts, which do not have axes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85bd6-115">El eje de categorías normalmente es el eje horizontal o eje X.</span><span class="sxs-lookup"><span data-stu-id="85bd6-115">The category axis is usually the horizontal or x-axis.</span></span> <span data-ttu-id="85bd6-116">Sin embargo, en el caso de los gráficos de barras, el eje de categorías es el eje vertical o eje Y.</span><span class="sxs-lookup"><span data-stu-id="85bd6-116">However, for bar charts, the category axis is the vertical or y-axis.</span></span>  
  
 <span data-ttu-id="85bd6-117">Un ejemplo de gráfico que especifica intervalos de eje diferentes está disponible como informe de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="85bd6-117">An example of a chart specifying different axis intervals is available as a sample report.</span></span> <span data-ttu-id="85bd6-118">Para más información acerca de cómo descargar este y otros informes de ejemplo, consulte el tema sobre [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][informes de ejemplo del Generador de informes y el Diseñador de informes](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="85bd6-118">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-show-all-category-labels-on-the-x-axis"></a><span data-ttu-id="85bd6-119">Para mostrar todas las etiquetas de categoría en el eje X</span><span class="sxs-lookup"><span data-stu-id="85bd6-119">To show all category labels on the x-axis</span></span>  
  
1.  <span data-ttu-id="85bd6-120">Haga clic con el botón secundario en el eje de categorías y, a continuación, haga clic en **Propiedades del eje**.</span><span class="sxs-lookup"><span data-stu-id="85bd6-120">Right-click the category axis and click **Axis Properties**.</span></span> <span data-ttu-id="85bd6-121">Se abre el cuadro de diálogo **Propiedades del eje** .</span><span class="sxs-lookup"><span data-stu-id="85bd6-121">The **Axis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="85bd6-122">En **Opciones del eje**, establezca `Interval` en **1**.</span><span class="sxs-lookup"><span data-stu-id="85bd6-122">In **Axis Options**, set `Interval` to **1**.</span></span> <span data-ttu-id="85bd6-123">Se mostrarán todas las etiquetas de grupo de categorías.</span><span class="sxs-lookup"><span data-stu-id="85bd6-123">Every category group label is displayed.</span></span> <span data-ttu-id="85bd6-124">Si desea mostrar una de cada dos etiquetas de grupo de categorías en el eje X, escriba **2**.</span><span class="sxs-lookup"><span data-stu-id="85bd6-124">If you want to show every other category group label on the x-axis, type **2**.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="85bd6-125">Cuando se establece un intervalo de eje, se deshabilita todo el etiquetado automático.</span><span class="sxs-lookup"><span data-stu-id="85bd6-125">When an axis interval is set, all automatic labeling is disabled.</span></span> <span data-ttu-id="85bd6-126">Si especifica un valor para el intervalo de eje, puede notar un comportamiento imprevisible del etiquetado en función del número de categorías existentes en el eje de categorías.</span><span class="sxs-lookup"><span data-stu-id="85bd6-126">If you specify a value for the axis interval, you may experience unpredictable labeling behavior depending on how many categories are on the category axis.</span></span>  
  
### <a name="to-enable-a-variable-interval-calculation-on-an-axis"></a><span data-ttu-id="85bd6-127">Para habilitar el cálculo de un intervalo variable en un eje</span><span class="sxs-lookup"><span data-stu-id="85bd6-127">To enable a variable interval calculation on an axis</span></span>  
  
1.  <span data-ttu-id="85bd6-128">Haga clic con el botón derecho en el eje del gráfico que quiera cambiar y, después, haga clic en **Propiedades del eje**.</span><span class="sxs-lookup"><span data-stu-id="85bd6-128">Right-click the chart axis that you want to change, and then click **Axis Properties**.</span></span> <span data-ttu-id="85bd6-129">Se abre el cuadro de diálogo **Propiedades del eje** .</span><span class="sxs-lookup"><span data-stu-id="85bd6-129">The **Axis Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="85bd6-130">En **Opciones del eje**, establezca `Interval` en **automático**. El gráfico mostrará el número óptimo de etiquetas de categoría que quepan a lo largo del eje.</span><span class="sxs-lookup"><span data-stu-id="85bd6-130">In **Axis Options**, set `Interval` to **Auto**. The chart will display the optimal number of category labels that can fit along the axis.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="85bd6-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85bd6-131">See Also</span></span>  
 <span data-ttu-id="85bd6-132">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85bd6-132">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="85bd6-133">[Aplicar formato a los puntos de datos de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85bd6-133">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="85bd6-134">[Ordenar datos en una región de datos &#40;Generador de informes y SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85bd6-134">[Sort Data in a Data Region &#40;Report Builder and SSRS&#41;](sort-data-in-a-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="85bd6-135">[Cuadro de diálogo Propiedades del eje, opciones del eje &#40;Generador de informes y SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85bd6-135">[Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="85bd6-136">[Especifique una escala logarítmica &#40;Generador de informes y SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85bd6-136">[Specify a Logarithmic Scale &#40;Report Builder and SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="85bd6-137">Trazar datos en un eje secundario &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="85bd6-137">Plot Data on a Secondary Axis &#40;Report Builder and SSRS&#41;</span></span>](plot-data-on-a-secondary-axis-report-builder-and-ssrs.md)  
  
  
