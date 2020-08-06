---
title: 'Lección 4: ejecutar predicciones de la cesta de la compra | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b3238f1b-ea04-4253-ade2-838a806b62fe
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 3b49fc242eb8b2242269c5af33cc094937bbe0de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671869"
---
# <a name="lesson-4-executing-market-basket-predictions"></a><span data-ttu-id="10012-102">Lección 4: Ejecución de predicciones de cesta de la compra</span><span class="sxs-lookup"><span data-stu-id="10012-102">Lesson 4: Executing Market Basket Predictions</span></span>
  <span data-ttu-id="10012-103">En esta lección, usará la `SELECT` instrucción DMX para crear predicciones basadas en los modelos de asociación que creó en la [Lección 2: agregar modelos de minería de datos a la estructura de minería de datos Market Basket](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="10012-103">In this lesson, you will use the DMX `SELECT` statement to create predictions based on the association models you created in [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="10012-104">Para crear una consulta de predicción se usa la instrucción `SELECT` de DMX y se agrega una cláusula `PREDICTION JOIN`.</span><span class="sxs-lookup"><span data-stu-id="10012-104">A prediction query is created by using the DMX `SELECT` statement and adding a `PREDICTION JOIN` clause.</span></span> <span data-ttu-id="10012-105">Para obtener más información sobre la sintaxis de una combinación de predicción, vea [seleccionar desde &#60;modelo&#62; combinación de predicción &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).</span><span class="sxs-lookup"><span data-stu-id="10012-105">For more information about the syntax of a prediction join, see [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).</span></span>  
  
 <span data-ttu-id="10012-106">El formulario **seleccionar de \<model> combinación de predicción** de la `SELECT` instrucción contiene tres partes:</span><span class="sxs-lookup"><span data-stu-id="10012-106">The **SELECT FROM \<model> PREDICTION JOIN** form of the `SELECT` statement contains three parts:</span></span>  
  
-   <span data-ttu-id="10012-107">Una lista de las funciones de predicción y las columnas del modelo de minería de datos devueltas en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="10012-107">A list of the mining model columns and prediction functions that are returned in the result set.</span></span> <span data-ttu-id="10012-108">Esta lista también puede incluir columnas de entrada de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="10012-108">This list can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="10012-109">Una consulta de origen que define los datos que se usan para crear una predicción.</span><span class="sxs-lookup"><span data-stu-id="10012-109">A source query that defines the data that is being used to create a prediction.</span></span> <span data-ttu-id="10012-110">Por ejemplo, si está creando muchas predicciones en un lote, la consulta de origen podría recuperar una lista de clientes.</span><span class="sxs-lookup"><span data-stu-id="10012-110">For example, if you are creating many predictions in a batch, the source query could retrieve a list of customers.</span></span>  
  
-   <span data-ttu-id="10012-111">Una asignación entre las columnas del modelo de minería de datos y los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="10012-111">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="10012-112">Si los nombres de las columnas coinciden, puede usar la sintaxis `NATURAL PREDICTION JOIN` y omitir las asignaciones de columna.</span><span class="sxs-lookup"><span data-stu-id="10012-112">If the columns names match, you can use the `NATURAL PREDICTION JOIN` syntax and omit the column mappings.</span></span>  
  
 <span data-ttu-id="10012-113">La consulta se puede mejorar si se usan funciones de predicción.</span><span class="sxs-lookup"><span data-stu-id="10012-113">You can enhance the query by using prediction functions.</span></span> <span data-ttu-id="10012-114">Las funciones de predicción proporcionan información adicional, como la probabilidad de que se produzca una predicción o la existencia de compatibilidad con una predicción en el conjunto de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="10012-114">Prediction functions provide additional information, such as the probability of a prediction occurring, or the support for a prediction in the training dataset.</span></span> <span data-ttu-id="10012-115">Para obtener más información sobre las funciones de predicción, consulte [funciones &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="10012-115">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="10012-116">También puede usar el generador de consultas de predicción de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] para crear consultas de predicción.</span><span class="sxs-lookup"><span data-stu-id="10012-116">You can also use the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create prediction queries.</span></span>  
  
## <a name="singleton-prediction-join-statement"></a><span data-ttu-id="10012-117">Instrucción singleton PREDICTION JOIN</span><span class="sxs-lookup"><span data-stu-id="10012-117">Singleton PREDICTION JOIN Statement</span></span>  
 <span data-ttu-id="10012-118">El primer paso consiste en crear una consulta singleton mediante la sintaxis **Select from \<model> PREDICT join** y proporcionar un único conjunto de valores como entrada.</span><span class="sxs-lookup"><span data-stu-id="10012-118">The first step is to create a singleton query, by using the **SELECT FROM \<model> PREDICTION JOIN** syntax and supplying a single set of values as input.</span></span> <span data-ttu-id="10012-119">A continuación, se incluye un ejemplo genérico de la instrucción singleton:</span><span class="sxs-lookup"><span data-stu-id="10012-119">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list>  
    FROM [<mining model>]   
[NATURAL] PREDICTION JOIN  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
AS [<input alias>]  
```  
  
 <span data-ttu-id="10012-120">En la primera línea del código se definen las columnas del modelo de minería de datos que devuelve la consulta y se especifica el nombre del modelo de minería de datos usado para generar la predicción:</span><span class="sxs-lookup"><span data-stu-id="10012-120">The first line of the code defines the columns from the mining model that the query returns, and specifies the name of the mining model used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>]   
```  
  
 <span data-ttu-id="10012-121">La línea del código siguiente indica la operación que se va a realizar.</span><span class="sxs-lookup"><span data-stu-id="10012-121">The next line of the code indicates the operation to perform.</span></span> <span data-ttu-id="10012-122">Dado que se especificarán valores para cada una de las columnas y se escribirán los nombres de columna exactamente de manera que coincidan con el modelo, puede usar la sintaxis `NATURAL PREDICTION JOIN`.</span><span class="sxs-lookup"><span data-stu-id="10012-122">Because you will specify values for each of the columns and type the column names exactly so as to match the model, you can use the `NATURAL PREDICTION JOIN` syntax.</span></span> <span data-ttu-id="10012-123">Sin embargo, si los nombres de columna fueran diferentes, tendría que especificar las asignaciones entre las columnas del modelo y las columnas de los nuevos datos agregando una cláusula `ON`.</span><span class="sxs-lookup"><span data-stu-id="10012-123">However, if the column names were different, you would have to specify mappings between the columns in the model and the columns in the new data by adding an `ON` clause.</span></span>  
  
```  
[NATURAL] PREDICTION JOIN  
```  
  
 <span data-ttu-id="10012-124">En las líneas siguientes del código se definen los artículos del carro de la compra que se utilizarán para predecir artículos adicionales que un cliente agregará:</span><span class="sxs-lookup"><span data-stu-id="10012-124">The next lines of the code define the products in the shopping cart that will be used to predict additional products that a customer will add:</span></span>  
  
```  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="10012-125">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="10012-125">Lesson Tasks</span></span>  
 <span data-ttu-id="10012-126">En esta lección realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="10012-126">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="10012-127">Cree una consulta que prediga qué otros elementos probablemente comprará un cliente, en función de los elementos ya existentes en el carro de la compra.</span><span class="sxs-lookup"><span data-stu-id="10012-127">Create a query that predicts what other items a customer will likely purchase, based on items already existing in their shopping cart.</span></span> <span data-ttu-id="10012-128">Creará esta consulta mediante el modelo de minería de datos con el *MINIMUM_PROBABILITY*predeterminado.</span><span class="sxs-lookup"><span data-stu-id="10012-128">You will create this query by using the mining model with the default *MINIMUM_PROBABILITY*.</span></span>  
  
-   <span data-ttu-id="10012-129">Crear una consulta que prediga qué otros artículos podría adquirir un cliente en función de los artículos que ya se están en su carro de la compra.</span><span class="sxs-lookup"><span data-stu-id="10012-129">Create a query that predicts what other items a customer will likely purchase based on items already existing in their shopping cart.</span></span> <span data-ttu-id="10012-130">Esta consulta se basa en un modelo diferente, en el que *MINIMUM_PROBABILITY* se ha establecido en 0,01.</span><span class="sxs-lookup"><span data-stu-id="10012-130">This query is based on a different model, in which *MINIMUM_PROBABILITY* has been set to 0.01.</span></span> <span data-ttu-id="10012-131">Dado que el valor predeterminado para *MINIMUM_PROBABILITY* en los modelos de asociación es 0,3, la consulta de este modelo debe devolver más elementos posibles que la consulta del modelo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="10012-131">Because the default value for *MINIMUM_PROBABILITY* in association models is 0.3, the query on this model should return more possible items than the query on the default model.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-the-default-minimum_probability"></a><span data-ttu-id="10012-132">Crear una predicción usando un modelo con el valor de MINIMUM_PROBABILITY predeterminado</span><span class="sxs-lookup"><span data-stu-id="10012-132">Create a Prediction by Using a Model with the Default MINIMUM_PROBABILITY</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="10012-133">Para crear una consulta de asociación</span><span class="sxs-lookup"><span data-stu-id="10012-133">To create an association query</span></span>  
  
1.  <span data-ttu-id="10012-134">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX** para abrir el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="10012-134">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="10012-135">Copie el ejemplo genérico de la instrucción `PREDICTION JOIN` en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="10012-135">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="10012-136">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10012-136">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="10012-137">por:</span><span class="sxs-lookup"><span data-stu-id="10012-137">with:</span></span>  
  
    ```  
    PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
     <span data-ttu-id="10012-138">Podría incluir simplemente el nombre de columna [Products], pero mediante la función [PREDICT &#40;DMX&#41;](/sql/dmx/predict-dmx) , puede limitar el número de productos que devuelve el algoritmo a tres.</span><span class="sxs-lookup"><span data-stu-id="10012-138">You could just include the column name [Products], but by using the [Predict &#40;DMX&#41;](/sql/dmx/predict-dmx) function, you can limit the number of products that are returned by the algorithm to three.</span></span> <span data-ttu-id="10012-139">También puede usar `INCLUDE_STATISTICS`, que devuelve la compatibilidad, la probabilidad y la probabilidad ajustada para cada producto.</span><span class="sxs-lookup"><span data-stu-id="10012-139">You can also use `INCLUDE_STATISTICS`, which returns the support, probability, and adjusted probability for each product.</span></span> <span data-ttu-id="10012-140">Estas estadísticas ayudan a valorar la precisión de la predicción.</span><span class="sxs-lookup"><span data-stu-id="10012-140">These statistics help you rate the accuracy of the prediction.</span></span>  
  
4.  <span data-ttu-id="10012-141">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10012-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="10012-142">por:</span><span class="sxs-lookup"><span data-stu-id="10012-142">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="10012-143">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10012-143">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="10012-144">por:</span><span class="sxs-lookup"><span data-stu-id="10012-144">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="10012-145">Esta instrucción utiliza la instrucción `UNION` para especificar tres productos que se deben incluir en el carro de la compra junto con los artículos previstos.</span><span class="sxs-lookup"><span data-stu-id="10012-145">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="10012-146">La columna Model de la instrucción `SELECT` corresponde a la columna de modelo incluida en la tabla de productos anidada.</span><span class="sxs-lookup"><span data-stu-id="10012-146">The Model column in the `SELECT` statement corresponds to the model column that is contained in the nested products table.</span></span>  
  
     <span data-ttu-id="10012-147">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="10012-147">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Default Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="10012-148">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="10012-148">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="10012-149">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="10012-149">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="10012-150">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="10012-150">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="10012-151">La consulta devuelve una tabla que contiene tres productos: HL Mountain Tire, Fender Set - Mountain y ML Mountain Tire.</span><span class="sxs-lookup"><span data-stu-id="10012-151">The query returns a table that contains three products: HL Mountain Tire, Fender Set - Mountain, and ML Mountain Tire.</span></span> <span data-ttu-id="10012-152">En la tabla se enumeran estos productos devueltos por orden de probabilidad.</span><span class="sxs-lookup"><span data-stu-id="10012-152">The table lists these returned products in order of probability.</span></span> <span data-ttu-id="10012-153">En la parte superior de la tabla aparece el producto devuelto con mayor probabilidad de estar incluido en el mismo carro de la compra que los tres productos especificados en la consulta.</span><span class="sxs-lookup"><span data-stu-id="10012-153">The returned product that is most likely to be included in the same shopping cart as the three products specified in the query appears at the top of the table.</span></span> <span data-ttu-id="10012-154">Los dos productos siguientes son los de mayor probabilidad de estar incluidos en el carro de la compra.</span><span class="sxs-lookup"><span data-stu-id="10012-154">The two products that follow are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="10012-155">La tabla también contiene estadísticas que describen la precisión de la predicción.</span><span class="sxs-lookup"><span data-stu-id="10012-155">The table also contains statistics describing the accuracy of the prediction.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-a-minimum_probability-of-001"></a><span data-ttu-id="10012-156">Crear una predicción usando un modelo con el valor 0,01 para MINIMUM_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="10012-156">Create a Prediction by Using a Model with a MINIMUM_PROBABILITY of 0.01</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="10012-157">Para crear una consulta de asociación</span><span class="sxs-lookup"><span data-stu-id="10012-157">To create an association query</span></span>  
  
1.  <span data-ttu-id="10012-158">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX** para abrir el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="10012-158">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="10012-159">Copie el ejemplo genérico de la instrucción `PREDICTION JOIN` en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="10012-159">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="10012-160">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10012-160">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="10012-161">por:</span><span class="sxs-lookup"><span data-stu-id="10012-161">with:</span></span>  
  
    ```  
    PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
4.  <span data-ttu-id="10012-162">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10012-162">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="10012-163">por:</span><span class="sxs-lookup"><span data-stu-id="10012-163">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="10012-164">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10012-164">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="10012-165">por:</span><span class="sxs-lookup"><span data-stu-id="10012-165">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="10012-166">Esta instrucción utiliza la instrucción `UNION` para especificar tres productos que se deben incluir en el carro de la compra junto con los artículos previstos.</span><span class="sxs-lookup"><span data-stu-id="10012-166">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="10012-167">La columna `[Model]` de la instrucción `SELECT` corresponde a la columna incluida en la tabla de artículos anidada.</span><span class="sxs-lookup"><span data-stu-id="10012-167">The `[Model]` column in the `SELECT` statement corresponds to the column in the nested products table.</span></span>  
  
     <span data-ttu-id="10012-168">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="10012-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Modified Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="10012-169">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="10012-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="10012-170">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Modified Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="10012-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="10012-171">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="10012-171">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="10012-172">La consulta devuelve una tabla que contiene tres artículos: HL Mountain Tire, Water Bottle y Fender Set - Mountain.</span><span class="sxs-lookup"><span data-stu-id="10012-172">The query returns a table that contains three products: HL Mountain Tire, Water Bottle, and Fender Set - Mountain.</span></span> <span data-ttu-id="10012-173">En la tabla se enumeran estos productos por orden de probabilidad.</span><span class="sxs-lookup"><span data-stu-id="10012-173">The table lists these products in order of probability.</span></span> <span data-ttu-id="10012-174">El producto que aparece al principio de la tabla es el producto con mayor probabilidad de estar incluido en el mismo carro de la compra que los tres artículos especificados en la consulta.</span><span class="sxs-lookup"><span data-stu-id="10012-174">The product that appears at the top of the table is the product that is most likely to be included in the same shopping cart as the three products specified in the query.</span></span> <span data-ttu-id="10012-175">Los productos restantes son los siguientes con mayor probabilidad de estar incluidos en el carro de la compra.</span><span class="sxs-lookup"><span data-stu-id="10012-175">The remaining products are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="10012-176">La tabla también contiene estadísticas que describen la precisión de la predicción.</span><span class="sxs-lookup"><span data-stu-id="10012-176">The table also contains statistics that describe the accuracy of the prediction.</span></span>  
  
     <span data-ttu-id="10012-177">Puede ver en los resultados de esta consulta que el valor del parámetro *MINIMUM_PROBABILITY* afecta a los resultados devueltos por la consulta.</span><span class="sxs-lookup"><span data-stu-id="10012-177">You can see from the results of this query that the value of the *MINIMUM_PROBABILITY* parameter affects the results returned by the query.</span></span>  
  
 <span data-ttu-id="10012-178">Éste es el último paso del tutorial de Market Basket.</span><span class="sxs-lookup"><span data-stu-id="10012-178">This is the last step in the Market Basket tutorial.</span></span> <span data-ttu-id="10012-179">Ahora dispone de un conjunto de modelos que puede usar para predecir los artículos que los clientes pueden adquirir simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="10012-179">You now have a set of models that you can use to predict the products that customers might purchase at the same time.</span></span>  
  
 <span data-ttu-id="10012-180">Para obtener información sobre cómo usar DMX en otro escenario predictivo, consulte el [tutorial de Bike Buyer DMX](../../2014/tutorials/bike-buyer-dmx-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="10012-180">To learn how to use DMX in another predictive scenario, see [Bike Buyer DMX Tutorial](../../2014/tutorials/bike-buyer-dmx-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10012-181">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10012-181">See Also</span></span>  
 <span data-ttu-id="10012-182">[Ejemplos de consultas de modelos de asociación](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="10012-182">[Association Model Query Examples](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span></span>  
 [<span data-ttu-id="10012-183">Interfaces de consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="10012-183">Data Mining Query Interfaces</span></span>](../../2014/analysis-services/data-mining/data-mining-query-tools.md)  
  
  
