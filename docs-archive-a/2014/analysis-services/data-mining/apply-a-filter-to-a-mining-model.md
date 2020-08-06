---
title: Aplicar un filtro a un modelo de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- model filter [data mining]
- filters [data mining]
- filtering input rows [Analysis Services]
- filtering data [Analysis Services]
ms.assetid: 4d0abeb5-e939-46d3-9097-6e0358244300
author: minewiskan
ms.author: owend
ms.openlocfilehash: d9f3147c36e69d9c2249d5bf6d1ba201799c6e27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675055"
---
# <a name="apply-a-filter-to-a-mining-model"></a><span data-ttu-id="1307c-102">Aplicar un filtro a un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="1307c-102">Apply a Filter to a Mining Model</span></span>
  <span data-ttu-id="1307c-103">Si la estructura de minería de datos contiene una tabla anidada, puede aplicar un filtro a la tabla de casos, a la tabla anidada o a ambas.</span><span class="sxs-lookup"><span data-stu-id="1307c-103">If your mining structure contains a nested table, you can apply a filter to the case table, the nested table, or both.</span></span>  
  
 <span data-ttu-id="1307c-104">El siguiente procedimiento muestra cómo crear ambos tipos de filtros: filtros de casos y filtros de filas de tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="1307c-104">The following procedure demonstrates how to create both kinds of filters: case filters, and filters on the nested table rows.</span></span>  
  
 <span data-ttu-id="1307c-105">La condición de la tabla de casos limita los clientes a aquéllos con ingresos entre 30000 y 40000.</span><span class="sxs-lookup"><span data-stu-id="1307c-105">The condition on the case table restricts customers to those with income between 30000 and 40000.</span></span> <span data-ttu-id="1307c-106">La condición de la tabla anidada limita los clientes a aquéllos que no compraron un producto determinado.</span><span class="sxs-lookup"><span data-stu-id="1307c-106">The condition on the nested table restricts the customers to those who did not purchase a particular item.</span></span>  
  
 <span data-ttu-id="1307c-107">La condición de filtro completa creada en este ejemplo es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1307c-107">The complete filter condition created in this example is as follows:</span></span>  
  
```  
[Income] > '30000'   
AND  [Income] < '40000'   
AND EXISTS (SELECT * FROM [<nested table name>]   
WHERE [Model] <> 'Water Bottle' )   
```  
  
### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="1307c-108">Para crear un filtro de casos en un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="1307c-108">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="1307c-109">En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], en el Explorador de soluciones, haga clic en la estructura de minería de datos que contiene el modelo de minería que desea filtrar.</span><span class="sxs-lookup"><span data-stu-id="1307c-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], in Solution Explorer, click the mining structure that contains the mining model you want to filter.</span></span>  
  
2.  <span data-ttu-id="1307c-110">Haga clic en la pestaña **Modelos de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="1307c-110">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="1307c-111">Seleccione el modelo y haga clic con el botón secundario del mouse para abrir el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="1307c-111">Select the model, and right-click to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="1307c-112">O bien</span><span class="sxs-lookup"><span data-stu-id="1307c-112">-or-</span></span>  
  
     <span data-ttu-id="1307c-113">Seleccione el modelo.</span><span class="sxs-lookup"><span data-stu-id="1307c-113">Select the model.</span></span> <span data-ttu-id="1307c-114">A continuación, en el menú **Modelo de minería de datos** , seleccione **Establecer filtro de modelos**.</span><span class="sxs-lookup"><span data-stu-id="1307c-114">Then, on the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
4.  <span data-ttu-id="1307c-115">En el cuadro de diálogo **Filtro del modelo** , haga clic en la fila superior de la cuadrícula en el cuadro de texto **Columna de la estructura de minería de datos** .</span><span class="sxs-lookup"><span data-stu-id="1307c-115">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
5.  <span data-ttu-id="1307c-116">Si el origen de datos contiene una única tabla plana, la lista desplegable mostrará únicamente los nombres de las columnas de dicha tabla.</span><span class="sxs-lookup"><span data-stu-id="1307c-116">If the data source contains a single flat table, the drop-down list displays only the names of the columns in that table.</span></span>  
  
     <span data-ttu-id="1307c-117">Si la estructura de minería de datos contiene varias tablas, la lista mostrará los nombres de las tablas de origen.</span><span class="sxs-lookup"><span data-stu-id="1307c-117">If the mining structure contains multiple tables, the list shows the names of the source tables.</span></span> <span data-ttu-id="1307c-118">Los nombres de columna no se muestran hasta que se seleccione una tabla.</span><span class="sxs-lookup"><span data-stu-id="1307c-118">The column names do not display until a table has been selected.</span></span>  
  
     <span data-ttu-id="1307c-119">Si la estructura de minería de datos contiene una tabla de casos y una tabla anidada, la lista desplegable mostrará las columnas de la tabla de casos y el nombre de la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="1307c-119">If the mining structure contains a case table and a nested table, the drop-down list shows columns from the case table, and the name of the nested table.</span></span>  
  
6.  <span data-ttu-id="1307c-120">Seleccione una columna en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1307c-120">Select a column from the drop-down list.</span></span>  
  
     <span data-ttu-id="1307c-121">El icono en la parte izquierda del cuadro de texto cambia para indicar que el elemento seleccionado es una tabla o una columna.</span><span class="sxs-lookup"><span data-stu-id="1307c-121">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
7.  <span data-ttu-id="1307c-122">Haga clic en el cuadro de texto **Operador** y seleccione un operador de la lista.</span><span class="sxs-lookup"><span data-stu-id="1307c-122">Click the **Operator** text box and select an operator from the list.</span></span> <span data-ttu-id="1307c-123">Los operadores válidos cambian en función del tipo de datos de la columna seleccionada.</span><span class="sxs-lookup"><span data-stu-id="1307c-123">The valid operators change depending on the data type of the column you selected.</span></span>  
  
8.  <span data-ttu-id="1307c-124">Haga clic en el cuadro de texto **Valor** y escriba un valor:</span><span class="sxs-lookup"><span data-stu-id="1307c-124">Click the **Value** text box, and type a value in the box.</span></span>  
  
     <span data-ttu-id="1307c-125">Por ejemplo, seleccione `Income` como columna, seleccione el operador mayor que (>) y, a continuación, escriba `30000` .</span><span class="sxs-lookup"><span data-stu-id="1307c-125">For example, select `Income` as the column, select the greater than operator (>), and then type `30000`.</span></span>  
  
9. <span data-ttu-id="1307c-126">Haga clic en la siguiente fila de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="1307c-126">Click the next row in the grid.</span></span>  
  
     <span data-ttu-id="1307c-127">La condición de filtro creada se agrega automáticamente al cuadro de texto Expresión.</span><span class="sxs-lookup"><span data-stu-id="1307c-127">The filter condition that you created is automatically added to the Expression text box.</span></span> <span data-ttu-id="1307c-128">Por ejemplo: `[Income] > '30000'`</span><span class="sxs-lookup"><span data-stu-id="1307c-128">For example, `[Income] > '30000'`</span></span>  
  
10. <span data-ttu-id="1307c-129">Haga clic en el cuadro de texto **Y/O** de la siguiente fila de la cuadrícula para agregar una condición.</span><span class="sxs-lookup"><span data-stu-id="1307c-129">Click the **AND/OR** text box in the next row of the grid to add a condition.</span></span>  
  
     <span data-ttu-id="1307c-130">Por ejemplo, para crear una condición BETWEEN, seleccione `AND` en la lista desplegable de operandos lógicos.</span><span class="sxs-lookup"><span data-stu-id="1307c-130">For example, to create a BETWEEN condition, select `AND` from the drop-down list of logical operands.</span></span>  
  
11. <span data-ttu-id="1307c-131">Seleccione un operador y escriba un valor tal como se describe en los pasos 7 y 8.</span><span class="sxs-lookup"><span data-stu-id="1307c-131">Select an operator and type a value as described in Steps 7 and 8.</span></span>  
  
     <span data-ttu-id="1307c-132">Por ejemplo, seleccione `Income` como columna de nuevo, seleccione el operador menor que (<) y, a continuación, escriba `40000` .</span><span class="sxs-lookup"><span data-stu-id="1307c-132">For example, select `Income` as the column again, select the less than operator (<), and then type `40000`.</span></span>  
  
12. <span data-ttu-id="1307c-133">Haga clic en la siguiente fila de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="1307c-133">Click the next row in the grid.</span></span>  
  
13. <span data-ttu-id="1307c-134">La condición  de filtro en el cuadro de texto Expresión se actualiza automáticamente para incluir la nueva condición.</span><span class="sxs-lookup"><span data-stu-id="1307c-134">The filter condition in the Expression text box is automatically updated to include the new condition.</span></span> <span data-ttu-id="1307c-135">La expresión completa es la siguiente: `[Income] > '30000'AND [Income] < '40000'`</span><span class="sxs-lookup"><span data-stu-id="1307c-135">The completed expression is as follows: `[Income] > '30000'AND [Income] < '40000'`</span></span>  
  
### <a name="to-add-a-filter-on-the-nested-table-in-a-mining-model"></a><span data-ttu-id="1307c-136">Para agregar un filtro en la tabla anidada en un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="1307c-136">To add a filter on the nested table in a mining model</span></span>  
  
1.  <span data-ttu-id="1307c-137">En el cuadro de diálogo \*\* \<name> filtro del modelo\*\* , haga clic en una fila vacía de la cuadrícula situada debajo de la **columna estructura de minería de datos**.</span><span class="sxs-lookup"><span data-stu-id="1307c-137">In the **\<name>Model Filter** Dialog box, click an empty row in the grid under **Mining Structure Column**.</span></span>  
  
2.  <span data-ttu-id="1307c-138">Seleccione el nombre de la tabla anidada en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="1307c-138">Select the name of the nested table from the drop-down list.</span></span>  
  
     <span data-ttu-id="1307c-139">El icono en la parte izquierda del cuadro de texto cambiará para indicar que el elemento seleccionado es el nombre de una tabla.</span><span class="sxs-lookup"><span data-stu-id="1307c-139">The icon at the left side of the text box changes to indicate that the selected item is the name of a table.</span></span>  
  
3.  <span data-ttu-id="1307c-140">Haga clic en el cuadro de texto **Operador** y seleccione **Contiene** o **No contiene**.</span><span class="sxs-lookup"><span data-stu-id="1307c-140">Click the **Operator** text box and select **Contains** or **Not Contain**.</span></span>  
  
     <span data-ttu-id="1307c-141">Éstas son las únicas condiciones disponibles para la tabla anidada en el cuadro de diálogo **Filtro de modelos** , porque se está restringiendo la tabla de casos a únicamente los casos que contienen un cierto valor en la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="1307c-141">These are the only conditions available for the nested table in the **Model Filter** dialog box, because you are restricting the case table to only those cases that contain a certain value in the nested table.</span></span> <span data-ttu-id="1307c-142">En el paso siguiente, se establecerá el valor de la condición en la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="1307c-142">You will set the value for the condition on the nested table in the next step.</span></span>  
  
4.  <span data-ttu-id="1307c-143">Haga clic en el cuadro **valor** y, a continuación, haga clic en el botón **(...)** para generar una expresión.</span><span class="sxs-lookup"><span data-stu-id="1307c-143">Click the **Value** box, and then click the **(...)** button to build an expression.</span></span>  
  
     <span data-ttu-id="1307c-144">Se abrirá el cuadro de diálogo \*\* \<name> filtro\*\* .</span><span class="sxs-lookup"><span data-stu-id="1307c-144">The **\<name>Filter** dialog box opens.</span></span> <span data-ttu-id="1307c-145">Este cuadro de diálogo solo puede establecer condiciones en la tabla actual, que en este caso es la tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="1307c-145">This dialog box can set conditions only on the current table, which in this case is the nested table.</span></span>  
  
5.  <span data-ttu-id="1307c-146">Haga clic en el cuadro **Columna de la estructura de minería de datos** y seleccione un nombre de columna en las listas desplegables de las columnas de tabla anidadas.</span><span class="sxs-lookup"><span data-stu-id="1307c-146">Click the **Mining Structure Column** box and select a column name from the dropdown lists of nested table columns.</span></span>  
  
6.  <span data-ttu-id="1307c-147">Haga clic en **Operador** y seleccione un operador en la lista de operadores válidos para la columna.</span><span class="sxs-lookup"><span data-stu-id="1307c-147">Click **Operator** and select an operator from the list of valid operators for the column.</span></span>  
  
7.  <span data-ttu-id="1307c-148">Haga clic en **Valor** y escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="1307c-148">Click **Value** and type a value.</span></span>  
  
     <span data-ttu-id="1307c-149">Por ejemplo, para **columna de la estructura de minería de datos,** seleccione `Model` .</span><span class="sxs-lookup"><span data-stu-id="1307c-149">For example, for **Mining Structure Column,** select `Model`.</span></span> <span data-ttu-id="1307c-150">Para **operador**, seleccione `<>` y escriba el valor `Water Bottle` .</span><span class="sxs-lookup"><span data-stu-id="1307c-150">For **Operator**, select `<>`, and type the value `Water Bottle`.</span></span> <span data-ttu-id="1307c-151">Esta condición crea la siguiente expresión de filtro:</span><span class="sxs-lookup"><span data-stu-id="1307c-151">This condition creates the following filter expression:</span></span>  
  
```  
EXISTS (SELECT * FROM [<nested table name>] WHERE [Model] <> 'Water Bottle' )   
```  
  
> [!NOTE]  
>  <span data-ttu-id="1307c-152">Dado que el número de atributos de tabla anidada es potencialmente ilimitado, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] no suministra ninguna lista de valores posibles entre los que seleccionar.</span><span class="sxs-lookup"><span data-stu-id="1307c-152">Because the number of nested table attributes is potentially unlimited, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] does not supply a list of possible values from which to select.</span></span> <span data-ttu-id="1307c-153">Debe escribir el valor exacto.</span><span class="sxs-lookup"><span data-stu-id="1307c-153">You must type the exact value.</span></span> <span data-ttu-id="1307c-154">Asimismo, no se puede utilizar a un operador LIKE en una tabla anidada.</span><span class="sxs-lookup"><span data-stu-id="1307c-154">Also, you cannot use a LIKE operator in a nested table.</span></span>  
  
1.  <span data-ttu-id="1307c-155">Agregue más condiciones según sea necesario; para ello, seleccione `AND` o `OR` en el cuadro **y/o** en el lado izquierdo de la cuadrícula de **condiciones** .</span><span class="sxs-lookup"><span data-stu-id="1307c-155">Add more conditions as necessary, combining the conditions by selecting `AND` or `OR` in the **AND/OR** box at the left side of the **Conditions** grid.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
2.  <span data-ttu-id="1307c-156">En el cuadro de diálogo **Filtro del modelo** , revise las condiciones que creó utilizando el cuadro de diálogo **Filtro** .</span><span class="sxs-lookup"><span data-stu-id="1307c-156">In the **Model Filter** dialog box, review the conditions that you created by using the **Filter** dialog box.</span></span> <span data-ttu-id="1307c-157">Las condiciones de la tabla anidada se anexan a las condiciones de la tabla de casos y el conjunto completo de condiciones de filtro se muestra en el cuadro de texto **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="1307c-157">The conditions for the nested table are appended to the conditions for the case table, and the complete set of filter conditions is displayed in the **Expression** text box.</span></span>  
  
3.  <span data-ttu-id="1307c-158">Si lo desea, haga clic en **Editar consulta** para cambiar manualmente la expresión de filtro.</span><span class="sxs-lookup"><span data-stu-id="1307c-158">Optionally, click **Edit Query** to manually change the filter expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1307c-159">Si cambia manualmente una parte de la expresión de filtro, la cuadrícula se deshabilitará y a partir de este momento deberá trabajar solo con la expresión de filtro en modo de edición de texto.</span><span class="sxs-lookup"><span data-stu-id="1307c-159">If you change any part of a filter expression manually, the grid will be disabled and thereafter you must work with the filter expression in text edit mode only.</span></span> <span data-ttu-id="1307c-160">Para restaurar el modo de edición de cuadrícula, debe borrar la expresión de filtro y comenzar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="1307c-160">To restore grid editing mode, you must clear the filter expression and start over.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="1307c-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1307c-161">See Also</span></span>  
 <span data-ttu-id="1307c-162">[Filtros para modelos de minería de datos &#40;Analysis Services-minería de datos&#41;](mining-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="1307c-162">[Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](mining-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="1307c-163">[Tareas y procedimientos del modelo de minería de datos](mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="1307c-163">[Mining Model Tasks and How-tos](mining-model-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="1307c-164">Eliminar un filtro de un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="1307c-164">Delete a Filter from a Mining Model</span></span>](delete-a-filter-from-a-mining-model.md)  
  
  
