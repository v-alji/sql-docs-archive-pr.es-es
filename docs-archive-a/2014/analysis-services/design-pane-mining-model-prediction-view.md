---
title: Panel de diseño (vista predicción de modelo de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.design.f1
ms.assetid: 17f24c8d-43cd-4f4d-83b3-a41ee8fbe8e8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 32ac73a2d6fde38d15d1f45a8439293695749ea4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746596"
---
# <a name="design-pane-mining-model-prediction-view"></a><span data-ttu-id="d7a83-102">Diseño (panel de la vista Predicción de modelo de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="d7a83-102">Design Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="d7a83-103">El panel **Diseño** contiene el Generador de consultas de predicción, que puede utilizar para generar predicciones de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="d7a83-103">The **Design** pane contains the Prediction Query Builder, which you can use to build data mining predictions.</span></span> <span data-ttu-id="d7a83-104">Puede diseñar consultas de predicción que usen tablas de datos de entrada de una vista del origen de datos para generar predicciones masivas o puede crear consultas de predicción singleton que permiten proporcionar valores individuales.</span><span class="sxs-lookup"><span data-stu-id="d7a83-104">You can design prediction queries that use tables of input data from a data source view, to generate bulk predictions, or you can create singleton prediction queries, which let you provide individual values.</span></span>  
  
 <span data-ttu-id="d7a83-105">Para ejecutar la consulta y ver los resultados, cambie a la vista de resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="d7a83-105">To run the query and view the results, switch to query result view.</span></span>  
  
 <span data-ttu-id="d7a83-106">La vista **Consulta** muestra la consulta Extensiones de minería de datos (DMX) que crea el Generador de consultas de predicción.</span><span class="sxs-lookup"><span data-stu-id="d7a83-106">The **Query** view displays the Data Mining Extensions (DMX) query that Prediction Query Builder creates.</span></span> <span data-ttu-id="d7a83-107">Si conoce DMX, puede personalizar esta consulta.</span><span class="sxs-lookup"><span data-stu-id="d7a83-107">If you are familiar with DMX, you can customize this query.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7a83-108">Si hace algún cambio manualmente en la consulta, los cambios se perderán al volver a la vista Diseño.</span><span class="sxs-lookup"><span data-stu-id="d7a83-108">If you make any manual changes to the query, your changes will be lost when you switch back to Design view.</span></span> <span data-ttu-id="d7a83-109">Si desea guardar la consulta DMX, puede copiar la consulta en el Portapapeles de Windows y, a continuación, pegarlo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d7a83-109">If you want to save the DMX query, you can copy the query to the Windows Clipboard and then paste it to a text file.</span></span>  
  
 <span data-ttu-id="d7a83-110">**Para obtener más información:** [Consultas de minería de datos](data-mining/data-mining-queries.md)</span><span class="sxs-lookup"><span data-stu-id="d7a83-110">**For More Information:** [Data Mining Queries](data-mining/data-mining-queries.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="d7a83-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="d7a83-111">Options</span></span>  
 <span data-ttu-id="d7a83-112">**Cambiar a vista de resultado de consulta**</span><span class="sxs-lookup"><span data-stu-id="d7a83-112">**Switch to query result view**</span></span>  
 <span data-ttu-id="d7a83-113">Haga clic para cambiar entre los paneles **Diseño**, **Consulta**y **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="d7a83-113">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="d7a83-114">Al cambiar al panel **Resultado** se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="d7a83-114">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="d7a83-115">**Guardar el resultado de la consulta**</span><span class="sxs-lookup"><span data-stu-id="d7a83-115">**Save the query result**</span></span>  
 <span data-ttu-id="d7a83-116">Abre el cuadro de diálogo **Guardar resultado de consulta de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="d7a83-116">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="d7a83-117">**Consulta singleton**</span><span class="sxs-lookup"><span data-stu-id="d7a83-117">**Singleton query**</span></span>  
 <span data-ttu-id="d7a83-118">Habilita la creación de una consulta singleton, en la que puede proporcionar valores directamente para la consulta en lugar de proporcionar una tabla como el origen de los datos conocidos.</span><span class="sxs-lookup"><span data-stu-id="d7a83-118">Enables creating a singleton query, in which you can provide values directly for the query instead of providing a table as the source of the known data.</span></span> <span data-ttu-id="d7a83-119">La tabla **Seleccionar tabla(s) de entrada** se reemplaza por una tabla **Entrada de consulta singleton** .</span><span class="sxs-lookup"><span data-stu-id="d7a83-119">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span>  
  
 <span data-ttu-id="d7a83-120">**Actualizar el resultado de la consulta**</span><span class="sxs-lookup"><span data-stu-id="d7a83-120">**Refresh query results**</span></span>  
 <span data-ttu-id="d7a83-121">Vuelve a procesar la consulta de predicción.</span><span class="sxs-lookup"><span data-stu-id="d7a83-121">Reprocesses the prediction query.</span></span> <span data-ttu-id="d7a83-122">Esto solo está habilitado en el panel **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="d7a83-122">This is enabled only in the **Result** pane.</span></span>  
  
 <span data-ttu-id="d7a83-123">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="d7a83-123">**Mining Model**</span></span>  
 <span data-ttu-id="d7a83-124">Muestra el modelo de minería de datos seleccionado en el que desea basar las predicciones.</span><span class="sxs-lookup"><span data-stu-id="d7a83-124">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="d7a83-125">**Seleccionar modelo**</span><span class="sxs-lookup"><span data-stu-id="d7a83-125">**Select Model**</span></span>  
 <span data-ttu-id="d7a83-126">Abre el cuadro de diálogo **Seleccionar modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="d7a83-126">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="d7a83-127">**Seleccionar tabla(s) de entrada**</span><span class="sxs-lookup"><span data-stu-id="d7a83-127">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="d7a83-128">Muestra las tablas de entrada seleccionadas que contienen datos conocidos en los que se basarán las predicciones.</span><span class="sxs-lookup"><span data-stu-id="d7a83-128">Displays the selected input tables that contain known data on which to base the predictions.</span></span>  
  
 <span data-ttu-id="d7a83-129">**Eliminar tabla**</span><span class="sxs-lookup"><span data-stu-id="d7a83-129">**Delete Table**</span></span>  
 <span data-ttu-id="d7a83-130">Elimina la tabla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7a83-130">Deletes the selected table.</span></span> <span data-ttu-id="d7a83-131">Esta botón se deshabilita si no existe o no se ha seleccionado una tabla.</span><span class="sxs-lookup"><span data-stu-id="d7a83-131">This button is disabled if a table has not been selected or does not exist.</span></span>  
  
 <span data-ttu-id="d7a83-132">**Seleccionar tabla de casos**</span><span class="sxs-lookup"><span data-stu-id="d7a83-132">**Select Case Table**</span></span>  
 <span data-ttu-id="d7a83-133">Abre el cuadro de diálogo **Seleccionar tabla** .</span><span class="sxs-lookup"><span data-stu-id="d7a83-133">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="d7a83-134">Este botón solo aparece si no se ha seleccionado una tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="d7a83-134">This button appears only if a case table has not been selected.</span></span>  
  
 <span data-ttu-id="d7a83-135">**Seleccionar tabla anidada**</span><span class="sxs-lookup"><span data-stu-id="d7a83-135">**Select Nested Table**</span></span>  
 <span data-ttu-id="d7a83-136">Abre el cuadro de diálogo **Seleccionar tabla** .</span><span class="sxs-lookup"><span data-stu-id="d7a83-136">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="d7a83-137">Este botón solo aparece si se ha seleccionado una tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="d7a83-137">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="d7a83-138">Este botón se deshabilita si la estructura de minería de datos asociada no contiene una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="d7a83-138">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="d7a83-139">**Modificar combinación**</span><span class="sxs-lookup"><span data-stu-id="d7a83-139">**Modify Join**</span></span>  
 <span data-ttu-id="d7a83-140">Abre el cuadro de diálogo **Especificar combinación anidada** .</span><span class="sxs-lookup"><span data-stu-id="d7a83-140">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="d7a83-141">Este botón solo está activo si se ha seleccionado una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="d7a83-141">This button is active only if the nested table is selected.</span></span>  
  
 <span data-ttu-id="d7a83-142">**Entrada de consulta singleton**</span><span class="sxs-lookup"><span data-stu-id="d7a83-142">**Singleton Query input**</span></span>  
 <span data-ttu-id="d7a83-143">Se habilita cuando selecciona el botón **Consulta singleton** .</span><span class="sxs-lookup"><span data-stu-id="d7a83-143">Enabled when you select the **Singleton query** button.</span></span> <span data-ttu-id="d7a83-144">Contiene las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d7a83-144">Contains the following columns:</span></span>  
  
|<span data-ttu-id="d7a83-145">Value</span><span class="sxs-lookup"><span data-stu-id="d7a83-145">Value</span></span>|<span data-ttu-id="d7a83-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7a83-146">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d7a83-147">**Columna del modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="d7a83-147">**Mining Model Column**</span></span>|<span data-ttu-id="d7a83-148">Muestra las columnas del modelo de minería de datos contenidas en el modelo de minería de datos seleccionado en la tabla **Modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="d7a83-148">Lists the mining model columns contained within the mining model that is selected in the **Mining Model** table.</span></span>|  
|<span data-ttu-id="d7a83-149">**Valor**</span><span class="sxs-lookup"><span data-stu-id="d7a83-149">**Value**</span></span>|<span data-ttu-id="d7a83-150">Seleccione un valor de la lista que contiene cada estado posible de la columna del modelo de minería de datos que se ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d7a83-150">Select a value from the list that contains each possible state of the selected mining model column.</span></span><br /><br /> <span data-ttu-id="d7a83-151">Si la columna es una columna de tabla anidada, haga clic en la celda de valor para abrir el cuadro de diálogo **Entrada de tabla anidada** .</span><span class="sxs-lookup"><span data-stu-id="d7a83-151">If the column is a nested table column, clicking the value cell opens the **Nested Table Input** dialog box.</span></span>|  
  
 <span data-ttu-id="d7a83-152">**Origen**</span><span class="sxs-lookup"><span data-stu-id="d7a83-152">**Source**</span></span>  
 <span data-ttu-id="d7a83-153">Seleccione el origen que contiene el campo que utilizará para la columna.</span><span class="sxs-lookup"><span data-stu-id="d7a83-153">Select the source that contains the field that you will use for the column.</span></span> <span data-ttu-id="d7a83-154">Puede usar el modelo de minería de datos seleccionado en la tabla **Modelo de minería de datos** , la tabla o las tablas seleccionadas en la tabla **Seleccionar tabla(s) de entrada** , una función de predicción o una expresión personalizada.</span><span class="sxs-lookup"><span data-stu-id="d7a83-154">You can either use the mining model that is selected in the **Mining Model** table, the input table or tables that are selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="d7a83-155">Se puede arrastrar las columnas de las tablas que contienen el modelo de minería de datos y las tablas de entrada a la celda.</span><span class="sxs-lookup"><span data-stu-id="d7a83-155">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
 <span data-ttu-id="d7a83-156">**Campo**</span><span class="sxs-lookup"><span data-stu-id="d7a83-156">**Field**</span></span>  
 <span data-ttu-id="d7a83-157">En la tabla de origen, seleccione una columna de la lista de columnas derivadas.</span><span class="sxs-lookup"><span data-stu-id="d7a83-157">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="d7a83-158">Si ha seleccionado **Función de predicción** en **Origen**, ésta contiene la función de predicción disponible para el modelo de minería de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d7a83-158">If you selected **Prediction Function** in **Source**, this contains the prediction function available for the selected mining model.</span></span>  
  
 <span data-ttu-id="d7a83-159">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="d7a83-159">**Group**</span></span>  
 <span data-ttu-id="d7a83-160">Use esta opción con la columna **Y/O** para agrupar expresiones.</span><span class="sxs-lookup"><span data-stu-id="d7a83-160">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="d7a83-161">Por ejemplo, `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="d7a83-161">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="d7a83-162">**Y/o**</span><span class="sxs-lookup"><span data-stu-id="d7a83-162">**And/Or**</span></span>  
 <span data-ttu-id="d7a83-163">Utilice esta opción para crear una consulta lógica.</span><span class="sxs-lookup"><span data-stu-id="d7a83-163">Use to create a logical query.</span></span> <span data-ttu-id="d7a83-164">Por ejemplo, `(expr1 Or expr2) And expr3`.</span><span class="sxs-lookup"><span data-stu-id="d7a83-164">For example, `(expr1 Or expr2) And expr3`.</span></span>  
  
 <span data-ttu-id="d7a83-165">**Criterios o argumento**</span><span class="sxs-lookup"><span data-stu-id="d7a83-165">**Criteria/Argument**</span></span>  
 <span data-ttu-id="d7a83-166">Especifique una condición o una expresión de usuario que se aplica a la columna.</span><span class="sxs-lookup"><span data-stu-id="d7a83-166">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="d7a83-167">Se puede arrastrar las columnas de las tablas que contienen el modelo de minería de datos y las tablas de entrada a la celda.</span><span class="sxs-lookup"><span data-stu-id="d7a83-167">Columns can be dragged from the tables containing the mining model and input tables onto the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a83-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d7a83-168">See Also</span></span>  
 <span data-ttu-id="d7a83-169">[Referencia de instrucciones de extensiones de minería de datos &#40;DMX&#41;](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="d7a83-169">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 <span data-ttu-id="d7a83-170">[Interfaces de consulta de minería de datos](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="d7a83-170">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="d7a83-171">Generador de consultas de predicción &#40;Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="d7a83-171">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
