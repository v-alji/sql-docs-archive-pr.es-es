---
title: Definir miembros calculados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 07f13e1c-0b20-4f9e-ad62-c438983f2785
author: minewiskan
ms.author: owend
ms.openlocfilehash: f2a054356613ebf3d4cf825c1fa4c238a5362ec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671780"
---
# <a name="defining-calculated-members"></a><span data-ttu-id="3c533-102">Definir miembros calculados</span><span class="sxs-lookup"><span data-stu-id="3c533-102">Defining Calculated Members</span></span>
  <span data-ttu-id="3c533-103">Los miembros calculados son miembros de una dimensión o un grupo de medida que se definen según una combinación de datos del cubo, operadores aritméticos, números y funciones.</span><span class="sxs-lookup"><span data-stu-id="3c533-103">Calculated members are members of a dimension or a measure group that are defined based on a combination of cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="3c533-104">Por ejemplo, puede crear un miembro calculado que calcule la suma de dos medidas físicas en el cubo.</span><span class="sxs-lookup"><span data-stu-id="3c533-104">For example, you can create a calculated member that calculates the sum of two physical measures in the cube.</span></span> <span data-ttu-id="3c533-105">Las definiciones de miembros calculados se almacenan en cubos pero sus valores se calculan en el momento de la consulta.</span><span class="sxs-lookup"><span data-stu-id="3c533-105">Calculated member definitions are stored in cubes, but their values are calculated at query time.</span></span>  
  
 <span data-ttu-id="3c533-106">Para crear un miembro calculado, utilice el comando **Nuevo miembro calculado** en la pestaña **Cálculos** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="3c533-106">To create a calculated member, use the **New Calculated Member** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="3c533-107">Puede crear un miembro calculado dentro de cualquier dimensión, incluida la dimensión de medidas.</span><span class="sxs-lookup"><span data-stu-id="3c533-107">You can create a calculated member within any dimension, including the measures dimension.</span></span> <span data-ttu-id="3c533-108">También puede colocar un miembro calculado en una carpeta para mostrar en el cuadro de diálogo **Propiedades de cálculo** .</span><span class="sxs-lookup"><span data-stu-id="3c533-108">You can also place a calculated member within a display folder in the **Calculation Properties** dialog box.</span></span> <span data-ttu-id="3c533-109">Para obtener más información, vea [Cálculos](multidimensional-models-olap-logical-cube-objects/calculations.md), [Cálculos en modelos multidimensionales](multidimensional-models/calculations-in-multidimensional-models.md)y [Crear miembros calculados](multidimensional-models/create-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="3c533-109">For more information, see [Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md), [Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md), and [Create Calculated Members](multidimensional-models/create-calculated-members.md).</span></span>  
  
 <span data-ttu-id="3c533-110">En las tareas de este tema se definen medidas calculadas para permitir que los usuarios vean el porcentaje de margen de beneficio bruto y el ratio de ventas para ventas por Internet, para ventas del distribuidor y para todas las ventas.</span><span class="sxs-lookup"><span data-stu-id="3c533-110">In the tasks in this topic, you define calculated measures to let users view the gross profit margin percentage and sales ratios for Internet sales, reseller sales, and for all sales.</span></span>  
  
## <a name="defining-calculations-to-aggregate-physical-measures"></a><span data-ttu-id="3c533-111">Definir cálculos para agregar medidas físicas</span><span class="sxs-lookup"><span data-stu-id="3c533-111">Defining Calculations to Aggregate Physical Measures</span></span>  
  
1.  <span data-ttu-id="3c533-112">Abra el Diseñador de cubos para el cubo [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial y, a continuación, haga clic en la pestaña **Cálculos** .</span><span class="sxs-lookup"><span data-stu-id="3c533-112">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="3c533-113">Observe el comando predeterminado CALCULATE en el panel de las **expresiones de cálculo** y en el panel **Organizador de script** .</span><span class="sxs-lookup"><span data-stu-id="3c533-113">Notice the default CALCULATE command in the **Calculation Expressions** pane and in the **Script Organizer** pane.</span></span> <span data-ttu-id="3c533-114">Este comando especifica que las medidas del cubo deberían agregarse según el valor especificado por sus propiedades AggregateFunction.</span><span class="sxs-lookup"><span data-stu-id="3c533-114">This command specifies that the measures in the cube should be aggregated according to the value that is specified by their AggregateFunction properties.</span></span> <span data-ttu-id="3c533-115">Los valores de medida normalmente se suman, pero también pueden contarse o agregarse de otra forma.</span><span class="sxs-lookup"><span data-stu-id="3c533-115">Measure values are generally summed, but may also be counted or aggregated in some other manner.</span></span>  
  
     <span data-ttu-id="3c533-116">La siguiente imagen muestra la pestaña **Cálculos** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="3c533-116">The following image shows the **Calculations** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="3c533-117">![Pestaña Cálculos del Diseñador de cubos](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Pestaña Cálculos del Diseñador de cubos")</span><span class="sxs-lookup"><span data-stu-id="3c533-117">![Calculations tab of Cube Designer](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Calculations tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="3c533-118">En la barra de herramientas de la pestaña **Cálculos** , haga clic en **Nuevo miembro calculado**.</span><span class="sxs-lookup"><span data-stu-id="3c533-118">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="3c533-119">En el panel de las **expresiones de cálculo** aparece un nuevo formulario en el que podrá definir las propiedades de este nuevo miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="3c533-119">A new form appears in the **Calculation Expressions** pane within which you define the properties of this new calculated member.</span></span> <span data-ttu-id="3c533-120">El nuevo miembro aparecerá también en el panel **Organizador de script** .</span><span class="sxs-lookup"><span data-stu-id="3c533-120">The new member also appears in the **Script Organizer** pane.</span></span>  
  
     <span data-ttu-id="3c533-121">La siguiente imagen muestra el formulario que aparece en el panel de las **expresiones de cálculo** al hacer clic en **Nuevo miembro calculado**.</span><span class="sxs-lookup"><span data-stu-id="3c533-121">The following image shows the form that appears in the **Calculation Expressions** pane when you click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="3c533-122">![Formulario del panel de expresiones de cálculo](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Formulario del panel de expresiones de cálculo")</span><span class="sxs-lookup"><span data-stu-id="3c533-122">![Calculation Expressions pane form](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Calculation Expressions pane form")</span></span>  
  
3.  <span data-ttu-id="3c533-123">En el cuadro **nombre** , cambie el nombre de la medida calculada a `[Total Sales Amount]` .</span><span class="sxs-lookup"><span data-stu-id="3c533-123">In the **Name** box, change the name of the calculated measure to `[Total Sales Amount]`.</span></span>  
  
     <span data-ttu-id="3c533-124">Si el nombre de un miembro calculado contiene un espacio, dicho nombre deberá ir entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="3c533-124">If the name of a calculated member contains a space, the calculated member name must be enclosed in square brackets.</span></span>  
  
     <span data-ttu-id="3c533-125">Observe que en la lista **Jerarquía primaria** , de manera predeterminada, se crea un nuevo miembro calculado en la dimensión **Measures** .</span><span class="sxs-lookup"><span data-stu-id="3c533-125">Notice in the **Parent hierarchy** list that, by default, a new calculated member is created in the **Measures** dimension.</span></span> <span data-ttu-id="3c533-126">A un miembro calculado de la dimensión Measures también se le denomina con frecuencia medida calculada.</span><span class="sxs-lookup"><span data-stu-id="3c533-126">A calculated member in the Measures dimension is also frequently called a calculated measure.</span></span>  
  
4.  <span data-ttu-id="3c533-127">En la pestaña **Metadatos** del panel **Herramientas de cálculo** de la pestaña **Cálculos** , expanda **Medidas** y, a continuación, **Ventas por Internet** para ver los metadatos del grupo de medida **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="3c533-127">On the **Metadata** tab in the **Calculation Tools** pane of the **Calculations** tab, expand **Measures** and then expand **Internet Sales** to view the metadata for the **Internet Sales** measure group.</span></span>  
  
     <span data-ttu-id="3c533-128">Puede arrastrar los elementos de metadatos desde el panel **Herramientas de cálculo** al cuadro **Expresión** y agregar entonces operadores y otros elementos para crear expresiones de Expresiones multidimensionales (MDX).</span><span class="sxs-lookup"><span data-stu-id="3c533-128">You can drag metadata elements from the **Calculation Tools** pane into the **Expression** box and then add operators and other elements to create Multidimensional Expressions (MDX) expressions.</span></span> <span data-ttu-id="3c533-129">O bien, puede escribir la expresión MDX directamente en el cuadro **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="3c533-129">Alternatively, you can type the MDX expression directly into the **Expression** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3c533-130">Si no puede ver los metadatos en el panel **Herramientas de cálculo** , haga clic en **Volver a conectar** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="3c533-130">If you cannot view any metadata in the **Calculation Tools** pane, click **Reconnect** on the toolbar.</span></span> <span data-ttu-id="3c533-131">Si esto no funciona, puede que tenga que procesar el cubo o iniciar la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c533-131">If this does not work, you may have to process the cube or start the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="3c533-132">Arrastre **Internet Sales-Sales Amount** de la pestaña **Metadatos** del panel **Herramientas de cálculo** al cuadro **Expresión** del panel de las **expresiones de cálculo** .</span><span class="sxs-lookup"><span data-stu-id="3c533-132">Drag **Internet Sales-Sales Amount** from the **Metadata** tab in the **Calculation Tools** pane into the **Expression** box in the **Calculation Expressions** pane.</span></span>  
  
6.  <span data-ttu-id="3c533-133">En el cuadro **Expresión** , escriba un signo más (`+`) después de **[Measures].[Internet Sales-Sales Amount]**.</span><span class="sxs-lookup"><span data-stu-id="3c533-133">In the **Expression** box, type a plus sign (`+`) after **[Measures].[Internet Sales-Sales Amount]**.</span></span>  
  
7.  <span data-ttu-id="3c533-134">En la pestaña **Metadatos** del panel **Herramientas de cálculo** , expanda **Venta del distribuidor**y, después, arrastre **Reseller Sales-Sales Amount** al cuadro **Expresión** del panel de las **expresiones de cálculo** después del signo más (+).</span><span class="sxs-lookup"><span data-stu-id="3c533-134">On the **Metadata** tab in the **Calculation Tools** pane, expand **Reseller Sales**, and then drag **Reseller Sales-Sales Amount** into the **Expression** box in the **Calculation Expressions** pane after the plus sign (+).</span></span>  
  
8.  <span data-ttu-id="3c533-135">En la lista **cadena de formato** , seleccione **"moneda".**</span><span class="sxs-lookup"><span data-stu-id="3c533-135">In the **Format string** list, select **"Currency".**</span></span>  
  
9. <span data-ttu-id="3c533-136">En la lista **Comportamiento si no está vacío** , active las casillas **Internet Sales-Sales Amount** y **Reseller Sales-Sales Amount**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c533-136">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="3c533-137">Las medidas especificadas en la lista **Comportamiento si no está vacío** se usan para resolver consultas NON EMPTY en MDX.</span><span class="sxs-lookup"><span data-stu-id="3c533-137">The measures you specify in the **Non-empty behavior** list are used to resolve NON EMPTY queries in MDX.</span></span> <span data-ttu-id="3c533-138">Si se especifican una o más medidas en la lista **Comportamiento si no está vacío** , [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] tratará al miembro calculado como vacío si todas las medidas especificadas están vacías.</span><span class="sxs-lookup"><span data-stu-id="3c533-138">When you specify one or more measures in the **Non-empty behavior** list, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] treats the calculated member as empty if all the specified measures are empty.</span></span> <span data-ttu-id="3c533-139">Si la propiedad **Non-empty behavior** está en blanco, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] deberá evaluar al miembro calculado para determinar si el miembro está vacío.</span><span class="sxs-lookup"><span data-stu-id="3c533-139">If the **Non-empty behavior** property is blank, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] must evaluate the calculated member itself to determine whether the member is empty.</span></span>  
  
     <span data-ttu-id="3c533-140">La siguiente imagen muestra el panel de las **expresiones de cálculo** llenado con la configuración especificada en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="3c533-140">The following image shows the **Calculation Expressions** pane populated with the settings that you specified in the previous steps.</span></span>  
  
     <span data-ttu-id="3c533-141">![Panel de expresiones de cálculo rellenado](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Panel de expresiones de cálculo rellenado")</span><span class="sxs-lookup"><span data-stu-id="3c533-141">![Populated Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Populated Calculation Expressions pane")</span></span>  
  
10. <span data-ttu-id="3c533-142">En la barra de herramientas de la pestaña **Cálculos** , haga clic en **Vista de script**y revise el script de cálculo en el panel de las **expresiones de cálculo** .</span><span class="sxs-lookup"><span data-stu-id="3c533-142">On the toolbar of the **Calculations** tab, click **Script View**, and then review the calculation script in the **Calculation Expressions** pane.</span></span>  
  
     <span data-ttu-id="3c533-143">Observe que el nuevo cálculo se agrega a la expresión CALCULATE inicial; los cálculos individuales se separan con un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="3c533-143">Notice that the new calculation is added to the initial CALCULATE expression; each individual calculation is separated by a semicolon.</span></span> <span data-ttu-id="3c533-144">Observe también que aparece un comentario al principio del script del cálculo.</span><span class="sxs-lookup"><span data-stu-id="3c533-144">Notice also that a comment appears at the beginning of the calculation script.</span></span> <span data-ttu-id="3c533-145">Se recomienda la agregación de comentarios dentro del script de cálculo para grupos de cálculos para ayudarle a usted y a otros programadores a comprender los scripts de cálculo complejos.</span><span class="sxs-lookup"><span data-stu-id="3c533-145">Adding comments within the calculation script for groups of calculations is a good practice, to help you and other developers understand complex calculation scripts.</span></span>  
  
11. <span data-ttu-id="3c533-146">Agregue una nueva línea al script de cálculo después del comando **Calculate;** y antes del script de cálculo recientemente agregada y, a continuación, agregue el siguiente texto al script en su propia línea:</span><span class="sxs-lookup"><span data-stu-id="3c533-146">Add a new line in the calculation script after the **Calculate;** command and before the newly added calculation script, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to aggregate Internet Sales and Reseller Sales measures */  
    ```  
  
     <span data-ttu-id="3c533-147">La siguiente imagen muestra los scripts de cálculo tal como deberían aparecer en el panel de las **expresiones de cálculo** en este punto del tutorial.</span><span class="sxs-lookup"><span data-stu-id="3c533-147">The following image shows the calculation scripts as they should appear in the **Calculation Expressions** pane at this point in the tutorial.</span></span>  
  
     <span data-ttu-id="3c533-148">![Scripts en el panel de expresiones de cálculo](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Scripts en el panel de expresiones de cálculo")</span><span class="sxs-lookup"><span data-stu-id="3c533-148">![Scripts in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Scripts in Calculation Expressions pane")</span></span>  
  
12. <span data-ttu-id="3c533-149">En la barra de herramientas de la pestaña **cálculos** , haga clic en **vista de formulario**, compruebe que `[Total Sales Amount]` está seleccionado en el panel **organizador de script** y, a continuación, haga clic en **nuevo miembro calculado**.</span><span class="sxs-lookup"><span data-stu-id="3c533-149">On the toolbar of the **Calculations** tab, click **Form View**, verify that `[Total Sales Amount]` is selected in the **Script Organizer** pane, and then click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="3c533-150">Cambie el nombre de este nuevo miembro calculado a `[Total Product Cost]` y, a continuación, cree la siguiente expresión en el cuadro **expresión** :</span><span class="sxs-lookup"><span data-stu-id="3c533-150">Change the name of this new calculated member to `[Total Product Cost]`, and then create the following expression in the **Expression** box:</span></span>  
  
    ```  
    [Measures].[Internet Sales-Total Product Cost] + [Measures].[Reseller Sales-Total Product Cost]  
    ```  
  
14. <span data-ttu-id="3c533-151">En la lista **Cadena de formato** , seleccione **"Moneda"**.</span><span class="sxs-lookup"><span data-stu-id="3c533-151">In the **Format string** list, select **"Currency"**.</span></span>  
  
15. <span data-ttu-id="3c533-152">En la lista **Comportamiento si no está vacío** , active las casillas **Internet Sales-Total Product Cost** y **Reseller Sales-Total Product Cost**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c533-152">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Total Product Cost** and **Reseller Sales-Total Product Cost**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="3c533-153">Ahora ha definido dos miembros calculados y ambos son visibles en el panel **Organizador de script** .</span><span class="sxs-lookup"><span data-stu-id="3c533-153">You have now defined two calculated members, both of which are visible in the **Script Organizer** pane.</span></span> <span data-ttu-id="3c533-154">Estos miembros calculados pueden ser utilizados por otros cálculos definidos posteriormente en el script de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3c533-154">These calculated members can be used by other calculations that you define later in the calculation script.</span></span> <span data-ttu-id="3c533-155">Puede ver la definición de cualquier miembro calculado seleccionando el miembro calculado en el panel **Organizador de script** ; la definición del miembro calculado aparecerá en el panel de las **expresiones de cálculo** de la vista Formulario.</span><span class="sxs-lookup"><span data-stu-id="3c533-155">You can view the definition of any calculated member by selecting the calculated member in the **Script Organizer** pane; the definition of the calculated member will appear in the **Calculation Expressions** pane in the Form view.</span></span> <span data-ttu-id="3c533-156">Los miembros calculados recientemente definidos no aparecerán en el panel **Herramientas de cálculo** hasta que se hayan implementado estos objetos.</span><span class="sxs-lookup"><span data-stu-id="3c533-156">Newly defined calculated members will not appear in the **Calculation Tools** pane until these objects have been deployed.</span></span> <span data-ttu-id="3c533-157">Los cálculos no requieren procesamiento.</span><span class="sxs-lookup"><span data-stu-id="3c533-157">Calculations do not require processing.</span></span>  
  
## <a name="defining-gross-profit-margin-calculations"></a><span data-ttu-id="3c533-158">Definir cálculos de margen de beneficio bruto</span><span class="sxs-lookup"><span data-stu-id="3c533-158">Defining Gross Profit Margin Calculations</span></span>  
  
1.  <span data-ttu-id="3c533-159">Compruebe que `[Total Product Cost]` está seleccionado en el panel **organizador de script** y, a continuación, haga clic en **nuevo miembro calculado** en la barra de herramientas de la pestaña **cálculos** .</span><span class="sxs-lookup"><span data-stu-id="3c533-159">Verify that `[Total Product Cost]` is selected in the **Script Organizer** pane, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
2.  <span data-ttu-id="3c533-160">En el cuadro **nombre** , cambie el nombre de esta nueva medida calculada a `[Internet GPM]` .</span><span class="sxs-lookup"><span data-stu-id="3c533-160">In the **Name** box, change the name of this new calculated measure to `[Internet GPM]`.</span></span>  
  
3.  <span data-ttu-id="3c533-161">En el cuadro **Expresión** , cree la siguiente expresión MDX:</span><span class="sxs-lookup"><span data-stu-id="3c533-161">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Internet Sales-Sales Amount] -   
    [Measures].[Internet Sales-Total Product Cost]) /  
    [Measures].[Internet Sales-Sales Amount]  
    ```  
  
4.  <span data-ttu-id="3c533-162">En la lista **Cadena de formato** , seleccione **"Porcentaje"**.</span><span class="sxs-lookup"><span data-stu-id="3c533-162">In the **Format string** list, select **"Percent"**.</span></span>  
  
5.  <span data-ttu-id="3c533-163">En la lista **Comportamiento si no está vacío** , active la casilla **Internet Sales-Sales Amount**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c533-163">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="3c533-164">En la barra de herramientas de la pestaña **Cálculos** , haga clic en **Nuevo miembro calculado**.</span><span class="sxs-lookup"><span data-stu-id="3c533-164">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
7.  <span data-ttu-id="3c533-165">En el cuadro **nombre** , cambie el nombre de esta nueva medida calculada a `[Reseller GPM]` .</span><span class="sxs-lookup"><span data-stu-id="3c533-165">In the **Name** box, change the name of this new calculated measure to `[Reseller GPM]`.</span></span>  
  
8.  <span data-ttu-id="3c533-166">En el cuadro **Expresión** , cree la siguiente expresión MDX:</span><span class="sxs-lookup"><span data-stu-id="3c533-166">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Reseller Sales-Sales Amount] -   
    [Measures].[Reseller Sales-Total Product Cost]) /  
    [Measures].[Reseller Sales-Sales Amount]  
    ```  
  
9. <span data-ttu-id="3c533-167">En la lista **Cadena de formato** , seleccione **"Porcentaje"**.</span><span class="sxs-lookup"><span data-stu-id="3c533-167">In the **Format string** list, select **"Percent"**.</span></span>  
  
10. <span data-ttu-id="3c533-168">En la lista **Comportamiento si no está vacío** , active la casilla **Reseller Sales-Sales Amount**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c533-168">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="3c533-169">En la barra de herramientas de la pestaña **Cálculos** , haga clic en **Nuevo miembro calculado**.</span><span class="sxs-lookup"><span data-stu-id="3c533-169">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
12. <span data-ttu-id="3c533-170">En el cuadro **nombre** , cambie el nombre de esta medida calculada a `[Total GPM]` .</span><span class="sxs-lookup"><span data-stu-id="3c533-170">In the **Name** box, change the name of this calculated measure to `[Total GPM]`.</span></span>  
  
13. <span data-ttu-id="3c533-171">En el cuadro **Expresión** , cree la siguiente expresión MDX:</span><span class="sxs-lookup"><span data-stu-id="3c533-171">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Total Sales Amount] -   
    [Measures].[Total Product Cost]) /  
    [Measures].[Total Sales Amount]  
    ```  
  
     <span data-ttu-id="3c533-172">Observe que este miembro calculado hace referencia a otros miembros calculados.</span><span class="sxs-lookup"><span data-stu-id="3c533-172">Notice that this calculated member is referencing other calculated members.</span></span> <span data-ttu-id="3c533-173">Como este miembro calculado se calculará después de los miembros calculados a los que hace referencia, se tratará de un miembro calculado válido.</span><span class="sxs-lookup"><span data-stu-id="3c533-173">Because this calculated member will be calculated after the calculated members that it references, this is a valid calculated member.</span></span>  
  
14. <span data-ttu-id="3c533-174">En la lista **Cadena de formato** , seleccione **"Porcentaje"**.</span><span class="sxs-lookup"><span data-stu-id="3c533-174">In the **Format string** list, select **"Percent"**.</span></span>  
  
15. <span data-ttu-id="3c533-175">En la lista **Comportamiento si no está vacío** , active las casillas **Internet Sales-Sales Amount** y **Reseller Sales-Sales Amount**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c533-175">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="3c533-176">En la barra de herramientas de la pestaña **Cálculos** , haga clic en **Vista de script** y revise los tres cálculos que acaba de agregar al script de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3c533-176">On the toolbar of the **Calculations** tab, click **Script View** and review the three calculations you just added to the calculation script.</span></span>  
  
17. <span data-ttu-id="3c533-177">Agregue una nueva línea al script de cálculo inmediatamente anterior al `[Internet GPM]` cálculo y, a continuación, agregue el siguiente texto al script en su propia línea:</span><span class="sxs-lookup"><span data-stu-id="3c533-177">Add a new line in the calculation script immediately before the `[Internet GPM]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate gross profit margin */  
    ```  
  
     <span data-ttu-id="3c533-178">La siguiente imagen muestra el panel **Expresiones** con los tres cálculos nuevos.</span><span class="sxs-lookup"><span data-stu-id="3c533-178">The following image shows the **Expressions** pane with the three new calculations.</span></span>  
  
     <span data-ttu-id="3c533-179">![Nuevos cálculos en el panel de expresiones de cálculo](../../2014/tutorials/media/l6-calculatedmembers-05.gif "Nuevos cálculos en el panel de expresiones de cálculo")</span><span class="sxs-lookup"><span data-stu-id="3c533-179">![New calculations in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-05.gif "New calculations in Calculation Expressions pane")</span></span>  
  
## <a name="defining-the-percent-of-total-calculations"></a><span data-ttu-id="3c533-180">Definir el porcentaje de los cálculos totales</span><span class="sxs-lookup"><span data-stu-id="3c533-180">Defining the Percent of Total Calculations</span></span>  
  
1.  <span data-ttu-id="3c533-181">En la barra de herramientas de la pestaña **Cálculos** , haga clic en **Vista de formulario**.</span><span class="sxs-lookup"><span data-stu-id="3c533-181">On the toolbar of the **Calculations** tab, click **Form View**.</span></span>  
  
2.  <span data-ttu-id="3c533-182">En el panel **organizador de script** , seleccione `[Total GPM]` y, a continuación, haga clic en **nuevo miembro calculado** en la barra de herramientas de la pestaña **cálculos** .</span><span class="sxs-lookup"><span data-stu-id="3c533-182">In the **Script Organizer** pane, select `[Total GPM]`, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="3c533-183">Si hace clic en el miembro calculado final del panel **Organizador de script** antes de hacer clic en **Nuevo miembro calculado** se asegurará de que el nuevo miembro calculado se escribe al final del script.</span><span class="sxs-lookup"><span data-stu-id="3c533-183">Clicking the final calculated member in the **Script Organizer** pane before you click **New Calculated Member** guarantees that the new calculated member will be entered at the end of the script.</span></span> <span data-ttu-id="3c533-184">Los scripts se ejecutan en el orden en el que aparecen en el panel **Organizador de script** .</span><span class="sxs-lookup"><span data-stu-id="3c533-184">Scripts execute in the order that they appear in the **Script Organizer** pane.</span></span>  
  
3.  <span data-ttu-id="3c533-185">Cambie el nombre de este nuevo miembro calculado a `[Internet Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="3c533-185">Change the name of this new calculated member to `[Internet Sales Ratio to All Products]`.</span></span>  
  
4.  <span data-ttu-id="3c533-186">Escriba la siguiente expresión en el cuadro **Expresión** :</span><span class="sxs-lookup"><span data-stu-id="3c533-186">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Internet Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Internet Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Internet Sales-Sales Amount] )  
        End  
    ```  
  
     <span data-ttu-id="3c533-187">Esta expresión MDX calcula la contribución al total de ventas por Internet de cada producto.</span><span class="sxs-lookup"><span data-stu-id="3c533-187">This MDX expression calculates the contribution to total Internet sales of each product.</span></span> <span data-ttu-id="3c533-188">La instrucción Case junto con la función IS EMPTY garantiza que no se produzca un error de división por cero cuando un producto no tiene ventas.</span><span class="sxs-lookup"><span data-stu-id="3c533-188">The Case statement together with the IS EMPTY function ensures that a divide by zero error does not occur when a product has no sales.</span></span>  
  
5.  <span data-ttu-id="3c533-189">En la lista **Cadena de formato** , seleccione **"Porcentaje"**.</span><span class="sxs-lookup"><span data-stu-id="3c533-189">In the **Format string** list, select **"Percent"**.</span></span>  
  
6.  <span data-ttu-id="3c533-190">En la lista **Comportamiento si no está vacío** , active la casilla **Internet Sales-Sales Amount**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c533-190">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="3c533-191">En la barra de herramientas de la pestaña **Cálculos** , haga clic en **Nuevo miembro calculado**.</span><span class="sxs-lookup"><span data-stu-id="3c533-191">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
8.  <span data-ttu-id="3c533-192">Cambie el nombre de este miembro calculado a `[Reseller Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="3c533-192">Change the name of this calculated member to `[Reseller Sales Ratio to All Products]`.</span></span>  
  
9. <span data-ttu-id="3c533-193">Escriba la siguiente expresión en el cuadro **Expresión** :</span><span class="sxs-lookup"><span data-stu-id="3c533-193">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Reseller Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Reseller Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Reseller Sales-Sales Amount] )  
        End  
    ```  
  
10. <span data-ttu-id="3c533-194">En la lista **Cadena de formato** , seleccione **"Porcentaje"**.</span><span class="sxs-lookup"><span data-stu-id="3c533-194">In the **Format string** list, select **"Percent"**.</span></span>  
  
11. <span data-ttu-id="3c533-195">En la lista **Comportamiento si no está vacío** , active la casilla **Reseller Sales-Sales Amount**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c533-195">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="3c533-196">En la barra de herramientas de la pestaña **Cálculos** , haga clic en **Nuevo miembro calculado**.</span><span class="sxs-lookup"><span data-stu-id="3c533-196">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="3c533-197">Cambie el nombre de este miembro calculado a `[Total Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="3c533-197">Change the name of this calculated member to `[Total Sales Ratio to All Products]`.</span></span>  
  
14. <span data-ttu-id="3c533-198">Escriba la siguiente expresión en el cuadro **Expresión** :</span><span class="sxs-lookup"><span data-stu-id="3c533-198">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Total Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Total Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Total Sales Amount] )  
        End  
    ```  
  
15. <span data-ttu-id="3c533-199">En la lista **Cadena de formato** , seleccione **"Porcentaje"**.</span><span class="sxs-lookup"><span data-stu-id="3c533-199">In the **Format string** list, select **"Percent"**.</span></span>  
  
16. <span data-ttu-id="3c533-200">En la lista **Comportamiento si no está vacío** , active las casillas **Internet Sales-Sales Amount** y **Reseller Sales-Sales Amount**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3c533-200">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
17. <span data-ttu-id="3c533-201">En la barra de herramientas de la pestaña **Cálculos** , haga clic en **Vista de script**y, a continuación, revise los tres cálculos que acaba de agregar al script de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3c533-201">On the toolbar of the **Calculations** tab, click **Script View**, and then review the three calculations that you just added to the calculation script.</span></span>  
  
18. <span data-ttu-id="3c533-202">Agregue una nueva línea al script de cálculo inmediatamente anterior al `[Internet Sales Ratio to All Products]` cálculo y, a continuación, agregue el siguiente texto al script en su propia línea:</span><span class="sxs-lookup"><span data-stu-id="3c533-202">Add a new line in the calculation script immediately before the `[Internet Sales Ratio to All Products]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate percentage of product to total product sales */  
    ```  
  
     <span data-ttu-id="3c533-203">Ahora ha definido un total de ocho miembros calculados, que están visibles en el panel **Organizador de scripts** cuando se está en la Vista de formulario.</span><span class="sxs-lookup"><span data-stu-id="3c533-203">You have now defined a total of eight calculated members, which are visible in the **Script Organizer** pane when you are in Form view.</span></span>  
  
## <a name="browsing-the-new-calculated-members"></a><span data-ttu-id="3c533-204">Examinar los nuevos miembros calculados</span><span class="sxs-lookup"><span data-stu-id="3c533-204">Browsing the New Calculated Members</span></span>  
  
1.  <span data-ttu-id="3c533-205">En el menú **Generar** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], haga clic en **Implementar Tutorial de Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="3c533-205">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="3c533-206">Cuando la implementación se haya completado correctamente, vaya a la pestaña **Explorador** y, a continuación, haga clic en **Volver a conectar**.</span><span class="sxs-lookup"><span data-stu-id="3c533-206">When deployment has successfully completed, switch to the **Browser** tab, click **Reconnect**.</span></span>  
  
3.  <span data-ttu-id="3c533-207">Haga clic en el icono de Excel y, a continuación, haga clic en **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="3c533-207">Click the Excel icon, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="3c533-208">En el panel **Lista de campos de la tabla dinámica** , expanda la carpeta **Valores** para ver los nuevos miembros calculados de la dimensión Medidas.</span><span class="sxs-lookup"><span data-stu-id="3c533-208">In the **PivotTable Field List** pane, expand **Values** folder to view the new calculated members in the Measures dimension.</span></span>  
  
5.  <span data-ttu-id="3c533-209">Arrastre **Importe de venta total** al área Valores y revise los resultados.</span><span class="sxs-lookup"><span data-stu-id="3c533-209">Drag the **Total Sales Amount** to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="3c533-210">Arrastre las medidas **Internet Sales-Sales Amount** y **Reseller Sales-Sales Amount** desde los grupos de medida **Internet Sales** y **Reseller Sales** hasta el área Valores.</span><span class="sxs-lookup"><span data-stu-id="3c533-210">Drag **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount** measures from the **Internet Sales** and **Reseller Sales** measure groups to the Values area.</span></span>  
  
     <span data-ttu-id="3c533-211">Observe que la medida **Total Sales Amount** es la suma de las medidas **Internet Sales-Sales Amount** y **Reseller Sales-Sales Amount** .</span><span class="sxs-lookup"><span data-stu-id="3c533-211">Notice that the **Total Sales Amount** measure is the sum of the **Internet Sales-Sales Amount** measure and the **Reseller Sales-Sales Amount** measure.</span></span>  
  
6.  <span data-ttu-id="3c533-212">Agregue la jerarquía definida por el usuario **Categorías de producto** al área de filtro del área **Filtro de informe** y, después, filtre los datos por **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="3c533-212">Add the **Product Categories** user-defined hierarchy to the filter area of the **Report Filter** area, and then filter the data by **Mountain Bikes**.</span></span>  
  
     <span data-ttu-id="3c533-213">Observe que la medida **Total Sales Amount** se calcula para la categoría de ventas del producto **Mountain Bikes** según las medidas **Internet Sales-Sales Amount** y **Reseller Sales-Sales Amount** de **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="3c533-213">Notice that the **Total Sales Amount** measure is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
7.  <span data-ttu-id="3c533-214">Agregue la jerarquía definida por el usuario **Date.Calendar Date** al área Etiquetas de fila y revise los resultados.</span><span class="sxs-lookup"><span data-stu-id="3c533-214">Add the **Date.Calendar Date** user-defined hierarchy to the Row labels area, and then review the results.</span></span>  
  
     <span data-ttu-id="3c533-215">Observe que la medida **Total Sales Amount** de cada año natural se calcula para la categoría de ventas del producto **Mountain Bikes** según las medidas **Internet Sales-Sales Amount** y **Reseller Sales-Sales Amount** de **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="3c533-215">Notice that the **Total Sales Amount** measure for each calendar year is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
8.  <span data-ttu-id="3c533-216">Agregue las medidas **Total GPM**, **Internet GPM**y **Reseller GPM** al área Valores y, a continuación, revise los resultados.</span><span class="sxs-lookup"><span data-stu-id="3c533-216">Add the **Total GPM**, **Internet GPM**, and **Reseller GPM** measures to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="3c533-217">Observe que el margen de beneficio bruto para la venta del distribuidor es notablemente inferior al de las ventas a través de Internet, como se muestra en la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="3c533-217">Notice that the gross profit margin for reseller sales is significantly lower than for sales over the Internet, as shown in the following image.</span></span>  
  
     <span data-ttu-id="3c533-218">![Panel Datos en el que se muestran las ventas del distribuidor](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Panel Datos en el que se muestran las ventas del distribuidor")</span><span class="sxs-lookup"><span data-stu-id="3c533-218">![Data pane showing reseller sales](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Data pane showing reseller sales")</span></span>  
  
9. <span data-ttu-id="3c533-219">Agregue las medidas **Total Sales Ratio to All Products**, **Internet Sales Ratio to All Products**y **Reseller Sales Ratio to All Products** al área Valores.</span><span class="sxs-lookup"><span data-stu-id="3c533-219">Add the **Total Sales Ratio to All Products**, **Internet Sales Ratio to All Products**, and **Reseller Sales Ratio to All Products** measures to the Values area.</span></span>  
  
     <span data-ttu-id="3c533-220">Observe que el ratio de las ventas de bicicletas de montaña en relación con todos los productos ha aumentado con el tiempo para las ventas por Internet, pero ha disminuido con el tiempo para la venta del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="3c533-220">Notice that the ratio of the sales of mountain bikes to all products has increased over time for Internet sales, but is decreasing over time for reseller sales.</span></span> <span data-ttu-id="3c533-221">Observe también que el ratio de la venta de bicicletas de montaña con respecto a todos los productos es inferior en la venta por distribuidor que en la venta por Internet.</span><span class="sxs-lookup"><span data-stu-id="3c533-221">Notice also that the ratio of the sale of mountain bikes to all products is lower from sales through resellers than it is for sales over the Internet.</span></span>  
  
10. <span data-ttu-id="3c533-222">Cambie el filtro de **Mountain Bikes** a **Bikes**, y revise los resultados.</span><span class="sxs-lookup"><span data-stu-id="3c533-222">Change the filter from **Mountain Bikes** to **Bikes**, and review the results.</span></span>  
  
     <span data-ttu-id="3c533-223">Observe que el margen de beneficio bruto de todas las bicicletas vendidas a través de distribuidores es negativo, porque las bicicletas de paseo y las bicicletas de carrera se están vendiendo con pérdida.</span><span class="sxs-lookup"><span data-stu-id="3c533-223">Notice that the gross profit margin for all bikes sold through resellers is negative, because touring bikes and road bikes are being sold at a loss.</span></span>  
  
11. <span data-ttu-id="3c533-224">Cambie el filtro a **Accessories**y, a continuación, revise los resultados.</span><span class="sxs-lookup"><span data-stu-id="3c533-224">Change the filter to **Accessories**, and then review the results.</span></span>  
  
     <span data-ttu-id="3c533-225">Observe que la venta de accesorios aumenta con el tiempo pero que estas ventas constituyen solo una pequeña fracción del total de ventas.</span><span class="sxs-lookup"><span data-stu-id="3c533-225">Notice that the sale of accessories is increasing over time, but that these sales make up only a small fraction of total sales.</span></span> <span data-ttu-id="3c533-226">Observe también que el margen de beneficio bruto para la venta de accesorios es superior que para las bicicletas.</span><span class="sxs-lookup"><span data-stu-id="3c533-226">Notice also that the gross profit margin for sales of accessories is higher than for bikes.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="3c533-227">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="3c533-227">Next Task in Lesson</span></span>  
 [<span data-ttu-id="3c533-228">Definir conjuntos con nombre</span><span class="sxs-lookup"><span data-stu-id="3c533-228">Defining Named Sets</span></span>](lesson-6-2-defining-named-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="3c533-229">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c533-229">See Also</span></span>  
 <span data-ttu-id="3c533-230">[Realizan](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="3c533-230">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="3c533-231">[Cálculos en modelos multidimensionales](multidimensional-models/calculations-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="3c533-231">[Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="3c533-232">Crear miembros calculados</span><span class="sxs-lookup"><span data-stu-id="3c533-232">Create Calculated Members</span></span>](multidimensional-models/create-calculated-members.md)  
  
  
