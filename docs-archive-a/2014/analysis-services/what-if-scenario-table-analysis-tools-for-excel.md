---
title: Escenario de si (herramientas de análisis de tabla para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- what if scenario
- scenario analysis
ms.assetid: 4df5a5c5-1983-4009-a7c5-cd340649fd2f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4bb5c5e866c1320c297fb4f2760bca58623f6601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752366"
---
# <a name="what-if-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="55b2f-102">Escenario Y si (Herramientas de análisis de tabla para Excel)</span><span class="sxs-lookup"><span data-stu-id="55b2f-102">What-If Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="55b2f-103">![Botón Escenario Y si de las herramientas de análisis de tabla](media/tat-whatif.gif "Botón Escenario Y si de las herramientas de análisis de tabla")</span><span class="sxs-lookup"><span data-stu-id="55b2f-103">![What If Scenario button in Table Analysis tools](media/tat-whatif.gif "What If Scenario button in Table Analysis tools")</span></span>

 <span data-ttu-id="55b2f-104">La herramienta escenario y **si** analiza patrones en los datos existentes y, a continuación, le permite evaluar el efecto que tendrían los cambios en una columna en el valor de una columna diferente.</span><span class="sxs-lookup"><span data-stu-id="55b2f-104">The **What-If** scenario tool analyzes patterns in existing data, and then enables you to evaluate the effect that changes in one column would have on the value of a different column.</span></span>

 <span data-ttu-id="55b2f-105">Por ejemplo, se podría estudiar el efecto de una subida del precio de un artículo sobre las ventas totales.</span><span class="sxs-lookup"><span data-stu-id="55b2f-105">For example, you could explore the effect of raising the price of an item on its total sales.</span></span>

 <span data-ttu-id="55b2f-106">La herramienta es flexible en cuanto al número de predicciones que se pueden crear.</span><span class="sxs-lookup"><span data-stu-id="55b2f-106">The tool is flexible about the number of predictions you can create.</span></span> <span data-ttu-id="55b2f-107">Una vez finalizado el análisis inicial, puede predecir cambios para todos los datos de la tabla o especificar valores de prueba de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="55b2f-107">After the initial analysis is complete, you can either predict changes for all the data in the table, or enter test values one at a time.</span></span>

## <a name="using-the-what-if-scenario-tool"></a><span data-ttu-id="55b2f-108">Usar la herramienta de escenario Y si</span><span class="sxs-lookup"><span data-stu-id="55b2f-108">Using the What-If Scenario Tool</span></span>

1.  <span data-ttu-id="55b2f-109">Abra una tabla de datos de Excel.</span><span class="sxs-lookup"><span data-stu-id="55b2f-109">Open an Excel data table.</span></span>

2.  <span data-ttu-id="55b2f-110">Haga clic en **escenarios**y seleccione **Qué hacer si**.</span><span class="sxs-lookup"><span data-stu-id="55b2f-110">Click **Scenarios**, and then select **What-If**.</span></span>

3.  <span data-ttu-id="55b2f-111">En el cuadro **escenario** , seleccione la columna que contiene el valor que va a cambiar y especifique el cambio como un valor específico o como un porcentaje de cambio (aumenta o disminuye) en los valores actuales.</span><span class="sxs-lookup"><span data-stu-id="55b2f-111">In the **Scenario** box, select the column that contains the value you will change, and specify the change either as a specific value or as a percentage of change (either increased or decreased) on the current values.</span></span>

4.  <span data-ttu-id="55b2f-112">En el cuadro **¿Qué ocurre** ?, especifique la columna para la que desea evaluar el efecto.</span><span class="sxs-lookup"><span data-stu-id="55b2f-112">In the **What happens to** box, specify the column for which you want to assess the effect.</span></span>

5.  <span data-ttu-id="55b2f-113">Opcionalmente, haga clic en **elegir las columnas que se van a usar para el análisis** para seleccionar las columnas que probablemente sean útiles para realizar la predicción.</span><span class="sxs-lookup"><span data-stu-id="55b2f-113">Optionally, click **Choose columns to be used for analysis** to select columns that are likely to be useful in making the prediction.</span></span> <span data-ttu-id="55b2f-114">También se puede anular la selección de las columnas que pueden resultar de poca utilidad a la hora de detectar patrones, como las que contienen identificadores de fila o nombres.</span><span class="sxs-lookup"><span data-stu-id="55b2f-114">You can also deselect columns that are likely to be of little use in detecting patterns, such as row IDs or names.</span></span>

6.  <span data-ttu-id="55b2f-115">En el cuadro **especificar fila o tabla** , elija si desea que el impacto se evalúe solo para la fila seleccionada actualmente o para el conjunto completo de datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="55b2f-115">In the **Specify row or table** box, choose whether you want the impact assessed for the currently selected row only, or for the complete set of data in the table.</span></span>

7.  <span data-ttu-id="55b2f-116">Si selecciona **en esta fila**, la herramienta muestra el resultado en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="55b2f-116">If you select **On this row**, the tool displays the result in the dialog box.</span></span> <span data-ttu-id="55b2f-117">Mientras el cuadro de diálogo permanece abierto, puede modificar las selecciones para probar otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="55b2f-117">While the dialog box remains open, you can modify your selections to test other scenarios.</span></span>

8.  <span data-ttu-id="55b2f-118">Si selecciona **toda la tabla**, la herramienta muestra un mensaje de estado en el cuadro de diálogo y agrega dos nuevas columnas a la tabla de datos original.</span><span class="sxs-lookup"><span data-stu-id="55b2f-118">If you select **Entire table**, the tool displays a status message in the dialog box, and adds two new columns to the original data table.</span></span> <span data-ttu-id="55b2f-119">Haga clic en **cerrar** para ver los resultados completos en la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="55b2f-119">Click **Close** to view the complete results in the worksheet.</span></span>

### <a name="requirements"></a><span data-ttu-id="55b2f-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55b2f-120">Requirements</span></span>
 <span data-ttu-id="55b2f-121">Esta herramienta utiliza el algoritmo de regresión logística de Microsoft, que admite la predicción de valores numéricos o discretos.</span><span class="sxs-lookup"><span data-stu-id="55b2f-121">This tool uses the Microsoft Logistic Regression algorithm, which supports prediction of either numeric or discrete values.</span></span> <span data-ttu-id="55b2f-122">Sin embargo, para obtener los mejores resultados, se recomienda seguir las prácticas recomendadas siguientes:</span><span class="sxs-lookup"><span data-stu-id="55b2f-122">However, to achieve the best results, we suggest the following best practices:</span></span>

-   <span data-ttu-id="55b2f-123">Seleccione columnas para el análisis que contengan información útil.</span><span class="sxs-lookup"><span data-stu-id="55b2f-123">Select columns for analysis that contain useful information.</span></span>

-   <span data-ttu-id="55b2f-124">Si incluye muy pocas columnas, puede ser difícil obtener un resultado.</span><span class="sxs-lookup"><span data-stu-id="55b2f-124">If you include too few columns it may be difficult to obtain a result.</span></span>

-   <span data-ttu-id="55b2f-125">Si usa la opción **para valor** , debe escribir un valor en el cuadro o seleccionar un valor de la lista.</span><span class="sxs-lookup"><span data-stu-id="55b2f-125">If you use the **To value** option, you must type a value in the box or select a value from the list.</span></span>

-   <span data-ttu-id="55b2f-126">Si usa la opción **porcentaje** , establezca el cambio en porcentaje de aumento o disminución.</span><span class="sxs-lookup"><span data-stu-id="55b2f-126">If you use the **Percentage** option, set the change as a percentage increase or decrease.</span></span> <span data-ttu-id="55b2f-127">El valor predeterminado es 120%, lo que supone un incremento del 20% sobre el valor actual.</span><span class="sxs-lookup"><span data-stu-id="55b2f-127">The default is 120%, meaning a 20% increase over the current value.</span></span>

> [!NOTE]
>  <span data-ttu-id="55b2f-128">Si no establece un valor, se podría producir un error.</span><span class="sxs-lookup"><span data-stu-id="55b2f-128">If you do not set a value, you might receive an error.</span></span>

## <a name="understanding-the-results-of-what-if-analysis"></a><span data-ttu-id="55b2f-129">Descripción de los resultados de un análisis Y si</span><span class="sxs-lookup"><span data-stu-id="55b2f-129">Understanding the Results of What-If Analysis</span></span>
 <span data-ttu-id="55b2f-130">Al crear un escenario **de tipo "si"** , la herramienta hace tres cosas:</span><span class="sxs-lookup"><span data-stu-id="55b2f-130">When you create a **What-If** scenario, the tool does three things:</span></span>

-   <span data-ttu-id="55b2f-131">Crea una estructura de minería de datos que almacena hechos clave sobre los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="55b2f-131">Creates a data mining structure that stores key facts about the data in your table.</span></span>

-   <span data-ttu-id="55b2f-132">Crea un modelo de minería de datos de regresión logística basado en los datos.</span><span class="sxs-lookup"><span data-stu-id="55b2f-132">Creates a logistic regression mining model based on the data.</span></span>

-   <span data-ttu-id="55b2f-133">Crea una consulta de predicción para cada uno de los valores especificados.</span><span class="sxs-lookup"><span data-stu-id="55b2f-133">Creates a prediction query for each of the values you specify.</span></span>

 <span data-ttu-id="55b2f-134">Puede generar todas las predicciones al mismo tiempo si especifica toda la **tabla**.</span><span class="sxs-lookup"><span data-stu-id="55b2f-134">You can output all the predictions at one time by specifying **Entire table**.</span></span> <span data-ttu-id="55b2f-135">En ese caso, la herramienta crea dos nuevas columnas en la tabla de datos original.</span><span class="sxs-lookup"><span data-stu-id="55b2f-135">The tool then creates two new columns in the original data table.</span></span>

 <span data-ttu-id="55b2f-136">Las columnas que se agregan a la tabla contienen dos tipos de información: el valor de predicción dado el cambio y su confianza.</span><span class="sxs-lookup"><span data-stu-id="55b2f-136">The columns that are added to the table contain two types of information: the predicted value given the change, and its confidence.</span></span> <span data-ttu-id="55b2f-137">La confianza significa la probabilidad de que la predicción sea correcta.</span><span class="sxs-lookup"><span data-stu-id="55b2f-137">Confidence means the probability that the prediction is correct.</span></span>

 <span data-ttu-id="55b2f-138">También se pueden especificar los valores de cambio uno a uno en el cuadro de diálogo y ver las predicciones de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="55b2f-138">You can also enter change values one by one in the dialog box, and view the predictions interactively.</span></span> <span data-ttu-id="55b2f-139">Esto es lo mismo que crear una *consulta de predicción singleton*.</span><span class="sxs-lookup"><span data-stu-id="55b2f-139">This is the same as creating a *singleton prediction query*.</span></span> <span data-ttu-id="55b2f-140">Los resultados de la consulta de predicción incluyen la siguiente información: el éxito o el fracaso de la predicción, el valor de predicción y el nivel de confianza.</span><span class="sxs-lookup"><span data-stu-id="55b2f-140">The results of the prediction query are output with the following information: the success or failure of prediction, the predicted value, and the confidence level.</span></span> <span data-ttu-id="55b2f-141">El nivel de confianza aparece como una barra que contiene una línea de puntos.</span><span class="sxs-lookup"><span data-stu-id="55b2f-141">The confidence level is shown as a bar that contains a dotted line.</span></span> <span data-ttu-id="55b2f-142">Cuanto más larga sea la línea de puntos, mayor será la confianza en el resultado.</span><span class="sxs-lookup"><span data-stu-id="55b2f-142">The longer the dotted line, the higher the confidence in the result.</span></span>

 <span data-ttu-id="55b2f-143">Por ejemplo, si intenta determinar el efecto de aumentar la edad del cliente en la voluntad del cliente por comprar y aumentar la edad del cliente a 25, la herramienta **What-if** consulta el modelo de minería de datos y devuelve el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="55b2f-143">For example, if you are trying to determine the effect of increasing the customer's age on the customer's willingness to buy, and increase the customer's age to 25, the **What-If** tool queries the data mining model and returns the following result:</span></span>

 <span data-ttu-id="55b2f-144">**El análisis Y si de Purchases Bicycle encontró una solución.**</span><span class="sxs-lookup"><span data-stu-id="55b2f-144">**What-If Analysis for Purchases Bicycle has found a solution.**</span></span>

 <span data-ttu-id="55b2f-145">**'Purchases Bicycle' = sí**</span><span class="sxs-lookup"><span data-stu-id="55b2f-145">**'Purchases Bicycle' = yes**</span></span>

 <span data-ttu-id="55b2f-146">**Confianza: Regular**</span><span class="sxs-lookup"><span data-stu-id="55b2f-146">**Confidence: Fair**</span></span>

 <span data-ttu-id="55b2f-147">Dado que este resultado se basa en una fila existente de la tabla de datos, eso significa que, para un cliente concreto, si todos los datos sobre ese cliente permanecen iguales pero la edad se aumenta a 25, probablemente compraría una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="55b2f-147">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's age was increased to 25, the customer would likely buy a bicycle.</span></span>

 <span data-ttu-id="55b2f-148">El obtener las predicciones con la tabla de datos original podría facilitar la determinación de si las predicciones son útiles.</span><span class="sxs-lookup"><span data-stu-id="55b2f-148">Outputting the predictions to the original data table might make it easier to determine whether the predictions are useful.</span></span>

## <a name="related-tools"></a><span data-ttu-id="55b2f-149">Herramientas relacionadas</span><span class="sxs-lookup"><span data-stu-id="55b2f-149">Related Tools</span></span>
 <span data-ttu-id="55b2f-150">El Cliente de minería de datos para Excel, que es un complemento independiente que ofrece funciones de minería de datos más avanzadas, incluye asistentes para crear modelos de minería de datos que predicen el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="55b2f-150">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="55b2f-151">Para obtener más información, vea [crear un modelo de minería de datos](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="55b2f-151">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="55b2f-152">Para obtener más información acerca del algoritmo usado por la herramienta de escenario y **si** , vea el tema "algoritmo de regresión logística de Microsoft" en libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="55b2f-152">For more information about the algorithm used by the **What-If** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in SQL Server Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="55b2f-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55b2f-153">See Also</span></span>
 [<span data-ttu-id="55b2f-154">Herramientas de análisis de tabla para Excel</span><span class="sxs-lookup"><span data-stu-id="55b2f-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


