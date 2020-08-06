---
title: Elegir y asignar los datos de prueba del modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining accuracy charts
- Mining Accuracy Chart [Analysis Services], column mappings
- input column mapping [Analysis Services]
- mapping input columns [Analysis Services]
ms.assetid: be0d9f20-40c3-4dac-81da-281cfe724126
author: minewiskan
ms.author: owend
ms.openlocfilehash: 84f1d01c40070069d610bb028ab003223c5afbcd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671840"
---
# <a name="choose-and-map-model-testing-data"></a><span data-ttu-id="83dec-102">Elegir y asignar datos de prueba para el modelo</span><span class="sxs-lookup"><span data-stu-id="83dec-102">Choose and Map Model Testing Data</span></span>
  <span data-ttu-id="83dec-103">Para crear un gráfico de precisión en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], debe elegir los datos que se utilizarán para probar el modelo y asignar dichos datos al modelo.</span><span class="sxs-lookup"><span data-stu-id="83dec-103">To create an accuracy chart in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you must choose the data that will be used to test the model, and map the data to the model.</span></span>  
  
 <span data-ttu-id="83dec-104">De forma predeterminada, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] utilizará los datos de prueba del modelo de minería de datos, siempre que se haya creado un conjunto de datos de exclusión al generar la estructura.</span><span class="sxs-lookup"><span data-stu-id="83dec-104">By default, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will use the mining model testing data, provided that you created a holdout data set when you built the mining structure.</span></span> <span data-ttu-id="83dec-105">La manera más fácil de probar los modelos basados en la misma estructura de minería de datos consiste en crear un conjunto de pruebas de exclusión, ya que los nombres de las columnas y los tipos de datos siempre coincidirán con el modelo y podrá estar casi seguro de que la distribución de los datos es similar.</span><span class="sxs-lookup"><span data-stu-id="83dec-105">Creating a holdout test set is the easiest way to test models that are based on the same mining structure, because the column names and data types will always match the model, and you can be reasonably assured that the distribution of the data is similar.</span></span> <span data-ttu-id="83dec-106">Además, el diseñador creará automáticamente las relaciones entre la columnas de entrada y las del modelo.</span><span class="sxs-lookup"><span data-stu-id="83dec-106">Also, the designer will automatically create the relationships between the input and model columns.</span></span>  
  
 <span data-ttu-id="83dec-107">Otra alternativa es especificar un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="83dec-107">Alternatively, you can specify an external source of data.</span></span> <span data-ttu-id="83dec-108">Para los datos externos, hay algunos requisitos adicionales:</span><span class="sxs-lookup"><span data-stu-id="83dec-108">For external data, there are some additional requirements:</span></span>  
  
-   <span data-ttu-id="83dec-109">El conjunto de datos externos se debe definir como una vista del origen de datos en una instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83dec-109">The external data set must be defined as a data source view in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="83dec-110">El conjunto de datos externos debe contener al menos una columna que se pueda asignar a la columna de predicción en el modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="83dec-110">The external data set must at least contain one column that can be mapped to the predictable column in the mining model.</span></span> <span data-ttu-id="83dec-111">Puede optar por omitir algunas columnas.</span><span class="sxs-lookup"><span data-stu-id="83dec-111">You can choose to ignore some columns.</span></span>  
  
-   <span data-ttu-id="83dec-112">No puede agregar columnas nuevas ni asignar columnas en una vista del origen de datos diferente.</span><span class="sxs-lookup"><span data-stu-id="83dec-112">You cannot add new columns or map columns in a different data source view.</span></span> <span data-ttu-id="83dec-113">La vista del origen de datos que seleccione debe contener todas las columnas que necesite para la consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="83dec-113">The data source view that you select must contain all the columns that you need for the prediction query.</span></span>  
  
-   <span data-ttu-id="83dec-114">Si los nombres de las columnas externas coinciden exactamente con los del modelo, el diseñador los asignará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="83dec-114">If the external column names exactly match those in the model, the designer will map them for you.</span></span> <span data-ttu-id="83dec-115">Si las asignaciones son erróneas, podrá cambiarlas, o eliminarlas y crear unas nuevas para las columnas existentes.</span><span class="sxs-lookup"><span data-stu-id="83dec-115">If the mappings are wrong, you can change them, or delete and create new mappings for existing columns.</span></span>  
  
-   <span data-ttu-id="83dec-116">Si utiliza un origen de datos externos, podrá aplicar filtros para restringir los datos de prueba a un subconjunto de casos que sea relevante.</span><span class="sxs-lookup"><span data-stu-id="83dec-116">If you use an external data source, you can apply filters to restrict the testing data to a relevant subset of cases.</span></span>  
  
-   <span data-ttu-id="83dec-117">Incluso aunque utilice el conjunto de pruebas de exclusión, deberá tener en cuenta que los filtros pueden producir diferencias entre los datos de prueba asociados con una estructura de minería de datos y los casos de prueba del modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="83dec-117">Even when you use the holdout test set, you should be aware that filters can cause differences between the testing data associated with a mining structure and the mining model test cases.</span></span>  
  
 <span data-ttu-id="83dec-118">En este tema se describe cómo elegir y asignar los datos de prueba:</span><span class="sxs-lookup"><span data-stu-id="83dec-118">This topic describes how to choose and map the testing data:</span></span>  
  
 [<span data-ttu-id="83dec-119">Seleccionar tablas de entrada para probar la precisión de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="83dec-119">Select input tables to test the accuracy of a mining model</span></span>](#bkmk_SelectInputs)  
  
 [<span data-ttu-id="83dec-120">Asignar columnas del modelo a las columnas de los datos de prueba</span><span class="sxs-lookup"><span data-stu-id="83dec-120">Map model columns to the columns in the testing data</span></span>](#bkmk_MapColumns)  
  
 [<span data-ttu-id="83dec-121">Cambiar la forma en la que las columnas de los datos de prueba se asignan al modelo</span><span class="sxs-lookup"><span data-stu-id="83dec-121">Change the way that columns in the testing data are mapped to the model</span></span>](#bkmk_ChangeMappings)  
  
##  <a name="to-select-input-tables-to-test-the-accuracy-of-a-mining-model"></a><a name="bkmk_SelectInputs"></a> <span data-ttu-id="83dec-122">Para seleccionar tablas de entrada para probar la precisión de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="83dec-122">To select input tables to test the accuracy of a mining model</span></span>  
  
1.  <span data-ttu-id="83dec-123">En el Diseñador de minería de datos de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], haga doble clic en la estructura de minería de datos que contiene los modelos de los que desea crear un gráfico.</span><span class="sxs-lookup"><span data-stu-id="83dec-123">In Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="83dec-124">Seleccione la pestaña **Gráfico de precisión de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="83dec-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="83dec-125">En la pestaña **Selección de entrada** de la vista **Gráfico de precisión de minería de datos** , seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="83dec-125">On the **Input Selection Tab** of the **Mining Accuracy Chart** view, select one of the following options:</span></span>  
  
     <span data-ttu-id="83dec-126">**Usar casos de prueba de modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="83dec-126">**Use mining model test cases**</span></span>  
  
     <span data-ttu-id="83dec-127">**Usar casos de prueba de estructura de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="83dec-127">**Use mining structure test cases**</span></span>  
  
     <span data-ttu-id="83dec-128">**Especificar otro conjunto de datos**</span><span class="sxs-lookup"><span data-stu-id="83dec-128">**Specify a different data set**</span></span>  
  
4.  <span data-ttu-id="83dec-129">Si ha seleccionado **Especificar otro conjunto de datos**, puede hacer clic en **Abrir editor de filtros** para crear condiciones de filtro en el conjunto de datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="83dec-129">If you selected **Specify a different data set**, optionally click **Open Filter Editor** to create filter conditions on the input data set.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="83dec-130">Haga clic en la pestaña **Gráfico de elevación** o la pestaña **Matriz de clasificación** para generar automáticamente el gráfico utilizando los datos de prueba que especificó.</span><span class="sxs-lookup"><span data-stu-id="83dec-130">Click the **Lift Chart** tab or the **Classification Matrix** tab to automatically build the chart by using the testing data you specified.</span></span>  
  
##  <a name="to-map-model-columns-to-the-columns-in-the-testing-data"></a><a name="bkmk_MapColumns"></a> <span data-ttu-id="83dec-131">Para asignar columnas del modelo a las columnas de los datos de prueba</span><span class="sxs-lookup"><span data-stu-id="83dec-131">To map model columns to the columns in the testing data</span></span>  
  
1.  <span data-ttu-id="83dec-132">Haga doble clic en la estructura de minería de datos que contiene los modelos de los que desea crear un gráfico para abrir la estructura y los modelos en el Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="83dec-132">Double-click the mining structure that contains the models you want to chart, to open the structure and models in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="83dec-133">Seleccione la pestaña **Gráfico de precisión de minería de datos** y luego seleccione la pestaña **Selección de entrada** .</span><span class="sxs-lookup"><span data-stu-id="83dec-133">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="83dec-134">En la pestaña **Selección de entrada** , en **Seleccionar un conjunto de datos para usarlo en un gráfico de precisión**, seleccione la opción **Especificar otro conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="83dec-134">In the **Input Selection** tab, under **Select data set to be used for Accuracy Chart**, select **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="83dec-135">Haga clic en el botón examinar **(...)** para abrir un cuadro de diálogo y generar la definición del conjunto de datos externo.</span><span class="sxs-lookup"><span data-stu-id="83dec-135">Click the browse button **(...)** to open a dialog box and build the definition of the external data set.</span></span>  
  
5.  <span data-ttu-id="83dec-136">En el cuadro de diálogo **Seleccionar estructura de minería de datos** , seleccione la estructura que contenga los modelos con los que desea trabajar y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="83dec-136">In the **Select Mining Structure** dialog box, select the mining structure that contains the models you want to work with, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="83dec-137">En la tabla **Seleccionar tabla(s) de entrada** de la pestaña **Gráfico de precisión de minería de datos** , haga clic en **Seleccionar tabla de casos** para abrir el cuadro de diálogo **Seleccionar tabla** .</span><span class="sxs-lookup"><span data-stu-id="83dec-137">On the **Select Input Table(s)** table of the **Mining Accuracy Chart** tab, click **Select Case Table** to open the **Select Table** dialog box.</span></span>  
  
7.  <span data-ttu-id="83dec-138">En el cuadro de diálogo **Seleccionar tablas** , seleccione un origen de datos de la lista **Origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="83dec-138">In the **Select Table** dialog box, select a data source from the **Data Source** list.</span></span> <span data-ttu-id="83dec-139">Elija una tabla con los datos que desee usar en las consultas de predicción para determinar la precisión de los modelos.</span><span class="sxs-lookup"><span data-stu-id="83dec-139">Choose a table that contains the data that you want to use in the prediction queries to determine the accuracy of the models.</span></span>  
  
8.  <span data-ttu-id="83dec-140">En el cuadro **Nombre de tabla o vista** , seleccione la tabla que contiene los datos que quiere usar para probar los modelos.</span><span class="sxs-lookup"><span data-stu-id="83dec-140">In the **Table/View Name** box, select the table that contains the data that you want to use to test the models.</span></span>  
  
9. <span data-ttu-id="83dec-141">Modifique las asignaciones, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="83dec-141">Edit the mappings, if necessary.</span></span> <span data-ttu-id="83dec-142">Las columnas de la estructura de minería de datos se asignan automáticamente a las columnas que tengan el mismo nombre en la tabla de entrada.</span><span class="sxs-lookup"><span data-stu-id="83dec-142">Columns in the mining structure are automatically mapped to the columns with the same name in the input table.</span></span> <span data-ttu-id="83dec-143">Para crear asignaciones manualmente, haga clic en una columna en la tabla **Seleccionar tabla(s) de entrada** y arrástrela a la columna correspondiente en la tabla **Estructura de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="83dec-143">To manually create mappings, click a column in the **Select Input Table(s)** table and drag it onto the corresponding column in the **Mining Structure** table.</span></span> <span data-ttu-id="83dec-144">Para eliminar una asignación, haga clic en la línea que vincula la columna de la tabla **Estructura de minería de datos** con la columna asignada de la tabla **Seleccionar tabla(s) de entrada** y, después, presione Suprimir.</span><span class="sxs-lookup"><span data-stu-id="83dec-144">To delete a mapping, click the line that links the column in the **Mining Structure** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="to-modify-the-way-input-data-is-mapped-to-the-model"></a><a name="bkmk_ChangeMappings"></a><span data-ttu-id="83dec-145">Para modificar la forma en que los datos de entrada se asignan al modelo</span><span class="sxs-lookup"><span data-stu-id="83dec-145">To modify the way input data is mapped to the model</span></span>  
  
1.  <span data-ttu-id="83dec-146">En el Diseñador de minería de datos, haga doble clic en la estructura que contiene los modelos que quiere incluir en un gráfico.</span><span class="sxs-lookup"><span data-stu-id="83dec-146">In Data Mining Designer, double-click the structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="83dec-147">Seleccione la pestaña **Gráfico de precisión de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="83dec-147">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="83dec-148">Haga clic en la pestaña **Selección de entrada** .</span><span class="sxs-lookup"><span data-stu-id="83dec-148">Click the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="83dec-149">En **seleccionar el conjunto de datos que se va a usar para el gráfico de precisión**, seleccione la opción **especificar un conjunto de datos diferente**.</span><span class="sxs-lookup"><span data-stu-id="83dec-149">In **Select data set to be used for Accuracy Chart**, select the option **Specify a different data set**.</span></span>  
  
5.  <span data-ttu-id="83dec-150">Haga clic en el botón examinar **(...)** para abrir un cuadro de diálogo y generar la definición del origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="83dec-150">Click the browse button **(...)** to open a dialog box and build the definition of the external data source.</span></span>  
  
6.  <span data-ttu-id="83dec-151">En el cuadro de diálogo **Especificar asignación de columnas** , haga clic en **Seleccionar tabla de casos**.</span><span class="sxs-lookup"><span data-stu-id="83dec-151">In the **Specify Column Mapping** dialog box, click **Select Case Table**.</span></span>  
  
7.  <span data-ttu-id="83dec-152">En el cuadro de diálogo Seleccionar tabla, seleccione una vista del origen de datos en la lista y la tabla que contiene los datos del caso.</span><span class="sxs-lookup"><span data-stu-id="83dec-152">In the Select Table dialog box, Select a data source view from the list, and select the table that contains the case data.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="83dec-153">Si las tablas que necesita no están disponibles, cierre el cuadro de diálogo y cree una nueva vista del origen de datos que contenga la tabla.</span><span class="sxs-lookup"><span data-stu-id="83dec-153">If the tables you need are not available, close the dialog box and create a new data source view that contains the table.</span></span> <span data-ttu-id="83dec-154">Para obtener información sobre cómo crear una vista del origen de datos, vea [Definir una vista del origen de datos &#40;Analysis Services&#41;](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="83dec-154">For information about how to create a data source view, see [Defining a Data Source View &#40;Analysis Services&#41;](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span></span>  
  
9. <span data-ttu-id="83dec-155">Si el modelo de minería de datos contiene una tabla anidada, haga clic en **Seleccionar tabla anidada**y seleccione la tabla anidada en la lista de tablas de la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="83dec-155">If the mining model contains a nested table, click **Select Nested Table**, and select the nested table from the list of tables in the data source view.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="83dec-156">Seleccione la línea de combinación de la asignación que desea modificar y seleccione **Modificar conexiones**.</span><span class="sxs-lookup"><span data-stu-id="83dec-156">Select the join line of the mapping you want to modify, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="83dec-157">Se abre el cuadro de diálogo **Modificar asignación** .</span><span class="sxs-lookup"><span data-stu-id="83dec-157">The **Modify Mapping** dialog box opens.</span></span> <span data-ttu-id="83dec-158">En la tabla de este cuadro de diálogo, **Columna de la estructura de minería de datos** incluye todas las columnas que contiene la estructura de minería de datos selecciona y **Columna de la tabla** incluye las columnas de las tablas de entrada que están asignadas a columnas en la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="83dec-158">In the table in this dialog box, **Mining Structure Column** lists each column that the selected mining structure contains, and **Table Column** lists the columns from input tables that are mapped to columns in the mining structure.</span></span>  
  
11. <span data-ttu-id="83dec-159">En **Columna de la tabla**, seleccione la fila que corresponda a la fila bajo **Columna de la estructura de minería de datos** para la que desee modificar una relación.</span><span class="sxs-lookup"><span data-stu-id="83dec-159">Under **Table Column**, select the row that corresponds to the row under **Mining Structure Column** for which you want to modify a relationship.</span></span> <span data-ttu-id="83dec-160">Seleccione una columna nueva en la lista o seleccione la entrada vacía en la lista para eliminar la columna.</span><span class="sxs-lookup"><span data-stu-id="83dec-160">Select a new column from the list, or select the blank entry from the list to delete the column.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="83dec-161">Las nuevas asignaciones de columna se muestran en el cuadro de diálogo **Especificar asignación de columnas** .</span><span class="sxs-lookup"><span data-stu-id="83dec-161">The new column mappings are displayed in the **Specify Column Mapping** dialog box.</span></span> <span data-ttu-id="83dec-162">Puede quitar una asignación seleccionando la línea entre las columnas y presionando la tecla Supr.</span><span class="sxs-lookup"><span data-stu-id="83dec-162">You can remove a mapping by selecting the line between the columns and pressing the DELETE key.</span></span> <span data-ttu-id="83dec-163">Para crear una conexión, seleccione una columna de la tabla **Estructura de minería de datos** y arrástrela hasta la columna correspondiente de la tabla **Seleccionar tabla(s) de entrada** .</span><span class="sxs-lookup"><span data-stu-id="83dec-163">You can create a new connection by selecting a column in the **Mining Structure** table and dragging it to the corresponding column in the **SelectInput Table(s)** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83dec-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83dec-164">See Also</span></span>  
 [<span data-ttu-id="83dec-165">Tareas y procedimientos de prueba y validación &#40;minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="83dec-165">Testing and Validation Tasks and How-tos &#40;Data Mining&#41;</span></span>](testing-and-validation-tasks-and-how-tos-data-mining.md)  
  
  
