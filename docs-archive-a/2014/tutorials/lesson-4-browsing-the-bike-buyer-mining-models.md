---
title: 'Lección 4: explorar los modelos de minería de datos Bike Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8de3c500-f881-42da-a096-b6c03300d58d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 709df371d840d4b24e420b4fcd08750fd31e8075
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671874"
---
# <a name="lesson-4-browsing-the-bike-buyer-mining-models"></a><span data-ttu-id="7b3bf-102">Lección 4: Examen de los modelos de minería de datos de Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="7b3bf-102">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>
  <span data-ttu-id="7b3bf-103">En esta lección, usará la instrucción [Select (DMX)](/sql/dmx/select-dmx) para explorar el contenido del árbol de decisión y los modelos de minería de datos de agrupación en clústeres creados en la [Lección 2: agregar modelos de minería de datos a la estructura de minería de datos predictiva](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="7b3bf-103">In this lesson, you will use the [SELECT (DMX)](/sql/dmx/select-dmx) statement to explore the content in the decision tree and clustering mining models that you created in [Lesson 2: Adding Mining Models to the Predictive Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="7b3bf-104">Las columnas incluidas en un modelo de minería de datos no son las columnas definidas por la estructura de minería de datos, sino un conjunto específico de columnas que describen las tendencias y los patrones encontrados por el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-104">The columns contained in a mining model are not the columns defined by the mining structure, but instead are a specific set of columns that describe the trends and patterns that are found by the algorithm.</span></span> <span data-ttu-id="7b3bf-105">Estas columnas del modelo de minería de datos se describen en el conjunto de filas de esquema de [conjunto de filas DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) .</span><span class="sxs-lookup"><span data-stu-id="7b3bf-105">These mining model columns are described in the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset) schema rowset.</span></span> <span data-ttu-id="7b3bf-106">Por ejemplo, la columna MODEL_NAME del conjunto de filas del esquema de contenido incluye el nombre del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-106">For example, the MODEL_NAME column in the content schema rowset contains the name of the mining model.</span></span> <span data-ttu-id="7b3bf-107">Para un modelo de minería de datos de agrupación en clústeres, la columna NODE_CAPTION contiene el nombre de cada clúster y la columna NODE_DESCRIPTION, una descripción de las características de cada clúster.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-107">For a clustering mining model, the NODE_CAPTION column contains the name of each cluster, and the NODE_DESCRIPTION column contains a description of the characteristics of each cluster.</span></span> <span data-ttu-id="7b3bf-108">Puede examinar estas columnas mediante el uso de SELECT FROM \<model> . Instrucción de contenido en DMX.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-108">You can browse these columns by using the SELECT FROM \<model>.CONTENT statement in DMX.</span></span> <span data-ttu-id="7b3bf-109">También puede utilizar esta instrucción para explorar los datos utilizados para crear el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-109">You can also use this statement to explore the data that was used to create the mining model.</span></span> <span data-ttu-id="7b3bf-110">La obtención de detalles debe estar habilitada en la estructura de minería de datos para poder usar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-110">Drillthrough must be enabled on the mining structure in order to use this statement.</span></span> <span data-ttu-id="7b3bf-111">Para obtener más información sobre la instrucción, vea [SELECT FROM &#60;model&#62;. CASOS &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="7b3bf-111">For more information about the statement, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
 <span data-ttu-id="7b3bf-112">También se pueden devolver todos los estados de una columna discreta mediante la instrucción SELECT DISTINCT.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-112">You can also return all the states of a discrete column by using the SELECT DISTINCT statement.</span></span> <span data-ttu-id="7b3bf-113">Por ejemplo, si realiza esta operación en una columna que contiene géneros, la consulta devolverá `male` y `female`.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-113">For example, if you perform this operation on a gender column, the query will return `male` and `female`.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="7b3bf-114">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="7b3bf-114">Lesson Tasks</span></span>  
 <span data-ttu-id="7b3bf-115">En esta lección realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-115">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="7b3bf-116">Explorar el contenido incluido en los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="7b3bf-116">Explore the content contained within the mining models</span></span>  
  
-   <span data-ttu-id="7b3bf-117">Devolver los casos de los datos de origen utilizados para entrenar los modelos de minería de datos</span><span class="sxs-lookup"><span data-stu-id="7b3bf-117">Return the cases from the source data that was used to train the mining models</span></span>  
  
-   <span data-ttu-id="7b3bf-118">Explorar los distintos estados disponibles para una columna discreta específica</span><span class="sxs-lookup"><span data-stu-id="7b3bf-118">Explore the different states available for a specific discrete column</span></span>  
  
## <a name="returning-the-content-of-a-mining-model"></a><span data-ttu-id="7b3bf-119">Devolver el contenido de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="7b3bf-119">Returning the Content of a Mining Model</span></span>  
 <span data-ttu-id="7b3bf-120">En esta lección se utiliza el [modelo SELECT FROM &#60;&#62;. CONTENT &#40;la instrucción DMX&#41;](/sql/dmx/select-from-model-dimension-content-dmx) para devolver el contenido del modelo de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-120">In this lesson, you use the [SELECT FROM &#60;model&#62;.CONTENT &#40;DMX&#41;](/sql/dmx/select-from-model-dimension-content-dmx) statement to return the contents of the clustering model.</span></span>  
  
 <span data-ttu-id="7b3bf-121">A continuación se encuentra un ejemplo genérico de SELECT FROM \<model> . Instrucción de contenido:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-121">The following is a generic example of the SELECT FROM \<model>.CONTENT statement:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CONTENT  
WHERE <where clause>  
```  
  
 <span data-ttu-id="7b3bf-122">En la primera línea del código se definen las columnas que deben devolverse a partir del contenido del modelo de minería de datos y el modelo de minería de datos al que están asociadas:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-122">The first line of the code defines the columns to return from the mining model content, and the mining model they are associated with:</span></span>  
  
```  
SELECT <select list> FROM [<mining model].CONTENT  
```  
  
 <span data-ttu-id="7b3bf-123">La cláusula .CONTENT junto al nombre del modelo de minería de datos especifica que se devuelve el contenido del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-123">The .CONTENT clause next to the name of the mining model specifies that you are returning content from the mining model.</span></span> <span data-ttu-id="7b3bf-124">Para obtener más información acerca de las columnas contenidas en el modelo de minería de datos, vea [DMSCHEMA_MINING_MODEL_CONTENT conjunto de filas](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="7b3bf-124">For more information about the columns contained in the mining model, see [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
 <span data-ttu-id="7b3bf-125">Opcionalmente, puede utilizar la última línea del código para filtrar los resultados devueltos por la instrucción:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-125">You can optionally use the final line of the code to filter the results returned by the statement:</span></span>  
  
```  
WHERE <where clause>  
```  
  
 <span data-ttu-id="7b3bf-126">Por ejemplo, si desea restringir los resultados de la consulta a solo los clústeres que contengan un gran número de casos, puede agregar la siguiente cláusula WHERE a la instrucción SELECT:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-126">For example, if you want to restrict the results of the query to only the clusters that contain a high number of cases, you can add the following WHERE clause to the SELECT statement:</span></span>  
  
```  
WHERE NODE_SUPPORT > 100  
```  
  
 <span data-ttu-id="7b3bf-127">Para obtener más información sobre cómo usar la instrucción WHERE, vea [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="7b3bf-127">For more information about using the WHERE statement, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-content-of-the-clustering-mining-model"></a><span data-ttu-id="7b3bf-128">Para devolver el contenido del modelo de minería de datos de agrupación en clústeres</span><span class="sxs-lookup"><span data-stu-id="7b3bf-128">To return the content of the clustering mining model</span></span>  
  
1.  <span data-ttu-id="7b3bf-129">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="7b3bf-130">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="7b3bf-131">Copie el ejemplo genérico de SELECT FROM \<model> . Instrucción de contenido en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-131">Copy the generic example of the SELECT FROM \<model>.CONTENT statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="7b3bf-132">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-132">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="7b3bf-133">por:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-133">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="7b3bf-134">También puede reemplazar \* por una lista de cualquiera de las columnas incluidas en el [conjunto de filas DMSCHEMA_MINING_MODEL_CONTENT](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span><span class="sxs-lookup"><span data-stu-id="7b3bf-134">You can also replace \* with a list of any of the columns contained within the [DMSCHEMA_MINING_MODEL_CONTENT Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/dmschema-mining-model-content-rowset).</span></span>  
  
4.  <span data-ttu-id="7b3bf-135">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-135">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="7b3bf-136">por:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-136">with:</span></span>  
  
    ```  
    [Clustering]  
    ```  
  
     <span data-ttu-id="7b3bf-137">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-137">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT * FROM [Clustering].CONTENT  
    ```  
  
5.  <span data-ttu-id="7b3bf-138">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-138">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="7b3bf-139">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `SELECT_CONTENT.dmx` .</span><span class="sxs-lookup"><span data-stu-id="7b3bf-139">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_CONTENT.dmx`.</span></span>  
  
7.  <span data-ttu-id="7b3bf-140">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="7b3bf-140">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="7b3bf-141">La consulta devuelve el contenido del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-141">The query returns the content of the mining model.</span></span>  
  
## <a name="use-drillthrough"></a><span data-ttu-id="7b3bf-142">Usar la obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="7b3bf-142">Use Drillthrough</span></span>  
 <span data-ttu-id="7b3bf-143">El paso siguiente es usar la instrucción de obtención de detalles para devolver el muestreo de los casos utilizados para entrenar el modelo de minería de datos del árbol de decisión.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-143">The next step is to use the drillthrough statement to return a sampling of the cases that were used to train the decision tree mining model.</span></span> <span data-ttu-id="7b3bf-144">En esta lección se utiliza el [modelo SELECT FROM &#60;&#62;. Los casos &#40;instrucción DMX&#41;](/sql/dmx/select-from-model-content-dmx) para devolver el contenido del modelo de árbol de decisión.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-144">In this lesson, you use the [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx) statement to return the contents of the decision tree model.</span></span>  
  
 <span data-ttu-id="7b3bf-145">A continuación se encuentra un ejemplo genérico de SELECT FROM \<model> . Instrucción CASEs:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-145">The following is a generic example of the SELECT FROM \<model>.CASES statement:</span></span>  
  
```  
SELECT <select list>   
FROM [<mining model>].CASES  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="7b3bf-146">En la primera línea del código se definen las columnas que deben devolverse a partir de los datos de origen y el modelo de minería de datos en el que se incluyen:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-146">The first line of the code defines the columns to return from the source data, and the mining model they are contained within:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>].CASES  
```  
  
 <span data-ttu-id="7b3bf-147">La cláusula .CASES especifica que se está realizando una consulta de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-147">The .CASES clause specifies that you are performing a drillthrough query.</span></span> <span data-ttu-id="7b3bf-148">Para poder utilizar la obtención de detalles, debe habilitarla al crear el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-148">In order to use drillthrough you must enable drillthrough when you create the mining model.</span></span>  
  
 <span data-ttu-id="7b3bf-149">La última línea del código es opcional y especifica el nodo del modelo de minería de datos del que se solicitan casos:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-149">The final line of the code is optional and specifies the node in the mining model that you are requesting cases from:</span></span>  
  
```  
WHERE IsInNode('<node id>')  
```  
  
 <span data-ttu-id="7b3bf-150">Para obtener más información sobre cómo usar la instrucción WHERE con IsInNode, vea [SELECT FROM &#60;model&#62;. CASOS &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span><span class="sxs-lookup"><span data-stu-id="7b3bf-150">For more information about using the WHERE statement with IsInNode, see [SELECT FROM &#60;model&#62;.CASES &#40;DMX&#41;](/sql/dmx/select-from-model-content-dmx).</span></span>  
  
#### <a name="to-return-the-cases-that-were-used-to-train-the-mining-model"></a><span data-ttu-id="7b3bf-151">Para devolver los casos utilizados para entrenar el modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="7b3bf-151">To return the cases that were used to train the mining model</span></span>  
  
1.  <span data-ttu-id="7b3bf-152">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-152">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="7b3bf-153">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-153">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="7b3bf-154">Copie el ejemplo genérico de SELECT FROM \<model> . CASEs en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-154">Copy the generic example of the SELECT FROM \<model>.CASES statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="7b3bf-155">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-155">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="7b3bf-156">por:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-156">with:</span></span>  
  
    ```  
    *  
    ```  
  
     <span data-ttu-id="7b3bf-157">También puede reemplazar \* por una lista de las columnas incluidas dentro de los datos de origen (como [Bike Buyer]).</span><span class="sxs-lookup"><span data-stu-id="7b3bf-157">You can also replace \* with a list of any of the columns contained within the source data (such as [Bike Buyer]).</span></span>  
  
4.  <span data-ttu-id="7b3bf-158">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-158">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="7b3bf-159">por:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-159">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="7b3bf-160">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-160">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT *   
    FROM [Decision Tree].CASES  
    ```  
  
5.  <span data-ttu-id="7b3bf-161">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-161">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="7b3bf-162">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `SELECT_DRILLTHROUGH.dmx` .</span><span class="sxs-lookup"><span data-stu-id="7b3bf-162">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DRILLTHROUGH.dmx`.</span></span>  
  
7.  <span data-ttu-id="7b3bf-163">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="7b3bf-163">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="7b3bf-164">La consulta devuelve los datos de origen utilizados para entrenar el modelo de minería de datos del árbol de decisión.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-164">The query returns the source data that was used to train the decision tree mining model.</span></span>  
  
## <a name="return-the-states-of-a-discrete-mining-model-column"></a><span data-ttu-id="7b3bf-165">Devolver los estados de una columna discreta del modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="7b3bf-165">Return the States of a Discrete Mining Model Column</span></span>  
 <span data-ttu-id="7b3bf-166">El paso siguiente es utilizar la instrucción SELECT DISTINCT para devolver los distintos estados posibles en la columna del modelo de minería de datos que se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-166">The next step is to use the SELECT DISTINCT statement to return the different possible states in the specified mining model column.</span></span>  
  
 <span data-ttu-id="7b3bf-167">A continuación, se incluye un ejemplo genérico de la instrucción SELECT DISTINCT:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-167">The following is a generic example of the SELECT DISTINCT statement:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
FROM [<mining model>]  
```  
  
 <span data-ttu-id="7b3bf-168">En la primera línea del código se definen las columnas del modelo de minería de datos para las que se devolverán estados:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-168">The first line of the code defines the mining model columns for which the states are returned:</span></span>  
  
```  
SELECT DISTINCT [<column>]   
```  
  
 <span data-ttu-id="7b3bf-169">Debe incluir DISTINCT para devolver todos los estados de la columna.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-169">You must include DISTINCT in order to return all of the states of the column.</span></span> <span data-ttu-id="7b3bf-170">Si no incluye DISTINCT, la instrucción completa se convierte en un acceso directo para una predicción y devuelve el estado más probable de la columna especificada.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-170">If you exclude DISTINCT, then the full statement becomes a shortcut for a prediction and returns the most likely state of the specified column.</span></span> <span data-ttu-id="7b3bf-171">Para más información, vea [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span><span class="sxs-lookup"><span data-stu-id="7b3bf-171">For more information, see [SELECT &#40;DMX&#41;](/sql/dmx/select-dmx).</span></span>  
  
#### <a name="to-return-the-states-of-a-discrete-column"></a><span data-ttu-id="7b3bf-172">Para devolver los estados de una columna discreta</span><span class="sxs-lookup"><span data-stu-id="7b3bf-172">To return the states of a discrete column</span></span>  
  
1.  <span data-ttu-id="7b3bf-173">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-173">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="7b3bf-174">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-174">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="7b3bf-175">Copie el ejemplo genérico de la instrucción SELECT DISTINCT en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-175">Copy the generic example of the SELECT Distinct statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="7b3bf-176">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-176">Replace the following:</span></span>  
  
    ```  
    [<column,name>   
    ```  
  
     <span data-ttu-id="7b3bf-177">por:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-177">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="7b3bf-178">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-178">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="7b3bf-179">por:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-179">with:</span></span>  
  
    ```  
    [Decision Tree]  
    ```  
  
     <span data-ttu-id="7b3bf-180">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="7b3bf-180">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT DISTINCT [Bike Buyer]   
    FROM [Decision Tree]  
    ```  
  
5.  <span data-ttu-id="7b3bf-181">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-181">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="7b3bf-182">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `SELECT_DISCRETE.dmx` .</span><span class="sxs-lookup"><span data-stu-id="7b3bf-182">In the **Save As** dialog box, browse to the appropriate folder, and name the file `SELECT_DISCRETE.dmx`.</span></span>  
  
7.  <span data-ttu-id="7b3bf-183">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="7b3bf-183">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="7b3bf-184">La consulta devuelve los estados posibles de la columna Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-184">The query returns the possible states of the Bike Buyer column.</span></span>  
  
 <span data-ttu-id="7b3bf-185">En la siguiente lección predecirá si los clientes potenciales serán compradores de bicicletas, utilizando el modelo de minería de datos del árbol de decisión.</span><span class="sxs-lookup"><span data-stu-id="7b3bf-185">In the next lesson, you will predict whether potential customers will be bike buyers by using the decision tree mining model.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="7b3bf-186">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="7b3bf-186">Next Lesson</span></span>  
 [<span data-ttu-id="7b3bf-187">Lección 5: Ejecución de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="7b3bf-187">Lesson 5: Executing Prediction Queries</span></span>](../../2014/tutorials/lesson-5-executing-prediction-queries.md)  
  
  
