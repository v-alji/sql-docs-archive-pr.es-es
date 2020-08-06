---
title: 'Tutorial: Agregar un parámetro a un informe (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eab34ec4-b3ad-4a76-95cc-07b2f75ee6d7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dff41066a2d505ab53b17a10fb3da9b6cb17130f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747934"
---
# <a name="tutorial-add-a-parameter-to-your-report-report-builder"></a><span data-ttu-id="43e42-102">Tutorial: Agregar un parámetro a un informe (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="43e42-102">Tutorial: Add a Parameter to Your Report (Report Builder)</span></span>
  <span data-ttu-id="43e42-103">Agregue un parámetro a un informe para permitir que los usuarios filtren los datos del informe desde el origen de datos o el informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-103">Add a parameter to your report to let users filter report data from the data source or in the report.</span></span> <span data-ttu-id="43e42-104">Los parámetros del informe se crean automáticamente para cada parámetro de la consulta que incluya en una consulta del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="43e42-104">Report parameters are created automatically for each query parameter that you include in a dataset query.</span></span> <span data-ttu-id="43e42-105">El tipo de datos de parámetro determina cómo aparece en la barra de herramientas de visualización de informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-105">The parameter data type determines how it appears on the report view toolbar.</span></span>  
  
 <span data-ttu-id="43e42-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span><span class="sxs-lookup"><span data-stu-id="43e42-106">![rs_tut_Parameter](../../2014/tutorials/media/rs-tut-parameter.gif "rs_tut_Parameter")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="43e42-107">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="43e42-107">What You Will Learn</span></span>  
 <span data-ttu-id="43e42-108">En este tutorial, aprenderá a realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="43e42-108">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="43e42-109">Crear un informe de matriz y un conjunto de datos con el asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="43e42-109">Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="43e42-110">Organizar datos, elegir el diseño y el estilo con el asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="43e42-110">Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>](#CompleteWizard)  
  
3.  [<span data-ttu-id="43e42-111">Agregar un parámetro de consulta para crear un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="43e42-111">Add a Query Parameter to Create a Report Parameter</span></span>](#Query)  
  
4.  [<span data-ttu-id="43e42-112">Cambiar el tipo de datos predeterminado y otras propiedades de un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="43e42-112">Change Default Data Type and Other Properties for a Report Parameter</span></span>](#ChangeDefaultProperties)  
  
    1.  [<span data-ttu-id="43e42-113">Agregar un conjunto de datos para proporcionar los valores disponibles y nombres para mostrar</span><span class="sxs-lookup"><span data-stu-id="43e42-113">Add a Dataset to Provide Available Values and Display Names</span></span>](#AddDataset)  
  
    2.  [<span data-ttu-id="43e42-114">Especificar valores disponibles para crear una lista desplegable de valores</span><span class="sxs-lookup"><span data-stu-id="43e42-114">Specify Available Values to Create a Drop-List of Values</span></span>](#AvailableValues)  
  
    3.  [<span data-ttu-id="43e42-115">Especificar valores predeterminados para que el informe se ejecute automáticamente</span><span class="sxs-lookup"><span data-stu-id="43e42-115">Specify Default Values so the Report Runs Automatically</span></span>](#DefaultValues)  
  
    4.  [<span data-ttu-id="43e42-116">Buscar un valor de un conjunto de datos que tiene pares de name y valor</span><span class="sxs-lookup"><span data-stu-id="43e42-116">Look up a Value from a Dataset that has Name/Value Pairs</span></span>](#NameValue)  
  
5.  [<span data-ttu-id="43e42-117">Mostrar el valor de parámetro seleccionado en el informe</span><span class="sxs-lookup"><span data-stu-id="43e42-117">Display the Selected Parameter Value in the Report</span></span>](#Expression)  
  
6.  [<span data-ttu-id="43e42-118">Utilizar el parámetro de informe en un filtro</span><span class="sxs-lookup"><span data-stu-id="43e42-118">Use the Report Parameter in a Filter</span></span>](#Filter)  
  
7.  [<span data-ttu-id="43e42-119">Cambiar el parámetro de informe a fin de que acepte varios valores</span><span class="sxs-lookup"><span data-stu-id="43e42-119">Change the Report Parameter to Accept Multiple Values</span></span>](#Multivalued)  
  
8.  [<span data-ttu-id="43e42-120">Agregar un parámetro booleano para obtener visibilidad condicional</span><span class="sxs-lookup"><span data-stu-id="43e42-120">Add a Boolean Parameter for Conditional Visibility</span></span>](#Boolean)  
  
9. [<span data-ttu-id="43e42-121">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="43e42-121">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="43e42-122">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="43e42-122">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="43e42-123">En este tutorial, los pasos del asistente se encuentran reunidos en un único procedimiento.</span><span class="sxs-lookup"><span data-stu-id="43e42-123">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="43e42-124">Para obtener instrucciones paso a paso sobre cómo ir hasta un servidor de informes, elegir un origen de datos y crear un conjunto de datos, consulte el primer tutorial de esta serie: [Tutorial: Crear un informe de tabla básico &#40;Generador de informes&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="43e42-124">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="43e42-125">Tiempo estimado para completar este tutorial: 25 minutos.</span><span class="sxs-lookup"><span data-stu-id="43e42-125">Estimated time to complete this tutorial: 25 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43e42-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43e42-126">Requirements</span></span>  
 <span data-ttu-id="43e42-127">Para obtener información sobre los requisitos, vea [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="43e42-127">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="43e42-128">1. crear un informe de matriz y un conjunto de DataSet desde el Asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="43e42-128">1. Create a Matrix Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="43e42-129">Cree un informe de matriz, un origen de datos y un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="43e42-129">Create a matrix report, a data source, and a dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="43e42-130">En este tutorial, la consulta contiene los valores de datos, de forma que no necesita un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="43e42-130">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="43e42-131">Esto hace que la consulta requiera bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="43e42-131">This makes the query quite long.</span></span> <span data-ttu-id="43e42-132">En un entorno empresarial, la consulta no contendría los datos.</span><span class="sxs-lookup"><span data-stu-id="43e42-132">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="43e42-133">Esto es solo con fines de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="43e42-133">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix-report"></a><span data-ttu-id="43e42-134">Para crear un nuevo informe de matriz</span><span class="sxs-lookup"><span data-stu-id="43e42-134">To create a new matrix report</span></span>  
  
1.  <span data-ttu-id="43e42-135">Haga clic en **Inicio**, seleccione **Programas**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Generador de informes**y luego haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="43e42-135">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="43e42-136">Aparece el cuadro de diálogo **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="43e42-136">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43e42-137">Si el cuadro de diálogo **Introducción** no aparece, en el botón **generador de informes** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="43e42-137">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="43e42-138">En el panel de la izquierda, compruebe que está seleccionada la opción **Informe** .</span><span class="sxs-lookup"><span data-stu-id="43e42-138">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="43e42-139">En el panel de la derecha, haga clic en **Asistente para tabla o matriz**.</span><span class="sxs-lookup"><span data-stu-id="43e42-139">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="43e42-140">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="43e42-140">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="43e42-141">En la página **Elegir un conjunto de datos** , haga clic en **Crear un conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="43e42-141">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
6.  <span data-ttu-id="43e42-142">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="43e42-142">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="43e42-143">En la página **Elegir una conexión a un origen de datos** , seleccione un origen de datos del tipo **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="43e42-143">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="43e42-144">Seleccione un origen de datos en la lista o vaya al servidor de informes para seleccionar uno.</span><span class="sxs-lookup"><span data-stu-id="43e42-144">Select a data source from the list or browse to the report server to select one.</span></span>  
  
8.  <span data-ttu-id="43e42-145">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="43e42-145">Click **Next**.</span></span>  
  
9. <span data-ttu-id="43e42-146">En la página **Diseñar una consulta** , haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="43e42-146">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
10. <span data-ttu-id="43e42-147">Pegue la siguiente consulta en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="43e42-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    ;WITH CTE (StoreID, Subcategory, Quantity)   
    AS (  
    SELECT 200 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 2002 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Camcorders' AS Subcategory, 1954 AS Quantity  
    UNION SELECT  200 AS StoreID, 'Accessories' AS Subcategory, 1895 AS Quantity  
    UNION SELECT  199 AS StoreID, 'Digital Cameras' AS Subcategory, 1849 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1579 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Camcorders' AS Subcategory, 1561 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Digital Cameras' AS Subcategory, 1553 AS Quantity  
    UNION SELECT  306 AS StoreID, 'Accessories' AS Subcategory, 1534 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Accessories' AS Subcategory, 1755 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Camcorders' AS Subcategory, 1631 AS Quantity  
    UNION SELECT 307 AS StoreID, 'Digital SLR Cameras' AS Subcategory, 1772 AS Quantity)  
    SELECT StoreID, Subcategory, Quantity  
    FROM CTE  
    ```  
  
     <span data-ttu-id="43e42-148">Esta consulta combina los resultados de varias instrucciones SELECT de [!INCLUDE[tsql](../includes/tsql-md.md)] dentro de una expresión de tabla común para especificar los valores que están basados en datos simplificados de la base de datos de ejemplo Contoso.</span><span class="sxs-lookup"><span data-stu-id="43e42-148">This query combines the results of several [!INCLUDE[tsql](../includes/tsql-md.md)] SELECT statements inside a common table expression to specify values that are based on simplified data from the Contoso sample database.</span></span> <span data-ttu-id="43e42-149">Los datos de ventas de Contoso representan los datos de ventas internacionales de bienes de consumo.</span><span class="sxs-lookup"><span data-stu-id="43e42-149">The Contoso sales data represents international sales data for consumer goods.</span></span> <span data-ttu-id="43e42-150">En este tutorial se utilizan los datos de ventas de cámaras.</span><span class="sxs-lookup"><span data-stu-id="43e42-150">This tutorial uses sales data for cameras.</span></span> <span data-ttu-id="43e42-151">Las subcategorías representan cámaras digitales, cámaras réflex digitales de una sola lente (SLR), cámaras de vídeo y accesorios.</span><span class="sxs-lookup"><span data-stu-id="43e42-151">The subcategories represent digital cameras, digital single lens reflex (SLR) cameras, camcorders, and accessories.</span></span>  
  
     <span data-ttu-id="43e42-152">La consulta especifica los nombres de columna que incluyen un identificador del almacén, una subcategoría de artículos de venta y la cantidad ordenada de los pedidos de ventas de tres almacenes.</span><span class="sxs-lookup"><span data-stu-id="43e42-152">The query specifies column names that include a store identifier, a sales item subcategory, and the quantity ordered for sales orders from three stores.</span></span> <span data-ttu-id="43e42-153">En esta consulta, el nombre del almacén no forma parte del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="43e42-153">In this query, the store name is not part of the result set.</span></span> <span data-ttu-id="43e42-154">Más adelante en este tutorial, buscará en otro conjunto de datos el nombre del almacén que corresponde al identificador del almacén.</span><span class="sxs-lookup"><span data-stu-id="43e42-154">Later in this tutorial, you will look up the name of the store that corresponds to the store identifier from a separate dataset.</span></span>  
  
     <span data-ttu-id="43e42-155">Esta consulta no contiene parámetros de consulta.</span><span class="sxs-lookup"><span data-stu-id="43e42-155">This query does not contain query parameters.</span></span> <span data-ttu-id="43e42-156">Agregará los parámetros de consulta posteriormente en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="43e42-156">You will add query parameters later in this tutorial.</span></span>  
  
11. <span data-ttu-id="43e42-157">En la barra de herramientas del diseñador de consultas, haga clic en **Ejecutar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="43e42-157">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="43e42-158">El conjunto de resultados muestra 11 filas de datos que muestran la cantidad de elementos vendidos para cada subcategoría de cuatro almacenes e incluye las columnas siguientes: StoreID, Subcategory, Quantity.</span><span class="sxs-lookup"><span data-stu-id="43e42-158">The result set displays 11 rows of data that show the quantity of items sold for each subcategory for four stores, and includes the following columns: StoreID, Subcategory, Quantity.</span></span>  
  
12. <span data-ttu-id="43e42-159">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="43e42-159">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-choose-layout-and-style-from-the-table-or-matrix-wizard"></a><a name="CompleteWizard"></a><span data-ttu-id="43e42-160">2. organizar datos, elegir el diseño y el estilo desde el Asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="43e42-160">2. Organize Data, Choose Layout, and Style from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="43e42-161">Utilice el asistente para proporcionar un diseño inicial en el que mostrar los datos.</span><span class="sxs-lookup"><span data-stu-id="43e42-161">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="43e42-162">El panel de vista previa del asistente le ayudará a visualizar el resultado de las agrupaciones de datos antes de completar la tabla o el diseño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="43e42-162">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the table or matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="43e42-163">Para organizar los datos en grupos</span><span class="sxs-lookup"><span data-stu-id="43e42-163">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="43e42-164">En la página **Organizar campos** , arrastre Subcategory a **Grupos de filas**.</span><span class="sxs-lookup"><span data-stu-id="43e42-164">On the **Arrange fields** page, drag Subcategory to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="43e42-165">Arrastre StoreID a **Grupos de columnas**.</span><span class="sxs-lookup"><span data-stu-id="43e42-165">Drag StoreID to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="43e42-166">Arrastre Quantity a **Valores**.</span><span class="sxs-lookup"><span data-stu-id="43e42-166">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="43e42-167">Ha organizado los valores de cantidad vendida en filas agrupadas por subcategoría.</span><span class="sxs-lookup"><span data-stu-id="43e42-167">You have organized the quantity sold values in rows grouped by subcategory.</span></span> <span data-ttu-id="43e42-168">Habrá una columna para cada almacén.</span><span class="sxs-lookup"><span data-stu-id="43e42-168">There will be one column for each store.</span></span>  
  
4.  <span data-ttu-id="43e42-169">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="43e42-169">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="43e42-170">En la página **elegir un diseño** , en **Opciones**, compruebe que esté seleccionada la opción **Mostrar subtotales y totales generales** .</span><span class="sxs-lookup"><span data-stu-id="43e42-170">On the **Choose a Layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="43e42-171">Al ejecutar el informe, la última columna mostrará la cantidad total de cada subcategoría para todos los almacenes y la última fila mostrará la cantidad total para todas las subcategorías de cada almacén.</span><span class="sxs-lookup"><span data-stu-id="43e42-171">When you run the report, the last column will show the total quantity of each subcategory for all stores, and the last row will show the total quantity for all subcategories for each store.</span></span>  
  
6.  <span data-ttu-id="43e42-172">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="43e42-172">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="43e42-173">En la página **elegir un estilo** , en el panel estilos, seleccione un estilo.</span><span class="sxs-lookup"><span data-stu-id="43e42-173">On the **Choose a Style** page, in the Styles pane, select a style.</span></span>  
  
8.  <span data-ttu-id="43e42-174">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="43e42-174">Click **Finish**.</span></span>  
  
     <span data-ttu-id="43e42-175">La matriz se agrega a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="43e42-175">The matrix is added to the design surface.</span></span> <span data-ttu-id="43e42-176">La matriz muestra tres columnas y tres filas.</span><span class="sxs-lookup"><span data-stu-id="43e42-176">The matrix displays three columns and three rows.</span></span> <span data-ttu-id="43e42-177">El contenido de las celdas de la primera fila es Subcategory, [StoreID] y Total.</span><span class="sxs-lookup"><span data-stu-id="43e42-177">The contents of the cells in the first row are Subcategory, [StoreID], and Total.</span></span> <span data-ttu-id="43e42-178">El contenido de las celdas de la segunda fila muestra expresiones que representan la subcategoría, la cantidad de artículos vendidos de cada almacén y el total de cada subcategoría de todos los almacenes.</span><span class="sxs-lookup"><span data-stu-id="43e42-178">The contents of the cells in the second row contain expressions that represent the subcategory, the quantity of items sold for each store, and the total quantity for each subcategory for all stores.</span></span> <span data-ttu-id="43e42-179">Las celdas de la última fila muestran los totales de cada almacén.</span><span class="sxs-lookup"><span data-stu-id="43e42-179">The cells in the final row display the grand total for each store.</span></span>  
  
9. <span data-ttu-id="43e42-180">Haga clic en la matriz, mantenga el mouse sobre el borde de la primera columna, agarre el controlador y expanda el ancho de la columna.</span><span class="sxs-lookup"><span data-stu-id="43e42-180">Click in the matrix, hover over the edge of the first column, grab the handle, and expand the column width.</span></span>  
  
10. <span data-ttu-id="43e42-181">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-181">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="43e42-182">El informe se ejecuta en el servidor de informes y muestra el título y la hora en que tuvo lugar el procesamiento del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-182">The report runs on the report server and displays the title and the time the report processing occurred.</span></span>  
  
 <span data-ttu-id="43e42-183">En esta situación, los encabezados de columna muestran el identificador del almacén, pero no su nombre.</span><span class="sxs-lookup"><span data-stu-id="43e42-183">In this scenario, the column headings display the store identifier but not the store name.</span></span> <span data-ttu-id="43e42-184">Más adelante agregará una expresión para buscar el nombre del almacén en un conjunto de datos que contiene pares identificador/nombre de almacén.</span><span class="sxs-lookup"><span data-stu-id="43e42-184">Later, you will add an expression to look up the store name in a dataset that contains store identifier/store name pairs.</span></span>  
  
##  <a name="3-add-a-query-parameter-to-create-a-report-parameter"></a><a name="Query"></a><span data-ttu-id="43e42-185">3. agregar un parámetro de consulta para crear un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="43e42-185">3. Add a Query Parameter to Create a Report Parameter</span></span>  
 <span data-ttu-id="43e42-186">Al agregar un parámetro de consulta a una consulta, el Generador de informes crea automáticamente un parámetro de informe de un solo valor con propiedades predeterminadas para el nombre, mensaje y tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="43e42-186">When you add a query parameter to a query, Report Builder automatically creates a single-valued report parameter with default properties for name, prompt, and data type.</span></span>  
  
#### <a name="to-add-a-query-parameter"></a><span data-ttu-id="43e42-187">Para agregar un parámetro de consulta</span><span class="sxs-lookup"><span data-stu-id="43e42-187">To add a query parameter</span></span>  
  
1.  <span data-ttu-id="43e42-188">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="43e42-188">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="43e42-189">En el panel Datos de informe, expanda la carpeta **Conjuntos de datos** , haga clic con el botón derecho en **DataSet1**y haga clic en **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="43e42-189">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
3.  <span data-ttu-id="43e42-190">Agregue la siguiente [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` cláusula como última línea de la consulta:</span><span class="sxs-lookup"><span data-stu-id="43e42-190">Add the following [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause as the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID = (@StoreID)  
    ```  
  
     <span data-ttu-id="43e42-191">La `WHERE` cláusula limita los datos recuperados al identificador del almacén especificado por el parámetro de consulta *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="43e42-191">The `WHERE` clause limits the retrieved data to the store identifier that is specified by the query parameter *@StoreID*.</span></span>  
  
4.  <span data-ttu-id="43e42-192">En la barra de herramientas del diseñador de consultas, haga clic en **Ejecutar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="43e42-192">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="43e42-193">Se abre el cuadro de diálogo **Definir parámetros de consulta** y se le pide un valor para el parámetro de consulta *@StoreID*.</span><span class="sxs-lookup"><span data-stu-id="43e42-193">The **Define Query Parameters** dialog box opens and prompts for a value for the query parameter *@StoreID*.</span></span>  
  
5.  <span data-ttu-id="43e42-194">En **Valor de parámetro**, escriba **200**.</span><span class="sxs-lookup"><span data-stu-id="43e42-194">In **Parameter Value**, type **200**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="43e42-195">El conjunto de resultados muestra las cantidades vendidas de accesorios, cámaras de vídeo y cámaras digitales SLR para el identificador de almacén **200**.</span><span class="sxs-lookup"><span data-stu-id="43e42-195">The result set displays the quantities sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="43e42-196">En el panel Datos de informe, expanda la carpeta **Parámetros** .</span><span class="sxs-lookup"><span data-stu-id="43e42-196">In the Report Data pane, expand the **Parameters** folder.</span></span>  
  
 <span data-ttu-id="43e42-197">Observe que ahora hay un parámetro de informe denominado *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="43e42-197">Notice that there is now a report parameter named *@StoreID*.</span></span> <span data-ttu-id="43e42-198">De forma predeterminada, el parámetro tiene el tipo de datos **Text**.</span><span class="sxs-lookup"><span data-stu-id="43e42-198">By default, the parameter has data type **Text**.</span></span> <span data-ttu-id="43e42-199">Como el identificador de almacén es un entero, va a cambiar el tipo de datos a Entero en el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="43e42-199">Because the store identifier is an integer, you will change the data type to Integer in the next procedure.</span></span>  
  
##  <a name="4-change-default-data-type-and-other-properties-for-a-report-parameter"></a><a name="ChangeDefaultProperties"></a><span data-ttu-id="43e42-200">4. cambiar el tipo de datos predeterminado y otras propiedades de un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="43e42-200">4. Change Default Data Type and Other Properties for a Report Parameter</span></span>  
 <span data-ttu-id="43e42-201">Después de crear un parámetro, puede ajustar los valores predeterminados de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="43e42-201">After a report parameter is created, you can adjust the default values for properties.</span></span>  
  
#### <a name="to-change-the-default-data-type-for-a-report-parameter"></a><span data-ttu-id="43e42-202">Para cambiar el tipo de datos predeterminado para un parámetro de informe</span><span class="sxs-lookup"><span data-stu-id="43e42-202">To change the default data type for a report parameter</span></span>  
  
1.  <span data-ttu-id="43e42-203">En el panel datos de informe bajo el nodo **parámetros** , haga clic con el botón secundario *@StoreID* y, a continuación, haga clic en **propiedades de parámetro**.</span><span class="sxs-lookup"><span data-stu-id="43e42-203">In the Report Data pane under the **Parameters** node, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="43e42-204">En prompt, escriba **¿identificador del almacén?**</span><span class="sxs-lookup"><span data-stu-id="43e42-204">In Prompt, type **Store identifier?**</span></span> <span data-ttu-id="43e42-205">Este texto aparece en la barra de herramientas del visor de informes al ejecutar el informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-205">This text appears on the report viewer toolbar when you run the report.</span></span>  
  
3.  <span data-ttu-id="43e42-206">En **Tipo de datos**, en la lista desplegable, seleccione **Entero**.</span><span class="sxs-lookup"><span data-stu-id="43e42-206">In **Data type**, from the drop-down list, select **Integer**.</span></span>  
  
4.  <span data-ttu-id="43e42-207">Acepte los valores predeterminados restantes del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="43e42-207">Accept the remaining default values in the dialog box.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="43e42-208">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-208">Preview the report.</span></span> <span data-ttu-id="43e42-209">El visor de informes muestra el mensaje para *@StoreID* .</span><span class="sxs-lookup"><span data-stu-id="43e42-209">The report viewer displays the prompt for *@StoreID*.</span></span>  
  
7.  <span data-ttu-id="43e42-210">En la barra de herramientas del visor de informes, al lado de Store ID, escriba **200**y, después, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="43e42-210">On the report viewer toolbar, next to Store ID, type **200**, and then click **View Report**.</span></span>  
  
##  <a name="4a-add-a-dataset-to-provide-available-values-and-display-names"></a><a name="AddDataset"></a><span data-ttu-id="43e42-211">4.</span><span class="sxs-lookup"><span data-stu-id="43e42-211">4a.</span></span> <span data-ttu-id="43e42-212">Agregar un conjunto de datos para proporcionar los valores disponibles y nombres para mostrar</span><span class="sxs-lookup"><span data-stu-id="43e42-212">Add a Dataset to Provide Available Values and Display Names</span></span>  
 <span data-ttu-id="43e42-213">Para asegurarse de que un usuario solo puede escribir valores válidos para un parámetro, puede crear una lista desplegable de valores entre los que elegir.</span><span class="sxs-lookup"><span data-stu-id="43e42-213">To ensure a user can type only valid values for a parameter, you can create a drop-down list of values to choose from.</span></span> <span data-ttu-id="43e42-214">Los valores pueden proceder de un conjunto de datos o de una lista que se especifique.</span><span class="sxs-lookup"><span data-stu-id="43e42-214">The values can come from a dataset or from a list that you specify.</span></span> <span data-ttu-id="43e42-215">Se deben proporcionar valores disponibles de un conjunto de datos que tenga una consulta que no contenga una referencia al parámetro.</span><span class="sxs-lookup"><span data-stu-id="43e42-215">Available values must be supplied from a dataset that has a query that does not contain a reference to the parameter.</span></span>  
  
#### <a name="to-create-a-dataset-for-valid-values-for-a-parameter"></a><span data-ttu-id="43e42-216">Para crear un conjunto de datos para los valores válidos de un parámetro</span><span class="sxs-lookup"><span data-stu-id="43e42-216">To create a dataset for valid values for a parameter</span></span>  
  
1.  <span data-ttu-id="43e42-217">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="43e42-217">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="43e42-218">En el panel Datos de informe, haga clic con el botón derecho en la carpeta **Conjuntos de datos** y, después, haga clic en **Agregar conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="43e42-218">In the Report Data pane, right-click the **Datasets** folder, and then click **Add Dataset**.</span></span>  
  
3.  <span data-ttu-id="43e42-219">En **Nombre**, escriba **Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="43e42-219">In **Name**, type **Stores**.</span></span>  
  
4.  <span data-ttu-id="43e42-220">Seleccione la opción **usar un conjunto de DataSet incrustado en mi informe** .</span><span class="sxs-lookup"><span data-stu-id="43e42-220">Select the **Use a dataset embedded in my report** option.</span></span>  
  
5.  <span data-ttu-id="43e42-221">En **origen de datos**, en la lista desplegable, elija el origen de datos que ha creado en el primer procedimiento.</span><span class="sxs-lookup"><span data-stu-id="43e42-221">In **Data source**, from the drop-down list, choose the data source you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="43e42-222">En **Tipo de consulta**, compruebe que la opción **Texto** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="43e42-222">In **Query type**, verify that **Text** is selected.</span></span>  
  
7.  <span data-ttu-id="43e42-223">En **Consulta**, pegue el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="43e42-223">In **Query**, paste the following text:</span></span>  
  
    ```  
    SELECT 200 AS StoreID, 'Contoso Catalog Store' as StoreName  
    UNION SELECT 199 AS StoreID, 'Contoso North America Online Store' as StoreName  
    UNION SELECT 307 AS StoreID, 'Contoso Asia Online Store' as StoreName  
    UNION SELECT 306 AS StoreID, 'Contoso Europe Online Store' as StoreName  
    ```  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="43e42-224">El panel Datos de informe muestra los campos StoreID y StoreName bajo el nodo de conjunto de datos **Almacenes** .</span><span class="sxs-lookup"><span data-stu-id="43e42-224">The Report Data pane displays the fields StoreID and StoreName under the **Stores** dataset node.</span></span>  
  
##  <a name="4b-specify-available-values-to-create-a-drop-down-list-of-values"></a><a name="AvailableValues"></a><span data-ttu-id="43e42-225">4B.</span><span class="sxs-lookup"><span data-stu-id="43e42-225">4b.</span></span> <span data-ttu-id="43e42-226">Especificar valores disponibles para crear una lista desplegable de valores</span><span class="sxs-lookup"><span data-stu-id="43e42-226">Specify Available Values to Create a Drop-down List of Values</span></span>  
 <span data-ttu-id="43e42-227">Después de crear un conjunto de datos para proporcionar los valores disponibles, debe cambiar las propiedades de informe para especificar qué conjunto de datos y qué campo utilizar para llenar la lista desplegable de valores válidos de la barra de herramientas del visor de informes.</span><span class="sxs-lookup"><span data-stu-id="43e42-227">After you create a dataset to provide available values, you must change the report properties to specify which dataset and which field to use to populate the drop-down list of valid values on the reportviewer toolbar.</span></span>  
  
#### <a name="to-provide-available-values-for-a-parameter-from-a-dataset"></a><span data-ttu-id="43e42-228">Para proporcionar los valores disponibles para un parámetro desde un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="43e42-228">To provide available values for a parameter from a dataset</span></span>  
  
1.  <span data-ttu-id="43e42-229">En el panel datos de informe, haga clic con el botón secundario en el parámetro *@StoreID* y, a continuación, haga clic en **propiedades de parámetro**.</span><span class="sxs-lookup"><span data-stu-id="43e42-229">In the Report Data pane, right-click the parameter *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
2.  <span data-ttu-id="43e42-230">Haga clic en **Valores disponibles**y luego haga clic en **Obtener valores de una consulta**.</span><span class="sxs-lookup"><span data-stu-id="43e42-230">Click **Available Values**, and then click **Get values from a query**.</span></span>  
  
3.  <span data-ttu-id="43e42-231">En **Conjunto de datos**, haga clic en **Almacenes**en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="43e42-231">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
4.  <span data-ttu-id="43e42-232">En **Campo de valor**, en la lista desplegable, haga clic en StoreID.</span><span class="sxs-lookup"><span data-stu-id="43e42-232">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
5.  <span data-ttu-id="43e42-233">En **Campo de etiqueta**, en la lista desplegable, haga clic en StoreName.</span><span class="sxs-lookup"><span data-stu-id="43e42-233">In **Label field**, from the drop-down list, click StoreName.</span></span> <span data-ttu-id="43e42-234">El campo de etiqueta especifica el nombre para mostrar del valor.</span><span class="sxs-lookup"><span data-stu-id="43e42-234">The label field specifies the display name for the value.</span></span>  
  
6.  <span data-ttu-id="43e42-235">Haga clic en **General**.</span><span class="sxs-lookup"><span data-stu-id="43e42-235">Click **General**.</span></span>  
  
7.  <span data-ttu-id="43e42-236">En prompt, escriba **¿nombre del almacén?**</span><span class="sxs-lookup"><span data-stu-id="43e42-236">In Prompt, type **Store name?**</span></span>  
  
     <span data-ttu-id="43e42-237">El usuario seleccionará ahora en una lista de nombres de almacén en lugar de entre los identificadores de almacén.</span><span class="sxs-lookup"><span data-stu-id="43e42-237">The user will now select from a list of store names instead of store identifiers.</span></span> <span data-ttu-id="43e42-238">Observe que el tipo de datos de parámetro sigue siendo **Entero** , porque el parámetro está basado en el identificador del almacén, no el nombre del almacén.</span><span class="sxs-lookup"><span data-stu-id="43e42-238">Note that the parameter data type remains **Integer** because the parameter is based on the store identifier, not the store name.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="43e42-239">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-239">Preview the report.</span></span>  
  
     <span data-ttu-id="43e42-240">En la barra de herramientas del visor de informes, el cuadro de texto del parámetro es ahora una lista desplegable que se muestra **\<Select a Value>** .</span><span class="sxs-lookup"><span data-stu-id="43e42-240">In the report viewer toolbar, the parameter text box is now a drop-down list that displays **\<Select a Value>**.</span></span>  
  
10. <span data-ttu-id="43e42-241">En la lista desplegable, seleccione almacén de catálogos de Contoso y, a continuación, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="43e42-241">From the drop-down list, select Contoso Catalog Store, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="43e42-242">El informe muestra la cantidad vendida de accesorios, cámaras de vídeo y cámaras digitales SLR para el identificador de almacén **200**.</span><span class="sxs-lookup"><span data-stu-id="43e42-242">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4c-specify-default-values-so-the-report-runs-automatically"></a><a name="DefaultValues"></a><span data-ttu-id="43e42-243">4C.</span><span class="sxs-lookup"><span data-stu-id="43e42-243">4c.</span></span> <span data-ttu-id="43e42-244">Especificar valores predeterminados para que el informe se ejecute automáticamente</span><span class="sxs-lookup"><span data-stu-id="43e42-244">Specify Default Values so the Report Runs Automatically</span></span>  
 <span data-ttu-id="43e42-245">Puede especificar un valor predeterminado para cada parámetro de modo que el informe se ejecute automáticamente.</span><span class="sxs-lookup"><span data-stu-id="43e42-245">You can specify a default value for each parameter so the report runs automatically.</span></span>  
  
#### <a name="to-specify-a-default-value-from-a-dataset"></a><span data-ttu-id="43e42-246">Para especificar un valor predeterminado de un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="43e42-246">To specify a default value from a dataset</span></span>  
  
1.  <span data-ttu-id="43e42-247">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="43e42-247">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="43e42-248">En el panel datos de informe, haga clic con el botón secundario *@StoreID* y, a continuación, haga clic en **propiedades de parámetro**.</span><span class="sxs-lookup"><span data-stu-id="43e42-248">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="43e42-249">Haga clic en **valores predeterminados**y, a continuación, en **obtener valores de una consulta**.</span><span class="sxs-lookup"><span data-stu-id="43e42-249">Click **Default Values**, and then click **Get values from a query**.</span></span>  
  
4.  <span data-ttu-id="43e42-250">En **Conjunto de datos**, haga clic en **Almacenes**en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="43e42-250">In **Dataset**, from the drop-down list, click **Stores**.</span></span>  
  
5.  <span data-ttu-id="43e42-251">En **Campo de valor**, en la lista desplegable, haga clic en StoreID.</span><span class="sxs-lookup"><span data-stu-id="43e42-251">In **Value field**, from the drop-down list, click StoreID.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="43e42-252">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-252">Preview the report.</span></span>  
  
 <span data-ttu-id="43e42-253">En *@StoreID* el caso de, el visor de informes muestra el valor "Contoso Norteamérica Online Store".</span><span class="sxs-lookup"><span data-stu-id="43e42-253">For *@StoreID*, the report viewer displays the value "Contoso North America Online Store".</span></span> <span data-ttu-id="43e42-254">Este es el primer valor del conjunto de resultados para los **almacenes**de conjuntos de DataSet.</span><span class="sxs-lookup"><span data-stu-id="43e42-254">This is the first value from the result set for the dataset **Stores**.</span></span> <span data-ttu-id="43e42-255">El informe muestra la cantidad vendida de cámaras digitales para el identificador del almacén **199**.</span><span class="sxs-lookup"><span data-stu-id="43e42-255">The report displays the quantity sold for Digital Cameras for store identifier **199**.</span></span>  
  
#### <a name="to-specify-a-custom-default-value"></a><span data-ttu-id="43e42-256">Para especificar un valor predeterminado personalizado</span><span class="sxs-lookup"><span data-stu-id="43e42-256">To specify a custom default value</span></span>  
  
1.  <span data-ttu-id="43e42-257">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="43e42-257">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="43e42-258">En el panel datos de informe, haga clic con el botón secundario *@StoreID* y, a continuación, haga clic en **propiedades de parámetro**.</span><span class="sxs-lookup"><span data-stu-id="43e42-258">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="43e42-259">Haga clic en **valores predeterminados**, haga clic en **especificar valores**y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="43e42-259">Click **Default Values**, and click **Specify values**, and then click **Add**.</span></span> <span data-ttu-id="43e42-260">Se agrega una nueva fila de valor.</span><span class="sxs-lookup"><span data-stu-id="43e42-260">A new value row is added.</span></span>  
  
4.  <span data-ttu-id="43e42-261">En **Valor**, escriba **200**.</span><span class="sxs-lookup"><span data-stu-id="43e42-261">In **Value**, type **200**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="43e42-262">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-262">Preview the report.</span></span>  
  
 <span data-ttu-id="43e42-263">Para *@StoreID* , el visor de informes muestra el valor "Contoso Catalog Store".</span><span class="sxs-lookup"><span data-stu-id="43e42-263">For *@StoreID*, the report viewer displays the value "Contoso Catalog Store".</span></span> <span data-ttu-id="43e42-264">Este es el nombre para mostrar del identificador de almacén **200**.</span><span class="sxs-lookup"><span data-stu-id="43e42-264">This is the display name for store identifier **200**.</span></span> <span data-ttu-id="43e42-265">El informe muestra la cantidad vendida de accesorios, cámaras de vídeo y cámaras digitales SLR para el identificador de almacén **200**.</span><span class="sxs-lookup"><span data-stu-id="43e42-265">The report displays the quantity sold for Accessories, Camcorders, and Digital SLR Cameras for the store identifier **200**.</span></span>  
  
##  <a name="4d-look-up-a-value-from-a-dataset-that-has-namevalue-pairs"></a><a name="NameValue"></a><span data-ttu-id="43e42-266">4D.</span><span class="sxs-lookup"><span data-stu-id="43e42-266">4d.</span></span> <span data-ttu-id="43e42-267">Buscar un valor de un conjunto de datos que tiene pares de name y valor</span><span class="sxs-lookup"><span data-stu-id="43e42-267">Look up a Value from a Dataset that has Name/Value Pairs</span></span>  
 <span data-ttu-id="43e42-268">Un conjunto de datos podría contener el identificador y el campo de nombre correspondiente.</span><span class="sxs-lookup"><span data-stu-id="43e42-268">A dataset might contain both the identifier and the corresponding name field.</span></span> <span data-ttu-id="43e42-269">Si solo tiene un identificador, puede buscar el nombre correspondiente en un conjunto de datos que haya creado y que tenga pares de nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="43e42-269">When you only have an identifier, you can look up the corresponding name in a dataset that you created that includes name/value pairs.</span></span>  
  
#### <a name="to-look-up-a-value-from-a-dataset"></a><span data-ttu-id="43e42-270">Para buscar un valor de un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="43e42-270">To look up a value from a dataset</span></span>  
  
1.  <span data-ttu-id="43e42-271">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="43e42-271">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="43e42-272">En la superficie de diseño, en la matriz, en el encabezado de columna de la primera fila, haga clic con el botón derecho en `[StoreID]` y, después, haga clic en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="43e42-272">On the design surface, in the matrix, in the first row column header, right-click `[StoreID]` and then click **Expression**.</span></span>  
  
3.  <span data-ttu-id="43e42-273">En el panel de expresión, elimine todo el texto excepto el `equals` (=) inicial.</span><span class="sxs-lookup"><span data-stu-id="43e42-273">In the expression pane, delete all text except the beginning `equals` (=).</span></span>  
  
4.  <span data-ttu-id="43e42-274">En **Categoría**, expanda **Funciones comunes**y haga clic en **Varios**.</span><span class="sxs-lookup"><span data-stu-id="43e42-274">In **Category**, expand **Common Functions**, and click **Miscellaneous**.</span></span> <span data-ttu-id="43e42-275">El panel de elementos muestra un conjunto de funciones.</span><span class="sxs-lookup"><span data-stu-id="43e42-275">The Item pane displays a set of functions.</span></span>  
  
5.  <span data-ttu-id="43e42-276">En Elemento, haga doble clic en **Búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="43e42-276">In Item, double-click **Lookup**.</span></span> <span data-ttu-id="43e42-277">En el panel de expresión se muestra `=Lookup(`.</span><span class="sxs-lookup"><span data-stu-id="43e42-277">The expression pane displays `=Lookup(`.</span></span> <span data-ttu-id="43e42-278">En el panel de ejemplo se muestra un ejemplo de sintaxis de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="43e42-278">The Example pane displays an example of Lookup syntax.</span></span>  
  
6.  <span data-ttu-id="43e42-279">Escriba la siguiente expresión: `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span><span class="sxs-lookup"><span data-stu-id="43e42-279">Type the following expression: `=Lookup(Fields!StoreID.Value,Fields!StoreID.Value,Fields!StoreName.Value,"Stores")`</span></span>  
  
     <span data-ttu-id="43e42-280">La función de búsqueda toma el valor de StoreID, lo busca en el conjunto de datos "Almacenes" y devuelve el valor de StoreName.</span><span class="sxs-lookup"><span data-stu-id="43e42-280">The Lookup function takes the value for StoreID, looks it up in the "Stores" dataset, and returns the StoreName value.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="43e42-281">El encabezado de columna del almacén contiene el texto para mostrar de una expresión compleja: **<\<Expr>>** .</span><span class="sxs-lookup"><span data-stu-id="43e42-281">The store column header contains the display text for a complex expression: **<\<Expr>>**.</span></span>  
  
8.  <span data-ttu-id="43e42-282">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-282">Preview the report.</span></span>  
  
 <span data-ttu-id="43e42-283">El cuadro de texto de la parte superior de cada página muestra el nombre del almacén en lugar del identificador del almacén.</span><span class="sxs-lookup"><span data-stu-id="43e42-283">The text box at the top of each page displays the store name instead of the store identifier.</span></span>  
  
##  <a name="5-display-the-selected-parameter-value-in-the-report"></a><a name="Expression"></a><span data-ttu-id="43e42-284">5. Mostrar el valor de parámetro seleccionado en el informe</span><span class="sxs-lookup"><span data-stu-id="43e42-284">5. Display the Selected Parameter Value in the Report</span></span>  
 <span data-ttu-id="43e42-285">Cuando los usuarios tienen preguntas sobre un informe, resulta útil saber qué valores de parámetro eligieron.</span><span class="sxs-lookup"><span data-stu-id="43e42-285">When a user has questions about a report, it helps to know which parameter values they chose.</span></span> <span data-ttu-id="43e42-286">Puede conservar los valores seleccionados por el usuario para cada parámetro del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-286">You can preserve user-selected values for each parameter in the report.</span></span> <span data-ttu-id="43e42-287">Una forma de hacerlo es mostrar los parámetros en un cuadro de texto en el pie de página.</span><span class="sxs-lookup"><span data-stu-id="43e42-287">One way is to display the parameters in a text box in the page footer.</span></span>  
  
#### <a name="to-display-the-selected-parameter-value-and-label-on-a-page-footer"></a><span data-ttu-id="43e42-288">Para mostrar el valor del parámetro seleccionado y etiquetarlo en un pie de página</span><span class="sxs-lookup"><span data-stu-id="43e42-288">To display the selected parameter value and label on a page footer</span></span>  
  
1.  <span data-ttu-id="43e42-289">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="43e42-289">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="43e42-290">Haga clic con el botón secundario en el pie de página, seleccione **Insertar**y, a continuación, haga clic en **cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="43e42-290">Right-click the page footer, point to **Insert**, and then click **Text Box**.</span></span> <span data-ttu-id="43e42-291">Arrastre el cuadro de texto junto al cuadro de texto que tiene la marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="43e42-291">Drag the text box next to the text box with the time stamp.</span></span> <span data-ttu-id="43e42-292">Agarre el controlador lateral del cuadro de texto y expanda el ancho.</span><span class="sxs-lookup"><span data-stu-id="43e42-292">Grab the side handle of the text box and expand the width.</span></span>  
  
3.  <span data-ttu-id="43e42-293">En el panel datos de informe, arrastre el parámetro *@StoreID* al cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="43e42-293">From the Report Data pane, drag the parameter *@StoreID* to the text box.</span></span> <span data-ttu-id="43e42-294">El cuadro de texto presenta `[@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="43e42-294">The text box displays `[@StoreID]`.</span></span>  
  
4.  <span data-ttu-id="43e42-295">Para mostrar la etiqueta de parámetro, haga clic en el cuadro de texto hasta que el cursor de inserción aparezca después de la expresión existente, escriba un espacio y, a continuación, arrastre otra copia del parámetro en el panel Datos de informe al cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="43e42-295">To display the parameter label, click in the text box until the insert cursor appears after the existing expression, type a space, and then drag another copy of the parameter from the Report Data pane to the text box.</span></span> <span data-ttu-id="43e42-296">El cuadro de texto presenta `[@StoreID] [@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="43e42-296">The text box displays `[@StoreID] [@StoreID]`.</span></span>  
  
5.  <span data-ttu-id="43e42-297">Haga clic con el botón secundario en la primera expresión y haga clic en **expresión**.</span><span class="sxs-lookup"><span data-stu-id="43e42-297">Right-click the first expression and click **Expression**.</span></span> <span data-ttu-id="43e42-298">Se abre el cuadro de diálogo **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="43e42-298">The **Expression** dialog box opens.</span></span> <span data-ttu-id="43e42-299">Reemplace el texto `Value` con `Label`.</span><span class="sxs-lookup"><span data-stu-id="43e42-299">Replace the text `Value` by `Label`.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="43e42-300">El texto indica: `[@StoreID.Label] [@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="43e42-300">The text displays: `[@StoreID.Label] [@StoreID]`.</span></span>  
  
7.  <span data-ttu-id="43e42-301">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-301">Preview the report.</span></span>  
  
##  <a name="6-use-the-report-parameter-in-a-filter"></a><a name="Filter"></a><span data-ttu-id="43e42-302">6. usar el parámetro de informe en un filtro</span><span class="sxs-lookup"><span data-stu-id="43e42-302">6. Use the Report Parameter in a Filter</span></span>  
 <span data-ttu-id="43e42-303">Los filtros ayudan a controlar qué datos se deben usar en un informe una vez que se han recuperado de un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="43e42-303">Filters help control which data to use in a report after it is retrieved from an external data source.</span></span> <span data-ttu-id="43e42-304">Para permitir que un usuario controle los datos que desea ver, puede incluir el parámetro de informe en un filtro para la matriz.</span><span class="sxs-lookup"><span data-stu-id="43e42-304">To let a user help control the data they want to see, you can include the report parameter in a filter for the matrix.</span></span>  
  
#### <a name="to-specify-a-parameter-in-a-matrix-filter"></a><span data-ttu-id="43e42-305">Para especificar un parámetro en un filtro de la matriz</span><span class="sxs-lookup"><span data-stu-id="43e42-305">To specify a parameter in a matrix filter</span></span>  
  
1.  <span data-ttu-id="43e42-306">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="43e42-306">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="43e42-307">Haga clic con el botón derecho en una fila o identificador del encabezado de columna de la matriz y, después, haga clic en **Propiedades de Tablix**.</span><span class="sxs-lookup"><span data-stu-id="43e42-307">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="43e42-308">Haga clic en **Filtros**y luego en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="43e42-308">Click **Filters**, and then click **Add**.</span></span> <span data-ttu-id="43e42-309">Aparece una nueva fila de filtro.</span><span class="sxs-lookup"><span data-stu-id="43e42-309">A new filter row appears.</span></span>  
  
4.  <span data-ttu-id="43e42-310">En **Expresión**, en la lista desplegable, seleccione el StoreId del campo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="43e42-310">In **Expression**, from the drop-down list, select the dataset field StoreID.</span></span> <span data-ttu-id="43e42-311">El tipo de datos indica **Entero**.</span><span class="sxs-lookup"><span data-stu-id="43e42-311">The data type displays **Integer**.</span></span> <span data-ttu-id="43e42-312">Cuando el valor de expresión es un campo de un conjunto de datos, el tipo de datos se establece automáticamente.</span><span class="sxs-lookup"><span data-stu-id="43e42-312">When the expression value is a dataset field, the data type is set automatically.</span></span>  
  
5.  <span data-ttu-id="43e42-313">En **operador**, compruebe que `equals` (=) está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="43e42-313">In **Operator**, verify that `equals` (=) is selected.</span></span>  
  
6.  <span data-ttu-id="43e42-314">En **Valor**, escriba `[@StoreID]`.</span><span class="sxs-lookup"><span data-stu-id="43e42-314">In **Value**, type `[@StoreID]`.</span></span> <span data-ttu-id="43e42-315">`[@StoreID]` es la sintaxis de expresión simple que representa `=Parameters!StoreID.Value`.</span><span class="sxs-lookup"><span data-stu-id="43e42-315">`[@StoreID]` is the simple expression syntax that represents `=Parameters!StoreID.Value`.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="43e42-316">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-316">Preview the report.</span></span>  
  
     <span data-ttu-id="43e42-317">La matriz solo muestra los datos de "Contoso Catalog Store".</span><span class="sxs-lookup"><span data-stu-id="43e42-317">The matrix displays data only for "Contoso Catalog Store".</span></span>  
  
9. <span data-ttu-id="43e42-318">En la barra de herramientas del visor de informes, para **¿Nombre del almacén?**, seleccione **Contoso Asia Online Store**y, después, haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="43e42-318">On the report viewer toolbar, for **Store name?**, select **Contoso Asia Online Store**, and then click **View Report**.</span></span>  
  
 <span data-ttu-id="43e42-319">La matriz muestra los datos correspondientes al almacén que había seleccionado.</span><span class="sxs-lookup"><span data-stu-id="43e42-319">The matrix displays data that corresponds to the store that you selected.</span></span>  
  
##  <a name="7-change-the-report-parameter-to-accept-multiple-values"></a><a name="Multivalued"></a><span data-ttu-id="43e42-320">7. cambiar el parámetro de informe para que acepte varios valores</span><span class="sxs-lookup"><span data-stu-id="43e42-320">7. Change the Report Parameter to Accept Multiple Values</span></span>  
 <span data-ttu-id="43e42-321">Para cambiar un parámetro de un solo valor a varios valores, debe cambiar la consulta y todas las expresiones que contienen una referencia al parámetro, incluidos los filtros.</span><span class="sxs-lookup"><span data-stu-id="43e42-321">To change a parameter from single to multivalued, you must change the query, and all expressions that contain a reference to the parameter, including filters.</span></span> <span data-ttu-id="43e42-322">Un parámetro de varios valores es una matriz de valores.</span><span class="sxs-lookup"><span data-stu-id="43e42-322">A multivalued parameter is an array of values.</span></span> <span data-ttu-id="43e42-323">En una consulta de conjunto de datos, la sintaxis de la consulta debe comprobar la inclusión de un valor en un conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="43e42-323">In a dataset query, query syntax must test for inclusion of one value in a set of values.</span></span> <span data-ttu-id="43e42-324">En una expresión de informe, la sintaxis de la expresión debe tener acceso a una matriz de valores y no a un valor individual.</span><span class="sxs-lookup"><span data-stu-id="43e42-324">In a report expression, expression syntax must access an array of values instead of an individual value.</span></span>  
  
#### <a name="to-change-a-parameter-from-single-to-multivalued"></a><span data-ttu-id="43e42-325">Para cambiar un parámetro de un solo valor a varios valores</span><span class="sxs-lookup"><span data-stu-id="43e42-325">To change a parameter from single to multivalued</span></span>  
  
1.  <span data-ttu-id="43e42-326">Cambie a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="43e42-326">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="43e42-327">En el panel datos de informe, haga clic con el botón secundario *@StoreID* y, a continuación, haga clic en **propiedades de parámetro**.</span><span class="sxs-lookup"><span data-stu-id="43e42-327">In the Report Data pane, right-click *@StoreID*, and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="43e42-328">Seleccione **Permitir varios valores**.</span><span class="sxs-lookup"><span data-stu-id="43e42-328">Select **Allow multiple values**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="43e42-329">En el panel Datos de informe, expanda la carpeta **Conjuntos de datos** , haga clic con el botón derecho en **DataSet1**y haga clic en **Consulta**.</span><span class="sxs-lookup"><span data-stu-id="43e42-329">In the Report Data pane, expand the **Datasets** folder, right-click **DataSet1**, and then click **Query**.</span></span>  
  
6.  <span data-ttu-id="43e42-330">Cambie `equals` (=) a `IN` en la [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` cláusula en la última línea de la consulta:</span><span class="sxs-lookup"><span data-stu-id="43e42-330">Change `equals` (=) to `IN` in the [!INCLUDE[tsql](../includes/tsql-md.md)] `WHERE` clause in the last line in the query:</span></span>  
  
    ```  
    WHERE StoreID IN (@StoreID)  
    ```  
  
     <span data-ttu-id="43e42-331">El operador `IN` prueba un valor para su inclusión en un conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="43e42-331">The `IN` operator tests a value for inclusion in a set of values.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="43e42-332">Haga clic con el botón derecho en una fila o identificador del encabezado de columna de la matriz y, después, haga clic en **Propiedades de Tablix**.</span><span class="sxs-lookup"><span data-stu-id="43e42-332">Right-click a row or column header handle on the matrix, and then click **Tablix Properties**.</span></span>  
  
9. <span data-ttu-id="43e42-333">Haga clic en **Filtros**.</span><span class="sxs-lookup"><span data-stu-id="43e42-333">Click **Filters**.</span></span>  
  
10. <span data-ttu-id="43e42-334">En **Operador**, seleccione **In**.</span><span class="sxs-lookup"><span data-stu-id="43e42-334">In **Operator**, select **In**.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="43e42-335">En el cuadro de texto que muestra el parámetro en el pie de página, elimine todo el texto.</span><span class="sxs-lookup"><span data-stu-id="43e42-335">In the text box that displays the parameter in the page footer, delete all text.</span></span>  
  
13. <span data-ttu-id="43e42-336">Haga clic con el botón derecho en el cuadro y, después, haga clic en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="43e42-336">Right-click the text box, and then click **Expression**.</span></span> <span data-ttu-id="43e42-337">Escriba la siguiente expresión: `=Join(Parameters!StoreID.Label, ", ")`</span><span class="sxs-lookup"><span data-stu-id="43e42-337">Type the following expression: `=Join(Parameters!StoreID.Label, ", ")`</span></span>  
  
     <span data-ttu-id="43e42-338">Esta expresión concatena todos los nombres de almacén seleccionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="43e42-338">This expression concatenates all store names that the user selected.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
15. <span data-ttu-id="43e42-339">Haga clic en el cuadro de texto que hay delante de la expresión que acaba de crear y, a continuación, escriba lo siguiente: Parameter Values Selected:.</span><span class="sxs-lookup"><span data-stu-id="43e42-339">Click in the text box in front of the expression that you just created, and then type the following: Parameter Values Selected:.</span></span>  
  
16. <span data-ttu-id="43e42-340">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-340">Preview the report.</span></span>  
  
17. <span data-ttu-id="43e42-341">Haga clic en la lista desplegable al lado de ¿Nombre del almacén?</span><span class="sxs-lookup"><span data-stu-id="43e42-341">Click the drop-down list next to Store Name?</span></span>  
  
     <span data-ttu-id="43e42-342">Cada valor válido aparece al lado de una casilla.</span><span class="sxs-lookup"><span data-stu-id="43e42-342">Each valid value appears next to a check box.</span></span>  
  
18. <span data-ttu-id="43e42-343">Haga clic en **Seleccionar todo**y, después, en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="43e42-343">Click **Select All**, and then click **View Report**.</span></span>  
  
     <span data-ttu-id="43e42-344">El informe muestra la cantidad vendida para todas las subcategorías en todos los almacenes.</span><span class="sxs-lookup"><span data-stu-id="43e42-344">The report displays the quantity sold for all subcategories for all stores.</span></span>  
  
19. <span data-ttu-id="43e42-345">En la lista desplegable, haga clic en **Seleccionar todo** para borrar la lista, haga clic en "Contoso Catalog Store" y en "Contoso Asia Online Store" y luego haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="43e42-345">From the drop-down list, click **Select All** to clear the list, click "Contoso Catalog Store" and "Contoso Asia Online Store", and then click **View Report**.</span></span>  
  
##  <a name="8-add-a-boolean-parameter-for-conditional-visibility"></a><a name="Boolean"></a><span data-ttu-id="43e42-346">8. agregar un parámetro booleano para la visibilidad condicional</span><span class="sxs-lookup"><span data-stu-id="43e42-346">8. Add a Boolean Parameter for Conditional Visibility</span></span>  
  
#### <a name="to-add-a-boolean-parameter"></a><span data-ttu-id="43e42-347">Para agregar un parámetro booleano</span><span class="sxs-lookup"><span data-stu-id="43e42-347">To add a boolean parameter</span></span>  
  
1.  <span data-ttu-id="43e42-348">En la superficie de diseño, en el panel Datos de informe, haga clic con el botón derecho en **Parámetros**y haga clic en **Agregar parámetro**.</span><span class="sxs-lookup"><span data-stu-id="43e42-348">On the design surface, in the Report Data pane, right-click **Parameters**, and click **Add Parameter**.</span></span>  
  
2.  <span data-ttu-id="43e42-349">En **Nombre**, escriba ShowSelections.</span><span class="sxs-lookup"><span data-stu-id="43e42-349">In **Name**, type ShowSelections.</span></span>  
  
3.  <span data-ttu-id="43e42-350">En **Pedir datos**, escriba ¿Mostrar selecciones?</span><span class="sxs-lookup"><span data-stu-id="43e42-350">In **Prompt**, type Show selections?</span></span>  
  
4.  <span data-ttu-id="43e42-351">En **tipo de datos**, en la lista desplegable, haga clic en **booleano**.</span><span class="sxs-lookup"><span data-stu-id="43e42-351">In **Data type**, from the drop-down list, click **Boolean**.</span></span>  
  
5.  <span data-ttu-id="43e42-352">Haga clic en **Valores predeterminados**.</span><span class="sxs-lookup"><span data-stu-id="43e42-352">Click **Default Values**.</span></span>  
  
6.  <span data-ttu-id="43e42-353">Haga clic en **Especificar valor**y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="43e42-353">Click **Specify value**, and then click **Add**.</span></span>  
  
7.  <span data-ttu-id="43e42-354">En **Valor**, escriba **False**.</span><span class="sxs-lookup"><span data-stu-id="43e42-354">In **Value**, type **False**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-set-visibility-based-on-a-boolean-parameter"></a><span data-ttu-id="43e42-355">Para establecer la visibilidad en función de un parámetro booleano</span><span class="sxs-lookup"><span data-stu-id="43e42-355">To set visibility based on a boolean parameter</span></span>  
  
1.  <span data-ttu-id="43e42-356">En la superficie de diseño, haga clic con el botón derecho en el cuadro de texto del pie de página que muestra los valores de parámetro y luego haga clic en **Propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="43e42-356">On the design surface, right-click the text box in the page footer that displays the parameter values, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="43e42-357">Haga clic en **Visibilidad**.</span><span class="sxs-lookup"><span data-stu-id="43e42-357">Click **Visibility**.</span></span>  
  
3.  <span data-ttu-id="43e42-358">Seleccione la opción **Mostrar u ocultar en función de una expresión**y, después, haga clic en el botón de expresión **Fx**.</span><span class="sxs-lookup"><span data-stu-id="43e42-358">Select the option **Show or hide based on an expression**, and then click the expression button **Fx**.</span></span>  
  
4.  <span data-ttu-id="43e42-359">Escriba la siguiente expresión: `=Not Parameters!ShowSelections.Value`</span><span class="sxs-lookup"><span data-stu-id="43e42-359">Type the following expression: `=Not Parameters!ShowSelections.Value`</span></span>  
  
     <span data-ttu-id="43e42-360">La propiedad Hidden controla la opción Visibilidad del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="43e42-360">The text box Visibility option is controlled by the property Hidden.</span></span> <span data-ttu-id="43e42-361">Aplique el operador `Not` para que cuando el parámetro esté seleccionado, la propiedad Hidden sea falsa y, así, se mostrará el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="43e42-361">Apply the `Not` operator so that when the parameter is selected, the Hidden property is false, and the text box will be displayed.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="43e42-362">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-362">Preview the report.</span></span>  
  
     <span data-ttu-id="43e42-363">El cuadro de texto que muestra las opciones de parámetro no aparece.</span><span class="sxs-lookup"><span data-stu-id="43e42-363">The text box that displays the parameter choices does not appear.</span></span>  
  
8.  <span data-ttu-id="43e42-364">En la barra de herramientas del visor de informes, al lado de **Mostrar selecciones**, haga clic en `True` .</span><span class="sxs-lookup"><span data-stu-id="43e42-364">In the report viewer toolbar, next to **Show selections**, click `True`.</span></span>  
  
9. <span data-ttu-id="43e42-365">Obtenga una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-365">Preview the report.</span></span>  
  
 <span data-ttu-id="43e42-366">El cuadro de texto del pie de página muestra todos los nombres de almacén que haya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="43e42-366">The text box in the page footer displays all the store names that you selected.</span></span>  
  
##  <a name="9-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="43e42-367">9. agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="43e42-367">9. Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="43e42-368">Para agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="43e42-368">To add a report title</span></span>  
  
1.  <span data-ttu-id="43e42-369">En la superficie de diseño, haga clic en **Haga clic para agregar título**.</span><span class="sxs-lookup"><span data-stu-id="43e42-369">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="43e42-370">Escriba Parameterized Product Sales y, a continuación, haga clic fuera del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="43e42-370">Type Parameterized Product Sales, and then click outside the text box.</span></span>  
  
##  <a name="10-save-the-report"></a><a name="Save"></a><span data-ttu-id="43e42-371">10. guardar el informe</span><span class="sxs-lookup"><span data-stu-id="43e42-371">10. Save the Report</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="43e42-372">Para guardar el informe en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="43e42-372">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="43e42-373">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="43e42-373">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="43e42-374">Haga clic en **Sitios y servidores recientes**.</span><span class="sxs-lookup"><span data-stu-id="43e42-374">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="43e42-375">Seleccione o escriba el nombre del servidor de informes donde tiene el permiso para guardar los informes.</span><span class="sxs-lookup"><span data-stu-id="43e42-375">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="43e42-376">Aparece el mensaje **Conectándose al servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="43e42-376">The message **Connecting to report server appears**.</span></span> <span data-ttu-id="43e42-377">Una vez completada la conexión, se mostrará el contenido de la carpeta de informes que el administrador del servidor de informes especificó como ubicación predeterminada para los informes.</span><span class="sxs-lookup"><span data-stu-id="43e42-377">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="43e42-378">En **Nombre**, reemplace el nombre predeterminado por Ventas de productos con parámetros.</span><span class="sxs-lookup"><span data-stu-id="43e42-378">In **Name**, replace the default name with Parameterized Sales Report.</span></span>  
  
5.  <span data-ttu-id="43e42-379">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="43e42-379">Click **Save**.</span></span>  
  
 <span data-ttu-id="43e42-380">El informe se guarda en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="43e42-380">The report is saved to the report server.</span></span> <span data-ttu-id="43e42-381">El servidor de informes al que está conectado aparece en la barra de estado en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="43e42-381">The report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="43e42-382">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="43e42-382">Next Steps</span></span>  
 <span data-ttu-id="43e42-383">De esta forma se concluye el tutorial sobre cómo agregar un parámetro a un informe.</span><span class="sxs-lookup"><span data-stu-id="43e42-383">This concludes the walkthrough for how to add a parameter to your report.</span></span> <span data-ttu-id="43e42-384">Para obtener más información sobre los parámetros, consulte [Parámetros de informe &#40;Generador de informes y Diseñador de informes&#41;](report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="43e42-384">To learn more about parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e42-385">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43e42-385">See Also</span></span>  
 <span data-ttu-id="43e42-386">[Tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="43e42-386">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="43e42-387">Generador de informes en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="43e42-387">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
