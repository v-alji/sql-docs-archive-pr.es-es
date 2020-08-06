---
title: 'Lección 3: procesar la estructura de minería de datos Market Basket | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 095a043f-cf6f-45bb-a021-ae4e1b535c65
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ce2c2e6944d524a38edc331d2cd128ca7cf7d419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743717"
---
# <a name="lesson-3-processing-the-market-basket-mining-structure"></a><span data-ttu-id="d316e-102">Lección 3: Procesar la estructura de minería de datos Market Basket</span><span class="sxs-lookup"><span data-stu-id="d316e-102">Lesson 3: Processing the Market Basket Mining Structure</span></span>
  <span data-ttu-id="d316e-103">En esta lección, usará la instrucción [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) y los VAssocSeqLineItems y vAssocSeqOrders de la base de datos de [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] ejemplo para procesar las estructuras de minería de datos y los modelos de minería de datos creados en la [Lección 1: crear la estructura de minería de datos Market Basket](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) y la [Lección 2: agregar modelos de minería de datos a la estructura de minería de datos Market Basket](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="d316e-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement and the vAssocSeqLineItems and vAssocSeqOrders from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) and [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span>  
  
 <span data-ttu-id="d316e-104">Al procesar una estructura de minería de datos, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] lee los datos de origen y genera las estructuras que admiten los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d316e-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="d316e-105">Al procesar un modelo de minería de datos, los datos definidos por la estructura de minería de datos se pasan por el algoritmo de minería de datos que haya elegido.</span><span class="sxs-lookup"><span data-stu-id="d316e-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you chose.</span></span> <span data-ttu-id="d316e-106">El algoritmo busca tendencias y patrones y, a continuación, almacena esta información en el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d316e-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="d316e-107">Por consiguiente, el modelo de minería de datos no contiene los datos de origen reales, sino la información descubierta por el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="d316e-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="d316e-108">Para obtener más información sobre el procesamiento de modelos de minería de datos, vea [requisitos y consideraciones de procesamiento &#40;minería de datos&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="d316e-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="d316e-109">Solo debe volver a procesar una estructura de minería de datos si cambia una columna de la estructura o los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="d316e-109">You only have to reprocess a mining structure if you change a structure column or change the source data.</span></span> <span data-ttu-id="d316e-110">Si agrega un modelo de minería de datos a una estructura de minería de datos que ya se ha procesado, puede usar la instrucción `INSERT INTO MINING MODEL` para entrenar el nuevo modelo de minería de datos en los datos existentes.</span><span class="sxs-lookup"><span data-stu-id="d316e-110">If you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to train the new mining model on the existing data.</span></span>  
  
 <span data-ttu-id="d316e-111">La estructura de minería de datos Market Basket contiene una tabla anidada, por lo que deberá definir las columnas de minería de datos que deben entrenarse usando la estructura de tablas anidadas y usar el comando `SHAPE` para definir las consultas que extraen los datos de aprendizaje de las tablas de origen.</span><span class="sxs-lookup"><span data-stu-id="d316e-111">Because the Market Basket mining structure contains a nested table, you will have to define the mining columns to be trained using the nested table structure, and use the `SHAPE` command to define the queries that pull the training data from the source tables.</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="d316e-112">Instrucción INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="d316e-112">INSERT INTO Statement</span></span>  
 <span data-ttu-id="d316e-113">Para entrenar la estructura de minería de datos Market Basket y sus modelos de minería de datos asociados, utilice la instrucción [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="d316e-113">In order to train the Market Basket mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="d316e-114">El código de la instrucción se puede dividir en las partes siguientes.</span><span class="sxs-lookup"><span data-stu-id="d316e-114">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="d316e-115">Identificación de la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d316e-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="d316e-116">Visualización en una lista de las columnas de la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="d316e-116">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="d316e-117">Definición de los datos de aprendizaje con `SHAPE`</span><span class="sxs-lookup"><span data-stu-id="d316e-117">Defining the training data using `SHAPE`</span></span>  
  
 <span data-ttu-id="d316e-118">A continuación, se incluye un ejemplo genérico de la instrucción `INSERT INTO`:</span><span class="sxs-lookup"><span data-stu-id="d316e-118">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],'<nested SELECT statement>')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="d316e-119">La primera línea del código identifica la estructura de minería de datos que se entrenará:</span><span class="sxs-lookup"><span data-stu-id="d316e-119">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="d316e-120">Las líneas siguientes del código especifican las columnas definidas por la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d316e-120">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="d316e-121">Debe incluir en la lista cada una de las columnas de la estructura de minería de datos, y cada columna debe estar asignada a una columna incluida en los datos de la consulta de origen:</span><span class="sxs-lookup"><span data-stu-id="d316e-121">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span> <span data-ttu-id="d316e-122">Puede usar `SKIP` para omitir columnas de los datos de origen que no existen en la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d316e-122">You can use `SKIP` to ignore columns that exist in the source data but do not exist in the mining structure.</span></span> <span data-ttu-id="d316e-123">Para obtener más información sobre cómo usar `SKIP` , vea [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx).</span><span class="sxs-lookup"><span data-stu-id="d316e-123">For more information about how to use `SKIP`, see [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx).</span></span>  
  
```  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
```  
  
 <span data-ttu-id="d316e-124">Las últimas líneas del código definen los datos que se utilizarán para entrenar la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d316e-124">The final lines of the code define the data that will be used to train the mining structure.</span></span> <span data-ttu-id="d316e-125">Los datos de origen se incluyen en dos tablas, por lo que usará `SHAPE` para relacionar estas tablas.</span><span class="sxs-lookup"><span data-stu-id="d316e-125">Because the source data is contained within two tables, you will use `SHAPE` to relate the tables.</span></span>  
  
```  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],''<nested SELECT statement>'')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="d316e-126">En esta lección usará `OPENQUERY` para definir los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="d316e-126">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="d316e-127">Para obtener información sobre otros métodos para definir una consulta en los datos de origen, vea [&#60;&#62;de consultas de datos de origen ](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="d316e-127">For information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="d316e-128">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="d316e-128">Lesson Tasks</span></span>  
 <span data-ttu-id="d316e-129">En esta lección realizará la tarea siguiente:</span><span class="sxs-lookup"><span data-stu-id="d316e-129">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="d316e-130">Procesar la estructura de minería de datos Market Basket</span><span class="sxs-lookup"><span data-stu-id="d316e-130">Process the Market Basket mining structure</span></span>  
  
## <a name="processing-the-market-basket-mining-structure"></a><span data-ttu-id="d316e-131">Procesar la estructura de minería de datos Market Basket</span><span class="sxs-lookup"><span data-stu-id="d316e-131">Processing the Market Basket Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="d316e-132">Para procesar la estructura de minería de datos con INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="d316e-132">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="d316e-133">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="d316e-133">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="d316e-134">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="d316e-134">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="d316e-135">Copie el ejemplo genérico de la instrucción INSERT INTO en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="d316e-135">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="d316e-136">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d316e-136">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="d316e-137">por:</span><span class="sxs-lookup"><span data-stu-id="d316e-137">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="d316e-138">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d316e-138">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    [<nested table>]  
    ( SKIP, <skipped column> )  
    ```  
  
     <span data-ttu-id="d316e-139">por:</span><span class="sxs-lookup"><span data-stu-id="d316e-139">with:</span></span>  
  
    ```  
    [OrderNumber],  
    [Products]   
    (SKIP, [Model])  
    ```  
  
     <span data-ttu-id="d316e-140">En la instrucción, `Products` hace referencia a la tabla Products definida por la instrucción SHAPE.</span><span class="sxs-lookup"><span data-stu-id="d316e-140">In the statement, `Products` refers to the Products table defined by the SHAPE statement.</span></span> <span data-ttu-id="d316e-141">`SKIP` se usa para omitir la columna Model, que se encuentra en el origen de datos como clave, pero no la usa la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d316e-141">`SKIP` is used to ignore the Model column, which exists in the source data as a key, but is not used by the mining structure.</span></span>  
  
5.  <span data-ttu-id="d316e-142">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d316e-142">Replace the following:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([<datasource>],'<SELECT statement>') }  
    APPEND  
    (   
      {OPENQUERY([<datasource>],'<nested SELECT statement>')  
    }  
    RELATE [<case key>] TO [<foreign key>]  
    ) AS [<nested table>]  
    ```  
  
     <span data-ttu-id="d316e-143">por:</span><span class="sxs-lookup"><span data-stu-id="d316e-143">with:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
     <span data-ttu-id="d316e-144">La consulta de origen hace referencia al [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] origen de datos definido en el [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] proyecto de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d316e-144">The source query references the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample project.</span></span> <span data-ttu-id="d316e-145">Utiliza este origen de datos para obtener acceso a las vistas vAssocSeqLineItems y vAssocSeqOrders.</span><span class="sxs-lookup"><span data-stu-id="d316e-145">It uses this data source to access the vAssocSeqLineItems and vAssocSeqOrders views.</span></span> <span data-ttu-id="d316e-146">Estas vistas contienen los datos de origen que se utilizarán para entrenar el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d316e-146">These views contain the source data that will be used to train the mining model.</span></span> <span data-ttu-id="d316e-147">Si no ha creado este proyecto o estas vistas, vea el [tutorial básico de minería de datos](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d316e-147">If you have not created this project or these views, see [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="d316e-148">En el comando `SHAPE`, usará `OPENQUERY` para definir dos consultas.</span><span class="sxs-lookup"><span data-stu-id="d316e-148">Within the `SHAPE` command, you will use `OPENQUERY` to define two queries.</span></span> <span data-ttu-id="d316e-149">La primera consulta define la tabla primaria y la segunda, la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="d316e-149">The first query defines the parent table, and the second query defines the nested table.</span></span> <span data-ttu-id="d316e-150">Las dos tablas se relacionan mediante la columna OrderNumber, que existe en ambas tablas.</span><span class="sxs-lookup"><span data-stu-id="d316e-150">The two tables are related using the OrderNumber column, which exists in both tables.</span></span>  
  
     <span data-ttu-id="d316e-151">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d316e-151">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Market Basket]  
    (  
       [OrderNumber],[Products] (SKIP, [Model])  
    )  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
6.  <span data-ttu-id="d316e-152">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="d316e-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="d316e-153">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Process Market Basket.dmx` .</span><span class="sxs-lookup"><span data-stu-id="d316e-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Market Basket.dmx`.</span></span>  
  
8.  <span data-ttu-id="d316e-154">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="d316e-154">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="d316e-155">Después de que la consulta haya terminado de ejecutarse, puede ver los modelos y los conjuntos de elementos encontrados, ver asociaciones o filtrar por conjunto de elementos, probabilidad o importancia.</span><span class="sxs-lookup"><span data-stu-id="d316e-155">After the query has finished running, you can view the patterns and itemsets that were found, view associations, or filter by itemset, probability, or importance.</span></span> <span data-ttu-id="d316e-156">Para ver esta información, en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , haga clic con el botón secundario en el nombre del modelo de datos y, a continuación, haga clic en **examinar**.</span><span class="sxs-lookup"><span data-stu-id="d316e-156">To view this information, in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click the name of the data model, and then click **Browse**.</span></span>  
  
 <span data-ttu-id="d316e-157">En la siguiente lección creará varias predicciones basadas en los modelos de minería de datos que ha agregado a la estructura Market Basket.</span><span class="sxs-lookup"><span data-stu-id="d316e-157">In the next lesson, you will create several predictions based on the mining models that you added to the Market Basket structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="d316e-158">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="d316e-158">Next Lesson</span></span>  
 [<span data-ttu-id="d316e-159">Lección 4: Ejecución de predicciones de cesta de la compra</span><span class="sxs-lookup"><span data-stu-id="d316e-159">Lesson 4: Executing Market Basket Predictions</span></span>](../../2014/tutorials/lesson-4-executing-market-basket-predictions.md)  
  
  
