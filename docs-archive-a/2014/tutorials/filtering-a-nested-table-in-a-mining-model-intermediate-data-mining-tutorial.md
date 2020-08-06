---
title: Filtrar una tabla anidada en un modelo de minería de datos (tutorial intermedio de minería de datos) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 0a3ae0e5-897b-4898-a60d-5455eec3d305
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1e6ce2936a3c6763ea41999b2724c0fe8c79301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749001"
---
# <a name="filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="57d30-102">Filtrar un tabla anidada en un modelo de minería de datos (tutorial intermedio de minería de datos)</span><span class="sxs-lookup"><span data-stu-id="57d30-102">Filtering a Nested Table in a Mining Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="57d30-103">Una vez creado y explorado el modelo, tal vez decida centrarse en un subconjunto de datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="57d30-103">After you have created and explored the model, you decide that you want to focus on a subset of the customer data.</span></span> <span data-ttu-id="57d30-104">Por ejemplo, es posible que solo desee analizar las cestas que contienen un producto específico o los datos demográficos de los clientes que no han realizado ninguna compra en un determinado período.</span><span class="sxs-lookup"><span data-stu-id="57d30-104">For example, you might want to analyze only the baskets that contain a specific item, or to analyze the demographics of customers who have not purchased anything in a certain period.</span></span>  
  
 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="57d30-105">proporciona la capacidad de filtrar los datos que se emplean en un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="57d30-105">provides the ability to filter the data that is used in a mining model.</span></span> <span data-ttu-id="57d30-106">Esta característica es útil porque no es necesario configurar una nueva vista del origen de datos para utilizar datos diferentes.</span><span class="sxs-lookup"><span data-stu-id="57d30-106">This feature is useful because you do not need to set up a new data source view to use different data.</span></span> <span data-ttu-id="57d30-107">En el Tutorial básico de minería de datos aprendió a filtrar datos de una tabla plana aplicando condiciones a la tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="57d30-107">In the Basic Data Mining Tutorial, you learned how to filter data from a flat table by applying conditions to the case table.</span></span> <span data-ttu-id="57d30-108">En esta tarea, creará un filtro que se aplica a una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="57d30-108">In this task, you create a filter that applies to a nested table.</span></span>  
  
## <a name="filters-on-nested-vs-case-tables"></a><span data-ttu-id="57d30-109">Comparación de los filtros en tablas anidadas y en tablas de casos</span><span class="sxs-lookup"><span data-stu-id="57d30-109">Filters on Nested vs. Case Tables</span></span>  
 <span data-ttu-id="57d30-110">Si la vista del origen de datos contiene una tabla de casos y una tabla anidada, como la vista del origen de datos utilizada en el modelo de asociación, puede filtrar valores de la tabla de casos, comprobar la presencia o ausencia de un valor en la tabla anidada o alguna combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="57d30-110">If your data source view contains a case table and a nested table, like the data source view used in the Association model, you can filter on values from the case table, the presence or absence of a value in the nested table, or some combination of both.</span></span>  
  
 <span data-ttu-id="57d30-111">En esta tarea, primero realizará una copia del modelo de asociación y, a continuación, agregará los atributos IncomeGroup y Region al nuevo modelo relacionado, para que pueda crear un filtro a partir de esos atributos en la tabla de casos.</span><span class="sxs-lookup"><span data-stu-id="57d30-111">In this task, you will first make a copy of the Association model and then add the IncomeGroup and Region attributes to the new related model, so that you can filter on those attributes in the case table.</span></span>  
  
#### <a name="to-create-and-modify-a-copy-of-the-association-model"></a><span data-ttu-id="57d30-112">Para crear y modificar una copia del modelo Association</span><span class="sxs-lookup"><span data-stu-id="57d30-112">To create and modify a copy of the Association model</span></span>  
  
1.  <span data-ttu-id="57d30-113">En la pestaña **modelos de minería de datos** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , haga clic con el botón secundario en el `Association` modelo y seleccione **nuevo modelo de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="57d30-113">In the **Mining Models** tab of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click the `Association` model, and select **New Mining Model**.</span></span>  
  
2.  <span data-ttu-id="57d30-114">En **nombre del modelo**, escriba `Association Filtered` .</span><span class="sxs-lookup"><span data-stu-id="57d30-114">For **Model Name**, type `Association Filtered`.</span></span> <span data-ttu-id="57d30-115">En **nombre del algoritmo**, seleccione **reglas de Asociación de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="57d30-115">For **Algorithm Name**, select **Microsoft Association Rules**.</span></span> <span data-ttu-id="57d30-116">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="57d30-116">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="57d30-117">En la columna del modelo de asociación filtrado, haga clic en la fila IncomeGroup y cambie el valor de **omitir** a **entrada**.</span><span class="sxs-lookup"><span data-stu-id="57d30-117">In the column for the Association Filtered model, click the IncomeGroup row and change the value from **Ignore** to **Input**.</span></span>  
  
 <span data-ttu-id="57d30-118">A continuación, creará un filtro para la tabla de casos en el nuevo modelo de asociación.</span><span class="sxs-lookup"><span data-stu-id="57d30-118">Next, you will create a filter on the case table in the new association model.</span></span> <span data-ttu-id="57d30-119">El filtro pasará al modelo solo los clientes de la región de destino o con el nivel de ingresos de destino.</span><span class="sxs-lookup"><span data-stu-id="57d30-119">The filter will pass to the model only the customers in the target region or with the target income level.</span></span> <span data-ttu-id="57d30-120">A continuación, agregará un segundo conjunto de condiciones de filtro para especificar que el modelo utilice solo los clientes cuyas cestas de la compra contengan al menos un producto.</span><span class="sxs-lookup"><span data-stu-id="57d30-120">Then, you will add a second set of filter conditions to specify that the model uses only customers whose shopping baskets contained at least one item.</span></span>  
  
#### <a name="to-add-a-filter-to-a-mining-model"></a><span data-ttu-id="57d30-121">Para agregar un filtro a un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="57d30-121">To add a filter to a mining model</span></span>  
  
1.  <span data-ttu-id="57d30-122">En la pestaña **modelos de minería de datos** , haga clic con el botón secundario en la Asociación de modelo filtrada y seleccione **establecer filtro de modelos**.</span><span class="sxs-lookup"><span data-stu-id="57d30-122">In the **Mining Models** tab, right-click the model Association Filtered, and select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="57d30-123">En el cuadro de diálogo **Filtro del modelo** , haga clic en la fila superior de la cuadrícula en el cuadro de texto **Columna de la estructura de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="57d30-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
3.  <span data-ttu-id="57d30-124">En el cuadro de texto columna de la **estructura de minería de datos** , seleccione IncomeGroup.</span><span class="sxs-lookup"><span data-stu-id="57d30-124">In the **Mining Structure Column** text box, select IncomeGroup.</span></span>  
  
     <span data-ttu-id="57d30-125">El icono situado en la parte izquierda del cuadro de texto cambia para indicar que el elemento seleccionado es una columna.</span><span class="sxs-lookup"><span data-stu-id="57d30-125">The icon at the left side of the text box changes to indicate that the selected item is a column.</span></span>  
  
4.  <span data-ttu-id="57d30-126">Haga clic en el cuadro de texto **operador** y seleccione el **=** operador de la lista.</span><span class="sxs-lookup"><span data-stu-id="57d30-126">Click the **Operator** text box and select the **=** operator from the list.</span></span>  
  
5.  <span data-ttu-id="57d30-127">Haga clic en el cuadro de texto **valor** y escriba `High` en el cuadro.</span><span class="sxs-lookup"><span data-stu-id="57d30-127">Click the **Value** text box, and type `High` in the box.</span></span>  
  
6.  <span data-ttu-id="57d30-128">Haga clic en la siguiente fila de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="57d30-128">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="57d30-129">Haga clic en el cuadro de texto **y/o** de la siguiente fila de la cuadrícula y seleccione **o**.</span><span class="sxs-lookup"><span data-stu-id="57d30-129">Click the **AND/OR** text box in the next row of the grid and select **OR**.</span></span>  
  
8.  <span data-ttu-id="57d30-130">En el cuadro de texto columna de la **estructura de minería de datos** , seleccione IncomeGroup.</span><span class="sxs-lookup"><span data-stu-id="57d30-130">In the **Mining Structure Column** text box, select IncomeGroup.</span></span> <span data-ttu-id="57d30-131">En el cuadro de texto **valor** , escriba `Moderate` .</span><span class="sxs-lookup"><span data-stu-id="57d30-131">In the **Value** text box, type `Moderate`.</span></span>  
  
     <span data-ttu-id="57d30-132">La condición de filtro que ha creado se agrega automáticamente al cuadro de texto **expresión** y debe aparecer de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="57d30-132">The filter condition that you created is automatically added to the **Expression** text box, and should appears as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate'`  
  
9. <span data-ttu-id="57d30-133">Haga clic en la siguiente fila de la cuadrícula, manteniendo el operador como predeterminado, **y**.</span><span class="sxs-lookup"><span data-stu-id="57d30-133">Click the next row in the grid, leaving the operator as the default, **AND**.</span></span>  
  
10. <span data-ttu-id="57d30-134">Para **operador**, deje el valor predeterminado, **Contains**.</span><span class="sxs-lookup"><span data-stu-id="57d30-134">For **Operator**, leave the default value, **Contains**.</span></span> <span data-ttu-id="57d30-135">Haga clic en el cuadro de texto **valor** .</span><span class="sxs-lookup"><span data-stu-id="57d30-135">Click the **Value** text box.</span></span>  
  
11. <span data-ttu-id="57d30-136">En el cuadro de diálogo **filtro** , en la primera fila de la **columna estructura de minería de datos**, seleccione `Model` .</span><span class="sxs-lookup"><span data-stu-id="57d30-136">In the **Filter** dialog box, in the first row under **Mining Structure Column**, select `Model`.</span></span>  
  
12. <span data-ttu-id="57d30-137">Para **operador**, seleccione **no es null**.</span><span class="sxs-lookup"><span data-stu-id="57d30-137">For **Operator**, select **IS NOT NULL**.</span></span> <span data-ttu-id="57d30-138">Deje en blanco el cuadro de texto **valor** .</span><span class="sxs-lookup"><span data-stu-id="57d30-138">Leave the **Value** text box blank.</span></span> <span data-ttu-id="57d30-139">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="57d30-139">Click **OK**.</span></span>  
  
     <span data-ttu-id="57d30-140">La condición de filtro del cuadro de texto **expresión** del cuadro de diálogo **filtro del modelo** se actualiza automáticamente para incluir la nueva condición en la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="57d30-140">The filter condition in the **Expression** text box of the **Model Filter** dialog box is automatically updated to include the new condition on the nested table.</span></span> <span data-ttu-id="57d30-141">La expresión completa es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="57d30-141">The completed expression is as follows:</span></span>  
  
     `[IncomeGroup] = 'High' OR [IncomeGroup] = 'Moderate' AND EXISTS SELECT * FROM [vAssocSeqLineItems] WHERE [Model] <> NULL).`  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)] ``  
  
#### <a name="to-enable-drillthrough-and-to-process-the-filtered-model"></a><span data-ttu-id="57d30-142">Para habilitar la obtención de detalles y procesar el modelo filtrado</span><span class="sxs-lookup"><span data-stu-id="57d30-142">To enable drillthrough and to process the filtered model</span></span>  
  
1.  <span data-ttu-id="57d30-143">En la pestaña **modelos de minería de datos** , haga clic con el botón secundario en el `Association Filtered` modelo y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="57d30-143">In the **Mining Models** tab, right-click the `Association Filtered` model, and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="57d30-144">Cambie la propiedad **AllowDrillThrough** a **true**.</span><span class="sxs-lookup"><span data-stu-id="57d30-144">Change the **AllowDrillThrough** property to **True**.</span></span>  
  
3.  <span data-ttu-id="57d30-145">Haga clic con el botón secundario en el `Association Filtered` modelo de minería de datos y seleccione **procesar modelo**.</span><span class="sxs-lookup"><span data-stu-id="57d30-145">Right-click the `Association Filtered` mining model, and select **Process Model**.</span></span>  
  
4.  <span data-ttu-id="57d30-146">Haga clic en **sí** en el mensaje de error para implementar el nuevo modelo en la [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="57d30-146">Click **Yes** in the error message to deploy the new model to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
5.  <span data-ttu-id="57d30-147">En el cuadro de diálogo **procesar estructura de minería de datos** , haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="57d30-147">In the **Process Mining Structure** dialog box, click **Run**.</span></span>  
  
6.  <span data-ttu-id="57d30-148">Cuando se haya completado el procesamiento, haga clic en **cerrar** para salir del cuadro de diálogo **progreso del proceso** y haga clic de nuevo en **cerrar** para salir del cuadro de diálogo **procesar estructura de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="57d30-148">When processing is complete click **Close** to exit the **Process Progress** dialog box, and click **Close** again to exit the **Process Mining Structure** dialog box.</span></span>  
  
 <span data-ttu-id="57d30-149">Mediante el Visor de árbol de contenido genérico de Microsoft y examinando el valor de NODE_SUPPORT, puede comprobar que el modelo filtrado contiene menos casos que el modelo original.</span><span class="sxs-lookup"><span data-stu-id="57d30-149">You can verify by using the Microsoft Generic Content Tree viewer and looking at the value for NODE_SUPPORT that the filtered model contains fewer cases than the original model.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57d30-150">Observaciones</span><span class="sxs-lookup"><span data-stu-id="57d30-150">Remarks</span></span>  
 <span data-ttu-id="57d30-151">El filtro de tabla anidada que acaba de crear solo comprueba la presencia de al menos una fila en la tabla anidada; no obstante, puede crear condiciones de filtro que comprueben la existencia de productos específicos.</span><span class="sxs-lookup"><span data-stu-id="57d30-151">The nested table filter that you just created checks only for the presence of at least one row in the nested table; however, you can also create filter conditions that check for the presence of specific products.</span></span>  <span data-ttu-id="57d30-152">Por ejemplo, podría crear el siguiente filtro:</span><span class="sxs-lookup"><span data-stu-id="57d30-152">For example, you could create the following filter:</span></span>  
  
```  
[IncomeGroup] = 'High' AND  
 EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] = 'Water Bottle' )   
```  
  
 <span data-ttu-id="57d30-153">Esta instrucción restringe los clientes de la tabla de casos a solo aquellos que han comprado una botella de agua.</span><span class="sxs-lookup"><span data-stu-id="57d30-153">This statement means that you are restricting the customers from the case table to only those who have purchased a water bottle.</span></span> <span data-ttu-id="57d30-154">Sin embargo, dado que el número de atributos de tabla anidada es potencialmente ilimitado, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] no suministra ninguna lista de valores posibles entre los que seleccionar.</span><span class="sxs-lookup"><span data-stu-id="57d30-154">However, because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="57d30-155">En lugar de ello, debe escribir el valor exacto.</span><span class="sxs-lookup"><span data-stu-id="57d30-155">Instead, you must type the exact value.</span></span>  
  
 <span data-ttu-id="57d30-156">Puede hacer clic en **Editar consulta** para cambiar manualmente la expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="57d30-156">You can click **Edit Query** to manually change the filter expression.</span></span> <span data-ttu-id="57d30-157">Sin embargo, si cambia manualmente una parte de la expresión de filtro, la cuadrícula estará deshabilitada y a partir de este momento deberá trabajar solo con la expresión de filtro en modo de edición de texto.</span><span class="sxs-lookup"><span data-stu-id="57d30-157">However, if you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="57d30-158">Para restaurar el modo de edición de cuadrícula, debe borrar la expresión de filtro y comenzar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="57d30-158">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="57d30-159">No se puede usar el operador LIKE en un filtro de tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="57d30-159">You cannot use the LIKE operator in a nested table filter.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="57d30-160">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="57d30-160">Next Task in Lesson</span></span>  
 [<span data-ttu-id="57d30-161">Predicción de asociaciones &#40;tutorial intermedio de minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="57d30-161">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="57d30-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57d30-162">See Also</span></span>  
 <span data-ttu-id="57d30-163">[Sintaxis y ejemplos del filtro de modelos &#40;Analysis Services:&#41;de minería de datos](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="57d30-163">[Model Filter Syntax and Examples &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/model-filter-syntax-and-examples-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="57d30-164">Filtros para modelos de minería &#40;Analysis Services - Minería de datos&#41;</span><span class="sxs-lookup"><span data-stu-id="57d30-164">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
