---
title: Transformación dinámica | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.pivottrans.f1
helpviewer_keywords:
- Pivot transformation
- normalized data [Integration Services]
- PivotUsage property
- datasets [Integration Services], normalized data
- less normalized data set [Integration Services]
ms.assetid: 55f5db6e-6777-435f-8a06-b68c129f8437
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 43bdc5be709ea00d4be4601f52c38e96fe3f1ce4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752309"
---
# <a name="pivot-transformation"></a><span data-ttu-id="472d3-102">Dinámica, transformación</span><span class="sxs-lookup"><span data-stu-id="472d3-102">Pivot Transformation</span></span>
  <span data-ttu-id="472d3-103">La transformación dinámica transforma un conjunto de datos normalizado en una versión menos normalizada pero más compacta dinamizando los datos de entrada en un valor de columna.</span><span class="sxs-lookup"><span data-stu-id="472d3-103">The Pivot transformation makes a normalized data set into a less normalized but more compact version by pivoting the input data on a column value.</span></span> <span data-ttu-id="472d3-104">Por ejemplo, un conjunto de datos **Orders** normalizado que enumera el nombre del cliente, el producto y la cantidad comprada normalmente tiene varias filas para cualquier cliente que compró varios productos, donde cada fila para ese cliente muestra los detalles de pedido de un producto diferente.</span><span class="sxs-lookup"><span data-stu-id="472d3-104">For example, a normalized **Orders** data set that lists customer name, product, and quantity purchased typically has multiple rows for any customer who purchased multiple products, with each row for that customer showing order details for a different product.</span></span> <span data-ttu-id="472d3-105">Al dinamizar el conjunto de datos en la columna de producto, la transformación dinámica puede obtener un conjunto de datos con una sola fila por cliente.</span><span class="sxs-lookup"><span data-stu-id="472d3-105">By pivoting the data set on the product column, the Pivot transformation can output a data set with a single row per customer.</span></span> <span data-ttu-id="472d3-106">Esa única fila enumera todas las compras realizadas por el cliente, con los nombres de los productos representados como nombres de columnas, y la cantidad indicada como un valor en la columna de producto.</span><span class="sxs-lookup"><span data-stu-id="472d3-106">That single row lists all the purchases by the customer, with the product names shown as column names, and the quantity shown as a value in the product column.</span></span> <span data-ttu-id="472d3-107">Dado que no todos los clientes compran todos los productos, muchas columnas pueden contener valores NULL.</span><span class="sxs-lookup"><span data-stu-id="472d3-107">Because not every customer purchases every product, many columns may contain null values.</span></span>  
  
 <span data-ttu-id="472d3-108">Cuando se dinamiza un conjunto de datos, las columnas de entrada ejecutan diferentes roles en el proceso de dinamización.</span><span class="sxs-lookup"><span data-stu-id="472d3-108">When a dataset is pivoted, input columns perform different roles in the pivoting process.</span></span> <span data-ttu-id="472d3-109">Una columna puede participar de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="472d3-109">A column can participate in the following ways:</span></span>  
  
-   <span data-ttu-id="472d3-110">La columna se pasa sin cambios a la salida.</span><span class="sxs-lookup"><span data-stu-id="472d3-110">The column is passed through unchanged to the output.</span></span> <span data-ttu-id="472d3-111">Dado que varias filas de entrada pueden obtener una sola fila de salida, la transformación copia solamente el primer valor de entrada para la columna.</span><span class="sxs-lookup"><span data-stu-id="472d3-111">Because many input rows can result only in one output row, the transformation copies only the first input value for the column.</span></span>  
  
-   <span data-ttu-id="472d3-112">La columna funciona como la clave o parte de la clave que identifica un conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="472d3-112">The column acts as the key or part of the key that identifies a set of records.</span></span>  
  
-   <span data-ttu-id="472d3-113">La columna define la dinamización.</span><span class="sxs-lookup"><span data-stu-id="472d3-113">The column defines the pivot.</span></span> <span data-ttu-id="472d3-114">Los valores de esta columna se asocian con columnas en el conjunto de datos dinamizado.</span><span class="sxs-lookup"><span data-stu-id="472d3-114">The values in this column are associated with columns in the pivoted dataset.</span></span>  
  
-   <span data-ttu-id="472d3-115">La columna contiene valores que se colocan en las columnas creadas por la dinamización.</span><span class="sxs-lookup"><span data-stu-id="472d3-115">The column contains values that are placed in the columns that the pivot creates.</span></span>  
  
 <span data-ttu-id="472d3-116">Esta transformación tiene una entrada, una salida normal y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="472d3-116">This transformation has one input, one regular output, and one error output.</span></span>  
  
## <a name="sort-and-duplicate-rows"></a><span data-ttu-id="472d3-117">Ordenar y duplicar filas</span><span class="sxs-lookup"><span data-stu-id="472d3-117">Sort and Duplicate Rows</span></span>  
 <span data-ttu-id="472d3-118">Para dinamizar los datos de un modo eficaz, lo que significa crear la menor cantidad posible de registros en el conjunto de datos de salida, los datos de entrada se deben ordenar en la columna de dinamización.</span><span class="sxs-lookup"><span data-stu-id="472d3-118">To pivot data efficiently, which means creating as few records in the output dataset as possible, the input data must be sorted on the pivot column.</span></span> <span data-ttu-id="472d3-119">Si los datos no se ordenan, la transformación dinámica puede generar varios registros para cada valor en la clave fija, que es la columna que define la pertenencia a un conjunto.</span><span class="sxs-lookup"><span data-stu-id="472d3-119">If the data is not sorted, the Pivot transformation might generate multiple records for each value in the set key, which is the column that defines set membership.</span></span> <span data-ttu-id="472d3-120">Por ejemplo, si un conjunto de datos se dinamiza en una columna **Name** pero los nombres no se ordenan, el conjunto de datos de salida puede tener más de una fila para cada cliente, porque se produce una dinamización cada vez que cambia el valor de **Name** .</span><span class="sxs-lookup"><span data-stu-id="472d3-120">For example, if a dataset is pivoted on a **Name** column but the names are not sorted, the output dataset could have more than one row for each customer, because a pivot occurs every time that the value in **Name** changes.</span></span>  
  
 <span data-ttu-id="472d3-121">Los datos de entrada pueden contener filas duplicadas, que darán lugar a que no funcione la transformación Dinamización.</span><span class="sxs-lookup"><span data-stu-id="472d3-121">The input data might contain duplicate rows, which will cause the Pivot transformation to fail.</span></span> <span data-ttu-id="472d3-122">"Filas duplicadas" significa filas que tienen los mismos valores en las columnas de clave fija y las columnas dinámicas.</span><span class="sxs-lookup"><span data-stu-id="472d3-122">"Duplicate rows" means rows that have the same values in the set key columns and the pivot columns.</span></span> <span data-ttu-id="472d3-123">Para evitar este error, puede configurar la transformación para que redirija las filas que causan el error hacia una salida de error, o bien agregar previamente valores para garantizar que no haya filas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="472d3-123">To avoid failure, you can either configure the transformation to redirect error rows to an error output or you can pre-aggregate values to ensure there are no duplicate rows.</span></span>  
  
##  <a name="options-in-the-pivot-dialog-box"></a><a name="options"></a> <span data-ttu-id="472d3-124">Opciones del cuadro de diálogo Dinamización</span><span class="sxs-lookup"><span data-stu-id="472d3-124">Options in the Pivot Dialog Box</span></span>  
 <span data-ttu-id="472d3-125">Configure la operación de dinamizar, para lo cual se configuran las opciones en el cuadro de diálogo **Dinamización** .</span><span class="sxs-lookup"><span data-stu-id="472d3-125">You configure the pivot operation by setting the options in the **Pivot** dialog box.</span></span> <span data-ttu-id="472d3-126">Para abrir el cuadro de diálogo **Dinamización** , agregue la transformación dinámica al paquete en [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], haga clic con el botón derecho en el componente y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="472d3-126">To open the **Pivot** dialog box, add the Pivot transformation to the package in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and then right-click the component and click **Edit**.</span></span>  
  
 <span data-ttu-id="472d3-127">En la lista siguiente, se describen las opciones en el cuadro de diálogo **Dinamización** .</span><span class="sxs-lookup"><span data-stu-id="472d3-127">The following list describes the options in the **Pivot** dialog box.</span></span>  
  
 <span data-ttu-id="472d3-128">**Clave dinámica**</span><span class="sxs-lookup"><span data-stu-id="472d3-128">**Pivot Key**</span></span>  
 <span data-ttu-id="472d3-129">Especifica la columna que se va a utilizar para los valores de toda la fila superior (fila de encabezado) de la tabla.</span><span class="sxs-lookup"><span data-stu-id="472d3-129">Specifies the column to use for values across the top row (header row) of the table.</span></span>  
  
 <span data-ttu-id="472d3-130">**Clave fija**</span><span class="sxs-lookup"><span data-stu-id="472d3-130">**Set Key**</span></span>  
 <span data-ttu-id="472d3-131">Especifica la columna que se va a usar para los valores en la columna izquierda de la tabla.</span><span class="sxs-lookup"><span data-stu-id="472d3-131">Specifies the column to use for values in the left column of the table.</span></span> <span data-ttu-id="472d3-132">La fecha de entrada se deben ordenar en esta columna.</span><span class="sxs-lookup"><span data-stu-id="472d3-132">The input date must be sorted on this column.</span></span>  
  
 <span data-ttu-id="472d3-133">**Valor dinámico**</span><span class="sxs-lookup"><span data-stu-id="472d3-133">**Pivot Value**</span></span>  
 <span data-ttu-id="472d3-134">Especifica la columna que se va a usar para los valores de la tabla, a excepción de los valores en la fila de encabezado y en la columna izquierda.</span><span class="sxs-lookup"><span data-stu-id="472d3-134">Specifies the column to use for the table values, other than the values in the header row and the left column.</span></span>  
  
 <span data-ttu-id="472d3-135">**Omitir valores de clave dinámica que no tengan coincidencias y notificarlos tras la ejecución de flujo de datos**</span><span class="sxs-lookup"><span data-stu-id="472d3-135">**Ignore un-matched Pivot Key values and report them after DataFlow execution**</span></span>  
 <span data-ttu-id="472d3-136">Seleccione esta opción para configurar la transformación dinámica con el fin de omitir las filas que contengan valores no reconocidos en la columna **Clave dinámica** y generar todos los valores de clave dinámica en un mensaje de registro cuando se ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="472d3-136">Select this option to configure the Pivot transformation to ignore rows containing unrecognized values in the **Pivot Key** column and to output all of the pivot key values to a log message, when the package is run.</span></span>  
  
 <span data-ttu-id="472d3-137">También puede configurar la transformación para generar los valores si establece la propiedad personalizada `PassThroughUnmatchedPivotKeys` en `True`.</span><span class="sxs-lookup"><span data-stu-id="472d3-137">You can also configure the transformation to output the values by setting the `PassThroughUnmatchedPivotKeys` custom property to `True`.</span></span>  
  
 <span data-ttu-id="472d3-138">**Generar columnas de salida dinámicas a partir de valores**</span><span class="sxs-lookup"><span data-stu-id="472d3-138">**Generate pivot output columns from values**</span></span>  
 <span data-ttu-id="472d3-139">Escriba los valores de clave dinámica en este cuadro para permitir la transformación dinámica con el fin de crear columnas de salida para cada valor.</span><span class="sxs-lookup"><span data-stu-id="472d3-139">Enter the pivot key values in this box to enable the Pivot transformation to create output columns for each value.</span></span> <span data-ttu-id="472d3-140">Puede especificar los valores antes de ejecutar el paquete o hacer lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="472d3-140">You can either enter the values prior to running the package, or do the following.</span></span>  
  
1.  <span data-ttu-id="472d3-141">Seleccione la opción **Omitir los valores de clave dinámica no coincidentes y registrarlos después de la ejecución del flujo de datos** y, después, haga clic en **Aceptar** en el cuadro de diálogo **Dinamización** para guardar los cambios en la transformación dinámica.</span><span class="sxs-lookup"><span data-stu-id="472d3-141">Select the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then click **OK** in the **Pivot** dialog box to save the changes to the Pivot transformation.</span></span>  
  
2.  <span data-ttu-id="472d3-142">Ejecute el paquete.</span><span class="sxs-lookup"><span data-stu-id="472d3-142">Run the package.</span></span>  
  
3.  <span data-ttu-id="472d3-143">Cuando el paquete se ejecute correctamente, haga clic en la pestaña **Progreso** y busque el mensaje del registro de información de la transformación dinámica que contiene los valores de clave dinámica.</span><span class="sxs-lookup"><span data-stu-id="472d3-143">When the package succeeds, click the **Progress** tab and look for the information log message from the Pivot transformation that contains the pivot key values.</span></span>  
  
4.  <span data-ttu-id="472d3-144">Haga clic con el botón derecho en el mensaje y, después, haga clic en **Copiar texto del mensaje**.</span><span class="sxs-lookup"><span data-stu-id="472d3-144">Right-click the message and click **Copy Message Text**.</span></span>  
  
5.  <span data-ttu-id="472d3-145">Haga clic en **Detener depuración** en el menú **Depurar** para ir al modo de diseño.</span><span class="sxs-lookup"><span data-stu-id="472d3-145">Click **Stop Debugging** on the **Debug** menu to switch to the design mode.</span></span>  
  
6.  <span data-ttu-id="472d3-146">Haga clic con el botón derecho en Transformación dinámica y, después, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="472d3-146">Right-click the Pivot transformation, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="472d3-147">Desactive la opción **Omitir los valores de clave dinámica no coincidentes y registrarlos después de la ejecución del flujo de datos** y pegue los valores de clave dinámica en el cuadro **Generar columnas de salida dinámicas a partir de valores** con el formato siguiente.</span><span class="sxs-lookup"><span data-stu-id="472d3-147">Uncheck the **Ignore un-matched Pivot Key values and report them after DataFlow execution** option, and then paste the pivot key values in the **Generate pivot output columns from values** box using the following format.</span></span>  
  
     <span data-ttu-id="472d3-148">[valor1],[valor2],[valor3]</span><span class="sxs-lookup"><span data-stu-id="472d3-148">[value1],[value2],[value3]</span></span>  
  
 <span data-ttu-id="472d3-149">**Generar columnas ahora**</span><span class="sxs-lookup"><span data-stu-id="472d3-149">**Generate Columns Now**</span></span>  
 <span data-ttu-id="472d3-150">Haga clic para crear una columna de salida por cada valor de clave dinámica que aparece en el cuadro **Generar columnas de salida dinámicas a partir de valores** .</span><span class="sxs-lookup"><span data-stu-id="472d3-150">Click to create an output column for each pivot key value that is listed in the **Generate pivot output columns from values** box.</span></span>  
  
 <span data-ttu-id="472d3-151">Las columnas de salida aparecen en el cuadro **Columnas de salida dinámicas existentes** .</span><span class="sxs-lookup"><span data-stu-id="472d3-151">The output columns appear in the **Existing pivoted output columns** box.</span></span>  
  
 <span data-ttu-id="472d3-152">**Columnas de salida dinámicas existentes**</span><span class="sxs-lookup"><span data-stu-id="472d3-152">**Existing pivoted output columns**</span></span>  
 <span data-ttu-id="472d3-153">Muestra las columnas de salida para los valores de clave dinámica</span><span class="sxs-lookup"><span data-stu-id="472d3-153">Lists the output columns for the pivot key values</span></span>  
  
 <span data-ttu-id="472d3-154">En la tabla siguiente se muestra un conjunto de datos antes de dinamizar los datos en la columna **Year** .</span><span class="sxs-lookup"><span data-stu-id="472d3-154">The following table shows a data set before the data is pivoted on the **Year** column.</span></span>  
  
|<span data-ttu-id="472d3-155">Year</span><span class="sxs-lookup"><span data-stu-id="472d3-155">Year</span></span>|<span data-ttu-id="472d3-156">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="472d3-156">Product Name</span></span>|<span data-ttu-id="472d3-157">Total</span><span class="sxs-lookup"><span data-stu-id="472d3-157">Total</span></span>|  
|----------|------------------|-----------|  
|<span data-ttu-id="472d3-158">2004</span><span class="sxs-lookup"><span data-stu-id="472d3-158">2004</span></span>|<span data-ttu-id="472d3-159">HL Mountain Tire</span><span class="sxs-lookup"><span data-stu-id="472d3-159">HL Mountain Tire</span></span>|<span data-ttu-id="472d3-160">1504884.15</span><span class="sxs-lookup"><span data-stu-id="472d3-160">1504884.15</span></span>|  
|<span data-ttu-id="472d3-161">2003</span><span class="sxs-lookup"><span data-stu-id="472d3-161">2003</span></span>|<span data-ttu-id="472d3-162">Road Tire Tube</span><span class="sxs-lookup"><span data-stu-id="472d3-162">Road Tire Tube</span></span>|<span data-ttu-id="472d3-163">35920.50</span><span class="sxs-lookup"><span data-stu-id="472d3-163">35920.50</span></span>|  
|<span data-ttu-id="472d3-164">2004</span><span class="sxs-lookup"><span data-stu-id="472d3-164">2004</span></span>|<span data-ttu-id="472d3-165">Water Bottle - 30 oz.</span><span class="sxs-lookup"><span data-stu-id="472d3-165">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="472d3-166">2805.00</span><span class="sxs-lookup"><span data-stu-id="472d3-166">2805.00</span></span>|  
|<span data-ttu-id="472d3-167">2002</span><span class="sxs-lookup"><span data-stu-id="472d3-167">2002</span></span>|<span data-ttu-id="472d3-168">Touring tire</span><span class="sxs-lookup"><span data-stu-id="472d3-168">Touring Tire</span></span>|<span data-ttu-id="472d3-169">62364.225</span><span class="sxs-lookup"><span data-stu-id="472d3-169">62364.225</span></span>|  
  
 <span data-ttu-id="472d3-170">La tabla siguiente muestra un conjunto de datos después de que los datos se hayan dinamizado en la columna **Year** .</span><span class="sxs-lookup"><span data-stu-id="472d3-170">The following table shows a data set after the data has been pivoted on the **Year** column.</span></span>  
  
||<span data-ttu-id="472d3-171">2002</span><span class="sxs-lookup"><span data-stu-id="472d3-171">2002</span></span>|<span data-ttu-id="472d3-172">2003</span><span class="sxs-lookup"><span data-stu-id="472d3-172">2003</span></span>|<span data-ttu-id="472d3-173">2004</span><span class="sxs-lookup"><span data-stu-id="472d3-173">2004</span></span>|  
|-|----------|----------|----------|  
|<span data-ttu-id="472d3-174">HL Mountain Tire</span><span class="sxs-lookup"><span data-stu-id="472d3-174">HL Mountain Tire</span></span>|<span data-ttu-id="472d3-175">141164.10</span><span class="sxs-lookup"><span data-stu-id="472d3-175">141164.10</span></span>|<span data-ttu-id="472d3-176">446297.775</span><span class="sxs-lookup"><span data-stu-id="472d3-176">446297.775</span></span>|<span data-ttu-id="472d3-177">1504884.15</span><span class="sxs-lookup"><span data-stu-id="472d3-177">1504884.15</span></span>|  
|<span data-ttu-id="472d3-178">Road Tire Tube</span><span class="sxs-lookup"><span data-stu-id="472d3-178">Road Tire Tube</span></span>|<span data-ttu-id="472d3-179">3592.05</span><span class="sxs-lookup"><span data-stu-id="472d3-179">3592.05</span></span>|<span data-ttu-id="472d3-180">35920.50</span><span class="sxs-lookup"><span data-stu-id="472d3-180">35920.50</span></span>|<span data-ttu-id="472d3-181">89801.25</span><span class="sxs-lookup"><span data-stu-id="472d3-181">89801.25</span></span>|  
|<span data-ttu-id="472d3-182">Water Bottle - 30 oz.</span><span class="sxs-lookup"><span data-stu-id="472d3-182">Water Bottle - 30 oz.</span></span>|<span data-ttu-id="472d3-183">*NULL*</span><span class="sxs-lookup"><span data-stu-id="472d3-183">*NULL*</span></span>|<span data-ttu-id="472d3-184">*NULL*</span><span class="sxs-lookup"><span data-stu-id="472d3-184">*NULL*</span></span>|<span data-ttu-id="472d3-185">2805.00</span><span class="sxs-lookup"><span data-stu-id="472d3-185">2805.00</span></span>|  
|<span data-ttu-id="472d3-186">Touring tire</span><span class="sxs-lookup"><span data-stu-id="472d3-186">Touring Tire</span></span>|<span data-ttu-id="472d3-187">62364.225</span><span class="sxs-lookup"><span data-stu-id="472d3-187">62364.225</span></span>|<span data-ttu-id="472d3-188">375051.60</span><span class="sxs-lookup"><span data-stu-id="472d3-188">375051.60</span></span>|<span data-ttu-id="472d3-189">1041810.00</span><span class="sxs-lookup"><span data-stu-id="472d3-189">1041810.00</span></span>|  
  
 <span data-ttu-id="472d3-190">Para dinamizar los datos de la columna **Year** , tal como se muestra más arriba, se establecen las opciones siguientes en el cuadro de diálogo **Dinamización** .</span><span class="sxs-lookup"><span data-stu-id="472d3-190">To pivot the data on the **Year** column, as shown above, the following options are set in the **Pivot** dialog box.</span></span>  
  
-   <span data-ttu-id="472d3-191">El año está seleccionado en el cuadro de lista **Clave dinámica** .</span><span class="sxs-lookup"><span data-stu-id="472d3-191">Year is selected in the **Pivot Key** list box.</span></span>  
  
-   <span data-ttu-id="472d3-192">El nombre de producto se selecciona en el cuadro de lista **Clave fija** .</span><span class="sxs-lookup"><span data-stu-id="472d3-192">Product Name is selected in the **Set Key** list box.</span></span>  
  
-   <span data-ttu-id="472d3-193">El total está seleccionado en el cuadro de lista **Valor dinámico** .</span><span class="sxs-lookup"><span data-stu-id="472d3-193">Total is selected in the **Pivot Value** list box.</span></span>  
  
-   <span data-ttu-id="472d3-194">Estos valores se van incluyendo en el cuadro **Generar columnas de salida dinámicas a partir de valores** .</span><span class="sxs-lookup"><span data-stu-id="472d3-194">The following values are entered in the **Generate pivot output columns from values** box.</span></span>  
  
     <span data-ttu-id="472d3-195">[2002],[2003],[2004]</span><span class="sxs-lookup"><span data-stu-id="472d3-195">[2002],[2003],[2004]</span></span>  
  
## <a name="configuration-of-the-pivot-transformation"></a><span data-ttu-id="472d3-196">Configuración de la transformación Dinámica</span><span class="sxs-lookup"><span data-stu-id="472d3-196">Configuration of the Pivot Transformation</span></span>  
 <span data-ttu-id="472d3-197">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="472d3-197">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="472d3-198">Para obtener más información sobre las propiedades que se pueden configurar en el cuadro de diálogo **Editor avanzado** , haga clic en uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="472d3-198">For more information about the properties that you can set in the **Advanced Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="472d3-199">Common Properties</span><span class="sxs-lookup"><span data-stu-id="472d3-199">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="472d3-200">Propiedades personalizadas de transformación</span><span class="sxs-lookup"><span data-stu-id="472d3-200">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-content"></a><span data-ttu-id="472d3-201">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="472d3-201">Related Content</span></span>  
 <span data-ttu-id="472d3-202">Para obtener más información sobre cómo establecer las propiedades de este componente, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="472d3-202">For information about how to set the properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="472d3-203">Consulte también</span><span class="sxs-lookup"><span data-stu-id="472d3-203">See Also</span></span>  
 <span data-ttu-id="472d3-204">[Transformación Anulación de dinamización](pivot-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="472d3-204">[Unpivot Transformation](pivot-transformation.md) </span></span>  
 <span data-ttu-id="472d3-205">[Flujo de datos](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="472d3-205">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="472d3-206">Transformaciones de Integration Services</span><span class="sxs-lookup"><span data-stu-id="472d3-206">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
