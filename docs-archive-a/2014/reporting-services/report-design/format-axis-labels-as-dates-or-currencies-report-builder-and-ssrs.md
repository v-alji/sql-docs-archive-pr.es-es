---
title: Aplicar formato de fecha o de moneda a las etiquetas de los ejes (Generador de informes y SSRS)| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9a01a74-2f51-4b35-be3a-a6138568f6cf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ffe9d903a2271db95d4b1c2ef6201d2b0f3edab3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671381"
---
# <a name="format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs"></a><span data-ttu-id="2ea03-102">Aplicar formato de fecha o de moneda a las etiquetas de los ejes (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="2ea03-102">Format Axis Labels as Dates or Currencies (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2ea03-103">Cuando se muestren valores DateTime con el formato correcto en un eje, un gráfico mostrará automáticamente dichos valores como días.</span><span class="sxs-lookup"><span data-stu-id="2ea03-103">When you show properly formatted DateTime values on an axis, a chart will automatically display these values as days.</span></span> <span data-ttu-id="2ea03-104">Para especificar un intervalo de fechas u horas para el eje X, como un intervalo de meses o de horas, debe dar formato a las etiquetas del eje y establecer el tipo de intervalo de éste en un intervalo de fechas u horas válido.</span><span class="sxs-lookup"><span data-stu-id="2ea03-104">To specify a date/time interval for the x-axis, such as an interval of months or an interval of hours, you must format the axis labels and set the type of axis interval to a valid date or time interval.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ea03-105">En gráficos de columnas y de dispersión, el eje horizontal, o eje X, es el eje de categorías.</span><span class="sxs-lookup"><span data-stu-id="2ea03-105">In column and scatter charts, the horizontal, or x-axis, is the category axis.</span></span> <span data-ttu-id="2ea03-106">En los gráficos de barras, el vertical, o eje Y, es el eje de categoría.</span><span class="sxs-lookup"><span data-stu-id="2ea03-106">In bar charts, the vertical, or y-axis, is the category axis.</span></span>  
  
 <span data-ttu-id="2ea03-107">Para dar el formato correcto a los intervalos de tiempo, los valores mostrados en el eje X se deben evaluar como un tipo de datos <xref:System.DateTime> .</span><span class="sxs-lookup"><span data-stu-id="2ea03-107">In order to format time intervals correctly, the values displayed on the x-axis must evaluate to a <xref:System.DateTime> data type.</span></span> <span data-ttu-id="2ea03-108">Si el campo tiene un tipo de datos <xref:System.String>, el gráfico no calculará los intervalos como fechas u horas.</span><span class="sxs-lookup"><span data-stu-id="2ea03-108">If your field has a data type of <xref:System.String>, the chart will not calculate intervals as dates or times.</span></span> <span data-ttu-id="2ea03-109">Para más información, vea [Gráficos &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="2ea03-109">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="2ea03-110">Cuando se agrega un valor numérico al eje Y, de forma predeterminada, el gráfico no da formato al número antes de mostrarlo.</span><span class="sxs-lookup"><span data-stu-id="2ea03-110">When a numeric value is added to the y-axis, by default, the chart does not format the number before displaying it.</span></span> <span data-ttu-id="2ea03-111">Si el campo numérico es una cifra de ventas, considere la posibilidad de dar formato de moneda a los números para aumentar la legibilidad del gráfico.</span><span class="sxs-lookup"><span data-stu-id="2ea03-111">If your numeric field is a sales figure, consider formatting the numbers as currencies to increase the readability of the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-format-x-axis-labels-as-monthly-intervals"></a><span data-ttu-id="2ea03-112">Para dar formato de intervalo mensual a las etiquetas del eje X</span><span class="sxs-lookup"><span data-stu-id="2ea03-112">To format x-axis labels as monthly intervals</span></span>  
  
1.  <span data-ttu-id="2ea03-113">Haga clic con el botón derecho en el eje horizontal, o X, del gráfico y, después, seleccione **Propiedades del eje horizontal**.</span><span class="sxs-lookup"><span data-stu-id="2ea03-113">Right-click the horizontal, or x-axis, of the chart, and select **HorizontalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="2ea03-114">En el cuadro de diálogo **Propiedades del eje horizontal** , seleccione **Número**.</span><span class="sxs-lookup"><span data-stu-id="2ea03-114">In the **HorizontalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="2ea03-115">En la lista **Categoría** , seleccione **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="2ea03-115">From the **Category** list, select **Date**.</span></span> <span data-ttu-id="2ea03-116">En la lista **Tipo** , seleccione un formato de fecha para aplicarlo a las etiquetas del eje X.</span><span class="sxs-lookup"><span data-stu-id="2ea03-116">From the **Type** list, select a date format to apply to the x-axis labels.</span></span>  
  
4.  <span data-ttu-id="2ea03-117">Seleccione **Opciones del eje**.</span><span class="sxs-lookup"><span data-stu-id="2ea03-117">Select **Axis Options.**</span></span>  
  
5.  <span data-ttu-id="2ea03-118">En **Intervalo**, escriba **1**.</span><span class="sxs-lookup"><span data-stu-id="2ea03-118">In **Interval**, type **1**.</span></span> <span data-ttu-id="2ea03-119">En la propiedad **Tipo de intervalo** , seleccione **Meses**.</span><span class="sxs-lookup"><span data-stu-id="2ea03-119">In **Interval type** property, select **Months**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2ea03-120">Si no especifica un tipo de intervalo, el gráfico calculará los intervalos en días.</span><span class="sxs-lookup"><span data-stu-id="2ea03-120">If you do not specify an interval type, the chart will calculate intervals in terms of days.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-format-y-axis-labels-using-a-currency-format"></a><span data-ttu-id="2ea03-121">Para dar formato de moneda a las etiquetas del eje Y</span><span class="sxs-lookup"><span data-stu-id="2ea03-121">To format y-axis labels using a currency format</span></span>  
  
1.  <span data-ttu-id="2ea03-122">Haga clic con el botón derecho en el eje vertical, o Y, del gráfico y, después, haga clic en **Propiedades del eje vertical**.</span><span class="sxs-lookup"><span data-stu-id="2ea03-122">Right-click the vertical, or y-axis, of the chart, and select **VerticalAxis Properties**.</span></span>  
  
2.  <span data-ttu-id="2ea03-123">En el cuadro de diálogo **Propiedades del eje vertical** , seleccione **Número**.</span><span class="sxs-lookup"><span data-stu-id="2ea03-123">In the **VerticalAxis Properties** dialog box, select **Number**.</span></span>  
  
3.  <span data-ttu-id="2ea03-124">En la lista **Categoría** , seleccione **Moneda**.</span><span class="sxs-lookup"><span data-stu-id="2ea03-124">From the **Category** list, select **Currency**.</span></span> <span data-ttu-id="2ea03-125">En la lista **Símbolo** , seleccione un formato de moneda para aplicarlo a las etiquetas del eje Y.</span><span class="sxs-lookup"><span data-stu-id="2ea03-125">From the **Symbol** list, select a currency format to apply to the y-axis labels.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2ea03-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ea03-126">See Also</span></span>  
 <span data-ttu-id="2ea03-127">[Aplicar formato a las etiquetas de los ejes de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2ea03-127">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2ea03-128">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2ea03-128">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2ea03-129">[Especificar una escala logarítmica &#40;Generador de informes y SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2ea03-129">[Specify a Logarithmic Scale &#40;Report Builder and SSRS&#41;](specify-a-logarithmic-scale-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="2ea03-130">Especificar un intervalo de eje &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2ea03-130">Specify an Axis Interval &#40;Report Builder and SSRS&#41;</span></span>](specify-an-axis-interval-report-builder-and-ssrs.md)  
  
  
