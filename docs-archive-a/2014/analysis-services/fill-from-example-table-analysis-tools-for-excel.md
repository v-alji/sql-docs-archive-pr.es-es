---
title: Rellenar a partir de ejemplo (herramientas de análisis de tabla para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- fill from example
ms.assetid: dac57d8f-1c65-4878-8ea0-9c680df5e4fb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 69ff9f554c51240eb6f9151718d30677bfb57996
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746055"
---
# <a name="fill-from-example-table-analysis-tools-for-excel"></a><span data-ttu-id="a723f-102">Rellenar desde ejemplo (Herramientas de análisis de tabla para Excel)</span><span class="sxs-lookup"><span data-stu-id="a723f-102">Fill From Example (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="a723f-103">![Botón Rellenar desde ejemplo, Herramientas de análisis de tabla](media/tat-fillex.gif "Botón Rellenar desde ejemplo, Herramientas de análisis de tabla")</span><span class="sxs-lookup"><span data-stu-id="a723f-103">![Fill From Example button in Table Analysis Tools](media/tat-fillex.gif "Fill From Example button in Table Analysis Tools")</span></span>  
  
 <span data-ttu-id="a723f-104">La herramienta **rellenar desde ejemplo** le ayuda a generar nuevas columnas de datos en función de los valores existentes.</span><span class="sxs-lookup"><span data-stu-id="a723f-104">The **Fill From Example** tool helps you build new columns of data based on existing values.</span></span>  
  
 <span data-ttu-id="a723f-105">Por ejemplo, suponga que los datos contienen una columna de importe de la **compra** , una columna de **cantidad de pedidos** y una columna de **cliente Premier** que se basa en alguna fórmula con las demás columnas.</span><span class="sxs-lookup"><span data-stu-id="a723f-105">For example, suppose your data contains a **Purchase Amount** column, an **Orders Quantity** column, and a **Premier Customer** column that is based on some formula using the other columns.</span></span> <span data-ttu-id="a723f-106">Si la columna de **cliente Premier** contiene muchas filas en blanco, podría usar las columnas **importe de compra** y **cantidad de pedidos** como entradas para deducir los valores que faltan.</span><span class="sxs-lookup"><span data-stu-id="a723f-106">If the  **Premier Customer** column contains many blank rows, you could use the **Purchase Amount** and **Orders Quantity** columns as the inputs, to infer the missing values.</span></span> <span data-ttu-id="a723f-107">La herramienta analiza los patrones existentes en los datos junto con los ejemplos especificados y predice a qué categoría se debe asignar cada cliente.</span><span class="sxs-lookup"><span data-stu-id="a723f-107">The tool analyzes existing patterns in the data together with the examples you entered, and predicts which category to assign to each customer.</span></span>  
  
 <span data-ttu-id="a723f-108">Si no está satisfecho con los resultados, puede precisarlos proporcionando más ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a723f-108">If you are not satisfied with the results, you can refine the results by providing more examples.</span></span>  
  
## <a name="using-the-fill-from-example-tool"></a><span data-ttu-id="a723f-109">Usar la herramienta Rellenar desde ejemplo</span><span class="sxs-lookup"><span data-stu-id="a723f-109">Using the Fill From Example Tool</span></span>  
  
1.  <span data-ttu-id="a723f-110">En la cinta de opciones **analizar** , haga clic en **rellenar desde ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="a723f-110">In the **Analyze** ribbon, click **Fill From Example**.</span></span>  
  
2.  <span data-ttu-id="a723f-111">La herramienta elegirá automáticamente la columna que va a rellenar basándose en el análisis de los datos, y el usuario podrá aceptar o invalidar esta sugerencia.</span><span class="sxs-lookup"><span data-stu-id="a723f-111">The tool will automatically pick a column to fill based on analysis of the data, and you can either accept or override this suggestion.</span></span>  
  
3.  <span data-ttu-id="a723f-112">Cree una columna para los nuevos datos y escriba ejemplos de los datos que desea predecir.</span><span class="sxs-lookup"><span data-stu-id="a723f-112">Create a column for the new data, and type in examples of the data that you want to predict.</span></span> <span data-ttu-id="a723f-113">Asegúrese de que existe al menos un ejemplo para cada valor que desea predecir.</span><span class="sxs-lookup"><span data-stu-id="a723f-113">Make sure that there is at least one example for every value that you want to predict.</span></span> <span data-ttu-id="a723f-114">Si está rellenando datos en una columna existente, seleccione la columna a la que le faltan valores.</span><span class="sxs-lookup"><span data-stu-id="a723f-114">If you are filling in data in an existing column, select the column that has missing values.</span></span>  
  
4.  <span data-ttu-id="a723f-115">Opcionalmente, haga clic en **elegir las columnas que se van a usar en el análisis**.</span><span class="sxs-lookup"><span data-stu-id="a723f-115">Optionally, click **Choose columns to be used in analysis**.</span></span> <span data-ttu-id="a723f-116">En el cuadro de diálogo **selección avanzada de columnas** , especifique las columnas que es más probable que sean útiles al rellenar los datos que faltan.</span><span class="sxs-lookup"><span data-stu-id="a723f-116">In the **Advanced Columns Selection** dialog box, specify the columns that are most likely to be useful when filling in the missing data.</span></span>  
  
     <span data-ttu-id="a723f-117">Por ejemplo, si sabe por experiencia que existe un efecto causal entre una columna y la columna con valores ausentes, puede anular la selección de otras columnas para obtener mejores resultados.</span><span class="sxs-lookup"><span data-stu-id="a723f-117">For example, if you know from experience that there is a causal effect between one column and the column that has missing values, you can deselect other columns to get better results.</span></span>  
  
     <span data-ttu-id="a723f-118">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a723f-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a723f-119">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a723f-119">Click **Run**.</span></span>  
  
     <span data-ttu-id="a723f-120">Una vez completado el análisis, la herramienta crea una nueva hoja de cálculo de **modelos** que contiene los resultados del análisis.</span><span class="sxs-lookup"><span data-stu-id="a723f-120">When analysis is complete, the tool creates a new **Patterns** worksheet that contains the results of analysis.</span></span> <span data-ttu-id="a723f-121">El informe enumera las reglas o influenciadores clave que se encontraron y muestra la probabilidad para cada regla.</span><span class="sxs-lookup"><span data-stu-id="a723f-121">The report lists the rules, or key influencers, that were found, and shows the probability for each rule.</span></span>  
  
     <span data-ttu-id="a723f-122">Asimismo, la herramienta agrega automáticamente una columna con los nuevos valores a la tabla de datos original.</span><span class="sxs-lookup"><span data-stu-id="a723f-122">The tool also automatically adds a column that contains the new values to the original data table.</span></span> <span data-ttu-id="a723f-123">Puede revisar los valores y compararlos con el original.</span><span class="sxs-lookup"><span data-stu-id="a723f-123">You can review the values and compare them against the original.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="a723f-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a723f-124">Requirements</span></span>  
 <span data-ttu-id="a723f-125">Sólo puede trabajar con datos en columnas.</span><span class="sxs-lookup"><span data-stu-id="a723f-125">You can only work with data in columns.</span></span> <span data-ttu-id="a723f-126">Si la serie que desea rellenar está almacenada en una fila, puede usar la función Pegar, Transponer de Excel para cambiar los datos a un formato de columna.</span><span class="sxs-lookup"><span data-stu-id="a723f-126">If the series that you want to fill is stored in a row, you can use the Paste, Transpose function in Excel to change the data to a columnar format.</span></span>  
  
## <a name="understanding-the-pattern-report"></a><span data-ttu-id="a723f-127">Descripción del informe de patrones</span><span class="sxs-lookup"><span data-stu-id="a723f-127">Understanding the Pattern Report</span></span>  
 <span data-ttu-id="a723f-128">Al ejecutar la herramienta **rellenar desde ejemplo** , se crea un informe que proporciona más información sobre los patrones detectados.</span><span class="sxs-lookup"><span data-stu-id="a723f-128">When you run the **Fill From Example** tool, a report is created that provides more information about the patterns that were detected.</span></span> <span data-ttu-id="a723f-129">Estos patrones se usan para extrapolar nuevos valores de datos.</span><span class="sxs-lookup"><span data-stu-id="a723f-129">These patterns are used for extrapolating new data values.</span></span>  
  
 <span data-ttu-id="a723f-130">El informe de patrones muestra los influenciadores clave de cada valor que se predijo.</span><span class="sxs-lookup"><span data-stu-id="a723f-130">The Pattern Report shows the key influencers for each value that was predicted.</span></span> <span data-ttu-id="a723f-131">Cada influenciador o regla se describe como una combinación de una columna, el valor de la misma y el impacto relativo de la regla en la predicción.</span><span class="sxs-lookup"><span data-stu-id="a723f-131">Each influencer or rule is described as a combination of a column, the value in that column, and the relative impact of the rule on the prediction.</span></span>  
  
 <span data-ttu-id="a723f-132">Por ejemplo, si intentaba rellenar una hoja de cálculo que mostraba la distancia en el envío de pedidos, lógicamente podría esperar que el destino tuviera un fuerte impacto en el valor de la distancia en el envío.</span><span class="sxs-lookup"><span data-stu-id="a723f-132">For example, if you were trying to fill in a worksheet that shows the shipping distance for orders, you might logically expect the destination to have a strong impact on the value for shipping distance.</span></span> <span data-ttu-id="a723f-133">En este caso, el informe contendría la siguiente fila:</span><span class="sxs-lookup"><span data-stu-id="a723f-133">In this case, the report might contain the following row:</span></span>  
  
|<span data-ttu-id="a723f-134">Columna</span><span class="sxs-lookup"><span data-stu-id="a723f-134">Column</span></span>|<span data-ttu-id="a723f-135">Value</span><span class="sxs-lookup"><span data-stu-id="a723f-135">Value</span></span>|<span data-ttu-id="a723f-136">Favorece</span><span class="sxs-lookup"><span data-stu-id="a723f-136">Favors</span></span>|<span data-ttu-id="a723f-137">Impacto relativo</span><span class="sxs-lookup"><span data-stu-id="a723f-137">Relative Impact</span></span>|  
|------------|-----------|------------|---------------------|  
|<span data-ttu-id="a723f-138">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="a723f-138">StateProvinceCode</span></span>|<span data-ttu-id="a723f-139">AB</span><span class="sxs-lookup"><span data-stu-id="a723f-139">AB</span></span>|<span data-ttu-id="a723f-140">>500 kilómetros</span><span class="sxs-lookup"><span data-stu-id="a723f-140">>500 kilometers</span></span>|<span data-ttu-id="a723f-141">80 %</span><span class="sxs-lookup"><span data-stu-id="a723f-141">80%</span></span>|  
  
 <span data-ttu-id="a723f-142">Esto significa que el valor AB de la columna **StateProvinceCode** predice fuertemente una distancia de envío de >500 kilómetros.</span><span class="sxs-lookup"><span data-stu-id="a723f-142">This means that the value AB in the **StateProvinceCode** column strongly predicts a shipping distance of >500 kilometers.</span></span>  
  
 <span data-ttu-id="a723f-143">Normalmente, las predicciones se basan en patrones que son mucho más complejos que este ejemplo y el informe puede contener muchas filas de reglas para cada predicción.</span><span class="sxs-lookup"><span data-stu-id="a723f-143">Typically, predictions are based on patterns that are far more complex than this example, and the report may contain many rows of rules for each prediction.</span></span> <span data-ttu-id="a723f-144">El efecto de todas las reglas se combina para obtener el valor de predicción.</span><span class="sxs-lookup"><span data-stu-id="a723f-144">The effect of all the rules are combined to derive the predicted value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a723f-145">El **impacto relativo** se muestra como una barra sombreada.</span><span class="sxs-lookup"><span data-stu-id="a723f-145">**Relative Impact** is shown as a shaded bar.</span></span> <span data-ttu-id="a723f-146">Cuanto más larga es la barra, mayor es la probabilidad de que esa regla sirva para predecir el valor rellenado.</span><span class="sxs-lookup"><span data-stu-id="a723f-146">The longer the bar, the greater the probability that this rule is predictive of the filled-in value.</span></span>  
  
 <span data-ttu-id="a723f-147">La herramienta también agrega una nueva columna a la tabla de datos original, denominada \<column name> Extended.</span><span class="sxs-lookup"><span data-stu-id="a723f-147">The tool also adds a new column to the original data table, named \<column name> Extended.</span></span>  
  
 <span data-ttu-id="a723f-148">Si la columna de datos original contenía un valor, éste se copia en la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="a723f-148">If the original data column contained a value, that value is copied into the new column.</span></span> <span data-ttu-id="a723f-149">Sin embargo, si la columna original contenía una celda en blanco, la nueva columna contendrá el valor predicho por el asistente.</span><span class="sxs-lookup"><span data-stu-id="a723f-149">However, if the original column contained a blank cell, the new column contains the value that was predicted by the wizard.</span></span>  
  
## <a name="related-tools-and-information"></a><span data-ttu-id="a723f-150">Información y herramientas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a723f-150">Related Tools and Information</span></span>  
 <span data-ttu-id="a723f-151">También puede usar el Asistente para [explorar datos](explore-data-sql-server-data-mining-add-ins.md) , disponible en el cliente de minería de datos para Excel, para examinar la distribución de valores en una columna de Excel.</span><span class="sxs-lookup"><span data-stu-id="a723f-151">You can also use the [Explore Data](explore-data-sql-server-data-mining-add-ins.md) wizard, available in the Data Mining Client for Excel, to examine the distribution of values in an Excel column.</span></span> <span data-ttu-id="a723f-152">Para obtener más información, vea [explorar y limpiar datos](exploring-and-cleaning-data.md).</span><span class="sxs-lookup"><span data-stu-id="a723f-152">For more information, see [Exploring and Cleaning Data](exploring-and-cleaning-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a723f-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a723f-153">See Also</span></span>  
 [<span data-ttu-id="a723f-154">Herramientas de análisis de tabla para Excel</span><span class="sxs-lookup"><span data-stu-id="a723f-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
