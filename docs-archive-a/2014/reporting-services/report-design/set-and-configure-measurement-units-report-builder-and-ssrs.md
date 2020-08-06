---
title: Establecer y configurar unidades de medida (Generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a15a96c3-7d2c-433e-a440-4ea051e967a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c01523dad9a96d2d45b96474d36873bac2484343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662551"
---
# <a name="set-and-configure-measurement-units-report-builder-and-ssrs"></a><span data-ttu-id="d9193-102">Establecer y configurar unidades de medida (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="d9193-102">Set and Configure Measurement Units (Report Builder and SSRS)</span></span>
  <span data-ttu-id="d9193-103">Los indicadores proporcionan dos unidades de medida: porcentaje y numérico.</span><span class="sxs-lookup"><span data-stu-id="d9193-103">Indicators provide two measurement units: percentage and numeric.</span></span> <span data-ttu-id="d9193-104">De forma predeterminada, los indicadores se configuran para usar porcentajes como unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="d9193-104">By default, indicators are configured to use percentages as the measurement unit.</span></span> <span data-ttu-id="d9193-105">Esto significa que un intervalo de porcentajes determina los valores de indicador asignados a cada icono del indicador.</span><span class="sxs-lookup"><span data-stu-id="d9193-105">This means that the indicator values assigned to each icon in the indicator set are determined by a percentage range.</span></span> <span data-ttu-id="d9193-106">Los intervalos de porcentajes están divididos uniformemente entre los iconos del conjunto de indicadores.</span><span class="sxs-lookup"><span data-stu-id="d9193-106">The percentage ranges are evenly divided across the icons in the indicator set.</span></span> <span data-ttu-id="d9193-107">Cada icono representa un estado del indicador.</span><span class="sxs-lookup"><span data-stu-id="d9193-107">Each icon represents an indicator state.</span></span> <span data-ttu-id="d9193-108">Puede cambiar los porcentajes para cada icono en el conjunto de indicadores especificando porcentajes inicial y final diferentes.</span><span class="sxs-lookup"><span data-stu-id="d9193-108">You can change the percentages for each icon in the indicator set by specifying different start and end percentages.</span></span> <span data-ttu-id="d9193-109">Los indicadores también detectan automáticamente los valores máximo y mínimo de los datos.</span><span class="sxs-lookup"><span data-stu-id="d9193-109">Indicators also automatically detect the minimum and maximum values in the data.</span></span>  
  
 <span data-ttu-id="d9193-110">Puede cambiar la unidad de medida para que sea un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="d9193-110">You can change the measurement unit to be a numeric value.</span></span> <span data-ttu-id="d9193-111">En este caso, no especifica para los datos el valor mínimo sino el máximo; en su lugar, solo proporciona los valores inicial y final para cada icono que usa el indicador.</span><span class="sxs-lookup"><span data-stu-id="d9193-111">In this case, you do not specify minimum or maximum for the data; instead, you provide only the start and end values for each icon that the indicator uses.</span></span>  
  
 <span data-ttu-id="d9193-112">Opciones como las unidades de medida se pueden establecer mediante expresiones.</span><span class="sxs-lookup"><span data-stu-id="d9193-112">Options such as measurement units can be set by using expressions.</span></span> <span data-ttu-id="d9193-113">Para más información, vea [Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d9193-113">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-use-the-numeric-state-measurement-unit"></a><span data-ttu-id="d9193-114">Utilizar la unidad de medida de estado numérica</span><span class="sxs-lookup"><span data-stu-id="d9193-114">To use the numeric state measurement unit</span></span>  
  
1.  <span data-ttu-id="d9193-115">Haga clic con el botón derecho en el indicador que quiera cambiar y seleccione **Propiedades de indicador**.</span><span class="sxs-lookup"><span data-stu-id="d9193-115">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="d9193-116">Haga clic en **Valores y estados** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="d9193-116">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="d9193-117">En la lista **Unidad de medida de estados** , haga clic en **Numérico**.</span><span class="sxs-lookup"><span data-stu-id="d9193-117">In the **States Measurement Unit** list, click **Numeric**.</span></span>  
  
     <span data-ttu-id="d9193-118">Si quiere, haga clic en el botón **Expresión** (*fx*) para modificar la expresión que establece los valores de la opción.</span><span class="sxs-lookup"><span data-stu-id="d9193-118">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="d9193-119">Para cada icono en el indicador establecido, actualice los valores de los cuadros de texto **Inicial** y **Final** .</span><span class="sxs-lookup"><span data-stu-id="d9193-119">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="d9193-120">Si quiere, haga clic en el botón **Expresión** (*fx*) para modificar la expresión que establece los valores de las opciones **Inicial** y **Final** .</span><span class="sxs-lookup"><span data-stu-id="d9193-120">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d9193-121">Los valores de los cuadros de texto **Inicial** y **Final** deben ser numéricos.</span><span class="sxs-lookup"><span data-stu-id="d9193-121">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-use-the-percentage-measurement-unit"></a><span data-ttu-id="d9193-122">Para utilizar la unidad de medida en porcentaje</span><span class="sxs-lookup"><span data-stu-id="d9193-122">To use the percentage measurement unit</span></span>  
  
1.  <span data-ttu-id="d9193-123">Haga clic con el botón derecho en el indicador que quiera cambiar y seleccione **Propiedades de indicador**.</span><span class="sxs-lookup"><span data-stu-id="d9193-123">Right-click the indicator you want to change and click **Indicator Properties**.</span></span>  
  
2.  <span data-ttu-id="d9193-124">Haga clic en **Valores y estados** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="d9193-124">Click **Values and States** in the left pane.</span></span>  
  
3.  <span data-ttu-id="d9193-125">En la lista **Unidad de medida de estados** , haga clic en **Porcentaje**.</span><span class="sxs-lookup"><span data-stu-id="d9193-125">In the **States Measurement Unit** list, click **Percentage**.</span></span>  
  
     <span data-ttu-id="d9193-126">Si quiere, haga clic en el botón **Expresión** (*fx*) para modificar la expresión que establece los valores de la opción.</span><span class="sxs-lookup"><span data-stu-id="d9193-126">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
4.  <span data-ttu-id="d9193-127">Opcionalmente, cambie las opciones **Mínimo** y **Máximo** para usar valores concretos en lugar de detectar automáticamente los valores máximo y mínimo de los datos usados en el indicador.</span><span class="sxs-lookup"><span data-stu-id="d9193-127">Optionally, change the **Minimum** and **Maximum** options to use specific values instead of automatically detecting the minimum and maximum values of the data that the indicator uses.</span></span> <span data-ttu-id="d9193-128">El valor de **Mínimo** debe ser menor que el valor de **Máximo**.</span><span class="sxs-lookup"><span data-stu-id="d9193-128">The value of **Minimum** must be smaller than the value of **Maximum**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d9193-129">Si establece los valores mínimo y máximo explícitamente, el indicador utiliza ese intervalo de valores sin tener en cuenta los valores máximo y mínimo reales de los datos.</span><span class="sxs-lookup"><span data-stu-id="d9193-129">If you explicitly set minimum and maximum values, that value range is used by the indicator regardless of the actual the minimum and maximum values in the data.</span></span> <span data-ttu-id="d9193-130">Esto significa que los valores menores que el mínimo y mayores que el máximo se excluye de la evaluación que determina qué icono de indicador se va a mostrar en el informe.</span><span class="sxs-lookup"><span data-stu-id="d9193-130">This means that values lower than the minimum and higher than the maximum are excluded from the evaluation that determine what indictor icon to show in the report.</span></span>  
  
     <span data-ttu-id="d9193-131">Si quiere, haga clic en el botón **Expresión** (*fx*) para modificar la expresión que establece los valores de la opción.</span><span class="sxs-lookup"><span data-stu-id="d9193-131">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the option.</span></span>  
  
5.  <span data-ttu-id="d9193-132">Para cada icono en el indicador establecido, actualice los valores de los cuadros de texto **Inicial** y **Final** .</span><span class="sxs-lookup"><span data-stu-id="d9193-132">For each icon in the indicator set, update the values in the **Start** and **End** text boxes.</span></span>  
  
     <span data-ttu-id="d9193-133">Si quiere, haga clic en el botón **Expresión** (*fx*) para modificar la expresión que establece los valores de las opciones **Inicial** y **Final** .</span><span class="sxs-lookup"><span data-stu-id="d9193-133">Optionally, click the **Expression** (*fx*) button to edit an expression that sets the values of the **Start** and **End** options.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d9193-134">Los valores de los cuadros de texto **Inicial** y **Final** deben ser numéricos.</span><span class="sxs-lookup"><span data-stu-id="d9193-134">The values in the **Start** and **End** text boxes must be numeric.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d9193-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d9193-135">See Also</span></span>  
 [<span data-ttu-id="d9193-136">Indicadores &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d9193-136">Indicators &#40;Report Builder and SSRS&#41;</span></span>](indicators-report-builder-and-ssrs.md)  
  
  
