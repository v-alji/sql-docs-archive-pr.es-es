---
title: Ejemplos de expresiones (Generador de informes y SSRS) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/08/2017
ms.openlocfilehash: c7ef06143dafdb5034d0f6202fdc16bc51f74ca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671402"
---
# <a name="expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="3a5f0-102">Ejemplos de expresiones (Generador de informes y SSRS)</span><span class="sxs-lookup"><span data-stu-id="3a5f0-102">Expression Examples (Report Builder and SSRS)</span></span>

<span data-ttu-id="3a5f0-103">Las expresiones se usan con frecuencia en los informes para controlar el contenido y la apariencia de los mismos.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-103">Expressions are used frequently in reports to control content and report appearance.</span></span> <span data-ttu-id="3a5f0-104">Las expresiones se escriben en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] y pueden usar funciones integradas de código personalizado, variables de informe y de grupo, y variables definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-104">Expressions are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], and can use built-in functions custom code, report and group variables, and user-defined variables.</span></span> <span data-ttu-id="3a5f0-105">Las expresiones comienzan con un signo igual (=).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-105">Expressions begin with an equal sign (=).</span></span> <span data-ttu-id="3a5f0-106">Para más información sobre el editor de expresiones y los tipos de referencias que se pueden incluir, vea [Usar expresiones en informes &#40;Generador de informes y SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) y [Agregar una expresión &#40;Generador de informes y SSRS&#41;](add-an-expression-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-106">For more information about the expression editor and the types of references that you can include, see [Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md), and [Add an Expression &#40;Report Builder and SSRS&#41;](add-an-expression-report-builder-and-ssrs.md).</span></span>  

> [!IMPORTANT]  
>  <span data-ttu-id="3a5f0-107">Cuando se habilita el espacio seguro para RDL, solo se pueden usar algunos tipos y miembros en el texto de la expresión en el tiempo de publicación del informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-107">When RDL Sandboxing is enabled, only certain types and members can be used in expression text at report publish time.</span></span> <span data-ttu-id="3a5f0-108">Para más información, consulte [Enable and Disable RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-108">For more information, see [Enable and Disable RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span></span>  

<span data-ttu-id="3a5f0-109">En este tema se incluyen ejemplos de expresiones que se pueden usar en los informes para realizar tareas comunes.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-109">This topic provides examples of expressions that can be used for common tasks in a report.</span></span>  

-   <span data-ttu-id="3a5f0-110">[Funciones de Visual Basic](#VisualBasicFunctions) : ejemplos de funciones de fecha, de cadena, de conversión y condicionales de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a5f0-110">[Visual Basic Functions](#VisualBasicFunctions) Examples for date, string, conversion and conditional [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions.</span></span>  

-   <span data-ttu-id="3a5f0-111">[Funciones de informe](#ReportFunctions) Ejemplos de agregados y otras funciones de informe integradas.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-111">[Report Functions](#ReportFunctions) Examples for aggregates and other built-in report functions.</span></span>  

-   <span data-ttu-id="3a5f0-112">[Apariencia de los datos del informe](#AppearanceofReportData) : ejemplos relacionados con el cambio de apariencia de un informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-112">[Appearance of Report Data](#AppearanceofReportData) Examples for changing the appearance of a report.</span></span>  

-   <span data-ttu-id="3a5f0-113">[Propiedades](#Properties) : ejemplos para establecer las propiedades de elementos de informe a fin de controlar el formato o la visibilidad.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-113">[Properties](#Properties) Examples for setting report item properties to control format or visibility.</span></span>  

-   <span data-ttu-id="3a5f0-114">[Parámetros](#Parameters) : ejemplos relacionados con el uso de parámetros en una expresión.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-114">[Parameters](#Parameters) Examples for using parameters in an expression.</span></span>  

-   <span data-ttu-id="3a5f0-115">[Código personalizado](#CustomCode) : ejemplos de código personalizado incrustado.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-115">[Custom Code](#CustomCode) Examples of embedded custom code.</span></span>  

<span data-ttu-id="3a5f0-116">Para obtener ejemplos de expresiones para usos específicos, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-116">For expression examples for specific uses, see the following topics:</span></span>  

-   [<span data-ttu-id="3a5f0-117">Ejemplos de expresión de grupo &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a5f0-117">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="3a5f0-118">Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a5f0-118">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="3a5f0-119">Filtros de uso frecuente &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a5f0-119">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="3a5f0-120">Referencias a las colecciones de variables de informe y de grupo &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a5f0-120">Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-report-and-group-variables-references-report-builder.md)  

<span data-ttu-id="3a5f0-121">Para más información sobre las expresiones simples y complejas, dónde se pueden usar las expresiones y los tipos de referencias que se pueden incluir en una expresión, vea los temas en [Expresiones &#40;Generador de informes y SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-121">For more information about simple and complex expressions, where you can use expressions, and the types of references that you can include in an expression, see topics under [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="3a5f0-122">Para más información sobre el contexto donde se evalúan las expresiones para calcular agregados, vea [Ámbito de expresión para los totales, agregados y colecciones integradas &#40;Generador de informes y SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-122">For more information about the context in which expressions are evaluated for calculating aggregates, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  

<span data-ttu-id="3a5f0-123">Para aprender a escribir expresiones que usan muchas de las funciones y operadores que también se usan en los ejemplos de expresiones de este tema, pero en el contexto de la escritura de un informe, vea [Tutorial: Introducing Expressions](../tutorial-introducing-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-123">To learn how to write expressions that use many of the functions and operators also used by expression examples in this topic, but in the context of writing a report, see [Tutorial: Introducing Expressions](../tutorial-introducing-expressions.md).</span></span>  

<span data-ttu-id="3a5f0-124">El editor de expresiones incluye también una vista jerárquica de funciones integradas.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-124">The expression editor includes a hierarchical view of built-in functions.</span></span> <span data-ttu-id="3a5f0-125">Cuando se selecciona una función, aparece un ejemplo de código en el panel de valores.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-125">When you select the function, a code example appears in the Values pane.</span></span> <span data-ttu-id="3a5f0-126">Para obtener más información, vea el cuadro de [diálogo expresión](../expression-dialog-box.md) o el [cuadro de diálogo expresión &#40;generador de informes&#41;](../expression-dialog-box-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-126">For more information, see the [Expression Dialog Box](../expression-dialog-box.md) or [Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md).</span></span>  

## <a name="functions"></a><span data-ttu-id="3a5f0-127">Functions</span><span class="sxs-lookup"><span data-stu-id="3a5f0-127">Functions</span></span>  

<span data-ttu-id="3a5f0-128">Muchas expresiones de un informe contienen funciones.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-128">Many expressions in a report contain functions.</span></span> <span data-ttu-id="3a5f0-129">Con estas funciones, se puede dar formato a los datos, aplicar lógica y obtener acceso a los metadatos del informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-129">You can format data, apply logic, and access report metadata using these functions.</span></span> <span data-ttu-id="3a5f0-130">Puede escribir expresiones que usen funciones de la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] biblioteca en tiempo de ejecución y de los <xref:System.Convert> espacios de <xref:System.Math> nombres y.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-130">You can write expressions that use functions from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library, and from the <xref:System.Convert> and <xref:System.Math> namespaces.</span></span> <span data-ttu-id="3a5f0-131">Puede agregar referencias a las funciones desde otros ensamblados o desde código personalizado.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-131">You can add references to functions from other assemblies or custom code.</span></span> <span data-ttu-id="3a5f0-132">También puede utilizar las clases de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , incluido <xref:System.Text.RegularExpressions> .</span><span class="sxs-lookup"><span data-stu-id="3a5f0-132">You can also use classes from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], including <xref:System.Text.RegularExpressions>.</span></span>  

###  <a name="visual-basic-functions"></a><a name="VisualBasicFunctions"></a> <span data-ttu-id="3a5f0-133">Funciones de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3a5f0-133">Visual Basic Functions</span></span>  
<span data-ttu-id="3a5f0-134">Las funciones de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] se pueden usar para manipular los datos que se muestran en los cuadros de texto o que se emplean en los parámetros, las propiedades u otras áreas del informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-134">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to manipulate the data that is displayed in text boxes or that is used for parameters, properties, or other areas of the report.</span></span> <span data-ttu-id="3a5f0-135">En esta sección se ofrecen ejemplos de algunas de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-135">This section provides examples demonstrating some of these functions.</span></span> <span data-ttu-id="3a5f0-136">Para obtener más información, vea [Miembros de la biblioteca en tiempo de ejecución de Visual Basic](https://go.microsoft.com/fwlink/?LinkId=198941) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-136">For more information, see [Visual Basic Runtime Library Members](https://go.microsoft.com/fwlink/?LinkId=198941) on MSDN.</span></span>  

<span data-ttu-id="3a5f0-137">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] proporciona muchas opciones de formato, por ejemplo, formatos de fecha específicos.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-137">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides many custom format options, for example, for specific date formats.</span></span> <span data-ttu-id="3a5f0-138">Para obtener más información, vea [Aplicar formato a tipos](https://go.microsoft.com/fwlink/?LinkId=112024) en MSDN.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-138">For more information, see [Formatting Types](https://go.microsoft.com/fwlink/?LinkId=112024) on MSDN.</span></span>  

#### <a name="math-functions"></a><span data-ttu-id="3a5f0-139">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="3a5f0-139">Math Functions</span></span>  

-   <span data-ttu-id="3a5f0-140">La función `Round` es útil para redondear números al entero más cercano.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-140">The `Round` function is useful to round numbers to the nearest integer.</span></span> <span data-ttu-id="3a5f0-141">La siguiente expresión redondea el valor1,3 a 1:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-141">The following expression rounds a 1.3 to 1:</span></span>  

```  
= Round(1.3)  
```  

<span data-ttu-id="3a5f0-142">También puede escribir una expresión para redondear un valor al múltiplo que usted especifique, de forma similar a la función `MRound` de Excel.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-142">You can also write an expression to round a value to a multiple that you specify, similar to the `MRound` function in Excel.</span></span> <span data-ttu-id="3a5f0-143">Multiplique el valor por un factor que crea un entero, redondee el número y, a continuación, divida por el mismo factor.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-143">Multiply the value by a factor that creates an integer, round the number, and then divide by the same factor.</span></span> <span data-ttu-id="3a5f0-144">Por ejemplo, para redondear 1,3 al múltiplo más cercano de 0,2 (1,4), utilice la siguiente expresión:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-144">For example, to round 1.3 to the nearest multiple of .2 (1.4), use the following expression:</span></span>  

```  
= Round(1.3*5)/5  
```  

####  <a name="date-functions"></a><a name="DateFunctions"></a><span data-ttu-id="3a5f0-145">Funciones de fecha</span><span class="sxs-lookup"><span data-stu-id="3a5f0-145">Date Functions</span></span>  

-   <span data-ttu-id="3a5f0-146">La función `Today` proporciona la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-146">The `Today` function provides the current date.</span></span> <span data-ttu-id="3a5f0-147">Esta expresión puede utilizarse en un cuadro de texto para mostrar la fecha en el informe o puede utilizarse en un parámetro para filtrar los datos por la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-147">This expression can be used in a text box to display the date on the report, or in a parameter to filter data based on the current date.</span></span>  

```  
=Today()  
```  

-   <span data-ttu-id="3a5f0-148">La función `DateAdd` es útil para suministrar un rango de fechas basado en un solo parámetro.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-148">The `DateAdd` function is useful for supplying a range of dates based on a single parameter.</span></span> <span data-ttu-id="3a5f0-149">La expresión siguiente proporciona una fecha que es seis meses posterior a la fecha de un parámetro denominado *StartDate*.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-149">The following expression provides a date that is six months after the date from a parameter named *StartDate*.</span></span>  

```  
=DateAdd(DateInterval.Month, 6, Parameters!StartDate.Value)  
```  

-   <span data-ttu-id="3a5f0-150">La función `Year` muestra el año correspondiente a una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-150">The `Year` function displays the year for a particular date.</span></span> <span data-ttu-id="3a5f0-151">Puede utilizarse para agrupar las fechas o para mostrar el año como etiqueta para un conjunto de fechas.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-151">You can use this to group dates together or to display the year as a label for a set of dates.</span></span> <span data-ttu-id="3a5f0-152">Esta expresión proporciona el año correspondiente a un determinado grupo de fechas de pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-152">This expression provides the year for a given group of sales order dates.</span></span> <span data-ttu-id="3a5f0-153">También es posible utilizar la función `Month` y otras funciones para manipular las fechas.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-153">The `Month` function and other functions can also be used to manipulate dates.</span></span> <span data-ttu-id="3a5f0-154">Para obtener más información, consulte la documentación de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a5f0-154">For more information, see the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] documentation.</span></span>  

```  
=Year(Fields!OrderDate.Value)  
```  

-   <span data-ttu-id="3a5f0-155">Puede combinar las funciones en una expresión para personalizar el formato.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-155">You can combine functions in an expression to customize the format.</span></span> <span data-ttu-id="3a5f0-156">La siguiente expresión cambia el formato día/mes/año de una fecha a número de la semana/semana/mes.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-156">The following expression changes the format of a date in the form month-day-year to month-week-week number.</span></span> <span data-ttu-id="3a5f0-157">Por ejemplo, 23/12/2009 a tercera semana de diciembre:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-157">For example, 12/23/2009 to December Week 3:</span></span>  

```  
=Format(Fields!MyDate.Value, "MMMM") & " Week " &   
(Int(DateDiff("d", DateSerial(Year(Fields!MyDate.Value),   
Month(Fields!MyDate.Value),1), Fields!FullDateAlternateKey.Value)/7)+1).ToString  
```  

<span data-ttu-id="3a5f0-158">Cuando se utiliza como un campo calculado en un conjunto de datos, puede utilizar esta expresión en un gráfico para agregar los valores por semana dentro de cada mes.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-158">When used as a calculated field in a dataset, you can use this expression on a chart to aggregate values by week within each month.</span></span>  

-   <span data-ttu-id="3a5f0-159">La siguiente expresión da formato al valor SellStartDate como MMM-AA.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-159">The following expression formats the SellStartDate value as MMM-YY.</span></span> <span data-ttu-id="3a5f0-160">El campo SellStartDate es un tipo de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-160">SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "MMM-yy")  
```  

-   <span data-ttu-id="3a5f0-161">La siguiente expresión da formato al valor SellStartDate como dd/MM/aaaa.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-161">The following expression formats the SellStartDate value as dd/MM/yyyy.</span></span> <span data-ttu-id="3a5f0-162">El campo SellStartDate es un tipo de datos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-162">The SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "dd/MM/yyyy")  
```  

-   <span data-ttu-id="3a5f0-163">La función `CDate` convierte el valor en una fecha.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-163">The `CDate` function converts the value to a date.</span></span> <span data-ttu-id="3a5f0-164">La función `Now` devuelve un valor de fecha que contiene la fecha y la hora actuales del sistema.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-164">The `Now` function returns a date value containing the current date and time according to your system.</span></span> <span data-ttu-id="3a5f0-165">`DateDiff` devuelve un valor de tipo Long que especifica el número de intervalos de tiempo entre dos valores de fecha.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-165">`DateDiff` returns a Long value specifying the number of time intervals between two Date values.</span></span>  

<span data-ttu-id="3a5f0-166">El ejemplo siguiente muestra la fecha de inicio del año en curso</span><span class="sxs-lookup"><span data-stu-id="3a5f0-166">The following example displays the start date of the current year</span></span>  

```  
=DateAdd(DateInterval.Year,DateDiff(DateInterval.Year,CDate("01/01/1900"),Now()),CDate("01/01/1900"))  
```  

-   <span data-ttu-id="3a5f0-167">El ejemplo siguiente muestra la fecha de inicio del mes anterior en función del mes actual.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-167">The following example displays the start date for the previous month based on the current month.</span></span>  

```  
=DateAdd(DateInterval.Month,DateDiff(DateInterval.Month,CDate("01/01/1900"),Now())-1,CDate("01/01/1900"))  
```  

-   <span data-ttu-id="3a5f0-168">La siguiente expresión genera los años de intervalo entre SellStartDate y LastReceiptDate.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-168">The following expression generates the interval years between SellStartDate and LastReceiptDate.</span></span> <span data-ttu-id="3a5f0-169">Estos campos están en dos conjuntos de datos distintos, DataSet1 y DataSet2.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-169">These fields are in two different datasets, DataSet1 and DataSet2.</span></span> <span data-ttu-id="3a5f0-170">La [función First &#40;Generador de informes y SSRS&#41;](report-builder-functions-first-function.md), que es una función de agregado, devuelve el primer valor de SellStartDate en DataSet1 y el primer valor de LastReceiptDate en DataSet2.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-170">The [First Function &#40;Report Builder and SSRS&#41;](report-builder-functions-first-function.md), which is an aggregate function, returns the first value of SellStartDate in DataSet1 and the first value of LastReceiptDate in DataSet2.</span></span>  

```  
=DATEDIFF("yyyy", First(Fields!SellStartDate.Value, "DataSet1"), First(Fields!LastReceiptDate.Value, "DataSet2"))  
```  

-   <span data-ttu-id="3a5f0-171">La función `DatePart` devuelve un valor entero que contiene el componente especificado de un valor de fecha determinado. La siguiente expresión devuelve el año del primer valor de SellStartDate en DataSet1.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-171">The `DatePart` function returns an Integer value containing the specified component of a given Date value.The following expression returns the year for the first value of the SellStartDate in DataSet1.</span></span> <span data-ttu-id="3a5f0-172">Se especifica el ámbito del conjunto de datos porque hay varios conjuntos de datos en el informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-172">The dataset scope is specified because there are multiple datasets in the report.</span></span>  

```  
=Datepart("yyyy", First(Fields!SellStartDate.Value, "DataSet1"))  

```  

-   <span data-ttu-id="3a5f0-173">La función `DateSerial` devuelve un valor de fecha que representa un año, un mes y un día especificados, con la información de hora establecida en medianoche.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-173">The `DateSerial` function returns a Date value representing a specified year, month, and day, with the time information set to midnight.</span></span> <span data-ttu-id="3a5f0-174">El ejemplo siguiente muestra la fecha final del mes anterior en función del mes actual.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-174">The following example displays the ending date for the prior month, based on the current month.</span></span>  

```  
=DateSerial(Year(Now()), Month(Now()), "1").AddDays(-1)  
```  

-   <span data-ttu-id="3a5f0-175">Las siguientes expresiones muestran varias fechas según un valor de parámetro de fecha seleccionado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-175">The following expressions display various dates based on a date parameter value selected by the user.</span></span>  

|<span data-ttu-id="3a5f0-176">Descripción de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a5f0-176">Example Description</span></span>|<span data-ttu-id="3a5f0-177">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a5f0-177">Example</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="3a5f0-178">Ayer</span><span class="sxs-lookup"><span data-stu-id="3a5f0-178">Yesterday</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-1)`|  
|<span data-ttu-id="3a5f0-179">Hace dos días</span><span class="sxs-lookup"><span data-stu-id="3a5f0-179">Two Days Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-2)`|  
|<span data-ttu-id="3a5f0-180">Hace un mes</span><span class="sxs-lookup"><span data-stu-id="3a5f0-180">One Month Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-1,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="3a5f0-181">Hace dos meses</span><span class="sxs-lookup"><span data-stu-id="3a5f0-181">Two Months Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-2,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="3a5f0-182">Hace un año</span><span class="sxs-lookup"><span data-stu-id="3a5f0-182">One Year Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-1,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="3a5f0-183">Hace dos años</span><span class="sxs-lookup"><span data-stu-id="3a5f0-183">Two Years Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-2,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  

####  <a name="string-functions"></a><a name="StringFunctions"></a><span data-ttu-id="3a5f0-184">Funciones de cadena</span><span class="sxs-lookup"><span data-stu-id="3a5f0-184">String Functions</span></span>  

-   <span data-ttu-id="3a5f0-185">Combine varios campos con operadores de concatenación y constantes de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a5f0-185">Combine more than one field by using concatenation operators and [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] constants.</span></span> <span data-ttu-id="3a5f0-186">La expresión siguiente devuelve dos campos, cada uno de ellos en una línea diferente del mismo cuadro de texto:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-186">The following expression returns two fields, each on a separate line in the same text box:</span></span>  

```  
=Fields!FirstName.Value & vbCrLf & Fields!LastName.Value   
```  

-   <span data-ttu-id="3a5f0-187">Aplique formato a las fechas y los números de una cadena con la función `Format`.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-187">Format dates and numbers in a string with the `Format` function.</span></span> <span data-ttu-id="3a5f0-188">La expresión siguiente muestra los valores de los parámetros *StartDate* y *EndDate* en formato de fecha larga:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-188">The following expression displays values of the *StartDate* and *EndDate* parameters in long date format:</span></span>  

```  
=Format(Parameters!StartDate.Value, "D") & " through " &  Format(Parameters!EndDate.Value, "D")    
```  

<span data-ttu-id="3a5f0-189">Si el cuadro de texto solo contiene una fecha o un número, debe utilizar la propiedad formato del cuadro de texto para aplicar formato en lugar de la `Format` función dentro del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-189">If the text box contains only a date or number, you should use the Format property of the text box to apply formatting instead of the `Format` function within the text box.</span></span>  

-   <span data-ttu-id="3a5f0-190">Las `Right` `Len` funciones, y `InStr` son útiles para devolver una subcadena; por ejemplo, recortar el nombre de usuario del *dominio* \\ *username* solo en el nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-190">The `Right`, `Len`, and `InStr` functions are useful for returning a substring, for example, trimming *DOMAIN*\\*username* to just the user name.</span></span> <span data-ttu-id="3a5f0-191">La siguiente expresión devuelve la parte de la cadena situada a la derecha de un carácter de barra diagonal inversa (\\) de un parámetro denominado *User*:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-191">The following expression returns the part of the string to the right of a backslash (\\) character from a parameter named *User*:</span></span>  

```  
=Right(Parameters!User.Value, Len(Parameters!User.Value) - InStr(Parameters!User.Value, "\"))  
```  

<span data-ttu-id="3a5f0-192">La siguiente expresión da como resultado el mismo valor que el anterior, con los miembros de la [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> clase en lugar de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] las funciones:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-192">The following expression results in the same value as the previous one, using members of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> class instead of [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions:</span></span>  

```  
=Parameters!User.Value.Substring(Parameters!User.Value.IndexOf("\")+1, Parameters!User.Value.Length-Parameters!User.Value.IndexOf("\")-1)  
```  

-   <span data-ttu-id="3a5f0-193">Muestre los valores seleccionados en un parámetro de varios valores.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-193">Display the selected values from a multivalue parameter.</span></span> <span data-ttu-id="3a5f0-194">En el ejemplo siguiente se usa la `Join` función para concatenar los valores seleccionados del parámetro *alseleccionar* en una sola cadena que se puede establecer como una expresión para el valor de un cuadro de texto en un elemento de informe:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-194">The following example uses the `Join` function to concatenate the selected values of the parameter *MySelection* into a single string that can be set as an expression for the value of a text box in a report item:</span></span>  

```  
= Join(Parameters!MySelection.Value)  
```  

<span data-ttu-id="3a5f0-195">El ejemplo siguiente hace lo mismo que el ejemplo anterior, además de mostrar una cadena de texto antes de la lista de valores seleccionados.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-195">The following example does the same as the above example, as well as displays a text string prior to the list of selected values.</span></span>  

```  
="Report for " & JOIN(Parameters!MySelection.Value, " & ")  

```  

-   <span data-ttu-id="3a5f0-196">Las `Regex` funciones de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> son útiles para cambiar el formato de las cadenas existentes, por ejemplo, para dar formato a un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-196">The `Regex` functions from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> are useful for changing the format of existing strings, for example, formatting a telephone number.</span></span> <span data-ttu-id="3a5f0-197">La expresión siguiente usa la `Replace` función para cambiar el formato de un número de teléfono de diez dígitos de un campo de "*nnn* - *nnn* - *nnnn*" a "(*nnn*) *nnn* - *nnnn*":</span><span class="sxs-lookup"><span data-stu-id="3a5f0-197">The following expression uses the `Replace` function to change the format of a ten-digit telephone number in a field from "*nnn*-*nnn*-*nnnn*" to "(*nnn*) *nnn*-*nnnn*":</span></span>  

```  
=System.Text.RegularExpressions.Regex.Replace(Fields!Phone.Value, "(\d{3})[ -.]*(\d{3})[ -.]*(\d{4})", "($1) $2-$3")  
```  

> [!NOTE]  
>  <span data-ttu-id="3a5f0-198">Compruebe que el valor de Fields!Phone.Value no tiene espacios adicionales y es del tipo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-198">Verify that the value for Fields!Phone.Value has no extra spaces and is of type <xref:System.String>.</span></span>  

#### <a name="lookup"></a><span data-ttu-id="3a5f0-199">Búsqueda</span><span class="sxs-lookup"><span data-stu-id="3a5f0-199">Lookup</span></span>  

-   <span data-ttu-id="3a5f0-200">Al especificar un campo clave, puede usar la función `Lookup` para recuperar un valor de un conjunto de datos para una relación uno a uno, por ejemplo, un par clave-valor.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-200">By specifying a key field, you can use the `Lookup` function to retrieve a value from a dataset for a one-to-one relationship, for example, a key-value pair.</span></span> <span data-ttu-id="3a5f0-201">En la expresión siguiente se muestra el nombre de producto de un conjunto de datos ("Producto"), según el identificador de producto con el que se va a realizar la coincidencia:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-201">The following expression displays the product name from a dataset ("Product"), given the product identifier to match on:</span></span>  

```  
=Lookup(Fields!PID.Value, Fields!ProductID.Value, Fields!ProductName.Value, "Product")  
```  

#### <a name="lookupset"></a><span data-ttu-id="3a5f0-202">LookupSet</span><span class="sxs-lookup"><span data-stu-id="3a5f0-202">LookupSet</span></span>  

-   <span data-ttu-id="3a5f0-203">Al especificar un campo de clave, puede usar la función `LookupSet` para recuperar un conjunto de valores de un conjunto de datos para una relación de uno a varios.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-203">By specifying a key field, you can use the `LookupSet` function to retrieve a set of values from a dataset for a one-to-many relationship.</span></span> <span data-ttu-id="3a5f0-204">Por ejemplo, una persona puede tener varios números de teléfono.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-204">For example, a person can have multiple telephone numbers.</span></span> <span data-ttu-id="3a5f0-205">En el siguiente ejemplo, suponga que el conjunto de datos PhoneList contiene un identificador de persona y un número de teléfono en cada fila.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-205">In the following example, assume the dataset PhoneList contains a person identifier and a telephone number in each row.</span></span> <span data-ttu-id="3a5f0-206">`LookupSet` devuelve una matriz de valores.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-206">`LookupSet` returns an array of values.</span></span> <span data-ttu-id="3a5f0-207">La siguiente expresión combina los valores devueltos en una sola cadena y muestra la lista de números de teléfono para la persona especificada por ContactID:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-207">The following expression combines the return values into a single string and displays the list of telephone numbers for the person specified by ContactID:</span></span>  

```  
=Join(LookupSet(Fields!ContactID.Value, Fields!PersonID.Value, Fields!PhoneNumber.Value, "PhoneList"),",")  
```  

####  <a name="conversion-functions"></a><a name="ConversionFunctions"></a><span data-ttu-id="3a5f0-208">Funciones de conversión</span><span class="sxs-lookup"><span data-stu-id="3a5f0-208">Conversion Functions</span></span>  
<span data-ttu-id="3a5f0-209">Puede usar las funciones de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] para convertir el tipo de datos de un campo en otro tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-209">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to convert a field from the one data type to a different data type.</span></span> <span data-ttu-id="3a5f0-210">Las funciones de conversión pueden usarse para convertir el tipo de datos predeterminado de un campo en el tipo de datos necesario para realizar cálculos o para combinar texto.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-210">Conversion functions can be used to convert the default data type for a field to the data type needed for calculations or to combine text.</span></span>  

-   <span data-ttu-id="3a5f0-211">La expresión siguiente convierte la constante 500 al tipo Decimal a fin de compararla con un tipo de datos money de [!INCLUDE[tsql](../../includes/tsql-md.md)] en el campo Valor de una expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-211">The following expression converts the constant 500 to type Decimal in order to compare it to a [!INCLUDE[tsql](../../includes/tsql-md.md)] money data type in the Value field for a filter expression.</span></span>  

```  
=CDec(500)  
```  

-   <span data-ttu-id="3a5f0-212">La expresión siguiente muestra el número de valores seleccionados para el parámetro de varios valores *MySelection*.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-212">The following expression displays the number of values selected for the multivalue parameter *MySelection*.</span></span>  

```  
=CStr(Parameters!MySelection.Count)  
```  

####  <a name="decision-functions"></a><a name="DecisionFunctions"></a> <span data-ttu-id="3a5f0-213">Funciones de decisión</span><span class="sxs-lookup"><span data-stu-id="3a5f0-213">Decision Functions</span></span>  

-   <span data-ttu-id="3a5f0-214">La función `Iif` devuelve un valor u otro en función de si la expresión es TRUE o no.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-214">The `Iif` function returns one of two values depending on whether the expression is true or not.</span></span> <span data-ttu-id="3a5f0-215">En la expresión siguiente, se usa la función `Iif` para devolver el valor booleano `True` si el valor de `LineTotal` es mayor que 100.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-215">The following expression uses the `Iif` function to return a Boolean value of `True` if the value of `LineTotal` exceeds 100.</span></span> <span data-ttu-id="3a5f0-216">En caso contrario, devuelve `False`:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-216">Otherwise it returns `False`:</span></span>  

```  
=IIF(Fields!LineTotal.Value > 100, True, False)  
```  

-   <span data-ttu-id="3a5f0-217">Use varias funciones `IIF` (lo que también se conoce como "funciones IIF anidadas") para devolver un valor entre tres posibles en función del valor de `PctComplete`.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-217">Use multiple `IIF` functions (also known as "nested IIFs") to return one of three values depending on the value of `PctComplete`.</span></span> <span data-ttu-id="3a5f0-218">La expresión siguiente puede situarse en el color de relleno de un cuadro de texto para cambiar el color de fondo en función del valor existente en dicho cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-218">The following expression can be placed in the fill color of a text box to change the background color depending on the value in the text box.</span></span>  

```  
=IIF(Fields!PctComplete.Value >= 10, "Green", IIF(Fields!PctComplete.Value >= 1, "Blue", "Red"))  
```  

<span data-ttu-id="3a5f0-219">Los valores mayores o iguales que 10 se muestran con un fondo verde, los valores entre 1 y 9 se muestran con un fondo azul, y los valores menores que 1 se muestran con un fondo rojo.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-219">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, and less than 1 display with a red background.</span></span>  

-   <span data-ttu-id="3a5f0-220">Otra forma de obtener la misma funcionalidad es con la función `Switch`.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-220">A different way to get the same functionality uses the `Switch` function.</span></span> <span data-ttu-id="3a5f0-221">La función `Switch` resulta de gran utilidad cuando se necesita probar tres condiciones o más.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-221">The `Switch` function is useful when you have three or more conditions to test.</span></span> <span data-ttu-id="3a5f0-222">La función `Switch` devuelve el valor asociado a la primera expresión en una serie que se evalúa como TRUE:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-222">The `Switch` function returns the value associated with the first expression in a series that evaluates to true:</span></span>  

```  
=Switch(Fields!PctComplete.Value >= 10, "Green", Fields!PctComplete.Value >= 1, "Blue", Fields!PctComplete.Value = 1, "Yellow", Fields!PctComplete.Value <= 0, "Red",)  
```  

<span data-ttu-id="3a5f0-223">Los valores mayores o iguales que 10 se muestran con un fondo verde, los valores entre 1 y 9 se muestran con un fondo azul, los valores iguales que 1 se muestran con un fondo amarillo, y los valores iguales o menores que 0 se muestran con un fondo rojo.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-223">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, equal to 1 display with a yellow background, and 0 or less display with a red background.</span></span>  

-   <span data-ttu-id="3a5f0-224">Comprueba el valor del campo `ImportantDate` y devuelve "Red" si es superior a una semana o "Blue" en los demás casos.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-224">Test the value of the `ImportantDate` field and return "Red" if it is more than a week old, and "Blue" otherwise.</span></span> <span data-ttu-id="3a5f0-225">Esta expresión puede utilizarse para controlar la propiedad Color de un cuadro de texto en un elemento de informe:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-225">This expression can be used to control the Color property of a text box in a report item:</span></span>  

```  
=IIF(DateDiff("d",Fields!ImportantDate.Value, Now())>7,"Red","Blue")  
```  

-   <span data-ttu-id="3a5f0-226">Comprueba el valor del campo `PhoneNumber` y devuelve "No value" si es un valor `null` (`Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]); en caso contrario, devuelve el valor del número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-226">Test the value of the `PhoneNumber` field and return "No Value" if it is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]); otherwise return the phone number value.</span></span> <span data-ttu-id="3a5f0-227">Esta expresión puede utilizarse para controlar el valor de un cuadro de texto en un elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-227">This expression can be used to control the value of a text box in a report item.</span></span>  

```  
=IIF(Fields!PhoneNumber.Value Is Nothing,"No Value",Fields!PhoneNumber.Value)  
```  

-   <span data-ttu-id="3a5f0-228">Comprueba el valor del campo `Department` y devuelve un nombre de subinforme o un valor `null` (`Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-228">Test the value of the `Department` field and return either a subreport name or a `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="3a5f0-229">Esta expresión puede utilizarse con subinformes detallados condicionales.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-229">This expression can be used for conditional drillthrough subreports.</span></span>  

```  
=IIF(Fields!Department.Value = "Development", "EmployeeReport", Nothing)  
```  

-   <span data-ttu-id="3a5f0-230">Comprueba si el valor de un campo es NULL.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-230">Test if a field value is null.</span></span> <span data-ttu-id="3a5f0-231">Esta expresión puede usarse para controlar la propiedad `Hidden` de un elemento de informe de imagen.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-231">This expression can be used to control the `Hidden` property of an image report item.</span></span> <span data-ttu-id="3a5f0-232">En el ejemplo siguiente, la imagen especificada por el campo [LargePhoto] solamente se muestra si el valor del campo es distinto de NULL.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-232">In the following example, the image specified by the field [LargePhoto] is displayed only if the value of the field is not null.</span></span>  

```  
=IIF(IsNothing(Fields!LargePhoto.Value),True,False)  
```  

-   <span data-ttu-id="3a5f0-233">La función `MonthName` devuelve un valor de cadena que contiene el nombre del mes especificado.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-233">The `MonthName` function returns a string value containing the name of the specified month.</span></span> <span data-ttu-id="3a5f0-234">El ejemplo siguiente muestra NA en el campo Month si el campo contiene el valor 0.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-234">The following example displays NA in the Month field when the field contains the value of 0.</span></span>  

```  
IIF(Fields!Month.Value=0,"NA",MonthName(IIF(Fields!Month.Value=0,1,Fields!Month.Value)))  

```  

###  <a name="report-functions"></a><a name="ReportFunctions"></a> <span data-ttu-id="3a5f0-235">Funciones de informe</span><span class="sxs-lookup"><span data-stu-id="3a5f0-235">Report Functions</span></span>  
<span data-ttu-id="3a5f0-236">En una expresión, puede agregar una referencia a las funciones de informe adicionales que manipulan datos de un informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-236">In an expression, you can add a reference to additional report functions that manipulate data in a report.</span></span> <span data-ttu-id="3a5f0-237">En esta sección, se ofrecen ejemplos de dos de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-237">This section provides examples for two of these functions.</span></span> <span data-ttu-id="3a5f0-238">Para más información sobre las funciones de informes y ejemplos, vea [Referencia a las funciones de agregado &#40;Generador de informes y SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-238">For more information about report functions and examples, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  

#####  <a name="sum"></a><a name="Sum"></a><span data-ttu-id="3a5f0-239">Sume</span><span class="sxs-lookup"><span data-stu-id="3a5f0-239">Sum</span></span>  

-   <span data-ttu-id="3a5f0-240">La función `Sum` puede calcular el total de los valores de un grupo o de una región de datos.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-240">The `Sum` function can total the values in a group or data region.</span></span> <span data-ttu-id="3a5f0-241">Esta función puede resultar útil en el encabezado o en el pie de página de un grupo.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-241">This function can be useful in the header or footer of a group.</span></span> <span data-ttu-id="3a5f0-242">La expresión siguiente muestra la suma de los datos del grupo o de la región de datos Order:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-242">The following expression displays the sum of data in the Order group or data region:</span></span>  

```  
=Sum(Fields!LineTotal.Value, "Order")  
```  

-   <span data-ttu-id="3a5f0-243">También puede usar la función `Sum` para calcular agregados condicionales.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-243">You can also use the `Sum` function for conditional aggregate calculations.</span></span> <span data-ttu-id="3a5f0-244">Por ejemplo, si un conjunto de datos tiene un campo denominado State cuyos valores posibles son Not Started, Started y Finished, la expresión siguiente, situada en un encabezado de grupo, calcula la suma de agregados solamente para el valor Finished:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-244">For example, if a dataset has a field that is named State with possible values Not Started, Started, Finished, the following expression, when placed in a group header, calculates the aggregate sum for only the value Finished:</span></span>  

```  
=Sum(IIF(Fields!State.Value = "Finished", 1, 0))  
```  

#####  <a name="rownumber"></a><a name="RowNumber"></a><span data-ttu-id="3a5f0-245">RowNumber</span><span class="sxs-lookup"><span data-stu-id="3a5f0-245">RowNumber</span></span>  

-   <span data-ttu-id="3a5f0-246">La función `RowNumber`, cuando se utiliza en un cuadro de texto de una región de datos, muestra el número de fila de cada instancia del cuadro de texto en que aparece la expresión.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-246">The `RowNumber` function, when used in a text box within a data region, displays the row number for each instance of the text box in which the expression appears.</span></span> <span data-ttu-id="3a5f0-247">Esta función puede ser de utilidad para numerar las filas de una tabla.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-247">This function can be useful to number rows in a table.</span></span> <span data-ttu-id="3a5f0-248">También puede resultar útil para tareas más complejas, como proporcionar saltos de página según el número de filas.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-248">It can also be useful for more complex tasks, such as providing page breaks based on number of rows.</span></span> <span data-ttu-id="3a5f0-249">Para obtener más información, vea [Saltos de página](#PageBreaks) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-249">For more information, see [Page Breaks](#PageBreaks) in this topic.</span></span>  

<span data-ttu-id="3a5f0-250">El ámbito que especifique para `RowNumber` controlará cuándo comienza la nueva numeración.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-250">The scope you specify for `RowNumber` controls when renumbering begins.</span></span> <span data-ttu-id="3a5f0-251">La palabra clave `Nothing` indica que la función empezará a contar desde la primera fila de la región de datos más externa.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-251">The `Nothing` keyword indicates that the function will start counting at the first row in the outermost data region.</span></span> <span data-ttu-id="3a5f0-252">Para empezar a contar en regiones de datos anidadas, utilice el nombre de la región de datos.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-252">To start counting within nested data regions, use the name of the data region.</span></span> <span data-ttu-id="3a5f0-253">Para empezar a contar en un grupo, utilice el nombre del grupo.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-253">To start counting within a group, use the name of the group.</span></span>  

```  
=RowNumber(Nothing)  
```  

##  <a name="appearance-of-report-data"></a><a name="AppearanceofReportData"></a> <span data-ttu-id="3a5f0-254">Apariencia de los datos del informe</span><span class="sxs-lookup"><span data-stu-id="3a5f0-254">Appearance of Report Data</span></span>  
<span data-ttu-id="3a5f0-255">Pueden utilizarse expresiones para manipular la apariencia de los datos en el informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-255">You can use expressions to manipulate how data appears on a report.</span></span> <span data-ttu-id="3a5f0-256">Por ejemplo, se pueden mostrar los valores de dos campos en un solo cuadro de texto, se puede mostrar información acerca del informe o se puede influir en el modo en que se insertan los saltos de página en el informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-256">For example, you can display the values of two fields in a single text box, display information about the report, or affect how page breaks are inserted in the report.</span></span>  

###  <a name="page-headers-and-footers"></a><a name="PageHeadersandFooters"></a><span data-ttu-id="3a5f0-257">Encabezados y pies de página</span><span class="sxs-lookup"><span data-stu-id="3a5f0-257">Page Headers and Footers</span></span>  
<span data-ttu-id="3a5f0-258">Cuando se diseña un informe, existe la posibilidad de mostrar el nombre del informe y el número de página en el pie del informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-258">When designing a report, you may want to display the name of the report and page number in the report footer.</span></span> <span data-ttu-id="3a5f0-259">Para ello, se utilizan las siguientes expresiones:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-259">To do this, you can use the following expressions:</span></span>  

-   <span data-ttu-id="3a5f0-260">La siguiente expresión proporciona el nombre del informe y la hora a la que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-260">The following expression provides the name of the report and the time it was run.</span></span> <span data-ttu-id="3a5f0-261">Puede colocarse en un cuadro de texto en el pie de página o en el cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-261">It can be placed in a text box in the report footer or in the body of the report.</span></span> <span data-ttu-id="3a5f0-262">A la hora se le aplica formato con la cadena de formato de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para fechas cortas:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-262">The time is formatted with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] formatting string for short date:</span></span>  

```  
=Globals.ReportName & ", dated " & Format(Globals.ExecutionTime, "d")  
```  

-   <span data-ttu-id="3a5f0-263">La siguiente expresión, situada en un cuadro de texto en el pie de página de un informe, devuelve el número de página y el total de páginas del informe:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-263">The following expression, placed in a text box in the footer of a report, provides page number and total pages in the report:</span></span>  

```  
=Globals.PageNumber & " of " & Globals.TotalPages  
```  

<span data-ttu-id="3a5f0-264">En los ejemplos siguientes, se indica cómo mostrar el primer y el último valor de una página en el encabezado de página, de manera similar a lo que aparece en una lista de directorios.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-264">The following examples describe how to display the first and last values from a page in the page header, similar to what you might find in a directory listing.</span></span> <span data-ttu-id="3a5f0-265">En el ejemplo se supone que existe una región de datos que contiene un cuadro de texto denominado `LastName`.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-265">The example assumes a data region that contains a text box named `LastName`.</span></span>  

-   <span data-ttu-id="3a5f0-266">La siguiente expresión, situada en un cuadro de texto a la izquierda del encabezado de página, proporciona el primer valor del cuadro de texto `LastName` en la página:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-266">The following expression, placed in a text box on the left side of the page header, provides the first value of the `LastName` text box on the page:</span></span>  

```  
=First(ReportItems("LastName").Value)  
```  

-   <span data-ttu-id="3a5f0-267">La expresión siguiente, situada en un cuadro de texto a la derecha del encabezado de página, proporciona el último valor del cuadro de texto `LastName` de la página:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-267">The following expression, placed in a text box on the right side of the page header, provides the last value of the `LastName` text box on the page:</span></span>  

```  
=Last(ReportItems("LastName").Value)  
```  

<span data-ttu-id="3a5f0-268">En el ejemplo siguiente, se indica cómo incluir un total para la página.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-268">The following example describes how to display a page total.</span></span> <span data-ttu-id="3a5f0-269">En el ejemplo se supone que existe una región de datos que contiene un cuadro de texto denominado `Cost`.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-269">The example assumes a data region that contains a text box named `Cost`.</span></span>  

-   <span data-ttu-id="3a5f0-270">La siguiente expresión, situada en el encabezado o pie de página, proporciona la suma de los valores del cuadro de texto `Cost` para la página:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-270">The following expression, placed in the page header or footer, provides the sum of the values in the `Cost` text box for the page:</span></span>  

```  
=Sum(ReportItems("Cost").Value)  
```  

> [!NOTE]  
>  <span data-ttu-id="3a5f0-271">Solamente puede hacerse referencia a un elemento de informe por expresión en un encabezado o pie de página.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-271">You can refer to only one report item per expression in a page header or footer.</span></span> <span data-ttu-id="3a5f0-272">Asimismo, puede hacer referencia al nombre del cuadro de texto, pero no a la expresión de datos real del cuadro de texto, en expresiones de encabezado y de pie de página.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-272">Also, you can refer to the text box name, but not the actual data expression within the text box, in page header and footer expressions.</span></span>  

###  <a name="page-breaks"></a><a name="PageBreaks"></a> <span data-ttu-id="3a5f0-273">Saltos de página</span><span class="sxs-lookup"><span data-stu-id="3a5f0-273">Page Breaks</span></span>  
<span data-ttu-id="3a5f0-274">Es posible que en algunos informes se desee insertar un salto de página al final de un número de filas determinado, en lugar de (o además de) en los grupos o elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-274">In some reports, you may want to place a page break at the end of a specified number of rows instead of, or in addition to, on groups or report items.</span></span> <span data-ttu-id="3a5f0-275">Para ello, cree un grupo que contenga los grupos o registros de detalle que desee, agregue un salto de página al grupo y, a continuación, agregue una expresión de grupo para agrupar por un número concreto de filas.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-275">To do this, create a group that contains the groups or detail records you want, add a page break to the group, and then add a group expression to group by a specified number of rows.</span></span>  

-   <span data-ttu-id="3a5f0-276">Si se coloca la expresión siguiente en la expresión de grupo, se asigna un número a cada conjunto de 25 filas.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-276">The following expression, when placed in the group expression, assigns a number to each set of 25 rows.</span></span> <span data-ttu-id="3a5f0-277">Cuando se define un salto de página para el grupo, el resultado de la expresión es un salto de página cada 25 filas.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-277">When a page break is defined for the group, this expression results in a page break every 25 rows.</span></span>  

```  
=Ceiling(RowNumber(Nothing)/25)  
```  

<span data-ttu-id="3a5f0-278">Para permitir al usuario establecer un valor para el número de filas por página, cree un parámetro denominado `RowsPerPage` y base la expresión de grupo en dicho parámetro, tal y como se muestra en la expresión siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-278">To allow the user to set a value for the number of rows per page, create a parameter named `RowsPerPage` and base the group expression on the parameter, as shown in the following expression:</span></span>  

```  
=Ceiling(RowNumber(Nothing)/Parameters!RowsPerPage.Value)  
```  

<span data-ttu-id="3a5f0-279">Para más información sobre cómo configurar saltos de página para un grupo, vea [Agregar un salto de página &#40;Generador de informes y SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-279">For more information about setting page breaks for a group, see [Add a Page Break &#40;Report Builder and SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span></span>  

##  <a name="properties"></a><a name="Properties"></a> <span data-ttu-id="3a5f0-280">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3a5f0-280">Properties</span></span>  
<span data-ttu-id="3a5f0-281">Las expresiones no se utilizan únicamente para mostrar datos en cuadros de texto.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-281">Expressions are not only used to display data in text boxes.</span></span> <span data-ttu-id="3a5f0-282">También se pueden utilizar para cambiar el modo en que se aplican las propiedades a los elementos de informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-282">They can also be used to change how properties are applied to report items.</span></span> <span data-ttu-id="3a5f0-283">Es posible cambiar la información de estilo de un elemento de informe o modificar su visibilidad.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-283">You can change style information for a report item, or change its visibility.</span></span>  

###  <a name="formatting"></a><a name="Formatting"></a><span data-ttu-id="3a5f0-284">Formato</span><span class="sxs-lookup"><span data-stu-id="3a5f0-284">Formatting</span></span>  

-   <span data-ttu-id="3a5f0-285">La expresión siguiente, cuando se usa en la propiedad Color de un cuadro de texto, cambia el color del texto según el valor del campo `Profit` :</span><span class="sxs-lookup"><span data-stu-id="3a5f0-285">The following expression, when used in the Color property of a text box, changes the color of the text depending on the value of the `Profit` field:</span></span>  

```  
=Iif(Fields!Profit.Value < 0, "Red", "Black")  
```  

<span data-ttu-id="3a5f0-286">También puede usar la variable de objeto [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] de `Me`.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-286">You can also use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] object variable `Me`.</span></span> <span data-ttu-id="3a5f0-287">Esta variable es otra manera de hacer referencia al valor de un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-287">This variable is another way of referring to the value of a text box.</span></span>  

`=Iif(Me.Value < 0, "Red", "Black")`  

-   <span data-ttu-id="3a5f0-288">La siguiente expresión, cuando se usa en la propiedad BackgroundColor de un elemento de informe en una región de datos, cambia el color de fondo de cada fila entre verde pálido y blanco:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-288">The following expression, when used in the BackgroundColor property of a report item in a data region, alternates the background color of each row between pale green and white:</span></span>  

```  
=Iif(RowNumber(Nothing) Mod 2, "PaleGreen", "White")  
```  

<span data-ttu-id="3a5f0-289">Si se utiliza una expresión para un ámbito determinado, puede que sea necesario indicar el conjunto de datos para la función de agregado:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-289">If you are using an expression for a specified scope, you may have to indicate the dataset for the aggregate function:</span></span>  

```  
=Iif(RowNumber("Employees") Mod 2, "PaleGreen", "White")  
```  

> [!NOTE]  
>  <span data-ttu-id="3a5f0-290">Los colores disponibles se obtienen de la enumeración KnownColor de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a5f0-290">Available colors come from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] KnownColor enumeration.</span></span>  

### <a name="chart-colors"></a><span data-ttu-id="3a5f0-291">Colores del gráfico</span><span class="sxs-lookup"><span data-stu-id="3a5f0-291">Chart Colors</span></span>  
<span data-ttu-id="3a5f0-292">Para especificar los colores de un gráfico de formas, puede usar código personalizado que le permita controlar el orden en que los colores se asignan a los valores de los puntos de datos.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-292">To specify colors for a Shape chart, you can use custom code to control the order that colors are mapped to data point values.</span></span> <span data-ttu-id="3a5f0-293">Esto le permitirá usar colores coherentes para varios gráficos que tienen los mismos grupos de categorías.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-293">This helps you use consistent colors for multiple charts that have the same category groups.</span></span> <span data-ttu-id="3a5f0-294">Para más información, vea [Especificar colores uniformes en varios gráficos de formas &#40;Generador de informes y SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-294">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  

###  <a name="visibility"></a><a name="Visibility"></a><span data-ttu-id="3a5f0-295">Visibilidad</span><span class="sxs-lookup"><span data-stu-id="3a5f0-295">Visibility</span></span>  
<span data-ttu-id="3a5f0-296">Es posible mostrar y ocultar los elementos de un informe mediante las propiedades de visibilidad del elemento de informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-296">You can show and hide items in a report using the visibility properties for the report item.</span></span> <span data-ttu-id="3a5f0-297">En una región de datos, como una tabla, se pueden ocultar inicialmente las filas de detalles basándose en el valor de una expresión.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-297">In a data region such as a table, you can initially hide detail rows based on the value in an expression.</span></span>  

-   <span data-ttu-id="3a5f0-298">La expresión siguiente, cuando se utiliza para la visibilidad inicial de las filas de detalles de un grupo, muestra las filas de detalles de todas las ventas que superen el 90 por ciento en el campo `PctQuota` :</span><span class="sxs-lookup"><span data-stu-id="3a5f0-298">The following expression, when used for initial visibility of detail rows in a group, shows the detail rows for all sales exceeding 90 percent in the `PctQuota` field:</span></span>  

```  
=Iif(Fields!PctQuota.Value>.9, False, True)  
```  

-   <span data-ttu-id="3a5f0-299">La expresión siguiente, cuando se establece en la propiedad Hidden de una tabla, muestra la tabla solo si tiene más de 12 filas:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-299">The following expression, when set in the Hidden property of a table, shows the table only if it has more than 12 rows:</span></span>  

```  
=IIF(CountRows()>12,false,true)  
```  

-   <span data-ttu-id="3a5f0-300">La siguiente expresión, cuando se establece en la `Hidden` propiedad de una columna, muestra la columna solo si el campo existe en el conjunto de datos de informe después de que se recuperen los datos del origen de datos:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-300">The following expression, when set in the `Hidden` property of a column, shows the column only if the field exists in the report dataset after the data is retrieved from the data source:</span></span>  

```  
=IIF(Fields!Column_1.IsMissing, true, false)  
```  

###  <a name="urls"></a><a name="Hyperlinks"></a><span data-ttu-id="3a5f0-301">URL</span><span class="sxs-lookup"><span data-stu-id="3a5f0-301">URLs</span></span>  
<span data-ttu-id="3a5f0-302">Puede personalizar direcciones URL con los datos de informe y, además, controlar de manera condicional si las dichas direcciones URL se agregan como acciones para un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-302">You can customize URLs by using report data and also conditionally control whether URLs are added as an action for a text box.</span></span>  

-   <span data-ttu-id="3a5f0-303">La expresión siguiente, cuando se usa como acción en un cuadro de texto, genera una dirección URL personalizada que especifica el campo `EmployeeID` del conjunto de datos como parámetro de URL.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-303">The following expression, when used as an action on a text box, generates a customized URL that specifies the dataset field `EmployeeID` as a URL parameter.</span></span>  

```  
="http://adventure-works/MyInfo?ID=" & Fields!EmployeeID.Value  
```  

<span data-ttu-id="3a5f0-304">Para más información, vea [Agregar un hipervínculo a una dirección URL &#40;Generador de informes y SSRS&#41;](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-304">For more information, see [Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span></span>  

-   <span data-ttu-id="3a5f0-305">La expresión siguiente controla de forma condicional si debe agregarse una dirección URL a un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-305">The following expression conditionally controls whether to add a URL in a text box.</span></span> <span data-ttu-id="3a5f0-306">Esta expresión depende de un parámetro denominado `IncludeURLs` que permite a un usuario decidir si deben incluirse direcciones URL activas en un informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-306">This expression depends on a parameter named `IncludeURLs` that allows a user to decide whether to include active URLs in a report.</span></span> <span data-ttu-id="3a5f0-307">Esta expresión se establece como acción en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-307">This expression is set as an action on a text box.</span></span> <span data-ttu-id="3a5f0-308">Si se establece el parámetro en FALSE y, a continuación, se visualiza el informe, puede exportar el informe a Microsoft Excel sin hipervínculos.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-308">By setting the parameter to False and then viewing the report, you can export the report Microsoft Excel without hyperlinks.</span></span>  

```  
=IIF(Parameters!IncludeURLs.Value,"http://adventure-works.com/productcatalog",Nothing)  
```  

##  <a name="report-data"></a><a name="ReportData"></a><span data-ttu-id="3a5f0-309">Datos de informe</span><span class="sxs-lookup"><span data-stu-id="3a5f0-309">Report Data</span></span>  
<span data-ttu-id="3a5f0-310">Pueden utilizarse expresiones para manipular los datos que se usan en el informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-310">Expressions can be used to manipulate the data that is used in the report.</span></span> <span data-ttu-id="3a5f0-311">Se puede hacer referencia a parámetros y a otra información del informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-311">You can refer to parameters and other report information.</span></span> <span data-ttu-id="3a5f0-312">Incluso se puede modificar la consulta que se usa para recuperar datos para el informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-312">You can even change the query that is used to retrieve data for the report.</span></span>  

###  <a name="parameters"></a><a name="Parameters"></a> <span data-ttu-id="3a5f0-313">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a5f0-313">Parameters</span></span>  
<span data-ttu-id="3a5f0-314">Pueden utilizarse expresiones en un parámetro para modificar su valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-314">You can use expressions in a parameter to vary the default value for the parameter.</span></span> <span data-ttu-id="3a5f0-315">Por ejemplo, puede usar un parámetro que filtre datos para un usuario determinado basándose en el identificador de usuario con el que se ejecuta el informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-315">For example, you can use a parameter to filter data to a particular user based on the user ID that is used to run the report.</span></span>  

-   <span data-ttu-id="3a5f0-316">La siguiente expresión, cuando se usa como valor predeterminado para un parámetro, obtiene el identificador de usuario de la persona que ejecuta el informe:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-316">The following expression, when used as the default value for a parameter, collects the user ID of the person running the report:</span></span>  

```  
=User!UserID  
```  

-   <span data-ttu-id="3a5f0-317">Para hacer referencia a un parámetro en un parámetro de consulta, una expresión de filtro, un cuadro de texto u otras áreas del informe, use la colección global `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-317">To refer to a parameter in a query parameter, filter expression, text box, or other area of the report, use the `Parameters` global collection.</span></span> <span data-ttu-id="3a5f0-318">En este ejemplo se da por supuesto que el parámetro se denomina *Department*:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-318">This example assumes that the parameter is named *Department*:</span></span>  

```  
=Parameters!Department.Value  
```  

-   <span data-ttu-id="3a5f0-319">Pueden crearse parámetros en un informe y establecerse como ocultos.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-319">Parameters can be created in a report but set to hidden.</span></span> <span data-ttu-id="3a5f0-320">Cuando se ejecuta el informe en el servidor de informes, el parámetro no se muestra en la barra de herramientas y el lector del informe no puede cambiar el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-320">When the report runs on the report server, the parameter does not appear in the toolbar and the report reader cannot change the default value.</span></span> <span data-ttu-id="3a5f0-321">Puede usar un parámetro oculto establecido en un valor predeterminado como constante personalizada.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-321">You can use a hidden parameter set to a default value as custom constant.</span></span> <span data-ttu-id="3a5f0-322">Puede usar este valor en cualquier expresión, incluida una expresión de campo.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-322">You can use this value in any expression, including a field expression.</span></span> <span data-ttu-id="3a5f0-323">La expresión siguiente identifica el campo especificado por el valor de parámetro predeterminado para el parámetro denominado *ParameterField*:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-323">The following expression identifies the field specified by the default parameter value for the parameter named *ParameterField*:</span></span>  

```  
=Fields(Parameters!ParameterField.Value).Value  
```  

## <a name="custom-code"></a><a name="CustomCode"></a><span data-ttu-id="3a5f0-324">Código personalizado</span><span class="sxs-lookup"><span data-stu-id="3a5f0-324">Custom Code</span></span>

<span data-ttu-id="3a5f0-325">En un informe, puede utilizarse código personalizado.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-325">You can use custom code in a report.</span></span> <span data-ttu-id="3a5f0-326">El código personalizado puede incrustarse en el informe o puede almacenarse en un ensamblado personalizado que se utilice en el informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-326">Custom code is either embedded in a report or stored in a custom assembly which is used in the report.</span></span> <span data-ttu-id="3a5f0-327">Para más información sobre código personalizado, vea [Referencias a ensamblados y código personalizado en expresiones en el Diseñador de informes &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-327">For more information about custom code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  

### <a name="using-group-variables-for-custom-aggregation"></a><span data-ttu-id="3a5f0-328">Usar variables de grupo para agregación personalizada</span><span class="sxs-lookup"><span data-stu-id="3a5f0-328">Using Group Variables for Custom Aggregation</span></span>

<span data-ttu-id="3a5f0-329">Puede inicializar el valor de una variable de grupo local en un ámbito de grupo determinado y, a continuación, incluir una referencia a esa variable en expresiones.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-329">You can initialize the value for a group variable that is local to a particular group scope and then include a reference to that variable in expressions.</span></span> <span data-ttu-id="3a5f0-330">Una forma de usar una variable de grupo con código personalizado es implementar un agregado personalizado.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-330">One of the ways that you can use a group variable with custom code is to implement a custom aggregate.</span></span> <span data-ttu-id="3a5f0-331">Para obtener más información, vea [Usar variables de grupo en Reporting Services 2008 para agregados personalizados (en inglés)](https://go.microsoft.com/fwlink/?LinkId=128714).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-331">For more information, see [Using Group Variables in Reporting Services 2008 for Custom Aggregation](https://go.microsoft.com/fwlink/?LinkId=128714).</span></span>  

<span data-ttu-id="3a5f0-332">Para más información sobre variables, vea [Referencias a las colecciones de variables de informe y de grupo &#40;Generador de informes y SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-332">For more information about variables, see [Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md).</span></span>  

## <a name="suppressing-null-or-zero-values-at-run-time"></a><span data-ttu-id="3a5f0-333">Suprimir valores NULL o valores cero en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="3a5f0-333">Suppressing Null or Zero Values at Run Time</span></span>

<span data-ttu-id="3a5f0-334">Algunos valores de una expresión pueden evaluarse como NULL o como indefinidos durante el procesamiento del informe.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-334">Some values in an expression can evaluate to null or undefined at report processing time.</span></span> <span data-ttu-id="3a5f0-335">Esto puede provocar errores en tiempo de ejecución que hacen que en el cuadro de texto se muestre **#Error** en lugar de la expresión evaluada.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-335">This can create run-time errors that result in **#Error** displaying in the text box instead of the evaluated expression.</span></span> <span data-ttu-id="3a5f0-336">La función `IIF` es especialmente sensible a este comportamiento porque, a diferencia de lo que ocurre en una instrucción If-Then-Else, se evalúa cada una de las partes de la instrucción `IIF` (incluidas las llamadas a función) antes de que se pasen a la rutina que comprueba si es `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-336">The `IIF` function is particularly sensitive to this behavior because, unlike an If-Then-Else statement, each part of the `IIF` statement is evaluated (including function calls) before being passed to the routine that tests for `true` or `false`.</span></span> <span data-ttu-id="3a5f0-337">La instrucción `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` genera **#Error** en el informe representado si el valor de `Fields!Sales.Value` es NOTHING.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-337">The statement `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` generates **#Error** in the rendered report if `Fields!Sales.Value` is NOTHING.</span></span>  

<span data-ttu-id="3a5f0-338">Para evitar esta condición, use una de las estrategias siguientes:</span><span class="sxs-lookup"><span data-stu-id="3a5f0-338">To avoid this condition, use one of the following strategies:</span></span>  

-   <span data-ttu-id="3a5f0-339">Establezca el numerador en 0 y el denominador en 1 si el valor del campo B es 0 o un valor no definido; en caso contrario, establezca el numerador en el valor del campo A y el denominador en el valor del campo B.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-339">Set the numerator to 0 and the denominator to 1 if the value for field B is 0 or undefined; otherwise, set the numerator to the value for field A and the denominator to the value for field B.</span></span>  

```  
=IIF(Field!B.Value=0, 0, Field!A.Value / IIF(Field!B.Value =0, 1, Field!B.Value))  
```  

-   <span data-ttu-id="3a5f0-340">Use una función de código personalizado para devolver el valor de la expresión.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-340">Use a custom code function to return the value for the expression.</span></span> <span data-ttu-id="3a5f0-341">En el ejemplo siguiente, se devuelve la diferencia porcentual entre un valor actual y un valor anterior.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-341">The following example returns the percentage difference between a current value and a previous value.</span></span> <span data-ttu-id="3a5f0-342">Esto puede usarse para calcular la diferencia entre dos valores consecutivos cualesquiera, y controla el caso extremo de la primera comparación (cuando no hay ningún valor anterior) y los casos en los que el valor anterior o el valor actual es `null` (`Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-342">This can be used to calculate the difference between any two successive values and it handles the edge case of the first comparison (when there is no previous value) and cases whether either the previous value or the current value is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  

```  
Public Function GetDeltaPercentage(ByVal PreviousValue, ByVal CurrentValue) As Object  
     If IsNothing(PreviousValue) OR IsNothing(CurrentValue) Then  
          Return Nothing  
     Else if PreviousValue = 0 OR CurrentValue = 0 Then  
          Return Nothing  
     Else
          Return (CurrentValue - PreviousValue) / CurrentValue  
     End If  
End Function  
```  

<span data-ttu-id="3a5f0-343">En la expresión siguiente se muestra cómo llamar a este código personalizado desde un cuadro de texto, para el contenedor "ColumnGroupByYear" (grupo o región de datos).</span><span class="sxs-lookup"><span data-stu-id="3a5f0-343">The following expression shows how to call this custom code from a text box, for the "ColumnGroupByYear" container (group or data region).</span></span>  

```  
=Code.GetDeltaPercentage(Previous(Sum(Fields!Sales.Value),"ColumnGroupByYear"), Sum(Fields!Sales.Value))  
```  

<span data-ttu-id="3a5f0-344">Esto ayuda a evitar excepciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-344">This helps to avoid run-time exceptions.</span></span> <span data-ttu-id="3a5f0-345">Ahora puede utilizar una expresión como `=IIF(Me.Value < 0, "red", "black")` en la propiedad `Color` del cuadro de texto para condicionalmente el texto para mostrar basándose en si los valores son mayores o menores que 0.</span><span class="sxs-lookup"><span data-stu-id="3a5f0-345">You can now use an expression like `=IIF(Me.Value < 0, "red", "black")` in the `Color` property of the text box to conditionally the display text based on whether the values are greater than or less than 0.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3a5f0-346">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3a5f0-346">See Also</span></span>

- [<span data-ttu-id="3a5f0-347">Ejemplos de ecuaciones de filtro &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a5f0-347">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="3a5f0-348">Ejemplos de expresión de grupo &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a5f0-348">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="3a5f0-349">Usar expresiones en informes &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a5f0-349">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)
- [<span data-ttu-id="3a5f0-350">Expresiones &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a5f0-350">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)
- [<span data-ttu-id="3a5f0-351">Filtros de uso frecuente &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3a5f0-351">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)