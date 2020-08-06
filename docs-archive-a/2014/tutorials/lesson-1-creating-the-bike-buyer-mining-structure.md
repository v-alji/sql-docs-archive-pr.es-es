---
title: 'Lección 1: crear la estructura de minería de datos Bike Buyer | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a73ac60b-660f-458a-bd2f-993fbeba7226
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d6384910858d87a80aa3c8f897bc88e45f4504fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747311"
---
# <a name="lesson-1-creating-the-bike-buyer-mining-structure"></a><span data-ttu-id="23469-102">Lección 1: Creación de la estructura de minería de datos de Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="23469-102">Lesson 1: Creating the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="23469-103">En esta lección creará una estructura de minería de datos que permita predecir si un cliente potencial de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] adquirirá una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="23469-103">In this lesson, you will create a mining structure that allows you to predict whether a potential customer of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] will purchase a bicycle.</span></span> <span data-ttu-id="23469-104">Si no está familiarizado con las estructuras de minería de datos y su rol en la minería de datos, vea estructuras de minería de datos [&#40;Analysis Services-data mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="23469-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="23469-105">La estructura de minería de datos Bike Buyer que creará en esta lección permite agregar modelos de minería de datos basados en el algoritmo de [Microsoft clustering](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)Algorithm[Microsoft](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="23469-105">The Bike Buyer mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)[Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="23469-106">En lecciones posteriores, utilizará los modelos de minería de datos de agrupación en clústeres para explorar las distintas formas en las que los clientes pueden agruparse, y utilizará los modelos de minería de datos del árbol de decisión para predecir si un cliente potencial adquirirá una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="23469-106">In later lessons, you will use the clustering mining models to explore the different ways in which customers can be grouped, and will use decision tree mining models to predict whether or not a potential customer will purchase a bicycle.</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="23469-107">Instrucción CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="23469-107">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="23469-108">Para crear una estructura de minería de datos, use la instrucción [Create Mining structure &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="23469-108">To create a mining structure, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="23469-109">El código de la instrucción se puede dividir en las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="23469-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="23469-110">Asignación de un nombre a la estructura.</span><span class="sxs-lookup"><span data-stu-id="23469-110">Naming the structure.</span></span>  
  
-   <span data-ttu-id="23469-111">Definición de la columna de clave.</span><span class="sxs-lookup"><span data-stu-id="23469-111">Defining the key column.</span></span>  
  
-   <span data-ttu-id="23469-112">Definición de las columnas de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="23469-112">Defining the mining columns.</span></span>  
  
-   <span data-ttu-id="23469-113">Definición de un conjunto de datos de pruebas opcional.</span><span class="sxs-lookup"><span data-stu-id="23469-113">Defining an optional testing data set.</span></span>  
  
 <span data-ttu-id="23469-114">A continuación, se incluye un ejemplo genérico de la instrucción CREATE MINING STRUCTURE:</span><span class="sxs-lookup"><span data-stu-id="23469-114">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
(  
    <key column>,  
    <mining structure columns>  
)   
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="23469-115">En la primera línea del código se define el nombre de la estructura:</span><span class="sxs-lookup"><span data-stu-id="23469-115">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="23469-116">Para obtener información acerca de cómo asignar un nombre a un objeto en extensiones de minería de datos (DMX), consulte [identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="23469-116">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="23469-117">En la siguiente línea del código se define la columna de clave para la estructura de minería de datos, que identifica de forma única una entidad de los datos de origen:</span><span class="sxs-lookup"><span data-stu-id="23469-117">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>,  
```  
  
 <span data-ttu-id="23469-118">En la estructura de minería de datos que va a crear, el identificador de cliente, `CustomerKey`, define una entidad en los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="23469-118">In the mining structure you will create, the customer identifier, `CustomerKey`, defines an entity in the source data.</span></span>  
  
 <span data-ttu-id="23469-119">La siguiente línea del código se utiliza para definir las columnas de minería de datos que usarán los modelos de minería de datos asociados a la estructura de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="23469-119">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="23469-120">Puede usar la función de discretización en \<mining structure columns> para discretar columnas continuas con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="23469-120">You can use the DISCRETIZE function within \<mining structure columns> to discretize continuous columns by using the following syntax:</span></span>  
  
 `DISCRETIZE(<method>,<number of buckets>)`  
  
 <span data-ttu-id="23469-121">Para obtener más información sobre la discretización de columnas, vea [métodos de discretización &#40;&#41;de minería de datos ](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="23469-121">For more information about discretizing columns, see [Discretization Methods &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span></span> <span data-ttu-id="23469-122">Para obtener más información acerca de los tipos de columnas de estructura de minería de datos que puede definir, vea [columnas de estructura de minería de datos](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="23469-122">For more information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
 <span data-ttu-id="23469-123">La línea final del código define una partición opcional en la estructura de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="23469-123">The final line of the code defines an optional partition in the mining structure:</span></span>  
  
```  
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="23469-124">Se especifica una parte de los datos que se van a utilizar para probar los modelos de minería relacionados con la estructura y los datos restantes se utilizan para el aprendizaje de los modelos.</span><span class="sxs-lookup"><span data-stu-id="23469-124">You specify some portion of the data to use for testing mining models that are related to the structure, and the remaining data is used for training the models.</span></span> <span data-ttu-id="23469-125">De forma predeterminada, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] crea un conjunto de datos de pruebas que contiene el 30 por ciento de todos los datos del caso.</span><span class="sxs-lookup"><span data-stu-id="23469-125">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates a test data set that contains 30 percent of all case data.</span></span> <span data-ttu-id="23469-126">Debe agregar la especificación donde se indique que el conjunto de datos de pruebas debería contener el 30 por ciento de los casos hasta un máximo de 1000.</span><span class="sxs-lookup"><span data-stu-id="23469-126">You will add the specification that the test data set should contain 30 percent of the cases up to a maximum of 1000 cases.</span></span> <span data-ttu-id="23469-127">Si el 30 por ciento de los casos es menor que 1000, el conjunto de datos de pruebas contendrá la cantidad menor.</span><span class="sxs-lookup"><span data-stu-id="23469-127">If 30 percent of the cases is less than 1000, the test data set will contain the smaller amount.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="23469-128">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="23469-128">Lesson Tasks</span></span>  
 <span data-ttu-id="23469-129">En esta lección realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="23469-129">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="23469-130">Crear una consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="23469-130">Create a new blank query.</span></span>  
  
-   <span data-ttu-id="23469-131">Modificar la consulta para crear la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="23469-131">Alter the query to create the mining structure.</span></span>  
  
-   <span data-ttu-id="23469-132">Ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="23469-132">Execute the query.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="23469-133">Crear la consulta</span><span class="sxs-lookup"><span data-stu-id="23469-133">Creating the Query</span></span>  
 <span data-ttu-id="23469-134">El primer paso es conectarse a una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y crear una consulta DMX en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23469-134">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="23469-135">Para crear una consulta DMX mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="23469-135">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="23469-136">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23469-136">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="23469-137">En el cuadro de diálogo **conectar con el servidor** , en **tipo de servidor**, seleccione **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="23469-137">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="23469-138">En **nombre del servidor**, escriba `LocalHost` o escriba el nombre de la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a la que desea conectarse para esta lección.</span><span class="sxs-lookup"><span data-stu-id="23469-138">In **Server name**, type `LocalHost`, or type the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="23469-139">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="23469-139">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="23469-140">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX** para abrir el **Editor de consultas** y una nueva consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="23469-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the **Query Editor** and a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="23469-141">Modificar la consulta</span><span class="sxs-lookup"><span data-stu-id="23469-141">Altering the Query</span></span>  
 <span data-ttu-id="23469-142">El paso siguiente es modificar la instrucción CREATE MINING STRUCTURE descrita anteriormente para crear la estructura de minería de datos de Bike Buyer.</span><span class="sxs-lookup"><span data-stu-id="23469-142">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Bike Buyer mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="23469-143">Para personalizar la instrucción CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="23469-143">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="23469-144">En el Editor de consultas, copie el ejemplo genérico de la instrucción CREATE MINING STRUCTURE en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="23469-144">In the Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="23469-145">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23469-145">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]   
    ```  
  
     <span data-ttu-id="23469-146">por:</span><span class="sxs-lookup"><span data-stu-id="23469-146">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
3.  <span data-ttu-id="23469-147">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23469-147">Replace the following:</span></span>  
  
    ```  
    <key column>   
    ```  
  
     <span data-ttu-id="23469-148">por:</span><span class="sxs-lookup"><span data-stu-id="23469-148">with:</span></span>  
  
    ```  
    CustomerKey LONG KEY  
    ```  
  
4.  <span data-ttu-id="23469-149">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23469-149">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>   
    ```  
  
     <span data-ttu-id="23469-150">por:</span><span class="sxs-lookup"><span data-stu-id="23469-150">with:</span></span>  
  
    ```  
    [Age] LONG DISCRETIZED(Automatic,10),  
    [Bike Buyer] LONG DISCRETE,  
    [Commute Distance] TEXT DISCRETE,  
    [Education] TEXT DISCRETE,  
    [Gender] TEXT DISCRETE,  
    [House Owner Flag] TEXT DISCRETE,  
    [Marital Status] TEXT DISCRETE,  
    [Number Cars Owned] LONG DISCRETE,  
    [Number Children At Home] LONG DISCRETE,  
    [Occupation] TEXT DISCRETE,  
    [Region] TEXT DISCRETE,  
    [Total Children]LONG DISCRETE,  
    [Yearly Income] DOUBLE CONTINUOUS  
    ```  
  
5.  <span data-ttu-id="23469-151">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23469-151">Replace the following:</span></span>  
  
    ```  
    WITH HOLDOUT (holdout specifier>)  
    ```  
  
     <span data-ttu-id="23469-152">por:</span><span class="sxs-lookup"><span data-stu-id="23469-152">with:</span></span>  
  
    ```  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
    ```  
  
     <span data-ttu-id="23469-153">Ahora, la instrucción completa de la estructura de minería de datos debería ser como sigue:</span><span class="sxs-lookup"><span data-stu-id="23469-153">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key] LONG KEY,  
       [Age]LONG DISCRETIZED(Automatic,10),  
       [Bike Buyer] LONG DISCRETE,  
       [Commute Distance] TEXT DISCRETE,  
       [Education] TEXT DISCRETE,  
       [Gender] TEXT DISCRETE,  
       [House Owner Flag] TEXT DISCRETE,  
       [Marital Status] TEXT DISCRETE,  
       [Number Cars Owned]LONG DISCRETE,  
       [Number Children At Home]LONG DISCRETE,  
       [Occupation] TEXT DISCRETE,  
       [Region] TEXT DISCRETE,  
       [Total Children]LONG DISCRETE,  
       [Yearly Income] DOUBLE CONTINUOUS  
    )  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
  
    ```  
  
6.  <span data-ttu-id="23469-154">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="23469-154">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="23469-155">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="23469-155">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Bike Buyer Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="23469-156">Ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="23469-156">Executing the Query</span></span>  
 <span data-ttu-id="23469-157">El último paso es ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="23469-157">The final step is to execute the query.</span></span> <span data-ttu-id="23469-158">Una vez creada y guardada una consulta, tiene que ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="23469-158">After a query is created and saved, it needs to be executed.</span></span> <span data-ttu-id="23469-159">Es decir, la instrucción tiene que ejecutarse para crear la estructura de minería de datos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="23469-159">That is, the statement needs to be run in order to create the mining structure on the server.</span></span> <span data-ttu-id="23469-160">Para obtener más información acerca de la ejecución de consultas en el editor de consultas, vea [motor de base de datos editor de consultas &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="23469-160">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="23469-161">Para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="23469-161">To execute the query</span></span>  
  
1.  <span data-ttu-id="23469-162">En el editor de consultas, en la barra de herramientas, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="23469-162">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="23469-163">El estado de la consulta se muestra en la pestaña **mensajes** , en la parte inferior del editor de consultas, una vez finalizada la ejecución de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="23469-163">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="23469-164">En Mensajes, debe aparecer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="23469-164">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="23469-165">Ya existe una nueva estructura denominada **Bike Buyer** en el servidor.</span><span class="sxs-lookup"><span data-stu-id="23469-165">A new structure named **Bike Buyer** now exists on the server.</span></span>  
  
 <span data-ttu-id="23469-166">En la siguiente lección agregará modelos de minería de datos a la estructura que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="23469-166">In the next lesson, you will add mining models to the structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="23469-167">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="23469-167">Next Lesson</span></span>  
 [<span data-ttu-id="23469-168">Lección 2: Adición de modelos de minería de datos a la estructura de minería de datos de Bike Buyer</span><span class="sxs-lookup"><span data-stu-id="23469-168">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md)  
  
  
