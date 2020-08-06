---
title: 'Lección 2: Modificar las propiedades del origen de datos de informe | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: c962b0ff-ce8a-4742-8262-dc730901afcf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 05e56a58ce28ee1e1e450d3af012cbd1ffe668ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669520"
---
# <a name="lesson-2-modifying-the-report-data-source-properties"></a><span data-ttu-id="c1147-102">Lesson 2: Modifying the Report Data Source Properties</span><span class="sxs-lookup"><span data-stu-id="c1147-102">Lesson 2: Modifying the Report Data Source Properties</span></span>
  <span data-ttu-id="c1147-103">En esta lección, usará el Administrador de informes para seleccionar un informe que se entregará a los destinatarios.</span><span class="sxs-lookup"><span data-stu-id="c1147-103">In this lesson, you will use Report Manager to select a report that will be delivered to recipients.</span></span> <span data-ttu-id="c1147-104">La suscripción controlada por datos que va a definir distribuirá el informe **Sales Order** creado en el tutorial [Crear un informe de tabla básico &#40;Tutorial de SSRS&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="c1147-104">The data-driven subscription that you will define will distribute the **Sales Order** report created in the tutorial [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md).</span></span> <span data-ttu-id="c1147-105">En los pasos siguientes, modificará la información de conexión del origen de datos que el informe utiliza para obtener los datos.</span><span class="sxs-lookup"><span data-stu-id="c1147-105">In the steps that follow, you will modify the data source connection information used by the report to get data.</span></span> <span data-ttu-id="c1147-106">Solo los informes que usan **credenciales almacenadas** para obtener acceso a un origen de datos del informe se pueden distribuir a través de una suscripción controlada por datos.</span><span class="sxs-lookup"><span data-stu-id="c1147-106">Only reports that use **stored credentials** to access a report data source can be distributed through a data-driven subscription.</span></span> <span data-ttu-id="c1147-107">Las credenciales almacenadas son necesarias para el procesamiento desatendido de informes.</span><span class="sxs-lookup"><span data-stu-id="c1147-107">Stored credentials are necessary for unattended report processing.</span></span>

 <span data-ttu-id="c1147-108">También modificará el conjunto de datos y el informe para usar un parámetro que filtrar el informe en `[Order]` de modo que la suscripción pueda dar como resultado diferentes instancias del informe para pedidos concretos y formatos de representación.</span><span class="sxs-lookup"><span data-stu-id="c1147-108">You will also modify the dataset and report to use a parameter to filter the report on the `[Order]` so the subscription can output different instances of the report for specific orders and rendering formats.</span></span>

 <span data-ttu-id="c1147-109">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="c1147-109">**In this topic:**</span></span>

-   [<span data-ttu-id="c1147-110">Para modificar las propiedades del origen de datos</span><span class="sxs-lookup"><span data-stu-id="c1147-110">To Modify the Data Source Properties</span></span>](#bkmk_modify_datasource)

-   [<span data-ttu-id="c1147-111">Para modificar AdventureWorksDataset</span><span class="sxs-lookup"><span data-stu-id="c1147-111">To Modify the AdventureWorksDataset</span></span>](#bkmk_modify_dataset)

-   [<span data-ttu-id="c1147-112">Para agregar un parámetro de informe y volver a publicarlo</span><span class="sxs-lookup"><span data-stu-id="c1147-112">To Add a Report Parameter and Republish the Report</span></span>](#bkmk_add_reportparameter)

-   [<span data-ttu-id="c1147-113">Para volver a implementar el informe</span><span class="sxs-lookup"><span data-stu-id="c1147-113">To Re-deploy the Report</span></span>](#bkmk_redeploy)

##  <a name="to-modify-the-data-source-properties"></a><a name="bkmk_modify_datasource"></a><span data-ttu-id="c1147-114">Para modificar las propiedades del origen de datos</span><span class="sxs-lookup"><span data-stu-id="c1147-114">To Modify the Data Source Properties</span></span>

1.  <span data-ttu-id="c1147-115">Inicie [Administrador de informes &#40;modo nativo de SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) con privilegios de administrador, por ejemplo, haga clic con el botón secundario en el icono de Internet Explorer y haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="c1147-115">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) with administrator privileges, for example, right-click the icon for Internet Explorer and click **Run as administrator**.</span></span>

2.  <span data-ttu-id="c1147-116">Busque la carpeta que contiene el informe **Sales Orders** y, en el menú contextual del informe, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="c1147-116">Browse to the folder containing the **Sales Orders** report and in the context menu of the report, click **Manage**.</span></span>

     <span data-ttu-id="c1147-117">![Abra el menú contextual del informe y seleccione administrar](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Abra el menú contextual del informe y seleccione administrar")</span><span class="sxs-lookup"><span data-stu-id="c1147-117">![Open the report context menu and select manage](../../2014/tutorials/media/ssrs-tutorial-datadriven-manage-report.gif "Open the report context menu and select manage")</span></span>

3.  <span data-ttu-id="c1147-118">Haga clic en la pestaña **Orígenes de datos** .</span><span class="sxs-lookup"><span data-stu-id="c1147-118">Click the **Data Sources** tab.</span></span>

4.  <span data-ttu-id="c1147-119">Como **Tipo de conexión**, seleccione **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c1147-119">For **Connection Type**, select **Microsoft SQL Server**.</span></span>

5.  <span data-ttu-id="c1147-120">La cadena de conexión del origen de datos personalizada será la siguiente y se supone que la base de datos de ejemplo está en un servidor de bases de datos local:</span><span class="sxs-lookup"><span data-stu-id="c1147-120">The custom data source connection string will be the following and it assumes that the sample database is on a local database server:</span></span>

    ```
    Data source=localhost; initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="c1147-121">Haga clic en **Credenciales almacenadas de forma segura en el servidor de informes**.</span><span class="sxs-lookup"><span data-stu-id="c1147-121">Click **Credentials stored securely in the report server**.</span></span>

7.  <span data-ttu-id="c1147-122">Escriba su nombre de usuario (con el formato *dominio\usuario*) y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="c1147-122">Type your user name (use the format *domain\user*) and password.</span></span> <span data-ttu-id="c1147-123">Si no dispone de permisos para tener acceso a la base de datos [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] , especifique un inicio de sesión que disponga de ellos.</span><span class="sxs-lookup"><span data-stu-id="c1147-123">If you do not have permission to access the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database, specify a login that does.</span></span>

8.  <span data-ttu-id="c1147-124">Haga clic en **Usar como credenciales de Windows para la conexión al origen de datos**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1147-124">Click **Use as windows credentials when connecting to the data source**, and then click **OK**.</span></span> <span data-ttu-id="c1147-125">Si no usa ninguna cuenta de dominio (por ejemplo, si usa un inicio de sesión de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ), no active esta casilla.</span><span class="sxs-lookup"><span data-stu-id="c1147-125">If you are not using a domain account (for example, if you are using a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login), do not click this checkbox.</span></span>

9. <span data-ttu-id="c1147-126">Haga clic en **Probar conexión** para comprobar que puede conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="c1147-126">Click **Test Connection** to verify you can connect to the data source.</span></span>

10. <span data-ttu-id="c1147-127">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c1147-127">Click **Apply**.</span></span>

11. <span data-ttu-id="c1147-128">Visualice el informe para comprobar que se ejecuta con las credenciales que ha especificado.</span><span class="sxs-lookup"><span data-stu-id="c1147-128">View the report to verify that the report runs with the credentials you specified.</span></span> <span data-ttu-id="c1147-129">Para ver el informe, haga clic en la pestaña **Ver** . tenga en cuenta que una vez que el informe está abierto, debe seleccionar un nombre de empleado y, a continuación, hacer clic en el botón **Ver informe** para ver el informe.</span><span class="sxs-lookup"><span data-stu-id="c1147-129">To view the report, click the **View** tab. Note that once the report is open, you must select an Employee name and then click the **View Report** button to view the report.</span></span>

##  <a name="to-modify-the-adventureworksdataset"></a><a name="bkmk_modify_dataset"></a><span data-ttu-id="c1147-130">Para modificar AdventureWorksDataset</span><span class="sxs-lookup"><span data-stu-id="c1147-130">To Modify the AdventureWorksDataset</span></span>

1.  <span data-ttu-id="c1147-131">Abra el informe Sales Orders en [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1147-131">Open the Sales Orders report in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]</span></span>

2.  <span data-ttu-id="c1147-132">Haga clic con el botón derecho en el conjunto de datos `AdventureWorksDataset` y haga clic en **Propiedades del conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="c1147-132">Right-click the dataset `AdventureWorksDataset` and click **Dataset Properties**.</span></span>

3.  <span data-ttu-id="c1147-133">Agregue la instrucción `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` antes que la instrucción `Group By` .</span><span class="sxs-lookup"><span data-stu-id="c1147-133">Add the statement `WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)` before the `Group By` statement.</span></span> <span data-ttu-id="c1147-134">La sintaxis de la consulta completa es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1147-134">The full query syntax is the following:</span></span>

    ```
    SELECT soh.OrderDate AS Date, soh.SalesOrderNumber AS [Order], pps.Name AS Subcat, pp.Name AS Product, SUM(sd.OrderQty) AS Qty, SUM(sd.LineTotal)  AS LineTotal
    FROM Sales.SalesPerson AS sp INNER JOIN
      Sales.SalesOrderHeader AS soh ON sp.BusinessEntityID = soh.SalesPersonID INNER JOIN
       Sales.SalesOrderDetail AS sd ON sd.SalesOrderID = soh.SalesOrderID INNER JOIN
       Production.Product AS pp ON sd.ProductID = pp.ProductID
    INNER JOIN
       Production.ProductSubcategory AS pps ON pp.ProductSubcategoryID = pps.ProductSubcategoryID 
    INNER JOIN
        Production.ProductCategory AS ppc ON ppc.ProductCategoryID = pps.ProductCategoryID

    WHERE (UPPER(SalesOrderNumber) =UPPER(@OrderNumber) or  @OrderNumber IS NULL)

    GROUP BY ppc.Name, soh.OrderDate, soh.SalesOrderNumber, pps.Name, pp.Name, soh.SalesPersonID
    HAVING (ppc.Name = 'Clothing')
    ```

4.  <span data-ttu-id="c1147-135">Haga clic en **Aceptar**</span><span class="sxs-lookup"><span data-stu-id="c1147-135">Click **OK**</span></span>

##  <a name="to-add-a-report-parameter-and-republish-the-report"></a><a name="bkmk_add_reportparameter"></a><span data-ttu-id="c1147-136">Para agregar un parámetro de informe y volver a publicar el informe</span><span class="sxs-lookup"><span data-stu-id="c1147-136">To Add a Report Parameter and Republish the Report</span></span>

1.  <span data-ttu-id="c1147-137">En el panel **Datos de informe** , haga clic en **Nuevo** y, a continuación, haga clic en **Parámetro**.</span><span class="sxs-lookup"><span data-stu-id="c1147-137">In the **Report Data** pane click **New** and then click **Parameter...**</span></span>

2.  <span data-ttu-id="c1147-138">En **Nombre**, escriba `OrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="c1147-138">In **Name**, type `OrderNumber`.</span></span>

3.  <span data-ttu-id="c1147-139">En **Inicio**, escriba `OrderNumber`.</span><span class="sxs-lookup"><span data-stu-id="c1147-139">In **Prompt**, type `OrderNumber`.</span></span>

4.  <span data-ttu-id="c1147-140">Seleccione **Permitir valor en blanco ("")**.</span><span class="sxs-lookup"><span data-stu-id="c1147-140">Select **Allow blank value ("")**.</span></span>

5.  <span data-ttu-id="c1147-141">Seleccione **Permitir valor NULL**.</span><span class="sxs-lookup"><span data-stu-id="c1147-141">Select **Allow null value**.</span></span>

6.  <span data-ttu-id="c1147-142">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1147-142">Click **OK**.</span></span> <span data-ttu-id="c1147-143">El parámetro se agregará a la carpeta **Panel Datos de informe** y tendrá una apariencia similar a la de la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1147-143">The parameter will be added to the **Report Data pane** and it will look like the following image:</span></span>

     <span data-ttu-id="c1147-144">![El nuevo parámetro es agregado al panel Datos de informe](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "El nuevo parámetro es agregado al panel Datos de informe")</span><span class="sxs-lookup"><span data-stu-id="c1147-144">![The new parameter is added to the Report Data pane](../../2014/tutorials/media/ssrs-tutorial-datadriven-parameter.gif "The new parameter is added to the Report Data pane")</span></span>

7.  <span data-ttu-id="c1147-145">Haga clic en la pestaña **Vista previa** para ejecutar el informe. Observe el cuadro de entrada del parámetro en la parte superior del informe.</span><span class="sxs-lookup"><span data-stu-id="c1147-145">Click the **Preview** tab to run the report.Note the parameter input box at the top of the report.</span></span> <span data-ttu-id="c1147-146">Puede:</span><span class="sxs-lookup"><span data-stu-id="c1147-146">You can either:</span></span>

    -   <span data-ttu-id="c1147-147">Haga clic en Ver informe para ver el informe completo sin usar un parámetro.</span><span class="sxs-lookup"><span data-stu-id="c1147-147">Click View Report to see the full report without using a parameter.</span></span>

    -   <span data-ttu-id="c1147-148">Cancelar la selección de la opción Null y escribir un número de pedido, por ejemplo so71949, para ver solo el único pedido del informe.</span><span class="sxs-lookup"><span data-stu-id="c1147-148">Unselect the Null option and type an order number, for example so71949 to view only the one order in the report.</span></span>

         <span data-ttu-id="c1147-149">![Visor de informes con área de parámetros visible](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Visor de informes con área de parámetros visible")</span><span class="sxs-lookup"><span data-stu-id="c1147-149">![Report viewer with parameter area visible](../../2014/tutorials/media/ssrs-tutorial-datadriven-reportviewer-parameter.gif "Report viewer with parameter area visible")</span></span>

8.  <span data-ttu-id="c1147-150">Volver a implementar el informe de modo que la configuración de la suscripción de la lección siguiente pueda usar los cambios efectuados en esta lección.</span><span class="sxs-lookup"><span data-stu-id="c1147-150">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="c1147-151">Para obtener más información sobre las propiedades del proyecto que se usan en el tutorial de tablas, vea la sección ' para publicar el informe en el servidor de informes (opcional) ' de la [Lección 6: agregar grupos y totales &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="c1147-151">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

##  <a name="to-re-deploy-the-report"></a><a name="bkmk_redeploy"></a><span data-ttu-id="c1147-152">Para volver a implementar el informe</span><span class="sxs-lookup"><span data-stu-id="c1147-152">To Re-deploy the Report</span></span>

1.  <span data-ttu-id="c1147-153">Volver a implementar el informe de modo que la configuración de la suscripción de la lección siguiente pueda usar los cambios efectuados en esta lección.</span><span class="sxs-lookup"><span data-stu-id="c1147-153">Re-deploy the report so the subscription configuration in the next lesson can utilize the changes you made in this lesson.</span></span> <span data-ttu-id="c1147-154">Para obtener más información sobre las propiedades del proyecto que se usan en el tutorial de tablas, vea la sección ' para publicar el informe en el servidor de informes (opcional) ' de la [Lección 6: agregar grupos y totales &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="c1147-154">For more information on the project properties used in the table tutorial, see section 'To Publish the Report to the Report Server (Optional)' of [Lesson 6: Adding Grouping and Totals &#40;Reporting Services&#41;](../reporting-services/lesson-6-adding-grouping-and-totals-reporting-services.md).</span></span>

2.  <span data-ttu-id="c1147-155">En la barra de herramientas, haga clic en **Generar** y, a continuación, haga clic en **Tutorial de implementación**.</span><span class="sxs-lookup"><span data-stu-id="c1147-155">On the toolbar click **Build** and then click **Deploy tutorial**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1147-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c1147-156">Next Steps</span></span>
 <span data-ttu-id="c1147-157">Ha configurado correctamente el informe para obtener datos utilizando credenciales almacenadas.</span><span class="sxs-lookup"><span data-stu-id="c1147-157">You successfully configured the report to get data using stored credentials.</span></span> <span data-ttu-id="c1147-158">A continuación, especifica la suscripción usando las páginas de suscripción controlada por datos en el Administrador de informes.</span><span class="sxs-lookup"><span data-stu-id="c1147-158">Next, you specify the subscription using the Data-Driven Subscription pages in Report Manager.</span></span> <span data-ttu-id="c1147-159">Consulte la [Lección 3: Definir una suscripción controlada por datos](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="c1147-159">See [Lesson 3: Defining a Data-Driven Subscription](../reporting-services/lesson-3-defining-a-data-driven-subscription.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c1147-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1147-160">See Also</span></span>
 <span data-ttu-id="c1147-161">[Administrar orígenes de datos de informe](report-data/manage-report-data-sources.md) [especificar información de credenciales y conexión para los orígenes de datos de informe](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [crear una suscripción controlada por datos &#40;tutorial de SSRS&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) [crear un informe de tabla básico &#40;tutorial de SSRS&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="c1147-161">[Manage Report Data Sources](report-data/manage-report-data-sources.md) [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md) [Create a Data-Driven Subscription &#40;SSRS Tutorial&#41;](../reporting-services/create-a-data-driven-subscription-ssrs-tutorial.md) [Create a Basic Table Report &#40;SSRS Tutorial&#41;](../reporting-services/create-a-basic-table-report-ssrs-tutorial.md)</span></span>


