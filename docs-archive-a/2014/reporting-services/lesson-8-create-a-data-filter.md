---
title: 'Lección 8: Crear un filtro de datos | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19ccbdba-e3da-40a4-b652-32c628cf32e5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9c11d4cf83619e53cd7e8f00091c66cc8e50ad76
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669499"
---
# <a name="lesson-8-create-a-data-filter"></a><span data-ttu-id="88646-102">Lección 8: Crear un filtro de datos</span><span class="sxs-lookup"><span data-stu-id="88646-102">Lesson 8: Create a Data Filter</span></span>
  <span data-ttu-id="88646-103">Después de agregar una acción de obtención de detalles en el informe primario, el paso siguiente consiste en crear un filtro de los datos de la tabla de datos que definió para el informe secundario.</span><span class="sxs-lookup"><span data-stu-id="88646-103">After you add a drillthrough action on the parent report, your next step is to create a data filter for the data table that you defined for the child report.</span></span>  
  
 <span data-ttu-id="88646-104">Puede crear un filtro basado en una tabla **o** un filtro de consulta para el informe de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="88646-104">You can create a table-based filter **or** a query filter for the drillthrough report.</span></span> <span data-ttu-id="88646-105">Esta lección proporciona instrucciones para ambas opciones.</span><span class="sxs-lookup"><span data-stu-id="88646-105">This lesson provides instructions for both options.</span></span>  
  
## <a name="table-based-filter"></a><span data-ttu-id="88646-106">Filtro basado en una tabla</span><span class="sxs-lookup"><span data-stu-id="88646-106">Table-Based Filter</span></span>  
 <span data-ttu-id="88646-107">Debe completar las tareas siguientes para implementar un filtro basado en una tabla.</span><span class="sxs-lookup"><span data-stu-id="88646-107">You need to complete the following tasks to implement a table-based filter.</span></span>  
  
-   <span data-ttu-id="88646-108">Agregue una expresión de filtro al Tablix en el informe secundario.</span><span class="sxs-lookup"><span data-stu-id="88646-108">Add a filter expression to the tablix in the child report.</span></span>  
  
-   <span data-ttu-id="88646-109">Cree una función que seleccione datos sin filtrar de la tabla `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="88646-109">Create a function that selects unfiltered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="88646-110">Agregue un controlador de eventos que enlaza el DataTable `PurchaseOrderDetail` al informe secundario.</span><span class="sxs-lookup"><span data-stu-id="88646-110">Add an event handler that binds the `PurchaseOrderDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-add-a-filter-expression-to-the-tablix-in-the-child-report"></a><span data-ttu-id="88646-111">Para agregar una expresión de filtro al Tablix en el informe secundario</span><span class="sxs-lookup"><span data-stu-id="88646-111">To add a filter expression to the tablix in the child report</span></span>  
  
1.  <span data-ttu-id="88646-112">Abra el informe secundario.</span><span class="sxs-lookup"><span data-stu-id="88646-112">Open the child report.</span></span>  
  
2.  <span data-ttu-id="88646-113">Seleccione un encabezado de columna en el Tablix, haga clic con el botón secundario en la celda gris que aparece encima del encabezado de columna y, a continuación, haga clic en **propiedades de Tablix**.</span><span class="sxs-lookup"><span data-stu-id="88646-113">Select a column heading in the tablix, right-click the gray cell that appears above the column heading, and then click **Tablix Properties**.</span></span>  
  
3.  <span data-ttu-id="88646-114">Haga clic en la página **filtros** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="88646-114">Click on the **Filters** page, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="88646-115">En la **expresión** presentada, haga clic en en `ProductID` la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="88646-115">In the **Expression** filed, click `ProductID` from the drop-down list.</span></span> <span data-ttu-id="88646-116">Es la columna a la que se aplica el filtro.</span><span class="sxs-lookup"><span data-stu-id="88646-116">This is the column to which you apply the filter.</span></span>  
  
5.  <span data-ttu-id="88646-117">Haga clic en el **=** operador igual () en la lista desplegable **operador** .</span><span class="sxs-lookup"><span data-stu-id="88646-117">Click the equal (**=**) operator in the **Operator** drop-down list.</span></span>  
  
6.  <span data-ttu-id="88646-118">Haga clic en el botón expresión situado junto al campo **valor** , haga clic en **parámetros** en el área **categoría** y, a continuación, haga doble clic `productid` en el área **valores** .</span><span class="sxs-lookup"><span data-stu-id="88646-118">Click the expression button next to the **Value** field, click **Parameters** in the **Category** area, and then double-click `productid` in the **Values** area.</span></span> <span data-ttu-id="88646-119">El campo **Establecer expresión para: Valor** ahora debe contener una expresión similar a **=Parameters!productid.Value**.</span><span class="sxs-lookup"><span data-stu-id="88646-119">The **Set expression for: Value** field should now contain expression similar to **=Parameters!productid.Value**.</span></span>  
  
7.  <span data-ttu-id="88646-120">Haga clic en **Aceptar** y en **Aceptar** de nuevo en el cuadro de diálogo **propiedades de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="88646-120">Click **OK,** and **OK** again in the **Tablix Properties** dialog box.</span></span>  
  
8.  <span data-ttu-id="88646-121">Guarde el archivo .rdlc.</span><span class="sxs-lookup"><span data-stu-id="88646-121">Save the .rdlc file.</span></span>  
  
#### <a name="to-create-a-function-that-selects-unfiltered-data-from-the-purchaseordedetail-table"></a><span data-ttu-id="88646-122">Para crear una función que seleccione datos sin filtrar de la tabla PurchaseOrdeDetail.</span><span class="sxs-lookup"><span data-stu-id="88646-122">To create a function that selects unfiltered data from the PurchaseOrdeDetail table</span></span>  
  
1.  <span data-ttu-id="88646-123">En el Explorador de soluciones, expanda Default.aspx y haga doble clic en Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="88646-123">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="88646-124">Cree una nueva función que acepte un parámetro, `productid`, de tipo Integer y devuelva un objeto `datatable` y haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="88646-124">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object, and does the following.</span></span>  
  
    1.  <span data-ttu-id="88646-125">Crea una instancia del conjunto de `DataSet2` datos,, que se creó en el paso 2 de la [Lección 4: definir una conexión de datos y una tabla de datos para el informe secundario](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span><span class="sxs-lookup"><span data-stu-id="88646-125">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="88646-126">Cree una conexión a la base de datos de SQL Server para ejecutar la consulta definida en la **Lección 4: Definir una conexión de datos y una tabla de datos para el informe secundario**.</span><span class="sxs-lookup"><span data-stu-id="88646-126">Create a connection to the SqlServer database to execute the query defined in **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="88646-127">La consulta devolverá datos sin filtrar.</span><span class="sxs-lookup"><span data-stu-id="88646-127">The query will return unfiltered data.</span></span>  
  
    4.  <span data-ttu-id="88646-128">Rellene la instancia DataSet con los datos sin filtrar ejecutando la consulta.</span><span class="sxs-lookup"><span data-stu-id="88646-128">Fill the DataSet instance with the unfiltered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="88646-129">Devuelva la DataTable `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="88646-129">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="88646-130">La función será similar a la siguiente. (Esto es solo para la referencia.</span><span class="sxs-lookup"><span data-stu-id="88646-130">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="88646-131">Puede seguir cualquier modelo que desee, para capturar los datos necesarios para el informe secundario).</span><span class="sxs-lookup"><span data-stu-id="88646-131">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table, fetch the  
            /// unfiltered data and bind it with the Child report  
            /// </summary>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail()  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail ", sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-binds-the-purchaseorderdetail-datatable-to-the-child-report"></a><span data-ttu-id="88646-132">Para agregar un controlador de eventos que enlaza el DataTable PurchaseOrderDetail al informe secundario.</span><span class="sxs-lookup"><span data-stu-id="88646-132">To add an event handler that binds the PurchaseOrderDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="88646-133">Abra el archivo Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="88646-133">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="88646-134">Haga clic con el botón secundario en el control ReportViewer y, a continuación, haga clic en **propiedades.**</span><span class="sxs-lookup"><span data-stu-id="88646-134">Right click the ReportViewer control, and then click **Properties.**</span></span>  
  
3.  <span data-ttu-id="88646-135">En la página **propiedades** , haga clic en el icono **eventos** .</span><span class="sxs-lookup"><span data-stu-id="88646-135">On the **Properties** page, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="88646-136">Haga doble clic en el evento de **obtención de detalles** .</span><span class="sxs-lookup"><span data-stu-id="88646-136">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="88646-137">De este modo agregará una sección del controlador de eventos en el código, que será similar al bloque siguiente.</span><span class="sxs-lookup"><span data-stu-id="88646-137">This will add an event handler section in the code, which will look similar to the below block.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="88646-138">Complete el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="88646-138">Complete the event handler.</span></span> <span data-ttu-id="88646-139">Debe incluir la funcionalidad siguiente.</span><span class="sxs-lookup"><span data-stu-id="88646-139">It should include the following functionalty.</span></span>  
  
    1.  <span data-ttu-id="88646-140">Capture la referencia al objeto de informe secundario del parámetro *DrillthroughEventArgs* .</span><span class="sxs-lookup"><span data-stu-id="88646-140">Fetch the child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="88646-141">Llame a la función.`GetPurchaseOrderDetail`</span><span class="sxs-lookup"><span data-stu-id="88646-141">Call the function, `GetPurchaseOrderDetail`</span></span>  
  
    3.  <span data-ttu-id="88646-142">Enlace el DataTable `PurchaseOrderDetail` con el origen de datos de correspondiente del informe.</span><span class="sxs-lookup"><span data-stu-id="88646-142">Bind the `PurchaseOrderDetail` DataTable with the report's corresponding data source.</span></span>  
  
         <span data-ttu-id="88646-143">El código de controlador de eventos completo será similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="88646-143">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                     //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                     //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail()));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="88646-144">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="88646-144">Save the file.</span></span>  
  
## <a name="query-filter"></a><span data-ttu-id="88646-145">Filtro de consulta</span><span class="sxs-lookup"><span data-stu-id="88646-145">Query Filter</span></span>  
 <span data-ttu-id="88646-146">Debe completar las tareas siguientes para implementar un filtro de consulta.</span><span class="sxs-lookup"><span data-stu-id="88646-146">You need to complete the following tasks to implement a query filter.</span></span>  
  
-   <span data-ttu-id="88646-147">Cree una función que seleccione datos filtrados de la tabla `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="88646-147">Create a function that selected filtered data from the `PurchaseOrderDetail` table.</span></span>  
  
-   <span data-ttu-id="88646-148">Agregue un controlador de eventos que recupere los valores de los parámetros y enlace el DataTable `PurchaseOrdeDetail` al informe secundario.</span><span class="sxs-lookup"><span data-stu-id="88646-148">Add an event handler that retrieves parameter values and binds the `PurchaseOrdeDetail` DataTable to the child report.</span></span>  
  
#### <a name="to-create-a-function-that-selects-filtered-data-from-the-purchaseorderdetail-table"></a><span data-ttu-id="88646-149">Para crear una función que seleccione datos filtrados de la tabla PurchaseOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="88646-149">To create a function that selects filtered data from the PurchaseOrderDetail table</span></span>  
  
1.  <span data-ttu-id="88646-150">En el Explorador de soluciones, expanda Default.aspx y haga doble clic en Default.aspx.cs.</span><span class="sxs-lookup"><span data-stu-id="88646-150">In Solution Explorer, expand Default.aspx, and then double click Default.aspx.cs.</span></span>  
  
2.  <span data-ttu-id="88646-151">Cree una nueva función que acepte un parámetro, `productid`, de tipo Integer, y devuelva un objeto `datatable` y haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="88646-151">Create a new function that accepts a parameter, `productid`, of type Integer and returns a `datatable` object and does the following.</span></span>  
  
    1.  <span data-ttu-id="88646-152">Crea una instancia del conjunto de `DataSet2` datos,, que se creó en el paso 2 de la [Lección 4: definir una conexión de datos y una tabla de datos para el informe secundario](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span><span class="sxs-lookup"><span data-stu-id="88646-152">Creates an instance of the dataset, `DataSet2`, which was created in Step 2 of [Lesson 4: Define a Data Connection and Data Table for Child Report](lesson-4-define-a-data-connection-and-data-table-for-child-report.md).</span></span>  
  
    2.  <span data-ttu-id="88646-153">Cree una conexión a la base de datos de SQL Server para ejecutar la consulta definida en la **Lección 4: Definir una conexión de datos y una tabla de datos para el informe secundario**.</span><span class="sxs-lookup"><span data-stu-id="88646-153">Create a connection to the SqlServer database to execute the query defined **Lesson 4: Define a Data Connection and DataTable for Child Report**.</span></span>  
  
    3.  <span data-ttu-id="88646-154">La consulta incluirá un parámetro, `productid`, para asegurarse de que los datos devueltos se filtran en función del `ProductID` seleccionado en el informe primario.</span><span class="sxs-lookup"><span data-stu-id="88646-154">The query will include a parameter, `productid`, to make sure the data returned is filtered based on the `ProductID` selected in the parent report.</span></span>  
  
    4.  <span data-ttu-id="88646-155">Rellene la instancia DataSet con los datos filtrados ejecutando la consulta.</span><span class="sxs-lookup"><span data-stu-id="88646-155">Fill the DataSet instance with the filtered data by executing the query.</span></span>  
  
    5.  <span data-ttu-id="88646-156">Devuelva la DataTable `PurchaseOrderDetail`.</span><span class="sxs-lookup"><span data-stu-id="88646-156">Return the `PurchaseOrderDetail` DataTable.</span></span>  
  
         <span data-ttu-id="88646-157">La función será similar a la siguiente. (Esto es solo para la referencia.</span><span class="sxs-lookup"><span data-stu-id="88646-157">The function will look similar to the one below, (This is just for your reference.</span></span> <span data-ttu-id="88646-158">Puede seguir cualquier modelo que desee, para capturar los datos necesarios para el informe secundario).</span><span class="sxs-lookup"><span data-stu-id="88646-158">You can follow any pattern that you want, to fetch the necessary data for child report).</span></span>  
  
        ```  
        /// <summary>  
            /// Function to query PurchaseOrderDetail table and filter the  
            /// data for a specific ProductID selected in the Parent report.  
            /// </summary>  
            /// <param name="productid">Parameter passed from the Parent report to filter data.</param>  
            /// <returns>A dataTable of type PurchaseOrderDetail</returns>  
            private DataTable GetPurchaseOrderDetail(int productid)  
            {  
                try  
                {  
                    //Create the instance for the typed dataset, DataSet2 which will   
                    //hold the [PurchaseOrderDetail] table details.  
                    //The dataset was created as part of the tutorial in Step 4.  
                    DataSet2 ds = new DataSet2();  
  
                    //Create a SQL Connection to the AdventureWorks2008 database using Windows Authentication.  
                    using (SqlConnection sqlconn = new SqlConnection("Data Source=.;Initial Catalog=Adventureworks;Integrated Security=SSPI"))  
                    {  
                        //Building the dynamic query with the parameter ProductID.  
                        SqlDataAdapter adap = new SqlDataAdapter("SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail where ProductID = " + productid, sqlconn);  
                        //Executing the QUERY and fill the dataset with the PurchaseOrderDetail table data.  
                        adap.Fill(ds, "PurchaseOrderDetail");  
                    }  
  
                    //Return the PurchaseOrderDetail table for the Report Data Source.  
                    return ds.PurchaseOrderDetail;  
                }  
                catch  
                {  
                    throw;  
                }  
            }  
        ```  
  
#### <a name="to-add-an-event-handler-that-retrieves-parameter-values-and-binds-the-purchaseordedetail-datatable-to-the-child-report"></a><span data-ttu-id="88646-159">Para agregar un controlador de eventos que recupere los valores de los parámetros y enlace el DataTable PurchaseOrdeDetail al informe secundario.</span><span class="sxs-lookup"><span data-stu-id="88646-159">To add an event handler that retrieves parameter values and binds the PurchaseOrdeDetail DataTable to the child report</span></span>  
  
1.  <span data-ttu-id="88646-160">Abra el archivo Default.aspx.</span><span class="sxs-lookup"><span data-stu-id="88646-160">Open Default.aspx.</span></span>  
  
2.  <span data-ttu-id="88646-161">Haga clic con el botón secundario en el control ReportViewer y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="88646-161">Right-click the ReportViewer control, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="88646-162">En el panel **propiedades** , haga clic en el icono **eventos** .</span><span class="sxs-lookup"><span data-stu-id="88646-162">On the **Properties** pane, click the **Events** icon.</span></span>  
  
4.  <span data-ttu-id="88646-163">Haga doble clic en el evento de **obtención de detalles** .</span><span class="sxs-lookup"><span data-stu-id="88646-163">Double click the **Drillthrough** event.</span></span>  
  
     <span data-ttu-id="88646-164">De este modo agregará una sección del controlador de eventos en el código, que será similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="88646-164">This will add an event handler section in the code that will look similar to the following.</span></span>  
  
    ```  
    protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
    {  
    }  
    ```  
  
5.  <span data-ttu-id="88646-165">Complete el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="88646-165">Complete the event handler.</span></span> <span data-ttu-id="88646-166">Debe incluir la funcionalidad siguiente.</span><span class="sxs-lookup"><span data-stu-id="88646-166">It should include the following functionality.</span></span>  
  
    1.  <span data-ttu-id="88646-167">Capture la referencia al objeto de informe secundario del parámetro *DrillthroughEventArgs* .</span><span class="sxs-lookup"><span data-stu-id="88646-167">Fetch the Child report object reference from the *DrillthroughEventArgs* parameter.</span></span>  
  
    2.  <span data-ttu-id="88646-168">Obtenga la lista de parámetros del informe secundario del objeto de informe secundario capturado.</span><span class="sxs-lookup"><span data-stu-id="88646-168">Get the child report parameter list from the child report object fetched.</span></span>  
  
    3.  <span data-ttu-id="88646-169">Recorra en iteración la colección de parámetros y recupere el valor del parámetro, `ProductID`, pasado desde el informe primario.</span><span class="sxs-lookup"><span data-stu-id="88646-169">Iterate through the parameter's collection and retrieve the value for the parameter, `ProductID`, passed from the parent report.</span></span>  
  
    4.  <span data-ttu-id="88646-170">Llame a la función, `GetPurchaseOrderDetail`, y pase el valor del parámetro `ProductID`.</span><span class="sxs-lookup"><span data-stu-id="88646-170">Call the function, `GetPurchaseOrderDetail`, and pass the value for parameter `ProductID`.</span></span>  
  
    5.  <span data-ttu-id="88646-171">Enlazar el `PurchaseOrderDetail` DataTable con el origen de datos correspondiente del informe.</span><span class="sxs-lookup"><span data-stu-id="88646-171">Bind the `PurchaseOrderDetail` DataTable with the Report's corresponding data source.</span></span>  
  
         <span data-ttu-id="88646-172">El código de controlador de eventos completo será similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="88646-172">The completed event handler code will look similar to the following.</span></span>  
  
        ```  
        protected void ReportViewer1_Drillthrough(object sender, Microsoft.Reporting.WebForms.DrillthroughEventArgs e)  
            {  
                try  
                {  
                    //Variable to store the parameter value passed from the MainReport.  
                    int productid = 0;  
  
                    //Get the instance of the Target report, in our case the JumpReport.rdlc.  
                    LocalReport report = (LocalReport)e.Report;  
  
                    //Get all the parameters passed from the main report to the target report.  
                    //OriginalParametersToDrillthrough actually returns a Generic list of   
                    //type ReportParameter.  
                    IList<ReportParameter> list = report.OriginalParametersToDrillthrough;  
  
                    //Parse through each parameters to fetch the values passed along with them.  
                    foreach (ReportParameter param in list)  
                    {  
                        //Since we know the report has only one parameter and it is not a multivalued,   
                        //we can directly fetch the first value from the Values array.  
                        productid = Convert.ToInt32(param.Values[0].ToString());  
                    }  
  
                    //Binding the DataTable to the Child report dataset.  
                    //The name DataSet1 which can be located from,   
                    //Go to Design view of Child.rdlc, Click View menu -> Report Data  
                    //You'll see this name under DataSet2.  
                    report.DataSources.Add(new ReportDataSource("DataSet1", GetPurchaseOrderDetail(productid)));  
                }  
                catch (Exception ex)  
                {  
                    Response.Write(ex.Message);  
                }  
            }  
        ```  
  
6.  <span data-ttu-id="88646-173">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="88646-173">Save the file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="88646-174">Tarea siguiente</span><span class="sxs-lookup"><span data-stu-id="88646-174">Next Task</span></span>  
 <span data-ttu-id="88646-175">Ha creado correctamente un filtro de datos para la tabla de datos que definió para el informe secundario.</span><span class="sxs-lookup"><span data-stu-id="88646-175">You have successfully created a data filter for the data table that you defined for the child report.</span></span> <span data-ttu-id="88646-176">A continuación, compilará y ejecutará la aplicación del sitio Web.</span><span class="sxs-lookup"><span data-stu-id="88646-176">Next, you will build and run the website application.</span></span>  
  
  
