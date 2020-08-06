---
title: Aplicar funciones de predicción a un modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Model Prediction [Analysis Services], selecting mining models
ms.assetid: cf9a97e2-c249-441b-af12-c977c1a91c44
author: minewiskan
ms.author: owend
ms.openlocfilehash: fde9de00adaa1712a9db6e18aabc6a83dd660efb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663196"
---
# <a name="apply-prediction-functions-to-a-model"></a><span data-ttu-id="ffa44-102">Aplicar funciones de predicción a un modelo</span><span class="sxs-lookup"><span data-stu-id="ffa44-102">Apply Prediction Functions to a Model</span></span>
  <span data-ttu-id="ffa44-103">Para crear una consulta de predicción, antes debe seleccionar el modelo de minería de datos en el que se basará la consulta.</span><span class="sxs-lookup"><span data-stu-id="ffa44-103">To create a prediction query, you must first select the mining model on which the query will be based.</span></span> <span data-ttu-id="ffa44-104">Puede seleccionar cualquier modelo de minería de datos que esté incluido en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="ffa44-104">You can select any mining model that exists in the current project.</span></span>  
  
 <span data-ttu-id="ffa44-105">Cuando haya seleccionado un modelo, agregue una *función de predicción* a la consulta.</span><span class="sxs-lookup"><span data-stu-id="ffa44-105">After you have selected a model, add a *prediction function* to the query.</span></span> <span data-ttu-id="ffa44-106">Se trata de una importación para comprender que las funciones de predicción se usan para muchos propósitos: sí, puede predecir valores, pero también puede obtener estadísticas relacionadas, así como la información que se usó para generar la predicción.</span><span class="sxs-lookup"><span data-stu-id="ffa44-106">It is import to understand that prediction functions are used for many purposes-yes, you can predict values, but you can also get related statistics, as well as information that was used in generating the prediction.</span></span> <span data-ttu-id="ffa44-107">Las funciones de predicción pueden devolver los siguientes tipos de valores:</span><span class="sxs-lookup"><span data-stu-id="ffa44-107">Prediction functions can return the following types of values:</span></span>  
  
-   <span data-ttu-id="ffa44-108">El nombre del atributo de predicción y el valor que se predice.</span><span class="sxs-lookup"><span data-stu-id="ffa44-108">The name of the predictable attribute, and the value that is predicted.</span></span>  
  
-   <span data-ttu-id="ffa44-109">Estadísticas acerca de la distribución y la varianza de los valores previstos.</span><span class="sxs-lookup"><span data-stu-id="ffa44-109">Statistics about the distribution and variance of the predicted values.</span></span>  
  
-   <span data-ttu-id="ffa44-110">La probabilidad del resultado especificado o todos los posibles resultados.</span><span class="sxs-lookup"><span data-stu-id="ffa44-110">The probability of a specified outcome, or of all possible outcomes.</span></span>  
  
-   <span data-ttu-id="ffa44-111">Los valores o puntuaciones superiores o inferiores.</span><span class="sxs-lookup"><span data-stu-id="ffa44-111">The top or bottom scores or values.</span></span>  
  
-   <span data-ttu-id="ffa44-112">Los valores asociados a un nodo, un objeto o un atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="ffa44-112">Values associated with a specified node, object, or attribute.</span></span>  
  
 <span data-ttu-id="ffa44-113">Hay una amplia variedad de funciones de predicción que puede utilizar, pero debe elegir la función que se ajuste al tipo de modelo que creó.</span><span class="sxs-lookup"><span data-stu-id="ffa44-113">There is a wide variety of prediction functions that you can use, but you must choose the function that suits the type of model you created.</span></span> <span data-ttu-id="ffa44-114">Normalmente, esta opción depende del algoritmo utilizado para crear el modelo.</span><span class="sxs-lookup"><span data-stu-id="ffa44-114">Usually this choice depends on the algorithm used to create the model.</span></span>  
  
-   <span data-ttu-id="ffa44-115">Para obtener una lista de las funciones de predicción admitidas por casi todos los tipos de modelo, vea [Funciones de predicción generales &#40;DMX&#41;](/sql/dmx/general-prediction-functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="ffa44-115">For a list of the prediction functions that are supported for almost all model types, see [General Prediction Functions &#40;DMX&#41;](/sql/dmx/general-prediction-functions-dmx).</span></span>  
  
-   <span data-ttu-id="ffa44-116">Además, los algoritmos individuales admiten diversas funciones especializadas.</span><span class="sxs-lookup"><span data-stu-id="ffa44-116">Additionally, individual algorithms support a variety of specialized functions.</span></span> <span data-ttu-id="ffa44-117">Por ejemplo, si crea un modelo de minería de datos basado en el algoritmo de clústeres de Microsoft, puede utilizar funciones especializadas de predicción para buscar información sobre los clústeres, como la distancia de un valor de datos al centroide del clúster.</span><span class="sxs-lookup"><span data-stu-id="ffa44-117">For example, if you create a mining model based on the Microsoft Clustering algorithm, you can use specialized prediction functions to find information about the clusters, such as the distance from a data value to the cluster centroid.</span></span>  
  
     <span data-ttu-id="ffa44-118">Para obtener ejemplos de cómo consultar un tipo específico de modelo de minería de datos, vea el tema de referencia del algoritmo, en [Algoritmos de minería de datos &#40;Analysis Services: Minería de datos&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="ffa44-118">For examples of how to query a specific type of mining model, see the algorithm reference topic, in [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
### <a name="choose-a-mining-model-to-use-for-prediction"></a><span data-ttu-id="ffa44-119">Elegir un modelo de minería de datos que utilizar en la predicción</span><span class="sxs-lookup"><span data-stu-id="ffa44-119">Choose a mining model to use for prediction</span></span>  
  
1.  <span data-ttu-id="ffa44-120">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], haga clic con el botón derecho en el modelo y seleccione **Generar consulta de predicción**.</span><span class="sxs-lookup"><span data-stu-id="ffa44-120">From [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the model, and select **Build Prediction Query**.</span></span>  
  
     <span data-ttu-id="ffa44-121">O bien</span><span class="sxs-lookup"><span data-stu-id="ffa44-121">--OR --</span></span>  
  
     <span data-ttu-id="ffa44-122">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga clic en la pestaña **Predicción de modelo de minería de datos**y, después, haga clic en **Seleccionar modelo** en la tabla  **Modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="ffa44-122">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the tab, **Mining Model Prediction**, and then click **Select Model** in the  **Mining Model** table.</span></span>  
  
2.  <span data-ttu-id="ffa44-123">En el cuadro de diálogo **Seleccionar modelo de minería de datos** , seleccione un modelo de minería de datos y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ffa44-123">In the **Select Mining Model** dialog box, select a mining model, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ffa44-124">Puede elegir un modelo en la base de datos actual de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffa44-124">You can choose any model within the current [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="ffa44-125">Para crear una consulta con un modelo en una base de datos diferente, debe abrir una nueva ventana de consulta en el contexto de esa base de datos o abrir el archivo de solución que contiene el modelo.</span><span class="sxs-lookup"><span data-stu-id="ffa44-125">To create a query using a model in a different database, you must either open a new query window in the context of that database, or open the solution file that contains that model.</span></span>  
  
### <a name="add-prediction-functions-to-a-query"></a><span data-ttu-id="ffa44-126">Agregue funciones de predicción a una consulta</span><span class="sxs-lookup"><span data-stu-id="ffa44-126">Add prediction functions to a query</span></span>  
  
1.  <span data-ttu-id="ffa44-127">En **Generador de consultas de predicción**, configure los datos de entrada utilizados para la predicción, proporcionando los valores en el cuadro de diálogo **Entrada de consulta singleton** o asignando el modelo a un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="ffa44-127">In the **Prediction Query Builder**, configure the input data used for prediction, either by providing values in the **Singleton Query Input** dialog box, or by mapping the model to an external data source.</span></span>  
  
     <span data-ttu-id="ffa44-128">Para más información, vea [Elegir y asignar datos de entrada para una consulta de predicción](choose-and-map-input-data-for-a-prediction-query.md).</span><span class="sxs-lookup"><span data-stu-id="ffa44-128">For more information, see [Choose and Map Input Data for a Prediction Query](choose-and-map-input-data-for-a-prediction-query.md).</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="ffa44-129">No es necesario proporcionar entradas para generar predicciones.</span><span class="sxs-lookup"><span data-stu-id="ffa44-129">It is not required that you provide inputs to generate predictions.</span></span> <span data-ttu-id="ffa44-130">Cuando no hay ninguna entrada, el algoritmo normalmente devolverá el valor predicho más probable en todas las entradas posibles.</span><span class="sxs-lookup"><span data-stu-id="ffa44-130">When there is no input, the algorithm will typically return the mostly likely predicted value across all possible inputs.</span></span>  
  
2.  <span data-ttu-id="ffa44-131">Haga clic en la columna **Origen** y elija un valor en la lista:</span><span class="sxs-lookup"><span data-stu-id="ffa44-131">Click the **Source** column, and choose a value from the list:</span></span>  
  
    |||  
    |-|-|  
    |**\<model name>**|<span data-ttu-id="ffa44-132">Seleccione esta opción para incluir los valores del modelo de minería de datos en la salida.</span><span class="sxs-lookup"><span data-stu-id="ffa44-132">Select this option to include values from the mining model in the output.</span></span> <span data-ttu-id="ffa44-133">Solo puede agregar nuevas columnas de predicción.</span><span class="sxs-lookup"><span data-stu-id="ffa44-133">You can only add predictable columns.</span></span><br /><br /> <span data-ttu-id="ffa44-134">Cuando se agrega una columna del modelo, el resultado devuelto es la lista de valores no distintivos de esa columna.</span><span class="sxs-lookup"><span data-stu-id="ffa44-134">When you add a column from the model, the result returned is the non-distinct list of values in that column.</span></span><br /><br /> <span data-ttu-id="ffa44-135">Las columnas que agrega con esta opción se incluyen en la parte SELECT de la instrucción DMX resultante.</span><span class="sxs-lookup"><span data-stu-id="ffa44-135">The columns that you add with this option are included in the SELECT portion of the resulting DMX statement.</span></span>|  
    |<span data-ttu-id="ffa44-136">**Prediction Function**</span><span class="sxs-lookup"><span data-stu-id="ffa44-136">**Prediction Function**</span></span>|<span data-ttu-id="ffa44-137">Seleccione esta opción para examinar una lista de funciones de predicción.</span><span class="sxs-lookup"><span data-stu-id="ffa44-137">Select this option to browse a list of prediction functions.</span></span><br /><br /> <span data-ttu-id="ffa44-138">Los valores o funciones que seleccione se agregan a la parte SELECT de la instrucción DMX resultante.</span><span class="sxs-lookup"><span data-stu-id="ffa44-138">The values or functions you select are added to the SELECT portion of the resulting DMX statement.</span></span><br /><br /> <span data-ttu-id="ffa44-139">La lista de funciones de predicción no se filtra ni se restringe por el tipo de modelo que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ffa44-139">The list of prediction functions is not filtered or constrained by the type of model you have selected.</span></span> <span data-ttu-id="ffa44-140">Por consiguiente, si tiene alguna duda sobre si la función se admite para el tipo actual del modelo, basta con agregar la función a la lista y verla si hay un error.</span><span class="sxs-lookup"><span data-stu-id="ffa44-140">Therefore, if you have any doubt about whether the function is supported for the current model type, you can just add the function to the list and see if there is an error.</span></span><br /><br /> <span data-ttu-id="ffa44-141">Los elementos de lista que van precedidos por $ (como $AdjustedProbability) representan las columnas de la tabla anidada que se genera cuando se utiliza la función `PredictHistogram`.</span><span class="sxs-lookup"><span data-stu-id="ffa44-141">List items that are preceded by $ (such as $AdjustedProbability) represent columns from the nested table that is output when you use the function, `PredictHistogram`.</span></span> <span data-ttu-id="ffa44-142">Estos son los métodos abreviados que puede usar para devolver una columna y no una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="ffa44-142">These are shortcuts that you can use to return a single column and not a nested table.</span></span>|  
    |<span data-ttu-id="ffa44-143">**Expresión personalizada**</span><span class="sxs-lookup"><span data-stu-id="ffa44-143">**Custom Expression**</span></span>|<span data-ttu-id="ffa44-144">Seleccione esta opción para escribir una expresión personalizada y asignar después un alias a la salida.</span><span class="sxs-lookup"><span data-stu-id="ffa44-144">Select this option to type a custom expression and then assign an alias to the output.</span></span><br /><br /> <span data-ttu-id="ffa44-145">La expresión personalizada se agrega a la parte SELECT de la consulta de predicción resultante DMX.</span><span class="sxs-lookup"><span data-stu-id="ffa44-145">The custom expression is added to the SELECT portion of the resulting DMX prediction query.</span></span><br /><br /> <span data-ttu-id="ffa44-146">Esta opción es útil si desea agregar el texto de la salida a cada fila, llamar a funciones de VB o llamar a procedimientos almacenados personalizados.</span><span class="sxs-lookup"><span data-stu-id="ffa44-146">This option is useful if you want to add text for output with each row, to call VB functions, or to call custom stored procedures.</span></span><br /><br /> <span data-ttu-id="ffa44-147">Para más información sobre cómo usar funciones de Excel y VBA desde DMX, vea [Funciones de VBA en MDX y DAX](/sql/mdx/vba-functions-in-mdx-and-dax).</span><span class="sxs-lookup"><span data-stu-id="ffa44-147">For information about using VBA and Excel functions from DMX, see [VBA functions in MDX and DAX](/sql/mdx/vba-functions-in-mdx-and-dax).</span></span>|  
  
3.  <span data-ttu-id="ffa44-148">Después de agregar cada función o expresión, cambie a la vista DMX para ver cómo se agrega la función dentro de la instrucción DMX.</span><span class="sxs-lookup"><span data-stu-id="ffa44-148">After adding each function or expression, switch to DMX view to see how the function is added within the DMX statement.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="ffa44-149">El generador de consultas de predicción no valida el DMX hasta que haga clic en **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="ffa44-149">The Prediction Query Builder does not validate the DMX until you click **Results**.</span></span> <span data-ttu-id="ffa44-150">A menudo, encontrará que la expresión que genera el generador de consultas DMX es no válida.</span><span class="sxs-lookup"><span data-stu-id="ffa44-150">Often, you will find that the expression that is produced by the query builder is not valid DMX.</span></span> <span data-ttu-id="ffa44-151">Algunas de las causas habituales son que se hace referencia a una columna que no está relacionada con la columna de predicción o bien que se intenta predecir una columna de una tabla anidada, lo que requiere una instrucción sub-SELECT.</span><span class="sxs-lookup"><span data-stu-id="ffa44-151">Typical causes are referencing a column that is not related to the predictable column, or trying to predict a column in a nested table, which requires a sub-SELECT statement.</span></span> <span data-ttu-id="ffa44-152">En este momento puede cambiar a la vista DMX y continuar modificando la instrucción.</span><span class="sxs-lookup"><span data-stu-id="ffa44-152">At this point, you can switch to DMX view and continue editing the statement.</span></span>  
  
### <a name="example-create-a-query-on-a-clustering-model"></a><span data-ttu-id="ffa44-153">Ejemplo: crear una consulta en un modelo de clústeres</span><span class="sxs-lookup"><span data-stu-id="ffa44-153">Example: Create a query on a clustering model</span></span>  
  
1.  <span data-ttu-id="ffa44-154">Si no tiene un modelo de clústeres disponible para crear esta consulta de ejemplo, cree el modelo, [TM_Clustering], con el [Tutorial básico de minería de datos](../../tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ffa44-154">If you do not have a clustering model available for building this sample query, create the model, [TM_Clustering], using the [Basic Data Mining Tutorial](../../tutorials/basic-data-mining-tutorial.md).</span></span>  
  
2.  <span data-ttu-id="ffa44-155">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], haga clic con el botón derecho en el modelo, [TM_Clustering], y seleccione **Generar consulta de predicción**.</span><span class="sxs-lookup"><span data-stu-id="ffa44-155">From [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the model, [TM_Clustering], and select **Build Prediction Query**.</span></span>  
  
3.  <span data-ttu-id="ffa44-156">En el menú **Modelo de minería de datos** , seleccione **Consulta singleton**.</span><span class="sxs-lookup"><span data-stu-id="ffa44-156">From the **Mining Model** menu, select **Singleton Query**.</span></span>  
  
4.  <span data-ttu-id="ffa44-157">En el cuadro de diálogo **Entrada de consulta singleton** , establezca los siguientes valores como entradas:</span><span class="sxs-lookup"><span data-stu-id="ffa44-157">In the **Singleton Query Input** dialog box, set the following values as inputs:</span></span>  
  
    -   <span data-ttu-id="ffa44-158">Gender = M</span><span class="sxs-lookup"><span data-stu-id="ffa44-158">Gender = M</span></span>  
  
    -   <span data-ttu-id="ffa44-159">Commute Distance = 5-10 miles</span><span class="sxs-lookup"><span data-stu-id="ffa44-159">Commute Distance = 5-10 miles</span></span>  
  
5.  <span data-ttu-id="ffa44-160">En la cuadrícula de la consulta, en **Origen**, seleccione el modelo de minería de datos TM_Clustering y agregue la columna [Bike Buyer].</span><span class="sxs-lookup"><span data-stu-id="ffa44-160">In the query grid, for **Source**, select TM_Clustering mining model, and add the column, [Bike Buyer].</span></span>  
  
6.  <span data-ttu-id="ffa44-161">En **origen**, seleccione **función de predicción**y agregue la función `Cluster` .</span><span class="sxs-lookup"><span data-stu-id="ffa44-161">For **Source**, select **Prediction Function**, and add the function, `Cluster`.</span></span>  
  
7.  <span data-ttu-id="ffa44-162">En **origen**, seleccione **función de predicción**, agregue la función, `PredictSupport` , y arrastre la columna modelo [Bike Buyer] al cuadro **criterios o argumento** .</span><span class="sxs-lookup"><span data-stu-id="ffa44-162">For **Source**, select **Prediction Function**, add the function, `PredictSupport`, and drag the model column [Bike Buyer] into the **Criteria/Argument** box.</span></span> <span data-ttu-id="ffa44-163">Escriba **Support** en la columna **Alias** .</span><span class="sxs-lookup"><span data-stu-id="ffa44-163">Type **Support** in the **Alias** column.</span></span>  
  
     <span data-ttu-id="ffa44-164">Copie la expresión que represente la función de predicción y la referencia de columna del cuadro **Criterios y argumento** .</span><span class="sxs-lookup"><span data-stu-id="ffa44-164">Copy the expression representing the prediction function and column reference from the **Criteria/Argument** box.</span></span>  
  
8.  <span data-ttu-id="ffa44-165">En **Origen**, seleccione **Expresión personalizada**, escriba una alias y, después, haga referencia a la función CEILING de Excel utilizando la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="ffa44-165">For **Source**, select **Custom Expression**, type an alias, and then reference the Excel CEILING function by using the following syntax:</span></span>  
  
    ```  
    Excel![CEILING](<arguments) as <return type>  
    ```  
  
     <span data-ttu-id="ffa44-166">Pegue la referencia de columna como argumento de la función.</span><span class="sxs-lookup"><span data-stu-id="ffa44-166">Paste the column reference in as the argument to the function.</span></span>  
  
     <span data-ttu-id="ffa44-167">Por ejemplo, la siguiente expresión devuelve el valor CEILING del valor proporcionado:</span><span class="sxs-lookup"><span data-stu-id="ffa44-167">For example, the following expression returns the CEILING of the support value:</span></span>  
  
    ```  
    EXCEL!CEILING(PredictSupport([TM_Clustering].[Bike Buyer]),2)  
    ```  
  
     <span data-ttu-id="ffa44-168">Escriba CEILING en la columna **Alias** .</span><span class="sxs-lookup"><span data-stu-id="ffa44-168">Type CEILING in the **Alias** column.</span></span>  
  
9. <span data-ttu-id="ffa44-169">Haga clic en **Cambiar a vista de texto de consulta** para revisar la instrucción DMX que se generó y haga clic en **Cambiar a vista de resultado de consulta** para ver el resultado de las columnas de la consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="ffa44-169">Click **Switch to query text view** to review the DMX statement that was generated, and then click **Switch to query result view** to see the columns output by the prediction query.</span></span>  
  
     <span data-ttu-id="ffa44-170">En la tabla siguiente se muestran los resultados esperados:</span><span class="sxs-lookup"><span data-stu-id="ffa44-170">The following table shows the expected results:</span></span>  
  
    |<span data-ttu-id="ffa44-171">Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="ffa44-171">Bike Buyer</span></span>|<span data-ttu-id="ffa44-172">$Cluster</span><span class="sxs-lookup"><span data-stu-id="ffa44-172">$Cluster</span></span>|<span data-ttu-id="ffa44-173">Support</span><span class="sxs-lookup"><span data-stu-id="ffa44-173">SUPPORT</span></span>|<span data-ttu-id="ffa44-174">CEILING</span><span class="sxs-lookup"><span data-stu-id="ffa44-174">CEILING</span></span>|  
    |----------------|--------------|-------------|-------------|  
    |<span data-ttu-id="ffa44-175">0</span><span class="sxs-lookup"><span data-stu-id="ffa44-175">0</span></span>|<span data-ttu-id="ffa44-176">Clúster 8</span><span class="sxs-lookup"><span data-stu-id="ffa44-176">Cluster 8</span></span>|<span data-ttu-id="ffa44-177">954</span><span class="sxs-lookup"><span data-stu-id="ffa44-177">954</span></span>|<span data-ttu-id="ffa44-178">953.948638926372</span><span class="sxs-lookup"><span data-stu-id="ffa44-178">953.948638926372</span></span>|  
  
 <span data-ttu-id="ffa44-179">Si desea agregar otras cláusulas en otra parte de la instrucción, por ejemplo, si desea agregar una cláusula WHERE, no puede agregarla mediante la cuadrícula; primero debe cambiar a la vista DMX.</span><span class="sxs-lookup"><span data-stu-id="ffa44-179">If you want to add other clauses elsewhere in the statement-for example, if you want to add a WHERE clause-you cannot add it by using the grid; you must switch to DMX view first.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa44-180">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ffa44-180">See Also</span></span>  
 [<span data-ttu-id="ffa44-181">Consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="ffa44-181">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
