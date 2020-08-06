---
title: 'Lección 1: crear la estructura de minería de datos Market Basket | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a817c8d1-aff4-42b4-b194-ad9cc1c60f35
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a6a6e123e525512a72d70bcc8ca2eba549d1347e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747312"
---
# <a name="lesson-1-creating-the-market-basket-mining-structure"></a><span data-ttu-id="c1df1-102">Lección 1: Creación de la estructura de minería de la cesta de la compra</span><span class="sxs-lookup"><span data-stu-id="c1df1-102">Lesson 1: Creating the Market Basket Mining Structure</span></span>
  <span data-ttu-id="c1df1-103">En esta lección creará una estructura de minería de datos que permita predecir qué productos de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] tiende a adquirir un cliente simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="c1df1-103">In this lesson, you will create a mining structure that allows you to predict what [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] products a customer tends to purchase at the same time.</span></span> <span data-ttu-id="c1df1-104">Si no está familiarizado con las estructuras de minería de datos y su rol en la minería de datos, vea estructuras de minería de datos [&#40;Analysis Services-data mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="c1df1-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="c1df1-105">La estructura de minería de datos de asociación que creará en esta lección permite agregar modelos de minería de datos basados en el [algoritmo de Asociación de Microsoft](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="c1df1-105">The association mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md).</span></span> <span data-ttu-id="c1df1-106">En lecciones posteriores utilizará los modelos de minería de datos para predecir el tipo de productos que un cliente tiende a adquirir simultáneamente, lo que se denomina análisis de cesta de mercado (Market Basket).</span><span class="sxs-lookup"><span data-stu-id="c1df1-106">In later lessons, you will use the mining models to predict the type of products a customer tends to purchase at the same time, which is called a market basket analysis.</span></span> <span data-ttu-id="c1df1-107">Por ejemplo, es posible que averigüe que los clientes tienden a comprar bicicletas de montaña, ruedas y cascos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="c1df1-107">For example, you may find that customers tend to buy mountain bikes, bike tires, and helmets at the same time.</span></span>  
  
 <span data-ttu-id="c1df1-108">En esta lección se define la estructura de minería de datos utilizando tablas anidadas.</span><span class="sxs-lookup"><span data-stu-id="c1df1-108">In this lesson, the mining structure is defined by using nested tables.</span></span> <span data-ttu-id="c1df1-109">Se utilizan tablas anidadas porque el dominio de datos que definirá la estructura se incluye en dos tablas de origen distintas.</span><span class="sxs-lookup"><span data-stu-id="c1df1-109">Nested tables are used because the data domain that will be defined by the structure is contained within two different source tables.</span></span> <span data-ttu-id="c1df1-110">Para obtener más información sobre las tablas anidadas, vea [tablas anidadas &#40;Analysis Services-&#41;de minería de datos ](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="c1df1-110">For more information on nested tables, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="c1df1-111">Instrucción CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="c1df1-111">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="c1df1-112">Para crear una estructura de minería de datos que contenga una tabla anidada, use la instrucción [Create Mining structure &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="c1df1-112">In order to create a mining structure containing a nested table, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="c1df1-113">El código de la instrucción se puede dividir en las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="c1df1-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="c1df1-114">Asignación de un nombre a la estructura</span><span class="sxs-lookup"><span data-stu-id="c1df1-114">Naming the structure</span></span>  
  
-   <span data-ttu-id="c1df1-115">Definición de la columna de clave</span><span class="sxs-lookup"><span data-stu-id="c1df1-115">Defining the key column</span></span>  
  
-   <span data-ttu-id="c1df1-116">Definición de las columnas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c1df1-116">Defining the mining columns</span></span>  
  
-   <span data-ttu-id="c1df1-117">Definición de las columnas de la tabla anidada</span><span class="sxs-lookup"><span data-stu-id="c1df1-117">Defining the nested table columns</span></span>  
  
 <span data-ttu-id="c1df1-118">A continuación, se incluye un ejemplo genérico de la instrucción CREATE MINING STRUCTURE:</span><span class="sxs-lookup"><span data-stu-id="c1df1-118">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<Mining Structure Name>]  
(  
   <key column>,  
   <mining structure columns>,  
   <table columns>  
   (  <nested key column>,  
      <nested mining structure columns> )  
)  
  
```  
  
 <span data-ttu-id="c1df1-119">En la primera línea del código se define el nombre de la estructura:</span><span class="sxs-lookup"><span data-stu-id="c1df1-119">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [Mining Structure Name]  
```  
  
 <span data-ttu-id="c1df1-120">Para obtener información sobre cómo asignar un nombre a un objeto en DMX, consulte [identifiers &#40;dmx&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="c1df1-120">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="c1df1-121">En la siguiente línea del código se define la columna de clave para la estructura de minería de datos, que identifica de forma única una entidad de los datos de origen:</span><span class="sxs-lookup"><span data-stu-id="c1df1-121">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>  
```  
  
 <span data-ttu-id="c1df1-122">La siguiente línea del código se utiliza para definir las columnas de minería de datos que usarán los modelos de minería de datos asociados a la estructura de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="c1df1-122">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="c1df1-123">En las siguientes líneas de código se definen las columnas de la tabla anidada:</span><span class="sxs-lookup"><span data-stu-id="c1df1-123">The next lines of the code define the nested table columns:</span></span>  
  
```  
<table columns>  
(  <nested key column>,  
   <nested mining structure columns> )  
```  
  
 <span data-ttu-id="c1df1-124">Para obtener información acerca de los tipos de columnas de estructura de minería de datos que puede definir, vea [columnas de estructura de minería de datos](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="c1df1-124">For information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1df1-125">De forma predeterminada, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] crea un conjunto de datos de exclusión del 30 por ciento para cada estructura de minería de datos; sin embargo, al utilizar DMX para crear una estructura de minería de datos, debe agregar el conjunto de datos de exclusiones manualmente, si así se desea.</span><span class="sxs-lookup"><span data-stu-id="c1df1-125">By default, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates a 30 percent holdout data set for each mining structure; however, when you use DMX to create a mining structure, you must manually add the holdout data set, if desired.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="c1df1-126">Tareas de la lección</span><span class="sxs-lookup"><span data-stu-id="c1df1-126">Lesson Tasks</span></span>  
 <span data-ttu-id="c1df1-127">En esta lección realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c1df1-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="c1df1-128">Crear una consulta en blanco</span><span class="sxs-lookup"><span data-stu-id="c1df1-128">Create a new blank query</span></span>  
  
-   <span data-ttu-id="c1df1-129">Modificar la consulta para crear la estructura de minería de datos</span><span class="sxs-lookup"><span data-stu-id="c1df1-129">Alter the query to create the mining structure</span></span>  
  
-   <span data-ttu-id="c1df1-130">Ejecución de la consulta</span><span class="sxs-lookup"><span data-stu-id="c1df1-130">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="c1df1-131">Crear la consulta</span><span class="sxs-lookup"><span data-stu-id="c1df1-131">Creating the Query</span></span>  
 <span data-ttu-id="c1df1-132">El primer paso es conectarse a una instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y crear una consulta DMX en [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1df1-132">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="c1df1-133">Para crear una consulta DMX mediante SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c1df1-133">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="c1df1-134">Abra [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1df1-134">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="c1df1-135">En el cuadro de diálogo **conectar con el servidor** , en **tipo de servidor**, seleccione **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="c1df1-135">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="c1df1-136">En **nombre del servidor**, escriba `LocalHost` o el nombre de la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] a la que desea conectarse para esta lección.</span><span class="sxs-lookup"><span data-stu-id="c1df1-136">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="c1df1-137">Haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="c1df1-137">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="c1df1-138">En **Explorador de objetos**, haga clic con el botón secundario en la instancia de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , seleccione **nueva consulta**y, a continuación, haga clic en **DMX**.</span><span class="sxs-lookup"><span data-stu-id="c1df1-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="c1df1-139">Se abre el Editor de consultas, que contiene una consulta nueva en blanco.</span><span class="sxs-lookup"><span data-stu-id="c1df1-139">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="c1df1-140">Modificar la consulta</span><span class="sxs-lookup"><span data-stu-id="c1df1-140">Altering the Query</span></span>  
 <span data-ttu-id="c1df1-141">El paso siguiente es modificar la instrucción CREATE MINING STRUCTURE descrita anteriormente para crear la estructura de minería de datos Market Basket.</span><span class="sxs-lookup"><span data-stu-id="c1df1-141">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Market Basket mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="c1df1-142">Para personalizar la instrucción CREATE MINING STRUCTURE</span><span class="sxs-lookup"><span data-stu-id="c1df1-142">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="c1df1-143">En el editor de consultas, copie el ejemplo genérico de la instrucción CREATE MINING STRUCTURE en la consulta en blanco.</span><span class="sxs-lookup"><span data-stu-id="c1df1-143">In Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="c1df1-144">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1df1-144">Replace the following:</span></span>  
  
    ```  
    [mining structure name]   
    ```  
  
     <span data-ttu-id="c1df1-145">por:</span><span class="sxs-lookup"><span data-stu-id="c1df1-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
3.  <span data-ttu-id="c1df1-146">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1df1-146">Replace the following:</span></span>  
  
    ```  
    <key column>  
    ```  
  
     <span data-ttu-id="c1df1-147">por:</span><span class="sxs-lookup"><span data-stu-id="c1df1-147">with:</span></span>  
  
    ```  
    OrderNumber TEXT KEY  
    ```  
  
4.  <span data-ttu-id="c1df1-148">Reemplace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1df1-148">Replace the following:</span></span>  
  
    ```  
    <table columns>  
    (  <nested key column>,  
       <nested mining structure columns> )  
    ```  
  
     <span data-ttu-id="c1df1-149">por:</span><span class="sxs-lookup"><span data-stu-id="c1df1-149">with:</span></span>  
  
    ```  
    [Products] TABLE (  
        [Model] TEXT KEY  
    )  
    ```  
  
     <span data-ttu-id="c1df1-150">El lenguaje TEXT KEY especifica que la columna Model es la columna de clave de la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="c1df1-150">The TEXT KEY language specifies that the Model column is the key column for the nested table.</span></span>  
  
     <span data-ttu-id="c1df1-151">Ahora, la instrucción completa de la estructura de minería de datos debería ser como sigue:</span><span class="sxs-lookup"><span data-stu-id="c1df1-151">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Market Basket] (  
        OrderNumber TEXT KEY,  
        [Products] TABLE (  
            [Model] TEXT KEY  
        )  
    )  
    ```  
  
5.  <span data-ttu-id="c1df1-152">En el menú **archivo** , haga clic en **Guardar DMXQuery1. DMX como**.</span><span class="sxs-lookup"><span data-stu-id="c1df1-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="c1df1-153">En el cuadro de diálogo **Guardar como** , vaya a la carpeta correspondiente y asigne el nombre al archivo `Market Basket Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="c1df1-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Market Basket Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="c1df1-154">Ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="c1df1-154">Executing the Query</span></span>  
 <span data-ttu-id="c1df1-155">El último paso es ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="c1df1-155">The final step is to execute the query.</span></span> <span data-ttu-id="c1df1-156">Después de crear y guardar una consulta, debe ejecutarse (es decir, debe ejecutarse la instrucción) para crear la estructura de minería de datos en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c1df1-156">After a query is created and saved, it needs to be executed (that is, the statement needs to be run) in order to create the mining structure on the server.</span></span> <span data-ttu-id="c1df1-157">Para obtener más información acerca de la ejecución de consultas en el editor de consultas, vea [motor de base de datos editor de consultas &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="c1df1-157">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="c1df1-158">Para ejecutar la consulta</span><span class="sxs-lookup"><span data-stu-id="c1df1-158">To execute the query</span></span>  
  
-   <span data-ttu-id="c1df1-159">En el editor de consultas, en la barra de herramientas, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c1df1-159">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="c1df1-160">El estado de la consulta se muestra en la pestaña **mensajes** , en la parte inferior del editor de consultas, una vez finalizada la ejecución de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="c1df1-160">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="c1df1-161">En Mensajes, debe aparecer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1df1-161">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="c1df1-162">Ahora hay una nueva estructura denominada cesta de la **compra** en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c1df1-162">A new structure named **Market Basket** now exists on the server.</span></span>  
  
 <span data-ttu-id="c1df1-163">En la siguiente lección agregará modelos de minería de datos a la estructura de minería de datos Market Basket que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="c1df1-163">In the next lesson, you will add mining models to the Market Basket mining structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="c1df1-164">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="c1df1-164">Next Lesson</span></span>  
 [<span data-ttu-id="c1df1-165">Lección 2: Adición de modelos de minería a la estructura de minería cesta de la compra</span><span class="sxs-lookup"><span data-stu-id="c1df1-165">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md)  
  
  
