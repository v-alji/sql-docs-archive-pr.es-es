---
title: Expresiones (Generador de informes y SSRS) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
ms.assetid: 76d3ac86-650c-46fe-8086-8b3edcea3882
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: afd1b21986d0400ec8861520f3e86d1a80269036
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671393"
---
# <a name="expressions-report-builder-and-ssrs"></a><span data-ttu-id="d5b65-102">Expresiones (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="d5b65-102">Expressions (Report Builder and SSRS)</span></span>

<span data-ttu-id="d5b65-103">Las expresiones se utilizan ampliamente a lo largo de un informe para recuperar, calcular, mostrar, agrupar, ordenar, filtrar y parametrizar datos y darles formato.</span><span class="sxs-lookup"><span data-stu-id="d5b65-103">Expressions are widely used throughout a report to retrieve, calculate, display, group, sort, filter, parameterize, and format data.</span></span> <span data-ttu-id="d5b65-104">Muchas propiedades de elementos de informe pueden establecerse en una expresión.</span><span class="sxs-lookup"><span data-stu-id="d5b65-104">Many report item properties can be set to an expression.</span></span> <span data-ttu-id="d5b65-105">Las expresiones le ayudan a controlar el contenido, el diseño y la interactividad de un informe.</span><span class="sxs-lookup"><span data-stu-id="d5b65-105">Expressions help you control the content, design, and interactivity of your report.</span></span> <span data-ttu-id="d5b65-106">Las expresiones se escriben en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], se guardan en la definición de informe y son evaluadas por el procesador de informes al ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="d5b65-106">Expressions are written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], saved in the report definition, and evaluated by the report processor when you run the report.</span></span>  

<span data-ttu-id="d5b65-107">A diferencia de aplicaciones como [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office Excel en que se trabaja directamente con datos en una hoja de cálculo, en un informe se trabaja con expresiones que son marcadores de posición para los datos.</span><span class="sxs-lookup"><span data-stu-id="d5b65-107">Unlike applications such as [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Office Excel where you work with data directly in a worksheet, in a report, you work with expressions that are placeholders for data.</span></span> <span data-ttu-id="d5b65-108">Para ver los datos reales de las expresiones evaluadas, debe obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="d5b65-108">To see the actual data from the evaluated expressions, you must preview the report.</span></span> <span data-ttu-id="d5b65-109">Al ejecutar el informe, el procesador de informes evalúa cada expresión a medida que combina los datos del informe y elementos de diseño del informe, como tablas y gráficos.</span><span class="sxs-lookup"><span data-stu-id="d5b65-109">When you run the report, the report processor evaluates each expression as it combines report data and report layout elements such as tables and charts.</span></span>  

<span data-ttu-id="d5b65-110">Cuando diseña un informe, muchas expresiones de los elementos de informe se establecen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d5b65-110">As you design a report, many expressions for report items are set for you.</span></span> <span data-ttu-id="d5b65-111">Por ejemplo, al arrastrar un campo desde el panel de datos hasta una celda de la tabla en la superficie de diseño del informe, el valor del cuadro de texto se establece en una expresión simple para el campo.</span><span class="sxs-lookup"><span data-stu-id="d5b65-111">For example, when you drag a field from the data pane to a table cell on the report design surface, the text box value is set to a simple expression for the field.</span></span> <span data-ttu-id="d5b65-112">En la siguiente figura, el panel Datos de informe muestra el identificador de los campos de conjunto de datos Name, SalesTerritory, Code y Sales.</span><span class="sxs-lookup"><span data-stu-id="d5b65-112">In the following figure, the Report Data pane displays the dataset fields ID, Name, SalesTerritory, Code, and Sales.</span></span> <span data-ttu-id="d5b65-113">Se han agregado tres campos a la tabla: [Name], [Code] y [Sales].</span><span class="sxs-lookup"><span data-stu-id="d5b65-113">Three fields have been added to the table: [Name], [Code], and [Sales].</span></span> <span data-ttu-id="d5b65-114">La notación [Name] en la superficie de diseño representa la expresión `=Fields!Name.Value`subyacente.</span><span class="sxs-lookup"><span data-stu-id="d5b65-114">The notation [Name] on the design surface represents the underlying expression `=Fields!Name.Value`.</span></span>  

<span data-ttu-id="d5b65-115">![rs_DataDesignandPreview](../media/rs-datadesignandpreview.gif "rs_DataDesignandPreview")</span><span class="sxs-lookup"><span data-stu-id="d5b65-115">![rs_DataDesignandPreview](../media/rs-datadesignandpreview.gif "rs_DataDesignandPreview")</span></span>  

<span data-ttu-id="d5b65-116">Al obtener una vista previa del informe, el procesador de informes combina la región de datos de la tabla con los datos reales de la conexión de datos y muestra una fila en la tabla para cada fila del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="d5b65-116">When you preview the report, the report processor combines the table data region with the actual data from the data connection and displays a row in the table for every row in the result set.</span></span>  

<span data-ttu-id="d5b65-117">Para escribir expresiones manualmente, seleccione un elemento en la superficie de diseño y use los menús contextuales y los cuadros de diálogo para establecer las propiedades del elemento.</span><span class="sxs-lookup"><span data-stu-id="d5b65-117">To enter expressions manually, select an item on the design surface, and use shortcut menus and dialog boxes to set the properties of the item.</span></span> <span data-ttu-id="d5b65-118">Cuando vea el botón ***(fx)*** o el valor `<Expression>` en una lista desplegable, sabrá que puede establecer la propiedad en una expresión.</span><span class="sxs-lookup"><span data-stu-id="d5b65-118">When you see the ***(fx)*** button or the value `<Expression>` in a drop-down list, you know that you can set the property to an expression.</span></span> <span data-ttu-id="d5b65-119">Para obtener más información, vea [Agregar una expresión &#40;Generador de informes y SSRS&#41;](add-an-expression-report-builder-and-ssrs.md)subyacente.</span><span class="sxs-lookup"><span data-stu-id="d5b65-119">For more information, see [Add an Expression &#40;Report Builder and SSRS&#41;](add-an-expression-report-builder-and-ssrs.md).</span></span>  

<span data-ttu-id="d5b65-120">Para mayor información y ejemplos, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="d5b65-120">For more information and examples, see the following topics:</span></span>  

-   [<span data-ttu-id="d5b65-121">Usar expresiones en informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-121">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="d5b65-122">Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-122">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="d5b65-123">Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-123">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="d5b65-124">Ejemplos de expresión de grupo &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-124">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](group-expression-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="d5b65-125">Tutoriales &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-125">Tutorials &#40;Report Builder&#41;</span></span>](../report-builder-tutorials.md)  

-   [<span data-ttu-id="d5b65-126">Tutoriales de Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-126">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](../reporting-services-tutorials-ssrs.md)  

-   [<span data-ttu-id="d5b65-127">Ejemplos de informes (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="d5b65-127">Report Samples (Report Builder and SSRS)</span></span>](https://go.microsoft.com/fwlink/?LinkId=198283)  

<span data-ttu-id="d5b65-128">Para desarrollar expresiones complejas o expresiones que utilizan código personalizado o ensamblados personalizados, recomendamos utilizar el Diseñador de informes en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5b65-128">To develop complex expressions or expressions that use custom code or custom assemblies, we recommend that you use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="d5b65-129">Para obtener más información, vea [Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)subyacente.</span><span class="sxs-lookup"><span data-stu-id="d5b65-129">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  

> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  

##  <a name="understanding-simple-and-complex-expressions"></a><a name="Types"></a> <span data-ttu-id="d5b65-130">Descripción de las expresiones simples y complejas</span><span class="sxs-lookup"><span data-stu-id="d5b65-130">Understanding Simple and Complex Expressions</span></span>  
<span data-ttu-id="d5b65-131">Las expresiones comienzan por un signo igual (=) y se escriben en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d5b65-131">Expressions begin with an equal sign (=) and are written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="d5b65-132">Las expresiones pueden incluir una combinación de constantes, operadores y referencias a valores integrados (campos, colecciones y funciones) y a código externo o personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5b65-132">Expressions can include a combination of constants, operators, and references to built-in values (fields, collections, and functions), and to external or custom code.</span></span>  

<span data-ttu-id="d5b65-133">Puede utilizarlas para especificar el valor de muchas propiedades de elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="d5b65-133">You can use expressions to specify the value of many report item properties.</span></span> <span data-ttu-id="d5b65-134">Las propiedades más comunes son los valores de los cuadros de texto y el texto de los marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="d5b65-134">The most common properties are values for text boxes and placeholder text.</span></span> <span data-ttu-id="d5b65-135">Normalmente, si un cuadro de texto contiene solo una expresión, esta es el valor de la propiedad de cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="d5b65-135">Typically, if a text box contains only one expression, the expression is the value of the text box property.</span></span> <span data-ttu-id="d5b65-136">Si un cuadro de texto contiene varias expresiones, cada una es el valor de texto del marcador de posición en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="d5b65-136">If a text box contains multiple expressions, each expression is the value of placeholder text in the text box.</span></span>  

<span data-ttu-id="d5b65-137">De forma predeterminada, las expresiones aparecen en la superficie de diseño del informe como *expresiones simples* o *expresiones complejas*.</span><span class="sxs-lookup"><span data-stu-id="d5b65-137">By default, expressions appear on the report design surface as *simple* or *complex expressions*.</span></span>  

-   <span data-ttu-id="d5b65-138">**Simple** : las expresiones simples contienen una referencia a un solo elemento de una colección integrada, como un campo de conjunto de datos, un parámetro o un campo integrado.</span><span class="sxs-lookup"><span data-stu-id="d5b65-138">**Simple** A simple expression contains a reference to a single item in a built-in collection, for example, a dataset field, a parameter, or a built-in field.</span></span> <span data-ttu-id="d5b65-139">En la superficie de diseño, una expresión simple aparece entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="d5b65-139">On the design surface, a simple expression appears in brackets.</span></span> <span data-ttu-id="d5b65-140">Por ejemplo, `[FieldName]` corresponde a la expresión `=Fields!FieldName.Value`subyacente.</span><span class="sxs-lookup"><span data-stu-id="d5b65-140">For example, `[FieldName]` corresponds to the underlying expression `=Fields!FieldName.Value`.</span></span> <span data-ttu-id="d5b65-141">Las expresiones simples se crean automáticamente al crear el diseño del informe y arrastrar los elementos del panel Datos de informe a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="d5b65-141">Simple expressions are created for you automatically as you create the report layout and drag items from the Report Data pane to the design surface.</span></span> <span data-ttu-id="d5b65-142">Para obtener más información sobre los símbolos que representan diferentes colecciones integradas, vea [Descripción de los símbolos de prefijo en expresiones simples](#DisplayText).</span><span class="sxs-lookup"><span data-stu-id="d5b65-142">For more information about the symbols that represent different built-in collections, see [Understanding Prefix Symbols for Simple Expressions](#DisplayText).</span></span>  

-   <span data-ttu-id="d5b65-143">**Compleja** : las expresiones complejas contienen referencias a varias referencias, operadores y llamadas a función integradas.</span><span class="sxs-lookup"><span data-stu-id="d5b65-143">**Complex** A complex expression contains references to multiple built-in references, operators, and function calls.</span></span> <span data-ttu-id="d5b65-144">Una expresión compleja aparece como <\<Expr>> cuando el valor de la expresión incluye más de una referencia simple.</span><span class="sxs-lookup"><span data-stu-id="d5b65-144">A complex expression appears as <\<Expr>> when the expression value includes more than a simple reference.</span></span> <span data-ttu-id="d5b65-145">Para ver la expresión, mantenga el mouse sobre ella y use la información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="d5b65-145">To view the expression, hover over it and use the tooltip.</span></span> <span data-ttu-id="d5b65-146">Para modificar la expresión, ábrala en el cuadro de diálogo **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="d5b65-146">To edit the expression, open it in the **Expression** dialog box.</span></span>  

<span data-ttu-id="d5b65-147">La siguiente figura muestra expresiones simples y complejas típicas para cuadros de texto y el texto de los marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="d5b65-147">The following figure shows typical simple and complex expressions for both text boxes and placeholder text.</span></span>  

<span data-ttu-id="d5b65-148">![rs_ExpressionDefaultFormat](../media/rs-expressiondefaultformat.gif "rs_ExpressionDefaultFormat")</span><span class="sxs-lookup"><span data-stu-id="d5b65-148">![rs_ExpressionDefaultFormat](../media/rs-expressiondefaultformat.gif "rs_ExpressionDefaultFormat")</span></span>  

<span data-ttu-id="d5b65-149">Para mostrar valores de ejemplo en lugar del texto de las expresiones, aplique el formato al cuadro de texto o al texto del marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="d5b65-149">To display sample values instead of text for expressions, apply formatting to the text box or placeholder text.</span></span> <span data-ttu-id="d5b65-150">La siguiente figura muestra la superficie de diseño del informe alternada para mostrar los valores de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d5b65-150">The following figure shows the report design surface toggled to show sample values:</span></span>  

<span data-ttu-id="d5b65-151">![rs_ExpressionSampleValuesFormat](../media/rs-expressionsamplevaluesformat.gif "rs_ExpressionSampleValuesFormat")</span><span class="sxs-lookup"><span data-stu-id="d5b65-151">![rs_ExpressionSampleValuesFormat](../media/rs-expressionsamplevaluesformat.gif "rs_ExpressionSampleValuesFormat")</span></span>  

<span data-ttu-id="d5b65-152">Para más información, vea [Aplicar formato a texto y a marcadores de posición &#40;Generador de informes y SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d5b65-152">For more information, see [Formatting Text and Placeholders &#40;Report Builder and SSRS&#41;](formatting-text-and-placeholders-report-builder-and-ssrs.md).</span></span>  

## <a name="understanding-prefix-symbols-in-simple-expressions"></a><a name="DisplayText"></a><span data-ttu-id="d5b65-153">Descripción de los símbolos de prefijo en expresiones simples</span><span class="sxs-lookup"><span data-stu-id="d5b65-153">Understanding Prefix Symbols in Simple Expressions</span></span>  

<span data-ttu-id="d5b65-154">Las expresiones simples usan símbolos para indicar si la referencia es a un campo, un parámetro, una colección integrada o la colección ReportItems.</span><span class="sxs-lookup"><span data-stu-id="d5b65-154">Simple expressions use symbols to indicate whether the reference is to a field, a parameter, a built-in collection, or the ReportItems collection.</span></span> <span data-ttu-id="d5b65-155">En la tabla siguiente, se muestran ejemplos de texto mostrado junto con el texto de la expresión correspondiente:</span><span class="sxs-lookup"><span data-stu-id="d5b65-155">The following table shows examples of display and expression text:</span></span>  

|<span data-ttu-id="d5b65-156">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5b65-156">Item</span></span>|<span data-ttu-id="d5b65-157">Ejemplo de texto mostrado</span><span class="sxs-lookup"><span data-stu-id="d5b65-157">Display text example</span></span>|<span data-ttu-id="d5b65-158">Ejemplo de texto de expresión</span><span class="sxs-lookup"><span data-stu-id="d5b65-158">Expression text example</span></span>|  
|----------|--------------------------|-----------------------------|  
|<span data-ttu-id="d5b65-159">Campos de conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="d5b65-159">Dataset fields</span></span>|`[Sales]`<br /><br /> `[SUM(Sales)]`<br /><br /> `[FIRST(Store)]`|`=Fields!Sales.Value`<br /><br /> `=Sum(Fields!Sales.Value)`<br /><br /> `=First(Fields!Store.Value)`|  
|<span data-ttu-id="d5b65-160">Parámetros de informe</span><span class="sxs-lookup"><span data-stu-id="d5b65-160">Report parameters</span></span>|`[@Param]`<br /><br /> `[@Param.Label]`|`=Parameters!Param.Value`<br /><br /> `=Parameters!Param.Label`|  
|<span data-ttu-id="d5b65-161">Campos integrados</span><span class="sxs-lookup"><span data-stu-id="d5b65-161">Built-in fields</span></span>|`[&ReportName]`|`=Globals!ReportName.Value`|  
|<span data-ttu-id="d5b65-162">Caracteres literales usados para el texto mostrado</span><span class="sxs-lookup"><span data-stu-id="d5b65-162">Literal characters used for display text</span></span>|`\[Sales\]`|`[Sales]`|  



##  <a name="writing-complex-expressions"></a><a name="References"></a><span data-ttu-id="d5b65-163">Escribir expresiones complejas</span><span class="sxs-lookup"><span data-stu-id="d5b65-163">Writing Complex Expressions</span></span>  
<span data-ttu-id="d5b65-164">Las expresiones pueden incluir referencias a funciones, operadores, constantes, campos, parámetros, elementos de colecciones integradas y referencias a código personalizado incrustado o a ensamblados personalizados.</span><span class="sxs-lookup"><span data-stu-id="d5b65-164">Expressions can include references to functions, operators, constants, fields, parameters, items from built-in collections, and to embedded custom code or custom assemblies.</span></span>  

> [!NOTE]
>  <span data-ttu-id="d5b65-165">Para desarrollar expresiones complejas o expresiones que utilizan código personalizado o ensamblados personalizados, recomendamos utilizar el Diseñador de informes en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5b65-165">To develop complex expressions or expressions that use custom code or custom assemblies, we recommend that you use Report Designer in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="d5b65-166">Para obtener más información, vea [Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)subyacente.</span><span class="sxs-lookup"><span data-stu-id="d5b65-166">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  

<span data-ttu-id="d5b65-167">En la tabla siguiente se enumeran los tipos de referencias que se pueden incluir en una expresión:</span><span class="sxs-lookup"><span data-stu-id="d5b65-167">The following table lists the kinds of references you can include in an expression:</span></span>  

|<span data-ttu-id="d5b65-168">Referencias</span><span class="sxs-lookup"><span data-stu-id="d5b65-168">References</span></span>|<span data-ttu-id="d5b65-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5b65-169">Description</span></span>|<span data-ttu-id="d5b65-170">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5b65-170">Example</span></span>|  
|----------------|-----------------|-------------|  
|[<span data-ttu-id="d5b65-171">Constantes</span><span class="sxs-lookup"><span data-stu-id="d5b65-171">Constants</span></span>](expressions-report-builder-and-ssrs.md)|<span data-ttu-id="d5b65-172">Describe las constantes a las que puede tener acceso interactivamente para las propiedades que requieren valores constantes, por ejemplo los colores de fuente.</span><span class="sxs-lookup"><span data-stu-id="d5b65-172">Describes the constants you can access interactively for properties that require constant values, such as font colors.</span></span>|`="Blue"`|  
|[<span data-ttu-id="d5b65-173">Operadores</span><span class="sxs-lookup"><span data-stu-id="d5b65-173">Operators</span></span>](operators-in-expressions-report-builder-and-ssrs.md)|<span data-ttu-id="d5b65-174">Describe los operadores que puede utilizar para combinar referencias en una expresión.</span><span class="sxs-lookup"><span data-stu-id="d5b65-174">Describes the operators you can use to combine references in an expression.</span></span> <span data-ttu-id="d5b65-175">Por ejemplo, el operador `&` se utiliza para concatenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="d5b65-175">For example, the `&` operator is used for concatenating strings.</span></span>|`="The report ran at: " & Globals!ExecutionTime & "."`|  
|[<span data-ttu-id="d5b65-176">Colecciones integradas</span><span class="sxs-lookup"><span data-stu-id="d5b65-176">Built-in Collections</span></span>](built-in-collections-in-expressions-report-builder.md)|<span data-ttu-id="d5b65-177">Describe las colecciones integradas que puede incluir en una expresión; por ejemplo, `Fields`, `Parameters`y `Variables`.</span><span class="sxs-lookup"><span data-stu-id="d5b65-177">Describes the built-in collections that you can include in an expression, such as `Fields`, `Parameters`, and `Variables`.</span></span>|`=Fields!Sales.Value`<br /><br /> `=Parameters!Store.Value`<br /><br /> `=Variables!MyCalculation.Value`|  
|[<span data-ttu-id="d5b65-178">Funciones integradas de informe y de agregado</span><span class="sxs-lookup"><span data-stu-id="d5b65-178">Built-in Report and Aggregate Functions</span></span>](report-builder-functions-aggregate-functions-reference.md)|<span data-ttu-id="d5b65-179">Describe funciones integradas, como `Sum` o `Previous`, a las que puede tener acceso desde una expresión.</span><span class="sxs-lookup"><span data-stu-id="d5b65-179">Describes the built-in functions, such as `Sum` or `Previous`, that you can access from an expression.</span></span>|`=Previous(Sum(Fields!Sales.Value))`|  
|[<span data-ttu-id="d5b65-180">Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-180">Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;</span></span>](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)|<span data-ttu-id="d5b65-181">Describe cómo puede obtener acceso a las clases integradas de CLR <xref:System.Math> y <xref:System.Convert>, a otras clases de CLR, a funciones de biblioteca en tiempo de ejecución de [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] o a métodos de un ensamblado externo.</span><span class="sxs-lookup"><span data-stu-id="d5b65-181">Describes how you can access the built-in CLR classes <xref:System.Math> and <xref:System.Convert>, other CLR classes, [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] run-time library functions, or methods from an external assembly.</span></span><br /><br /> <span data-ttu-id="d5b65-182">Describe cómo puede tener acceso a código personalizado incrustado en un informe, o que se compila e instala como un ensamblado personalizado en el cliente de informes y en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="d5b65-182">Describes how you can access custom code that is embedded in your report, or that you compile and install as a custom assembly on both the report client and the report server.</span></span>|`=Sum(Fields!Sales.Value)`<br /><br /> `=CDate(Fields!SalesDate.Value)`<br /><br /> `=DateAdd("d",3,Fields!BirthDate.Value)`<br /><br /> `=Code.ToUSD(Fields!StandardCost.Value)`|  



##  <a name="validating-expressions"></a><a name="Valid"></a><span data-ttu-id="d5b65-183">Validar expresiones</span><span class="sxs-lookup"><span data-stu-id="d5b65-183">Validating Expressions</span></span>  
<span data-ttu-id="d5b65-184">Cuando cree una expresión para una propiedad de elemento de informe determinada, las referencias que puede incluir en una expresión dependen de los valores que la propiedad del elemento de informe pueda aceptar y del ámbito en el que se evalúa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="d5b65-184">When you create an expression for a specific report item property, the references that you can include in an expression depend on the values that the report item property can accept and the scope in which the property is evaluated.</span></span> <span data-ttu-id="d5b65-185">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d5b65-185">For example:</span></span>  

-   <span data-ttu-id="d5b65-186">De forma predeterminada, la expresión [Suma] calcula la suma de los datos que están en el ámbito en el momento en que se evalúa la expresión.</span><span class="sxs-lookup"><span data-stu-id="d5b65-186">By default, the expression [Sum] calculates the sum of data that is in scope at the time the expression is evaluated.</span></span> <span data-ttu-id="d5b65-187">Para una celda de la tabla, el ámbito depende de la fila y las pertenencias a los grupos de columnas.</span><span class="sxs-lookup"><span data-stu-id="d5b65-187">For a table cell, the scope depends on row and column group memberships.</span></span> <span data-ttu-id="d5b65-188">Para obtener más información, vea [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md)subyacente.</span><span class="sxs-lookup"><span data-stu-id="d5b65-188">For more information, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  

-   <span data-ttu-id="d5b65-189">Para el valor de una propiedad Font, el valor se debe evaluar como el nombre de una fuente.</span><span class="sxs-lookup"><span data-stu-id="d5b65-189">For the value for a Font property, the value must evaluate to the name of a font.</span></span>  

-   <span data-ttu-id="d5b65-190">La sintaxis de la expresión se valida en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="d5b65-190">Expression syntax is validated at design time.</span></span> <span data-ttu-id="d5b65-191">La validación del ámbito de la expresión se produce al publicar el informe.</span><span class="sxs-lookup"><span data-stu-id="d5b65-191">Expression scope validation occurs when you publish the report.</span></span> <span data-ttu-id="d5b65-192">En el caso de la validación que depende de los datos reales, los errores se pueden detectar solo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d5b65-192">For validation that depends on the actual data, errors can only be detected at run-time.</span></span> <span data-ttu-id="d5b65-193">Algunas de estas expresiones generan #Error como un mensaje de error en el informe representado.</span><span class="sxs-lookup"><span data-stu-id="d5b65-193">Some of these expressions produce #Error as an error message in the rendered report.</span></span> <span data-ttu-id="d5b65-194">Para ayudar a determinar los problemas de este tipo de error, debe utilizar el Diseñador de informes en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5b65-194">To help determine the issues for this kind of error, you must use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="d5b65-195">El Diseñador de informes proporciona un ventana de salida que proporciona más información acerca de estos errores.</span><span class="sxs-lookup"><span data-stu-id="d5b65-195">Report Designer provides an Output window that provides more information about these errors.</span></span>  

<span data-ttu-id="d5b65-196">Para obtener más información, vea [Referencia de expresiones &#40;Generador de informes y SSRS&#41;](expression-reference-report-builder-and-ssrs.md)subyacente.</span><span class="sxs-lookup"><span data-stu-id="d5b65-196">For more information, see [Expression Reference &#40;Report Builder and SSRS&#41;](expression-reference-report-builder-and-ssrs.md).</span></span>  

## <a name="in-this-section"></a><a name="Section"></a> <span data-ttu-id="d5b65-197">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d5b65-197">In This Section</span></span>

[<span data-ttu-id="d5b65-198">Agregar una expresión &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-198">Add an Expression &#40;Report Builder and SSRS&#41;</span></span>](add-an-expression-report-builder-and-ssrs.md)  

[<span data-ttu-id="d5b65-199">Usar expresiones en informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-199">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)  

[<span data-ttu-id="d5b65-200">Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-200">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  

[<span data-ttu-id="d5b65-201">Referencia de expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-201">Expression Reference &#40;Report Builder and SSRS&#41;</span></span>](expression-reference-report-builder-and-ssrs.md)  

## <a name="see-also"></a><span data-ttu-id="d5b65-202">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5b65-202">See Also</span></span>

- [<span data-ttu-id="d5b65-203">Expresión (cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="d5b65-203">Expression Dialog Box</span></span>](../expression-dialog-box.md)   
- [<span data-ttu-id="d5b65-204">Expresión &#40;cuadro de diálogo del Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="d5b65-204">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)