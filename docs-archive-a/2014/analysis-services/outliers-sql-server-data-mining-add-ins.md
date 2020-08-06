---
title: Valores atípicos (SQL Server complementos de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- exceptions [data mining]
- data preparation
- outliers [data mining]
- data cleaning
ms.assetid: e6fa7c62-4005-4792-9211-3b699377a517
author: minewiskan
ms.author: owend
ms.openlocfilehash: 92dddf3338d15e700576a13476ee364696bfd274
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752433"
---
# <a name="outliers-sql-server-data-mining-add-ins"></a><span data-ttu-id="91705-102">Valores atípicos (Complementos de minería de datos de SQL Server)</span><span class="sxs-lookup"><span data-stu-id="91705-102">Outliers (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="91705-103">![Asistente para quitar valores atípicos, cinta de opciones Minería de datos](media/dmc-outliers.gif "Asistente para quitar valores atípicos, cinta de opciones Minería de datos")</span><span class="sxs-lookup"><span data-stu-id="91705-103">![Outliers wizard in Data Mining ribbon](media/dmc-outliers.gif "Outliers wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="91705-104">Un valor *atípico* significa un valor de datos que es problemático por cualquiera de los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="91705-104">An *outlier* means a data value that is problematic for any one of the following reasons:</span></span>  
  
-   <span data-ttu-id="91705-105">El valor está fuera del intervalo esperado.</span><span class="sxs-lookup"><span data-stu-id="91705-105">Value is outside the expected range.</span></span>  
  
-   <span data-ttu-id="91705-106">Es posible que los datos se hayan especificado de forma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="91705-106">Data might have been entered incorrectly.</span></span>  
  
-   <span data-ttu-id="91705-107">El valor es un valor ausente.</span><span class="sxs-lookup"><span data-stu-id="91705-107">Value is missing.</span></span>  
  
-   <span data-ttu-id="91705-108">Los datos consisten en un espacio u otra cadena de tipo NULL.</span><span class="sxs-lookup"><span data-stu-id="91705-108">Data consists of a space or other null string.</span></span>  
  
-   <span data-ttu-id="91705-109">El valor es preciso pero está tan alejado de la distribución que puede afectar significativamente al modelo.</span><span class="sxs-lookup"><span data-stu-id="91705-109">Value is accurate, but is so far outside the distribution that it can significantly affect the model.</span></span>  
  
 <span data-ttu-id="91705-110">El Cliente de minería de datos para Excel le ayuda a detectar estos datos y a actualizar los valores o a suprimirlos.</span><span class="sxs-lookup"><span data-stu-id="91705-110">The Data Mining Client for Excel helps you detect this data, and then update the values or suppress them.</span></span> <span data-ttu-id="91705-111">Por ejemplo, puede reemplazar los valores atípicos por una media aritmética o puede eliminar las filas que sean susceptibles de contener valores erróneos.</span><span class="sxs-lookup"><span data-stu-id="91705-111">For example, you can replace outliers with an arithmetic mean, or you can delete rows that contain potentially wrong values.</span></span>  
  
## <a name="handling-outliers"></a><span data-ttu-id="91705-112">Tratar los valores atípicos</span><span class="sxs-lookup"><span data-stu-id="91705-112">Handling Outliers</span></span>  
 <span data-ttu-id="91705-113">El Asistente para **quitar valores atípicos** ofrece varias herramientas para administrar los valores atípicos de forma adecuada:</span><span class="sxs-lookup"><span data-stu-id="91705-113">The **Remove Outliers** wizard gives you several tools to handle outliers appropriately:</span></span>  
  
-   <span data-ttu-id="91705-114">Primero, puede explorar los datos para entender mejor la distribución de los valores y la relación de los valores atípicos con los otros datos.</span><span class="sxs-lookup"><span data-stu-id="91705-114">First, you can explore the data to better understand the distribution of values and the relationship of the outliers to other data.</span></span>  
  
     <span data-ttu-id="91705-115">Por ejemplo, puede usar la tarea **explorar datos** para revisar y corregir los valores.</span><span class="sxs-lookup"><span data-stu-id="91705-115">For example, you can use the **Explore Data** task to review and fix the values.</span></span> <span data-ttu-id="91705-116">El Asistente para **quitar valores atípicos** también muestra un gráfico, ya sea un gráfico de líneas o de barras, para ayudarle a entender la distribución de todos los valores.</span><span class="sxs-lookup"><span data-stu-id="91705-116">The **Remove Outliers** wizard also displays a graph, either a line or a bar chart, to help you understand the distribution of all values.</span></span>  
  
-   <span data-ttu-id="91705-117">A continuación, puede usar el asistente **valores atípicos** para quitar o cambiar valores atípicos.</span><span class="sxs-lookup"><span data-stu-id="91705-117">Next, you can use the **Outliers** wizard to remove or change outliers.</span></span> <span data-ttu-id="91705-118">El método que use dependerá de si los valores son discretos o continuos.</span><span class="sxs-lookup"><span data-stu-id="91705-118">The method that you use depends on whether the values are discrete or continuous.</span></span>  
  
     <span data-ttu-id="91705-119">El asistente muestra los valores discretos en un gráfico de barras, donde cada barra representa un valor concreto y el alto de la barra indica el número de casos para cada valor.</span><span class="sxs-lookup"><span data-stu-id="91705-119">The wizard displays discrete values in a bar chart, where each bar represents a specific value, and the height of the bar indicates the number of cases for each value.</span></span> <span data-ttu-id="91705-120">Deslizando el control de umbral en el gráfico, puede cortar barras que representen grupos de valores extremos o potencialmente erróneos.</span><span class="sxs-lookup"><span data-stu-id="91705-120">By sliding the threshold control on the chart, you can cut off bars that represent groups of extreme or potentially bad values.</span></span>  
  
-   <span data-ttu-id="91705-121">El asistente muestra los valores continuos en un gráfico de barras o en un gráfico de líneas.</span><span class="sxs-lookup"><span data-stu-id="91705-121">The wizard displays continuous values either on a bar chart or line chart.</span></span> <span data-ttu-id="91705-122">En el gráfico de líneas, el valor está representado en el eje X y el recuento de los valores en el eje Y.</span><span class="sxs-lookup"><span data-stu-id="91705-122">On the line chart, the value is represented on the x-axis and the count of values on the y-axis.</span></span>  
  
     <span data-ttu-id="91705-123">Puede controlar si desea quitar o mantener los valores de los extremos inferior y superior del gráfico cambiando los valores **mínimo** y **máximo** , o deslizando las barras.</span><span class="sxs-lookup"><span data-stu-id="91705-123">You can control whether to remove or keep values at the low and high ends of the chart by changing the **Minimum** and **Maximum** values, or sliding the bars.</span></span> <span data-ttu-id="91705-124">Cuando se cambia la configuración de valor mínimo y máximo, los datos que se van a eliminar se muestran con un sombreado en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="91705-124">As you change the minimum and maximum value settings, the data that will be suppressed is shown by shading in the graph.</span></span>  
  
 <span data-ttu-id="91705-125">Una vez seleccionados los valores atípicos con los que va a trabajar, debe indicar al asistente cómo tiene que tratar dichos valores.</span><span class="sxs-lookup"><span data-stu-id="91705-125">After you have selected which outliers to work with, you tell the wizard how to handle the outliers.</span></span> <span data-ttu-id="91705-126">Puede eliminar las filas que contienen los valores atípicos o puede especificar un valor de reemplazo, como un valor promedio, un valor NULL u otro valor de su elección.</span><span class="sxs-lookup"><span data-stu-id="91705-126">You can either delete the rows that contain the outlier values, or you can specify a replacement value, such as a mean, a null, or another value of your choice.</span></span>  
  
 <span data-ttu-id="91705-127">Finalmente, el asistente le da algunas opciones para mostrar los nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="91705-127">Finally, the wizard gives you some options for displaying the new data.</span></span> <span data-ttu-id="91705-128">Puede reemplazar los datos originales por valores nuevos, agregar a la tabla una nueva columna que contenga los nuevos valores, o crear una nueva hoja de cálculo que contenga los datos actualizados.</span><span class="sxs-lookup"><span data-stu-id="91705-128">You can replace the original data with the new values, add a new column to the table that contains the new values, or create a new worksheet that contains the updated data.</span></span>  
  
### <a name="using-the-outlier-wizard"></a><span data-ttu-id="91705-129">Usar el Asistente para quitar valores atípicos</span><span class="sxs-lookup"><span data-stu-id="91705-129">Using the Outlier Wizard</span></span>  
  
1.  <span data-ttu-id="91705-130">En la cinta de opciones **minería de datos** , haga clic en **limpiar datos**y seleccione **valores atípicos**.</span><span class="sxs-lookup"><span data-stu-id="91705-130">In the **Data Mining** ribbon, click **Clean Data**, and select **Outliers**.</span></span>  
  
2.  <span data-ttu-id="91705-131">En el cuadro de diálogo **seleccionar datos de origen** , seleccione una tabla de datos de Excel o un rango de celdas y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="91705-131">In the **Select Source Data** dialog box, select an Excel data table, or a range of cells, and click **Next**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="91705-132">No puede usar el asistente **valores atípicos** en datos externos, a menos que lo copie primero en Excel.</span><span class="sxs-lookup"><span data-stu-id="91705-132">You cannot use the **Outliers** wizard on external data, unless you copy it to Excel first.</span></span>  
  
3.  <span data-ttu-id="91705-133">En el cuadro de diálogo **Seleccionar columna** , seleccione una **sola** columna.</span><span class="sxs-lookup"><span data-stu-id="91705-133">In the **Select Column** dialog box, select a **single** column.</span></span>  
  
     <span data-ttu-id="91705-134">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="91705-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="91705-135">En el cuadro de diálogo **especificar umbrales** , revise la distribución de los datos.</span><span class="sxs-lookup"><span data-stu-id="91705-135">In the **Specify Thresholds** dialog box, review the distribution of data.</span></span>  
  
    -   <span data-ttu-id="91705-136">Si la columna contiene valores discretos, el asistente muestra un histograma que contiene el recuento para cada valor discreto.</span><span class="sxs-lookup"><span data-stu-id="91705-136">If the column contains discrete values, the wizard displays a histogram containing the count for each discrete value.</span></span>  
  
         <span data-ttu-id="91705-137">Suponiendo que los valores atípicos son valores raros, puede filtrarlos cambiando el valor **mínimo** .</span><span class="sxs-lookup"><span data-stu-id="91705-137">Assuming that outliers are rare values, you can filter them out by changing the **Minimum** value.</span></span>  
  
    -   <span data-ttu-id="91705-138">Si la columna contiene datos numéricos, puede hacer clic en el botón **ver como discreto** o en el botón **ver como numérico** para alternar entre ver los valores en un gráfico de barras o en un gráfico de líneas.</span><span class="sxs-lookup"><span data-stu-id="91705-138">If the column contains numeric data, you can click the **View as Discrete** button or the **View as Numeric** button to toggle between viewing the values in a bar chart or line chart.</span></span>  
  
5.  <span data-ttu-id="91705-139">En el cuadro de diálogo **especificar umbrales** , elija el intervalo de datos que desea mantener escribiendo un valor mínimo y máximo, o arrastrando las barras deslizantes.</span><span class="sxs-lookup"><span data-stu-id="91705-139">In the **Specify Thresholds** dialog box, choose the range of data you want to keep by typing a minimum and maximum value, or by dragging the slider bars.</span></span> <span data-ttu-id="91705-140">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="91705-140">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="91705-141">En el cuadro de diálogo **control de valores atípicos** , especifique si desea eliminar o reemplazar los valores y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="91705-141">In the **Outlier Handling** dialog box, specify whether you want the values to be deleted or replaced, and click **Next**.</span></span>  
  
7.  <span data-ttu-id="91705-142">En el cuadro de diálogo **Seleccionar destino** , especifique dónde desea que se guarden los nuevos datos.</span><span class="sxs-lookup"><span data-stu-id="91705-142">In the **Select Destination** dialog box, specify where you want the new data to be saved.</span></span>  
  
### <a name="related-options"></a><span data-ttu-id="91705-143">Opciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="91705-143">Related Options</span></span>  
 <span data-ttu-id="91705-144">El asistente proporciona estas opciones:</span><span class="sxs-lookup"><span data-stu-id="91705-144">The wizard provides these options:</span></span>  
  
|<span data-ttu-id="91705-145">**Opciones**</span><span class="sxs-lookup"><span data-stu-id="91705-145">**Options**</span></span>|<span data-ttu-id="91705-146">**Comentario**</span><span class="sxs-lookup"><span data-stu-id="91705-146">**Comment**</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="91705-147">**Seleccionar columna**</span><span class="sxs-lookup"><span data-stu-id="91705-147">**Select Column**</span></span>|<span data-ttu-id="91705-148">Solo se puede trabajar con una columna cada vez.</span><span class="sxs-lookup"><span data-stu-id="91705-148">You can work with only one column at a time.</span></span>|  
|<span data-ttu-id="91705-149">**Especificar el tratamiento de los umbrales**</span><span class="sxs-lookup"><span data-stu-id="91705-149">**Specify Thresholds Handling**</span></span>|<span data-ttu-id="91705-150">Establezca un umbral usando **mínimo** para excluir los valores que se encuentran en menos filas que el valor de umbral.</span><span class="sxs-lookup"><span data-stu-id="91705-150">Set a threshold using **Minimum** to exclude values that are found in fewer rows than the threshold value.</span></span><br /><br /> <span data-ttu-id="91705-151">Inicialmente, el valor **mínimo** es igual al valor con el menor número de filas y no se puede hacer que el mínimo sea menor que ese valor.</span><span class="sxs-lookup"><span data-stu-id="91705-151">Initially the value in **Minimum** is equal to the value with the fewest rows, and you cannot make the minimum lower than that value.</span></span>|  
|<span data-ttu-id="91705-152">**Tratamiento de valores atípicos**</span><span class="sxs-lookup"><span data-stu-id="91705-152">**Outlier Handling**</span></span>|<span data-ttu-id="91705-153">Si decide eliminar los valores atípicos, puede o cambiar los datos de la hoja de cálculo actual o bien crear una copia de los datos en una nueva hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="91705-153">If you decide to delete outliers, you can either change the data in the current worksheet, or create a copy of the data in a new worksheet.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91705-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91705-154">See Also</span></span>  
 [<span data-ttu-id="91705-155">Explorar datos &#40;SQL Server complementos de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="91705-155">Explore Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](explore-data-sql-server-data-mining-add-ins.md)  
  
  
