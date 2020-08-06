---
title: 'Tutorial: Crear un informe de tabla básico (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d9e30521-f8ae-4c45-89c3-d40727f622f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3587e2a53e2b09dd347a2733875eafd708b8a05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670251"
---
# <a name="tutorial-creating-a-basic-table-report-report-builder"></a><span data-ttu-id="014bb-102">Tutorial: Crear un informe de tabla básico (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="014bb-102">Tutorial: Creating a Basic Table Report (Report Builder)</span></span>
  <span data-ttu-id="014bb-103">Este tutorial muestra cómo crear un informe de tabla básico basado en datos de ventas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="014bb-103">This tutorial teaches you to create a basic table report based on sample sales data.</span></span> <span data-ttu-id="014bb-104">En la siguiente ilustración se muestra el informe que va a crear.</span><span class="sxs-lookup"><span data-stu-id="014bb-104">The following illustration shows the report you will create.</span></span>  
  
 <span data-ttu-id="014bb-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="014bb-105">![rs_CreateBasicReportTutorial](../../2014/tutorials/media/rs-createbasicreporttutorial.gif "rs_CreateBasicReportTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="014bb-106">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="014bb-106">What You Will Learn</span></span>  
 <span data-ttu-id="014bb-107">En este tutorial, aprenderá a realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="014bb-107">In this tutorial, you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="014bb-108">Crear un informe desde Introducción</span><span class="sxs-lookup"><span data-stu-id="014bb-108">Create a New Report from Getting Started</span></span>](#CreateTable)  
  
    1.  [<span data-ttu-id="014bb-109">Especificar una conexión de datos en el Asistente para tablas</span><span class="sxs-lookup"><span data-stu-id="014bb-109">Specify a Data Connection in the Table Wizard</span></span>](#DataConnection)  
  
    2.  [<span data-ttu-id="014bb-110">Crear una consulta en el Asistente para tablas</span><span class="sxs-lookup"><span data-stu-id="014bb-110">Create a Query in the Table Wizard</span></span>](#Query)  
  
    3.  [<span data-ttu-id="014bb-111">Organizar datos en grupos en el Asistente para tablas</span><span class="sxs-lookup"><span data-stu-id="014bb-111">Organize Data into Groups in the Table Wizard</span></span>](#Groups)  
  
    4.  [<span data-ttu-id="014bb-112">Agregar filas de subtotal y de total en el Asistente para tablas</span><span class="sxs-lookup"><span data-stu-id="014bb-112">Add Subtotal and Total Rows in the Table Wizard</span></span>](#Subtotals)  
  
    5.  [<span data-ttu-id="014bb-113">Elegir un estilo en el Asistente para tablas</span><span class="sxs-lookup"><span data-stu-id="014bb-113">Choose a Style in the Table Wizard</span></span>](#Style)  
  
2.  [<span data-ttu-id="014bb-114">Dar formato a los datos como moneda</span><span class="sxs-lookup"><span data-stu-id="014bb-114">Format Data as Currency</span></span>](#FormatCurrency)  
  
3.  [<span data-ttu-id="014bb-115">Dar formato a los datos como fecha</span><span class="sxs-lookup"><span data-stu-id="014bb-115">Format Data as Date</span></span>](#FormatDate)  
  
4.  [<span data-ttu-id="014bb-116">Cambiar el ancho de columna</span><span class="sxs-lookup"><span data-stu-id="014bb-116">Change Column Widths</span></span>](#Width)  
  
5.  [<span data-ttu-id="014bb-117">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="014bb-117">Add a Report Title</span></span>](#Title)  
  
6.  [<span data-ttu-id="014bb-118">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="014bb-118">Save the Report</span></span>](#Save)  
  
7.  [<span data-ttu-id="014bb-119">Exportar el informe</span><span class="sxs-lookup"><span data-stu-id="014bb-119">Export the Report</span></span>](#Export)  
  
 <span data-ttu-id="014bb-120">Tiempo estimado para completar este tutorial: 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="014bb-120">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="014bb-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="014bb-121">Requirements</span></span>  
 <span data-ttu-id="014bb-122">Para obtener más información sobre los requisitos, consulte [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="014bb-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-new-report-from-getting-started"></a><a name="CreateTable"></a><span data-ttu-id="014bb-123">1. crear un nuevo informe a partir de Introducción</span><span class="sxs-lookup"><span data-stu-id="014bb-123">1. Create a New Report from Getting Started</span></span>  
 <span data-ttu-id="014bb-124">Cree un informe de tabla en el cuadro de diálogo **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="014bb-124">Create a table report from the **Getting Started** dialog box.</span></span> <span data-ttu-id="014bb-125">Existen dos modos: diseño de informe y el diseño de conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="014bb-125">There are two modes: report design and shared dataset design.</span></span> <span data-ttu-id="014bb-126">En el modo de diseño de informe, los datos se especifican en el panel Datos de informe y el diseño del informe se especifica en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="014bb-126">In report design mode, you specify data in the Report Data pane and the report layout on the design surface.</span></span> <span data-ttu-id="014bb-127">En modo de diseño de conjunto de datos compartido, se crean consultas de conjunto de datos para compartir con otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="014bb-127">In shared dataset design mode, you create dataset queries to share with others.</span></span> <span data-ttu-id="014bb-128">En este tutorial, utilizará el modo de diseño de informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-128">In this tutorial, you will be using report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="014bb-129">Para crear un informe nuevo</span><span class="sxs-lookup"><span data-stu-id="014bb-129">To create a new report</span></span>  
  
1.  <span data-ttu-id="014bb-130">Haga clic en **Inicio**, seleccione **Programas**, **Generador de informes de Microsoft SQL Server 2012**y, a continuación, haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="014bb-130">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="014bb-131">Se abre el cuadro de diálogo **Introducción**.</span><span class="sxs-lookup"><span data-stu-id="014bb-131">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="014bb-132">Si el cuadro de diálogo **Introducción** no aparece, en el botón **generador de informes** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="014bb-132">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="014bb-133">En el panel de la izquierda, compruebe que está seleccionada la opción **Nuevo informe** .</span><span class="sxs-lookup"><span data-stu-id="014bb-133">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="014bb-134">En el panel derecho, compruebe que **Asistente para tabla o matriz** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="014bb-134">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection-in-the-table-wizard"></a><a name="DataConnection"></a><span data-ttu-id="014bb-135">1Una.</span><span class="sxs-lookup"><span data-stu-id="014bb-135">1a.</span></span> <span data-ttu-id="014bb-136">Especificar una conexión de datos en el Asistente para tablas</span><span class="sxs-lookup"><span data-stu-id="014bb-136">Specify a Data Connection in the Table Wizard</span></span>  
 <span data-ttu-id="014bb-137">Una conexión de datos contiene la información para conectarse a un origen de datos externo, por ejemplo una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="014bb-137">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="014bb-138">Normalmente, la información de conexión y el tipo de credenciales que se debe usar utilizar se obtienen del propietario del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="014bb-138">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span> <span data-ttu-id="014bb-139">Para especificar una conexión de datos, puede utilizar un origen de datos compartido del servidor de informes o crear un origen de datos incrustado que solo se utilice en este informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-139">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span>  
  
 <span data-ttu-id="014bb-140">En este tutorial, utilizará un origen del datos incrustado.</span><span class="sxs-lookup"><span data-stu-id="014bb-140">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="014bb-141">Para obtener más información sobre cómo usar orígenes de datos compartidos, consulte [Maneras alternativas de obtener una conexión de datos &#40;Generador de informes&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="014bb-141">To learn more about using a shared data sources, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="014bb-142">Para crear un origen de datos incrustado</span><span class="sxs-lookup"><span data-stu-id="014bb-142">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="014bb-143">En la página **Elegir un conjunto de datos** , seleccione **Crear un conjunto de datos**y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="014bb-143">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="014bb-144">Se abre la página **Elegir una conexión a un origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="014bb-144">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="014bb-145">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="014bb-145">Click **New**.</span></span> <span data-ttu-id="014bb-146">Se abre el cuadro de diálogo **Propiedades del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="014bb-146">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="014bb-147">En **nombre**, escriba **Product sales** nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="014bb-147">In **Name**, type **Product Sales** a name for the data source.</span></span>  
  
4.  <span data-ttu-id="014bb-148">En **Seleccionar un tipo de conexión**, compruebe que está seleccionado **Microsoft SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="014bb-148">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
5.  <span data-ttu-id="014bb-149">En **cadena de conexión**, escriba el siguiente texto, donde *\<servername>* es el nombre de una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="014bb-149">In **Connection string**, type the following text, where *\<servername>* is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
    ```  
    Data Source=<servername>  
    ```  
  
     <span data-ttu-id="014bb-150">Puesto que va a usar una consulta con los datos en lugar de recuperar los datos de una base de datos, la cadena de conexión no incluye el nombre de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="014bb-150">Because you will use a query that contains the data instead of retrieving the data from a database, the connection string does not include the database name.</span></span> <span data-ttu-id="014bb-151">Para obtener más información, consulte [Requisitos previos para los tutoriales&#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="014bb-151">For more information, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
6.  <span data-ttu-id="014bb-152">Haga clic en **Credenciales**.</span><span class="sxs-lookup"><span data-stu-id="014bb-152">Click **Credentials**.</span></span> <span data-ttu-id="014bb-153">Escriba las credenciales necesarias para tener acceso al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="014bb-153">Enter the credentials that you need to access the external data source.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="014bb-154">Volverá a encontrarse en la página **Elegir una conexión a un origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="014bb-154">You are back on the **Choose a connection to a data source** page.</span></span>  
  
8.  <span data-ttu-id="014bb-155">Para comprobar que se puede conectar al origen de datos, haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="014bb-155">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="014bb-156">Aparece un mensaje que indica que la conexión se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="014bb-156">The message "Connection created successfully" appears.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="014bb-157">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="014bb-157">Click **Next**.</span></span>  
  
##  <a name="1b-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="014bb-158">ter.</span><span class="sxs-lookup"><span data-stu-id="014bb-158">1b.</span></span> <span data-ttu-id="014bb-159">Crear una consulta en el Asistente para tablas</span><span class="sxs-lookup"><span data-stu-id="014bb-159">Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="014bb-160">En un informe puede usar un conjunto de datos compartido que tenga una consulta predefinida o crear un conjunto de datos incrustado para usarlo exclusivamente en ese informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-160">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="014bb-161">En este tutorial, creará un conjunto de datos incrustado.</span><span class="sxs-lookup"><span data-stu-id="014bb-161">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="014bb-162">En este tutorial, la consulta contiene los valores de datos, de forma que no necesita un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="014bb-162">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="014bb-163">Esto hace que la consulta requiera bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="014bb-163">This makes the query quite long.</span></span> <span data-ttu-id="014bb-164">En un entorno empresarial, la consulta no contendría los datos.</span><span class="sxs-lookup"><span data-stu-id="014bb-164">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="014bb-165">Esto es solo con fines de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="014bb-165">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="014bb-166">Para crear una consulta</span><span class="sxs-lookup"><span data-stu-id="014bb-166">To create a query</span></span>  
  
1.  <span data-ttu-id="014bb-167">En la página **Diseñar una consulta** , el diseñador de consultas relacionales está abierto.</span><span class="sxs-lookup"><span data-stu-id="014bb-167">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="014bb-168">En este tutorial, usará el diseñador de consultas basado en texto.</span><span class="sxs-lookup"><span data-stu-id="014bb-168">For this tutorial, you will use the text-based query designer.</span></span>  
  
     <span data-ttu-id="014bb-169">Haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="014bb-169">Click **Edit As Text**.</span></span> <span data-ttu-id="014bb-170">El diseñador de consultas basado en texto muestra un panel de consulta y un panel de resultados.</span><span class="sxs-lookup"><span data-stu-id="014bb-170">The text-based query designer displays a query pane and a results pane.</span></span>  
  
2.  <span data-ttu-id="014bb-171">Pegue la siguiente consulta [!INCLUDE[tsql](../includes/tsql-md.md)] en el cuadro **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="014bb-171">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(9924.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Mini Battery Charger' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Telephoto Conversion Lens' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,'Accessories' as Subcategory,    
       'USB Cable' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Business Videographer' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-10' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Social Videographer' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2009-01-11' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Advanced Digital' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Compact Digital' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2009-01-08' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Consumer Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-09' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera 35mm' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2009-01-07' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'SLR Camera' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
  
    ```  
  
3.  <span data-ttu-id="014bb-172">En la barra de herramientas del diseñador de consultas, haga clic en **Ejecutar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="014bb-172">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="014bb-173">La consulta se ejecuta y muestra el conjunto de resultados para los campos SalesDate, Subcategory, Product, Sales y Quantity.</span><span class="sxs-lookup"><span data-stu-id="014bb-173">The query runs and displays the result set for the fields SalesDate, Subcategory, Product, Sales, and Quantity.</span></span>  
  
     <span data-ttu-id="014bb-174">En el conjunto de resultados, los encabezados de columna están basados en los nombres de la consulta.</span><span class="sxs-lookup"><span data-stu-id="014bb-174">In the result set, the column headings are based on the names in the query.</span></span> <span data-ttu-id="014bb-175">En el conjunto de datos, los encabezados de columna se convierten en nombres de campo y se guardan en el informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-175">In the dataset, the column headings become the field names, and are saved in the report.</span></span> <span data-ttu-id="014bb-176">Después de completar el asistente, puede usar el panel Datos de informe para ver la colección de campos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="014bb-176">After you complete the wizard, you can use the Report Data pane to view the collection of dataset fields.</span></span>  
  
4.  <span data-ttu-id="014bb-177">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="014bb-177">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups-in-the-table-wizard"></a><a name="Groups"></a><span data-ttu-id="014bb-178">1C.</span><span class="sxs-lookup"><span data-stu-id="014bb-178">1c.</span></span> <span data-ttu-id="014bb-179">Organizar datos en grupos en el Asistente para tablas</span><span class="sxs-lookup"><span data-stu-id="014bb-179">Organize Data into Groups in the Table Wizard</span></span>  
 <span data-ttu-id="014bb-180">Al seleccionar los campos por los que desea agrupar, diseña una tabla que tiene filas y columnas en las que se muestran datos detallados y datos agregados.</span><span class="sxs-lookup"><span data-stu-id="014bb-180">When you select fields to group on, you design a table that has rows and columns that display detail data and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="014bb-181">Para organizar los datos en grupos</span><span class="sxs-lookup"><span data-stu-id="014bb-181">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="014bb-182">En la página **organizar campos** , arrastre Product hasta **valores**.</span><span class="sxs-lookup"><span data-stu-id="014bb-182">On the **Arrange fields** page, drag Product to **Values**.</span></span>  
  
2.  <span data-ttu-id="014bb-183">Arrastre Quantity hasta **Valores** y colóquelo debajo de Product.</span><span class="sxs-lookup"><span data-stu-id="014bb-183">Drag Quantity to **Values** and place below Product.</span></span>  
  
     <span data-ttu-id="014bb-184">Quantity se suma automáticamente mediante la función Sum, que es el agregado predeterminado para los campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="014bb-184">Quantity is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="014bb-185">El valor es [Sum(Quantity)].</span><span class="sxs-lookup"><span data-stu-id="014bb-185">The value is [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="014bb-186">Puede abrir la lista desplegable para ver las demás funciones de agregado disponibles.</span><span class="sxs-lookup"><span data-stu-id="014bb-186">You can open the drop-down list to view the other aggregate functions available.</span></span> <span data-ttu-id="014bb-187">No cambie la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="014bb-187">Do not change the aggregate function.</span></span>  
  
3.  <span data-ttu-id="014bb-188">Arrastre Sales hasta **Valores** y colóquelo debajo de [Sum(Quantity)].</span><span class="sxs-lookup"><span data-stu-id="014bb-188">Drag Sales to **Values** and place below [Sum(Quantity)].</span></span>  
  
     <span data-ttu-id="014bb-189">La función Sum agrega Sales.</span><span class="sxs-lookup"><span data-stu-id="014bb-189">Sales is aggregated by the Sum function.</span></span> <span data-ttu-id="014bb-190">El valor es [Sum(Sales)].</span><span class="sxs-lookup"><span data-stu-id="014bb-190">The value is [Sum(Sales)].</span></span>  
  
     <span data-ttu-id="014bb-191">Los pasos 1, 2 y 3 especifican los datos que deben mostrarse en la tabla.</span><span class="sxs-lookup"><span data-stu-id="014bb-191">Steps 1, 2, and 3 specify the data to display in the table.</span></span>  
  
4.  <span data-ttu-id="014bb-192">Arrastre SalesDate hasta **Grupos de filas**.</span><span class="sxs-lookup"><span data-stu-id="014bb-192">Drag SalesDate to **Row groups**.</span></span>  
  
5.  <span data-ttu-id="014bb-193">Arrastre Subcategory hasta **Grupos de filas** y colóquelo debajo de SalesDate.</span><span class="sxs-lookup"><span data-stu-id="014bb-193">Drag Subcategory to **Row groups** and place below SalesDate.</span></span>  
  
     <span data-ttu-id="014bb-194">Los pasos 4 y 5 organizan los valores de los campos primero por fecha y, después, por la subcategoría de producto de esa fecha.</span><span class="sxs-lookup"><span data-stu-id="014bb-194">Steps 4 and 5 organize the values for the fields first by date, and then by product subcategory for that date.</span></span>  
  
6.  <span data-ttu-id="014bb-195">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="014bb-195">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotal-and-total-rows-in-the-table-wizard"></a><a name="Subtotals"></a><span data-ttu-id="014bb-196">1D.</span><span class="sxs-lookup"><span data-stu-id="014bb-196">1d.</span></span> <span data-ttu-id="014bb-197">Agregar filas de subtotal y de total en el Asistente para tablas</span><span class="sxs-lookup"><span data-stu-id="014bb-197">Add Subtotal and Total Rows in the Table Wizard</span></span>  
 <span data-ttu-id="014bb-198">Después de crear grupos, puede agregar filas y darles formato, para mostrar en ellas los valores agregados de los campos.</span><span class="sxs-lookup"><span data-stu-id="014bb-198">After you create groups, you can add and format rows on which to display aggregate values for the fields.</span></span> <span data-ttu-id="014bb-199">Puede decidir si mostrar todos los datos o permitir que los usuarios expandan y contraigan de forma interactiva los datos agrupados.</span><span class="sxs-lookup"><span data-stu-id="014bb-199">You can choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="014bb-200">Para agregar subtotales y totales</span><span class="sxs-lookup"><span data-stu-id="014bb-200">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="014bb-201">En la página **Elegir el diseño** , en **Opciones**, compruebe que esté seleccionada la opción **Mostrar subtotales y totales generales** .</span><span class="sxs-lookup"><span data-stu-id="014bb-201">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
2.  <span data-ttu-id="014bb-202">Compruebe que esté seleccionada la opción **Bloqueado, subtotal abajo** .</span><span class="sxs-lookup"><span data-stu-id="014bb-202">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
     <span data-ttu-id="014bb-203">El panel Vista previa del asistente muestra una tabla con cinco filas.</span><span class="sxs-lookup"><span data-stu-id="014bb-203">The wizard Preview pane displays a table with five rows.</span></span> <span data-ttu-id="014bb-204">Al ejecutar el informe, cada fila se mostrará de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="014bb-204">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="014bb-205">La primera fila se repetirá una vez en la tabla para mostrar los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="014bb-205">The first row will repeat once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="014bb-206">La segunda fila se repetirá una vez en cada artículo de línea del pedido de venta y mostrará el nombre del producto, la cantidad del pedido y el total de línea.</span><span class="sxs-lookup"><span data-stu-id="014bb-206">The second row will repeat once for each line item in the sales order and display the product name, order quantity, and line total.</span></span>  
  
    3.  <span data-ttu-id="014bb-207">La tercera fila se repetirá una vez en cada pedido de venta para mostrar los subtotales de cada pedido.</span><span class="sxs-lookup"><span data-stu-id="014bb-207">The third row will repeat once for each sales order to display subtotals per order.</span></span>  
  
    4.  <span data-ttu-id="014bb-208">La cuarta fila se repetirá una vez en cada fecha de pedido para mostrar los subtotales por día.</span><span class="sxs-lookup"><span data-stu-id="014bb-208">The fourth row will repeat once for each order date to display the subtotals per day.</span></span>  
  
    5.  <span data-ttu-id="014bb-209">La quinta fila se repetirá una vez en la tabla para mostrar los totales generales.</span><span class="sxs-lookup"><span data-stu-id="014bb-209">The fifth row will repeat once for the table to display the grand totals.</span></span>  
  
3.  <span data-ttu-id="014bb-210">Desactive la opción **Expandir o contraer grupos**.</span><span class="sxs-lookup"><span data-stu-id="014bb-210">Clear the option **Expand/collapse groups**.</span></span> <span data-ttu-id="014bb-211">En este tutorial, el informe creado no usa la característica de obtención de detalles que permite a un usuario expandir una jerarquía de grupos primarios para mostrar filas de grupos secundarios y filas de detalles.</span><span class="sxs-lookup"><span data-stu-id="014bb-211">In this tutorial, the report you create does not use the drilldown feature that lets a user expand a parent group hierarchy to display child group rows and detail rows.</span></span>  
  
4.  <span data-ttu-id="014bb-212">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="014bb-212">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style-in-the-table-wizard"></a><a name="Style"></a><span data-ttu-id="014bb-213">1E.</span><span class="sxs-lookup"><span data-stu-id="014bb-213">1e.</span></span> <span data-ttu-id="014bb-214">Elegir un estilo en el Asistente para tablas</span><span class="sxs-lookup"><span data-stu-id="014bb-214">Choose a Style in the Table Wizard</span></span>  
 <span data-ttu-id="014bb-215">Un estilo especifica un estilo de fuente, un conjunto de colores y un estilo de borde.</span><span class="sxs-lookup"><span data-stu-id="014bb-215">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-table-style"></a><span data-ttu-id="014bb-216">Para especificar un estilo de tabla</span><span class="sxs-lookup"><span data-stu-id="014bb-216">To specify a table style</span></span>  
  
1.  <span data-ttu-id="014bb-217">En la página **elegir un estilo** , en el panel estilos, seleccione oceánico.</span><span class="sxs-lookup"><span data-stu-id="014bb-217">On the **Choose a Style** page, in the Styles pane, select Ocean.</span></span>  
  
     <span data-ttu-id="014bb-218">El panel Vista previa muestra un ejemplo de la tabla con ese estilo.</span><span class="sxs-lookup"><span data-stu-id="014bb-218">The Preview pane displays a sample of the table with that style.</span></span>  
  
2.  <span data-ttu-id="014bb-219">Opcionalmente, haga clic en los otros estilos para ver el ejemplo con ellos aplicados.</span><span class="sxs-lookup"><span data-stu-id="014bb-219">Optionally, click the other styles to see the sample with them applied.</span></span>  
  
3.  <span data-ttu-id="014bb-220">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="014bb-220">Click **Finish**.</span></span>  
  
 <span data-ttu-id="014bb-221">La tabla se agrega a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="014bb-221">The table is added to the design surface.</span></span> <span data-ttu-id="014bb-222">La tabla tiene 5 columnas y 5 filas.</span><span class="sxs-lookup"><span data-stu-id="014bb-222">The table has 5 columns and 5 rows.</span></span> <span data-ttu-id="014bb-223">El panel Grupos de filas muestra tres grupos de filas: SalesDate, Subcategory y Details.</span><span class="sxs-lookup"><span data-stu-id="014bb-223">The Row Groups pane shows three row groups: SalesDate, Subcategory, and Details.</span></span> <span data-ttu-id="014bb-224">Los datos detallados son todos los datos recuperados por la consulta del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="014bb-224">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="014bb-225">2. dar formato a los datos como moneda</span><span class="sxs-lookup"><span data-stu-id="014bb-225">2. Format Data as Currency</span></span>  
 <span data-ttu-id="014bb-226">De forma predeterminada, los datos de resumen del campo Sales se muestran en forma de número general.</span><span class="sxs-lookup"><span data-stu-id="014bb-226">By default, the summary data for the Sales field displays a general number.</span></span> <span data-ttu-id="014bb-227">Aplíquele el formato adecuado para mostrar el número como moneda.</span><span class="sxs-lookup"><span data-stu-id="014bb-227">Format it to display the number as currency.</span></span> <span data-ttu-id="014bb-228">Alterne **Estilos de marcador de posición** para mostrar los cuadros de texto con formato y el texto de marcador de posición como valores de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="014bb-228">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="014bb-229">Para dar formato a un campo de moneda</span><span class="sxs-lookup"><span data-stu-id="014bb-229">To format a currency field</span></span>  
  
1.  <span data-ttu-id="014bb-230">Haga clic en **Diseño** para cambiar a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="014bb-230">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="014bb-231">Haga clic en la celda en la segunda fila (bajo la fila de encabezados de columna) en la columna Sales y arrástrela hacia abajo para seleccionar todas las celdas que contienen `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="014bb-231">Click the cell in the second row (under the column headings row) in the Sales column and drag down to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="014bb-232">En la pestaña **Inicio** , en el grupo **Número** , haga clic en el botón **Moneda** .</span><span class="sxs-lookup"><span data-stu-id="014bb-232">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="014bb-233">Las celdas cambian para mostrar la moneda con formato.</span><span class="sxs-lookup"><span data-stu-id="014bb-233">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="014bb-234">Si la configuración regional es Inglés (Estados Unidos), el texto de ejemplo predeterminado es [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="014bb-234">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="014bb-235">Si no ve un valor de moneda de ejemplo, haga clic en **estilos de marcador de posición** en el grupo **números** y, a continuación, haga clic en **valores de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="014bb-235">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="014bb-236">Haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-236">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="014bb-237">Los valores de resumen de Sales se muestran como moneda.</span><span class="sxs-lookup"><span data-stu-id="014bb-237">The summary values for Sales display as currency.</span></span>  
  
##  <a name="3-format-data-as-date"></a><a name="FormatDate"></a><span data-ttu-id="014bb-238">3. dar formato a los datos como fecha</span><span class="sxs-lookup"><span data-stu-id="014bb-238">3. Format Data as Date</span></span>  
 <span data-ttu-id="014bb-239">De forma predeterminada, en el campo SalesDate se muestra información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="014bb-239">By default, the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="014bb-240">Puede darle formato para mostrar solo la fecha.</span><span class="sxs-lookup"><span data-stu-id="014bb-240">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="014bb-241">Para dar formato a un campo de fecha como el formato predeterminado</span><span class="sxs-lookup"><span data-stu-id="014bb-241">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="014bb-242">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="014bb-242">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="014bb-243">Haga clic en la celda que contiene `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="014bb-243">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="014bb-244">En la cinta de opciones, en la pestaña **Inicio** , en el grupo **número** , en la lista desplegable, seleccione **fecha**.</span><span class="sxs-lookup"><span data-stu-id="014bb-244">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="014bb-245">La celda muestra la fecha de ejemplo **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="014bb-245">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="014bb-246">Si no ve un valor de fecha de ejemplo, haga clic en **Estilos de marcador de posición** en el grupo **Números** y, después, haga clic en **Valores de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="014bb-246">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="014bb-247">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-247">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="014bb-248">Los valores SalesDate se muestran en el formato de fecha predeterminado.</span><span class="sxs-lookup"><span data-stu-id="014bb-248">The SalesDate values display in the default date format.</span></span>  
  
#### <a name="to-change-the-date-format-to-a-custom-format"></a><span data-ttu-id="014bb-249">Para cambiar el formato de fecha a un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="014bb-249">To change the date format to a custom format</span></span>  
  
1.  <span data-ttu-id="014bb-250">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="014bb-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="014bb-251">Haga clic en la celda que contiene `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="014bb-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="014bb-252">En la pestaña **Inicio** , en el grupo **número** , haga clic en el iniciador del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="014bb-252">On the **Home** tab, in the **Number** group, click the dialog box launcher.</span></span>  
  
     <span data-ttu-id="014bb-253">El selector es la pequeña flecha situada en la esquina derecha del grupo.</span><span class="sxs-lookup"><span data-stu-id="014bb-253">The launcher is the small arrow in the right-hand corner of the group.</span></span> <span data-ttu-id="014bb-254">Se abre el cuadro de diálogo **Propiedades del cuadro de texto** .</span><span class="sxs-lookup"><span data-stu-id="014bb-254">The **Text Box Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="014bb-255">En el panel Categoría, compruebe que está seleccionada la opción **Fecha** .</span><span class="sxs-lookup"><span data-stu-id="014bb-255">In the Category pane, verify that **Date** is selected.</span></span>  
  
5.  <span data-ttu-id="014bb-256">En el panel **Tipo** , seleccione **31 de enero de 2000**.</span><span class="sxs-lookup"><span data-stu-id="014bb-256">In the **Type** pane, select **January 31, 2000**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="014bb-257">La celda muestra la fecha de ejemplo **[31 de enero de 2000]**.</span><span class="sxs-lookup"><span data-stu-id="014bb-257">The cell displays the example date **[January 31, 2000]**.</span></span>  
  
7.  <span data-ttu-id="014bb-258">Haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-258">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="014bb-259">El valor SalesDate se muestra con el nombre del mes en lugar del número del mes.</span><span class="sxs-lookup"><span data-stu-id="014bb-259">The SalesDate value displays with the name of the month instead of the number for the month.</span></span>  
  
##  <a name="4-change-column-widths"></a><a name="Width"></a><span data-ttu-id="014bb-260">4. cambiar el ancho de las columnas</span><span class="sxs-lookup"><span data-stu-id="014bb-260">4. Change Column Widths</span></span>  
 <span data-ttu-id="014bb-261">De forma predeterminada, cada celda de una tabla contiene un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="014bb-261">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="014bb-262">Un cuadro de texto se expande verticalmente para alojar el texto cuando se representa la página.</span><span class="sxs-lookup"><span data-stu-id="014bb-262">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="014bb-263">En el informe representado, cada fila se expande hasta el alto del cuadro de texto más alto representado de la fila.</span><span class="sxs-lookup"><span data-stu-id="014bb-263">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="014bb-264">El alto de la fila en la superficie de diseño no tiene efecto alguno en el alto de la fila en el informe representado.</span><span class="sxs-lookup"><span data-stu-id="014bb-264">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="014bb-265">Para reducir la cantidad de espacio vertical que ocupa cada fila, expanda el ancho de columna para dar cabida en una línea al contenido previsto de los cuadros de texto de la columna.</span><span class="sxs-lookup"><span data-stu-id="014bb-265">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-table-columns"></a><span data-ttu-id="014bb-266">Para cambiar el ancho de las columnas de la tabla</span><span class="sxs-lookup"><span data-stu-id="014bb-266">To change the width of table columns</span></span>  
  
1.  <span data-ttu-id="014bb-267">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="014bb-267">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="014bb-268">Haga clic en la tabla para que los identificadores de columna y de fila aparezcan encima y al lado de la tabla.</span><span class="sxs-lookup"><span data-stu-id="014bb-268">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="014bb-269">Las barras grises situadas en la parte superior y en el lado de la tabla son los identificadores de fila y de columna.</span><span class="sxs-lookup"><span data-stu-id="014bb-269">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="014bb-270">Sitúe el cursor en la línea que hay entre los controladores de columna para que cambie a una flecha doble.</span><span class="sxs-lookup"><span data-stu-id="014bb-270">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="014bb-271">Arrastre las columnas hasta que tengan el tamaño deseado.</span><span class="sxs-lookup"><span data-stu-id="014bb-271">Drag the columns to the size you want.</span></span> <span data-ttu-id="014bb-272">Por ejemplo, expanda la columna Producto para que el nombre de producto se muestre en una línea.</span><span class="sxs-lookup"><span data-stu-id="014bb-272">For example, expand the column for Product so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="014bb-273">Haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-273">Click **Run** to preview your report.</span></span>  
  
##  <a name="5-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="014bb-274">5. agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="014bb-274">5. Add a Report Title</span></span>  
 <span data-ttu-id="014bb-275">Los títulos de informe aparecen en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="014bb-275">A report title appears at the top of the report.</span></span> <span data-ttu-id="014bb-276">Puede situar el título del informe en un encabezado de informe o, si el informe no lo utiliza, en un cuadro de texto en la parte superior del cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-276">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="014bb-277">En este tutorial, deberá utilizar el cuadro de texto que se coloca automáticamente en la parte superior del cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-277">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="014bb-278">El texto se puede mejorar aún más aplicando estilos de fuente, tamaños y colores diferentes a las frases y caracteres individuales.</span><span class="sxs-lookup"><span data-stu-id="014bb-278">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="014bb-279">Para obtener más información, vea [Dar formato al texto en un cuadro de texto &#40;Generador de informes y SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="014bb-279">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="014bb-280">Para agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="014bb-280">To add a report title</span></span>  
  
1.  <span data-ttu-id="014bb-281">En la superficie de diseño, haga clic en **Haga clic para agregar título**.</span><span class="sxs-lookup"><span data-stu-id="014bb-281">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="014bb-282">Escriba **Ventas del producto**y después haga clic fuera del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="014bb-282">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="014bb-283">Haga clic con el botón secundario en el cuadro de texto que contiene **Ventas del producto** y haga clic en **Propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="014bb-283">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="014bb-284">En el cuadro de diálogo **Propiedades de cuadro de texto** , haga clic en **Fuente**.</span><span class="sxs-lookup"><span data-stu-id="014bb-284">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="014bb-285">En la lista **Tamaño** , seleccione **18 pt**.</span><span class="sxs-lookup"><span data-stu-id="014bb-285">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="014bb-286">En la lista **Color** , seleccione **Azul aciano**.</span><span class="sxs-lookup"><span data-stu-id="014bb-286">In the **Color** list, select **Cornflower Blue**.</span></span>  
  
7.  <span data-ttu-id="014bb-287">Seleccione **Negrita**.</span><span class="sxs-lookup"><span data-stu-id="014bb-287">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report"></a><a name="Save"></a><span data-ttu-id="014bb-288">6. guardar el informe</span><span class="sxs-lookup"><span data-stu-id="014bb-288">6. Save the Report</span></span>  
 <span data-ttu-id="014bb-289">Guarde el informe un servidor de informes o en su equipo.</span><span class="sxs-lookup"><span data-stu-id="014bb-289">Save the report to a report server or your computer.</span></span> <span data-ttu-id="014bb-290">Si no guarda el informe en el servidor de informes, varias características de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , como los elementos de informe y los subinformes, no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="014bb-290">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="014bb-291">Para guardar el informe en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="014bb-291">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="014bb-292">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="014bb-292">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="014bb-293">Haga clic en **Sitios y servidores recientes**.</span><span class="sxs-lookup"><span data-stu-id="014bb-293">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="014bb-294">Seleccione o escriba el nombre del servidor de informes donde tiene el permiso para guardar los informes.</span><span class="sxs-lookup"><span data-stu-id="014bb-294">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="014bb-295">Aparecerá el mensaje "Conectando con el servidor de informes".</span><span class="sxs-lookup"><span data-stu-id="014bb-295">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="014bb-296">Una vez completada la conexión, se mostrará el contenido de la carpeta de informes que el administrador del servidor de informes especificó como ubicación predeterminada para los informes.</span><span class="sxs-lookup"><span data-stu-id="014bb-296">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="014bb-297">En **Nombre**, reemplace el nombre predeterminado por **Ventas de producto**.</span><span class="sxs-lookup"><span data-stu-id="014bb-297">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="014bb-298">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="014bb-298">Click **Save**.</span></span>  
  
 <span data-ttu-id="014bb-299">El informe se guarda en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="014bb-299">The report is saved to the report server.</span></span> <span data-ttu-id="014bb-300">El nombre del servidor de informes al que está conectado aparecerá en la barra de estado en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="014bb-300">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="014bb-301">Para guardar el informe en el equipo</span><span class="sxs-lookup"><span data-stu-id="014bb-301">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="014bb-302">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="014bb-302">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="014bb-303">Haga clic en **Escritorio**, **Mis documentos**o **Mi PC**y vaya a la carpeta donde quiere guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-303">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="014bb-304">En **Nombre**, reemplace el nombre predeterminado por **Ventas de producto**.</span><span class="sxs-lookup"><span data-stu-id="014bb-304">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="014bb-305">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="014bb-305">Click **Save**.</span></span>  
  
##  <a name="7-export-the-report"></a><a name="Export"></a><span data-ttu-id="014bb-306">7. exportar el informe</span><span class="sxs-lookup"><span data-stu-id="014bb-306">7. Export the Report</span></span>  
 <span data-ttu-id="014bb-307">Los informes se pueden exportar a diversos formatos, por ejemplo Microsoft Excel y valores separados por comas (CSV).</span><span class="sxs-lookup"><span data-stu-id="014bb-307">Reports can be exported to different formats such Microsoft Excel and comma separated value (CSV).</span></span> <span data-ttu-id="014bb-308">Para obtener más información, vea [exportar informes &#40;generador de informes y SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="014bb-308">For more information, see [Exporting Reports &#40;Report Builder and SSRS&#41;](report-builder/export-reports-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="014bb-309">En este tutorial, exportará el informe a Excel y establecerá una propiedad en el informe para proporcionar un nombre personalizado para la pestaña del libro.</span><span class="sxs-lookup"><span data-stu-id="014bb-309">In this tutorial, you will export the report to Excel and set a property on the report to provide a custom name for the workbook tab.</span></span>  
  
#### <a name="to-specify-the-workbook-tab-name"></a><span data-ttu-id="014bb-310">Para especificar el nombre de la pestaña del libro</span><span class="sxs-lookup"><span data-stu-id="014bb-310">To specify the workbook tab name</span></span>  
  
1.  <span data-ttu-id="014bb-311">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="014bb-311">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="014bb-312">Haga clic en cualquier lugar fuera del informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-312">Click anywhere outside the report.</span></span>  
  
3.  <span data-ttu-id="014bb-313">. En el panel Propiedades, busque la propiedad InitialPageName y escriba **Excel de ventas del producto**.</span><span class="sxs-lookup"><span data-stu-id="014bb-313">.In the Properties pane, locate the InitialPageName property and type **Product Sales Excel**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="014bb-314">Si el panel Propiedades no está visible, haga clic en la pestaña vista de la cinta de opciones y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="014bb-314">If the Properties pane is not visible, click the View tab on the ribbon, and then click **Properties**.</span></span>  
  
#### <a name="to-export-a-report-to-excel"></a><span data-ttu-id="014bb-315">Exportar un informe a Excel</span><span class="sxs-lookup"><span data-stu-id="014bb-315">To export a report to Excel</span></span>  
  
1.  <span data-ttu-id="014bb-316">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="014bb-316">Click **Run** to preview the report.</span></span>  
  
2.  <span data-ttu-id="014bb-317">. En la cinta de opciones, haga clic en **exportar**y, a continuación, en **Excel**.</span><span class="sxs-lookup"><span data-stu-id="014bb-317">.On the ribbon, click **Export**, and then click **Excel**.</span></span>  
  
     <span data-ttu-id="014bb-318">Se abre el cuadro de diálogo **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="014bb-318">The **Save As** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="014bb-319">Vaya a la carpeta **documentos** .</span><span class="sxs-lookup"><span data-stu-id="014bb-319">Browse to the **Documents** folder.</span></span>  
  
4.  <span data-ttu-id="014bb-320">En el cuadro de texto **nombre de archivo** , escriba Excel de **ventas del producto**.</span><span class="sxs-lookup"><span data-stu-id="014bb-320">In the **File name** text box, type **Product Sales Excel**.</span></span>  
  
5.  <span data-ttu-id="014bb-321">Compruebe que el tipo de archivo es **libro de Excel**.</span><span class="sxs-lookup"><span data-stu-id="014bb-321">Verify that the file type is **Excel Workbook**.</span></span>  
  
6.  <span data-ttu-id="014bb-322">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="014bb-322">Click **Save**.</span></span>  
  
#### <a name="to-view-the-report-in-excel"></a><span data-ttu-id="014bb-323">Ver el informe en Excel.</span><span class="sxs-lookup"><span data-stu-id="014bb-323">To view the report in Excel</span></span>  
  
1.  <span data-ttu-id="014bb-324">Abra la carpeta **documentos** y haga doble clic en **Product sales Excel.xlsx**.</span><span class="sxs-lookup"><span data-stu-id="014bb-324">Open the **Documents** folder and double click **Product Sales Excel.xlsx**.</span></span>  
  
2.  <span data-ttu-id="014bb-325">Compruebe que el nombre de la pestaña del libro es **Excel de Ventas del producto**.</span><span class="sxs-lookup"><span data-stu-id="014bb-325">Verify that the name of the workbook tab is **Product Sales Excel**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="014bb-326">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="014bb-326">Next Steps</span></span>  
 <span data-ttu-id="014bb-327">Aquí termina el tutorial sobre la creación de un informe de tabla básico.</span><span class="sxs-lookup"><span data-stu-id="014bb-327">This concludes the walkthrough for how to create a basic table report.</span></span> <span data-ttu-id="014bb-328">Para obtener más información, consulte [Tablas, matrices y listas &#40;Generador de informes y SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="014bb-328">For more information about tables, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="014bb-329">Consulte también</span><span class="sxs-lookup"><span data-stu-id="014bb-329">See Also</span></span>  
 <span data-ttu-id="014bb-330">[Tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="014bb-330">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="014bb-331">Generador de informes en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="014bb-331">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
