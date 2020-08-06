---
title: 'Lección 4: Definir una conexión de datos y una tabla de datos para el informe secundario | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6aa2c56-227c-43c5-a28e-c7104131ac5e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d9144d960ad933afa65f9d4483e96b5f732d944
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669507"
---
# <a name="lesson-4-define-a-data-connection-and-data-table-for-child-report"></a><span data-ttu-id="90c4c-102">Lección 4: Definir una conexión de datos y una tabla de datos para el informe secundario</span><span class="sxs-lookup"><span data-stu-id="90c4c-102">Lesson 4: Define a Data Connection and Data Table for Child Report</span></span>
  <span data-ttu-id="90c4c-103">Después de diseñar el informe primario, el paso siguiente es crear una conexión de datos y una tabla de datos para el informe secundario.</span><span class="sxs-lookup"><span data-stu-id="90c4c-103">After you design the parent report, you next step is to create a data connection and a data table for the child report.</span></span> <span data-ttu-id="90c4c-104">En este tutorial, la conexión de datos se produce con la base de datos AdventureWorks2008.</span><span class="sxs-lookup"><span data-stu-id="90c4c-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="90c4c-105">También tiene la opción de conectar con la base de datos AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="90c4c-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-datatable-by-adding-a-dataset-for-child-report"></a><span data-ttu-id="90c4c-106">Para definir una conexión de datos y una DataTable agregando un DataSet (para el informe secundario)</span><span class="sxs-lookup"><span data-stu-id="90c4c-106">To define a data connection and DataTable by adding a DataSet (for child report)</span></span>  
  
1.  <span data-ttu-id="90c4c-107">En el menú **sitio web** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-107">On the **Website** menu, click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="90c4c-108">En el cuadro de diálogo **Agregar nuevo elemento** , haga clic en **DataSet** y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-108">In the **Add New Item** dialog box, click **DataSet** and then click **Add**.</span></span> <span data-ttu-id="90c4c-109">Cuando se le pida, debe agregar el elemento a la carpeta **App_Code** haciendo clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-109">When prompted, you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="90c4c-110">De este modo, agrega un nuevo archivo XSD **DataSet2.xsd** al proyecto y abre el Diseñador de DataSet.</span><span class="sxs-lookup"><span data-stu-id="90c4c-110">This adds a new XSD file **DataSet2.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="90c4c-111">En la ventana del Cuadro de herramientas, arrastre un control **TableAdapter** hasta la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="90c4c-111">From the Toolbox window, drag a **TableAdapter** control to the design surface.</span></span> <span data-ttu-id="90c4c-112">De este modo, se inicia el Asistente para configuración de **TableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="90c4c-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="90c4c-113">En la página **elegir la conexión de datos** , haga clic en **nueva conexión**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="90c4c-114">En el cuadro de diálogo **Agregar conexión** , realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="90c4c-114">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="90c4c-115">En el cuadro **nombre del servidor** , escriba el servidor donde se encuentra la base de datos **AdventureWorks2008** .</span><span class="sxs-lookup"><span data-stu-id="90c4c-115">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="90c4c-116">La instancia de SQL Server Express predeterminada es **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-116">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="90c4c-117">En la sección **Iniciar sesión en el servidor** , seleccione la opción que proporciona acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="90c4c-117">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="90c4c-118">**Usar autenticación de Windows** es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="90c4c-118">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="90c4c-119">En la lista desplegable **Seleccione o escriba un nombre de base de datos** , haga clic en **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-119">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="90c4c-120">Haga clic en **Aceptar** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-120">Click **OK**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="90c4c-121">Si ha seleccionado **Usar autenticación de SQL Server** en el paso 5 (b), seleccione la opción si quiere incluir la información confidencial en la cadena o establecer la información en su código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="90c4c-121">If you selected **Use SQL Server Authentication** in Step 5 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
7.  <span data-ttu-id="90c4c-122">En la página **guardar la cadena de conexión en el archivo de configuración de la aplicación** , escriba el nombre de la cadena de conexión o acepte el valor predeterminado **AdventureWorks2008ConnectionString**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-122">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="90c4c-123">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-123">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="90c4c-124">En la página **elegir un tipo de comando** , seleccione **usar instrucciones SQL**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-124">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="90c4c-125">En la página **Escriba una instrucción SQL** , escriba la siguiente consulta de TRANSACT-SQL para recuperar datos de la base de datos **AdventureWorks2008** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-125">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail  
    ```  
  
     <span data-ttu-id="90c4c-126">También puede crear la consulta haciendo clic en **generador de consultas**y, a continuación, comprobar la consulta haciendo clic en el botón **Ejecutar consulta** .</span><span class="sxs-lookup"><span data-stu-id="90c4c-126">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query** button.</span></span> <span data-ttu-id="90c4c-127">Si la consulta no devuelve los datos esperados, puede utilizar una versión anterior de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="90c4c-127">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="90c4c-128">Para obtener más información acerca de cómo instalar la versión **AdventureWorks2008** de AdventureWorks, vea [Tutorial: instalar la base de datos AdventureWorks](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="90c4c-128">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
10. <span data-ttu-id="90c4c-129">En la página **elegir los métodos que se van a generar** , desactive **crear métodos para enviar actualizaciones directamente a la base de datos (GenerateDBDirectMethods)** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-129">On the **Choose Methods to Generate** page, uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="90c4c-130">Ya ha completado la configuración de la [DataTable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) ADO.net como origen de datos para el informe.</span><span class="sxs-lookup"><span data-stu-id="90c4c-130">You have now completed configuring the ADO.NET [DataTable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) as data source for your report.</span></span> <span data-ttu-id="90c4c-131">En la página del Diseñador de Dataset en Visual Studio, debería ver el objeto **DataTable** que ha agregado, con las columnas especificadas en la consulta.</span><span class="sxs-lookup"><span data-stu-id="90c4c-131">On the DataSet Designer page in Visual Studio, you should see the **DataTable** you added, listing the columns specified in the query.</span></span> <span data-ttu-id="90c4c-132">DataSet2 contiene los datos de la tabla PurhcaseOrderDetail, según la consulta.</span><span class="sxs-lookup"><span data-stu-id="90c4c-132">DataSet2 contains the data from the PurhcaseOrderDetail table, based on the query.</span></span>  
  
11. <span data-ttu-id="90c4c-133">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="90c4c-133">Save the file.</span></span>  
  
12. <span data-ttu-id="90c4c-134">Para obtener una vista previa de los datos, haga clic en **vista previa de datos** en el menú **datos** y, a continuación, haga clic en **vista previa**.</span><span class="sxs-lookup"><span data-stu-id="90c4c-134">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="90c4c-135">Tarea siguiente</span><span class="sxs-lookup"><span data-stu-id="90c4c-135">Next Task</span></span>  
 <span data-ttu-id="90c4c-136">Ha creado correctamente una conexión de datos y una tabla de datos para el informe secundario.</span><span class="sxs-lookup"><span data-stu-id="90c4c-136">You have successfully created a data connection and data table for the child report.</span></span> <span data-ttu-id="90c4c-137">Después, diseñará el informe secundario usando el Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="90c4c-137">Next, you will design the child report using the Report Wizard.</span></span>  
  
  
