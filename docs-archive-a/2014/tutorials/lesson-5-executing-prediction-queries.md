---
title: 'Lección 5: ejecutar consultas de predicción | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0037bd2f-aa2d-464b-bf86-b0210f0438b1
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a5f4d6dd79f62541e207df688349f694680e2421
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747304"
---
# <a name="lesson-5-executing-prediction-queries"></a><span data-ttu-id="05723-102">Lección 5: Ejecución de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="05723-102">Lesson 5: Executing Prediction Queries</span></span>
  <span data-ttu-id="05723-103">En esta lección, usará la forma [seleccionar de la \<model> combinación de predicción (DMX)](/sql/dmx/select-from-model-cases-dmx) de la instrucción SELECT para crear dos tipos diferentes de predicciones basadas en el modelo de árbol de decisión creado en la [Lección 2: agregar modelos de minería de datos a la estructura de minería de datos de asociación](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="05723-103">In this lesson, you will use the [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement to create two different types of predictions based on the decision tree model you created in [Lesson 2: Adding Mining Models to the Association Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="05723-104">Estos tipos de predicciones se definen a continuación.</span><span class="sxs-lookup"><span data-stu-id="05723-104">These prediction types are defined below.</span></span>  
  
 <span data-ttu-id="05723-105">Consulta singleton</span><span class="sxs-lookup"><span data-stu-id="05723-105">Singleton Query</span></span>  
 <span data-ttu-id="05723-106">Use una consulta singleton para proporcionar valores ad hoc al realizar predicciones.</span><span class="sxs-lookup"><span data-stu-id="05723-106">Use a singleton query to provide ad hoc values when making predictions.</span></span> <span data-ttu-id="05723-107">Por ejemplo, puede determinar si es probable que un cliente sea un comprador de bicicletas pasando entradas a la consulta, como la distancia al lugar de trabajo, el prefijo telefónico o el número de hijos del cliente.</span><span class="sxs-lookup"><span data-stu-id="05723-107">For example, you can determine whether a single customer is likely to be a bike buyer, by passing inputs to the query such as the commute distance, the area code, or the number of children of the customer.</span></span> <span data-ttu-id="05723-108">La consulta singleton devuelve un valor que indica la probabilidad de que la persona compre una bicicleta basándose en esas entradas.</span><span class="sxs-lookup"><span data-stu-id="05723-108">The singleton query returns a value that indicates how likely the person is to purchase a bicycle based on those inputs.</span></span>  
  
 <span data-ttu-id="05723-109">Consulta por lotes</span><span class="sxs-lookup"><span data-stu-id="05723-109">Batch Query</span></span>  
 <span data-ttu-id="05723-110">Utilice una consulta por lotes para determinar qué clientes potenciales incluidos en una tabla es probable que adquieran una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="05723-110">Use a batch query to determine who in a table of potential customers is likely to purchase a bicycle.</span></span> <span data-ttu-id="05723-111">Por ejemplo, si el departamento de marketing le proporciona una lista de clientes y atributos de clientes, puede utilizar una predicción por lotes para determinar qué clientes de la tabla es probable que adquieran una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="05723-111">For example, if your marketing department provides you with a list of customers and customer attributes, then you can use a batch prediction to determine who from the table is likely to purchase a bicycle.</span></span>  
  
 <span data-ttu-id="05723-112">La forma [seleccionar de la \<model> combinación de predicción (DMX)](/sql/dmx/select-from-model-cases-dmx) de la instrucción SELECT contiene tres partes:</span><span class="sxs-lookup"><span data-stu-id="05723-112">The [SELECT FROM \<model> PREDICTION JOIN (DMX)](/sql/dmx/select-from-model-cases-dmx) form of the SELECT statement contains three parts:</span></span>  
  
-   <span data-ttu-id="05723-113">Una lista de las funciones de predicción y las columnas del modelo de minería de datos devueltas en los resultados.</span><span class="sxs-lookup"><span data-stu-id="05723-113">A list of the mining model columns and prediction functions that are returned in the results.</span></span> <span data-ttu-id="05723-114">Los resultados también pueden incluir columnas de entrada de los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="05723-114">The results can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="05723-115">La consulta de origen que define los datos que se utilizan para crear una predicción.</span><span class="sxs-lookup"><span data-stu-id="05723-115">The source query defining the data that is being used to create a prediction.</span></span> <span data-ttu-id="05723-116">Por ejemplo, en una consulta por lotes, podría ser una lista de clientes.</span><span class="sxs-lookup"><span data-stu-id="05723-116">For example, in a batch query this could be a list of customers.</span></span>  
  
-   <span data-ttu-id="05723-117">Una asignación entre las columnas del modelo de minería de datos y los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="05723-117">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="05723-118">Si los nombres coinciden, puede utilizar la sintaxis NATURAL y no incluir las asignaciones de columnas.</span><span class="sxs-lookup"><span data-stu-id="05723-118">If these names match, then you can use NATURAL syntax and leave out the column mappings.</span></span>  
  
 <span data-ttu-id="05723-119">La consulta se puede mejorar aún más si se utilizan funciones de predicción.</span><span class="sxs-lookup"><span data-stu-id="05723-119">You can further enhance the query by using prediction functions.</span></span> <span data-ttu-id="05723-120">Las funciones de predicción proporcionan información adicional como, por ejemplo, la probabilidad de que se produzca una predicción, y ofrecen compatibilidad con la predicción en el conjunto de datos de entrenamiento.</span><span class="sxs-lookup"><span data-stu-id="05723-120">Prediction functions provide additional information, such as the probability of a prediction occurring, and provide support for the prediction in the training dataset.</span></span> <span data-ttu-id="05723-121">Para obtener más información sobre las funciones de predicción, consulte [funciones &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="05723-121">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="05723-122">Las predicciones de este tutorial se basan en la tabla ProspectiveBuyer de la base de datos de ejemplo [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05723-122">The predictions in this tutorial are based on the ProspectiveBuyer table in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database.</span></span> <span data-ttu-id="05723-123">La tabla ProspectiveBuyer contiene una lista de clientes potenciales y de sus características asociadas.</span><span class="sxs-lookup"><span data-stu-id="05723-123">The ProspectiveBuyer table contains a list of potential customers and their associated characteristics.</span></span> <span data-ttu-id="05723-124">Los clientes de esta tabla son independientes de los clientes utilizados para crear el modelo de minería de datos del árbol de decisión.</span><span class="sxs-lookup"><span data-stu-id="05723-124">The customers in this table are independent of the customers that were used to create the decision tree mining model.</span></span>  
  
 <span data-ttu-id="05723-125">También se pueden crear predicciones usando el generador de consultas de predicción de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05723-125">You can also create predictions by using the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="05723-126">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="05723-126">Lesson Tasks</span></span>  
 <span data-ttu-id="05723-127">En esta lección realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="05723-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="05723-128">Crear una consulta singleton para determinar si es probable que un cliente específico adquiera una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="05723-128">Create a singleton query to determine whether a specific customer is likely to purchase a bicycle.</span></span>  
  
-   <span data-ttu-id="05723-129">Crear una consulta por lotes para determinar qué clientes de los incluidos en una tabla es probable que adquieran una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="05723-129">Create a batch query to determine which customers, listed in a table of customers, are likely to purchase a bicycle.</span></span>  
  
## <a name="singleton-query"></a><span data-ttu-id="05723-130">Consulta singleton</span><span class="sxs-lookup"><span data-stu-id="05723-130">Singleton Query</span></span>  
 <span data-ttu-id="05723-131">El primer paso es usar el [modelo SELECT FROM &#60;&#62; combinación de predicción &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) en una consulta de predicción singleton.</span><span class="sxs-lookup"><span data-stu-id="05723-131">The first step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a singleton prediction query.</span></span> <span data-ttu-id="05723-132">A continuación, se incluye un ejemplo genérico de la instrucción singleton:</span><span class="sxs-lookup"><span data-stu-id="05723-132">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
```  
  
 <span data-ttu-id="05723-133">En la primera línea del código se definen las columnas del modelo de minería de datos que debe devolver la consulta y se especifica el modelo de minería de datos usado para generar la predicción:</span><span class="sxs-lookup"><span data-stu-id="05723-133">The first line of the code defines the columns from the mining model that the query should return, and specifies the mining model that is used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model name>]   
```  
  
 <span data-ttu-id="05723-134">En las líneas siguientes del código se definen las características del cliente que se utilizan para crear una predicción:</span><span class="sxs-lookup"><span data-stu-id="05723-134">The next lines of the code define the characteristics of the customer that you use to create a prediction:</span></span>  
  
```  
NATURAL PREDICTION JOIN  
(SELECT '<value>' AS [<column>], ...)  
AS [<input alias>]  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="05723-135">Si especifica NATURAL PREDICTION JOIN, el servidor compara los nombres de cada columna del modelo con los nombres de las columnas de los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="05723-135">If you specify NATURAL PREDICTION JOIN, the server matches each column from the model to a column from the input, based on column names.</span></span> <span data-ttu-id="05723-136">Si los nombres de columna no coinciden, las columnas se omiten.</span><span class="sxs-lookup"><span data-stu-id="05723-136">If column names do not match, the columns are ignored.</span></span>  
  
#### <a name="to-create-a-singleton-prediction-query"></a><span data-ttu-id="05723-137">Para crear una consulta de predicción singleton</span><span class="sxs-lookup"><span data-stu-id="05723-137">To create a singleton prediction query</span></span>  
  
1.  <span data-ttu-id="05723-138">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="05723-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="05723-139">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="05723-139">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="05723-140">Copie el ejemplo genérico de la instrucción singleton en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="05723-140">Copy the generic example of the singleton statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="05723-141">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="05723-141">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="05723-142">por:</span><span class="sxs-lookup"><span data-stu-id="05723-142">with:</span></span>  
  
    ```  
    [Bike Buyer] AS Buyer, PredictHistogram([Bike Buyer]) AS Statistics  
    ```  
  
     <span data-ttu-id="05723-143">La instrucción AS se utiliza para asignar un alias a las columnas devueltas por la consulta.</span><span class="sxs-lookup"><span data-stu-id="05723-143">The AS statement is used to alias columns returned by the query.</span></span> <span data-ttu-id="05723-144">La función [PredictHistogram](/sql/dmx/predicthistogram-dmx) devuelve estadísticas sobre la predicción, incluida la probabilidad y la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="05723-144">The [PredictHistogram](/sql/dmx/predicthistogram-dmx) function returns statistics about the prediction, including the probability and the support.</span></span> <span data-ttu-id="05723-145">Para obtener más información sobre las funciones que se pueden usar en una instrucción de predicción, consulte [funciones &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="05723-145">For more information about the functions that can be used in a prediction statement, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
4.  <span data-ttu-id="05723-146">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="05723-146">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="05723-147">por:</span><span class="sxs-lookup"><span data-stu-id="05723-147">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="05723-148">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="05723-148">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column name>], ...)  AS t  
    ```  
  
     <span data-ttu-id="05723-149">por:</span><span class="sxs-lookup"><span data-stu-id="05723-149">with:</span></span>  
  
    ```  
    (SELECT 35 AS [Age],  
      '5-10 Miles' AS [Commute Distance],  
      '1' AS [House Owner Flag],  
      2 AS [Number Cars Owned],  
      2 AS [Total Children]) AS t  
    ```  
  
     <span data-ttu-id="05723-150">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="05723-150">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
       [Bike Buyer] AS Buyer,  
       PredictHistogram([Bike Buyer]) AS Statistics  
    FROM  
       [Decision Tree]  
    NATURAL PREDICTION JOIN  
    (SELECT 35 AS [Age],  
       '5-10 Miles' AS [Commute Distance],  
       '1' AS [House Owner Flag],  
       2 AS [Number Cars Owned],  
       2 AS [Total Children]) AS t  
    ```  
  
6.  <span data-ttu-id="05723-151">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="05723-151">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="05723-152">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Singleton_Query.dmx` .</span><span class="sxs-lookup"><span data-stu-id="05723-152">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Singleton_Query.dmx`.</span></span>  
  
8.  <span data-ttu-id="05723-153">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="05723-153">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="05723-154">La consulta devuelve una predicción acerca de si un cliente con las características especificadas adquirirá una bicicleta, así como estadísticas acerca de la predicción.</span><span class="sxs-lookup"><span data-stu-id="05723-154">The query returns a prediction about whether a customer with the specified characteristics will purchase a bicycle, as well as statistics about that prediction.</span></span>  
  
## <a name="batch-query"></a><span data-ttu-id="05723-155">Consulta por lotes</span><span class="sxs-lookup"><span data-stu-id="05723-155">Batch Query</span></span>  
 <span data-ttu-id="05723-156">El siguiente paso consiste en usar el [modelo SELECT FROM &#60;&#62; combinación de predicción &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) en una consulta de predicción por lotes.</span><span class="sxs-lookup"><span data-stu-id="05723-156">The next step is to use the [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx) in a batch prediction query.</span></span> <span data-ttu-id="05723-157">A continuación, se incluye un ejemplo genérico de una instrucción por lotes:</span><span class="sxs-lookup"><span data-stu-id="05723-157">The following is a generic example of a batch statement:</span></span>  
  
```  
SELECT TOP <number> <select list>   
FROM [<mining model name>]  
PREDICTION JOIN  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
ON <on clause, mapping,>  
WHERE <where clause, boolean expression,>  
ORDER BY <expression>  
```  
  
 <span data-ttu-id="05723-158">Como en la consulta singleton, en las dos primeras líneas del código se definen las columnas del modelo de minería de datos devueltas por la consulta, así como el nombre del modelo de minería de datos utilizado para generar la predicción.</span><span class="sxs-lookup"><span data-stu-id="05723-158">As in the singleton query, the first two lines of the code define the columns from mining model that the query returns, as well as the name of the mining model that is used to generate the prediction.</span></span> <span data-ttu-id="05723-159">La \<number> instrucción Top especifica que la consulta solo devolverá el número o los resultados especificados por \<number> .</span><span class="sxs-lookup"><span data-stu-id="05723-159">The TOP \<number> statement specifies that the query will only return the number or the results specified by \<number>.</span></span>  
  
 <span data-ttu-id="05723-160">En las líneas siguientes del código se definen los datos de origen en los que se basan las predicciones:</span><span class="sxs-lookup"><span data-stu-id="05723-160">The next lines of the code define the source data that the predictions are based on:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
  AS [<input alias>]  
```  
  
 <span data-ttu-id="05723-161">En cuanto al método utilizado para recuperar los datos de origen, hay varias opciones, pero en este tutorial se usará OPENQUERY.</span><span class="sxs-lookup"><span data-stu-id="05723-161">You have several options for the method of retrieving the source data, but in this tutorial, you will use OPENQUERY.</span></span> <span data-ttu-id="05723-162">Para obtener más información sobre las opciones disponibles, vea [&#60;&#62;de consultas de datos de origen ](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="05723-162">For more information about the options available, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
 <span data-ttu-id="05723-163">En la línea siguiente se definen la asignación entre las columnas de origen del modelo de minería de datos y las columnas de los datos de origen:</span><span class="sxs-lookup"><span data-stu-id="05723-163">The next line defines the mapping between the source columns in the mining model and the columns in the source data:</span></span>  
  
```  
ON <column mappings>  
```  
  
 <span data-ttu-id="05723-164">La cláusula WHERE filtra los resultados devueltos por la consulta de predicción:</span><span class="sxs-lookup"><span data-stu-id="05723-164">The WHERE clause filters the results returned by the prediction query:</span></span>  
  
```  
WHERE <where clause, boolean expression,>  
```  
  
 <span data-ttu-id="05723-165">En la última línea del código, que es opcional, se especifica la columna por la cual se ordenarán los resultados:</span><span class="sxs-lookup"><span data-stu-id="05723-165">The last and optional line of the code specifies the column that the results will be ordered by:</span></span>  
  
```  
ORDER BY <expression> [DESC|ASC]  
```  
  
 <span data-ttu-id="05723-166">Utilice ORDER BY en combinación con la \<number> instrucción Top para filtrar los resultados que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="05723-166">Use ORDER BY in combination with the TOP \<number> statement, to filter the results that are returned.</span></span> <span data-ttu-id="05723-167">Por ejemplo, en esta predicción se devolverán los diez principales compradores de bicicletas, ordenados por la probabilidad de que la predicción sea correcta.</span><span class="sxs-lookup"><span data-stu-id="05723-167">For example, in this prediction you will return the top ten bike buyers, ordered by the probability of the prediction being correct.</span></span> <span data-ttu-id="05723-168">Puede utilizar la sintaxis [DESC|ASC] para controlar el orden en el que aparecen los resultados.</span><span class="sxs-lookup"><span data-stu-id="05723-168">You can use [DESC|ASC] syntax to control the order in which the results are displayed.</span></span>  
  
#### <a name="to-create-a-batch-prediction-query"></a><span data-ttu-id="05723-169">Para crear una consulta de predicción por lotes</span><span class="sxs-lookup"><span data-stu-id="05723-169">To create a batch prediction query</span></span>  
  
1.  <span data-ttu-id="05723-170">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="05723-170">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="05723-171">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="05723-171">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="05723-172">Copie el ejemplo genérico de la instrucción por lotes en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="05723-172">Copy the generic example of the batch statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="05723-173">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="05723-173">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="05723-174">por:</span><span class="sxs-lookup"><span data-stu-id="05723-174">with:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    ```  
  
     <span data-ttu-id="05723-175">La cláusula TOP 10 especifica que la consulta solo devolverá los diez primeros resultados.</span><span class="sxs-lookup"><span data-stu-id="05723-175">The TOP 10 clause specifies that only the top ten results will be returned by the query.</span></span> <span data-ttu-id="05723-176">La instrucción ORDER BY de esta consulta ordena los resultados según la probabilidad de que la predicción sea correcta, por lo que solo se devolverán los diez resultados más probables.</span><span class="sxs-lookup"><span data-stu-id="05723-176">The ORDER BY statement in this query orders the results by the probability of the prediction being correct, so only the ten most likely results will be returned.</span></span>  
  
4.  <span data-ttu-id="05723-177">Reemplace el marcador de posición siguiente:</span><span class="sxs-lookup"><span data-stu-id="05723-177">Replace the following placeholder:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="05723-178">Con el nombre del modelo:</span><span class="sxs-lookup"><span data-stu-id="05723-178">With the name of the model:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="05723-179">Reemplace la instrucción OPENQUERY genérica siguiente:</span><span class="sxs-lookup"><span data-stu-id="05723-179">Replace the following generic OPENQUERY statement:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="05723-180">Con una instrucción que haga referencia al almacenamiento de datos Adventureworks actual, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="05723-180">With a statement that references the current Adventureworks data warehouse, such as:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW 2014],  
      'SELECT  
        [LastName],  
        [FirstName],  
        [MaritalStatus],  
        [Gender],  
        [YearlyIncome],  
        [TotalChildren],  
        [NumberChildrenAtHome],  
        [Education],  
        [Occupation],  
        [HouseOwnerFlag],  
        [NumberCarsOwned]  
      FROM  
        [dbo].[ProspectiveBuyer]  
      ') AS t  
    ```  
  
6.  <span data-ttu-id="05723-181">Reemplace la sintaxis genérica siguiente:</span><span class="sxs-lookup"><span data-stu-id="05723-181">Replace the following generic syntax:</span></span>  
  
    ```  
    <ON clause, mapping,>   
    WHERE <where clause, boolean expression,>  
    ORDER BY <expression>  
    ```  
  
     <span data-ttu-id="05723-182">Con las asignaciones de columna necesarias para este modelo y conjunto de datos de entrada:</span><span class="sxs-lookup"><span data-stu-id="05723-182">With the column mappings needed for this model and input data set:</span></span>  
  
    ```  
    [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
     <span data-ttu-id="05723-183">Especifique `DESC` para que los resultados con la probabilidad más alta aparezcan primero en la lista.</span><span class="sxs-lookup"><span data-stu-id="05723-183">Specify `DESC` in order to list the results with the highest probability first.</span></span>  
  
     <span data-ttu-id="05723-184">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="05723-184">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      TOP 10  
      t.[LastName],  
      t.[FirstName],  
      [Decision Tree].[Bike Buyer],  
      PredictProbability([Bike Buyer])  
    FROM  
      [Decision Tree]  
    PREDICTION JOIN  
      OPENQUERY([Adventure Works DW 2014],  
        'SELECT  
          [LastName],  
          [FirstName],  
          [MaritalStatus],  
          [Gender],  
          [YearlyIncome],  
          [TotalChildren],  
          [NumberChildrenAtHome],  
          [Education],  
          [Occupation],  
          [HouseOwnerFlag],  
          [NumberCarsOwned]  
        FROM  
          [dbo].[ProspectiveBuyer]  
        ') AS t  
    ON  
      [Decision Tree].[Marital Status] = t.[MaritalStatus] AND  
      [Decision Tree].[Gender] = t.[Gender] AND  
      [Decision Tree].[Yearly Income] = t.[YearlyIncome] AND  
      [Decision Tree].[Total Children] = t.[TotalChildren] AND  
      [Decision Tree].[Number Children At Home] = t.[NumberChildrenAtHome] AND  
      [Decision Tree].[Education] = t.[Education] AND  
      [Decision Tree].[Occupation] = t.[Occupation] AND  
      [Decision Tree].[House Owner Flag] = t.[HouseOwnerFlag] AND  
      [Decision Tree].[Number Cars Owned] = t.[NumberCarsOwned]  
    WHERE [Decision Tree].[Bike Buyer] =1  
    ORDER BY PredictProbability([Bike Buyer]) DESC  
    ```  
  
7.  <span data-ttu-id="05723-185">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="05723-185">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="05723-186">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Batch_Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="05723-186">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Batch_Prediction.dmx`.</span></span>  
  
9. <span data-ttu-id="05723-187">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="05723-187">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="05723-188">La consulta devuelve una tabla que contiene nombres de cliente, una predicción acerca de si cada cliente adquirirá una bicicleta y la probabilidad de la predicción.</span><span class="sxs-lookup"><span data-stu-id="05723-188">The query returns a table containing customer names, a prediction of whether each customer will purchase a bicycle, and the probability of the prediction.</span></span>  
  
 <span data-ttu-id="05723-189">Éste es el último paso del tutorial de Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="05723-189">This is the last step in the Bike Buyer tutorial.</span></span> <span data-ttu-id="05723-190">Ahora dispone de un conjunto de modelos de minería de datos que puede utilizar para explorar las similitudes entre sus clientes y predecir si los clientes potenciales adquirirán una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="05723-190">You now have a set of mining models that you can use to explore similarities between you customers and predict whether potential customers will purchase a bicycle.</span></span>  
  
 <span data-ttu-id="05723-191">Para obtener información sobre cómo usar DMX en un escenario de cesta de la compra, consulte el [tutorial DMX](../../2014/tutorials/market-basket-dmx-tutorial.md)de la cesta de la compra.</span><span class="sxs-lookup"><span data-stu-id="05723-191">To learn how to use DMX in a Market Basket scenario, see [Market Basket DMX Tutorial](../../2014/tutorials/market-basket-dmx-tutorial.md).</span></span>  
  
  
