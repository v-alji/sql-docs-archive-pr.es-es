---
title: 'Lección 2: Definir una conexión de datos y una tabla de datos para el informe primario | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f02dee0c-85ad-45d4-b707-10e9e8541db9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 045ff576061bf12d163668cb9a57651e591768a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663299"
---
# <a name="lesson-2-define-a-data-connection-and-data-table-for-parent-report"></a><span data-ttu-id="19120-102">Lección 2: Definir una conexión de datos y una tabla de datos para el informe primario</span><span class="sxs-lookup"><span data-stu-id="19120-102">Lesson 2: Define a Data Connection and Data Table for Parent Report</span></span>
  <span data-ttu-id="19120-103">Después de crear un proyecto de sitio Web nuevo con la plantilla de sitio Web ASP.NET para Visual C#, el paso siguiente consiste en crear una conexión de datos y una tabla de datos para el informe primario.</span><span class="sxs-lookup"><span data-stu-id="19120-103">After you create a new website project using the ASP.NET website template for Visual C#, your next step is to create a data connection and a data table for the parent report.</span></span> <span data-ttu-id="19120-104">En este tutorial, la conexión de datos se produce con la base de datos AdventureWorks2008.</span><span class="sxs-lookup"><span data-stu-id="19120-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="19120-105">También tiene la opción de conectar con la base de datos AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="19120-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-data-table-by-adding-a-dataset-for-parent-report"></a><span data-ttu-id="19120-106">Para definir una conexión de datos y una tabla de datos agregando un DataSet (para el informe primario)</span><span class="sxs-lookup"><span data-stu-id="19120-106">To define a data connection and Data Table by adding a DataSet (for parent report)</span></span>  
  
1.  <span data-ttu-id="19120-107">En el menú **Sitio web** , seleccione **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="19120-107">On the **Website** menu, select **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="19120-108">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **conjunto** de elementos y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="19120-108">In the **Add New Item** dialog box, select **DataSet** and click **Add**.</span></span> <span data-ttu-id="19120-109">Cuando se le pida, debe agregar el elemento a la carpeta **App_Code** haciendo clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="19120-109">When prompted you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="19120-110">De este modo, agrega un nuevo archivo XSD **DataSet1.xsd** al proyecto y abre el Diseñador de DataSet.</span><span class="sxs-lookup"><span data-stu-id="19120-110">This adds a new XSD file **DataSet1.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="19120-111">En la ventana cuadro de herramientas, arrastre un control **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** hasta la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="19120-111">From the Toolbox window, drag a **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** control to the design surface.</span></span> <span data-ttu-id="19120-112">De este modo, se inicia el Asistente para configuración de **TableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="19120-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="19120-113">En la página **elegir la conexión de datos** , haga clic en **nueva conexión**.</span><span class="sxs-lookup"><span data-stu-id="19120-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="19120-114">Si es la primera vez que crea un origen de datos en Visual Studio, verá la página **elegir origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="19120-114">If this is the first time you've created a data source in Visual Studio, you will see the **Choose Data Source** page.</span></span> <span data-ttu-id="19120-115">En el cuadro **Origen de datos** , seleccione **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="19120-115">In the **Data Source** box, select **Microsoft SQL Server**.</span></span>  
  
6.  <span data-ttu-id="19120-116">En el cuadro de diálogo **Agregar conexión** , realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="19120-116">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="19120-117">En el cuadro **nombre del servidor** , escriba el servidor donde se encuentra la base de datos **AdventureWorks2008** .</span><span class="sxs-lookup"><span data-stu-id="19120-117">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="19120-118">La instancia de SQL Server Express predeterminada es **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="19120-118">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="19120-119">En la sección **Iniciar sesión en el servidor** , seleccione la opción que proporciona acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="19120-119">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="19120-120">**Usar autenticación de Windows** es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="19120-120">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="19120-121">En la lista desplegable **Seleccione o escriba un nombre de base de datos** , haga clic en **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="19120-121">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="19120-122">Haga clic en **Aceptar** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19120-122">Click **OK**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="19120-123">Si ha seleccionado **Usar autenticación de SQL Server** en el paso 6 (b), seleccione la opción si quiere incluir la información confidencial en la cadena o establecer la información en su código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="19120-123">If you selected **Use SQL Server Authentication** in the Step 6 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
8.  <span data-ttu-id="19120-124">En la página **guardar la cadena de conexión en el archivo de configuración de la aplicación** , escriba el nombre de la cadena de conexión o acepte el valor predeterminado **AdventureWorks2008ConnectionString**.</span><span class="sxs-lookup"><span data-stu-id="19120-124">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="19120-125">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="19120-125">Click **Next**.</span></span>  
  
9. <span data-ttu-id="19120-126">En la página **elegir un tipo de comando** , seleccione **usar instrucciones SQL**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19120-126">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="19120-127">En la página **Escriba una instrucción SQL** , escriba la siguiente consulta de TRANSACT-SQL para recuperar datos de la base de datos **AdventureWorks2008** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19120-127">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT ProductID, Name, ProductNumber, SafetyStockLevel, ReorderPoint FROM  Production.Product Order By ProductID  
    ```  
  
     <span data-ttu-id="19120-128">También puede crear la consulta haciendo clic en **generador de consultas**y, a continuación, comprobar la consulta haciendo clic en **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="19120-128">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query**.</span></span> <span data-ttu-id="19120-129">Si la consulta no devuelve los datos esperados, puede utilizar una versión anterior de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="19120-129">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="19120-130">Para obtener más información acerca de cómo instalar la versión **AdventureWorks2008** de AdventureWorks, vea [Tutorial: instalar la base de datos AdventureWorks](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="19120-130">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
11. <span data-ttu-id="19120-131">En la página **elegir los métodos que se van a generar** , asegúrese de desactivar **crear métodos para enviar actualizaciones directamente a la base de datos (GenerateDBDirectMethods)** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="19120-131">On the **Choose Methods to Generate** page, be sure to uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="19120-132">Asegúrese de desactivar la creación</span><span class="sxs-lookup"><span data-stu-id="19120-132">Be sure to uncheck Create</span></span>  
  
     <span data-ttu-id="19120-133">Ahora ha completado la configuración del objeto DataTable de ADO.NET como origen de datos para el informe.</span><span class="sxs-lookup"><span data-stu-id="19120-133">You have now completed configuring the ADO.NET DataTable object as the data source for your report.</span></span> <span data-ttu-id="19120-134">En la página del Diseñador de Dataset en Visual Studio, debería ver el objeto DataTable que agregó, con las columnas especificadas en la consulta.</span><span class="sxs-lookup"><span data-stu-id="19120-134">On the DataSet Designer page in Visual Studio, you should see the DataTable object you added, listing the columns specified in the query.</span></span> <span data-ttu-id="19120-135">DataSet1 contiene los datos de la tabla Product, según la consulta.</span><span class="sxs-lookup"><span data-stu-id="19120-135">DataSet1 contains the data from the Product table, based on the query.</span></span>  
  
12. <span data-ttu-id="19120-136">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="19120-136">Save the file.</span></span>  
  
13. <span data-ttu-id="19120-137">Para obtener una vista previa de los datos, haga clic en **vista previa de datos** en el menú **datos** y, a continuación, haga clic en **vista previa**.</span><span class="sxs-lookup"><span data-stu-id="19120-137">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="19120-138">Tarea siguiente</span><span class="sxs-lookup"><span data-stu-id="19120-138">Next Task</span></span>  
 <span data-ttu-id="19120-139">Ha creado correctamente una conexión de datos y una tabla de datos para el informe primario.</span><span class="sxs-lookup"><span data-stu-id="19120-139">You have successfully created a data connection and a data table for the parent report.</span></span> <span data-ttu-id="19120-140">Después, diseñará el informe primario usando el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="19120-140">Next, you will design the parent report using the Report Wizard.</span></span>  
  
  
