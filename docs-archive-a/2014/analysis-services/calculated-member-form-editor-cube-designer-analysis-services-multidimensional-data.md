---
title: Editor de formulario de miembro calculado (pestaña cálculos, diseñador de cubos) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.calculationexpression.calculatedmember.f1
ms.assetid: f7719b9e-b1e6-4792-90a6-30d9d8eb1196
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9dd45ece03fd81e0e7356e7bdcd0ec8dc53287bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670086"
---
# <a name="calculated-member-form-editor-calculations-tab-cube-designer-analysis-services---multidimensional-data"></a><span data-ttu-id="86afa-102">Editor de Formulario de miembro calculado (pestaña Cálculos, Diseñador de cubos) (Analysis Services -  Datos multidimensionales)</span><span class="sxs-lookup"><span data-stu-id="86afa-102">Calculated Member Form Editor (Calculations Tab, Cube Designer) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="86afa-103">Utilice el panel del **Editor de Formulario de miembro calculado** de la pestaña **Cálculos** del Diseñador de cubos para crear o modificar un miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-103">Use the **Calculated Member Form Editor** pane on the **Calculations** tab in Cube Designer to create or modify a calculated member.</span></span>  
  
 <span data-ttu-id="86afa-104">**Nota** Este panel solamente se muestra en la vista de formulario.</span><span class="sxs-lookup"><span data-stu-id="86afa-104">**Note** This pane is displayed only in form view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="86afa-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="86afa-105">Options</span></span>  
 <span data-ttu-id="86afa-106">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="86afa-106">**Name**</span></span>  
 <span data-ttu-id="86afa-107">Escriba el nombre del miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-107">Type the name of the calculated member.</span></span>  
  
 <span data-ttu-id="86afa-108">**Propiedades del miembro primario**</span><span class="sxs-lookup"><span data-stu-id="86afa-108">**Parent Properties**</span></span>  
 <span data-ttu-id="86afa-109">Expanda esta opción para ver las opciones **Jerarquía primaria**, **Miembro primario**y **Cambiar** .</span><span class="sxs-lookup"><span data-stu-id="86afa-109">Expand to view the **Parent hierarchy**, **Parent member**, and **Change** options.</span></span>  
  
 <span data-ttu-id="86afa-110">**Jerarquía primaria**</span><span class="sxs-lookup"><span data-stu-id="86afa-110">**Parent hierarchy**</span></span>  
 <span data-ttu-id="86afa-111">Seleccione la dimensión y la jerarquía del cubo seleccionado que debe incluir el miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-111">Select the dimension and hierarchy in the selected cube that is to include the calculated member.</span></span> <span data-ttu-id="86afa-112">Seleccione MEASURES para definir una medida calculada.</span><span class="sxs-lookup"><span data-stu-id="86afa-112">Select MEASURES to define a calculated measure.</span></span>  
  
 <span data-ttu-id="86afa-113">**Miembro primario**</span><span class="sxs-lookup"><span data-stu-id="86afa-113">**Parent member**</span></span>  
 <span data-ttu-id="86afa-114">Seleccione el miembro bajo el que debe aparecer el miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-114">Select the member beneath which the calculated member is to appear.</span></span>  
  
 <span data-ttu-id="86afa-115">**Nota** Esta opción está disponible si **Jerarquía primaria** especifica una jerarquía distinta de MEASURES.</span><span class="sxs-lookup"><span data-stu-id="86afa-115">**Note** This option is available if **Parent hierarchy** specifies a hierarchy other than MEASURES.</span></span>  
  
 <span data-ttu-id="86afa-116">**Cambio**</span><span class="sxs-lookup"><span data-stu-id="86afa-116">**Change**</span></span>  
 <span data-ttu-id="86afa-117">Seleccione esta opción para mostrar el cuadro de diálogo **Seleccionar miembro primario** y, luego, un miembro para **Miembro primario**.</span><span class="sxs-lookup"><span data-stu-id="86afa-117">Select to display the **Select Parent Member** dialog box and choose a member for **Parent member**.</span></span> <span data-ttu-id="86afa-118">Para más información sobre el cuadro de diálogo **Seleccionar miembro primario**, vea [Cuadro de diálogo Seleccionar miembro primario &#40;Analysis Services - Datos multidimensionales&#41;](select-parent-member-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="86afa-118">For more information about the **Select Parent Member** dialog box, see [Select Parent Member Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](select-parent-member-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="86afa-119">**Expression**</span><span class="sxs-lookup"><span data-stu-id="86afa-119">**Expression**</span></span>  
 <span data-ttu-id="86afa-120">Expanda esta opción para ver o modificar la expresión MDX (Expresiones multidimensionales) para el miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-120">Expand to view or edit the Multidimensional Expressions (MDX) expression for the calculated member.</span></span>  
  
 <span data-ttu-id="86afa-121">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="86afa-121">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86afa-122">Es recomendable que esta expresión se evalúe como una cadena o un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="86afa-122">It is recommended that this expression evaluate to a string or to a numeric value.</span></span>  
  
 <span data-ttu-id="86afa-123">**Propiedades adicionales**</span><span class="sxs-lookup"><span data-stu-id="86afa-123">**Additional Properties**</span></span>  
 <span data-ttu-id="86afa-124">Expanda para ver las opciones **Cadena de formato**, **Visible**, **Comportamiento si no está vacío**, **Expresiones de color**y **Expresiones de fuente** .</span><span class="sxs-lookup"><span data-stu-id="86afa-124">Expand to view the **Format string**, **Visible**, **Non-empty behavior**, **Color Expressions**, and **Font Expressions** options.</span></span>  
  
 <span data-ttu-id="86afa-125">**Cadena de formato**</span><span class="sxs-lookup"><span data-stu-id="86afa-125">**Format string**</span></span>  
 <span data-ttu-id="86afa-126">Escriba la cadena de formato MDX utilizada para dar formato al valor que devuelve el miembro calculado o seleccione una cadena de formato predefinida.</span><span class="sxs-lookup"><span data-stu-id="86afa-126">Type the MDX format string used to format the value returned by the calculated member, or select a predefined format string.</span></span>  
  
 <span data-ttu-id="86afa-127">Para más información sobre las cadenas de forato MDX, vea [FORMAT_STRING, contenido &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-format-string-contents.md).</span><span class="sxs-lookup"><span data-stu-id="86afa-127">For more information about MDX format strings, see [FORMAT_STRING Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-format-string-contents.md).</span></span>  
  
 <span data-ttu-id="86afa-128">**Estarán**</span><span class="sxs-lookup"><span data-stu-id="86afa-128">**Visible**</span></span>  
 <span data-ttu-id="86afa-129">Seleccione **True** para permitir que las aplicaciones cliente vean el miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-129">Select **True** to allow the calculated member to be visible to client applications.</span></span>  
  
 <span data-ttu-id="86afa-130">**Comportamiento si no está vacío**</span><span class="sxs-lookup"><span data-stu-id="86afa-130">**Non-empty behavior**</span></span>  
 <span data-ttu-id="86afa-131">Seleccione el nombre de la medida utilizada para resolver las consultas NON EMPTY en MDX para el miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-131">Select the name of the measure used to resolve NON EMPTY queries in MDX for the calculated member.</span></span> <span data-ttu-id="86afa-132">Si la propiedad **Comportamiento si no está vacío** está en blanco, es necesario evaluar el miembro calculado repetidamente para determinar si está vacío.</span><span class="sxs-lookup"><span data-stu-id="86afa-132">If the **Non Empty Behavior** property is blank, the calculated member must be evaluated repeatedly to determine if a member is empty.</span></span> <span data-ttu-id="86afa-133">Si la propiedad **Comportamiento si no está vacío** contiene el nombre de una medida, el miembro calculado se trata como si estuviera vacío si la medida especificada está vacía.</span><span class="sxs-lookup"><span data-stu-id="86afa-133">If the **Non Empty Behavior** property contains the name of a measure, the calculated member is treated as empty if the specified measure is empty.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="86afa-134">Esta propiedad está desusada.</span><span class="sxs-lookup"><span data-stu-id="86afa-134">This property is deprecated.</span></span> <span data-ttu-id="86afa-135">No la active.</span><span class="sxs-lookup"><span data-stu-id="86afa-135">Avoid setting it.</span></span> <span data-ttu-id="86afa-136">Consulte [características Desusadas Analysis Services en SQL Server 2014](deprecated-analysis-services-features-in-sql-server-2014.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="86afa-136">See [Deprecated Analysis Services Features in SQL Server 2014](deprecated-analysis-services-features-in-sql-server-2014.md) for details.</span></span>  
  
 <span data-ttu-id="86afa-137">**Expresiones de color**</span><span class="sxs-lookup"><span data-stu-id="86afa-137">**Color Expressions**</span></span>  
 <span data-ttu-id="86afa-138">Expanda para ver las opciones **Color en primer plano** y **Color de fondo** .</span><span class="sxs-lookup"><span data-stu-id="86afa-138">Expand to view the **Fore color** and **Back color** options.</span></span>  
  
 <span data-ttu-id="86afa-139">**Color en primer plano**</span><span class="sxs-lookup"><span data-stu-id="86afa-139">**Fore color**</span></span>  
 <span data-ttu-id="86afa-140">Escriba la expresión MDX que proporciona el color del primer plano del miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-140">Type the MDX expression that provides the foreground color of the calculated member.</span></span>  
  
 <span data-ttu-id="86afa-141">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="86afa-141">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="86afa-142">Haga clic en el botón de selección del color para mostrar el cuadro de diálogo **Color** e inserte el valor RGB (rojo-verde-azul) para un color específico en la expresión MDX.</span><span class="sxs-lookup"><span data-stu-id="86afa-142">Click the color selection button to display the **Color** dialog box and insert the RGB (Red-Green-Blue) value for a specified color into the MDX expression.</span></span> <span data-ttu-id="86afa-143">Para más información sobre los valores RGB, vea [Contenido de FORE_COLOR y BACK_COLOR &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span><span class="sxs-lookup"><span data-stu-id="86afa-143">For more information about RGB values, see [FORE_COLOR and BACK_COLOR Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span></span>  
  
 <span data-ttu-id="86afa-144">**Color de fondo**</span><span class="sxs-lookup"><span data-stu-id="86afa-144">**Back color**</span></span>  
 <span data-ttu-id="86afa-145">Escriba la expresión MDX que proporciona el color de fondo del miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-145">Type the MDX expression that provides the background color of the calculated member.</span></span>  
  
 <span data-ttu-id="86afa-146">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="86afa-146">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="86afa-147">Haga clic en el botón de selección del color para mostrar el cuadro de diálogo **Color** e inserte el valor RGB (rojo-verde-azul) para un color específico en la expresión MDX.</span><span class="sxs-lookup"><span data-stu-id="86afa-147">Click the color selection button to display the **Color** dialog box and insert the RGB (Red-Green-Blue) value for a specified color into the MDX expression.</span></span> <span data-ttu-id="86afa-148">Para más información sobre los valores RGB, vea [Contenido de FORE_COLOR y BACK_COLOR &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span><span class="sxs-lookup"><span data-stu-id="86afa-148">For more information about RGB values, see [FORE_COLOR and BACK_COLOR Contents &#40;MDX&#41;](multidimensional-models/mdx/mdx-cell-properties-fore-color-and-back-color-contents.md).</span></span>  
  
 <span data-ttu-id="86afa-149">**Expresiones de fuente**</span><span class="sxs-lookup"><span data-stu-id="86afa-149">**Font Expressions**</span></span>  
 <span data-ttu-id="86afa-150">Expanda para ver las opciones **Nombre de fuente**, **Tamaño de fuente**e **Indicadores de fuente** .</span><span class="sxs-lookup"><span data-stu-id="86afa-150">Expand to view the **Font name**, **Font size**, and **Font flags** options.</span></span>  
  
 <span data-ttu-id="86afa-151">**Nombre de fuente**</span><span class="sxs-lookup"><span data-stu-id="86afa-151">**Font name**</span></span>  
 <span data-ttu-id="86afa-152">Escriba la expresión MDX que proporciona el nombre de la fuente utilizada para el miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-152">Type the MDX expression that provides the name of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="86afa-153">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="86afa-153">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="86afa-154">Haga clic en el botón de selección de fuentes para mostrar el cuadro de diálogo **Fuente** e inserte los valores de propiedad para una fuente determinada en la expresión MDX.</span><span class="sxs-lookup"><span data-stu-id="86afa-154">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="86afa-155">Para más información sobre valores de propiedades, vea [Crear y usar los valores de propiedad &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="86afa-155">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
 <span data-ttu-id="86afa-156">**Tamaño de fuente**</span><span class="sxs-lookup"><span data-stu-id="86afa-156">**Font size**</span></span>  
 <span data-ttu-id="86afa-157">Escriba la expresión MDX que proporciona el tamaño de la fuente utilizada para el miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-157">Type the MDX expression that provides the size of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="86afa-158">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="86afa-158">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="86afa-159">Haga clic en el botón de selección de fuentes para mostrar el cuadro de diálogo **Fuente** e inserte los valores de propiedad para una fuente determinada en la expresión MDX.</span><span class="sxs-lookup"><span data-stu-id="86afa-159">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="86afa-160">Para más información sobre valores de propiedades, vea [Crear y usar los valores de propiedad &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="86afa-160">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
 <span data-ttu-id="86afa-161">**Indicadores de fuente**</span><span class="sxs-lookup"><span data-stu-id="86afa-161">**Font flags**</span></span>  
 <span data-ttu-id="86afa-162">Escriba la expresión MDX que proporciona el valor de mapa de bits que contiene las marcas de fuente, como subrayado o negrita, de la fuente utilizada para el miembro calculado.</span><span class="sxs-lookup"><span data-stu-id="86afa-162">Type the MDX expression that provides the bitmapped value containing the font flags, such as underline or bold, of the font used for the calculated member.</span></span>  
  
 <span data-ttu-id="86afa-163">Arrastre los elementos seleccionados del panel **Herramientas de cálculo** hasta esta opción para incluir la sintaxis MDX para el elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="86afa-163">Drag selected elements from the **Calculation Tools** pane to this option to include the MDX syntax for the selected element.</span></span>  
  
 <span data-ttu-id="86afa-164">Haga clic en el botón de selección de fuentes para mostrar el cuadro de diálogo **Fuente** e inserte los valores de propiedad para una fuente determinada en la expresión MDX.</span><span class="sxs-lookup"><span data-stu-id="86afa-164">Click the font selection button to display the **Font** dialog box and insert the property values for a specified font into the MDX expression.</span></span> <span data-ttu-id="86afa-165">Para más información sobre valores de propiedades, vea [Crear y usar los valores de propiedad &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span><span class="sxs-lookup"><span data-stu-id="86afa-165">For more information about property values, see [Creating and Using Property Values &#40;MDX&#41;](creating-and-using-property-values-mdx.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86afa-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86afa-166">See Also</span></span>  
 <span data-ttu-id="86afa-167">[Realizan](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="86afa-167">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="86afa-168">[Crear miembros calculados](multidimensional-models/create-calculated-members.md) </span><span class="sxs-lookup"><span data-stu-id="86afa-168">[Create Calculated Members](multidimensional-models/create-calculated-members.md) </span></span>  
 <span data-ttu-id="86afa-169">[Diseñador de cubos &#40;Analysis Services de datos multidimensionales&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="86afa-169">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="86afa-170">[Cálculos &#40;diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](calculations-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="86afa-170">[Calculations &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculations-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="86afa-171">[Barra de herramientas &#40;pestaña cálculos, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="86afa-171">[Toolbar &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](toolbar-calculations-tab-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="86afa-172">[Organizador de scripts &#40;pestaña cálculos, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="86afa-172">[Script Organizer &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](script-organizer-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="86afa-173">[Herramientas de cálculo &#40;pestaña cálculos, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="86afa-173">[Calculation Tools &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](calculation-tools-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="86afa-174">[Editor de formulario de conjuntos con nombre &#40;pestaña cálculos, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="86afa-174">[Named Set Form Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](named-set-form-editor-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="86afa-175">Editor de scripts &#40;pestaña cálculos, diseñador de cubos&#41; &#40;Analysis Services de datos multidimensionales&#41;</span><span class="sxs-lookup"><span data-stu-id="86afa-175">Script Editor &#40;Calculations Tab, Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](script-editor-calculations-cube-designer-analysis-services-multidimensional-data.md)  
  
  
