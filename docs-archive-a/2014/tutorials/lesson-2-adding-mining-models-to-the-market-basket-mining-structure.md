---
title: 'Lección 2: agregar modelos de minería de datos a la estructura de minería de datos Market Basket | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d96a7a7d-35d7-4b34-abb5-f0822c256253
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b9573d9359983e33cf23533787c26039572710ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746645"
---
# <a name="lesson-2-adding-mining-models-to-the-market-basket-mining-structure"></a><span data-ttu-id="55966-102">Lección 2: Adición de modelos de minería a la estructura de minería cesta de la compra</span><span class="sxs-lookup"><span data-stu-id="55966-102">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>
  <span data-ttu-id="55966-103">En esta lección, agregará dos modelos de minería de datos a la estructura de minería de datos Market Basket que creó en la [Lección 1: creación de la estructura de minería de datos Market Basket](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="55966-103">In this lesson, you will add two mining models to the Market Basket mining structure that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="55966-104">Estos modelos de minería de datos le permitirán crear predicciones.</span><span class="sxs-lookup"><span data-stu-id="55966-104">These mining models will allow you to create predictions.</span></span>  
  
 <span data-ttu-id="55966-105">Para predecir los tipos de productos que los clientes tienden a comprar al mismo tiempo, creará dos modelos de minería de datos con el [algoritmo de Asociación de Microsoft](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) y dos valores distintos para el parámetro *MINIMUM_PROBABILTY* .</span><span class="sxs-lookup"><span data-stu-id="55966-105">To predict the types of products that customers tend to purchase at the same time, you will create two mining models using the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) and two different values for the *MINIMUM_PROBABILTY* parameter.</span></span>  
  
 <span data-ttu-id="55966-106">*MINIMUM_PROBABILTY* es un [!INCLUDE[msCoName](../includes/msconame-md.md)] parámetro de algoritmo de asociación que ayuda a determinar el número de reglas que contendrá un modelo de minería de datos especificando la probabilidad mínima que debe tener una regla.</span><span class="sxs-lookup"><span data-stu-id="55966-106">*MINIMUM_PROBABILTY* is a [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm parameter that helps to determine the number of rules that a mining model will contain by specifying the minimum probability that a rule must have.</span></span> <span data-ttu-id="55966-107">Por ejemplo, al establecer este valor en 0,4 se especifica que se puede generar una regla solo si la combinación de productos que la regla describe tiene al menos una probabilidad del 40 por ciento de que esto ocurra.</span><span class="sxs-lookup"><span data-stu-id="55966-107">For example, setting this value to 0.4 specifies that a rule can be generated only if the combination of products that the rule describes has at least a forty percent probability of occurring.</span></span>  
  
 <span data-ttu-id="55966-108">Verá el efecto de cambiar el parámetro *MINIMUM_PROBABILTY* en una lección posterior.</span><span class="sxs-lookup"><span data-stu-id="55966-108">You will view the effect of changing the *MINIMUM_PROBABILTY* parameter in a later lesson.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="55966-109">Instrucción ALTER MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="55966-109">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="55966-110">Para agregar un modelo de minería de datos que contenga una tabla anidada a una estructura de minería de datos, use la instrucción [ALTER Mining structure &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="55966-110">To add a mining model that contains a nested table to a mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="55966-111">El código de la instrucción se puede dividir en las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="55966-111">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="55966-112">Identificación de la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="55966-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="55966-113">Asignación de un nombre al modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="55966-113">Naming the mining model</span></span>  
  
-   <span data-ttu-id="55966-114">Definición de la columna de clave</span><span class="sxs-lookup"><span data-stu-id="55966-114">Defining the key column</span></span>  
  
-   <span data-ttu-id="55966-115">Definición de las columnas de entrada y de predicción</span><span class="sxs-lookup"><span data-stu-id="55966-115">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="55966-116">Definición de las columnas de la tabla anidada</span><span class="sxs-lookup"><span data-stu-id="55966-116">Defining the nested table columns</span></span>  
  
-   <span data-ttu-id="55966-117">Identificación de los cambios de parámetros y el algoritmo</span><span class="sxs-lookup"><span data-stu-id="55966-117">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="55966-118">El siguiente es un ejemplo genérico de la instrucción `ALTER MINING STRUCTURE` que agrega un modelo de minería de datos a una estructura que incluye columnas de tabla anidada:</span><span class="sxs-lookup"><span data-stu-id="55966-118">The following is a generic example of the `ALTER MINING STRUCTURE` statement that adds a mining model to a structure that includes nested table columns:</span></span>  
  
```  
ALTER MINING STRUCTURE [<Mining Structure Name>]  
ADD MINING MODEL [<Mining Model Name>]  
(  
    [<key column>],  
    <mining model column> <usage>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
) USING <algorithm>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="55966-119">La primera línea del código identifica la estructura de minería de datos existente a la que se agregará el modelo de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="55966-119">The first line of the code identifies the existing mining structure to which the mining model will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="55966-120">La siguiente línea de código asigna un nombre al modelo de minería de datos que se agregará a la estructura de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="55966-120">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="55966-121">Para obtener información acerca de cómo asignar un nombre a un objeto en extensiones de minería de datos (DMX), consulte [identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="55966-121">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="55966-122">Las líneas siguientes del código definen las columnas de la estructura de minería de datos que usará el modelo de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="55966-122">The next lines of the code define the columns in the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns> <usage>,  
```  
  
 <span data-ttu-id="55966-123">Solo puede usar columnas que ya existen en la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="55966-123">You can only use columns that already exist in the mining structure.</span></span>  
  
 <span data-ttu-id="55966-124">La primera columna de la lista de columnas del modelo de minería de datos debe ser la columna de clave en la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="55966-124">The first column in the list of mining model columns must be the key column in the mining structure.</span></span> <span data-ttu-id="55966-125">Sin embargo, no es necesario escribir `KEY` después de la columna de clave para especificar el uso.</span><span class="sxs-lookup"><span data-stu-id="55966-125">However, you do not have to type `KEY` after the key column to specify usage.</span></span> <span data-ttu-id="55966-126">Eso se debe a que ya ha definido la columna como una clave cuando creó la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="55966-126">That is because you have already defined the column as a key when you created the mining structure.</span></span>  
  
 <span data-ttu-id="55966-127">Las líneas restantes especifican el uso de las columnas en el nuevo modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="55966-127">The remaining lines specify the usage of the columns in the new mining model.</span></span> <span data-ttu-id="55966-128">Puede especificar que una columna del modelo de minería de datos se utilizará para la predicción mediante la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="55966-128">You can specify that a column in the mining model will be used for prediction by using the following syntax:</span></span>  
  
```  
<column name> PREDICT,  
```  
  
 <span data-ttu-id="55966-129">Si no especifica el uso, no tiene que incluir una columna de la estructura de minería de datos en la lista.</span><span class="sxs-lookup"><span data-stu-id="55966-129">If you do not specify usage, you do not have to include a data mining structure column in the list.</span></span> <span data-ttu-id="55966-130">Todas las columnas que se usan por la estructura de minería de datos a la que se hace referencia están disponibles automáticamente para su uso por parte de los modelos de minería de datos que se basan en dicha estructura.</span><span class="sxs-lookup"><span data-stu-id="55966-130">All columns that are used by the referenced data mining structure are automatically available for use by the mining models that are based on that structure.</span></span> <span data-ttu-id="55966-131">Sin embargo, el modelo no usará las columnas para entrenamiento a menos que especifique el uso.</span><span class="sxs-lookup"><span data-stu-id="55966-131">However, the model will not use the columns for training unless you specify the usage.</span></span>  
  
 <span data-ttu-id="55966-132">En la última línea del código se define el algoritmo y los parámetros del algoritmo que se utilizarán para generar el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="55966-132">The last line in the code defines the algorithm and algorithm parameters that will be used to generate the mining model.</span></span>  
  
```  
) USING <algorithm>( <algorithm parameters> )  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="55966-133">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="55966-133">Lesson Tasks</span></span>  
 <span data-ttu-id="55966-134">En esta lección realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="55966-134">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="55966-135">Agregar un modelo de minería de datos de asociación a la estructura con la probabilidad predeterminada</span><span class="sxs-lookup"><span data-stu-id="55966-135">Add an association mining model to the structure using the default probability</span></span>  
  
-   <span data-ttu-id="55966-136">Agregar un modelo de minería de datos de asociación a la estructura con una probabilidad modificada</span><span class="sxs-lookup"><span data-stu-id="55966-136">Add an association mining model to the structure using a modified probability</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-using-the-default-minimum_probability"></a><span data-ttu-id="55966-137">Agregar un modelo de minería de datos de asociación a la estructura con el valor predeterminado de MINIMUM_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="55966-137">Adding an Association Mining Model to the Structure Using the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="55966-138">La primera tarea consiste en agregar un nuevo modelo de minería de datos a la estructura de minería de datos Market Basket en función del [!INCLUDE[msCoName](../includes/msconame-md.md)] algoritmo de asociación que utiliza el valor predeterminado para *MINIMUM_PROBABILITY*.</span><span class="sxs-lookup"><span data-stu-id="55966-138">The first task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm using the default value for *MINIMUM_PROBABILITY*.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="55966-139">Agregar un modelo de minería de datos de asociación</span><span class="sxs-lookup"><span data-stu-id="55966-139">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="55966-140">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="55966-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="55966-141">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="55966-141">Query Editor opens and contains a new, blank query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="55966-142">Para crear una consulta de DMX frente a una base de datos de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] concreta, haga clic con el botón secundario en la base de datos en lugar de la instancia.</span><span class="sxs-lookup"><span data-stu-id="55966-142">To create a DMX query against a specific [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, right-click the database instead of the instance.</span></span>  
  
2.  <span data-ttu-id="55966-143">Copie el ejemplo genérico de la instrucción `ALTER MINING STRUCTURE` en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="55966-143">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="55966-144">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55966-144">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="55966-145">por:</span><span class="sxs-lookup"><span data-stu-id="55966-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
4.  <span data-ttu-id="55966-146">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55966-146">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="55966-147">por:</span><span class="sxs-lookup"><span data-stu-id="55966-147">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="55966-148">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55966-148">Replace the following:</span></span>  
  
    ```  
    [<key column>],  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="55966-149">por:</span><span class="sxs-lookup"><span data-stu-id="55966-149">with:</span></span>  
  
    ```  
    OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="55966-150">En este caso, la tabla `[Products]` se ha designado como la columna de predicción`.` Además, la columna `[Model]` está incluida en la lista de columnas de tabla anidada porque es la columna de clave de la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="55966-150">In this case, the `[Products]` table has been designated as the predictable column`.` Also, the `[Model]` column is included in the list of nested table columns because it is the key column of the nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="55966-151">Recuerde que una clave anidada es diferente de una clave de caso.</span><span class="sxs-lookup"><span data-stu-id="55966-151">Remember that a nested key is different from a case key.</span></span> <span data-ttu-id="55966-152">Una clave de caso es un identificador único del caso, mientras que la clave anidada es un atributo que desea usar como modelo.</span><span class="sxs-lookup"><span data-stu-id="55966-152">A case key is a unique identifier of the case, whereas the nested key is an attribute that you want to model.</span></span>  
  
6.  <span data-ttu-id="55966-153">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55966-153">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="55966-154">por:</span><span class="sxs-lookup"><span data-stu-id="55966-154">with:</span></span>  
  
    ```  
    Using Microsoft_Association_Rules  
    ```  
  
     <span data-ttu-id="55966-155">Ahora, la instrucción resultante debería ser como sigue:</span><span class="sxs-lookup"><span data-stu-id="55966-155">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Default Association]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    Using Microsoft_Association_Rules  
    ```  
  
7.  <span data-ttu-id="55966-156">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="55966-156">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="55966-157">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Default_Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="55966-157">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Default_Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="55966-158">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="55966-158">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-changing-the-default-minimum_probability"></a><span data-ttu-id="55966-159">Agregar un modelo de minería de datos de asociación a la estructura cambiando el valor predeterminado de MINIMUM_PROBABILITY</span><span class="sxs-lookup"><span data-stu-id="55966-159">Adding an Association Mining Model to the Structure Changing the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="55966-160">La siguiente tarea es agregar un nuevo modelo de minería de datos a la estructura de minería de datos Market Basket basado en el algoritmo de asociación de [!INCLUDE[msCoName](../includes/msconame-md.md)] y, después, cambiar el valor predeterminado de MINIMUM_PROBABILITY a 0,01.</span><span class="sxs-lookup"><span data-stu-id="55966-160">The next task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm, and change the default value for MINIMUM_PROBABILITY to 0.01.</span></span> <span data-ttu-id="55966-161">Al cambiar el parámetro, el algoritmo de asociación de [!INCLUDE[msCoName](../includes/msconame-md.md)] creará más reglas.</span><span class="sxs-lookup"><span data-stu-id="55966-161">Changing the parameter will cause the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm to create more rules.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="55966-162">Agregar un modelo de minería de datos de asociación</span><span class="sxs-lookup"><span data-stu-id="55966-162">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="55966-163">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="55966-163">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="55966-164">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="55966-164">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="55966-165">Copie el ejemplo genérico de la instrucción `ALTER MINING STRUCTURE` en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="55966-165">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="55966-166">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55966-166">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="55966-167">por:</span><span class="sxs-lookup"><span data-stu-id="55966-167">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="55966-168">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55966-168">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="55966-169">por:</span><span class="sxs-lookup"><span data-stu-id="55966-169">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="55966-170">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55966-170">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="55966-171">por:</span><span class="sxs-lookup"><span data-stu-id="55966-171">with:</span></span>  
  
    ```  
    OrderNumber,  
    [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="55966-172">En este caso, la tabla `[Products]` se ha designado como la columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="55966-172">In this case, the `[Products]` table has been designated as the predictable column.</span></span> <span data-ttu-id="55966-173">Además, la columna `[MODEL]` está incluida en la lista porque es la columna de clave de la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="55966-173">Also, the `[MODEL]` column is included in the list because it is the key column in the nested table.</span></span>  
  
6.  <span data-ttu-id="55966-174">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="55966-174">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="55966-175">por:</span><span class="sxs-lookup"><span data-stu-id="55966-175">with:</span></span>  
  
    ```  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
     <span data-ttu-id="55966-176">Ahora, la instrucción resultante debería ser como sigue:</span><span class="sxs-lookup"><span data-stu-id="55966-176">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Modified Assocation]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
7.  <span data-ttu-id="55966-177">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="55966-177">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="55966-178">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Modified Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="55966-178">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="55966-179">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="55966-179">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="55966-180">En esta siguiente lección procesará la estructura de minería de datos Market Basket junto con sus modelos de minería de datos asociados.</span><span class="sxs-lookup"><span data-stu-id="55966-180">In this next lesson you will process the Market Basket mining structure together with its associated mining models.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="55966-181">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="55966-181">Next Lesson</span></span>  
 [<span data-ttu-id="55966-182">Lección 3: Procesar la estructura de minería de datos Market Basket</span><span class="sxs-lookup"><span data-stu-id="55966-182">Lesson 3: Processing the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-market-basket-mining-structure.md)  
  
  
