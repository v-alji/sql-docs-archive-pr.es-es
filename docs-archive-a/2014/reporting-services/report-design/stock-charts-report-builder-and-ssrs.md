---
title: Gráficos de cotizaciones (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f75ca11e-b7f5-4ac0-ba17-fe6f82742dad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0f8c9c7dbc750bdb477f2ea1d96aa03f7ad022f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662526"
---
# <a name="stock-charts-report-builder-and-ssrs"></a><span data-ttu-id="ce80d-102">Gráficos de cotizaciones (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="ce80d-102">Stock Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="ce80d-103">Los gráficos de cotizaciones están diseñados específicamente para datos financieros o científicos que usen hasta cuatro valores por punto de datos.</span><span class="sxs-lookup"><span data-stu-id="ce80d-103">A stock chart is specifically designed for financial or scientific data that uses up to four values per data point.</span></span> <span data-ttu-id="ce80d-104">Estos valores se corresponden con los valores máximo, mínimo, de apertura y de cierre que se usan para trazar datos de acciones financieras.</span><span class="sxs-lookup"><span data-stu-id="ce80d-104">These values align with the high, low, open and close values that are used to plot financial stock data.</span></span> <span data-ttu-id="ce80d-105">Este tipo de gráfico muestra los valores de apertura y de cierre mediante marcadores, que son normalmente líneas o triángulos.</span><span class="sxs-lookup"><span data-stu-id="ce80d-105">This chart type displays opening and closing values by using markers, which are typically lines or triangles.</span></span> <span data-ttu-id="ce80d-106">En el ejemplo siguiente, los marcadores de la izquierda muestran los valores de apertura y los marcadores de la derecha muestran los valores de cierre.</span><span class="sxs-lookup"><span data-stu-id="ce80d-106">In the following example, the opening values are shown by the markers on the left, and the closing values are shown by the markers on the right.</span></span>  
  
 <span data-ttu-id="ce80d-107">![Gráfico de cotizaciones](../media/rs-stockchart.gif "Gráfico de cotizaciones")</span><span class="sxs-lookup"><span data-stu-id="ce80d-107">![Stock chart](../media/rs-stockchart.gif "Stock chart")</span></span>  
  
 <span data-ttu-id="ce80d-108">Un ejemplo de gráfico de cotizaciones está disponible como informe de ejemplo del Generador de informes de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce80d-108">An example of a stock chart is available as a sample [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="ce80d-109">Para más información acerca de cómo descargar este y otros informes de ejemplo, consulte el tema sobre [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)][informes de ejemplo del Generador de informes y el Diseñador de informes](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="ce80d-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="ce80d-110">Variaciones</span><span class="sxs-lookup"><span data-stu-id="ce80d-110">Variations</span></span>  
  
-   <span data-ttu-id="ce80d-111">**Vela japonesa**.</span><span class="sxs-lookup"><span data-stu-id="ce80d-111">**Candlestick**.</span></span> <span data-ttu-id="ce80d-112">El gráfico de vela japonesa es una variante especializada del gráfico de cotizaciones, en el que se usan cuadros para mostrar el intervalo existente entre los valores de apertura y de cierre.</span><span class="sxs-lookup"><span data-stu-id="ce80d-112">The candlestick chart is a specialized form of the stock chart, wherein boxes are used to show the range between the open and close values.</span></span> <span data-ttu-id="ce80d-113">Al igual que el gráfico de cotizaciones, el gráfico de vela japonesa puede mostrar hasta cuatro valores por punto de datos.</span><span class="sxs-lookup"><span data-stu-id="ce80d-113">Like the stock chart, the candlestick chart can display up to four values per data point.</span></span>  
  
## <a name="data-considerations-for-stock-charts"></a><span data-ttu-id="ce80d-114">Consideraciones sobre los datos para los gráficos de cotizaciones</span><span class="sxs-lookup"><span data-stu-id="ce80d-114">Data Considerations for Stock Charts</span></span>  
  
-   <span data-ttu-id="ce80d-115">Cuando se presentan muchos puntos de datos de acciones, como la tendencia anual del precio de las acciones, resulta difícil distinguir los valores máximo, mínimo, de apertura y de cierre de cada punto de datos.</span><span class="sxs-lookup"><span data-stu-id="ce80d-115">When presenting many stock data points, such as annual stock price trend, it is difficult to distinguish each open, close, high and low value of each data point.</span></span> <span data-ttu-id="ce80d-116">En este escenario, puede resultar más factible usar un gráfico de líneas en lugar de uno de cotizaciones.</span><span class="sxs-lookup"><span data-stu-id="ce80d-116">In this scenario, consider using a line chart instead of a stock chart.</span></span>  
  
-   <span data-ttu-id="ce80d-117">Cuando se generan las etiquetas del eje, normalmente se empieza por el cero.</span><span class="sxs-lookup"><span data-stu-id="ce80d-117">When axis labels are generated, labeling usually begins at zero.</span></span>  <span data-ttu-id="ce80d-118">En general, los precios de las acciones no fluctúan tanto como otros conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="ce80d-118">In general, stock prices do not fluctuate to the same degree as other data sets.</span></span> <span data-ttu-id="ce80d-119">Por esta razón, es posible que desee que las etiquetas del eje no empiecen por el cero con el fin de obtener una mejor perspectiva de los datos.</span><span class="sxs-lookup"><span data-stu-id="ce80d-119">For this reason, you may want to disable the axis labels from starting at zero, in order to get a better view of your data.</span></span> <span data-ttu-id="ce80d-120">Para ello, establezca **IncludeZero** en **false** en el cuadro de diálogo **Propiedades del eje** o en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="ce80d-120">To do this, set **IncludeZero** to **false** in the **Axis Properties** dialog box or the Properties window.</span></span> <span data-ttu-id="ce80d-121">Para más información sobre cómo genera el gráfico etiquetas de eje, vea [Aplicar formato a las etiquetas de los ejes de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ce80d-121">For more information about how the chart generates axis labels, see [Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="ce80d-122">proporciona muchas fórmulas calculadas para su uso con los gráficos de cotizaciones, incluyendo indicadores de precio, indicadores de fuerza relativa, convergencia de media móvil, etc.</span><span class="sxs-lookup"><span data-stu-id="ce80d-122">provides many calculated formulas for use with stock charts, including Price Indicator, Relative Strength Index, MACD and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce80d-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ce80d-123">See Also</span></span>  
 <span data-ttu-id="ce80d-124">[Gráficos de intervalos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ce80d-124">[Range Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ce80d-125">[Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ce80d-125">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="ce80d-126">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ce80d-126">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ce80d-127">Cuadro de diálogo Propiedades del eje, Opciones del eje &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ce80d-127">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
