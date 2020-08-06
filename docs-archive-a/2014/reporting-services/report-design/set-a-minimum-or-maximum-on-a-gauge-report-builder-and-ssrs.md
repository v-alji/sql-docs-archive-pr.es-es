---
title: Establecer un valor mínimo o máximo en un medidor (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b4c260c0-5a88-4f30-8977-eb5cc78fc146
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 344122dbff647a8c35b838ecce637602f202864b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663904"
---
# <a name="set-a-minimum-or-maximum-on-a-gauge-report-builder-and-ssrs"></a><span data-ttu-id="97bcc-102">Establecer un valor mínimo o máximo en un medidor (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="97bcc-102">Set a Minimum or Maximum on a Gauge (Report Builder and SSRS)</span></span>
  <span data-ttu-id="97bcc-103">A diferencia del gráfico, donde se definen varios grupos, el medidor solo muestra un valor.</span><span class="sxs-lookup"><span data-stu-id="97bcc-103">Unlike the chart, where multiple groups are defined, the gauge only shows one value.</span></span> <span data-ttu-id="97bcc-104">Puesto que el Generador de informes y el Diseñador de informes determinan el contexto o la importancia relativa del valor que se está intentando mostrar en el medidor, se deberán definir los valores mínimo y máximo de la escala.</span><span class="sxs-lookup"><span data-stu-id="97bcc-104">Since Report Builder and Report Designer determine the context or relative significance of the one value that you are trying to show on the gauge, you must define the minimum and maximum of the scale.</span></span> <span data-ttu-id="97bcc-105">Por ejemplo, si los valores de datos son clasificaciones entre 0 y 10, le interesará establecer el mínimo en 0 y el máximo en 10.</span><span class="sxs-lookup"><span data-stu-id="97bcc-105">For example, if your data values are rankings between 0 and 10, you will want to set the minimum to 0 and maximum to 10.</span></span> <span data-ttu-id="97bcc-106">Los números del intervalo se calculan automáticamente en función de los valores mínimo y máximo especificados.</span><span class="sxs-lookup"><span data-stu-id="97bcc-106">The interval numbers are calculated automatically based on the values specified for the minimum and maximum.</span></span> <span data-ttu-id="97bcc-107">De forma predeterminada, los valores mínimo y máximo están establecidos en 0 y 100, pero estos son valores arbitrarios que conviene cambiar.</span><span class="sxs-lookup"><span data-stu-id="97bcc-107">By default, the minimum and maximum are set to 0 and 100, but this is an arbitrary value that you should change.</span></span> <span data-ttu-id="97bcc-108">La aplicación no calcula el valor como un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="97bcc-108">The application does not calculate your value as a percentage.</span></span>  
  
 <span data-ttu-id="97bcc-109">Si el intervalo de valores es grande, por ejemplo de 0 a 10000, considere la posibilidad de usar un multiplicador para reducir el número de ceros en el medidor.</span><span class="sxs-lookup"><span data-stu-id="97bcc-109">If the range of your values is large, for example from 0 to 10000, consider using a multiplier to reduce the number of zeroes on the gauge.</span></span> <span data-ttu-id="97bcc-110">El multiplicador únicamente reducirá la escala de los números en el medidor, no el valor en sí mismo.</span><span class="sxs-lookup"><span data-stu-id="97bcc-110">The multiplier will only reduce the scale of the numbers on the gauge, not the value itself.</span></span>  
  
 <span data-ttu-id="97bcc-111">Puede utilizar las expresiones para establecer los valores de las opciones **Mínimo** y **Máximo** .</span><span class="sxs-lookup"><span data-stu-id="97bcc-111">You can use expressions to set the values of the **Minimum** and **Maximum** options.</span></span> <span data-ttu-id="97bcc-112">Para más información, vea [Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="97bcc-112">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-set-the-minimum-and-maximum-on-the-gauge"></a><span data-ttu-id="97bcc-113">Para establecer los valores mínimo y máximo en el medidor</span><span class="sxs-lookup"><span data-stu-id="97bcc-113">To set the minimum and maximum on the gauge</span></span>  
  
1.  <span data-ttu-id="97bcc-114">Haga clic con el botón derecho en la escala y seleccione **Propiedades de escala**.</span><span class="sxs-lookup"><span data-stu-id="97bcc-114">Right-click on the scale and select **Scale Properties**.</span></span> <span data-ttu-id="97bcc-115">Aparece el cuadro de diálogo **Propiedades de escala** .</span><span class="sxs-lookup"><span data-stu-id="97bcc-115">The **Scale Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="97bcc-116">En **General**, especifique un valor para **Mínimo**.</span><span class="sxs-lookup"><span data-stu-id="97bcc-116">In **General**, specify a value for **Minimum**.</span></span> <span data-ttu-id="97bcc-117">De forma predeterminada, este valor es 0.</span><span class="sxs-lookup"><span data-stu-id="97bcc-117">By default, this value is 0.</span></span> <span data-ttu-id="97bcc-118">Si quiere, haga clic en el botón **Expresión** (*fx*) para modificar la expresión que establece el valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="97bcc-118">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
3.  <span data-ttu-id="97bcc-119">Especifique un valor **Máximo**.</span><span class="sxs-lookup"><span data-stu-id="97bcc-119">Specify a value for **Maximum**.</span></span> <span data-ttu-id="97bcc-120">De forma predeterminada, este valor es 100.</span><span class="sxs-lookup"><span data-stu-id="97bcc-120">By default, this value is 100.</span></span> <span data-ttu-id="97bcc-121">Si quiere, haga clic en el botón **Expresión** (*fx*) para modificar la expresión que establece el valor de la opción.</span><span class="sxs-lookup"><span data-stu-id="97bcc-121">Optionally, click the **Expression** (*fx*) button to edit the expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="97bcc-122">(Opcional) Si los valores mínimo y máximo son grandes, especifique un valor para la opción **Multiplicar etiquetas de escala por** .</span><span class="sxs-lookup"><span data-stu-id="97bcc-122">(Optional) If the values for your minimum and maximum are large, specify a value for the **Multiply scale labels by** option.</span></span> <span data-ttu-id="97bcc-123">Para especificar un multiplicador que reduzca la escala, use un número decimal.</span><span class="sxs-lookup"><span data-stu-id="97bcc-123">To specify a multiplier that reduces your scale, use a decimal number.</span></span> <span data-ttu-id="97bcc-124">Por ejemplo, si tiene una escala de 0 a 1000, puede especificar un valor de multiplicador de 0,01 para que se vea de 0 a 10.</span><span class="sxs-lookup"><span data-stu-id="97bcc-124">For example, if you have a scale from 0 to 1000, you can specify a multiplier value of 0.01 to reduce the scale to read 0 to 10.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97bcc-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="97bcc-125">See Also</span></span>  
 <span data-ttu-id="97bcc-126">[Aplicar formato a las escalas de un medidor &#40;Generador de informes y SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="97bcc-126">[Formatting Scales on a Gauge &#40;Report Builder and SSRS&#41;](formatting-scales-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="97bcc-127">[Aplicar formato a los punteros de un medidor &#40;Generador de informes y SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="97bcc-127">[Formatting Pointers on a Gauge &#40;Report Builder and SSRS&#41;](formatting-pointers-on-a-gauge-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="97bcc-128">Medidores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="97bcc-128">Gauges &#40;Report Builder and SSRS&#41;</span></span>](gauges-report-builder-and-ssrs.md)  
  
  
