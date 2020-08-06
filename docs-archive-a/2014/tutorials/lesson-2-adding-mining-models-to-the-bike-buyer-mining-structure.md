---
title: 'Lección 2: agregar modelos de minería de datos a la estructura de minería de datos Bike Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 03fe44c5-6452-4ed0-95f6-9682670c0f52
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: de65fb7a85154f607cd8f266faec4621cdc41476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746648"
---
# <a name="lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure"></a><span data-ttu-id="641b7-102">Lección 2: Adición de modelos de minería de datos a la estructura de minería de datos de Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="641b7-102">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="641b7-103">En esta lección, agregará dos modelos de minería de datos a la estructura de minería de datos Bike Buyer que creó [la lección 1: creación de la estructura de minería de datos Bike Buyer](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="641b7-103">In this lesson, you will add two mining models to the Bike Buyer mining structure that you created [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md).</span></span> <span data-ttu-id="641b7-104">Estos modelos de minería de datos le permitirán explorar los datos usando un modelo y crear predicciones usando otro modelo.</span><span class="sxs-lookup"><span data-stu-id="641b7-104">These mining models will allow you to explore the data using one model, and to create predictions using another.</span></span>  
  
 <span data-ttu-id="641b7-105">Para explorar cómo se pueden clasificar los clientes potenciales por sus características, creará un modelo de minería de datos basado en el [algoritmo de clústeres de Microsoft](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="641b7-105">To explore how potential customers can be categorized by their characteristics, you will create a mining model based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span> <span data-ttu-id="641b7-106">En una lección posterior, explorará cómo este algoritmo encuentra clústeres de clientes que comparten características parecidas.</span><span class="sxs-lookup"><span data-stu-id="641b7-106">In a later lesson, you will explore how this algorithm finds clusters of customers who share similar characteristics.</span></span> <span data-ttu-id="641b7-107">Por ejemplo, podría averiguar que ciertos clientes tienden a vivir cerca unos de otros, van al trabajo en bicicleta y tienen una formación parecida.</span><span class="sxs-lookup"><span data-stu-id="641b7-107">For example, you might find that certain customers tend to live close to each other, commute by bicycle, and have similar education backgrounds.</span></span> <span data-ttu-id="641b7-108">Puede utilizar estos clústeres para comprender mejor cómo están relacionados distintos clientes y para utilizar la información para crear una estrategia de marketing dirigida a clientes concretos.</span><span class="sxs-lookup"><span data-stu-id="641b7-108">You can use these clusters to better understand how different customers are related, and to use the information to create a marketing strategy that targets specific customers.</span></span>  
  
 <span data-ttu-id="641b7-109">Para predecir si es probable que un posible cliente compre una bicicleta, creará un modelo de minería de datos basado en el [algoritmo de árboles de decisión de Microsoft](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="641b7-109">To predict whether a potential customer is likely to buy a bicycle, you will create a mining model based on the [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="641b7-110">Este algoritmo examina la información asociada a cada cliente potencial y encuentra características útiles para predecir si adquirirá una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="641b7-110">This algorithm looks through the information that is associated with each potential customer, and finds characteristics that are useful in predicting if they will buy a bicycle.</span></span> <span data-ttu-id="641b7-111">A continuación, compara los valores de las características de compradores de bicicletas anteriores con los nuevos clientes potenciales para determinar si es probable que éstos adquieran una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="641b7-111">It then compares the values of the characteristics of previous bike buyers against new potential customers to determine whether the new potential customers are likely to buy a bicycle.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="641b7-112">Instrucción ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="641b7-112">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="641b7-113">Para agregar un modelo de minería de datos a la estructura de minería de datos, use la instrucción [ALTER Mining structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="641b7-113">In order to add a mining model to the mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="641b7-114">El código de la instrucción se puede dividir en las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="641b7-114">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="641b7-115">Identificación de la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="641b7-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="641b7-116">Asignación de un nombre al modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="641b7-116">Naming the mining model</span></span>  
  
-   <span data-ttu-id="641b7-117">Definición de la columna de clave</span><span class="sxs-lookup"><span data-stu-id="641b7-117">Defining the key column</span></span>  
  
-   <span data-ttu-id="641b7-118">Definición de las columnas de entrada y de predicción</span><span class="sxs-lookup"><span data-stu-id="641b7-118">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="641b7-119">Identificación de los cambios de parámetros y el algoritmo</span><span class="sxs-lookup"><span data-stu-id="641b7-119">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="641b7-120">A continuación, se incluye un ejemplo genérico de la instrucción ALTER MINING MODEL:</span><span class="sxs-lookup"><span data-stu-id="641b7-120">The following is a generic example of the ALTER MINING MODEL statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
(  
    [<key column>],  
    <mining model columns>,  
) USING <algorithm name>( <algorithm parameters> )  
WITH FILTER (<expression>)  
```  
  
 <span data-ttu-id="641b7-121">La primera línea de código identifica la estructura de minería de datos existente a la que se agregarán los modelos de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="641b7-121">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="641b7-122">La siguiente línea de código asigna un nombre al modelo de minería de datos que se agregará a la estructura de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="641b7-122">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="641b7-123">Para obtener información sobre cómo asignar un nombre a un objeto en DMX, consulte [identifiers &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="641b7-123">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="641b7-124">Las líneas siguientes del código definen columnas de la estructura de minería de datos que utilizará el modelo de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="641b7-124">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns>  
```  
  
 <span data-ttu-id="641b7-125">Solo puede utilizar columnas que ya existan en la estructura de minería de datos, y la primera columna de la lista debe ser la columna de clave de la estructura.</span><span class="sxs-lookup"><span data-stu-id="641b7-125">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="641b7-126">La siguiente línea de código define el algoritmo de minería de datos que genera el modelo de minería de datos y los parámetros de algoritmo que pueden establecerse:</span><span class="sxs-lookup"><span data-stu-id="641b7-126">The next line of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm:</span></span>  
  
```  
) USING <algorithm name>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="641b7-127">Para obtener más información acerca de los parámetros de algoritmo que puede ajustar, vea [algoritmo de árboles de decisión de Microsoft](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) y algoritmo de [clústeres de Microsoft](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="641b7-127">For more information about the algorithm parameters that you can adjust, see [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) and [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span>  
  
 <span data-ttu-id="641b7-128">Puede especificar que una columna del modelo de minería de datos se utilice para la predicción mediante la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="641b7-128">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
 <span data-ttu-id="641b7-129">La última línea de código, que es opcional, define un filtro que se aplica durante el aprendizaje y prueba del modelo.</span><span class="sxs-lookup"><span data-stu-id="641b7-129">The final line of the code, which is optional, defines a filter that is applied when training and testing the model.</span></span> <span data-ttu-id="641b7-130">Para obtener más información sobre cómo aplicar filtros a los modelos de minería de datos, vea [filtros para modelos de minería de datos &#40;Analysis Services-&#41;de minería de datos ](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="641b7-130">For more information about how to apply filters to mining models, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="641b7-131">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="641b7-131">Lesson Tasks</span></span>  
 <span data-ttu-id="641b7-132">En esta lección realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="641b7-132">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="641b7-133">Agregar un modelo de minería de datos del árbol de decisión a la estructura Bike Buyer mediante el algoritmo Árboles de decisión de [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="641b7-133">Add a decision tree mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm</span></span>  
  
-   <span data-ttu-id="641b7-134">Agregar un modelo de minería de datos de agrupación en clústeres a la estructura Bike Buyer mediante el algoritmo de clústeres de [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="641b7-134">Add a clustering mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm</span></span>  
  
-   <span data-ttu-id="641b7-135">Dado que desean verse los resultados para todos los casos, todavía no se agrega un filtro a ningún modelo.</span><span class="sxs-lookup"><span data-stu-id="641b7-135">Because you want to see results for all cases, you will not yet add a filter to either model.</span></span>  
  
## <a name="adding-a-decision-tree-mining-model-to-the-structure"></a><span data-ttu-id="641b7-136">Agregar un modelo de minería de datos de árbol de decisión a la estructura</span><span class="sxs-lookup"><span data-stu-id="641b7-136">Adding a Decision Tree Mining Model to the Structure</span></span>  
 <span data-ttu-id="641b7-137">El primer paso es agregar un modelo de minería de datos basado en el algoritmo Árboles de decisión de [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="641b7-137">The first step is to add a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
#### <a name="to-add-a-decision-tree-mining-model"></a><span data-ttu-id="641b7-138">Para agregar un modelo de minería de datos del árbol de decisión</span><span class="sxs-lookup"><span data-stu-id="641b7-138">To add a decision tree mining model</span></span>  
  
1.  <span data-ttu-id="641b7-139">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX** para abrir el editor de consultas y una nueva consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="641b7-139">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="641b7-140">Copie el ejemplo genérico de la instrucción ALTER MINING STRUCTURE en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="641b7-140">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="641b7-141">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="641b7-141">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="641b7-142">por:</span><span class="sxs-lookup"><span data-stu-id="641b7-142">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="641b7-143">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="641b7-143">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="641b7-144">por:</span><span class="sxs-lookup"><span data-stu-id="641b7-144">with:</span></span>  
  
    ```  
    Decision Tree  
    ```  
  
5.  <span data-ttu-id="641b7-145">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="641b7-145">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    ```  
  
     <span data-ttu-id="641b7-146">por:</span><span class="sxs-lookup"><span data-stu-id="641b7-146">with:</span></span>  
  
    ```  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ```  
  
     <span data-ttu-id="641b7-147">En este caso, la columna `[Bike Buyer]` se ha designado como columna PREDICT.</span><span class="sxs-lookup"><span data-stu-id="641b7-147">In this case, the `[Bike Buyer]` column has been designated as the PREDICT column.</span></span>  
  
6.  <span data-ttu-id="641b7-148">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="641b7-148">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )   
    ```  
  
     <span data-ttu-id="641b7-149">por:</span><span class="sxs-lookup"><span data-stu-id="641b7-149">with:</span></span>  
  
    ```  
    Using Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="641b7-150">La instrucción WITH DRILLTHROUGH permite explorar los casos utilizados para generar el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="641b7-150">The WITH DRILLTHROUGH statement allows you to explore the cases that were used to build the mining model.</span></span>  
  
     <span data-ttu-id="641b7-151">Ahora, la instrucción resultante debería ser como sigue:</span><span class="sxs-lookup"><span data-stu-id="641b7-151">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Decision Tree]  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ) USING Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
7.  <span data-ttu-id="641b7-152">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="641b7-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="641b7-153">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `DT_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="641b7-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `DT_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="641b7-154">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="641b7-154">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-a-clustering-mining-model-to-the-structure"></a><span data-ttu-id="641b7-155">Agregar un modelo de minería de datos de agrupación en clústeres a la estructura</span><span class="sxs-lookup"><span data-stu-id="641b7-155">Adding a Clustering Mining Model to the Structure</span></span>  
 <span data-ttu-id="641b7-156">A continuación, podrá agregar un modelo de minería de datos a la estructura de minería de datos Bike Buyer basado en el algoritmo de clústeres de [!INCLUDE[msCoName](../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="641b7-156">You can now add a mining model to the Bike Buyer mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span> <span data-ttu-id="641b7-157">Puesto que el modelo de minería de datos de agrupación en clústeres utilizará todas las columnas definidas en la estructura de minería de datos, puede utilizar un acceso directo para agregar el modelo a la estructura sin incluir la definición de las columnas de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="641b7-157">Because the clustering mining model will use all the columns defined in the mining structure, you can use a shortcut to add the model to the structure by omitting the definition of the mining columns.</span></span>  
  
#### <a name="to-add-a-clustering-mining-model"></a><span data-ttu-id="641b7-158">Para agregar un modelo de minería de datos de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="641b7-158">To add a Clustering mining model</span></span>  
  
1.  <span data-ttu-id="641b7-159">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX** para abrir el editor de consultas y una nueva consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="641b7-159">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor opens and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="641b7-160">Copie el ejemplo genérico de la instrucción ALTER MINING STRUCTURE en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="641b7-160">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="641b7-161">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="641b7-161">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="641b7-162">por:</span><span class="sxs-lookup"><span data-stu-id="641b7-162">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="641b7-163">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="641b7-163">Replace the following:</span></span>  
  
    ```  
    <mining model>   
    ```  
  
     <span data-ttu-id="641b7-164">por:</span><span class="sxs-lookup"><span data-stu-id="641b7-164">with:</span></span>  
  
    ```  
    Clustering Model  
    ```  
  
5.  <span data-ttu-id="641b7-165">Elimine lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="641b7-165">Delete the following:</span></span>  
  
    ```  
    (  
        [<key column>],  
        <mining model columns>,  
    )  
    ```  
  
6.  <span data-ttu-id="641b7-166">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="641b7-166">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="641b7-167">por:</span><span class="sxs-lookup"><span data-stu-id="641b7-167">with:</span></span>  
  
    ```  
    USING Microsoft_Clustering  
    ```  
  
     <span data-ttu-id="641b7-168">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="641b7-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Clustering]  
    USING Microsoft_Clustering   
    ```  
  
7.  <span data-ttu-id="641b7-169">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="641b7-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="641b7-170">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Clustering_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="641b7-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Clustering_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="641b7-171">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="641b7-171">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="641b7-172">En la siguiente lección procesará los modelos y la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="641b7-172">In the next lesson, you will process the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="641b7-173">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="641b7-173">Next Lesson</span></span>  
 [<span data-ttu-id="641b7-174">Lección 3: Procesamiento de la estructura de minería de datos de Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="641b7-174">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-bike-buyer-mining-structure.md)  
  
  
