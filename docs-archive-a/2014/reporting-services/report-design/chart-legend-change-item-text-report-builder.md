---
title: Cambiar el texto de un elemento de leyenda (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9e82fa34-17ed-494f-b25d-03dcc353a21f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d0bb721aa0ff03a5211065111c98605cd86e971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676360"
---
# <a name="change-the-text-of-a-legend-item-report-builder-and-ssrs"></a><span data-ttu-id="f612f-102">Cambiar el texto de un elemento de leyenda (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="f612f-102">Change the Text of a Legend Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="f612f-103">Cuando se coloca un campo en el área Valores del gráfico, se genera automáticamente un elemento de leyenda que contiene el nombre de este campo.</span><span class="sxs-lookup"><span data-stu-id="f612f-103">When a field is placed in the Values area of the chart, a legend item is automatically generated that contains the name of this field.</span></span> <span data-ttu-id="f612f-104">Cada elemento de leyenda se conecta a una serie individual del gráfico, a excepción de los gráficos de formas, donde la leyenda se conecta a puntos de datos individuales en lugar de a series individuales.</span><span class="sxs-lookup"><span data-stu-id="f612f-104">Every legend item is connected to an individual series on the chart, with the exception of shape charts, where the legend is connected to individual data points instead of individual series.</span></span>  
  
 <span data-ttu-id="f612f-105">En los gráficos de formas, puede cambiar el texto de un elemento de leyenda para mostrar más información sobre los puntos de datos individuales.</span><span class="sxs-lookup"><span data-stu-id="f612f-105">On shape charts, you can change the text of a legend item to show more information about the individual data points.</span></span> <span data-ttu-id="f612f-106">Por ejemplo, si desea mostrar los valores de los puntos de datos como porcentajes en la leyenda, puede utilizar una palabra clave como `#PERCENT`.</span><span class="sxs-lookup"><span data-stu-id="f612f-106">For example, if you want to show the values of the data points as percentages in the legend, you can use a keyword such as `#PERCENT`.</span></span> <span data-ttu-id="f612f-107">Puede anexar códigos de formato de .NET Framework junto con las palabras clave para aplicar formatos numéricos y de fecha.</span><span class="sxs-lookup"><span data-stu-id="f612f-107">You can append .NET Framework format codes in conjunction with keywords to apply numeric and date formats.</span></span> <span data-ttu-id="f612f-108">Para obtener más información sobre las palabras clave, vea [Aplicar formato a los puntos de datos de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f612f-108">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="f612f-109">![Gráfico nítido](../media/sharpchart.png "Gráfico nítido")</span><span class="sxs-lookup"><span data-stu-id="f612f-109">![Sharp Chart](../media/sharpchart.png "Sharp Chart")</span></span>  
  
 <span data-ttu-id="f612f-110">En los gráficos que no son de formas, puede cambiar el texto de un elemento de leyenda.</span><span class="sxs-lookup"><span data-stu-id="f612f-110">On non-shape charts, you can change the text of a legend item.</span></span> <span data-ttu-id="f612f-111">Por ejemplo, si la serie se denomina "Serie1", es posible que desee cambiar el texto por otro más descriptivo como "Ventas para 2008".</span><span class="sxs-lookup"><span data-stu-id="f612f-111">For example, if your series name is "Series1", you may want to change the text to something more descriptive like "Sales for 2008".</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-shape-chart"></a><span data-ttu-id="f612f-112">Para modificar el texto que aparece en la leyenda en un gráfico de formas</span><span class="sxs-lookup"><span data-stu-id="f612f-112">To modify the text that appears in the legend on a Shape chart</span></span>  
  
1.  <span data-ttu-id="f612f-113">Haga clic con el botón derecho en una serie o en un campo del área **Valores** y seleccione **Propiedades de la serie**.</span><span class="sxs-lookup"><span data-stu-id="f612f-113">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="f612f-114">Haga clic en **Leyenda** y, en el cuadro **Texto de leyenda personalizado** , escriba una palabra clave.</span><span class="sxs-lookup"><span data-stu-id="f612f-114">Click **Legend** and in the **Custom legend text** box, type a keyword.</span></span>  
  
 <span data-ttu-id="f612f-115">En la tabla siguiente se proporcionan ejemplos de palabras clave específicas de los gráficos que pueden usarse para la propiedad **Texto de leyenda personalizado** .</span><span class="sxs-lookup"><span data-stu-id="f612f-115">The following table provides examples of chart-specific keywords to use for the **Custom Legend Text** property.</span></span> <span data-ttu-id="f612f-116">Para obtener más información sobre las palabras clave, vea [Aplicar formato a los puntos de datos de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="f612f-116">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
|<span data-ttu-id="f612f-117">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="f612f-117">Keyword</span></span>|<span data-ttu-id="f612f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="f612f-118">Description</span></span>|<span data-ttu-id="f612f-119">El ejemplo de lo que aparece como texto en la leyenda</span><span class="sxs-lookup"><span data-stu-id="f612f-119">Example of what appears as text in the legend</span></span>|  
|-------------|-----------------|---------------------------------------------------|  
|`#PERCENT{P1}`|<span data-ttu-id="f612f-120">Muestra el porcentaje del valor total con un decimal.</span><span class="sxs-lookup"><span data-stu-id="f612f-120">Displays the percentage of the total value to one decimal place.</span></span>|<span data-ttu-id="f612f-121">85.0%</span><span class="sxs-lookup"><span data-stu-id="f612f-121">85.0%</span></span>|  
|`#VALY`|<span data-ttu-id="f612f-122">Muestra el valor numérico real del campo de datos.</span><span class="sxs-lookup"><span data-stu-id="f612f-122">Displays the actual numeric value of the data field.</span></span>|<span data-ttu-id="f612f-123">17000</span><span class="sxs-lookup"><span data-stu-id="f612f-123">17000</span></span>|  
|`#VALY{C2}`|<span data-ttu-id="f612f-124">Muestra el valor numérico real del campo de datos con formato monetario y con dos decimales.</span><span class="sxs-lookup"><span data-stu-id="f612f-124">Displays the actual numeric value of the data field as a currency to two decimal places.</span></span>|<span data-ttu-id="f612f-125">$17000.00</span><span class="sxs-lookup"><span data-stu-id="f612f-125">$17000.00</span></span>|  
|`#AXISLABEL (#PERCENT{P0})`|<span data-ttu-id="f612f-126">Muestra la representación de texto del campo de categorías, seguida por el porcentaje que cada categoría representa en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="f612f-126">Displays the text representation of the category field, followed by the percentage that each category displays on the chart.</span></span>|<span data-ttu-id="f612f-127">Michael Blythe (85%)</span><span class="sxs-lookup"><span data-stu-id="f612f-127">Michael Blythe (85%)</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="f612f-128">La palabra clave #AXISLABEL solo se puede evaluar en tiempo de ejecución cuando no se especifica ningún campo en el área **Grupos de la serie** .</span><span class="sxs-lookup"><span data-stu-id="f612f-128">The #AXISLABEL keyword can only be evaluated at run time when there is not a field specified in the **Series Groups** area.</span></span>  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-non-shape-chart"></a><span data-ttu-id="f612f-129">Para modificar el texto que aparece en la leyenda en un gráfico que no es de formas</span><span class="sxs-lookup"><span data-stu-id="f612f-129">To modify the text that appears in the legend on a non-Shape chart</span></span>  
  
1.  <span data-ttu-id="f612f-130">Haga clic con el botón derecho en una serie o en un campo del área **Valores** y seleccione **Propiedades de la serie**.</span><span class="sxs-lookup"><span data-stu-id="f612f-130">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="f612f-131">Haga clic en **Leyenda** y, en el cuadro **Texto de leyenda personalizado** , escriba una etiqueta de leyenda.</span><span class="sxs-lookup"><span data-stu-id="f612f-131">Click **Legend** and in the **Custom legend text** box, type a legend label.</span></span> <span data-ttu-id="f612f-132">La serie se actualizada con el texto especificado.</span><span class="sxs-lookup"><span data-stu-id="f612f-132">The series is updated with your text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f612f-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f612f-133">See Also</span></span>  
 <span data-ttu-id="f612f-134">[Aplicar formato a la leyenda de un gráfico &#40;Generador de informes y SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="f612f-134">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="f612f-135">[Aplicar formato a los colores de serie de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="f612f-135">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="f612f-136">Ocultar elementos de leyenda en el gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f612f-136">Hide Legend Items on the Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-hide-items-report-builder.md)  
  
  
