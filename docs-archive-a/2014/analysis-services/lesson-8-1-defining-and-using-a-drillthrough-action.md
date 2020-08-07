---
title: Definir y utilizar una acción de obtención de detalles | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 3765f865-2b93-44be-b290-28e3815d5ecb
author: minewiskan
ms.author: owend
ms.openlocfilehash: ea19a9721d87936bc88b5401c71ee550a47bc1ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745470"
---
# <a name="defining-and-using-a-drillthrough-action"></a><span data-ttu-id="d8ed3-102">Definir y utilizar una acción de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="d8ed3-102">Defining and Using a Drillthrough Action</span></span>
  <span data-ttu-id="d8ed3-103">El dimensionamiento de datos de hecho mediante una dimensión de hecho sin filtrar correctamente los datos devueltos por la consulta puede producir un rendimiento lento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-103">Dimensioning fact data by a fact dimension without correctly filtering the data that the query returns can cause slow query performance.</span></span> <span data-ttu-id="d8ed3-104">Para evitarlo, puede definir una acción de obtención de detalles que restrinja el número total de filas que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-104">To avoid this, you can define a drillthrough action that restricts the total number of rows that are returned.</span></span> <span data-ttu-id="d8ed3-105">Esto mejorará significativamente el rendimiento de las consultas.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-105">This will significantly improve query performance.</span></span>  
  
 <span data-ttu-id="d8ed3-106">En las tareas de este tema, definirá una acción de obtención de detalles para devolver información detallada de pedidos para las ventas a clientes a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-106">In the tasks in this topic, you define a drillthrough action to return order detail information for sales to customers over the Internet.</span></span>  
  
## <a name="defining-the-drillthrough-action-properties"></a><span data-ttu-id="d8ed3-107">Definir las propiedades de la acción de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="d8ed3-107">Defining the Drillthrough Action Properties</span></span>  
  
1.  <span data-ttu-id="d8ed3-108">En el Diseñador de cubos del cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , haga clic en la pestaña **Acciones** .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-108">In Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, click the **Actions** tab.</span></span>  
  
     <span data-ttu-id="d8ed3-109">La pestaña **Acciones** incluye varios paneles.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-109">The **Actions** tab includes several panes.</span></span> <span data-ttu-id="d8ed3-110">En la parte izquierda de la pestaña están el panel **Organizador de acciones** y el panel **Herramientas de cálculo** .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-110">On the left side of the tab are the **Action Organizer** pane and the **Calculation Tools** pane.</span></span> <span data-ttu-id="d8ed3-111">El panel situado a la derecha de los dos paneles es el panel **Mostrar** , que contiene los detalles de la acción que está seleccionada en el panel **Organizador de acciones** .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-111">The pane to the right of these two panes is the **Display** pane, which contains the details of the action that is selected in the **Action Organizer** pane.</span></span>  
  
     <span data-ttu-id="d8ed3-112">La siguiente imagen muestra la pestaña **Acciones** del Diseñador de cubos.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-112">The following image shows the **Actions** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="d8ed3-113">![Pestaña Acciones del Diseñador de cubos](../../2014/tutorials/media/l8-action1.gif "Pestaña Acciones del Diseñador de cubos")</span><span class="sxs-lookup"><span data-stu-id="d8ed3-113">![Actions tab of Cube Designer](../../2014/tutorials/media/l8-action1.gif "Actions tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="d8ed3-114">En la barra de herramientas de la pestaña **Acciones** , haga clic en el botón **Nueva acción de obtención de detalles** .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-114">On the toolbar of the **Actions** tab, click the **New Drillthrough Action** button.</span></span>  
  
     <span data-ttu-id="d8ed3-115">Aparecerá una plantilla de Acción en blanco en el panel de información.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-115">A blank action template appears in the display pane.</span></span>  
  
     <span data-ttu-id="d8ed3-116">![Plantilla Acción en blanco en el panel de visualización](../../2014/tutorials/media/l8-action2.gif "Plantilla Acción en blanco en el panel de visualización")</span><span class="sxs-lookup"><span data-stu-id="d8ed3-116">![Blank Action template in the display pane](../../2014/tutorials/media/l8-action2.gif "Blank Action template in the display pane")</span></span>  
  
3.  <span data-ttu-id="d8ed3-117">En el cuadro **nombre** , cambie el nombre de esta acción a `Internet Sales Details Drillthrough Action` .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-117">In the **Name** box, change the name of this action to `Internet Sales Details Drillthrough Action`.</span></span>  
  
4.  <span data-ttu-id="d8ed3-118">En la lista **Miembros de grupo de medida** , seleccione **Internet Sales**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-118">In the **Measure group members** list, select **Internet Sales**.</span></span>  
  
5.  <span data-ttu-id="d8ed3-119">En el cuadro **Columnas de obtención de detalles** , seleccione **Internet Sales Order Details** en la lista **Dimensiones** .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-119">In the **Drillthrough Columns** box, select **Internet Sales Order Details** in the **Dimensions** list.</span></span>  
  
6.  <span data-ttu-id="d8ed3-120">En la lista **Columnas devueltas** , active las casillas **Item Description** y **Order Number** y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-120">In the **Return Columns** list, select the **Item Description** and the **Order Number** check boxes, and then click **OK**.</span></span> <span data-ttu-id="d8ed3-121">La siguiente imagen muestra la plantilla de Acción con el aspecto que debería tener en este punto del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-121">The following image shows the Action template as it should appear at this point in this procedure.</span></span>  
  
     <span data-ttu-id="d8ed3-122">![Cuadro Columnas de obtención de detalles](../../2014/tutorials/media/l8-action3.gif "Cuadro Columnas de obtención de detalles")</span><span class="sxs-lookup"><span data-stu-id="d8ed3-122">![Drillthrough Columns box](../../2014/tutorials/media/l8-action3.gif "Drillthrough Columns box")</span></span>  
  
7.  <span data-ttu-id="d8ed3-123">Expanda el cuadro **Propiedades adicionales** , como en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-123">Expand the **Additional Properties** box, as shown in the following image.</span></span>  
  
     <span data-ttu-id="d8ed3-124">![Cuadro Propiedades adicionales](../../2014/tutorials/media/l8-action4.gif "Cuadro Propiedades adicionales")</span><span class="sxs-lookup"><span data-stu-id="d8ed3-124">![Additional Properties box](../../2014/tutorials/media/l8-action4.gif "Additional Properties box")</span></span>  
  
8.  <span data-ttu-id="d8ed3-125">En el cuadro **número máximo de filas** , escriba `10` .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-125">In the **Maximum Rows** box, type `10`.</span></span>  
  
9. <span data-ttu-id="d8ed3-126">En el cuadro **título** , escriba `Drillthrough to Order Details...` .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-126">In the **Caption** box, type `Drillthrough to Order Details...`.</span></span>  
  
     <span data-ttu-id="d8ed3-127">Esta configuración limita el número de filas devueltas y especifica el título que aparece en el menú de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-127">These settings limit the number of rows returned and specify the caption that appears in the client application menu.</span></span> <span data-ttu-id="d8ed3-128">En la ilustración siguiente se muestra esta configuración en el cuadro **Propiedades adicionales** .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-128">The following image shows these settings in the **AdditionalProperties** box.</span></span>  
  
     <span data-ttu-id="d8ed3-129">![Cuadro Propiedades adicionales](../../2014/tutorials/media/l8-action5.gif "Cuadro Propiedades adicionales")</span><span class="sxs-lookup"><span data-stu-id="d8ed3-129">![Additional Properties box](../../2014/tutorials/media/l8-action5.gif "Additional Properties box")</span></span>  
  
## <a name="using-the-drillthrough-action"></a><span data-ttu-id="d8ed3-130">Usar la acción de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="d8ed3-130">Using the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="d8ed3-131">En el menú **Compilar** , haga clic en **Tutorial de Implementar Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-131">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="d8ed3-132">Cuando la implementación se haya completado correctamente, haga clic en la pestaña **Explorador** del Diseñador de cubos para el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y, a continuación, haga clic en el botón **Volver a conectar** .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-132">When deployment has successfully completed, click the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="d8ed3-133">Inicie Excel.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-133">Start Excel.</span></span>  
  
4.  <span data-ttu-id="d8ed3-134">Agregue la medida **Internet Sales-Sales Amount** al área Valores.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-134">Add the **Internet Sales-Sales Amount** measure to the Values area.</span></span>  
  
5.  <span data-ttu-id="d8ed3-135">Agregue la jerarquía definida por el usuario **Customer Geography** desde la carpeta **Location** de la dimensión **Customer** al panel **Filtro de informe** .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-135">Add the **Customer Geography** user-defined hierarchy from the **Location** folder in the **Customer** dimension to the **Report Filter** area.</span></span>  
  
6.  <span data-ttu-id="d8ed3-136">En la tabla dinámica, en **Customer Geography**, agregue un filtro que seleccione un solo cliente.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-136">On the PivotTable, in **Customer Geography**, add a filter that selects a single customer.</span></span> <span data-ttu-id="d8ed3-137">Expanda sucesivamente **All Customers**, **Australia**, **Queensland**, **Brisbane**y **4000**, active la casilla correspondiente a **Adam Powell**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-137">Expand **All Customers**, expand **Australia**, expand **Queensland**, expand **Brisbane**, expand **4000**, select the check box for **Adam Powell**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d8ed3-138">Las ventas totales de productos de [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] a Adam Powell aparecerán en el área de datos.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-138">The total sales of products by [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] to Adam Powell are displayed in the data area.</span></span>  
  
7.  <span data-ttu-id="d8ed3-139">Haga clic con el botón derecho en el importe de venta, seleccione **Acciones adicionales**y, después, haga clic en **Drillthrough to Order Details**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-139">Right-click on the sales amount, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="d8ed3-140">La información detallada de los pedidos enviados a Adam Powell aparecerá en el **Visor de muestras de datos**, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-140">The details of the orders that were shipped to Adam Powell are displayed in the **Data Sample Viewer**, as shown in the following image.</span></span> <span data-ttu-id="d8ed3-141">Sin embargo, algunos detalles adicionales podrían ser igualmente útiles, caso de la fecha del pedido, la fecha de vencimiento y la fecha de envío.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-141">However, some additional details would also be useful, such as the order date, due date, and ship date.</span></span> <span data-ttu-id="d8ed3-142">En el siguiente procedimiento, agregará estos detalles adicionales.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-142">In the next procedure, you will add these additional details.</span></span>  
  
     <span data-ttu-id="d8ed3-143">![Pedidos enviados a Adam Powell](../../2014/tutorials/media/l8-action6.gif "Pedidos enviados a Adam Powell")</span><span class="sxs-lookup"><span data-stu-id="d8ed3-143">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action6.gif "Orders shipped to Adam Powell")</span></span>  
  
8.  <span data-ttu-id="d8ed3-144">Cerrar Excel/</span><span class="sxs-lookup"><span data-stu-id="d8ed3-144">Close Excel/</span></span>  
  
## <a name="modifying-the-drillthrough-action"></a><span data-ttu-id="d8ed3-145">Modificar la acción de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="d8ed3-145">Modifying the Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="d8ed3-146">Abra el Diseñador de dimensiones para la dimensión **Internet Sales Order Details** .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-146">Open Dimension Designer for the **Internet Sales Order Details** dimension.</span></span>  
  
     <span data-ttu-id="d8ed3-147">Observe que solo se han definido tres atributos para esta dimensión.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-147">Notice that only three attributes have been defined for this dimension.</span></span>  
  
2.  <span data-ttu-id="d8ed3-148">En el panel **Vista del origen de datos** , haga clic con el botón derecho en un área abierta y, después, haga clic en **Mostrar todas las tablas**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-148">In the **Data Source View** pane, right-click an open area, and then click **Show All Tables**.</span></span>  
  
3.  <span data-ttu-id="d8ed3-149">En el menú **Formato** , elija **Diseño automático** y haga clic en **Diagrama**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-149">On the **Format** menu, point to **Autolayout** and then click **Diagram**.</span></span>  
  
4.  <span data-ttu-id="d8ed3-150">Busque la tabla **InternetSales (dbo.FactInternetSales)** haciendo clic con el botón derecho en un área abierta del panel **Vista del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-150">Locate the **InternetSales (dbo.FactInternetSales)** table by right-clicking in an open area of the **Data Source View** pane.</span></span> <span data-ttu-id="d8ed3-151">Después, haga clic en **Buscar tabla,** en **InternetSales,** y, por último, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-151">Then click **Find Table,** click **InternetSales,** and click **OK**.</span></span>  
  
5.  <span data-ttu-id="d8ed3-152">Cree nuevos atributos basados en las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="d8ed3-152">Create new attributes based on the following columns:</span></span>  
  
    -   <span data-ttu-id="d8ed3-153">OrderDateKey</span><span class="sxs-lookup"><span data-stu-id="d8ed3-153">OrderDateKey</span></span>  
  
    -   <span data-ttu-id="d8ed3-154">DueDateKey</span><span class="sxs-lookup"><span data-stu-id="d8ed3-154">DueDateKey</span></span>  
  
    -   <span data-ttu-id="d8ed3-155">ShipDateKey</span><span class="sxs-lookup"><span data-stu-id="d8ed3-155">ShipDateKey</span></span>  
  
6.  <span data-ttu-id="d8ed3-156">Cambie la propiedad **nombre** del atributo **Order Date Key** a `Order Date` then, haga clic en el botón examinar de la propiedad **columna Name** y, en el cuadro de diálogo **columna de nombre** , seleccione **Date** como la tabla de origen y seleccione SimpleDate como columna de origen.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-156">Change the **Name** property for the **Order Date Key** attribute to `Order Date` Then, click the browse button for the **Name Column** property, and in the **Name Column** dialog box, select **Date** as the source table and select SimpleDate as the source column.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="d8ed3-157">Cambie la propiedad **nombre** del atributo de **clave de fecha de vencimiento** a y, `Due Date` a continuación, use el mismo método que el atributo de **clave de fecha de pedido** y cambie la propiedad columna de **nombre** de este atributo por **Date. SimpleDate (WCHAR)**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-157">Change the **Name** property for the **Due Date Key** attribute to `Due Date`, and then, by using the same method as the **Order Date Key** attribute, change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
8.  <span data-ttu-id="d8ed3-158">Cambie la propiedad **nombre** del atributo **Ship Date Key** a `Ship Date` y, a continuación, cambie la propiedad **columna Name** de este atributo por **Date. SimpleDate (WCHAR)**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-158">Change the **Name** property for the **Ship Date Key** attribute to `Ship Date`, and then change the **Name Column** property for this attribute to **Date.SimpleDate (WChar)**.</span></span>  
  
9. <span data-ttu-id="d8ed3-159">Cambie a la pestaña **Acciones** del Diseñador de cubos para el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-159">Switch to the **Actions** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>  
  
10. <span data-ttu-id="d8ed3-160">En el cuadro **Columnas de obtención de detalles** , active las casillas para agregar las siguientes columnas a la lista **Columnas devueltas** y, después, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="d8ed3-160">In the **Drillthrough Columns** box, select the check boxes to add the following columns to the **Return Columns** list, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="d8ed3-161">Order Date</span><span class="sxs-lookup"><span data-stu-id="d8ed3-161">Order Date</span></span>  
  
    -   <span data-ttu-id="d8ed3-162">Due Date</span><span class="sxs-lookup"><span data-stu-id="d8ed3-162">Due Date</span></span>  
  
    -   <span data-ttu-id="d8ed3-163">Ship Date</span><span class="sxs-lookup"><span data-stu-id="d8ed3-163">Ship Date</span></span>  
  
     <span data-ttu-id="d8ed3-164">La siguiente imagen muestra estas columnas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-164">The following image shows these columns selected.</span></span>  
  
     <span data-ttu-id="d8ed3-165">![Cuadro Columnas de obtención de detalles](../../2014/tutorials/media/l8-action7.gif "Cuadro Columnas de obtención de detalles")</span><span class="sxs-lookup"><span data-stu-id="d8ed3-165">![Drillthrough Columns box](../../2014/tutorials/media/l8-action7.gif "Drillthrough Columns box")</span></span>  
  
## <a name="reviewing-the-modified-drillthrough-action"></a><span data-ttu-id="d8ed3-166">Revisar la acción de obtención de detalles modificada</span><span class="sxs-lookup"><span data-stu-id="d8ed3-166">Reviewing the Modified Drillthrough Action</span></span>  
  
1.  <span data-ttu-id="d8ed3-167">En el menú **Compilar** , haga clic en **Tutorial de Implementar Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-167">On the **Build** menu, click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="d8ed3-168">Cuando la implementación se haya completado correctamente, cambie a la pestaña **Explorador** del Diseñador de cubos para el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] y haga clic en el botón **Volver a conectar** .</span><span class="sxs-lookup"><span data-stu-id="d8ed3-168">When deployment has successfully completed, switch to the **Browser** tab in Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Reconnect** button.</span></span>  
  
3.  <span data-ttu-id="d8ed3-169">Inicie Excel.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-169">Start Excel.</span></span>  
  
4.  <span data-ttu-id="d8ed3-170">Vuelva a crear la tabla dinámica usando **Internet Sales-Sales Amount** en el área Valores y **Geografía del cliente** en el Filtro de informe.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-170">Recreate the PivotTable using **Internet Sales-Sales Amount** in the Values area and **Customer Geography** in the Report Filter.</span></span>  
  
     <span data-ttu-id="d8ed3-171">Agregue un filtro que seleccione **All Customers**, **Australia**, **Queensland**, **Brisbane**, **4000**, **Adam Powell**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-171">Add a filter that selects from **All Customers**, **Australia**, **Queensland**, **Brisbane**, **4000**, **Adam Powell**.</span></span>  
  
5.  <span data-ttu-id="d8ed3-172">Haga clic en la celda de datos de **Internet Sales-Sales Amount** , seleccione **Acciones adicionales**y, después, haga clic en **Drillthrough to Order Details**.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-172">Click the **Internet Sales-Sales Amount** data cell, point to **Additional Actions**, and then click **Drillthrough to Order Details**.</span></span>  
  
     <span data-ttu-id="d8ed3-173">La información detallada de estos pedidos enviados a Adam Powell aparecerá en una hoja de cálculo temporal.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-173">The details of these orders shipped to Adam Powell are displayed in a temporary worksheet.</span></span> <span data-ttu-id="d8ed3-174">Dicha información incluye la descripción de los artículos, el número y la fecha de pedido, la fecha de vencimiento y la fecha de envío, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="d8ed3-174">This includes item description, order number, order date, due date, and ship date information, as shown in the following image.</span></span>  
  
     <span data-ttu-id="d8ed3-175">![Pedidos enviados a Adam Powell](../../2014/tutorials/media/l8-action8.gif "Pedidos enviados a Adam Powell")</span><span class="sxs-lookup"><span data-stu-id="d8ed3-175">![Orders shipped to Adam Powell](../../2014/tutorials/media/l8-action8.gif "Orders shipped to Adam Powell")</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="d8ed3-176">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="d8ed3-176">Next Lesson</span></span>  
 [<span data-ttu-id="d8ed3-177">Lección 9: definir perspectivas y traducciones</span><span class="sxs-lookup"><span data-stu-id="d8ed3-177">Lesson 9: Defining Perspectives and Translations</span></span>](lesson-9-defining-perspectives-and-translations.md)  
  
## <a name="see-also"></a><span data-ttu-id="d8ed3-178">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8ed3-178">See Also</span></span>  
 <span data-ttu-id="d8ed3-179">[Acciones &#40;Analysis Services de datos multidimensionales&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="d8ed3-179">[Actions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models/actions-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="d8ed3-180">[Acciones en modelos multidimensionales](multidimensional-models/actions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="d8ed3-180">[Actions in Multidimensional Models](multidimensional-models/actions-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="d8ed3-181">[Relaciones de dimensión](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span><span class="sxs-lookup"><span data-stu-id="d8ed3-181">[Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md) </span></span>  
 <span data-ttu-id="d8ed3-182">[Definir una relación de hechos](lesson-5-2-defining-a-fact-relationship.md) </span><span class="sxs-lookup"><span data-stu-id="d8ed3-182">[Defining a Fact Relationship](lesson-5-2-defining-a-fact-relationship.md) </span></span>  
 [<span data-ttu-id="d8ed3-183">Definir relaciones de hechos y propiedades de las relaciones de hechos</span><span class="sxs-lookup"><span data-stu-id="d8ed3-183">Define a Fact Relationship and Fact Relationship Properties</span></span>](multidimensional-models/define-a-fact-relationship-and-fact-relationship-properties.md)  
  
  
