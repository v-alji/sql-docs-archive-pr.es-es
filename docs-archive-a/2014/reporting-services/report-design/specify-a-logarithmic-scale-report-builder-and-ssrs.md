---
title: Especificar una escala logarítmica (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f3092c1c-b128-433d-9a95-983508b2a8d4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2cc422a6f95a420445dc604d08a23e8f8e65c95d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662535"
---
# <a name="specify-a-logarithmic-scale-report-builder-and-ssrs"></a><span data-ttu-id="7361f-102">Especificar una escala logarítmica (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="7361f-102">Specify a Logarithmic Scale (Report Builder and SSRS)</span></span>
  <span data-ttu-id="7361f-103">Si tiene datos que son proporcionales en términos logarítmicos, puede que le interese usar una escala logarítmica en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="7361f-103">If you have data that is logarithmically proportional, you may want to consider using a logarithmic scale on the chart.</span></span> <span data-ttu-id="7361f-104">Esto le ayudará a mejorar el aspecto del gráfico haciendo que los datos sean más fáciles de interpretar.</span><span class="sxs-lookup"><span data-stu-id="7361f-104">This helps improve the appearance of the chart by making your data more manageable.</span></span> <span data-ttu-id="7361f-105">La mayoría de las escalas logarítmicas son de base 10.</span><span class="sxs-lookup"><span data-stu-id="7361f-105">Most logarithmic scales use a base of 10.</span></span>  
  
 <span data-ttu-id="7361f-106">Esta característica solo está disponible en el eje de valores.</span><span class="sxs-lookup"><span data-stu-id="7361f-106">This feature is only available on the value axis.</span></span> <span data-ttu-id="7361f-107">El eje de valores es normalmente el vertical, o eje Y.</span><span class="sxs-lookup"><span data-stu-id="7361f-107">The value axis is usually the vertical, or y-axis.</span></span> <span data-ttu-id="7361f-108">En los gráficos de barras, sin embargo, es el eje horizontal, o X.</span><span class="sxs-lookup"><span data-stu-id="7361f-108">On bar charts, however, it is the horizontal, or x-axis.</span></span>  
  
 <span data-ttu-id="7361f-109">Si el eje es logarítmico, todas las demás propiedades relativas al eje se ajustarán de acuerdo con una escala logarítmica.</span><span class="sxs-lookup"><span data-stu-id="7361f-109">If your axis is logarithmic, all other properties relating to the axis will be scaled logarithmically.</span></span> <span data-ttu-id="7361f-110">Por ejemplo, si especifica una escala logarítmica de base 10 en el eje y establece un intervalo de eje de 2, se generarán intervalos con una magnitud de 10 elevado a 2, es decir, 100.</span><span class="sxs-lookup"><span data-stu-id="7361f-110">For example, if you specify a base-10 logarithmic scale on your axis, setting an axis interval of 2 will generate intervals in magnitudes of 10 to the power of 2, or 100.</span></span> <span data-ttu-id="7361f-111">Esto significa que en el eje de valores aparecerán los valores 1, 100, 10000, en lugar del resultado predeterminado 1, 10, 100, 1000, 10000.</span><span class="sxs-lookup"><span data-stu-id="7361f-111">This means your axis values will read 1, 100, 10000, instead of the default result of 1, 10, 100, 1000, 10000.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-logarithmic-scale"></a><span data-ttu-id="7361f-112">Para especificar una escala logarítmica</span><span class="sxs-lookup"><span data-stu-id="7361f-112">To specify a logarithmic scale</span></span>  
  
1.  <span data-ttu-id="7361f-113">Haga clic con el botón derecho en el eje Y del gráfico y, después, haga clic en **Propiedades del eje vertical**.</span><span class="sxs-lookup"><span data-stu-id="7361f-113">Right-click the y-axis of your chart, and click **VerticalAxis Properties**.</span></span> <span data-ttu-id="7361f-114">Se abrirá el cuadro de diálogo **Propiedades del eje vertical** .</span><span class="sxs-lookup"><span data-stu-id="7361f-114">The **VerticalAxis Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="7361f-115">En **Opciones del eje**, seleccione **Usar escala logarítmica**.</span><span class="sxs-lookup"><span data-stu-id="7361f-115">In **Axis Options**, select **Uselogarithmic scale**.</span></span>  
  
3.  <span data-ttu-id="7361f-116">En el cuadro de texto **Base logarítmica** , escriba un valor positivo para la base logarítmica.</span><span class="sxs-lookup"><span data-stu-id="7361f-116">In the **Logbase** text box, type a positive value for the logarithmic base.</span></span> <span data-ttu-id="7361f-117">Si no se especifica ningún valor, el valor predeterminado para la base logarítmica es 10.</span><span class="sxs-lookup"><span data-stu-id="7361f-117">If no value is specified, the logarithmic base defaults to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7361f-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7361f-118">See Also</span></span>  
 <span data-ttu-id="7361f-119">[Aplicar formato a las etiquetas de los ejes de un gráfico &#40;Generador de informes y SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7361f-119">[Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7361f-120">[Aplicar formato a un gráfico &#40;Generador de informes y SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7361f-120">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="7361f-121">[Aplicar formato de fecha o de moneda a las etiquetas de los ejes &#40;Generador de informes y SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="7361f-121">[Format Axis Labels as Dates or Currencies &#40;Report Builder and SSRS&#41;](format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="7361f-122">Gráficos &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="7361f-122">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
