---
title: Definir y examinar KPI | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 648b9a02-1278-4f11-b940-6f0de6a4042d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44febe6c6c5d432f0cdee43e8eaaa3401c54a2c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745478"
---
# <a name="defining-and-browsing-kpis"></a><span data-ttu-id="aa908-102">Definir y examinar KPI</span><span class="sxs-lookup"><span data-stu-id="aa908-102">Defining and Browsing KPIs</span></span>
  <span data-ttu-id="aa908-103">Para definir indicadores clave de rendimiento (KPI), deberá primero definir un nombre de KPI y el grupo de medida con el que desea asociar el KPI.</span><span class="sxs-lookup"><span data-stu-id="aa908-103">To define key performance indicators (KPIs), you first define a KPI name and the measure group to which the KPI is associated.</span></span> <span data-ttu-id="aa908-104">Un KPI se puede asociar con todos los grupos de medida o con un solo grupo de medida.</span><span class="sxs-lookup"><span data-stu-id="aa908-104">A KPI can be associated with all measure groups or with a single measure group.</span></span> <span data-ttu-id="aa908-105">Se definirán entonces los siguientes elementos del KPI:</span><span class="sxs-lookup"><span data-stu-id="aa908-105">You then define the following elements of the KPI:</span></span>

-   <span data-ttu-id="aa908-106">La expresión de valor</span><span class="sxs-lookup"><span data-stu-id="aa908-106">The value expression</span></span>

     <span data-ttu-id="aa908-107">Una expresión de valor es una medida física como Sales, una medida calculada como Profit o un cálculo que se define dentro del KPI mediante una expresión de Expresiones Multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="aa908-107">A value expression is a physical measure such as Sales, a calculated measure such as Profit, or a calculation that is defined within the KPI by using a Multidimensional Expressions (MDX) expression.</span></span>

-   <span data-ttu-id="aa908-108">La expresión objetivo</span><span class="sxs-lookup"><span data-stu-id="aa908-108">The goal expression</span></span>

     <span data-ttu-id="aa908-109">Una expresión objetivo es un valor, o una expresión MDX que se resuelve en un valor, que define el objetivo de la medida definida por la expresión de valor.</span><span class="sxs-lookup"><span data-stu-id="aa908-109">A goal expression is a value, or an MDX expression that resolves to a value, that defines the target for the measure that the value expression defines.</span></span> <span data-ttu-id="aa908-110">Por ejemplo, una expresión objetivo podría ser la cantidad en la que los responsables de una compañía desean incrementar las ventas o el beneficio.</span><span class="sxs-lookup"><span data-stu-id="aa908-110">For example, a goal expression could be the amount by which the business managers of a company want to increase sales or profit.</span></span>

-   <span data-ttu-id="aa908-111">La expresión de estado</span><span class="sxs-lookup"><span data-stu-id="aa908-111">The status expression</span></span>

     <span data-ttu-id="aa908-112">Una expresión de estado es una expresión MDX que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utiliza para evaluar el estado actual de la expresión de valor en comparación con la expresión objetivo.</span><span class="sxs-lookup"><span data-stu-id="aa908-112">A status expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current status of the value expression compared to the goal expression.</span></span> <span data-ttu-id="aa908-113">Una expresión objetivo es un valor normalizado en el intervalo de -1 a +1, donde -1 es muy malo y +1 es muy bueno.</span><span class="sxs-lookup"><span data-stu-id="aa908-113">A goal expression is a normalized value in the range of -1 to +1, where -1 is very bad, and +1 is very good.</span></span> <span data-ttu-id="aa908-114">La expresión de estado muestra un gráfico para ayudarle a determinar fácilmente el estado de la expresión de valor en comparación con la expresión objetivo.</span><span class="sxs-lookup"><span data-stu-id="aa908-114">The status expression displays a graphic to help you easily determine the status of the value expression compared to the goal expression.</span></span>

-   <span data-ttu-id="aa908-115">La expresión de tendencia</span><span class="sxs-lookup"><span data-stu-id="aa908-115">The trend expression</span></span>

     <span data-ttu-id="aa908-116">Una expresión de tendencia es una expresión MDX que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] utiliza para evaluar la tendencia actual de la expresión de valor en comparación con la expresión objetivo.</span><span class="sxs-lookup"><span data-stu-id="aa908-116">A trend expression is an MDX expression that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to evaluate the current trend of the value expression compared to the goal expression.</span></span> <span data-ttu-id="aa908-117">La expresión de tendencia ayuda al usuario corporativo a determinar rápidamente si la expresión de valor está mejorando o empeorando en relación con la expresión objetivo.</span><span class="sxs-lookup"><span data-stu-id="aa908-117">The trend expression helps the business user to quickly determine whether the value expression is becoming better or worse relative to the goal expression.</span></span> <span data-ttu-id="aa908-118">Puede asociar uno de los diversos gráficos con la expresión de tendencia para ayudar a los usuarios corporativos a comprender rápidamente la tendencia.</span><span class="sxs-lookup"><span data-stu-id="aa908-118">You can associate one of several graphics with the trend expression to help business users be able to quickly understand the trend.</span></span>

 <span data-ttu-id="aa908-119">Además de estos elementos definidos para un KPI, también deben definirse varias propiedades de un KPI.</span><span class="sxs-lookup"><span data-stu-id="aa908-119">In addition to these elements that you define for a KPI, you also define several properties of a KPI.</span></span> <span data-ttu-id="aa908-120">Estas propiedades incluyen una carpeta de muestra, un KPI primario si el KPI se calcula desde otros KPI, el miembro de hora actual si lo hay, el peso del KPI si lo tiene y una descripción del KPI.</span><span class="sxs-lookup"><span data-stu-id="aa908-120">These properties include a display folder, a parent KPI if the KPI is computed from other KPIs, the current time member if there is one, the weight of the KPI if it has one, and a description of the KPI.</span></span>

> [!NOTE]
>  <span data-ttu-id="aa908-121">Para obtener más ejemplos de KPI, consulte los ejemplos de KPI en la pestaña Plantillas del panel Herramientas de cálculo o en los ejemplos del almacenamiento de datos de ejemplo **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="aa908-121">For more examples of KPIs, see the KPI examples on the Templates tab in the Calculation Tools pane or in the examples in the **Adventure Works DW 2012** sample data warehouse.</span></span> <span data-ttu-id="aa908-122">Para obtener más información sobre cómo instalar esta base de datos, consulte [Instalar los datos y proyectos de ejemplo para el tutorial de modelado multidimensional de Analysis Services](install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="aa908-122">For more information about how to install this database, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](install-sample-data-and-projects.md).</span></span>

 <span data-ttu-id="aa908-123">En las tareas de esta lección definirá los KPI del proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y, a continuación, examinará el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] con estos KPI.</span><span class="sxs-lookup"><span data-stu-id="aa908-123">In the task in this lesson, you define  KPIs in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, and you then browse the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube by using these KPIs.</span></span> <span data-ttu-id="aa908-124">Definirá los siguientes KPI:</span><span class="sxs-lookup"><span data-stu-id="aa908-124">You will define the following KPIs:</span></span>

-   <span data-ttu-id="aa908-125">Reseller Revenue</span><span class="sxs-lookup"><span data-stu-id="aa908-125">Reseller Revenue</span></span>

     <span data-ttu-id="aa908-126">Este KPI se utiliza para medir la forma en que comparar las ventas reales del distribuidor con las cuotas de venta para ventas del distribuidor, la distancia que separa las ventas del el objetivo y qué tendencia se dirige al objetivo.</span><span class="sxs-lookup"><span data-stu-id="aa908-126">This KPI is used to measure how actual reseller sales compare to sales quotas for reseller sales, how close the sales are to the goal, and what the trend is toward reaching the goal.</span></span>

-   <span data-ttu-id="aa908-127">Product Gross Profit Margin</span><span class="sxs-lookup"><span data-stu-id="aa908-127">Product Gross Profit Margin</span></span>

     <span data-ttu-id="aa908-128">Este KPI se utiliza para determinar la distancia que existe entre el margen de beneficio bruto de cada categoría de producto y el objetivo especificado de cada categoría de producto, y también para determinar la tendencia hasta alcanzar este objetivo.</span><span class="sxs-lookup"><span data-stu-id="aa908-128">This KPI is used to determine how close the gross profit margin is for each product category to a specified goal for each product category, and also to determine the trend toward reaching this goal.</span></span>

## <a name="defining-the-reseller-revenue-kpi"></a><span data-ttu-id="aa908-129">Definir el KPI Reseller Revenue</span><span class="sxs-lookup"><span data-stu-id="aa908-129">Defining the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="aa908-130">Abra el Diseñador de cubos para el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y, después, haga clic en la pestaña **KPI** .</span><span class="sxs-lookup"><span data-stu-id="aa908-130">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **KPIs** tab.</span></span>

     <span data-ttu-id="aa908-131">La pestaña **KPI** incluye varios paneles.</span><span class="sxs-lookup"><span data-stu-id="aa908-131">The **KPIs** tab includes several panes.</span></span> <span data-ttu-id="aa908-132">En la parte izquierda de la pestaña están el panel **Organizador de KPI** y el panel **Herramientas de cálculo** .</span><span class="sxs-lookup"><span data-stu-id="aa908-132">On the left side of the tab are the **KPI Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="aa908-133">El panel de información del centro de la pestaña contiene los detalles del KPI seleccionado en el panel **Organizador de KPI** .</span><span class="sxs-lookup"><span data-stu-id="aa908-133">The display pane in the middle of the tab contains the details of the KPI that is selected in the **KPI Organizer** pane.</span></span>

     <span data-ttu-id="aa908-134">La siguiente imagen muestra la pestaña **KPI** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="aa908-134">The following image shows the **KPIs** tab of Cube Designer.</span></span>

     <span data-ttu-id="aa908-135">![Pestaña KPIs del Diseñador de cubos](../../2014/tutorials/media/l7-kpi-1.gif "Pestaña KPIs del Diseñador de cubos")</span><span class="sxs-lookup"><span data-stu-id="aa908-135">![KPIs tab of Cube Designer](../../2014/tutorials/media/l7-kpi-1.gif "KPIs tab of Cube Designer")</span></span>

2.  <span data-ttu-id="aa908-136">En la barra de herramientas de la pestaña **KPI** , haga clic en el botón **Nuevo KPI** .</span><span class="sxs-lookup"><span data-stu-id="aa908-136">On the toolbar of the **KPIs** tab, click the **New KPI** button.</span></span>

     <span data-ttu-id="aa908-137">En el panel de información aparecerá una plantilla de KPI en blanco, como en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="aa908-137">A blank KPI template appears in the display pane, as shown in the following image.</span></span>

     <span data-ttu-id="aa908-138">![Plantilla KPI en blanco en el panel de información](../../2014/tutorials/media/l7-kpi-2.gif "Plantilla KPI en blanco en el panel de información")</span><span class="sxs-lookup"><span data-stu-id="aa908-138">![Blank KPI template in display pane](../../2014/tutorials/media/l7-kpi-2.gif "Blank KPI template in display pane")</span></span>

3.  <span data-ttu-id="aa908-139">En el cuadro **nombre** , escriba `Reseller Revenue` y, a continuación, seleccione **reseller sales** en la lista **grupo de medida asociado** .</span><span class="sxs-lookup"><span data-stu-id="aa908-139">In the **Name** box, type `Reseller Revenue`, and then select **Reseller Sales** in the **Associated measure group** list.</span></span>

4.  <span data-ttu-id="aa908-140">En la pestaña **Metadatos** del panel **Herramientas de cálculo** , expanda **Medidas**, **Reseller Sales**y, después, arrastre la medida **Reseller Sales-Sales Amount** al cuadro **Expresión de valor** .</span><span class="sxs-lookup"><span data-stu-id="aa908-140">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Reseller Sales**, and then drag the **Reseller Sales-Sales Amount** measure to the **Value Expression** box.</span></span>

5.  <span data-ttu-id="aa908-141">En la pestaña **Metadatos** del panel **Herramientas de cálculo** , expanda **Medidas**, **Sales Quotas**y,después, arrastre la medida **Sales Amount Quota** al cuadro **Expresión objetivo** .</span><span class="sxs-lookup"><span data-stu-id="aa908-141">On the **Metadata** tab in the **Calculation Tools** pane, expand **Measures**, expand **Sales Quotas**, and then drag the **Sales Amount Quota** measure to the **Goal Expression** box.</span></span>

6.  <span data-ttu-id="aa908-142">Compruebe que está seleccionado **Indicador** en la lista **Indicador de estado** y, después, escriba la siguiente expresión MDX en el cuadro **Expresión de estado** :</span><span class="sxs-lookup"><span data-stu-id="aa908-142">Verify that **Gauge** is selected in the **Status indicator** list, and then type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
     When 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.95
       Then 1
     When
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")<.95
       And 
      KpiValue("Reseller Revenue")/KpiGoal("Reseller Revenue")>=.85
       Then 0
      Else-1
    End
    ```

     <span data-ttu-id="aa908-143">Esta expresión MDX proporciona lo básico para evaluar el progreso hacia el objetivo.</span><span class="sxs-lookup"><span data-stu-id="aa908-143">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span> <span data-ttu-id="aa908-144">En esta expresión MDX, si las ventas reales del distribuidor están por encima del 85 por ciento del objetivo, se utilizará un valor de 0 para llenar el gráfico seleccionado.</span><span class="sxs-lookup"><span data-stu-id="aa908-144">In this MDX expression, if actual reseller sales are more than 85 percent of the goal, a value of 0 is used to populate the chosen graphic.</span></span> <span data-ttu-id="aa908-145">Como el gráfico seleccionado es un indicador, el puntero del indicador estará a mitad de camino entre el estado vacío y el lleno.</span><span class="sxs-lookup"><span data-stu-id="aa908-145">Because a gauge is the chosen graphic, the pointer in the gauge will be half-way between empty and full.</span></span> <span data-ttu-id="aa908-146">Si las ventas reales por distribuidor están por encima del 90 por ciento, el puntero del indicador ocupará tres cuartas partes del espacio entre vacío y lleno.</span><span class="sxs-lookup"><span data-stu-id="aa908-146">If actual reseller sales are more the 90 percent, the pointer on the gauge will be three-fourths of the way between empty and full.</span></span>

7.  <span data-ttu-id="aa908-147">Compruebe que está seleccionado **Flecha estándar** en la lista **Indicador de tendencia** y, después, escriba la siguiente expresión en el cuadro **Expresión de tendencia** :</span><span class="sxs-lookup"><span data-stu-id="aa908-147">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following expression in the **Trend expression** box:</span></span>

    ```
    Case
     When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
     When  (
      KpiValue("Reseller Revenue") - 
       (KpiValue("Reseller Revenue"), 
        ParallelPeriod
         ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
          /
          (KpiValue ("Reseller Revenue"),
           ParallelPeriod
            ([Date].[Calendar Date].[Calendar Year],1,
             [Date].[Calendar Date].CurrentMember)))
           >=.02
      Then 1
       When(
        KpiValue("Reseller Revenue") - 
         (KpiValue ( "Reseller Revenue" ),
          ParallelPeriod
           ([Date].[Calendar Date].[Calendar Year],1,
            [Date].[Calendar Date].CurrentMember))
           /
            (KpiValue("Reseller Revenue"),
             ParallelPeriod
              ([Date].[Calendar Date].[Calendar Year],1,
                [Date].[Calendar Date].CurrentMember)))
            <=.02
      Then -1
       Else 0
    End
    ```

     <span data-ttu-id="aa908-148">Esta expresión MDX proporciona lo básico para evaluar la tendencia hasta lograr el objetivo definido.</span><span class="sxs-lookup"><span data-stu-id="aa908-148">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-reseller-revenue-kpi"></a><span data-ttu-id="aa908-149">Examinar el cubo mediante el KPI Reseller Revenue</span><span class="sxs-lookup"><span data-stu-id="aa908-149">Browsing the Cube by Using the Reseller Revenue KPI</span></span>

1.  <span data-ttu-id="aa908-150">En el menú **Generar** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], haga clic en **Implementar Tutorial de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="aa908-150">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="aa908-151">Cuando la implementación se haya completado correctamente, haga clic en el botón **Vista de explorador** de la barra de herramientas de la pestaña **KPI** y, después, haga clic en **Volver a conectar**.</span><span class="sxs-lookup"><span data-stu-id="aa908-151">When deployment has successfully completed, on the toolbar of the **KPIs** tab, click the **Browser View** button, and then click **Reconnect**.</span></span>

     <span data-ttu-id="aa908-152">Los indicadores de estado y de tendencia aparecen en el panel **Examinador de KPI** para ventas por distribuidor basadas en valores para el miembro predeterminado de cada dimensión, junto con el valor para el valor y el objetivo.</span><span class="sxs-lookup"><span data-stu-id="aa908-152">The status and trend gauges are displayed in the **KPI Browser** pane for reseller sales based on the values for the default member of each dimension, together with the value for the value and the goal.</span></span> <span data-ttu-id="aa908-153">El miembro predeterminado de cada dimensión es el miembro Todos del nivel Todos, porque no ha definido ningún otro miembro de ninguna otra dimensión como miembro predeterminado.</span><span class="sxs-lookup"><span data-stu-id="aa908-153">The default member of each dimension is the All member of the All level, because you have not defined any other member of any dimension as the default member.</span></span>

3.  <span data-ttu-id="aa908-154">En el panel de filtros, seleccione **Sales Territory** en la lista **Dimensión** , seleccione **Sales Territories** en la lista **Jerarquía** , seleccione **Igual** en la lista **Operador** , active la casilla **Norteamérica** en la lista **Expresión de filtro** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa908-154">In the filter pane, select **Sales Territory** in the **Dimension** list, select **Sales Territories** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **North America** check box in the **Filter Expression** list, and then click **OK**.</span></span>

4.  <span data-ttu-id="aa908-155">En la fila siguiente del panel **Filtro** , seleccione **Date** en la lista **Dimensión** , seleccione **Calendar Date** en la lista **Jerarquía** , seleccione **Igual** en la lista **Operador** , active la casilla **Q3 CY 2007** en la lista **Expresión de filtro** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa908-155">In the next row in the **Filter** pane, select **Date** in the **Dimension** list, select **Calendar Date** in the **Hierarchy** list, select **Equal** in the **Operator** list, select the **Q3 CY 2007** check box in the **Filter Expression** list, and then click **OK**.</span></span>

5.  <span data-ttu-id="aa908-156">Haga clic en cualquier sitio del panel **Explorador de KPI** para actualizar los valores para el KPI **Reseller Revenue KPI**.</span><span class="sxs-lookup"><span data-stu-id="aa908-156">Click anywhere in the **KPI Browser** pane to update the values for the **Reseller Revenue KPI**.</span></span>

     <span data-ttu-id="aa908-157">Observe que las secciones **Valor**, **Objetivo**y **Estado** del KPI reflejan los valores para el nuevo período de tiempo</span><span class="sxs-lookup"><span data-stu-id="aa908-157">Notice that the **Value**, **Goal**, and **Status** sections of the KPI reflect the values for the new time period</span></span>

## <a name="defining-the-product-gross-profit-margin-kpi"></a><span data-ttu-id="aa908-158">Definir el KPI Product Gross Profit Margin</span><span class="sxs-lookup"><span data-stu-id="aa908-158">Defining the Product Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="aa908-159">Haga clic en el botón **Vista de formulario** de la barra de herramientas de la pestaña **KPI** y, después, haga clic en el botón **Nuevo KPI** .</span><span class="sxs-lookup"><span data-stu-id="aa908-159">Click the **Form View** button on the toolbar of the **KPIs** tab, and then click the **New KPI** button.</span></span>

2.  <span data-ttu-id="aa908-160">En el cuadro **nombre** , escriba `Product Gross Profit Margin` y, a continuación, compruebe que **\<All>** aparece en la lista **grupo de medida asociado** .</span><span class="sxs-lookup"><span data-stu-id="aa908-160">In the **Name** box, type `Product Gross Profit Margin`, and then verify that **\<All>** appears in the **Associated measure group** list.</span></span>

3.  <span data-ttu-id="aa908-161">En la pestaña **Metadatos** del panel **Herramientas de cálculo** , arrastre la medida **Total GPM** al cuadro **Expresión de valor** .</span><span class="sxs-lookup"><span data-stu-id="aa908-161">In the **Metadata** tab in the **Calculation Tools** pane, drag the **Total GPM** measure to the **Value Expression** box.</span></span>

4.  <span data-ttu-id="aa908-162">En el cuadro **Expresión objetivo** , escriba la expresión siguiente:</span><span class="sxs-lookup"><span data-stu-id="aa908-162">In the **Goal Expression** box, type the following expression:</span></span>

    ```
    Case
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Accessories]
        Then .40                 
        When [Product].[Category].CurrentMember 
          Is [Product].[Category].[Bikes]
        Then .12                
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Clothing]
        Then .20
        When [Product].[Category].CurrentMember Is
          [Product].[Category].[Components]
        Then .10
        Else .12            
    End
    ```

5.  <span data-ttu-id="aa908-163">En la lista **Indicador de estado** , seleccione **Cilindro**.</span><span class="sxs-lookup"><span data-stu-id="aa908-163">In the **Status indicator** list, select **Cylinder**.</span></span>

6.  <span data-ttu-id="aa908-164">Escriba la siguiente expresión MDX en el cuadro **Expresión de estado** :</span><span class="sxs-lookup"><span data-stu-id="aa908-164">Type the following MDX expression in the **Status expression** box:</span></span>

    ```
    Case
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .90
        Then 1
        When KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) <  .90
             And 
             KpiValue( "Product Gross Profit Margin" ) / 
             KpiGoal ( "Product Gross Profit Margin" ) >= .80
        Then 0
        Else -1
    End
    ```

     <span data-ttu-id="aa908-165">Esta expresión MDX proporciona lo básico para evaluar el progreso hacia el objetivo.</span><span class="sxs-lookup"><span data-stu-id="aa908-165">This MDX expression provides the basis for evaluating the progress toward the goal.</span></span>

7.  <span data-ttu-id="aa908-166">Compruebe que está seleccionado **Flecha estándar** en la lista **Indicador de tendencia** y, después, escriba la siguiente expresión MDX en el cuadro **Expresión de tendencia** :</span><span class="sxs-lookup"><span data-stu-id="aa908-166">Verify that **Standard arrow** is selected in the **Trend indicator** list, and then type the following MDX expression in the **Trend expression** box:</span></span>

    ```
    Case
    When IsEmpty
      (ParallelPeriod
       ([Date].[Calendar Date].[Calendar Year],1,
           [Date].[Calendar Date].CurrentMember))
      Then 0  
       When VBA!Abs
        (
          KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            ) /
            (
              KpiValue ( "Product Gross Profit Margin" ),
              ParallelPeriod
              ( 
                [Date].[ Calendar Date].[ Calendar Year],
                1,
                [Date].[ Calendar Date].CurrentMember
              )
            )  
          ) <=.02
      Then 0
      When KpiValue( "Product Gross Profit Margin" ) - 
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[ Calendar Date].[ Calendar Year],
               1,
               [Date].[ Calendar Date].CurrentMember
             )
           ) /
           (
             KpiValue ( "Product Gross Profit Margin" ),
             ParallelPeriod
             ( 
               [Date].[Calendar Date].[Calendar Year],
               1,
               [Date].[Calendar Date].CurrentMember
             )
           )  >.02
      Then 1
      Else -1
    End
    ```

     <span data-ttu-id="aa908-167">Esta expresión MDX proporciona lo básico para evaluar la tendencia hasta lograr el objetivo definido.</span><span class="sxs-lookup"><span data-stu-id="aa908-167">This MDX expression provides the basis for evaluating the trend toward achieving the defined goal.</span></span>

## <a name="browsing-the-cube-by-using-the-total-gross-profit-margin-kpi"></a><span data-ttu-id="aa908-168">Examinar el cubo mediante el KPI Total Gross Profit Margin</span><span class="sxs-lookup"><span data-stu-id="aa908-168">Browsing the Cube by Using the Total Gross Profit Margin KPI</span></span>

1.  <span data-ttu-id="aa908-169">En el menú **Generar** , haga clic en **Implementar Tutorial de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="aa908-169">On the **Build** menu, click **Deploy Analysis Service Tutorial**.</span></span>

2.  <span data-ttu-id="aa908-170">Cuando la implementación se haya completado correctamente, haga clic en **Volver a conectar** en la barra de herramientas de la pestaña **KPI** y, después, haga clic en **Vista de explorador**.</span><span class="sxs-lookup"><span data-stu-id="aa908-170">When deployment has successfully completed, click **Reconnect** on the toolbar of the **KPIs** tab, and then click **Browser View**.</span></span>

     <span data-ttu-id="aa908-171">`Product Gross Profit Margin`Aparece el KPI y muestra el valor de KPI del **tercer trimestre 2007** y el **Norteamérica** territorio de ventas.</span><span class="sxs-lookup"><span data-stu-id="aa908-171">The `Product Gross Profit Margin` KPI appears and displays the KPI value for **Q3 CY 2007** and the **North America** sales territory.</span></span>

3.  <span data-ttu-id="aa908-172">En el panel **Filtro** , seleccione **Product** en la lista **Dimensión** , seleccione **Category** en la lista **Jerarquía** , seleccione **Igual** en la lista **Operador** y **Bikes** en la lista **Expresión de filtro** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa908-172">In the **Filter** pane, select **Product** in the **Dimension** list, select **Category** in the **Hierarchy** list, select **Equal** in the **Operator** list, and then select **Bikes** in the **Filter Expression** list, and then click **OK**.</span></span>

     <span data-ttu-id="aa908-173">Aparecerá el margen de beneficio bruto para la venta de bicicletas por distribuidor en Norteamérica en el tercer trimestre de 2007.</span><span class="sxs-lookup"><span data-stu-id="aa908-173">The gross profit margin for the sale of Bikes by resellers in North America in Q3 CY 2007 appears.</span></span>

## <a name="next-lesson"></a><span data-ttu-id="aa908-174">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="aa908-174">Next Lesson</span></span>
 [<span data-ttu-id="aa908-175">Lección 8: definir acciones</span><span class="sxs-lookup"><span data-stu-id="aa908-175">Lesson 8: Defining Actions</span></span>](lesson-8-defining-actions.md)


