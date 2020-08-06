---
title: 'Lección 2: agregar datos | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 13c3a8cc-b1db-4aba-ad9b-038b7971be8d
author: minewiskan
ms.author: owend
ms.openlocfilehash: c844ea6558949407ca9b8206601ff7fe802ec399
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670659"
---
# <a name="lesson-2-add-data"></a><span data-ttu-id="022a8-102">Lección 2: Agregar datos</span><span class="sxs-lookup"><span data-stu-id="022a8-102">Lesson 2: Add Data</span></span>
  <span data-ttu-id="022a8-103">En esta lección usará el Asistente para la importación de tablas de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] para conectarse a la base de datos SQL AdventureWorksDW, seleccionar datos, obtener una vista previa, filtrar los datos e importarlos al área de trabajo del modelo.</span><span class="sxs-lookup"><span data-stu-id="022a8-103">In this lesson, you will use the Table Import Wizard in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] to connect to the AdventureWorksDW SQL database, select data, preview, and filter the data, and then import the data into your model workspace.</span></span>  
  
 <span data-ttu-id="022a8-104">Con el Asistente para importación de tabla, puede importar datos desde una variedad de orígenes relacionales: Access, SQL, Oracle, Sybase, Informix, DB2, Teradata y mucho más.</span><span class="sxs-lookup"><span data-stu-id="022a8-104">By using the Table Import Wizard, you can import data from a variety of relational sources: Access, SQL, Oracle, Sybase, Informix, DB2, Teradata, and more.</span></span> <span data-ttu-id="022a8-105">El procedimiento para importar los datos de cada uno de estos orígenes relacionales es muy similar al que se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="022a8-105">The steps for importing data from each of these relational sources are very similar to what is described below.</span></span> <span data-ttu-id="022a8-106">Asimismo, los datos se pueden seleccionar mediante un procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="022a8-106">Additionally, data can be selected using a stored procedure.</span></span>  
  
 <span data-ttu-id="022a8-107">Para obtener más información sobre la importación de datos y los diferentes tipos de orígenes de datos de los que puede realizar la importación, vea [Orígenes de datos &#40;SSAS tabular&#41;](data-sources-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="022a8-107">To learn more about importing data and the different types of data sources you can import from, see [Data Sources &#40;SSAS Tabular&#41;](data-sources-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="022a8-108">Tiempo estimado para completar esta lección: **20 minutos**</span><span class="sxs-lookup"><span data-stu-id="022a8-108">Estimated time to complete this lesson: **20 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="022a8-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="022a8-109">Prerequisites</span></span>  
 <span data-ttu-id="022a8-110">Este tema forma parte de un tutorial de modelado tabular, que se debe completar en orden.</span><span class="sxs-lookup"><span data-stu-id="022a8-110">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="022a8-111">Antes de realizar las tareas de esta lección, debe haber completado la lección anterior: [Lección 1: Crear un nuevo proyecto de modelo tabular](lesson-1-create-a-new-tabular-model-project.md).</span><span class="sxs-lookup"><span data-stu-id="022a8-111">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 1: Create a New Tabular Model Project](lesson-1-create-a-new-tabular-model-project.md).</span></span>  
  
## <a name="create-a-connection"></a><span data-ttu-id="022a8-112">Crear una conexión</span><span class="sxs-lookup"><span data-stu-id="022a8-112">Create a Connection</span></span>  
  
#### <a name="to-create-a-connection-to-a-the-adventureworksdw2012-database"></a><span data-ttu-id="022a8-113">Para crear una conexión con la base de datos AdventureWorksDW2012</span><span class="sxs-lookup"><span data-stu-id="022a8-113">To create a connection to a the AdventureWorksDW2012 database</span></span>  
  
1.  <span data-ttu-id="022a8-114">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en el menú **Modelo** y, a continuación, haga clic en **Importar desde el origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="022a8-114">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **Model** menu, and then click **Import from Data Source**.</span></span>  
  
     <span data-ttu-id="022a8-115">De esta forma se inicia el Asistente para la importación de tablas, que le guía a través del proceso para establecer una conexión a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="022a8-115">This launches the Table Import Wizard which guides you through setting up a connection to a data source.</span></span> <span data-ttu-id="022a8-116">Si **Importar desde el origen de datos** está atenuado, haga doble clic en **Model.bim** en **Explorador de soluciones** para abrir el modelo en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="022a8-116">If **Import from Data Source** is greyed out, double click **Model.bim** in **Solution Explorer** to open the model in the designer.</span></span>  
  
2.  <span data-ttu-id="022a8-117">En el **Asistente para la importación de tablas**, bajo **Bases de datos relacionales**, haga clic en **Microsoft SQL Server**y después en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="022a8-117">In the **Table Import Wizard**, under **Relational Databases**, click **Microsoft SQL Server**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="022a8-118">En la página **conectar a una base de datos de Microsoft SQL Server** , en **nombre descriptivo**de la conexión, escriba `Adventure Works DB from SQL` .</span><span class="sxs-lookup"><span data-stu-id="022a8-118">In the **Connect to a Microsoft SQL Server Database** page, in **Friendly Connection Name**, type `Adventure Works DB from SQL`.</span></span>  
  
4.  <span data-ttu-id="022a8-119">En **Nombre del servidor**, escriba el nombre del servidor en el que instaló la base de datos AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="022a8-119">In **Server name**, type the name of the server you installed the AdventureWorksDW database.</span></span>  
  
5.  <span data-ttu-id="022a8-120">En el campo **Nombre de la base de datos** , haga clic en la flecha abajo y seleccione **AdventureWorksDW**; a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="022a8-120">In the **Database name** field, click the down arrow and select **AdventureWorksDW**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="022a8-121">En la página **Información de suplantación** , tendrá que especificar las credenciales que usará Analysis Services para conectar con el origen de datos al importar y procesar los datos.</span><span class="sxs-lookup"><span data-stu-id="022a8-121">In the **Impersonation Information** page, you need to specify the credentials Analysis Services will use to connect to the data source when importing and processing data.</span></span> <span data-ttu-id="022a8-122">Compruebe que **Nombre de usuario y contraseña específicos de Windows** está seleccionado y, en **Nombre de usuario** y **Contraseña**, especifique las credenciales de inicio de sesión de Windows y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="022a8-122">Verify **Specific Windows user name and password** is selected, and then in **User Name** and **Password**, enter your Windows logon credentials, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="022a8-123">El uso de una cuenta de usuario y una contraseña de Windows es el método más seguro de conexión a un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="022a8-123">Using a Windows user account and password provides the most secure method of connecting to a data source.</span></span> <span data-ttu-id="022a8-124">Para más información, vea [Suplantación &#40;SSAS tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="022a8-124">For more information, see [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span></span>  
  
7.  <span data-ttu-id="022a8-125">En la página **Elegir cómo importar los datos** , compruebe que la opción **Seleccionar de una lista de tablas y vistas para elegir los datos para importar** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="022a8-125">In the **Choose How to Import the Data** page, verify **Select from a list of tables and views to choose the data to import** is selected.</span></span> <span data-ttu-id="022a8-126">Tendrá que seleccionar valores de una lista de tablas y vistas, así que haga clic en **Siguiente** para mostrar una lista de todas las tablas de origen de la base de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="022a8-126">You want to select from a list of tables and views, so click **Next** to display a list of all the source tables in the source database.</span></span>  
  
8.  <span data-ttu-id="022a8-127">En la página **Seleccionar tablas y vistas** , active la casilla para las siguientes tablas: **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**y **FactInternetSales**.</span><span class="sxs-lookup"><span data-stu-id="022a8-127">In the **Select Tables and Views** page, select the check box for the following tables: **DimCustomer**, **DimDate**, **DimGeography**, **DimProduct**, **DimProductCategory**, **DimProductSubcategory**, and **FactInternetSales**.</span></span>  
  
9. <span data-ttu-id="022a8-128">Vamos a asignar nombres fáciles de identificar a las tablas del modelo.</span><span class="sxs-lookup"><span data-stu-id="022a8-128">We want to give the tables in the model more easily understood names.</span></span> <span data-ttu-id="022a8-129">Haga clic en la celda de la columna **Nombre descriptivo** de **DimCustomer**.</span><span class="sxs-lookup"><span data-stu-id="022a8-129">Click on the cell in the **Friendly Name** column for **DimCustomer**.</span></span> <span data-ttu-id="022a8-130">Cambie el nombre de la tabla quitando "DIM" de DimCustomer.</span><span class="sxs-lookup"><span data-stu-id="022a8-130">Rename the table by removing "Dim" from DimCustomer.</span></span>  
  
10. <span data-ttu-id="022a8-131">Cambie el nombre de las demás tablas:</span><span class="sxs-lookup"><span data-stu-id="022a8-131">Rename the other tables:</span></span>  
  
    |<span data-ttu-id="022a8-132">Nombre de origen</span><span class="sxs-lookup"><span data-stu-id="022a8-132">Source name</span></span>|<span data-ttu-id="022a8-133">Nombre descriptivo</span><span class="sxs-lookup"><span data-stu-id="022a8-133">Friendly Name</span></span>|  
    |-----------------|-------------------|  
    |<span data-ttu-id="022a8-134">DimDate</span><span class="sxs-lookup"><span data-stu-id="022a8-134">DimDate</span></span>|<span data-ttu-id="022a8-135">Date</span><span class="sxs-lookup"><span data-stu-id="022a8-135">Date</span></span>|  
    |<span data-ttu-id="022a8-136">DimGeography</span><span class="sxs-lookup"><span data-stu-id="022a8-136">DimGeography</span></span>|<span data-ttu-id="022a8-137">Geography</span><span class="sxs-lookup"><span data-stu-id="022a8-137">Geography</span></span>|  
    |<span data-ttu-id="022a8-138">DimProduct</span><span class="sxs-lookup"><span data-stu-id="022a8-138">DimProduct</span></span>|<span data-ttu-id="022a8-139">Producto</span><span class="sxs-lookup"><span data-stu-id="022a8-139">Product</span></span>|  
    |<span data-ttu-id="022a8-140">DimProductCategory</span><span class="sxs-lookup"><span data-stu-id="022a8-140">DimProductCategory</span></span>|<span data-ttu-id="022a8-141">Categoría de productos</span><span class="sxs-lookup"><span data-stu-id="022a8-141">Product Category</span></span>|  
    |<span data-ttu-id="022a8-142">DimProductSubcategory</span><span class="sxs-lookup"><span data-stu-id="022a8-142">DimProductSubcategory</span></span>|<span data-ttu-id="022a8-143">Product Subcategory</span><span class="sxs-lookup"><span data-stu-id="022a8-143">Product Subcategory</span></span>|  
    |<span data-ttu-id="022a8-144">FactInternetSales</span><span class="sxs-lookup"><span data-stu-id="022a8-144">FactInternetSales</span></span>|<span data-ttu-id="022a8-145">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="022a8-145">Internet Sales</span></span>|  
  
     <span data-ttu-id="022a8-146">**NO** haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="022a8-146">**DO NOT** click **Finish**.</span></span>  
  
 <span data-ttu-id="022a8-147">Ahora que se ha conectado a la base de datos, ha seleccionado las tablas que se importarán y ha asignado nombres descriptivos a las tablas, vaya a la siguiente sección, [Filtrar los datos de la tabla antes de importar](#FilterData).</span><span class="sxs-lookup"><span data-stu-id="022a8-147">Now that you have connected to the database, selected the tables to import, and given the tables friendly names, go to the next section, [Filter the Table Data prior to Importing](#FilterData).</span></span>  
  
##  <a name="filter-the-table-data"></a><a name="FilterData"></a><span data-ttu-id="022a8-148">Filtrar los datos de la tabla</span><span class="sxs-lookup"><span data-stu-id="022a8-148">Filter the Table Data</span></span>  
 <span data-ttu-id="022a8-149">La tabla DimCustomer que va a importar de la base de datos contiene un subconjunto de los datos de la base de datos Adventure original de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="022a8-149">The DimCustomer table that you are importing from the database contains a subset of the data from the original SQL Server Adventure Works database.</span></span> <span data-ttu-id="022a8-150">Filtrará algunas de las columnas de la tabla DimCustomer que no son necesarias.</span><span class="sxs-lookup"><span data-stu-id="022a8-150">You will filter out some of the columns from the DimCustomer table that aren't necessary.</span></span> <span data-ttu-id="022a8-151">Cuando sea posible, querrá filtrar los datos que no se utilicen para ahorrar espacio en memoria usado por el modelo.</span><span class="sxs-lookup"><span data-stu-id="022a8-151">When possible, you will want to filter out data that will not be used in order to save in-memory space used by the model.</span></span>  
  
#### <a name="to-filter-the-table-data-prior-to-importing"></a><span data-ttu-id="022a8-152">Para filtrar los datos de las tablas antes de importar</span><span class="sxs-lookup"><span data-stu-id="022a8-152">To filter the table data prior to importing</span></span>  
  
1.  <span data-ttu-id="022a8-153">Seleccione la fila de la tabla **Customer** y luego haga clic en **Vista previa y filtro**.</span><span class="sxs-lookup"><span data-stu-id="022a8-153">Select the row for the **Customer** table, and then click **Preview & Filter**.</span></span> <span data-ttu-id="022a8-154">La ventana **Vista previa de la tabla seleccionada** se abre con todas las columnas de la tabla de origen DimCustomer mostradas.</span><span class="sxs-lookup"><span data-stu-id="022a8-154">The **Preview Selected Table** window opens with all the columns in the DimCustomer source table displayed.</span></span>  
  
2.  <span data-ttu-id="022a8-155">Desactive la casilla situada sobre las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="022a8-155">Clear the checkbox at the top of the following columns:</span></span>  
  
    |<span data-ttu-id="022a8-156">Customer</span><span class="sxs-lookup"><span data-stu-id="022a8-156">Customer</span></span>|  
    |--------------|  
    |<span data-ttu-id="022a8-157">**SpanishEducation**</span><span class="sxs-lookup"><span data-stu-id="022a8-157">**SpanishEducation**</span></span>|  
    |<span data-ttu-id="022a8-158">**FrenchEducation**</span><span class="sxs-lookup"><span data-stu-id="022a8-158">**FrenchEducation**</span></span>|  
    |<span data-ttu-id="022a8-159">**SpanishOccupation**</span><span class="sxs-lookup"><span data-stu-id="022a8-159">**SpanishOccupation**</span></span>|  
    |<span data-ttu-id="022a8-160">**FrenchOccupation**</span><span class="sxs-lookup"><span data-stu-id="022a8-160">**FrenchOccupation**</span></span>|  
  
     <span data-ttu-id="022a8-161">Puesto que los valores de estas columnas no son pertinentes para el análisis de ventas por Internet, no hay necesidad de importarlas.</span><span class="sxs-lookup"><span data-stu-id="022a8-161">Since the values for these columns are not relevant to Internet sales analysis, there is no need to import these columns.</span></span> <span data-ttu-id="022a8-162">La eliminación de columnas innecesarias reducirá el tamaño de su modelo.</span><span class="sxs-lookup"><span data-stu-id="022a8-162">Eliminating unnecessary columns will make your model smaller.</span></span>  
  
3.  <span data-ttu-id="022a8-163">Compruebe que el resto de las columnas estén activadas y después haga clic **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="022a8-163">Verify that all other columns are checked, and then click **OK**.</span></span>  
  
     <span data-ttu-id="022a8-164">Observe que las palabras **filtros aplicados** se muestran ahora en la columna **detalles del filtro** en la fila **Customer** ; Si hace clic en ese vínculo, verá una descripción de texto de los filtros que acaba de aplicar.</span><span class="sxs-lookup"><span data-stu-id="022a8-164">Notice the words **Applied filters** are now displayed in the **Filter Details** column in the **Customer** row; if you click on that link you'll see a text description of the filters you just applied.</span></span>  
  
4.  <span data-ttu-id="022a8-165">Filtre las tablas restantes desactivando las casillas de las columnas siguientes en cada tabla:</span><span class="sxs-lookup"><span data-stu-id="022a8-165">Filter the remaining tables by clearing the checkboxes for the following columns in each table:</span></span>  
  
    |<span data-ttu-id="022a8-166">Date</span><span class="sxs-lookup"><span data-stu-id="022a8-166">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="022a8-167">**DateKey**</span><span class="sxs-lookup"><span data-stu-id="022a8-167">**DateKey**</span></span>|  
    |<span data-ttu-id="022a8-168">**SpanishDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="022a8-168">**SpanishDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="022a8-169">**FrenchDayNameOfWeek**</span><span class="sxs-lookup"><span data-stu-id="022a8-169">**FrenchDayNameOfWeek**</span></span>|  
    |<span data-ttu-id="022a8-170">**SpanishMonthName**</span><span class="sxs-lookup"><span data-stu-id="022a8-170">**SpanishMonthName**</span></span>|  
    |<span data-ttu-id="022a8-171">**FrenchMonthName**</span><span class="sxs-lookup"><span data-stu-id="022a8-171">**FrenchMonthName**</span></span>|  
  
    |<span data-ttu-id="022a8-172">Geography</span><span class="sxs-lookup"><span data-stu-id="022a8-172">Geography</span></span>|  
    |---------------|  
    |<span data-ttu-id="022a8-173">**SpanishCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="022a8-173">**SpanishCountryRegionName**</span></span>|  
    |<span data-ttu-id="022a8-174">**FrenchCountryRegionName**</span><span class="sxs-lookup"><span data-stu-id="022a8-174">**FrenchCountryRegionName**</span></span>|  
    |<span data-ttu-id="022a8-175">**IpAddressLocator**</span><span class="sxs-lookup"><span data-stu-id="022a8-175">**IpAddressLocator**</span></span>|  
  
    |<span data-ttu-id="022a8-176">Producto</span><span class="sxs-lookup"><span data-stu-id="022a8-176">Product</span></span>|  
    |-------------|  
    |<span data-ttu-id="022a8-177">**SpanishProductName**</span><span class="sxs-lookup"><span data-stu-id="022a8-177">**SpanishProductName**</span></span>|  
    |<span data-ttu-id="022a8-178">**FrenchProductName**</span><span class="sxs-lookup"><span data-stu-id="022a8-178">**FrenchProductName**</span></span>|  
    |<span data-ttu-id="022a8-179">**FrenchDescription**</span><span class="sxs-lookup"><span data-stu-id="022a8-179">**FrenchDescription**</span></span>|  
    |<span data-ttu-id="022a8-180">**ChineseDescription**</span><span class="sxs-lookup"><span data-stu-id="022a8-180">**ChineseDescription**</span></span>|  
    |<span data-ttu-id="022a8-181">**ArabicDescription**</span><span class="sxs-lookup"><span data-stu-id="022a8-181">**ArabicDescription**</span></span>|  
    |<span data-ttu-id="022a8-182">**HebrewDescription**</span><span class="sxs-lookup"><span data-stu-id="022a8-182">**HebrewDescription**</span></span>|  
    |<span data-ttu-id="022a8-183">**ThaiDescription**</span><span class="sxs-lookup"><span data-stu-id="022a8-183">**ThaiDescription**</span></span>|  
    |<span data-ttu-id="022a8-184">**GermanDescription**</span><span class="sxs-lookup"><span data-stu-id="022a8-184">**GermanDescription**</span></span>|  
    |<span data-ttu-id="022a8-185">**JapaneseDescription**</span><span class="sxs-lookup"><span data-stu-id="022a8-185">**JapaneseDescription**</span></span>|  
    |<span data-ttu-id="022a8-186">**TurkishDescription**</span><span class="sxs-lookup"><span data-stu-id="022a8-186">**TurkishDescription**</span></span>|  
  
    |<span data-ttu-id="022a8-187">Categoría de productos</span><span class="sxs-lookup"><span data-stu-id="022a8-187">Product Category</span></span>|  
    |----------------------|  
    |<span data-ttu-id="022a8-188">**SpanishProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="022a8-188">**SpanishProductCategoryName**</span></span>|  
    |<span data-ttu-id="022a8-189">**FrenchProductCategoryName**</span><span class="sxs-lookup"><span data-stu-id="022a8-189">**FrenchProductCategoryName**</span></span>|  
  
    |<span data-ttu-id="022a8-190">Product Subcategory</span><span class="sxs-lookup"><span data-stu-id="022a8-190">Product Subcategory</span></span>|  
    |-------------------------|  
    |<span data-ttu-id="022a8-191">**SpanishProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="022a8-191">**SpanishProductSubcategoryName**</span></span>|  
    |<span data-ttu-id="022a8-192">**FrenchProductSubcategoryName**</span><span class="sxs-lookup"><span data-stu-id="022a8-192">**FrenchProductSubcategoryName**</span></span>|  
  
    |<span data-ttu-id="022a8-193">Internet Sales</span><span class="sxs-lookup"><span data-stu-id="022a8-193">Internet Sales</span></span>|  
    |--------------------|  
    |<span data-ttu-id="022a8-194">**OrderDateKey**</span><span class="sxs-lookup"><span data-stu-id="022a8-194">**OrderDateKey**</span></span>|  
    |<span data-ttu-id="022a8-195">**DueDateKey**</span><span class="sxs-lookup"><span data-stu-id="022a8-195">**DueDateKey**</span></span>|  
    |<span data-ttu-id="022a8-196">**ShipDateKey**</span><span class="sxs-lookup"><span data-stu-id="022a8-196">**ShipDateKey**</span></span>|  
  
 <span data-ttu-id="022a8-197">Ahora que ha obtenido una vista previa de los datos innecesarios y los ha filtrado, puede importar los datos.</span><span class="sxs-lookup"><span data-stu-id="022a8-197">Now that you have previewed and filtered out unnecessary data, you can import the data.</span></span> <span data-ttu-id="022a8-198">Vaya a la siguiente sección, **Importar los datos de las columnas y las tablas seleccionadas**.</span><span class="sxs-lookup"><span data-stu-id="022a8-198">Go to the next section **Import the Selected Tables and Column Data**.</span></span>  
  
##  <a name="import-the-selected-tables-and-column-data"></a><a name="Import"></a><span data-ttu-id="022a8-199">Importar las tablas y los datos de columna seleccionados</span><span class="sxs-lookup"><span data-stu-id="022a8-199">Import the Selected Tables and Column Data</span></span>  
 <span data-ttu-id="022a8-200">Ahora puede importar los datos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="022a8-200">You can now import the selected data.</span></span> <span data-ttu-id="022a8-201">El asistente importa los datos de la tabla junto con todas las relaciones entre las tablas.</span><span class="sxs-lookup"><span data-stu-id="022a8-201">The wizard imports the table data along with any relationships between tables.</span></span> <span data-ttu-id="022a8-202">Las nuevas tablas y columnas se crean en el modelo con los nombres descriptivos que especificó, y los datos que filtró no se importan.</span><span class="sxs-lookup"><span data-stu-id="022a8-202">New tables and columns are created in the model using the friendly names you specified, and data that you filtered out will not be imported.</span></span>  
  
#### <a name="to-import-the-selected-tables-and-column-data"></a><span data-ttu-id="022a8-203">Para importar las tablas y los datos de columna seleccionados</span><span class="sxs-lookup"><span data-stu-id="022a8-203">To import the selected tables and column data</span></span>  
  
1.  <span data-ttu-id="022a8-204">Revise lo que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="022a8-204">Review your selections.</span></span> <span data-ttu-id="022a8-205">Si todo parece correcto, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="022a8-205">If everything looks OK, click **Finish**.</span></span>  
  
     <span data-ttu-id="022a8-206">Mientras importa los datos, el asistente muestra cuántas filas se han capturado.</span><span class="sxs-lookup"><span data-stu-id="022a8-206">While importing the data, the wizard displays how many rows have been fetched.</span></span> <span data-ttu-id="022a8-207">Cuando se hayan importado todos los datos, se muestra un mensaje para indicarlo.</span><span class="sxs-lookup"><span data-stu-id="022a8-207">When all the data has been imported, a message indicating success is displayed.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="022a8-208"> Para ver las relaciones que se crearon automáticamente entre las tablas importadas, en la fila **Preparación de datos** , haga clic en **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="022a8-208">To see the relationships that were automatically created between the imported tables, on the **Data preparation** row, click **Details**.</span></span>  
  
2.  <span data-ttu-id="022a8-209">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="022a8-209">Click **Close**.</span></span>  
  
     <span data-ttu-id="022a8-210">El asistente se cierra y aparece el diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="022a8-210">The wizard closes and the model designer is visible.</span></span> <span data-ttu-id="022a8-211">Cada tabla se ha agregado como una nueva pestaña en el diseñador de modelos.</span><span class="sxs-lookup"><span data-stu-id="022a8-211">Each table has been added as a new tab in the model designer.</span></span>  
  
## <a name="save-the-model-project"></a><span data-ttu-id="022a8-212">Guardar el proyecto de modelo</span><span class="sxs-lookup"><span data-stu-id="022a8-212">Save the Model Project</span></span>  
 <span data-ttu-id="022a8-213">Es importante que guarde frecuentemente el proyecto de modelo.</span><span class="sxs-lookup"><span data-stu-id="022a8-213">It is important to frequently save your model project.</span></span>  
  
#### <a name="to-save-the-model-project"></a><span data-ttu-id="022a8-214">Para guardar el proyecto de modelo</span><span class="sxs-lookup"><span data-stu-id="022a8-214">To save the model project</span></span>  
  
-   <span data-ttu-id="022a8-215">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], haga clic en el menú **Archivo** y luego en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="022a8-215">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click on the **File** menu, and then click **Save All**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="022a8-216">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="022a8-216">Next Step</span></span>  
 <span data-ttu-id="022a8-217">Para continuar este tutorial, vaya a la lección siguiente: [Lección 3: Cambiar el nombre de las columnas](rename-columns.md).</span><span class="sxs-lookup"><span data-stu-id="022a8-217">To continue this tutorial, go to the next lesson: [Lesson 3: Rename Columns](rename-columns.md).</span></span>  
  
  
