---
title: 'Tutorial: Agregar un minigráfico a un informe (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 18c90a36-48bf-4805-a960-2d1e8f00c2dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb1bf83810b6c743b977e399864ce2edd514f572
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747931"
---
# <a name="tutorial-add-a-sparkline-to-your-report-report-builder"></a><span data-ttu-id="17212-102">Tutorial: Agregar un minigráfico a un informe (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="17212-102">Tutorial: Add a Sparkline to Your Report (Report Builder)</span></span>
  <span data-ttu-id="17212-103">En este tutorial, crea un informe de la tabla básico basado en datos de ventas de ejemplo y, a continuación, agrega un minigráfico a una celda de la tabla.</span><span class="sxs-lookup"><span data-stu-id="17212-103">In this tutorial, you create a basic table report based on sample sales data, and then add a sparkline chart to a cell in the table.</span></span>  
  
 <span data-ttu-id="17212-104">Una versión mejorada del informe que creará en este tutorial está disponible como informe de ejemplo del Generador de informes de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17212-104">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="17212-105">Para obtener más información acerca de cómo descargar este informe de ejemplo y otros, vea [generador de informes informes de ejemplo](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="17212-105">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span> <span data-ttu-id="17212-106">La siguiente ilustración muestra un informe de ejemplo similar al que creará.</span><span class="sxs-lookup"><span data-stu-id="17212-106">The following illustration shows the sample report similar to the one that you will create.</span></span>  
  
 <span data-ttu-id="17212-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span><span class="sxs-lookup"><span data-stu-id="17212-107">![rs_SparklineMatrixTutorial](../../2014/tutorials/media/rs-sparklinematrixtutorial.gif "rs_SparklineMatrixTutorial")</span></span>  
  
 <span data-ttu-id="17212-108">En el vídeo [Cómo: crear un minigráfico en una tabla (generador de informes vídeo)](https://technet.microsoft.com/bi/ff871942.aspx) se muestra cómo crear un informe similar con minigráficos.</span><span class="sxs-lookup"><span data-stu-id="17212-108">The video [How to: Create a Sparkline in a Table (Report Builder Video)](https://technet.microsoft.com/bi/ff871942.aspx) illustrates how to create a similar report with sparklines.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="17212-109">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="17212-109">What You Will Learn</span></span>  
 <span data-ttu-id="17212-110">En este tutorial, aprenderá a realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="17212-110">In this tutorial, you will learn how to do the following:</span></span>  
  
 1. [<span data-ttu-id="17212-111">Crear un informe con una tabla</span><span class="sxs-lookup"><span data-stu-id="17212-111">Create a Report with a Table</span></span>](#CreateTable)  
  
 2. [<span data-ttu-id="17212-112">Crear una consulta en el Asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="17212-112">Create a Query in the Table or Matrix Wizard</span></span>](#Query)  
  
 3. [<span data-ttu-id="17212-113">Agregar un minigráfico a la tabla</span><span class="sxs-lookup"><span data-stu-id="17212-113">Add a Sparkline to the Table</span></span>](#Sparkline)  
  
 4. [<span data-ttu-id="17212-114">Alinear los minigráficos vertical y horizontalmente</span><span class="sxs-lookup"><span data-stu-id="17212-114">Align the Sparklines Vertically and Horizontally</span></span>](#AlignSparklines)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="17212-115">Otros pasos opcionales</span><span class="sxs-lookup"><span data-stu-id="17212-115">Other Optional Steps</span></span>  
 5. [<span data-ttu-id="17212-116">Dar formato a los datos como moneda</span><span class="sxs-lookup"><span data-stu-id="17212-116">Format Data as Currency</span></span>](#FormatCurrency)  
  
 6. [<span data-ttu-id="17212-117">Dar formato a los datos como datos</span><span class="sxs-lookup"><span data-stu-id="17212-117">Format Data as Dates</span></span>](#FormatDates)  
  
 7. [<span data-ttu-id="17212-118">Cambiar el ancho de columna</span><span class="sxs-lookup"><span data-stu-id="17212-118">Change Column Widths</span></span>](#Width)  
  
 8. [<span data-ttu-id="17212-119">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="17212-119">Add a Report Title</span></span>](#Title)  
  
 9. [<span data-ttu-id="17212-120">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="17212-120">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="17212-121">Tiempo estimado para completar este tutorial: 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="17212-121">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17212-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17212-122">Requirements</span></span>  
 <span data-ttu-id="17212-123">Para obtener más información sobre los requisitos, consulte [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="17212-123">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-report-with-a-table"></a><a name="CreateTable"></a><span data-ttu-id="17212-124">1. crear un informe con una tabla</span><span class="sxs-lookup"><span data-stu-id="17212-124">1. Create a Report with a Table</span></span>  
  
#### <a name="to-create-a-report"></a><span data-ttu-id="17212-125">Para crear un informe</span><span class="sxs-lookup"><span data-stu-id="17212-125">To create a report</span></span>  
  
1.  <span data-ttu-id="17212-126">Haga clic en **Inicio**, seleccione **Programas**, **Generador de informes de Microsoft SQL Server 2012**y, a continuación, haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="17212-126">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="17212-127">Se abre el cuadro de diálogo **Introducción**.</span><span class="sxs-lookup"><span data-stu-id="17212-127">The **Getting Started** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="17212-128">Si el cuadro de diálogo **Introducción** no aparece, en el botón **generador de informes** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="17212-128">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="17212-129">En el panel de la izquierda, compruebe que está seleccionada la opción **Nuevo informe** .</span><span class="sxs-lookup"><span data-stu-id="17212-129">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="17212-130">En el panel de la derecha, haga clic en **Asistente para tabla o matriz**.</span><span class="sxs-lookup"><span data-stu-id="17212-130">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="17212-131">En la página **Elegir un conjunto de datos** , seleccione **Crear un conjunto de datos**y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="17212-131">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="17212-132">Se abre la página **Elegir una conexión a un origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="17212-132">The **Choose a connection to a data source** page opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="17212-133">Este tutorial no necesita datos concretos; solo necesita una conexión a una base de datos de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="17212-133">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="17212-134">Si ya tiene una conexión de origen de datos enumerada en **Conexiones de origen de datos**, puede seleccionarla e ir al paso 10.</span><span class="sxs-lookup"><span data-stu-id="17212-134">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to step 10.</span></span> <span data-ttu-id="17212-135">Para obtener más información, consulte [Maneras alternativas de obtener una conexión de datos &#40;Generador de informes&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="17212-135">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  <span data-ttu-id="17212-136">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="17212-136">Click **New**.</span></span> <span data-ttu-id="17212-137">Se abre el cuadro de diálogo **Propiedades del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="17212-137">The **Data Source Properties** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="17212-138">En **Nombre**, escriba **Ventas de producto**como nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="17212-138">In **Name**, type **Product Sales**, a name for the data source.</span></span>  
  
7.  <span data-ttu-id="17212-139">En **Seleccionar un tipo de conexión**, compruebe que está seleccionado **Microsoft SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="17212-139">In **Select a connection type**, verify that **Microsoft SQL Server** is selected.</span></span>  
  
8.  <span data-ttu-id="17212-140">En **Cadena de conexión**, escriba el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="17212-140">In **Connection string**, type the following text:</span></span>  
  
     <span data-ttu-id="17212-141">**Origen de datos =\<servername>**</span><span class="sxs-lookup"><span data-stu-id="17212-141">**Data Source=\<servername>**</span></span>  
  
     <span data-ttu-id="17212-142">La expresión \<servername>, por ejemplo Report001, especifica un equipo en el que se ha instalado una instancia del motor de SQL Server Database.</span><span class="sxs-lookup"><span data-stu-id="17212-142">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="17212-143">Dado que los datos del informe no se extraen de una base de datos de SQL Server, no necesita incluir el nombre de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="17212-143">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="17212-144">Para analizar la consulta se utiliza la base de datos predeterminada en el servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="17212-144">The default database on the specified server is used to parse the query.</span></span>  
  
9. <span data-ttu-id="17212-145">Haga clic en **Credenciales**.</span><span class="sxs-lookup"><span data-stu-id="17212-145">Click **Credentials**.</span></span> <span data-ttu-id="17212-146">Escriba las credenciales necesarias para tener acceso al origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="17212-146">Enter the credentials that you need to access the external data source.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="17212-147">Volverá a encontrarse en la página **Elegir una conexión a un origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="17212-147">You are back on the **Choose a connection to a data source** page.</span></span>  
  
11. <span data-ttu-id="17212-148">Para comprobar que se puede conectar al origen de datos, haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="17212-148">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="17212-149">Aparece un mensaje que indica que la conexión se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="17212-149">The message "Connection created successfully" appears.</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="17212-150">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="17212-150">Click **Next**.</span></span>  
  
##  <a name="2-create-a-query-in-the-table-wizard"></a><a name="Query"></a><span data-ttu-id="17212-151">2. crear una consulta en el Asistente para tablas</span><span class="sxs-lookup"><span data-stu-id="17212-151">2. Create a Query in the Table Wizard</span></span>  
 <span data-ttu-id="17212-152">En un informe puede usar un conjunto de datos compartido que tenga una consulta predefinida o crear un conjunto de datos incrustado para usarlo exclusivamente en ese informe.</span><span class="sxs-lookup"><span data-stu-id="17212-152">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="17212-153">En este tutorial, creará un conjunto de datos incrustado.</span><span class="sxs-lookup"><span data-stu-id="17212-153">In this tutorial, you will create an embedded dataset.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="17212-154">En este tutorial, la consulta contiene los valores de datos, de forma que no necesita un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="17212-154">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="17212-155">Esto hace que la consulta requiera bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="17212-155">This makes the query quite long.</span></span> <span data-ttu-id="17212-156">En un entorno empresarial, la consulta no contendría los datos.</span><span class="sxs-lookup"><span data-stu-id="17212-156">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="17212-157">Esto es solo con fines de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="17212-157">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-query"></a><span data-ttu-id="17212-158">Para crear una consulta</span><span class="sxs-lookup"><span data-stu-id="17212-158">To create a query</span></span>  
  
1.  <span data-ttu-id="17212-159">En la página **Diseñar una consulta** , el diseñador de consultas relacionales está abierto.</span><span class="sxs-lookup"><span data-stu-id="17212-159">On the **Design a query** page, the relational query designer is open.</span></span> <span data-ttu-id="17212-160">En este tutorial, usará el diseñador de consultas basado en texto.</span><span class="sxs-lookup"><span data-stu-id="17212-160">For this tutorial, you will use the text-based query designer.</span></span>  
  
2.  <span data-ttu-id="17212-161">Haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="17212-161">Click **Edit As Text**.</span></span> <span data-ttu-id="17212-162">El diseñador de consultas basado en texto muestra un panel de consulta y un panel de resultados.</span><span class="sxs-lookup"><span data-stu-id="17212-162">The text-based query designer displays a query pane and a results pane.</span></span>  
  
3.  <span data-ttu-id="17212-163">Pegue la siguiente consulta [!INCLUDE[tsql](../includes/tsql-md.md)] en el cuadro **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="17212-163">Paste the following [!INCLUDE[tsql](../includes/tsql-md.md)] query into the **Query** box.</span></span>  
  
    ```  
    SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Carrying Case' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Accessories' as Subcategory,  
       'Budget Movie-Maker' as Product, CAST(1056.00 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,  'Accessories' as Subcategory,  
       'Slim Digital' as Product, CAST(1380.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2010-01-05' AS date) as SalesDate,'Accessories' as Subcategory,    
       'Budget Movie-Maker' as Product, CAST(780.00 AS money) AS Sales, 26 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate, 'Accessories' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3798.00 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(10400.00 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2010-01-09' AS date) as SalesDate, 'Camcorders' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(3000.00 AS money) AS Sales, 60 as Quantity  
    UNION SELECT CAST('2010-01-10' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Budget Movie-Maker' as Product, CAST(7234.50 AS money) AS Sales, 39 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Carrying Case' as Product, CAST(10836.00 AS money) AS Sales, 84 as Quantity  
    UNION SELECT CAST('2010-01-07' AS date) as SalesDate,  'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(2550.00 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2010-01-04' AS date) as SalesDate, 'Digital' as Subcategory,   
       'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2010-01-08' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(18530.00 AS money) AS Sales, 34 as Quantity  
    UNION SELECT CAST('2010-01-06' AS date) as SalesDate, 'Digital SLR' as Subcategory,   
       'Slim Digital' as Product, CAST(26576.00 AS money) AS Sales, 88 as Quantity  
    ```  
  
4.  <span data-ttu-id="17212-164">En la barra de herramientas del diseñador de consultas, haga clic en Ejecutar (**!**).</span><span class="sxs-lookup"><span data-stu-id="17212-164">On the query designer toolbar, click Run  (**!**).</span></span>  
  
     <span data-ttu-id="17212-165">La consulta se ejecuta y muestra el conjunto de resultados para los campos **SalesDate**, **Subcategory**, **Product**, **Sales**y **Quantity**.</span><span class="sxs-lookup"><span data-stu-id="17212-165">The query runs and displays the result set for the fields **SalesDate**, **Subcategory**, **Product**, **Sales**, and **Quantity**.</span></span>  
  
5.  <span data-ttu-id="17212-166">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="17212-166">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="17212-167">En la página **Organizar campos** , arrastre **Sales** hasta **Valores**.</span><span class="sxs-lookup"><span data-stu-id="17212-167">On the **Arrange fields** page, drag **Sales** to **Values**.</span></span>  
  
     <span data-ttu-id="17212-168">La función Sum agrega**Sales** .</span><span class="sxs-lookup"><span data-stu-id="17212-168">**Sales** is aggregated by the Sum function.</span></span> <span data-ttu-id="17212-169">El valor es [Sum(Sales)].</span><span class="sxs-lookup"><span data-stu-id="17212-169">The value is [Sum(Sales)].</span></span>  
  
7.  <span data-ttu-id="17212-170">Arrastre **Product** hasta **Grupos de filas**.</span><span class="sxs-lookup"><span data-stu-id="17212-170">Drag **Product** to **Row groups**.</span></span>  
  
8.  <span data-ttu-id="17212-171">Arrastre **SalesDate** hasta **Grupos de columnas**.</span><span class="sxs-lookup"><span data-stu-id="17212-171">Drag **SalesDate** to **Column groups**.</span></span>  
  
9. <span data-ttu-id="17212-172">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="17212-172">Click **Next**.</span></span>  
  
10. <span data-ttu-id="17212-173">En la página **Elegir el diseño** , en **Opciones**, compruebe que esté seleccionada la opción **Mostrar subtotales y totales generales** .</span><span class="sxs-lookup"><span data-stu-id="17212-173">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="17212-174">El panel Vista previa del asistente muestra una tabla con tres filas.</span><span class="sxs-lookup"><span data-stu-id="17212-174">The wizard Preview pane displays a table with three rows.</span></span> <span data-ttu-id="17212-175">Al ejecutar el informe, cada fila se mostrará de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="17212-175">When you run the report, each row will display in the following way:</span></span>  
  
    1.  <span data-ttu-id="17212-176">La primera fila aparecerá una vez en la tabla para mostrar los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="17212-176">The first row will appear once for the table to show column headings.</span></span>  
  
    2.  <span data-ttu-id="17212-177">La segunda fila se repetirá una vez en cada producto y mostrará el nombre del producto, el total por día y el total de línea.</span><span class="sxs-lookup"><span data-stu-id="17212-177">The second row will repeat once for each product and display the product name, total per day, and line total.</span></span>  
  
    3.  <span data-ttu-id="17212-178">La tercera fila aparecerá una vez en la tabla para mostrar los totales generales.</span><span class="sxs-lookup"><span data-stu-id="17212-178">The third row will appear once for the table to display the grand totals.</span></span>  
  
11. <span data-ttu-id="17212-179">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="17212-179">Click **Next**.</span></span>  
  
12. <span data-ttu-id="17212-180">En la página **Elegir un estilo** , en el panel **Estilos** , seleccione **Pizarra**.</span><span class="sxs-lookup"><span data-stu-id="17212-180">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>  
  
     <span data-ttu-id="17212-181">El panel Vista previa muestra un ejemplo de la tabla con ese estilo.</span><span class="sxs-lookup"><span data-stu-id="17212-181">The Preview pane displays a sample of the table with that style.</span></span>  
  
13. <span data-ttu-id="17212-182">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="17212-182">Click **Finish**.</span></span>  
  
14. <span data-ttu-id="17212-183">La tabla se agrega a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="17212-183">The table is added to the design surface.</span></span> <span data-ttu-id="17212-184">La tabla tiene tres columnas y tres filas.</span><span class="sxs-lookup"><span data-stu-id="17212-184">The table has three columns and three rows.</span></span>  
  
     <span data-ttu-id="17212-185">Busque en el panel Agrupación.</span><span class="sxs-lookup"><span data-stu-id="17212-185">Look in the Grouping pane.</span></span> <span data-ttu-id="17212-186">Si no ve el panel Agrupación, en el menú **Vista** , haga clic en **Agrupación**.</span><span class="sxs-lookup"><span data-stu-id="17212-186">If you can't see the Grouping pane, on the **View** menu, click **Grouping**.</span></span> <span data-ttu-id="17212-187">El panel Grupos de filas muestra un grupo de filas: **Product**.</span><span class="sxs-lookup"><span data-stu-id="17212-187">The Row Groups pane shows one row group: **Product**.</span></span> <span data-ttu-id="17212-188">El panel Grupos de columnas muestra un grupo de columnas: **SalesDate**.</span><span class="sxs-lookup"><span data-stu-id="17212-188">The Column Groups pane shows one column group: **SalesDate**.</span></span> <span data-ttu-id="17212-189">Los datos detallados son todos los datos recuperados por la consulta del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="17212-189">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
15. <span data-ttu-id="17212-190">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="17212-190">Click **Run** to preview the report.</span></span>  
  
##  <a name="3-add-a-sparkline"></a><a name="Sparkline"></a><span data-ttu-id="17212-191">3. agregar un minigráfico</span><span class="sxs-lookup"><span data-stu-id="17212-191">3. Add a Sparkline</span></span>  
  
#### <a name="to-add-a-sparkline-chart-to-a-table"></a><span data-ttu-id="17212-192">Para agregar un minigráfico a una tabla</span><span class="sxs-lookup"><span data-stu-id="17212-192">To add a sparkline chart to a table</span></span>  
  
1.  <span data-ttu-id="17212-193">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="17212-193">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="17212-194">Seleccione la columna Total en su tabla.</span><span class="sxs-lookup"><span data-stu-id="17212-194">Select the Total column in your table.</span></span>  
  
3.  <span data-ttu-id="17212-195">Haga clic con el botón derecho, señale **Insertar columna**y, después, haga clic en **Izquierda**.</span><span class="sxs-lookup"><span data-stu-id="17212-195">Right-click, point to **Insert Column**, and then click **Left**.</span></span>  
  
4.  <span data-ttu-id="17212-196">En la nueva columna, haga clic con el botón secundario en la fila [product], seleccione la pestaña **Insertar** de la cinta de opciones y, a continuación, haga clic en **minigráfico**.</span><span class="sxs-lookup"><span data-stu-id="17212-196">In the new column, right-click in the [Product] row, point to the **Insert** ribbon tab, and then click **Sparkline**.</span></span>  
  
5.  <span data-ttu-id="17212-197">Asegúrese de que el primer minigráfico de la fila de **columna** está seleccionado y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="17212-197">Make sure the first sparkline in the **Column** row is selected and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="17212-198">Haga clic en el minigráfico para mostrar el panel Datos del gráfico.</span><span class="sxs-lookup"><span data-stu-id="17212-198">Click the sparkline to show the Chart Data pane.</span></span>  
  
7.  <span data-ttu-id="17212-199">Haga clic en el signo más (+) en el cuadro valores y, a continuación, haga clic en **ventas**.</span><span class="sxs-lookup"><span data-stu-id="17212-199">Click the plus (+) sign in the Values box, and then click **Sales**.</span></span>  
  
     <span data-ttu-id="17212-200">Los valores del campo **Sales** son ahora los valores para el minigráfico.</span><span class="sxs-lookup"><span data-stu-id="17212-200">The values in the **Sales** field are now the values for the sparkline.</span></span>  
  
8.  <span data-ttu-id="17212-201">Haga clic en el signo más (+) en el cuadro grupos de categorías y, a continuación, haga clic en **fechaventa**.</span><span class="sxs-lookup"><span data-stu-id="17212-201">Click the plus (+) sign in the Category Groups box, and then click **SalesDate**.</span></span>  
  
9. <span data-ttu-id="17212-202">Haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="17212-202">Click **Run** to preview your report.</span></span>  
  
     <span data-ttu-id="17212-203">Tenga en cuenta que hay minigráficos en cada fila de la tabla, pero no son correctos.</span><span class="sxs-lookup"><span data-stu-id="17212-203">Note that there are sparkline charts in each row of the table, but they're not correct.</span></span> <span data-ttu-id="17212-204">Las barras de los gráficos no están alineadas entre sí.</span><span class="sxs-lookup"><span data-stu-id="17212-204">The bars in the charts don't line up with each other.</span></span> <span data-ttu-id="17212-205">Solo hay cuatro barras en la segunda fila de datos, por lo que las barras son más anchas que las de la primera fila, que tiene seis.</span><span class="sxs-lookup"><span data-stu-id="17212-205">There are only four bars in the second row of data, so the bars are wider than the bars in the first row, which has six.</span></span> <span data-ttu-id="17212-206">No puede comparar los valores para cada producto por día.</span><span class="sxs-lookup"><span data-stu-id="17212-206">You can't compare values for each product per day.</span></span> <span data-ttu-id="17212-207">Tienen que estar alineados entre sí.</span><span class="sxs-lookup"><span data-stu-id="17212-207">They need to line up with each other.</span></span>  
  
     <span data-ttu-id="17212-208">Además, observe que para cada fila, la barra más alta de esa fila es el alto de la fila.</span><span class="sxs-lookup"><span data-stu-id="17212-208">Also note that for each row, the tallest bar for that row is the height of the row.</span></span> <span data-ttu-id="17212-209">Esto también es engañoso, porque los valores más grandes de cada fila no son iguales: el valor más grande de Budget Movie-Maker es $10.400, pero el valor más grande para digital delgada es $26.576-más de dos veces más grande.</span><span class="sxs-lookup"><span data-stu-id="17212-209">This is misleading, too, because the largest values for each row are not equal: the largest value for Budget Movie-Maker is $10,400, but the largest value for Slim Digital is $26,576-more than twice as large.</span></span> <span data-ttu-id="17212-210">Además, las barras más grandes de esas dos filas tienen aproximadamente el mismo alto.</span><span class="sxs-lookup"><span data-stu-id="17212-210">And yet the largest bars in those two rows are about the same height.</span></span> <span data-ttu-id="17212-211">También es necesario realizar esto para ajustarse a los demás minigráficos.</span><span class="sxs-lookup"><span data-stu-id="17212-211">That also needs to be made to scale with the other sparklines.</span></span>  
  
     <span data-ttu-id="17212-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span><span class="sxs-lookup"><span data-stu-id="17212-212">![rs_SprklineMtrxUnaligndBars](../../2014/tutorials/media/rs-sprklinemtrxunaligndbars.gif "rs_SprklineMtrxUnaligndBars")</span></span>  
  
##  <a name="4-align-the-sparklines-vertically-and-horizontally"></a><a name="AlignSparklines"></a><span data-ttu-id="17212-213">4. alinear los minigráficos vertical y horizontalmente</span><span class="sxs-lookup"><span data-stu-id="17212-213">4. Align the Sparklines Vertically and Horizontally</span></span>  
 <span data-ttu-id="17212-214">Los minigráficos son difíciles de leer cuando no todos usan las mismas medidas.</span><span class="sxs-lookup"><span data-stu-id="17212-214">The sparklines are hard to read when they don't all use the same measurements.</span></span> <span data-ttu-id="17212-215">Los ejes horizontal y vertical de cada uno tienen que coincidir con el resto.</span><span class="sxs-lookup"><span data-stu-id="17212-215">Both the horizontal and vertical axes for each need to match the rest.</span></span>  
  
#### <a name="to-set-alignment-for-the-sparklines-in-the-table"></a><span data-ttu-id="17212-216">Para establecer la alineación de los minigráficos en la tabla</span><span class="sxs-lookup"><span data-stu-id="17212-216">To set alignment for the sparklines in the table</span></span>  
  
1.  <span data-ttu-id="17212-217">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="17212-217">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="17212-218">Haga clic con el botón derecho en el minigráfico y, después, haga clic en **Propiedades del eje vertical**.</span><span class="sxs-lookup"><span data-stu-id="17212-218">Right-click the sparkline and click **Vertical Axis Properties**.</span></span>  
  
3.  <span data-ttu-id="17212-219">Active la casilla **Alinear ejes en** .</span><span class="sxs-lookup"><span data-stu-id="17212-219">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="17212-220">Tablix1 aparecerá en la lista.</span><span class="sxs-lookup"><span data-stu-id="17212-220">Tablix1 is showing in the list.</span></span> <span data-ttu-id="17212-221">Es la única opción.</span><span class="sxs-lookup"><span data-stu-id="17212-221">That is the only option.</span></span> <span data-ttu-id="17212-222">Establece el alto de las barras en cada minigráfico con respecto a los demás.</span><span class="sxs-lookup"><span data-stu-id="17212-222">This sets the height of the bars in each sparkline relative to the others.</span></span>  
  
4.  <span data-ttu-id="17212-223">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="17212-223">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="17212-224">Haga clic con el botón derecho en el minigráfico y, después, haga clic en **Propiedades del eje horizontal**.</span><span class="sxs-lookup"><span data-stu-id="17212-224">Right-click the sparkline and click **Horizontal Axis Properties**.</span></span>  
  
6.  <span data-ttu-id="17212-225">Active la casilla **Alinear ejes en** .</span><span class="sxs-lookup"><span data-stu-id="17212-225">Check the **Align axes in** check box.</span></span>  
  
     <span data-ttu-id="17212-226">Tablix1 aparecerá en la lista.</span><span class="sxs-lookup"><span data-stu-id="17212-226">Tablix1 is showing in the list.</span></span> <span data-ttu-id="17212-227">Es la única opción.</span><span class="sxs-lookup"><span data-stu-id="17212-227">That is the only option.</span></span> <span data-ttu-id="17212-228">Establece el ancho de las barras en cada minigráfico con respecto a los demás.</span><span class="sxs-lookup"><span data-stu-id="17212-228">This sets the width of the bars in each sparkline relative to the others.</span></span> <span data-ttu-id="17212-229">Si algunos minigráficos tienen menos barras que otros, dichos minigráficos tendrán espacios en blanco correspondientes a los datos que faltan.</span><span class="sxs-lookup"><span data-stu-id="17212-229">If some sparklines have fewer bars than others, then those sparklines will have blank spaces for the missing data.</span></span>  
  
7.  <span data-ttu-id="17212-230">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="17212-230">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="17212-231">Para volver a obtener una vista previa de un informe, haga clic en **Ejecutar** .</span><span class="sxs-lookup"><span data-stu-id="17212-231">Click **Run** to preview your report again.</span></span>  
  
 <span data-ttu-id="17212-232">Observe que todas las barras están ahora alineadas con las barras de las demás filas.</span><span class="sxs-lookup"><span data-stu-id="17212-232">Note that all the bars are now aligned with the bars in the other rows.</span></span>  
  
##  <a name="5-optional-format-data-as-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="17212-233">5. (opcional) dar formato a los datos como moneda</span><span class="sxs-lookup"><span data-stu-id="17212-233">5. (Optional) Format Data as Currency</span></span>  
 <span data-ttu-id="17212-234">De forma predeterminada, los datos de resumen del campo **sales** muestran un número general.</span><span class="sxs-lookup"><span data-stu-id="17212-234">By default, the summary data for the **Sales** field displays a general number.</span></span> <span data-ttu-id="17212-235">Aplíquele el formato adecuado para mostrar el número como moneda.</span><span class="sxs-lookup"><span data-stu-id="17212-235">Format it to display the number as currency.</span></span> <span data-ttu-id="17212-236">Alterne **Estilos de marcador de posición** para mostrar los cuadros de texto con formato y el texto de marcador de posición como valores de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="17212-236">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-a-currency-field"></a><span data-ttu-id="17212-237">Para dar formato a un campo de moneda</span><span class="sxs-lookup"><span data-stu-id="17212-237">To format a currency field</span></span>  
  
1.  <span data-ttu-id="17212-238">Haga clic en **Diseño** para cambiar a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="17212-238">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="17212-239">Haga clic en la celda de la segunda fila (bajo la fila de encabezados de columna) en la columna **fechaventa** y arrastre para seleccionar todas las celdas que contienen `[Sum(Sales)]` .</span><span class="sxs-lookup"><span data-stu-id="17212-239">Click the cell in the second row (under the column headings row) in the **SalesDate** column and drag to select all cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="17212-240">En la pestaña **Inicio** , en el grupo **Número** , haga clic en el botón **Moneda** .</span><span class="sxs-lookup"><span data-stu-id="17212-240">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span> <span data-ttu-id="17212-241">Las celdas cambian para mostrar la moneda con formato.</span><span class="sxs-lookup"><span data-stu-id="17212-241">The cells change to show the formatted currency.</span></span>  
  
     <span data-ttu-id="17212-242">Si la configuración regional es Inglés (Estados Unidos), el texto de ejemplo predeterminado es [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="17212-242">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="17212-243">Si no ve un valor de moneda de ejemplo, haga clic en **estilos de marcador de posición** en el grupo **números** y, a continuación, haga clic en **valores de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="17212-243">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="17212-244">Haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="17212-244">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="17212-245">Los valores de Resumen de **sales** se muestran como moneda.</span><span class="sxs-lookup"><span data-stu-id="17212-245">The summary values for **Sales** display as currency.</span></span>  
  
##  <a name="6-optional-format-data-as-dates"></a><a name="FormatDates"></a><span data-ttu-id="17212-246">6. (opcional) dar formato a los datos como fechas</span><span class="sxs-lookup"><span data-stu-id="17212-246">6. (Optional) Format Data as Dates</span></span>  
 <span data-ttu-id="17212-247">De forma predeterminada, el campo **fechaventa** muestra información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="17212-247">By default, the **SalesDate** field displays both date and time information.</span></span> <span data-ttu-id="17212-248">Puede darle formato para mostrar solo la fecha.</span><span class="sxs-lookup"><span data-stu-id="17212-248">You can format them to display only the date.</span></span>  
  
#### <a name="to-format-a-date-field-as-the-default-format"></a><span data-ttu-id="17212-249">Para dar formato a un campo de fecha como el formato predeterminado</span><span class="sxs-lookup"><span data-stu-id="17212-249">To format a date field as the default format</span></span>  
  
1.  <span data-ttu-id="17212-250">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="17212-250">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="17212-251">Haga clic en la celda que contiene `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="17212-251">Click the cell that contains `[SalesDate]`.</span></span>  
  
3.  <span data-ttu-id="17212-252">En la cinta de opciones, en la pestaña **Inicio** , en el grupo **número** , en la lista desplegable, seleccione **fecha**.</span><span class="sxs-lookup"><span data-stu-id="17212-252">On the Ribbon, on the **Home** tab, in the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="17212-253">La celda muestra la fecha de ejemplo **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="17212-253">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="17212-254">Si no ve un valor de fecha de ejemplo, haga clic en **Estilos de marcador de posición** en el grupo **Números** y, después, haga clic en **Valores de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="17212-254">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="17212-255">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="17212-255">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="17212-256">Los valores de **fechaventa** se muestran en el formato de fecha predeterminado.</span><span class="sxs-lookup"><span data-stu-id="17212-256">The **SalesDate** values display in the default date format.</span></span>  
  
##  <a name="7-optional-change-column-widths"></a><a name="Width"></a><span data-ttu-id="17212-257">7. (opcional) cambiar el ancho de las columnas</span><span class="sxs-lookup"><span data-stu-id="17212-257">7. (Optional) Change Column Widths</span></span>  
 <span data-ttu-id="17212-258">De forma predeterminada, cada celda de una tabla contiene un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="17212-258">By default, each cell in a table contains a text box.</span></span> <span data-ttu-id="17212-259">Un cuadro de texto se expande verticalmente para alojar el texto cuando se representa la página.</span><span class="sxs-lookup"><span data-stu-id="17212-259">A text box expands vertically to accommodate text when the page is rendered.</span></span> <span data-ttu-id="17212-260">En el informe representado, cada fila se expande hasta el alto del cuadro de texto más alto representado de la fila.</span><span class="sxs-lookup"><span data-stu-id="17212-260">In the rendered report, each row expands to the height of the tallest rendered text box in the row.</span></span> <span data-ttu-id="17212-261">El alto de la fila en la superficie de diseño no tiene efecto alguno en el alto de la fila en el informe representado.</span><span class="sxs-lookup"><span data-stu-id="17212-261">The height of the row on the design surface has no affect on the height of the row in the rendered report.</span></span>  
  
 <span data-ttu-id="17212-262">Para reducir la cantidad de espacio vertical que ocupa cada fila, expanda el ancho de columna para dar cabida en una línea al contenido previsto de los cuadros de texto de la columna.</span><span class="sxs-lookup"><span data-stu-id="17212-262">To reduce the amount of vertical space each row takes, expand the column width to accommodate the expected contents of the text boxes in the column on one line.</span></span>  
  
#### <a name="to-change-the-width-of-columns"></a><span data-ttu-id="17212-263">Para cambiar el ancho de las columnas</span><span class="sxs-lookup"><span data-stu-id="17212-263">To change the width of columns</span></span>  
  
1.  <span data-ttu-id="17212-264">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="17212-264">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="17212-265">Haga clic en la tabla para que los identificadores de columna y de fila aparezcan encima y al lado de la tabla.</span><span class="sxs-lookup"><span data-stu-id="17212-265">Click the table so that column and row handles appear above and next to the table.</span></span>  
  
     <span data-ttu-id="17212-266">Las barras grises situadas en la parte superior y en el lado de la tabla son los identificadores de fila y de columna.</span><span class="sxs-lookup"><span data-stu-id="17212-266">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
3.  <span data-ttu-id="17212-267">Sitúe el cursor en la línea que hay entre los controladores de columna para que cambie a una flecha doble.</span><span class="sxs-lookup"><span data-stu-id="17212-267">Point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="17212-268">Arrastre las columnas hasta que tengan el tamaño deseado.</span><span class="sxs-lookup"><span data-stu-id="17212-268">Drag the columns to the size you want.</span></span> <span data-ttu-id="17212-269">Por ejemplo, expanda la columna de **Product** para que el nombre de producto se muestre en una línea.</span><span class="sxs-lookup"><span data-stu-id="17212-269">For example, expand the column for **Product** so that the product name displays on one line.</span></span>  
  
4.  <span data-ttu-id="17212-270">Haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="17212-270">Click **Run** to preview your report.</span></span>  
  
##  <a name="8-optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="17212-271">8. (opcional) agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="17212-271">8. (Optional) Add a Report Title</span></span>  
 <span data-ttu-id="17212-272">Los títulos de informe aparecen en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="17212-272">A report title appears at the top of the report.</span></span> <span data-ttu-id="17212-273">Puede situar el título del informe en un encabezado de informe o, si el informe no lo utiliza, en un cuadro de texto en la parte superior del cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="17212-273">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="17212-274">En este tutorial, deberá utilizar el cuadro de texto que se coloca automáticamente en la parte superior del cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="17212-274">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
 <span data-ttu-id="17212-275">El texto se puede mejorar aún más aplicando estilos de fuente, tamaños y colores diferentes a las frases y caracteres individuales.</span><span class="sxs-lookup"><span data-stu-id="17212-275">The text can be further enhanced by applying different font styles, sizes, and colors to phrases and individual characters of the text.</span></span> <span data-ttu-id="17212-276">Para obtener más información, vea [Dar formato al texto en un cuadro de texto &#40;Generador de informes y SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="17212-276">For more information, see [Format Text in a Text Box &#40;Report Builder and SSRS&#41;](report-design/format-text-in-a-text-box-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="17212-277">Para agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="17212-277">To add a report title</span></span>  
  
1.  <span data-ttu-id="17212-278">En la superficie de diseño, haga clic en **Haga clic para agregar título**.</span><span class="sxs-lookup"><span data-stu-id="17212-278">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="17212-279">Escriba **Ventas del producto**y después haga clic fuera del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="17212-279">Type **Product Sales**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="17212-280">Haga clic con el botón secundario en el cuadro de texto que contiene **Ventas del producto** y haga clic en **Propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="17212-280">Right-click the text box that contains **Product Sales** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="17212-281">En el cuadro de diálogo **Propiedades de cuadro de texto** , haga clic en **Fuente**.</span><span class="sxs-lookup"><span data-stu-id="17212-281">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="17212-282">En la lista **Tamaño** , seleccione **18 pt**.</span><span class="sxs-lookup"><span data-stu-id="17212-282">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="17212-283">En la lista **color** , seleccione **granate**.</span><span class="sxs-lookup"><span data-stu-id="17212-283">In the **Color** list, select **Maroon**.</span></span>  
  
7.  <span data-ttu-id="17212-284">Seleccione **Negrita**.</span><span class="sxs-lookup"><span data-stu-id="17212-284">Select **Bold**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="9-save-the-report"></a><a name="Save"></a><span data-ttu-id="17212-285">9. guardar el informe</span><span class="sxs-lookup"><span data-stu-id="17212-285">9. Save the Report</span></span>  
 <span data-ttu-id="17212-286">Guarde el informe un servidor de informes o en su equipo.</span><span class="sxs-lookup"><span data-stu-id="17212-286">Save the report to a report server or your computer.</span></span> <span data-ttu-id="17212-287">Si no guarda el informe en el servidor de informes, varias características de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , como los elementos de informe y los subinformes, no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="17212-287">If you do not save the report to the report server, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="17212-288">Para guardar el informe en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="17212-288">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="17212-289">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="17212-289">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="17212-290">Haga clic en **Sitios y servidores recientes**.</span><span class="sxs-lookup"><span data-stu-id="17212-290">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="17212-291">Seleccione o escriba el nombre del servidor de informes donde tiene el permiso para guardar los informes.</span><span class="sxs-lookup"><span data-stu-id="17212-291">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="17212-292">Aparecerá el mensaje "Conectando con el servidor de informes".</span><span class="sxs-lookup"><span data-stu-id="17212-292">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="17212-293">Una vez completada la conexión, se mostrará el contenido de la carpeta de informes que el administrador del servidor de informes especificó como ubicación predeterminada para los informes.</span><span class="sxs-lookup"><span data-stu-id="17212-293">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="17212-294">En **Nombre**, reemplace el nombre predeterminado por **Ventas de producto**.</span><span class="sxs-lookup"><span data-stu-id="17212-294">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
5.  <span data-ttu-id="17212-295">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="17212-295">Click **Save**.</span></span>  
  
 <span data-ttu-id="17212-296">El informe se guarda en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="17212-296">The report is saved to the report server.</span></span> <span data-ttu-id="17212-297">El nombre del servidor de informes al que está conectado aparecerá en la barra de estado en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="17212-297">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="17212-298">Para guardar el informe en el equipo</span><span class="sxs-lookup"><span data-stu-id="17212-298">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="17212-299">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="17212-299">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="17212-300">Haga clic en **Escritorio**, **Mis documentos**o **Mi PC**y vaya a la carpeta donde quiere guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="17212-300">Click **Desktop**, **My Documents**, or **My computer**, and browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="17212-301">En **Nombre**, reemplace el nombre predeterminado por **Ventas de producto**.</span><span class="sxs-lookup"><span data-stu-id="17212-301">In **Name**, replace the default name with **Product Sales**.</span></span>  
  
4.  <span data-ttu-id="17212-302">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="17212-302">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="17212-303">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="17212-303">Next Steps</span></span>  
 <span data-ttu-id="17212-304">Esto concluye el tutorial para crear un informe de tabla con minigráficos.</span><span class="sxs-lookup"><span data-stu-id="17212-304">This concludes the tutorial for creating a table report with sparkline charts.</span></span> <span data-ttu-id="17212-305">Para obtener más información sobre minigráficos, vea [Minigráficos y barras de datos &#40;Generador de informes y SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="17212-305">For more information about sparklines, see [Sparklines and Data Bars &#40;Report Builder and SSRS&#41;](report-design/sparklines-and-data-bars-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17212-306">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17212-306">See Also</span></span>  
 <span data-ttu-id="17212-307">[Tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="17212-307">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="17212-308">Generador de informes en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="17212-308">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
