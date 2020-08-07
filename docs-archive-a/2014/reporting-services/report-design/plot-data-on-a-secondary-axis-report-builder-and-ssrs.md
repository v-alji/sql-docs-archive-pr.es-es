---
title: Trazar datos en un eje secundario (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 094f39bf-3634-4852-9fc3-3adec4b266e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cec58820e0373bb1e9ef2d50d022e5b4ef7e962b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743924"
---
# <a name="plot-data-on-a-secondary-axis-report-builder-and-ssrs"></a><span data-ttu-id="448e7-102">Trazar datos en un eje secundario (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="448e7-102">Plot Data on a Secondary Axis (Report Builder and SSRS)</span></span>
  <span data-ttu-id="448e7-103">El gráfico tiene dos tipos de ejes: el principal y el secundario.</span><span class="sxs-lookup"><span data-stu-id="448e7-103">The chart has two axis types: primary and secondary.</span></span> <span data-ttu-id="448e7-104">El eje secundario resulta de gran utilidad cuando se comparan dos conjuntos de valores con dos intervalos de datos definidos que comparten una categoría común.</span><span class="sxs-lookup"><span data-stu-id="448e7-104">The secondary axis is useful when comparing two value sets with two distinct data ranges that share a common category.</span></span>  
  
 <span data-ttu-id="448e7-105">Por ejemplo, imagine que tiene un gráfico que calcula los ingresos frente a los impuestos durante el año 2008.</span><span class="sxs-lookup"><span data-stu-id="448e7-105">For example, suppose you have a chart that calculates Revenue vs. Tax for the year 2008.</span></span> <span data-ttu-id="448e7-106">En este caso, el período de tiempo 2008 es común a ambos conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="448e7-106">In this case, the 2008 time period is common to both value sets.</span></span> <span data-ttu-id="448e7-107">Sin embargo, si ambas series se trazan en el mismo eje Y, no podremos realizar una comparación útil porque la escala del eje Y se optimiza para los valores más altos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="448e7-107">However, when both series are plotted on the same y-axis, we cannot make a useful comparison because the scale of the y-axis is optimized for the largest values in the dataset.</span></span> <span data-ttu-id="448e7-108">Si mostramos los ingresos en el eje principal, y los impuestos en el eje secundario, podremos mostrar cada serie en su propio eje Y con su propia escala de valores.</span><span class="sxs-lookup"><span data-stu-id="448e7-108">If we show Revenue on the primary axis, and Tax on the secondary axis, we can display each series on its own y-axis with its own scale of values.</span></span> <span data-ttu-id="448e7-109">Las series siguen compartiendo un eje X común.</span><span class="sxs-lookup"><span data-stu-id="448e7-109">The series still share a common x-axis.</span></span>  
  
 <span data-ttu-id="448e7-110">En aquellas situaciones en las que se necesita comparar más de dos series, considere un enfoque diferente para comparar y mostrar dichas series.</span><span class="sxs-lookup"><span data-stu-id="448e7-110">In situations where there are more than two series to be compared, consider a different approach for comparing and displaying multiple series in a chart.</span></span> <span data-ttu-id="448e7-111">Para más información, vea [Mostrar varias series en un gráfico &#40;Generador de informes y SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md):</span><span class="sxs-lookup"><span data-stu-id="448e7-111">For more information, see [Multiple Series on a Chart &#40;Report Builder and SSRS&#41;](multiple-series-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="448e7-112">Un ejemplo de este gráfico está disponible como informe de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="448e7-112">An example of this chart is available as a sample report.</span></span> <span data-ttu-id="448e7-113">Para más información acerca de cómo descargar este y otros informes de ejemplo, consulte el tema sobre [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][informes de ejemplo del Generador de informes y el Diseñador de informes](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="448e7-113">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-plot-a-series-on-the-secondary-axis"></a><span data-ttu-id="448e7-114">Para trazar una serie en el eje secundario</span><span class="sxs-lookup"><span data-stu-id="448e7-114">To plot a series on the secondary axis</span></span>  
  
1.  <span data-ttu-id="448e7-115">Haga clic con el botón derecho en la serie del gráfico o en un campo del área **Valores** que quiera mostrar en el eje secundario y, después, haga clic en **Propiedades de la serie**.</span><span class="sxs-lookup"><span data-stu-id="448e7-115">Right-click the series in the chart or right-click on a field in the **Values** area that you want to display on the secondary axis and click **Series Properties**.</span></span> <span data-ttu-id="448e7-116">Aparece el cuadro de diálogo **Propiedades de la serie** .</span><span class="sxs-lookup"><span data-stu-id="448e7-116">The **Series Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="448e7-117">Haga clic en **Ejes y área del gráfico**y seleccione los ejes secundarios que desea habilitar, el eje de valores o el eje de categorías.</span><span class="sxs-lookup"><span data-stu-id="448e7-117">Click **Axes and Chart Area**, and select which of the secondary axes you want to enable, the value axis or the category axis.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="448e7-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="448e7-118">See Also</span></span>  
 <span data-ttu-id="448e7-119">[Aplicar formato a las etiquetas de los ejes de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="448e7-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="448e7-120">Especificar un intervalo de eje &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="448e7-120">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
