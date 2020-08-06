---
title: Resaltar datos en el gráfico agregando franjas (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: addd6137-4b6e-4e88-a7e8-9600fcd1ccce
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 01b0bb41a71daf9ac558ce8d8bb84480426870c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663905"
---
# <a name="highlight-chart-data-by-adding-strip-lines-report-builder-and-ssrs"></a><span data-ttu-id="be5c8-102">Resaltar datos en el gráfico agregando franjas (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="be5c8-102">Highlight Chart Data by Adding Strip Lines (Report Builder and SSRS)</span></span>
  <span data-ttu-id="be5c8-103">Las franjas son intervalos horizontales o verticales que sombrean el fondo del gráfico a intervalos regulares o personalizados.</span><span class="sxs-lookup"><span data-stu-id="be5c8-103">Strip lines, or strips, are horizontal or vertical ranges that shade the background of the chart in regular or custom intervals.</span></span> <span data-ttu-id="be5c8-104">Puede usar las franjas para:</span><span class="sxs-lookup"><span data-stu-id="be5c8-104">You can use strip lines to:</span></span>  
  
-   <span data-ttu-id="be5c8-105">Mejorar la legibilidad y facilitar la búsqueda de valores individuales en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="be5c8-105">Improve readability for looking up individual values on the chart.</span></span> <span data-ttu-id="be5c8-106">Especifique franjas a intervalos regulares para ayudar a separar los puntos de datos durante la lectura del gráfico.</span><span class="sxs-lookup"><span data-stu-id="be5c8-106">Specify strip lines at regular intervals to help separate data points when reading the chart.</span></span>  
  
-   <span data-ttu-id="be5c8-107">Resaltar fechas que tienen lugar a intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="be5c8-107">Highlight dates that occur at regular intervals.</span></span> <span data-ttu-id="be5c8-108">Por ejemplo, en un informe de ventas puede usar franjas para identificar los puntos de datos correspondientes a los fines de semana.</span><span class="sxs-lookup"><span data-stu-id="be5c8-108">For example, in a sales report you might use strip lines to identify weekend data points.</span></span>  
  
-   <span data-ttu-id="be5c8-109">Resaltar un intervalo con clave concreto.</span><span class="sxs-lookup"><span data-stu-id="be5c8-109">Highlight a specific key range.</span></span> <span data-ttu-id="be5c8-110">Siguiendo con el ejemplo anterior, podría usar una franja para resaltar el intervalo de ventas más alto, comprendido entre 80 y 100 dólares.</span><span class="sxs-lookup"><span data-stu-id="be5c8-110">Using the previous example, you can use one strip line to highlight the highest range of sales that is between $80-100.</span></span>  
  
 <span data-ttu-id="be5c8-111">Las franjas no se pueden aplicar a los gráficos de formas ni a los gráficos polares.</span><span class="sxs-lookup"><span data-stu-id="be5c8-111">Strip lines are not applicable to Shape or Polar chart types.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-interlaced-strip-lines-at-regular-intervals-on-a-chart"></a><span data-ttu-id="be5c8-112">Mostrar en un gráfico franjas entrelazadas a intervalos regulares</span><span class="sxs-lookup"><span data-stu-id="be5c8-112">To display interlaced strip lines at regular intervals on a chart</span></span>  
  
1.  <span data-ttu-id="be5c8-113">Para mostrar las franjas horizontales, haga clic con el botón derecho en el eje del gráfico vertical y haga clic en **Propiedades del eje vertical**.</span><span class="sxs-lookup"><span data-stu-id="be5c8-113">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="be5c8-114">Para mostrar las franjas verticales, haga clic con el botón derecho en el eje del gráfico horizontal y haga clic en **Propiedades del eje horizontal**.</span><span class="sxs-lookup"><span data-stu-id="be5c8-114">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
2.  <span data-ttu-id="be5c8-115">Seleccione la opción **Usar entrelazado** .</span><span class="sxs-lookup"><span data-stu-id="be5c8-115">Select the **Use interlacing** option.</span></span> <span data-ttu-id="be5c8-116">En el gráfico aparecerán franjas de color gris.</span><span class="sxs-lookup"><span data-stu-id="be5c8-116">Grey strip lines will appear on your chart.</span></span>  
  
3.  <span data-ttu-id="be5c8-117">(Opcional) Especifique un color para las franjas; para ello, use la lista desplegable **Color** .</span><span class="sxs-lookup"><span data-stu-id="be5c8-117">(Optional) Specify a color for the strip lines using the adjacent **Color** drop-down list.</span></span>  
  
### <a name="to-display-interlaced-strip-lines-at-custom-intervals-on-a-chart"></a><span data-ttu-id="be5c8-118">Mostrar en un gráfico franjas entrelazadas a intervalos personalizados</span><span class="sxs-lookup"><span data-stu-id="be5c8-118">To display interlaced strip lines at custom intervals on a chart</span></span>  
  
1.  <span data-ttu-id="be5c8-119">Para mostrar las franjas horizontales, haga clic con el botón derecho en el eje del gráfico vertical y haga clic en **Propiedades del eje vertical**.</span><span class="sxs-lookup"><span data-stu-id="be5c8-119">To show horizontal strip lines, right-click the vertical chart axis and click **VerticalAxis Properties**.</span></span>  
  
     <span data-ttu-id="be5c8-120">Para mostrar las franjas verticales, haga clic con el botón derecho en el eje del gráfico horizontal y haga clic en **Propiedades del eje horizontal**.</span><span class="sxs-lookup"><span data-stu-id="be5c8-120">To show vertical strip lines, right-click the horizontal chart axis and click **Horizontal Axis Properties**.</span></span>  
  
     <span data-ttu-id="be5c8-121">En la ventana de propiedades se muestran las propiedades del eje.</span><span class="sxs-lookup"><span data-stu-id="be5c8-121">The axis properties are displayed in the Properties window.</span></span>  
  
2.  <span data-ttu-id="be5c8-122">En la sección **Apariencia** del panel de propiedades, para la propiedad StripLines, haga clic en el botón para editar colecciones (...) con el fin de abrir el **Editor de la colección ChartStripLine**.</span><span class="sxs-lookup"><span data-stu-id="be5c8-122">In the **Appearance** section of the Properties pane, for the StripLines property, click the Edit Collection (...) button to open the **ChartStripLine Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="be5c8-123">Haga clic en **Agregar** para agregar una nueva franja a la colección.</span><span class="sxs-lookup"><span data-stu-id="be5c8-123">Click **Add** to add a new strip line to the collection.</span></span>  
  
4.  <span data-ttu-id="be5c8-124">Haga clic en StripWidth para especificar el ancho de la franja, que se mide en pulgadas en el informe.</span><span class="sxs-lookup"><span data-stu-id="be5c8-124">Click StripWidth to specify the width of the strip line, measured in inches on the report.</span></span> <span data-ttu-id="be5c8-125">Si está resaltando fechas u horas, haga clic en StripWidthType y seleccione un intervalo de tiempo.</span><span class="sxs-lookup"><span data-stu-id="be5c8-125">If you are highlighting dates or times, click StripWidthType and select a time interval.</span></span>  
  
5.  <span data-ttu-id="be5c8-126">Escriba un valor o una expresión para Interval para especificar la frecuencia de repetición de la franja.</span><span class="sxs-lookup"><span data-stu-id="be5c8-126">Type a value or expression for the Interval to specify how often the strip line will repeat.</span></span>  <span data-ttu-id="be5c8-127">Por ejemplo, si especifica un intervalo de 10, y el ancho de la franja es 5, las franjas se mostrarán en los valores 0 a 5, 15 a 20, 30 a 35, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="be5c8-127">For example, if you specify an interval of 10, and your strip line width is 5, strip lines will display at values of 0 to 5, 15 to 20, 30 to 35, and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="be5c8-128">De forma predeterminada, Interval está establecido en automático, lo que significa que el gráfico no calculará un intervalo para las franjas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="be5c8-128">By default, Interval is set to Auto, which means the chart will not calculate an interval for custom strip lines.</span></span> <span data-ttu-id="be5c8-129">El gráfico solamente calcula los intervalos para las franjas si se establece un valor de intervalo.</span><span class="sxs-lookup"><span data-stu-id="be5c8-129">The chart only calculates intervals for strip lines if an interval value is set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be5c8-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be5c8-130">See Also</span></span>  
 <span data-ttu-id="be5c8-131">[Aplicar formato a las etiquetas de los ejes de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="be5c8-131">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="be5c8-132">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="be5c8-132">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="be5c8-133">Agregar una media móvil a un gráfico &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="be5c8-133">Add a Moving Average to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-moving-average-to-a-chart-report-builder-and-ssrs.md)  
  
  
