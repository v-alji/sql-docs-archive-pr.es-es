---
title: Cuadro de diálogo filtro de conjunto de datos o filtro de modelo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a9602174-b7e2-4e16-8ded-dfd8eb9264d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: afa796cd8cb23894c059deba411b3e1d6676e3b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746617"
---
# <a name="data-set-filter-or-model-filter-dialog-box"></a><span data-ttu-id="0e725-102">Cuadro de diálogo Filtro de conjunto de datos o Filtro de modelo</span><span class="sxs-lookup"><span data-stu-id="0e725-102">Data Set Filter or Model Filter Dialog Box</span></span>
  <span data-ttu-id="0e725-103">Este cuadro de diálogo le ayuda a generar los filtros que puede aplicar a un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="0e725-103">This dialog box helps you build the filters that you can apply to a data set.</span></span>  <span data-ttu-id="0e725-104">El conjunto de datos puede ser un conjunto de datos externo que se use para las pruebas, o los datos del caso para un modelo de minería.</span><span class="sxs-lookup"><span data-stu-id="0e725-104">The data set can be an external data set used for testing, or the case data for a mining model.</span></span> <span data-ttu-id="0e725-105">El nombre del cuadro de diálogo cambia en función de si el filtro está destinado a un conjunto de datos externo o a un modelo de minería.</span><span class="sxs-lookup"><span data-stu-id="0e725-105">The name of the dialog box changes depending on whether the filter is for an external data set or for a mining model.</span></span>  
  
 <span data-ttu-id="0e725-106">Si aplica el filtro a un conjunto de datos nuevo, el modelo de minería de datos se evalúa utilizando solamente esos casos en el conjunto de datos que cumpla las condiciones.</span><span class="sxs-lookup"><span data-stu-id="0e725-106">If you apply the filter to a new data set, the data mining model is evaluated by using only those cases in the data set that meet the conditions.</span></span> <span data-ttu-id="0e725-107">Si aplica el filtro al propio modelo de minería, el modelo se entrenará y se probará utilizando solamente los casos del conjunto de datos de pruebas existente que cumpla los criterios del filtro.</span><span class="sxs-lookup"><span data-stu-id="0e725-107">If you apply the filter to the mining model itself, the model will be trained and tested by using only the cases in the existing test data set that meet the filter criteria.</span></span>  
  
-   <span data-ttu-id="0e725-108">El cuadro de diálogo **Filtro de conjunto de datos** está disponible en la pestaña **Selección de entrada** del diseñador **Gráfico de precisión de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="0e725-108">The **Data Set Filter** dialog box is available from the **Input Selection** tab of the **Mining Accuracy Chart** designer.</span></span>  
  
-   <span data-ttu-id="0e725-109">El cuadro de diálogo **Filtro de modelos** está disponible en la pestaña **Modelos de minería de datos** del diseñador Minería de datos.</span><span class="sxs-lookup"><span data-stu-id="0e725-109">The **Model Filter** dialog box is available from the **Mining Models** tab of the Data Miningdesigner.</span></span>  
  
-   <span data-ttu-id="0e725-110">La cuadrícula **Condiciones** contiene las columnas en las que puede especificar un nombre de columna o de tabla, un operador y los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="0e725-110">The **Conditions** grid contains columns where you can specify a table or column name, an operator, and target values.</span></span> <span data-ttu-id="0e725-111">Mediante esta cuadrícula, básicamente está creando una cláusula WHERE.</span><span class="sxs-lookup"><span data-stu-id="0e725-111">By using this grid you are essentially creating a WHERE clause.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="0e725-112"> Para probar la exactitud en un subconjunto de los datos de entrenamiento originales, puede agregar la vista del origen de datos que se usó para definir el conjunto de entrenamiento como datos de prueba externos y, a continuación, agregar las condiciones en la cuadrícula **Filtro de conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="0e725-112">To test accuracy on a subset of the original training data, you can add the data source view that was used to define the training set as the external testing data, and then add conditions in the **Data Set Filter** grid.</span></span>  
  
 <span data-ttu-id="0e725-113">**Para más información:** [Prueba y validación &#40;minería de datos&#41;](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="0e725-113">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="0e725-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="0e725-114">Options</span></span>  
 <span data-ttu-id="0e725-115">**Condiciones**</span><span class="sxs-lookup"><span data-stu-id="0e725-115">**Conditions**</span></span>  
 <span data-ttu-id="0e725-116">Muestra los nombres de tabla, seguidos de los nombres de columna y las condiciones.</span><span class="sxs-lookup"><span data-stu-id="0e725-116">Displays table names, followed by column names with conditions.</span></span>  
  
|<span data-ttu-id="0e725-117">Value</span><span class="sxs-lookup"><span data-stu-id="0e725-117">Value</span></span>|<span data-ttu-id="0e725-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e725-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0e725-119">**Y/o**</span><span class="sxs-lookup"><span data-stu-id="0e725-119">**And/Or**</span></span>|<span data-ttu-id="0e725-120">Elija un operador para unir varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="0e725-120">Choose an operator to join multiple conditions.</span></span>|  
|<span data-ttu-id="0e725-121">**Columna de la estructura de minería de datos**</span><span class="sxs-lookup"><span data-stu-id="0e725-121">**Mining Structure Column**</span></span>|<span data-ttu-id="0e725-122">Haga clic para seleccionar un origen de datos y, a continuación, haga clic en las líneas sucesivas en la cuadrícula para agregar las columnas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0e725-122">Click to select a data source, and then click successive lines in the grid to add columns from the data source.</span></span><br /><br /> <span data-ttu-id="0e725-123">La primera línea de la cuadrícula especifica la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0e725-123">The first line in the grid specifies the data source view.</span></span> <span data-ttu-id="0e725-124">Después de seleccionar una vista del origen de datos, **Columna de la estructura de minería de datos** muestra un icono de tabla y el campo **Valor** muestra la combinación de todos los criterios que ha definido para este origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0e725-124">After you select a data source view, **Mining Structure Column** displays a table icon, and the **Value** field displays the combination of all criteria that you have defined for this data source.</span></span><br /><br /> <span data-ttu-id="0e725-125">Después de haber seleccionado un origen de datos, el cuadro **Columna de la estructura de minería de datos** proporciona una lista desplegable de columnas individuales del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0e725-125">After you have selected a data source, the **Mining Structure Column** box provides a dropdown list of individual columns in the data source.</span></span>|  
|<span data-ttu-id="0e725-126">**Operador**</span><span class="sxs-lookup"><span data-stu-id="0e725-126">**Operator**</span></span>|<span data-ttu-id="0e725-127">Seleccione un operador de la lista.</span><span class="sxs-lookup"><span data-stu-id="0e725-127">Select an operator from the list.</span></span>|  
|<span data-ttu-id="0e725-128">**Valor**</span><span class="sxs-lookup"><span data-stu-id="0e725-128">**Value**</span></span>|<span data-ttu-id="0e725-129">Para las tablas, el campo **Valor** muestra la combinación de todos los filtros que se aplican al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="0e725-129">For tables, the **Value** field shows the combination of all filters applied to the data source.</span></span> <span data-ttu-id="0e725-130">También puede hacer clic en el botón compilar **(...)** que se encuentra a la derecha del cuadro de texto para abrir el cuadro de diálogo **filtro** y generar una condición.</span><span class="sxs-lookup"><span data-stu-id="0e725-130">You can also click the build **(...)** button at the right of the text box to open the **Filter** dialog box and build a condition.</span></span>|  
  
 <span data-ttu-id="0e725-131">**Expression**</span><span class="sxs-lookup"><span data-stu-id="0e725-131">**Expression**</span></span>  
 <span data-ttu-id="0e725-132">Muestra el conjunto de criterios que generó con la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0e725-132">Displays the set of criteria that you built by using the grid.</span></span>  
  
 <span data-ttu-id="0e725-133">**Editar consulta**</span><span class="sxs-lookup"><span data-stu-id="0e725-133">**Edit Query**</span></span>  
 <span data-ttu-id="0e725-134">Cambia el modo de edición de filtro para que pueda escribir directamente una expresión de filtro en el cuadro de texto **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="0e725-134">Changes the filter editing mode so that you can type a filter expression directly in the **Expression** text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e725-135">Una vez realizados los cambios manuales en la expresión de filtro, no puede volver al modo de edición de cuadrícula, incluso después de haber guardado la expresión en el cuadro **expresión de filtro** en la pestaña **selección de entrada** . Si desea crear una expresión con la cuadrícula, debe eliminar la expresión de filtro existente y empezar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0e725-135">After you have made manual changes to the filter expression, you cannot return to grid edit mode, even after you have saved the expression in the **Filter Expression** box on the **Input Selection** tab. If you want to build an expression by using the grid, you must delete the existing filter expression and start over.</span></span>  
  
 <span data-ttu-id="0e725-136">**Revertir modificaciones de consulta**</span><span class="sxs-lookup"><span data-stu-id="0e725-136">**Revert Query Edits**</span></span>  
 <span data-ttu-id="0e725-137">Restaura la cuadrícula a su estado anterior y cancela cualquier cambio que realizara en la expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="0e725-137">Restores the grid to its previous state and cancels any changes that you made to the filter expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e725-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e725-138">See Also</span></span>  
 <span data-ttu-id="0e725-139">[Tareas y procedimientos de prueba y validación &#40;&#41;de minería de datos](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="0e725-139">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="0e725-140">Diseñador de gráficos de precisión de minería de datos &#40;&#41;de minería de datos</span><span class="sxs-lookup"><span data-stu-id="0e725-140">Mining Accuracy Chart Designer &#40;Data Mining&#41;</span></span>](mining-accuracy-chart-designer-data-mining.md)  
  
  
