---
title: 'Lección 3: procesar la estructura de minería de datos Bike Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e748c2cd-339d-4e82-82f1-be2d0fc41b61
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2e3f85016b32884b9a6b809e28d20d9985f97cd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747305"
---
# <a name="lesson-3-processing-the-bike-buyer-mining-structure"></a><span data-ttu-id="f6a5e-102">Lección 3: Procesamiento de la estructura de minería de datos de Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="f6a5e-102">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="f6a5e-103">En esta lección, usará la instrucción INSERT INTO y la vista vTargetMail de la base de datos de [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] ejemplo para procesar las estructuras de minería de datos y los modelos de minería de datos creados en la [Lección 1: crear la estructura de minería de datos Bike Buyer](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) y [Lección 2: agregar modelos de minería de datos a la estructura de minería de datos Bike Buyer](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span><span class="sxs-lookup"><span data-stu-id="f6a5e-103">In this lesson, you will use the INSERT INTO statement and the vTargetMail view from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) and [Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="f6a5e-104">Al procesar una estructura de minería de datos, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] lee los datos de origen y genera las estructuras que admiten los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="f6a5e-105">Al procesar un modelo de minería de datos, los datos definidos por la estructura de minería de datos se pasan por el algoritmo de minería de datos que elija.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you choose.</span></span> <span data-ttu-id="f6a5e-106">El algoritmo busca tendencias y patrones y, a continuación, almacena esta información en el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="f6a5e-107">Por consiguiente, el modelo de minería de datos no contiene los datos de origen reales, sino la información descubierta por el algoritmo.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="f6a5e-108">Para obtener más información sobre el procesamiento de modelos de minería de datos, vea [requisitos y consideraciones de procesamiento &#40;minería de datos&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="f6a5e-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="f6a5e-109">Solamente necesita volver a procesar una estructura de minería de datos si cambia una columna de la estructura o los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-109">You need to reprocess a mining structure only if you change a structure column or change the source data.</span></span> <span data-ttu-id="f6a5e-110">Si agrega un modelo de minería de datos a una estructura de minería de datos que ya se ha procesado, puede usar la instrucción INSERT INTO MINING MODEL para entrenar el nuevo modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-110">If you add a mining model to a mining structure that has already been processed, you can use the INSERT INTO MINING MODEL statement to train the new mining model.</span></span>  
  
## <a name="train-structure-template"></a><span data-ttu-id="f6a5e-111">Entrenar la plantilla de la estructura</span><span class="sxs-lookup"><span data-stu-id="f6a5e-111">Train Structure Template</span></span>  
 <span data-ttu-id="f6a5e-112">Para entrenar la estructura de minería de datos y sus modelos de minería de datos asociados, utilice la instrucción [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="f6a5e-112">In order to train the mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="f6a5e-113">El código de la instrucción se puede dividir en las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="f6a5e-114">Identificación de la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f6a5e-114">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="f6a5e-115">Visualización en una lista de las columnas de la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="f6a5e-115">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="f6a5e-116">Definición de los datos de entrenamiento</span><span class="sxs-lookup"><span data-stu-id="f6a5e-116">Defining the training data</span></span>  
  
 <span data-ttu-id="f6a5e-117">A continuación, se incluye un ejemplo genérico de la instrucción INSERT INTO:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-117">The following is a generic example of the INSERT INTO statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="f6a5e-118">La primera línea del código identifica la estructura de minería de datos que se entrenará:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-118">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="f6a5e-119">La línea siguiente del código especifica las columnas definidas por la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-119">The next line of the code specifies the columns that are defined by the mining structure.</span></span> <span data-ttu-id="f6a5e-120">Debe incluir en la lista cada una de las columnas de la estructura de minería de datos, y cada columna debe estar asignada a una columna incluida en los datos de la consulta de origen:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-120">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="f6a5e-121">La última línea del código define los datos que se usarán para entrenar la estructura de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-121">The final line of the code defines the data that will be used to train the mining structure:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="f6a5e-122">En esta lección usará `OPENQUERY` para definir los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-122">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="f6a5e-123">Para obtener información sobre otros métodos para definir la consulta de origen, vea [&#60;consulta de datos de origen&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="f6a5e-123">For information about other methods of defining the source query, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="f6a5e-124">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="f6a5e-124">Lesson Tasks</span></span>  
 <span data-ttu-id="f6a5e-125">En esta lección realizará la tarea siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-125">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="f6a5e-126">Procesar la estructura de minería de datos de Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="f6a5e-126">Process the Bike Buyer mining structure</span></span>  
  
## <a name="processing-the-predictive-mining-structure"></a><span data-ttu-id="f6a5e-127">Procesar la estructura de minería de datos de predicción</span><span class="sxs-lookup"><span data-stu-id="f6a5e-127">Processing the Predictive Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="f6a5e-128">Para procesar la estructura de minería de datos con INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="f6a5e-128">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="f6a5e-129">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="f6a5e-130">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="f6a5e-131">Copie el ejemplo genérico de la instrucción INSERT INTO en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-131">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="f6a5e-132">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-132">Replace the following:</span></span>  
  
    ```  
    [<mining structure name>]   
    ```  
  
     <span data-ttu-id="f6a5e-133">por:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-133">with:</span></span>  
  
    ```  
    Bike Buyer  
    ```  
  
4.  <span data-ttu-id="f6a5e-134">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-134">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="f6a5e-135">por:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-135">with:</span></span>  
  
    ```  
    [Customer Key],  
    [Age],  
    [Bike Buyer],  
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
  
5.  <span data-ttu-id="f6a5e-136">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-136">Replace the following:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="f6a5e-137">por:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-137">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
     <span data-ttu-id="f6a5e-138">La instrucción OPENQUERY hace referencia al origen de datos de [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] para obtener acceso a la vista vTargetMail.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-138">The OPENQUERY statement references the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source to access the view vTargetMail.</span></span> <span data-ttu-id="f6a5e-139">La vista contiene los datos de origen que se usarán para entrenar los modelos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-139">The view contains the source data that will be used to train the mining models.</span></span>  
  
     <span data-ttu-id="f6a5e-140">Ahora la apariencia de la instrucción completa debe ser como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6a5e-140">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key],  
       [Age],  
       [Bike Buyer],  
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
    )  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
6.  <span data-ttu-id="f6a5e-141">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-141">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="f6a5e-142">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Process Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="f6a5e-142">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Bike Buyer Structure.dmx`.</span></span>  
  
8.  <span data-ttu-id="f6a5e-143">En la barra de herramientas, haga clic en el botón **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="f6a5e-143">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="f6a5e-144">En la siguiente lección explorará el contenido de los modelos de minería de datos que ha agregado a la estructura de minería de datos en esta lección.</span><span class="sxs-lookup"><span data-stu-id="f6a5e-144">In the next lesson, you will explore content in the mining models you added to the mining structure in this lesson.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="f6a5e-145">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="f6a5e-145">Next Lesson</span></span>  
 [<span data-ttu-id="f6a5e-146">Lección 4: Examen de los modelos de minería de datos de Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="f6a5e-146">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>](../../2014/tutorials/lesson-4-browsing-the-bike-buyer-mining-models.md)  
  
  
