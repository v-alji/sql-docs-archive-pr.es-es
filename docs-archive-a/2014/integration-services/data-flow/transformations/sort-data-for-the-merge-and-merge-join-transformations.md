---
title: Ordenar datos para las transformaciones Mezclar y Combinación de mezcla | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- sort attributes [Integration Services]
- output columns [Integration Services]
ms.assetid: 22ce3f5d-8a88-4423-92c2-60a8f82cd4fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7bb4e91ad84c6baa52e1d7fb4b0104d835b7e4cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744207"
---
# <a name="sort-data-for-the-merge-and-merge-join-transformations"></a><span data-ttu-id="a7e8d-102">Ordenar datos para las transformaciones Mezclar y Combinación de mezcla</span><span class="sxs-lookup"><span data-stu-id="a7e8d-102">Sort Data for the Merge and Merge Join Transformations</span></span>
  <span data-ttu-id="a7e8d-103">En [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], las transformaciones Mezclar y Combinación de mezcla requieren datos ordenados en sus entradas.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-103">In [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], the Merge and Merge Join transformations require sorted data for their inputs.</span></span> <span data-ttu-id="a7e8d-104">Los datos de entrada deben estar ordenados físicamente, y se deben establecer opciones de ordenación en las salidas y en las columnas de salida del origen o en la transformación de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-104">The input data must be sorted physically, and sort options must be set on the outputs and the output columns in the source or in the upstream transformation.</span></span> <span data-ttu-id="a7e8d-105">Si las opciones de ordenación indican que los datos están ordenados, pero en realidad no lo están, los resultados de la operación de mezcla o combinación de mezcla son impredecibles.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-105">If the sort options indicate that the data is sorted, but the data is not actually sorted, the results of the merge or merge join operation are unpredictable.</span></span>  
  
## <a name="sorting-the-data"></a><span data-ttu-id="a7e8d-106">Ordenar los datos</span><span class="sxs-lookup"><span data-stu-id="a7e8d-106">Sorting the Data</span></span>  
 <span data-ttu-id="a7e8d-107">Para ordenar estos datos, puede usar uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7e8d-107">You can sort this data by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="a7e8d-108">En el origen, use una cláusula ORDER BY en la instrucción empleada para cargar los datos.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-108">In the source, use an ORDER BY clause in the statement that is used to load the data.</span></span>  
  
-   <span data-ttu-id="a7e8d-109">En el flujo de datos, inserte una transformación Ordenar antes de la transformación Mezclar o Combinación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-109">In the data flow, insert a Sort transformation before the Merge or Merge Join transformation.</span></span>  
  
 <span data-ttu-id="a7e8d-110">Si los datos son cadenas, las transformaciones Mezclar y Combinación de mezcla esperan que los valores de cadena se hayan ordenado usando la intercalación de Windows.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-110">If the data is string data, both the Merge and Merge Join transformations expect the string values to have been sorted by using Windows collation.</span></span> <span data-ttu-id="a7e8d-111">Para proporcionar valores de cadena a las transformaciones Mezclar y Combinación de mezcla ordenadas mediante la intercalación de Windows, use el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7e8d-111">To provide string values to the Merge and Merge Join transformations that are sorted by using Windows collation, use the following procedure.</span></span>  
  
#### <a name="to-provide-string-values-that-are-sorted-by-using-windows-collation"></a><span data-ttu-id="a7e8d-112">Para proporcionar valores de cadena ordenados mediante la intercalación de Windows</span><span class="sxs-lookup"><span data-stu-id="a7e8d-112">To provide string values that are sorted by using Windows collation</span></span>  
  
-   <span data-ttu-id="a7e8d-113">Utilice una transformación Ordenar para ordenar los datos.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-113">Use a Sort transformation to sort the data.</span></span>  
  
     <span data-ttu-id="a7e8d-114">La transformación Ordenar utiliza la intercalación de Windows para ordenar los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-114">The Sort transformation uses Windows collation to sort string values.</span></span>  
  
     <span data-ttu-id="a7e8d-115">O bien</span><span class="sxs-lookup"><span data-stu-id="a7e8d-115">-or-</span></span>  
  
-   <span data-ttu-id="a7e8d-116">Utilice el operador CAST de Transact-SQL para convertir primero los valores `varchar` en valores `nvarchar` y, a continuación, utilice la cláusula ORDER BY de Transact-SQL para ordenar los datos.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-116">Use the Transact-SQL CAST operator to first cast `varchar` values to `nvarchar` values, and then use the Transact-SQL ORDER BY clause to sort the data.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a7e8d-117">No puede utilizar la cláusula ORDER BY en solitario porque la cláusula ORDER BY utiliza una intercalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para ordenar los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-117">You cannot use the ORDER BY clause alone because the ORDER BY clause uses a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation to sort string values.</span></span> <span data-ttu-id="a7e8d-118">El uso de la intercalación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] puede dar lugar a un criterio de ordenación diferente del obtenido con la intercalación de Windows, lo que puede hacer que la transformación Mezclar o Combinación de mezcla genere resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-118">The use of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] collation might result in a different sort order than Windows collation, which can cause the Merge or Merge Join transformation to produce unexpected results.</span></span>  
  
## <a name="setting-sort-options-on-the-data"></a><span data-ttu-id="a7e8d-119">Establecer opciones de ordenación en los datos</span><span class="sxs-lookup"><span data-stu-id="a7e8d-119">Setting Sort Options on the Data</span></span>  
 <span data-ttu-id="a7e8d-120">Hay dos propiedades de ordenación importantes que se deben establecer para el origen o la transformación de nivel superior que proporciona los datos a las transformaciones Mezclar y Combinación de mezcla:</span><span class="sxs-lookup"><span data-stu-id="a7e8d-120">There are two important sort properties that must be set for the source or upstream transformation that supplies data to the Merge and Merge Join transformations:</span></span>  
  
-   <span data-ttu-id="a7e8d-121">La propiedad `IsSorted` de la salida que indica si los datos se han ordenado.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-121">The `IsSorted` property of the output that indicates whether the data has been sorted.</span></span> <span data-ttu-id="a7e8d-122">Esta propiedad debe estar establecida en `True`.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-122">This property must be set to `True`.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="a7e8d-123">Aunque se establezca el valor de la propiedad `IsSorted` en `True`, los datos no se ordenan.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-123">Setting the value of the `IsSorted` property to `True` does not sort the data.</span></span> <span data-ttu-id="a7e8d-124">Esta propiedad únicamente proporciona una sugerencia a los componentes de nivel inferior acerca de que los datos se han ordenado previamente.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-124">This property only provides a hint to downstream components that the data has been previously sorted.</span></span>  
  
-   <span data-ttu-id="a7e8d-125">La propiedad `SortKeyPosition` de las columnas de salida que indica si una columna está ordenada, el criterio de ordenación de ésta y la secuencia en la que se ordenan varias columnas.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-125">The `SortKeyPosition` property of output columns that indicates whether a column is sorted, the column's sort order, and the sequence in which multiple columns are sorted.</span></span> <span data-ttu-id="a7e8d-126">Esta propiedad se debe establecer para cada columna de datos ordenados.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-126">This property must be set for each column of sorted data.</span></span>  
  
 <span data-ttu-id="a7e8d-127">Si usa una transformación Ordenar para ordenar los datos, esta transformación establece ambas propiedades como requeridas por la transformación Mezclar o Combinación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-127">If you use a Sort transformation to sort the data, the Sort transformation sets both of these properties as required by the Merge or Merge Join transformation.</span></span> <span data-ttu-id="a7e8d-128">Es decir, la transformación Ordenar establece la propiedad `IsSorted` de su salida en `True`, y establece las propiedades `SortKeyPosition` de sus columnas de resultados.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-128">That is, the Sort transformation sets the `IsSorted` property of its output to `True`, and sets the `SortKeyPosition` properties of its output columns.</span></span>  
  
 <span data-ttu-id="a7e8d-129">Sin embargo, si no usa una transformación Ordenar para ordenar los datos, debe establecer estas propiedades de ordenación manualmente en el origen o en la transformación de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-129">However, if you do not use a Sort transformation to sort the data, you must set these sort properties manually on the source or the upstream transformation.</span></span> <span data-ttu-id="a7e8d-130">Para establecer manualmente las propiedades de ordenación en el origen o en la transformación de nivel superior, use el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-130">To manually set the sort properties on the source or upstream transformation, use the following procedure.</span></span>  
  
#### <a name="to-manually-set-sort-attributes-on-a-source-or-transformation-component"></a><span data-ttu-id="a7e8d-131">Para establecer manualmente los atributos de ordenación en un componente de origen o de transformación</span><span class="sxs-lookup"><span data-stu-id="a7e8d-131">To manually set sort attributes on a source or transformation component</span></span>  
  
1.  <span data-ttu-id="a7e8d-132">En [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-132">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="a7e8d-133">En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-133">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a7e8d-134">En la pestaña **Flujo de datos** , busque el origen o la transformación de nivel superior adecuados, o arrástrelos desde el **Cuadro de herramientas** hasta la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-134">On the **Data Flow** tab, locate the appropriate source or upstream transformation, or drag it from the **Toolbox** to the design surface.</span></span>  
  
4.  <span data-ttu-id="a7e8d-135">Haga clic con el botón derecho en el componente y haga clic en **Mostrar editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-135">Right-click the component and click **Show Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="a7e8d-136">Haga clic en la pestaña **Propiedades de entrada y salida** .</span><span class="sxs-lookup"><span data-stu-id="a7e8d-136">Click the **Input and Output Properties** tab.</span></span>  
  
6.  <span data-ttu-id="a7e8d-137">Haga clic en \*\* \<component name> salida\*\*y establezca la `IsSorted` propiedad en `True` .</span><span class="sxs-lookup"><span data-stu-id="a7e8d-137">Click **\<component name> Output**, and set the `IsSorted` property to `True`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a7e8d-138">Si establece manualmente la propiedad `IsSorted` de la salida en `True` y los datos no están ordenados, es posible que falten datos o haya comparaciones de datos no válidas en la transformación de nivel inferior Mezclar o Combinación de mezcla al ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-138">If you manually set the `IsSorted` property of the output to `True` and the data is not sorted, there might be missing data or bad data comparisons in the downstream Merge or Merge Join transformation when you run the package.</span></span>  
  
7.  <span data-ttu-id="a7e8d-139">Expanda **Columnas de salida**.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-139">Expand **Output Columns**.</span></span>  
  
8.  <span data-ttu-id="a7e8d-140">Haga clic en la columna que desea indicar que esté ordenada y establezca su propiedad `SortKeyPosition` en un valor entero distinto de cero siguiendo estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="a7e8d-140">Click the column that you want to indicate is sorted and set its `SortKeyPosition` property to a nonzero integer value by following these guidelines:</span></span>  
  
    -   <span data-ttu-id="a7e8d-141">El valor entero debe representar una secuencia numérica, a partir de 1 y con incrementos de 1.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-141">The integer value must represent a numeric sequence, starting with 1 and incremented by 1.</span></span>  
  
    -   <span data-ttu-id="a7e8d-142">Un valor entero positivo indica un criterio de ordenación ascendente.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-142">A positive integer value indicates an ascending sort order.</span></span>  
  
    -   <span data-ttu-id="a7e8d-143">Un valor entero negativo indica un criterio de ordenación descendente.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-143">A negative integer value indicates a descending sort order.</span></span> <span data-ttu-id="a7e8d-144">Si se establece en un número negativo, el valor absoluto del número determina la posición de la columna en la secuencia de ordenación.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-144">(If set to a negative number, the absolute value of the number determines the column's position in the sort sequence.)</span></span>  
  
    -   <span data-ttu-id="a7e8d-145">El valor predeterminado, 0, indica que la columna no está ordenada.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-145">The default value of 0 indicates that the column is not sorted.</span></span> <span data-ttu-id="a7e8d-146">Conserve el valor 0 para las columnas de salida que no forman parte de la ordenación.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-146">Leave the value of 0 for output columns that do not participate in the sort.</span></span>  
  
     <span data-ttu-id="a7e8d-147">Como ejemplo del modo en que se establece la propiedad `SortKeyPosition`, considere la instrucción Transact-SQL siguiente que carga datos en un origen:</span><span class="sxs-lookup"><span data-stu-id="a7e8d-147">As an example of how to set the `SortKeyPosition` property, consider the following Transact-SQL statement that loads data in a source:</span></span>  
  
     `SELECT * FROM MyTable ORDER BY ColumnA, ColumnB DESC, ColumnC`  
  
     <span data-ttu-id="a7e8d-148">Para esta instrucción, se establecería la propiedad `SortKeyPosition` para cada columna de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="a7e8d-148">For this statement, you would set the `SortKeyPosition` property for each column as follows:</span></span>  
  
    -   <span data-ttu-id="a7e8d-149">Establezca la propiedad `SortKeyPosition` de ColumnA en 1.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-149">Set the `SortKeyPosition` property of ColumnA to 1.</span></span> <span data-ttu-id="a7e8d-150">Esto indica que ColumnA es la primera columna que se va a ordenar y se hará en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-150">This indicates that ColumnA is the first column to be sorted and is sorted in ascending order.</span></span>  
  
    -   <span data-ttu-id="a7e8d-151">Establezca la propiedad `SortKeyPosition` de ColumnB en -2.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-151">Set the `SortKeyPosition` property of ColumnB to -2.</span></span> <span data-ttu-id="a7e8d-152">Esto indica que ColumnB es la segunda columna que se va a ordenar y se hará en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-152">This indicates that ColumnB is the second column to be sorted and is sorted in descending order</span></span>  
  
    -   <span data-ttu-id="a7e8d-153">Establezca la propiedad `SortKeyPosition` de ColumnC en 3.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-153">Set the `SortKeyPosition` property of ColumnC to 3.</span></span> <span data-ttu-id="a7e8d-154">Esto indica que ColumnC es la tercera columna que se va a ordenar y se hará en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-154">This indicates that ColumnC is the third column to be sorted and is sorted in ascending order.</span></span>  
  
9. <span data-ttu-id="a7e8d-155">Repita el paso 8 para cada columna ordenada.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-155">Repeat step 8 for each sorted column.</span></span>  
  
10. <span data-ttu-id="a7e8d-156">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-156">Click **OK**.</span></span>  
  
11. <span data-ttu-id="a7e8d-157">Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="a7e8d-157">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e8d-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a7e8d-158">See Also</span></span>  
 <span data-ttu-id="a7e8d-159">[Transformación Mezclar](merge-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="a7e8d-159">[Merge Transformation](merge-transformation.md) </span></span>  
 <span data-ttu-id="a7e8d-160">[Transformación Combinación de mezcla](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="a7e8d-160">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="a7e8d-161">[Transformaciones de Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="a7e8d-161">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="a7e8d-162">[Rutas de Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="a7e8d-162">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="a7e8d-163">Tarea Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="a7e8d-163">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
