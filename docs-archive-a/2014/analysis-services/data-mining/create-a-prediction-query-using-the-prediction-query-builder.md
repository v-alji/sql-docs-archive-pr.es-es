---
title: Cree una consulta de predicción mediante la Generador de consultas de predicción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- Mining Model Prediction [Analysis Services], prediction queries
ms.assetid: e02836e5-dd8c-4c97-a078-840ae79d3660
author: minewiskan
ms.author: owend
ms.openlocfilehash: 13f39de4085cb74949e9540570d574c09e72ee27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663800"
---
# <a name="create-a-prediction-query-using-the-prediction-query-builder"></a><span data-ttu-id="8f393-102">Crear una consulta de predicción con el Generador de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="8f393-102">Create a Prediction Query Using the Prediction Query Builder</span></span>
  <span data-ttu-id="8f393-103">Puede crear consultas de predicción mientras está generando una solución de minería de datos en BI Development Studio o al hacer clic con el botón derecho en un modelo de minería de datos existente en SQL Server Management Studio y, después, elegir la opción **Generar consulta de predicción**.</span><span class="sxs-lookup"><span data-stu-id="8f393-103">You can create prediction queries either while you are building a data mining solution in BI Development Studio, or by right-clicking an existing mining model in SQL Server Management Studio, and then choosing the option, **Build Prediction Query**.</span></span>  
  
 <span data-ttu-id="8f393-104">El **Generador de consultas de predicción** tiene los tres modos de diseño siguientes, entre los que puede cambiar haciendo clic en los iconos en la esquina superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="8f393-104">The **Prediction Query Builder** has the following three design modes, which you can switch among by clicking the icons in the upper-left corner.</span></span>  
  
-   <span data-ttu-id="8f393-105">**Diseño**</span><span class="sxs-lookup"><span data-stu-id="8f393-105">**Design**</span></span>  
  
-   <span data-ttu-id="8f393-106">**Consultar**</span><span class="sxs-lookup"><span data-stu-id="8f393-106">**Query**</span></span>  
  
-   <span data-ttu-id="8f393-107">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="8f393-107">**Result**</span></span>  
  
 <span data-ttu-id="8f393-108">El modo**Diseño** permite generar una consulta de predicción eligiendo los datos de entrada, asignando los datos al modelo y, después, agregando funciones de predicción en instrucciones que se generan utilizando la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8f393-108">**Design** mode lets you build a prediction query by choosing input data, mapping the data to the model, and then adding prediction functions into statements you build by using the grid.</span></span> <span data-ttu-id="8f393-109">La cuadrícula de diseño contiene estos bloques de creación:</span><span class="sxs-lookup"><span data-stu-id="8f393-109">The design grid contains these building blocks:</span></span>  
  
 <span data-ttu-id="8f393-110">**Origen**</span><span class="sxs-lookup"><span data-stu-id="8f393-110">**Source**</span></span>  
 <span data-ttu-id="8f393-111">Elija el origen de la nueva columna.</span><span class="sxs-lookup"><span data-stu-id="8f393-111">Choose the source of the new column.</span></span> <span data-ttu-id="8f393-112">Puede utilizar columnas del modelo de minería de datos, las tablas de entrada incluidas en la vista del origen de datos, una función de predicción o una expresión personalizada.</span><span class="sxs-lookup"><span data-stu-id="8f393-112">You can use columns from the mining model, input tables included in the data source view, a prediction function, or a customized expression.</span></span>  
  
 <span data-ttu-id="8f393-113">**Campo**</span><span class="sxs-lookup"><span data-stu-id="8f393-113">**Field**</span></span>  
 <span data-ttu-id="8f393-114">Determina la columna o función específica asociada con la selección de la columna **Origen** .</span><span class="sxs-lookup"><span data-stu-id="8f393-114">Determines the specific column or function that is associated with the selection in the **Source** column.</span></span>  
  
 <span data-ttu-id="8f393-115">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8f393-115">**Alias**</span></span>  
 <span data-ttu-id="8f393-116">Determina cuál será el nombre de la columna en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="8f393-116">Determines how the column is to be named in the result set.</span></span>  
  
 <span data-ttu-id="8f393-117">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="8f393-117">**Show**</span></span>  
 <span data-ttu-id="8f393-118">Determina si la selección de la columna **Origen** aparecerá en los resultados.</span><span class="sxs-lookup"><span data-stu-id="8f393-118">Determines whether the selection in the **Source** column is displayed in the results.</span></span>  
  
 <span data-ttu-id="8f393-119">**Grupo**</span><span class="sxs-lookup"><span data-stu-id="8f393-119">**Group**</span></span>  
 <span data-ttu-id="8f393-120">Funciona con la columna **Y/O** para agrupar expresiones mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="8f393-120">Works with the **And/Or** column to group expressions together by using parentheses.</span></span> <span data-ttu-id="8f393-121">Por ejemplo, (expr1 o expr2) y expr3.</span><span class="sxs-lookup"><span data-stu-id="8f393-121">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="8f393-122">**Y/o**</span><span class="sxs-lookup"><span data-stu-id="8f393-122">**And/Or**</span></span>  
 <span data-ttu-id="8f393-123">Crea lógica en la consulta.</span><span class="sxs-lookup"><span data-stu-id="8f393-123">Creates logic in the query.</span></span> <span data-ttu-id="8f393-124">Por ejemplo, (expr1 o expr2) y expr3.</span><span class="sxs-lookup"><span data-stu-id="8f393-124">For example, (expr1 or expr2) and expr3.</span></span>  
  
 <span data-ttu-id="8f393-125">**Criterios o argumento**</span><span class="sxs-lookup"><span data-stu-id="8f393-125">**Criteria/Argument**</span></span>  
 <span data-ttu-id="8f393-126">Especifica una condición o expresión de usuario que se aplica a la columna.</span><span class="sxs-lookup"><span data-stu-id="8f393-126">Specifies a condition or user expression that applies to the column.</span></span> <span data-ttu-id="8f393-127">Puede arrastrar columnas desde las tablas a la celda.</span><span class="sxs-lookup"><span data-stu-id="8f393-127">You can drag columns from the tables to the cell.</span></span>  
  
 <span data-ttu-id="8f393-128">El modo**Consulta** proporciona un editor de texto que le da acceso directo al lenguaje de extensiones de minería de datos (DMX), junto con una vista de los datos de entrada y las columnas del modelo.</span><span class="sxs-lookup"><span data-stu-id="8f393-128">**Query** mode provides a text editor that gives you direct access to the Data Mining Extensions (DMX) language, along with a view of the input data and model columns.</span></span> <span data-ttu-id="8f393-129">Cuando selecciona el modo **Consulta** , la cuadrícula que ha usado para definir la consulta se reemplaza por un editor de texto básico.</span><span class="sxs-lookup"><span data-stu-id="8f393-129">When you select **Query** mode, the grid that you used to define the query is replaced by a basic text editor.</span></span> <span data-ttu-id="8f393-130">Puede utilizar este editor para copiar y guardar las consultas que haya creado o para pegar las consultas DMX existentes y desde el Portapapeles y ejecutarlas después.</span><span class="sxs-lookup"><span data-stu-id="8f393-130">You can use this editor to copy and save queries you have composed, or to paste in existing DMX queries and from the Clipboard and run them.</span></span>  
  
 <span data-ttu-id="8f393-131">La vista**Resultado** ejecuta la consulta actual y muestra los resultados en una cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="8f393-131">**Result** view runs the current query and displays the results in a grid.</span></span> <span data-ttu-id="8f393-132">Si los datos subyacentes han cambiado y desea volver a ejecutar la consulta, haga clic en el botón Reproducir en la barra de estado.</span><span class="sxs-lookup"><span data-stu-id="8f393-132">If the underlying data has changed and you want to rerun the query, click the Play button in the status bar</span></span>  
  
 <span data-ttu-id="8f393-133">Puede diseñar una consulta de minería de datos mediante una combinación de las herramientas visuales y el editor de texto.</span><span class="sxs-lookup"><span data-stu-id="8f393-133">You can design a data mining query by using a combination of the visual tools and the text editor.</span></span> <span data-ttu-id="8f393-134">Si escribe los cambios de la consulta en el editor de texto y vuelve a la vista **Diseño** , todos los cambios se perderán y la consulta revierte a la original que se creó en el Generador de consultas de predicción. Este tema le dirige en el uso del generador de consultas gráfico.</span><span class="sxs-lookup"><span data-stu-id="8f393-134">If you type changes to the query in the text editor and switch back to the **Design** view, all the changes are lost, and the query reverts to the original query created by Prediction Query Builder This topic walks you through use of the graphical query builder.</span></span>  
  
### <a name="to-create-a-prediction-query"></a><span data-ttu-id="8f393-135">Para crear una consulta de predicción</span><span class="sxs-lookup"><span data-stu-id="8f393-135">To create a prediction query</span></span>  
  
1.  <span data-ttu-id="8f393-136">Haga clic en la pestaña **Predicción de modelo de minería de datos** del Diseñador de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="8f393-136">Click the **Mining Model Prediction** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="8f393-137">Haga clic en **Seleccionar modelo** en la tabla **Modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="8f393-137">Click **Select Model** on the **Mining Model** table.</span></span>  
  
     <span data-ttu-id="8f393-138">Se abre el cuadro de diálogo **Seleccionar modelo de minería de datos** , donde se muestran todas las estructuras de minería de datos que existen en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="8f393-138">The **Select Mining Model** dialog box opens to show all the mining structures that exist in the current project.</span></span>  
  
3.  <span data-ttu-id="8f393-139">Seleccione el modelo en el que desee crear una predicción y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8f393-139">Select the model on which you want to create a prediction, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="8f393-140">En la tabla **Seleccionar tabla(s) de entrada** , haga clic en **Seleccionar tabla de casos**.</span><span class="sxs-lookup"><span data-stu-id="8f393-140">On the **Select Input Table(s)** table, click **Select Case Table**.</span></span>  
  
     <span data-ttu-id="8f393-141">Se abrirá el cuadro de diálogo **Seleccionar tabla** .</span><span class="sxs-lookup"><span data-stu-id="8f393-141">The **Select Table** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="8f393-142">En la lista **Origen de datos** , seleccione el origen de datos que contenga los datos sobre los que se va a crear la predicción.</span><span class="sxs-lookup"><span data-stu-id="8f393-142">In the **Data Source** list, select the data source that contains the data on which to create a prediction.</span></span>  
  
6.  <span data-ttu-id="8f393-143">En el cuadro **Nombre de tabla o vista** , seleccione la tabla que contenga los datos sobre los que se vaya a crear una predicción y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8f393-143">In the **Table/View Name** box, select the table that contains the data on which to create a prediction, and then click **OK**.</span></span>  
  
     <span data-ttu-id="8f393-144">Después de seleccionar la tabla de entrada, el Generador de consultas de predicción crea una asignación predeterminada entre el modelo de minería de datos y la tabla de entrada, en función de los nombres de las columnas.</span><span class="sxs-lookup"><span data-stu-id="8f393-144">After you select the input table, Prediction Query Builder creates a default mapping between the mining model and the input table, based on the names of the columns.</span></span> <span data-ttu-id="8f393-145">Para eliminar una asignación, seleccione la línea que vincula la columna de la tabla **Modelo de minería de datos** con la columna asignada de la tabla **Seleccionar tabla(s) de entrada** y presione ELIMINAR.</span><span class="sxs-lookup"><span data-stu-id="8f393-145">To delete a mapping, click to select the line that links the column in the **Mining Model** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span> <span data-ttu-id="8f393-146">También puede crear asignaciones manualmente haciendo clic en una columna de la tabla **Seleccionar tabla(s) de entrada** y arrastrándola hasta la columna correspondiente de la tabla **Modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="8f393-146">You can also manually create mappings by clicking a column in the **Select Input Table(s)** table and dragging it onto the corresponding column in the **Mining Model** table.</span></span>  
  
7.  <span data-ttu-id="8f393-147">Agregue cualquier combinación de los tres tipos siguientes de información a la cuadrícula del Generador de consultas de predicción:</span><span class="sxs-lookup"><span data-stu-id="8f393-147">Add any combination of the following three types of information to the Prediction Query Builder grid:</span></span>  
  
    -   <span data-ttu-id="8f393-148">Columnas de predicción del cuadro **Modelo de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="8f393-148">Predictable columns from the **Mining Model** box.</span></span>  
  
    -   <span data-ttu-id="8f393-149">Cualquier combinación de columnas de entrada del cuadro **Seleccionar tabla(s) de entrada** .</span><span class="sxs-lookup"><span data-stu-id="8f393-149">Any combination of input columns from the **Select Input Table(s)** box.</span></span>  
  
    -   <span data-ttu-id="8f393-150">Funciones de predicción</span><span class="sxs-lookup"><span data-stu-id="8f393-150">Prediction functions</span></span>  
  
8.  <span data-ttu-id="8f393-151">Ejecute la consulta haciendo clic en el primer botón de la barra de herramientas de la pestaña **Predicción de modelo de minería de datos** y seleccione **Resultado**.</span><span class="sxs-lookup"><span data-stu-id="8f393-151">Run the query by clicking the first button on the toolbar of the **Mining Model Prediction** tab, and then selecting **Result**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f393-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8f393-152">See Also</span></span>  
 <span data-ttu-id="8f393-153">[Crear una consulta Singleton en el diseñador de minería de datos](create-a-singleton-query-in-the-data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="8f393-153">[Create a Singleton Query in the Data Mining Designer](create-a-singleton-query-in-the-data-mining-designer.md) </span></span>  
 [<span data-ttu-id="8f393-154">Consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="8f393-154">Data Mining Queries</span></span>](data-mining-queries.md)  
  
  
