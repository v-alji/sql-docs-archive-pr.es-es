---
title: Explorador de KPI (pestaña KPI, diseñador de cubos) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.kpibrowserpane.f1
ms.assetid: 2f61bde6-e6ec-4511-8645-c272374014ad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 591dfb7c27842e365b78484153dbbde3713b452e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669947"
---
# <a name="kpi-browser-kpis-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="c9604-102">Explorador de KPI (pestaña KPI, Diseñador de cubos) (Analysis Services - Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="c9604-102">KPI Browser (KPIs Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="c9604-103">Use el panel **Explorador de KPI** de la pestaña **KPI** del Diseñador de cubos para ver y comprobar el resultado de los indicadores clave de rendimiento (KPI).</span><span class="sxs-lookup"><span data-stu-id="c9604-103">Use the **KPI Browser** pane on the **KPIs** tab in Cube Designer to view and test the results of Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="c9604-104">Los KPI deben implementarse primero en una instancia de antes de la [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] exploración.</span><span class="sxs-lookup"><span data-stu-id="c9604-104">KPIs must first be deployed to a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance before browsing.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9604-105">Este panel solo se muestra en vista de explorador.</span><span class="sxs-lookup"><span data-stu-id="c9604-105">This pane is displayed only in browser view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9604-106">Opciones</span><span class="sxs-lookup"><span data-stu-id="c9604-106">Options</span></span>  
 <span data-ttu-id="c9604-107">**Cuadrícula de subcubo**</span><span class="sxs-lookup"><span data-stu-id="c9604-107">**Subcube grid**</span></span>  
 <span data-ttu-id="c9604-108">Se usa para definir un subcubo y restringir el resultado de los KPI que se van a mostrar en el panel **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="c9604-108">Use to define a subcube and restrict the results of the KPIs to be displayed in the **Results** pane.</span></span> <span data-ttu-id="c9604-109">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c9604-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="c9604-110">**Dimensión**</span><span class="sxs-lookup"><span data-stu-id="c9604-110">**Dimension**</span></span>  
 <span data-ttu-id="c9604-111">Seleccione la dimensión a la que se aplica este filtro.</span><span class="sxs-lookup"><span data-stu-id="c9604-111">Select the dimension to which this filter applies.</span></span>  
  
 <span data-ttu-id="c9604-112">**Hierarchy**</span><span class="sxs-lookup"><span data-stu-id="c9604-112">**Hierarchy**</span></span>  
 <span data-ttu-id="c9604-113">Seleccione la jerarquía a la que se aplica este filtro.</span><span class="sxs-lookup"><span data-stu-id="c9604-113">Select the hierarchy to which this filter applies.</span></span>  
  
 <span data-ttu-id="c9604-114">**Operador**</span><span class="sxs-lookup"><span data-stu-id="c9604-114">**Operator**</span></span>  
 <span data-ttu-id="c9604-115">Seleccione el operador que define cómo se aplica la expresión de **Expresión de filtro** en la jerarquía seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c9604-115">Select the operator that defines how the expression in **Filter Expression** is applied to the selected hierarchy.</span></span> <span data-ttu-id="c9604-116">En la tabla siguiente se describen los operadores disponibles.</span><span class="sxs-lookup"><span data-stu-id="c9604-116">The following table describes the available operators.</span></span>  
  
|<span data-ttu-id="c9604-117">Value</span><span class="sxs-lookup"><span data-stu-id="c9604-117">Value</span></span>|<span data-ttu-id="c9604-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9604-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c9604-119">**Igual**</span><span class="sxs-lookup"><span data-stu-id="c9604-119">**Equal**</span></span>|<span data-ttu-id="c9604-120">Los resultados están restringidos al conjunto definido en **Expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9604-120">The results are restricted to the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="c9604-121">**No igual**</span><span class="sxs-lookup"><span data-stu-id="c9604-121">**Not Equal**</span></span>|<span data-ttu-id="c9604-122">Los resultados están restringidos a los miembros excluidos por el conjunto definido en **Expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9604-122">The results are restricted to the members excluded by the set defined in **Filter Expression**.</span></span>|  
|<span data-ttu-id="c9604-123">**En**</span><span class="sxs-lookup"><span data-stu-id="c9604-123">**In**</span></span>|<span data-ttu-id="c9604-124">Los resultados están restringidos al conjunto con nombre seleccionado en **Expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9604-124">The results are restricted to the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="c9604-125">**No en el**</span><span class="sxs-lookup"><span data-stu-id="c9604-125">**Not In**</span></span>|<span data-ttu-id="c9604-126">Los resultados están restringidos a los miembros excluidos por el conjunto con nombre seleccionado en **Expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9604-126">The results are restricted to the members excluded by the named set chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="c9604-127">**Contains**</span><span class="sxs-lookup"><span data-stu-id="c9604-127">**Contains**</span></span>|<span data-ttu-id="c9604-128">El resultado se restringe a los miembros cuyos nombres contienen la cadena de **Expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9604-128">The results are restricted to members whose member names contain the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="c9604-129">**Comienza por**</span><span class="sxs-lookup"><span data-stu-id="c9604-129">**Begins With**</span></span>|<span data-ttu-id="c9604-130">El resultado se restringe a los miembros cuyos nombres comienzan con la cadena de **Expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9604-130">The results are restricted to members whose member names begin with the string in **Filter Expression**.</span></span>|  
|<span data-ttu-id="c9604-131">**Intervalo (Inclusivo)**</span><span class="sxs-lookup"><span data-stu-id="c9604-131">**Range (Inclusive)**</span></span>|<span data-ttu-id="c9604-132">El resultado se restringe al intervalo elegido en **Expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9604-132">The results are restricted to the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="c9604-133">**Intervalo (Exclusivo)**</span><span class="sxs-lookup"><span data-stu-id="c9604-133">**Range (Exclusive)**</span></span>|<span data-ttu-id="c9604-134">El resultado se restringe a los miembros excluidos por el intervalo elegido en **Expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9604-134">The results are restricted to the members excluded by the range chosen in **Filter Expression**.</span></span>|  
|<span data-ttu-id="c9604-135">**MDX.**</span><span class="sxs-lookup"><span data-stu-id="c9604-135">**MDX**</span></span>|<span data-ttu-id="c9604-136">El resultado se restringe a la expresión MDX (Expresiones multidimensionales) establecida en **Expresión de filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9604-136">The results are restricted to the Multidimensional Expressions (MDX) expression set in **Filter Expression**.</span></span>|  
  
 <span data-ttu-id="c9604-137">**Expresión de filtro**</span><span class="sxs-lookup"><span data-stu-id="c9604-137">**Filter Expression**</span></span>  
 <span data-ttu-id="c9604-138">Escriba la expresión que evaluará el **Operador**, lo que restringe el resultado de KPI que se examinará.</span><span class="sxs-lookup"><span data-stu-id="c9604-138">Type the expression that is to be evaluated by **Operator**, which restricts the KPI results to be browsed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9604-139">Este campo es un elemento de entrada de datos dinámico que cambia el aspecto para reflejar los tipos de datos necesarios para el operador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c9604-139">This field is a dynamic data entry element, changing appearance to reflect the types of data necessary for the selected operator.</span></span>  
  
 <span data-ttu-id="c9604-140">**Cuadrícula de resultados**</span><span class="sxs-lookup"><span data-stu-id="c9604-140">**Results grid**</span></span>  
 <span data-ttu-id="c9604-141">Muestra el valor evaluado, el objetivo, el estado y la tendencia de los KPI, basándose en el filtro definido en **Cuadrícula de filtro**.</span><span class="sxs-lookup"><span data-stu-id="c9604-141">Displays the evaluated value, goal, status, and trend for the KPIs, based on the filter defined in **Filter grid**.</span></span> <span data-ttu-id="c9604-142">La cuadrícula contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c9604-142">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="c9604-143">**Mostrar estructura**</span><span class="sxs-lookup"><span data-stu-id="c9604-143">**Display Structure**</span></span>  
 <span data-ttu-id="c9604-144">Muestra los KPI que contiene el cubo, organizado jerárquicamente según los valores de **Carpeta para mostrar** o **KPI primario** de cada KPI.</span><span class="sxs-lookup"><span data-stu-id="c9604-144">Displays the KPIs contained by the cube, hierarchically organized according to the **Display folder** or **Parent KPI** values for each KPI.</span></span>  
  
 <span data-ttu-id="c9604-145">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c9604-145">**Value**</span></span>  
 <span data-ttu-id="c9604-146">Muestra el valor del KPI.</span><span class="sxs-lookup"><span data-stu-id="c9604-146">Displays the value of the KPI.</span></span>  
  
 <span data-ttu-id="c9604-147">**Objetivo**</span><span class="sxs-lookup"><span data-stu-id="c9604-147">**Goal**</span></span>  
 <span data-ttu-id="c9604-148">Muestra el valor objetivo del KPI.</span><span class="sxs-lookup"><span data-stu-id="c9604-148">Displays the goal value of the KPI.</span></span>  
  
 <span data-ttu-id="c9604-149">**Estado**</span><span class="sxs-lookup"><span data-stu-id="c9604-149">**Status**</span></span>  
 <span data-ttu-id="c9604-150">Muestra el gráfico de estado del KPI.</span><span class="sxs-lookup"><span data-stu-id="c9604-150">Displays the status graphic of the KPI.</span></span>  
  
 <span data-ttu-id="c9604-151">**Tendencia**</span><span class="sxs-lookup"><span data-stu-id="c9604-151">**Trend**</span></span>  
 <span data-ttu-id="c9604-152">Muestra el gráfico de tendencia del KPI.</span><span class="sxs-lookup"><span data-stu-id="c9604-152">Displays the trend graphic of the KPI.</span></span>  
  
 <span data-ttu-id="c9604-153">**Peso**</span><span class="sxs-lookup"><span data-stu-id="c9604-153">**Weight**</span></span>  
 <span data-ttu-id="c9604-154">Muestra el factor de peso del KPI.</span><span class="sxs-lookup"><span data-stu-id="c9604-154">Displays the weight factor of the KPI.</span></span>  
  
 <span data-ttu-id="c9604-155">**Denominación**</span><span class="sxs-lookup"><span data-stu-id="c9604-155">**(Description)**</span></span>  
 <span data-ttu-id="c9604-156">Muestra un icono de información si se proporciona una descripción para un KPI.</span><span class="sxs-lookup"><span data-stu-id="c9604-156">Displays an information icon if a description is provided for a KPI.</span></span>  
  
 <span data-ttu-id="c9604-157">Mantenga el mouse sobre el icono de información para mostrar la Información sobre herramientas que contiene la descripción del KPI.</span><span class="sxs-lookup"><span data-stu-id="c9604-157">Hover the mouse over the information icon to display a ToolTip containing the description for the KPI.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9604-158">Si se produce un error al calcular un KPI en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , esta opción muestra información asociada con el error.</span><span class="sxs-lookup"><span data-stu-id="c9604-158">If an error occurs while calculating a KPI on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, this option displays information associated with the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9604-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9604-159">See Also</span></span>  
 [<span data-ttu-id="c9604-160">KPI &#40;diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="c9604-160">KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](kpis-cube-designer-analysis-services-multidimensional-data.md)  
  
  
