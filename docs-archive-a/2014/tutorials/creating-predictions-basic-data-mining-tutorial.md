---
title: Crear predicciones (tutorial básico de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a8410ed2-bb98-4d51-a9eb-b239be1201c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 456aec6c6b9d0d1a5d0ee1d9949507a37577130c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743720"
---
# <a name="creating-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="0e391-102">Crear predicciones (Tutorial básico de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="0e391-102">Creating Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="0e391-103">Después de probar la precisión de los modelos de minería de datos y decidir que está satisfecho con los resultados, puede generar predicciones mediante el Generador de consultas de predicción en la pestaña **predicción de modelo de minería** de datos del diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="0e391-103">After you have tested the accuracy of your mining models and decided that you are satisfied with the results, you can then generate predictions by using the Prediction Query Builder on the **Mining Model Prediction** tab in the Data Mining Designer.</span></span>  
  
 <span data-ttu-id="0e391-104">El Generador de consultas de predicción tiene tres vistas.</span><span class="sxs-lookup"><span data-stu-id="0e391-104">The Prediction Query Builder has three views.</span></span> <span data-ttu-id="0e391-105">Con las vistas **diseño** y **consulta** , puede compilar y examinar la consulta.</span><span class="sxs-lookup"><span data-stu-id="0e391-105">With the **Design** and **Query** views, you can build and examine your query.</span></span> <span data-ttu-id="0e391-106">Después, puede ejecutar la consulta y ver los resultados en la vista de **resultados** .</span><span class="sxs-lookup"><span data-stu-id="0e391-106">You can then run the query and view the results in the **Result** view.</span></span>  
  
 <span data-ttu-id="0e391-107">Todas las consultas de predicción utilizan DMX, que es el acrónimo del lenguaje de Extensiones de minería de datos (DMX).</span><span class="sxs-lookup"><span data-stu-id="0e391-107">All prediction queries use DMX, which is short for the Data Mining Extensions (DMX) language.</span></span> <span data-ttu-id="0e391-108">DMX tiene una sintaxis similar a la de T-SQL, pero se utiliza con consultas en objetos de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="0e391-108">DMX has syntax like that of T-SQL but is used for queries against data mining objects.</span></span> <span data-ttu-id="0e391-109">Aunque la sintaxis DMX no es complicada, el uso de un generador de consultas como este, o el de los [Complementos de minería de datos SQL Server para Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md), facilita la selección de entradas y expresiones de compilación, por lo que se recomienda encarecidamente conocer los aspectos básicos.</span><span class="sxs-lookup"><span data-stu-id="0e391-109">Although DMX syntax is not complicated, using a query builder like this one, or the one in the [SQL Server Data Mining Add-Ins for Office](../../2014/analysis-services/data-mining/sql-server-data-mining-add-ins-for-office.md), makes it much easier to select inputs and build expressions, so we highly recommend that you learn the basics.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="0e391-110">Crear la consulta</span><span class="sxs-lookup"><span data-stu-id="0e391-110">Creating the Query</span></span>  
 <span data-ttu-id="0e391-111">El primer paso para crear una consulta de predicción consiste en seleccionar un modelo de minería de datos y una tabla de entrada.</span><span class="sxs-lookup"><span data-stu-id="0e391-111">The first step in creating a prediction query is to select a mining model and input table.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="0e391-112">Para seleccionar un modelo de minería de datos y una tabla de entrada</span><span class="sxs-lookup"><span data-stu-id="0e391-112">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="0e391-113">En la pestaña **predicción de modelo de minería** de datos del diseñador de minería de datos, en el cuadro modelo de **minería** de datos, haga clic en **Seleccionar modelo**.</span><span class="sxs-lookup"><span data-stu-id="0e391-113">On the **Mining Model Prediction** tab of Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="0e391-114">En el cuadro de diálogo **Seleccionar modelo de minería de datos** , desplácese por el árbol hasta la estructura de **correo de destino** , expanda la estructura, seleccione y, `TM_Decision_Tree` a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e391-114">In the **Select Mining Model** dialog box, navigate through the tree to the **Targeted Mailing** structure, expand the structure, select `TM_Decision_Tree`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="0e391-115">En el cuadro **seleccionar tabla (s) de entrada** , haga clic en **seleccionar tabla de casos**.</span><span class="sxs-lookup"><span data-stu-id="0e391-115">In the **Select Input Table(s)** box, click **Select Case Table**.</span></span>  
  
4.  <span data-ttu-id="0e391-116">En el cuadro de diálogo **seleccionar tabla** , en la lista **origen de datos** , seleccione la vista del origen de datos [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0e391-116">In the **Select Table** dialog box, in the **Data Source** list, select the data source view [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span>  
  
5.  <span data-ttu-id="0e391-117">En **nombre de tabla o vista**, seleccione la tabla **ProspectiveBuyer (DBO)** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e391-117">In **Table/View Name**, select the **ProspectiveBuyer (dbo)** table, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0e391-118">La `ProspectiveBuyer` tabla es muy similar a la tabla de casos **vTargetMail** .</span><span class="sxs-lookup"><span data-stu-id="0e391-118">The `ProspectiveBuyer` table most closely resembles the **vTargetMail** case table.</span></span>  
  
## <a name="mapping-the-columns"></a><span data-ttu-id="0e391-119">Asignar las columnas</span><span class="sxs-lookup"><span data-stu-id="0e391-119">Mapping the Columns</span></span>  
 <span data-ttu-id="0e391-120">Después de seleccionar la tabla de entrada, el Generador de consultas de predicción crea una asignación predeterminada entre el modelo de minería de datos y la tabla de entrada, en función de los nombres de las columnas.</span><span class="sxs-lookup"><span data-stu-id="0e391-120">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="0e391-121">Al menos una columna de la estructura debe coincidir con una columna de los datos externos.</span><span class="sxs-lookup"><span data-stu-id="0e391-121">At least one column from the structure must match a column in the external data.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0e391-122">Los datos que use para determinar la precisión de los modelos deben contener una columna que se pueda asignar a la columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="0e391-122">The data that you use to determine the accuracy of the models must contain a column that can be mapped to the predictable column.</span></span> <span data-ttu-id="0e391-123">Si no existe esa columna, puede crear una con valores vacíos, pero debe tener el mismo tipo de datos que la columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="0e391-123">If such a column does not exist, you can create one with empty values, but it must have the same data type as the predictable column.</span></span>  
  
#### <a name="to-map-the-inputs-to-the-model"></a><span data-ttu-id="0e391-124">Para asignar las entradas al modelo</span><span class="sxs-lookup"><span data-stu-id="0e391-124">To map the inputs to the model</span></span>  
  
1.  <span data-ttu-id="0e391-125">Haga clic con el botón secundario en las líneas que conectan la ventana **modelo de minería de datos** a la ventana **seleccionar tabla de entrada** y seleccione **modificar conexiones**.</span><span class="sxs-lookup"><span data-stu-id="0e391-125">Right-click the lines connecting the **Mining Model** window to the **Select Input Table** window, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="0e391-126">Observe que no todas las columnas están asignadas.</span><span class="sxs-lookup"><span data-stu-id="0e391-126">Notice that not every column is mapped.</span></span> <span data-ttu-id="0e391-127">Agregaremos asignaciones para varias columnas de la **tabla**.</span><span class="sxs-lookup"><span data-stu-id="0e391-127">We will add mappings for several **Table Columns**.</span></span> <span data-ttu-id="0e391-128">También generaremos una columna de fecha de nacimiento nueva en función de la columna de fecha actual, para que la coincidencia de las columnas sea mejor.</span><span class="sxs-lookup"><span data-stu-id="0e391-128">We will also generate a new birth date column based on the current date column, so that the columns match better.</span></span>  
  
2.  <span data-ttu-id="0e391-129">En **columna**de la tabla, haga clic en la `Bike Buyer` celda y seleccione ProspectiveBuyer. Unknown en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0e391-129">Under **Table Column**, click the `Bike Buyer` cell and select ProspectiveBuyer.Unknown from the dropdown.</span></span>  
  
     <span data-ttu-id="0e391-130">De esta forma se asigna la columna de predicción, [Bike Buyer], a una columna de la tabla de entrada.</span><span class="sxs-lookup"><span data-stu-id="0e391-130">This maps the predictable column, [Bike Buyer], to an input table column.</span></span>  
  
3.  <span data-ttu-id="0e391-131">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e391-131">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="0e391-132">En **Explorador de soluciones**, haga clic con el botón secundario en la vista del origen de datos **Targeted mailing** y seleccione **Diseñador de vistas**.</span><span class="sxs-lookup"><span data-stu-id="0e391-132">In **Solution Explorer**, right-click the **Targeted Mailing** data source view and select **View Designer**.</span></span>  
  
5.  <span data-ttu-id="0e391-133">Haga clic con el botón secundario en la tabla ProspectiveBuyer y seleccione **nuevo cálculo con nombre**.</span><span class="sxs-lookup"><span data-stu-id="0e391-133">Right-click the table, ProspectiveBuyer, and select **New Named Calculation**.</span></span>  
  
6.  <span data-ttu-id="0e391-134">En el cuadro de diálogo **crear cálculo con nombre** , en **nombre de columna**, escriba `calcAge` .</span><span class="sxs-lookup"><span data-stu-id="0e391-134">In the **Create Named Calculation** dialog box, for **Column name**, type `calcAge`.</span></span>  
  
7.  <span data-ttu-id="0e391-135">En **Descripción**, escriba **Calculate Age based on FechaNacimiento**.</span><span class="sxs-lookup"><span data-stu-id="0e391-135">For **Description**, type **Calculate age based on birthdate**.</span></span>  
  
8.  <span data-ttu-id="0e391-136">En el cuadro **expresión** , escriba `DATEDIFF(YYYY,[BirthDate],getdate())` y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e391-136">In the **Expression** box, type `DATEDIFF(YYYY,[BirthDate],getdate())` and then click **OK**.</span></span>  
  
     <span data-ttu-id="0e391-137">Dado que la tabla de entrada no tiene ninguna columna **Age** que se corresponda con la del modelo, puede utilizar esta expresión para calcular la edad del cliente a partir de la columna FechaNacimiento de la tabla de entrada.</span><span class="sxs-lookup"><span data-stu-id="0e391-137">Because the input table has no **Age** column corresponding to the one in the model, you can use this expression to calculate customer age from the BirthDate column in the input table.</span></span> <span data-ttu-id="0e391-138">Como la **edad** se identificó como la columna más influyente para predecir la compra de bicicletas, debe existir en el modelo y en la tabla de entrada.</span><span class="sxs-lookup"><span data-stu-id="0e391-138">Since **Age** was identified as the most influential column for predicting bike buying, it must exist in both the model and in the input table.</span></span>  
  
9. <span data-ttu-id="0e391-139">En el diseñador de minería de datos, seleccione la pestaña **predicción de modelo de minería** de datos y vuelva a abrir la ventana **modificar conexiones** .</span><span class="sxs-lookup"><span data-stu-id="0e391-139">In Data Mining Designer, select the **Mining Model Prediction** tab and re-open the **Modify Connections** window.</span></span>  
  
10. <span data-ttu-id="0e391-140">En **columna**de la tabla, haga clic en la celda **Age** y seleccione ProspectiveBuyer. Calc en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="0e391-140">Under **Table Column**, click the **Age** cell and select ProspectiveBuyer.calcAge from the dropdown.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="0e391-141">Si no ve la columna en la lista, puede que tenga que actualizar la definición de la vista del origen de datos que se ha cargado en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="0e391-141">If you do not see the column in the list, you might have to refresh the definition of the data source view that is loaded in the designer.</span></span> <span data-ttu-id="0e391-142">Para ello, en el menú **archivo** , seleccione **guardar todo**y, a continuación, cierre y vuelva a abrir el proyecto en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="0e391-142">To do this, from the **File** menu, select **Save all**, and then close and re-open the project in the designer.</span></span>  
  
11. <span data-ttu-id="0e391-143">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e391-143">Click **OK**.</span></span>  
  
## <a name="designing-the-prediction-query"></a><span data-ttu-id="0e391-144">Diseñar la consulta de predicción</span><span class="sxs-lookup"><span data-stu-id="0e391-144">Designing the Prediction Query</span></span>  
  
1.  <span data-ttu-id="0e391-145">El primer botón de la barra de herramientas de la pestaña **predicción de modelo de minería de datos** es el botón **cambiar a vista de diseño/cambiar a vista de resultado/cambiar a vista de consulta** .</span><span class="sxs-lookup"><span data-stu-id="0e391-145">The first button on the toolbar of the **Mining Model Prediction** tab is the **Switch to design view / Switch to result view / Switch to query view** button.</span></span> <span data-ttu-id="0e391-146">Haga clic en la flecha hacia abajo de este botón y seleccione **diseño**.</span><span class="sxs-lookup"><span data-stu-id="0e391-146">Click the down arrow on this button, and select **Design**.</span></span>  
  
2.  <span data-ttu-id="0e391-147">En la cuadrícula de la pestaña **predicción de modelo de minería de datos** , haga clic en la celda de la primera fila vacía de la columna **origen** y, a continuación, seleccione **función de predicción**.</span><span class="sxs-lookup"><span data-stu-id="0e391-147">In the grid on the **Mining Model Prediction** tab, click the cell in the first empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
3.  <span data-ttu-id="0e391-148">En la fila **función de predicción** , en la columna **campo** , seleccione `PredictProbability` .</span><span class="sxs-lookup"><span data-stu-id="0e391-148">In the **Prediction Function** row, in the **Field** column, select `PredictProbability`.</span></span>  
  
     <span data-ttu-id="0e391-149">En la columna **alias** de la misma fila, escriba **probabilidad de resultado**.</span><span class="sxs-lookup"><span data-stu-id="0e391-149">In the **Alias** column of the same row, type **Probability of result**.</span></span>  
  
4.  <span data-ttu-id="0e391-150">En la ventana **modelo de minería de datos** anterior, seleccione y arrastre [Bike Buyer] a la celda **criterios o argumento** .</span><span class="sxs-lookup"><span data-stu-id="0e391-150">From the **Mining Model** window above, select and drag [Bike Buyer] into the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="0e391-151">Cuando lo permita, [TM_Decision_Tree]. [Bike Buyer] aparece en la celda **criterios o argumento** .</span><span class="sxs-lookup"><span data-stu-id="0e391-151">When you let go, [TM_Decision_Tree].[Bike Buyer] appears in the **Criteria/Argument** cell.</span></span>  
  
     <span data-ttu-id="0e391-152">De esta forma, se especificará la columna de destino para la función `PredictProbability`.</span><span class="sxs-lookup"><span data-stu-id="0e391-152">This specifies the target column for the `PredictProbability` function.</span></span> <span data-ttu-id="0e391-153">Para obtener más información acerca de las funciones, consulte [extensiones de minería de datos &#40;referencia de funciones DMX&#41;](/sql/dmx/data-mining-extensions-dmx-function-reference).</span><span class="sxs-lookup"><span data-stu-id="0e391-153">For more information about functions, see [Data Mining Extensions &#40;DMX&#41; Function Reference](/sql/dmx/data-mining-extensions-dmx-function-reference).</span></span>  
  
5.  <span data-ttu-id="0e391-154">Haga clic en la siguiente fila vacía de la columna **origen** y, a continuación, seleccione **TM_Decision_Tree** modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="0e391-154">Click the next empty row in the **Source** column, and then select **TM_Decision_Tree** mining model.</span></span>  
  
6.  <span data-ttu-id="0e391-155">En la `TM_Decision_Tree` fila, en la columna **campo** , seleccione `Bike Buyer` .</span><span class="sxs-lookup"><span data-stu-id="0e391-155">In the `TM_Decision_Tree` row, in the **Field** column, select `Bike Buyer`.</span></span>  
  
7.  <span data-ttu-id="0e391-156">En la `TM_Decision_Tree` fila, en la columna **criterios o argumento** , escriba `=1` .</span><span class="sxs-lookup"><span data-stu-id="0e391-156">In the `TM_Decision_Tree` row, in the **Criteria/Argument** column, type `=1`.</span></span>  
  
8.  <span data-ttu-id="0e391-157">Haga clic en la siguiente fila vacía de la columna **origen** y, a continuación, seleccione **tabla ProspectiveBuyer**.</span><span class="sxs-lookup"><span data-stu-id="0e391-157">Click the next empty row in the **Source** column, and then select **ProspectiveBuyer table**.</span></span>  
  
9. <span data-ttu-id="0e391-158">En la `ProspectiveBuyer` fila, en la columna **campo** , seleccione **ProspectiveBuyerKey**.</span><span class="sxs-lookup"><span data-stu-id="0e391-158">In the `ProspectiveBuyer` row, in the **Field** column, select **ProspectiveBuyerKey**.</span></span>  
  
     <span data-ttu-id="0e391-159">De esta forma, se agregará el identificador único a la consulta de predicción para que pueda identificar quién es más y menos probable que compre una bicicleta.</span><span class="sxs-lookup"><span data-stu-id="0e391-159">This adds the unique identifier to the prediction query so that you can identify who is and who is not likely to buy a bicycle.</span></span>  
  
10. <span data-ttu-id="0e391-160">Agregue cinco filas más a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0e391-160">Add five more rows to the grid.</span></span> <span data-ttu-id="0e391-161">En cada fila, seleccione la **tabla ProspectiveBuyer** como **origen** y, a continuación, agregue las columnas siguientes en las celdas **campo** :</span><span class="sxs-lookup"><span data-stu-id="0e391-161">For each row, select **ProspectiveBuyer table** as the **Source** and then add the following columns in the **Field** cells:</span></span>  
  
    -   <span data-ttu-id="0e391-162">calcAge</span><span class="sxs-lookup"><span data-stu-id="0e391-162">calcAge</span></span>  
  
    -   <span data-ttu-id="0e391-163">Apellidos</span><span class="sxs-lookup"><span data-stu-id="0e391-163">LastName</span></span>  
  
    -   <span data-ttu-id="0e391-164">Nombre</span><span class="sxs-lookup"><span data-stu-id="0e391-164">FirstName</span></span>  
  
    -   <span data-ttu-id="0e391-165">AddressLine1</span><span class="sxs-lookup"><span data-stu-id="0e391-165">AddressLine1</span></span>  
  
    -   <span data-ttu-id="0e391-166">AddressLine2</span><span class="sxs-lookup"><span data-stu-id="0e391-166">AddressLine2</span></span>  
  
 <span data-ttu-id="0e391-167">Finalmente, ejecute la consulta y examine los resultados.</span><span class="sxs-lookup"><span data-stu-id="0e391-167">Finally, run the query and browse the results.</span></span>  
  
 <span data-ttu-id="0e391-168">La **predicción generador de consultas** también incluye estos controles:</span><span class="sxs-lookup"><span data-stu-id="0e391-168">The **Prediction Query Builder** also includes these controls:</span></span>  
  
-   <span data-ttu-id="0e391-169">**Mostrar** casilla</span><span class="sxs-lookup"><span data-stu-id="0e391-169">**Show** check box</span></span>  
  
     <span data-ttu-id="0e391-170">Permite quitar cláusulas de la consulta sin tener que eliminarlas desde el diseñador.</span><span class="sxs-lookup"><span data-stu-id="0e391-170">Lets you remove clauses from the query without having to delete them from the designer.</span></span> <span data-ttu-id="0e391-171">Esto puede resultar útil cuando se trabaja con consultas complejas y se desear conservar la sintaxis sin tener que copiar y pegar DMX en la ventana.</span><span class="sxs-lookup"><span data-stu-id="0e391-171">This can be useful when you are working with complex queries and want to preserve syntax without having to copy and paste DMX into the window.</span></span>  
  
-   <span data-ttu-id="0e391-172">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="0e391-172">**Group**</span></span>  
  
     <span data-ttu-id="0e391-173">Inserta un paréntesis de apertura (izquierdo) al principio de la línea seleccionada o inserta un paréntesis de cierre (derecho) al final de la línea actual.</span><span class="sxs-lookup"><span data-stu-id="0e391-173">Inserts an opening (left) parentheses at the beginning of the selected line, or inserts a closing (right) parenthesis at the end of the current line.</span></span>  
  
-   <span data-ttu-id="0e391-174">**Y/O**</span><span class="sxs-lookup"><span data-stu-id="0e391-174">**AND/OR**</span></span>  
  
     <span data-ttu-id="0e391-175">Inserta el operador `AND` o el operador `OR` inmediatamente después de la función o columna actual.</span><span class="sxs-lookup"><span data-stu-id="0e391-175">Inserts the  `AND` operator or the `OR` operator immediately after the current function or column.</span></span>  
  
#### <a name="to-run-the-query-and-view-results"></a><span data-ttu-id="0e391-176">Para ejecutar la consulta y ver los resultados</span><span class="sxs-lookup"><span data-stu-id="0e391-176">To run the query and view results</span></span>  
  
1.  <span data-ttu-id="0e391-177">En la pestaña **predicción de modelo de minería de datos** , seleccione el botón **resultado** .</span><span class="sxs-lookup"><span data-stu-id="0e391-177">In the **Mining Model Prediction** tab, select the **Result** button.</span></span>  
  
2.  <span data-ttu-id="0e391-178">Una vez que la consulta se ejecute y se muestren los resultados, puede revisarlos.</span><span class="sxs-lookup"><span data-stu-id="0e391-178">After the query runs and the results are displayed, you can review the results.</span></span>  
  
     <span data-ttu-id="0e391-179">La pestaña **predicción de modelo de minería de datos** muestra información de contacto de los clientes potenciales que probablemente sean compradores de bicicletas.</span><span class="sxs-lookup"><span data-stu-id="0e391-179">The **Mining Model Prediction** tab displays contact information for potential customers who are likely to be bike buyers.</span></span> <span data-ttu-id="0e391-180">La columna **probabilidad de resultado** indica la probabilidad de que la predicción sea correcta.</span><span class="sxs-lookup"><span data-stu-id="0e391-180">The **Probability of result** column indicates the probability of the prediction being correct.</span></span> <span data-ttu-id="0e391-181">Puede utilizar estos resultados para determinar a qué clientes potenciales debe dirigirse en el correo.</span><span class="sxs-lookup"><span data-stu-id="0e391-181">You can use these results to determine which potential customers to target for the mailing.</span></span>  
  
3.  <span data-ttu-id="0e391-182">En este punto, puede guardar los resultados.</span><span class="sxs-lookup"><span data-stu-id="0e391-182">At this point, you can save the results.</span></span> <span data-ttu-id="0e391-183">Tiene tres opciones:</span><span class="sxs-lookup"><span data-stu-id="0e391-183">You have three options:</span></span>  
  
    -   <span data-ttu-id="0e391-184">Haga clic con el botón secundario en una fila de datos de los resultados y seleccione **copiar** para guardar solo ese valor (y el encabezado de columna) en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0e391-184">Right-click a row of data in the results, and select **Copy** to save just that value (and the column heading) to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="0e391-185">Haga clic con el botón secundario en cualquier fila de los resultados y seleccione **copiar todo** para copiar todo el conjunto de resultados, incluidos los encabezados de columna, en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="0e391-185">Right-click any row in the results, and select **Copy All** to copy the entire result set, including column headings, to the Clipboard.</span></span>  
  
    -   <span data-ttu-id="0e391-186">Haga clic en **Guardar resultado** de la consulta para guardar los resultados directamente en una base de datos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0e391-186">Click **Save query result** to save the results directly to a database as follows:</span></span>  
  
        1.  <span data-ttu-id="0e391-187">En el cuadro de diálogo **Guardar resultado de consulta de minería de datos** , seleccione un origen de datos o defina un nuevo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0e391-187">In the **Save Data Mining Query Result** dialog box, select a data source, or define a new data source.</span></span>  
  
        2.  <span data-ttu-id="0e391-188">Escriba un nombre para la tabla que contendrá los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="0e391-188">Type a name for the table that will contain the query results.</span></span>  
  
        3.  <span data-ttu-id="0e391-189">Use la opción **Agregar a DSV**para crear la tabla y agregarla a una vista del origen de datos existente.</span><span class="sxs-lookup"><span data-stu-id="0e391-189">Use the option, **Add to DSV**, to create the table and add it to an existing data source view.</span></span> <span data-ttu-id="0e391-190">Esto resulta útil si desea conservar todas las tablas relacionadas para un modelo, como los datos de entrenamiento, los datos de origen de la predicción y los resultados de la consulta, en la misma vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0e391-190">This is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source view.</span></span>  
  
        4.  <span data-ttu-id="0e391-191">Use la opción **sobrescribir si existe**, para actualizar una tabla existente con los resultados más recientes.</span><span class="sxs-lookup"><span data-stu-id="0e391-191">Use the option, **Overwrite if exists**, to update an existing table with the latest results.</span></span>  
  
             <span data-ttu-id="0e391-192">Debe utilizar la opción de sobrescribir la tabla si ha agregado algunas columnas a la consulta de predicción, cambiado los nombres o los tipos de datos de las columnas en la consulta de predicción, o si ha ejecutado alguna instrucción ALTER en la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="0e391-192">You must use the option to overwrite the table if you have added any columns to the prediction query, changed the names or data types of any columns in the prediction query, or if you have run any ALTER statements on the destination table.</span></span>  
  
             <span data-ttu-id="0e391-193">Además, si varias columnas tienen el mismo nombre (por ejemplo, la **expresión**de nombre de columna predeterminada), debe crear un alias para las columnas con nombres duplicados, o se producirá un error cuando el diseñador intente guardar los resultados en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0e391-193">Also, if multiple columns have the same name (for example, the default column name **Expression**) you must create an alias for the columns with duplicate names, or an error will be raised when the designer tries to save the results to SQL Server.</span></span> <span data-ttu-id="0e391-194">La razón es que SQL Server no permite que varias columnas tengan el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="0e391-194">The reason is that SQL Server does not allow multiple columns to have the same name.</span></span>  
  
             <span data-ttu-id="0e391-195">Para obtener más información, vea [cuadro de diálogo Guardar resultado de consulta de minería de datos &#40;vista predicción de modelo de minería de datos&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span><span class="sxs-lookup"><span data-stu-id="0e391-195">For more information, see [Save Data Mining Query Result Dialog Box &#40;Mining Model Prediction View&#41;](../../2014/analysis-services/save-data-mining-query-result-dialog-box-mining-model-prediction-view.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0e391-196">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="0e391-196">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0e391-197">Usar la obtención de detalles en datos de estructura &#40;tutorial básico de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="0e391-197">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="0e391-198">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e391-198">See Also</span></span>  
 [<span data-ttu-id="0e391-199">Crear una consulta de predicción con el Generador de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="0e391-199">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
