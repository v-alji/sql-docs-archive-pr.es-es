---
title: Aplicar filtros a los datos de prueba del modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input row filtering [SQL Server]
- filtering input rows [Analysis Services]
- Mining Accuracy Chart [Analysis Services], filtering input rows
ms.assetid: 9ccc9a23-5597-4b35-a05f-2fc8eb885147
author: minewiskan
ms.author: owend
ms.openlocfilehash: d1fd2b643ae4f7d831cab980ca45b7d43d8b58f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663197"
---
# <a name="apply-filters-to-model-testing-data"></a><span data-ttu-id="a147a-102">Aplicar filtros a los datos de prueba del modelo</span><span class="sxs-lookup"><span data-stu-id="a147a-102">Apply Filters to Model Testing Data</span></span>
  <span data-ttu-id="a147a-103">Al especificar un origen de datos externo que se va a utilizar para probar un modelo, opcionalmente puede aplicar un filtro para restringir los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a147a-103">When you specify an external data source to use in testing a model, you can optionally apply a filter to restrict the input data.</span></span> <span data-ttu-id="a147a-104">Por ejemplo, es posible que desee probar el modelo específicamente para realizar predicciones para los clientes con a un intervalo de ingresos determinado.</span><span class="sxs-lookup"><span data-stu-id="a147a-104">For example, you might want to test the model specifically for predictions on customers in a certain income range.</span></span>  
  
 <span data-ttu-id="a147a-105">Por ejemplo, en el escenario de distribución de correo directo de AdventureWorks, puede crear una expresión de filtro como la siguiente en ProspectiveBuyer, que es la tabla que contiene los datos de prueba, y restringir los casos de prueba por intervalo de ingresos:</span><span class="sxs-lookup"><span data-stu-id="a147a-105">For example, in the AdventureWorks targeted mailing scenario, you can create a filter expression like the following one on ProspectiveBuyer, which is the table that contains the testing data, and restrict testing cases by income range:</span></span>  
  
 `[YearlyIncome] = '50000'`  
  
 <span data-ttu-id="a147a-106">El comportamiento de los filtros es ligeramente diferente, dependiendo de si se filtran datos del entrenamiento del modelo o un conjunto de datos de prueba:</span><span class="sxs-lookup"><span data-stu-id="a147a-106">The behavior of filters is slightly different, depending on whether you are filtering model training data or a testing data set:</span></span>  
  
-   <span data-ttu-id="a147a-107">Al definir un filtro en un conjunto de datos de prueba, realmente está creando una cláusula WHERE en los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="a147a-107">When you define a filter on a testing data set, you create a WHERE clause on the incoming data.</span></span> <span data-ttu-id="a147a-108">Si está filtrando un conjunto de datos de entrada que se usa para evaluar un modelo, la expresión del filtro se traduce a una instrucción de Transact-SQL y se aplica a la tabla de entrada en el momento de crear el gráfico.</span><span class="sxs-lookup"><span data-stu-id="a147a-108">If you are filtering an input data set used for evaluating a model, the filter expression is translated to a Transact-SQL statement and applied to the input table when the chart is created.</span></span> <span data-ttu-id="a147a-109">Como resultado, se puede reducir en gran medida el número de casos de prueba.</span><span class="sxs-lookup"><span data-stu-id="a147a-109">As a result, the number of test cases can be greatly reduced.</span></span>  
  
-   <span data-ttu-id="a147a-110">Al aplicar un filtro a un modelo de minería de datos, la expresión del filtro que cree se traducirá a una instrucción de Extensiones de minería de datos (DMX) y se aplicará al modelo individual.</span><span class="sxs-lookup"><span data-stu-id="a147a-110">When you apply a filter to a mining model, the filter expression that you create is translated to a Data Mining Extensions (DMX) statement, and applied to the individual model.</span></span> <span data-ttu-id="a147a-111">Por lo tanto, al aplicar un filtro a un modelo, solamente se utilizará un subconjunto de los datos originales para entrenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="a147a-111">Therefore, when you apply a filter to a model, only a subset of the original data is used to train the model.</span></span> <span data-ttu-id="a147a-112">Esto puede causar problemas si se filtra el modelo de entrenamiento con un conjunto de criterios, de tal forma que el modelo se ajuste a cierto conjunto de datos, y, a continuación, se prueba el modelo con otro conjunto de criterios.</span><span class="sxs-lookup"><span data-stu-id="a147a-112">This can cause problems if you filter the training model with one set of criteria, so that the model is tuned to a certain set of data, and then test the model with another set of criteria.</span></span>  
  
-   <span data-ttu-id="a147a-113">Si define un conjunto de datos de pruebas en el momento de crear la estructura, entre los casos del modelo utilizados para el entrenamiento solamente se incluyen los que se encuentran en el conjunto de entrenamiento de la estructura de minería de datos **y** que cumplen con las condiciones del filtro.</span><span class="sxs-lookup"><span data-stu-id="a147a-113">If you defined a testing data set when you created the structure, the model cases used for training include only those cases that are in the mining structure training set **and** which meet the conditions of the filter.</span></span> <span data-ttu-id="a147a-114">De este modo, al probar un modelo y seleccionar la opción **Usar casos de prueba de modelo de minería de datos**, entre los casos de prueba solamente se incluirán los que se encuentran en el conjunto de prueba de la estructura de minería de datos y que cumplen las condiciones del filtro.</span><span class="sxs-lookup"><span data-stu-id="a147a-114">Thus, when you are testing a model and select the option **Use mining model test cases**, the testing cases will include only the cases that are in the mining structure test set and which meet the conditions of the filter.</span></span> <span data-ttu-id="a147a-115">Sin embargo, si no definió un conjunto de datos de exclusiones, en los casos del modelo utilizados para la prueba se incluyen todos los casos del conjunto de datos que cumplan las condiciones de filtro.</span><span class="sxs-lookup"><span data-stu-id="a147a-115">However, if you did not define a holdout data set, the model cases used for testing include all the cases in the data set that meet the filter conditions</span></span>  
  
-   <span data-ttu-id="a147a-116">Las condiciones de filtro que se apliquen en un modelo también afectarán a las consultas de obtención de detalles en los casos del modelo.</span><span class="sxs-lookup"><span data-stu-id="a147a-116">Filter conditions that you apply on a model also affect drillthrough queries on the model cases.</span></span>  
  
 <span data-ttu-id="a147a-117">En resumen, cuando se prueban varios modelos, aunque todos estén basados en la misma estructura de minería de datos, se debe tener en cuenta que es posible que los modelos utilicen subconjuntos de datos diferentes para el entrenamiento y las pruebas.</span><span class="sxs-lookup"><span data-stu-id="a147a-117">In summary, when you test multiple models, even if all the models are based on the same mining structure, you must be aware that the models potentially use different subsets of data for training and testing.</span></span> <span data-ttu-id="a147a-118">Esto puede tener los efectos siguientes en los gráficos de precisión:</span><span class="sxs-lookup"><span data-stu-id="a147a-118">This can have the following effects on accuracy charts:</span></span>  
  
-   <span data-ttu-id="a147a-119">El número total de casos en los conjuntos de pruebas puede variar entre los modelos que se prueban.</span><span class="sxs-lookup"><span data-stu-id="a147a-119">The total number of cases in the testing sets can vary among the models being tested.</span></span>  
  
-   <span data-ttu-id="a147a-120">Es posible que los porcentajes para cada modelo no estén alineados en el gráfico si los modelos utilizan subconjuntos de datos de entrenamiento o de prueba diferentes.</span><span class="sxs-lookup"><span data-stu-id="a147a-120">The percentages for each model may not align in the chart, if the models use different subsets of training data or testing data.</span></span>  
  
 <span data-ttu-id="a147a-121">Para determinar si un modelo contiene un filtro predefinido que puede afectar a los resultados, busque la propiedad **Filter** en el panel **Propiedad** o consulte el modelo utilizando los conjuntos de filas de esquema de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="a147a-121">To determine whether a model contains a predefined filter that might affect results, you can look for the **Filter** property in the **Property** pane, or you can query the model by using the data mining schema rowsets.</span></span> <span data-ttu-id="a147a-122">Por ejemplo, la consulta siguiente devuelve el texto del filtro para el modelo especificado:</span><span class="sxs-lookup"><span data-stu-id="a147a-122">For example, the following query returns the filter text for the specified model:</span></span>  
  
 `SELECT [FILTER] FROM $system.DMSCHEMA_MINING_MODELS WHERE MODEL_NAME = 'name of model'`  
  
> [!WARNING]  
>  <span data-ttu-id="a147a-123">Si desea quitar el filtro de un modelo de minería de datos existente, o cambiar las condiciones del filtro, deberá volver a procesar dicho modelo.</span><span class="sxs-lookup"><span data-stu-id="a147a-123">If you want to remove the filter from an existing mining model, or change the filter conditions, you must reprocess the mining model.</span></span>  
  
 <span data-ttu-id="a147a-124">Para más información sobre los tipos de filtros que se pueden aplicar y cómo se evalúan las expresiones de filtro, vea [Sintaxis y ejemplos del filtro de modelos &#40;Analysis Services: Minería de datos&#41;](model-filter-syntax-and-examples-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="a147a-124">For more information about the kinds of filters you can apply, and how filter expressions are evaluated, see [Model Filter Syntax and Examples &#40;Analysis Services - Data Mining&#41;](model-filter-syntax-and-examples-analysis-services-data-mining.md).</span></span>  
  
### <a name="create-a-filter-on-external-testing-data"></a><span data-ttu-id="a147a-125">Crear un filtro en datos de prueba externos</span><span class="sxs-lookup"><span data-stu-id="a147a-125">Create a filter on external testing data</span></span>  
  
1.  <span data-ttu-id="a147a-126">Haga doble clic en la estructura de minería de datos que contiene el modelo que desea probar para abrir el Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="a147a-126">Double-click the mining structure that contains the model you want to test, to open Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="a147a-127">Seleccione la pestaña **Gráfico de precisión de minería de datos** y luego seleccione la pestaña **Selección de entrada** .</span><span class="sxs-lookup"><span data-stu-id="a147a-127">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="a147a-128">En la pestaña **Selección de entrada** , en **Seleccionar un conjunto de datos para usarlo en un gráfico de precisión**, seleccione la opción **Especificar otro conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="a147a-128">On the **Input Selection** tab, under **Select data set to be used for Accuracy Chart**, select the option **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="a147a-129">Haga clic en el botón examinar **(...)** para abrir un cuadro de diálogo y elija el conjunto de datos externo.</span><span class="sxs-lookup"><span data-stu-id="a147a-129">Click the browse button **(...)** to open a dialog box and choose the external data set.</span></span>  
  
5.  <span data-ttu-id="a147a-130">Elija la tabla de casos y agregue una tabla anidada si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="a147a-130">Choose the case table, and add a nested table if necessary.</span></span> <span data-ttu-id="a147a-131">Asigne columnas del modelo a columnas del conjunto de datos externos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a147a-131">Map columns in the model to columns in the external data set as necessary.</span></span> <span data-ttu-id="a147a-132">Cierre el cuadro de diálogo **Especificar asignación de columna** para guardar la definición de la tabla de origen.</span><span class="sxs-lookup"><span data-stu-id="a147a-132">Close the **Specify Column Mapping** dialog box to save the source table definition.</span></span>  
  
6.  <span data-ttu-id="a147a-133">Haga clic en **Abrir editor de filtros** para definir un filtro para el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="a147a-133">Click **Open Filter Editor** to define a filter for the data set.</span></span>  
  
     <span data-ttu-id="a147a-134">Aparece el cuadro de diálogo **Filtro de conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="a147a-134">The **Data Set Filter** dialog box opens.</span></span> <span data-ttu-id="a147a-135">Si la estructura contiene una tabla anidada, puede crear un filtro en dos partes.</span><span class="sxs-lookup"><span data-stu-id="a147a-135">If the structure contains a nested table, you can create a filter in two parts.</span></span> <span data-ttu-id="a147a-136">En primer lugar, establezca las condiciones en la tabla de casos mediante el cuadro de diálogo **Filtro de conjunto de datos** y, a continuación, establezca las condiciones en las filas anidadas mediante el cuadro de diálogo **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="a147a-136">First, set conditions on the case table by using the **Data Set Filter** dialog box, and then set conditions on the nested rows by using the **Filter** dialog box.</span></span>  
  
7.  <span data-ttu-id="a147a-137">En el cuadro de diálogo **Filtro de conjunto de datos** , haga clic en la fila superior de la cuadrícula, en **Columna de la estructura de minería de datos**, y seleccione una tabla o columna en la lista.</span><span class="sxs-lookup"><span data-stu-id="a147a-137">In the **Data Set Filter** dialog box, click the top row in the grid, under **Mining Structure Column**, and select a table or column from the list.</span></span>  
  
     <span data-ttu-id="a147a-138">Si la vista del origen de datos contiene varias tablas o una tabla anidada, debe seleccionar primero el nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a147a-138">If the data source view contains multiple tables, or a nested table, you must first select the table name.</span></span> <span data-ttu-id="a147a-139">De lo contrario, puede seleccionar las columnas directamente en la tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="a147a-139">Otherwise, you can select columns from the case table directly.</span></span>  
  
     <span data-ttu-id="a147a-140">Agregue una nueva fila para cada columna que desea filtrar.</span><span class="sxs-lookup"><span data-stu-id="a147a-140">Add a new row for each column that you want to filter.</span></span>  
  
8.  <span data-ttu-id="a147a-141">Use las columnas **Operator**y **Value** para definir cómo se filtra la columna.</span><span class="sxs-lookup"><span data-stu-id="a147a-141">Use **Operator**, and **Value** columns to define how the column is filtered.</span></span>  
  
     <span data-ttu-id="a147a-142">**Nota** : escriba los valores sin usar comillas tipográficas.</span><span class="sxs-lookup"><span data-stu-id="a147a-142">**Note** Type values without using quotation marks.</span></span>  
  
9. <span data-ttu-id="a147a-143">Haga clic en el cuadro de texto **Y/O** y seleccione un operador lógico para definir cómo se combinan varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="a147a-143">Click the **And/Or** text box and select a logical operator to define how multiple conditions are combine.</span></span>  
  
10. <span data-ttu-id="a147a-144">Opcionalmente, haga clic en el botón examinar **(...)** a la derecha del cuadro de texto **valor** para abrir el cuadro de diálogo **filtro** y establecer las condiciones en la tabla anidada o en las columnas individuales de la tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="a147a-144">Optionally, click the browse button **(...)** at the right of the **Value** text box to open the **Filter** dialog box and set conditions on the nested table or on the individual case table columns.</span></span>  
  
11. <span data-ttu-id="a147a-145">Vea el texto que aparece en el panel **Expresión** para comprobar que las condiciones de filtro completadas son correctas.</span><span class="sxs-lookup"><span data-stu-id="a147a-145">Verify that the completed filter conditions are correct by viewing the text in the **Expression** pane.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="a147a-146">La condición de filtro se aplica al origen de datos al crear el gráfico de precisión.</span><span class="sxs-lookup"><span data-stu-id="a147a-146">The filter condition is applied to the data source when you create the accuracy chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a147a-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a147a-147">See Also</span></span>  
 <span data-ttu-id="a147a-148">[Elegir y asignar los datos de prueba del modelo](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="a147a-148">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 <span data-ttu-id="a147a-149">[Usar datos de tabla anidada como entrada para un gráfico de precisión](using-nested-table-data-as-an-input-for-an-accuracy-chart.md) </span><span class="sxs-lookup"><span data-stu-id="a147a-149">[Using Nested Table Data as an Input for an Accuracy Chart](using-nested-table-data-as-an-input-for-an-accuracy-chart.md) </span></span>  
 [<span data-ttu-id="a147a-150">Elegir un tipo de gráfico de precisión y establecer las opciones del gráfico</span><span class="sxs-lookup"><span data-stu-id="a147a-150">Choose an Accuracy Chart Type and Set Chart Options</span></span>](choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  
