---
title: Pestaña selección de entrada (vista gráfico de precisión de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.columnmapping.f1
ms.assetid: f8b1193c-5c86-4c7e-8e35-158d293184fa
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c5e99e5be275dff6e218d172316c612b5ba0c41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673399"
---
# <a name="input-selection-tab-mining-accuracy-chart-view"></a><span data-ttu-id="ae9ea-102">Pestaña Selección de entrada (vista Gráfico de precisión de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="ae9ea-102">Input Selection Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="ae9ea-103">Utilice la pestaña **Selección de entrada** del diseñador **Gráfico de precisión de minería de datos** para especificar el origen de datos que se utiliza para probar el modelo y generar el gráfico de precisión.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-103">Use the **Input Selection** tab of the **Mining Accuracy Chart** designer to specify the source of the data that is used to test the model and build the accuracy chart.</span></span>  
  
 <span data-ttu-id="ae9ea-104">**Para más información:** [Prueba y validación &#40;minería de datos&#41;](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="ae9ea-104">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae9ea-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="ae9ea-105">Options</span></span>  
 <span data-ttu-id="ae9ea-106">\*\*Sincronizar columnas y valores de \*\*  **predicción**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-106">**Synchronize Prediction**  **Columns and Values**</span></span>  
 <span data-ttu-id="ae9ea-107">Seleccione esta opción para coordinar los atributos de predicción de la cuadrícula a fin de que se deriven de la misma columna de estructura de minería de datos de predicción, incluso aunque tengan un nombre diferente, durante el entrenamiento del modelo.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-107">Select to coordinate the predictable attributes in the grid so that, even if they have a different name, they are derived from the same predictable mining structure column during model training.</span></span>  
  
 <span data-ttu-id="ae9ea-108">**Nota** : esta opción no está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-108">**Note** This option is selected by default.</span></span> <span data-ttu-id="ae9ea-109">Solamente debería activar esta casilla en los casos en los que sepa que dos columnas de estructura de minería de datos se derivan del mismo origen multidimensional o relacional subyacente, y en los que las columnas contengan los mismos estados o se hayan discretizado del mismo modo.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-109">You should only clear this box for cases in which you know that two mining structure columns derive from the same underlying relational or multi-dimensional source, and that the columns contain the same states or have been discretized in the same way.</span></span>  
  
 <span data-ttu-id="ae9ea-110">**Seleccione las columnas del modelo de minería de datos de predicción que se mostrarán en el gráfico de elevación**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-110">**Select predictable mining model columns to show in the lift chart**</span></span>  
 <span data-ttu-id="ae9ea-111">Cuadrícula que contiene columnas para controlar qué modelos se incluyen en el gráfico de elevación y cómo se utilizan en éste.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-111">A grid that contains columns to control which models are included in the lift chart and how they are used in the lift chart.</span></span>  
  
|<span data-ttu-id="ae9ea-112">Value</span><span class="sxs-lookup"><span data-stu-id="ae9ea-112">Value</span></span>|<span data-ttu-id="ae9ea-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae9ea-113">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae9ea-114">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-114">**Show**</span></span>|<span data-ttu-id="ae9ea-115">Active la casilla situada junto al nombre de cada columna de predicción del modelo de minería que desee mostrar en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-115">Select the box next to the name of each predictable column in the mining model that you want to display in the chart.</span></span><br /><br /> <span data-ttu-id="ae9ea-116">Si el gráfico es demasiado complejo para verlo con facilidad, borre el cuadro situado al lado de una o varias columnas para simplificar el gráfico.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-116">If the chart is too complex to view easily, clear the box next to one or more columns to simplify the chart.</span></span><br /><br /> <span data-ttu-id="ae9ea-117">Nota: No se pueden crear gráficos de precisión hasta que haya al menos una columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-117">Note: You cannot create an accuracy chart unless at least one column is selected.</span></span>|  
|<span data-ttu-id="ae9ea-118">**Modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-118">**Mining Model**</span></span>|<span data-ttu-id="ae9ea-119">Muestra los modelos de minería contenidos en la estructura de minería.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-119">Lists the mining models that are contained in the mining structure.</span></span>|  
|<span data-ttu-id="ae9ea-120">**Nombre de columna de predicción**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-120">**Predictable Column Name**</span></span>|<span data-ttu-id="ae9ea-121">Seleccione una columna de predicción que esté contenida dentro de los modelos de minería de datos que se utilizarán para crear el gráfico de elevación.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-121">Select a predictable column that is contained in the mining models that are used to create the lift chart.</span></span>|  
|<span data-ttu-id="ae9ea-122">**Valor de predicción**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-122">**Predict Value**</span></span>|<span data-ttu-id="ae9ea-123">Seleccione un valor para la columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-123">Select a value for the predictable column.</span></span> <span data-ttu-id="ae9ea-124">Si deja esta opción en blanco, el gráfico de elevación predice en qué medida será satisfactoria la realización del modelo para todos los estados de la columna de predicción.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-124">If you leave this blank, the lift chart predicts how well the model performs for all states of the predictable column.</span></span>|  
  
 <span data-ttu-id="ae9ea-125">**Seleccionar un conjunto de datos para usarlo en un gráfico de precisión**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-125">**Select data set to be used for Accuracy Chart**</span></span>  
 <span data-ttu-id="ae9ea-126">Grupo de opciones que contiene tres opciones para especificar los datos de las pruebas de precisión.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-126">An option group that contains three options for specifying accuracy test data.</span></span>  
  
|<span data-ttu-id="ae9ea-127">Value</span><span class="sxs-lookup"><span data-stu-id="ae9ea-127">Value</span></span>|<span data-ttu-id="ae9ea-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae9ea-128">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae9ea-129">**Usar casos de prueba de modelo de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-129">**Use mining model test cases**</span></span>|<span data-ttu-id="ae9ea-130">Utilice el conjunto de pruebas que se creó cuando dividió la estructura de minería de datos, y aplique el filtro que se define en el modelo.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-130">Use the testing set that was created when you partitioned the mining structure, and apply the filter that is defined on the model.</span></span> <span data-ttu-id="ae9ea-131">Para más información sobre filtros de modelos, vea [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](data-mining/mining-models-analysis-services-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="ae9ea-131">For information about model filters, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](data-mining/mining-models-analysis-services-data-mining.md)</span></span>|  
|<span data-ttu-id="ae9ea-132">**Usar casos de prueba de estructura de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-132">**Use mining structure test cases**</span></span>|<span data-ttu-id="ae9ea-133">Utilice el conjunto de pruebas que se creó cuando dividió la estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-133">Use the testing set that was created when you partitioned the mining structure.</span></span>|  
|<span data-ttu-id="ae9ea-134">**Especificar otro conjunto de datos**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-134">**Specify a different data set**</span></span>|<span data-ttu-id="ae9ea-135">Especifique una tabla de una vista del origen de datos existente para utilizar como conjunto de datos de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-135">Specify a table from an existing data source view to use as a test data set.</span></span>|  
  
## <a name="filtering-options"></a><span data-ttu-id="ae9ea-136">Opciones de filtrado</span><span class="sxs-lookup"><span data-stu-id="ae9ea-136">Filtering Options</span></span>  
 <span data-ttu-id="ae9ea-137">Si selecciona la opción **Especificar otro conjunto de datos**, puede definir una vista del origen de datos y crear filtros para aplicarlos a esos datos.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-137">If you select the option **Specify a different data set**, you can define a data source view and create filters to apply to that data.</span></span> <span data-ttu-id="ae9ea-138">Al crear un filtro, está creando una cláusula WHERE en la consulta que devuelve los datos de pruebas de la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-138">When you create a filter, you are creating a WHERE clause in the query that returns the test data from the data source view.</span></span>  
  
 <span data-ttu-id="ae9ea-139">**Nota:** No se puede especificar un filtro en el modelo de minería de datos mediante la pestaña **selección de entrada** . Para crear un filtro de modelo, haga clic en la pestaña **modelos de minería de datos** y edite las propiedades del modelo.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-139">**Note** You cannot specify a filter on the mining model by using the **Input Selection** tab. To create a model filter, click the **Mining Models** tab and edit the model properties.</span></span>  
  
 <span data-ttu-id="ae9ea-140">Si no creó un conjunto de exclusiones para las pruebas cuando creó la estructura de minería de datos, puede seleccionar esta opción y, a continuación, especificar la vista del origen de datos original como conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-140">If you did not create a holdout set for testing when you created the mining structure, you can select this option and then specify the original data source view as a test set.</span></span> <span data-ttu-id="ae9ea-141">Con esta solución alternativa, puede establecer también filtros en el conjunto de datos original.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-141">By using  this workaround, you can also set filters on the original data set.</span></span>  
  
 <span data-ttu-id="ae9ea-142">**Especificar asignación de columnas.**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-142">**Specify Column Mapping**</span></span>  
 <span data-ttu-id="ae9ea-143">Abre el cuadro de diálogo **Especificar asignación de columnas**, en el que se selecciona el origen de datos, se especifican el caso y las tablas anidadas y se asignan columnas de datos externas a las columnas de estructura de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-143">Opens the **Specify Column Mapping** dialog box, where you select the data source, specify case and nested tables, and map external data columns to the mining structure columns.</span></span>  
  
 <span data-ttu-id="ae9ea-144">Para más información, vea [Cuadro de diálogo Especificar asignación de columna &#40;gráfico de precisión de minería de datos&#41;](specify-column-mapping-dialog-box-mining-accuracy-chart.md).</span><span class="sxs-lookup"><span data-stu-id="ae9ea-144">For more information, see [Specify Column Mapping Dialog Box &#40;Mining Accuracy Chart&#41;](specify-column-mapping-dialog-box-mining-accuracy-chart.md).</span></span>  
  
 <span data-ttu-id="ae9ea-145">**Expresión de filtro**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-145">**Filter Expression**</span></span>  
 <span data-ttu-id="ae9ea-146">Muestra la condición de filtro que se generó con los editores de filtro.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-146">Displays the filter condition that you built by using the filter editors.</span></span>  
  
 <span data-ttu-id="ae9ea-147">**Abrir editor de filtros**</span><span class="sxs-lookup"><span data-stu-id="ae9ea-147">**Open Filter Editor**</span></span>  
 <span data-ttu-id="ae9ea-148">Abre el cuadro de diálogo **Filtro de conjunto de datos** , que le permite seleccionar las tablas externas y establecer condiciones en las columnas de la tabla de casos, y el cuadro de diálogo **Filtro** , que le ayuda a generar las condiciones que se aplican a las columnas individuales de la tabla seleccionada, o a las columnas de las tablas anidadas.</span><span class="sxs-lookup"><span data-stu-id="ae9ea-148">Opens the **Data Set Filter** dialog box, which lets you select external tables, and set conditions on case table columns, and the **Filter** dialog box, which helps you build conditions that apply to individual columns in the selected table, or to columns in nested tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae9ea-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae9ea-149">See Also</span></span>  
 <span data-ttu-id="ae9ea-150">[Tareas y procedimientos de prueba y validación &#40;&#41;de minería de datos](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ae9ea-150">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 <span data-ttu-id="ae9ea-151">[Diseñador de gráficos de precisión de minería de datos &#40;&#41;de minería de datos](mining-accuracy-chart-designer-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ae9ea-151">[Mining Accuracy Chart Designer &#40;Data Mining&#41;](mining-accuracy-chart-designer-data-mining.md) </span></span>  
 <span data-ttu-id="ae9ea-152">[Aplicar un filtro a un modelo de minería de datos](data-mining/apply-a-filter-to-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="ae9ea-152">[Apply a Filter to a Mining Model](data-mining/apply-a-filter-to-a-mining-model.md) </span></span>  
 [<span data-ttu-id="ae9ea-153">Filtros para modelos de minería &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="ae9ea-153">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](data-mining/mining-models-analysis-services-data-mining.md)  
  
  