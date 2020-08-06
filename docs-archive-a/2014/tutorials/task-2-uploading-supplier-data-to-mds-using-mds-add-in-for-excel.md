---
title: 'Tarea 2: carga de datos de proveedor en MDS mediante Complemento MDS para Excel | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 598deb57-e0cc-4e0a-aeb1-94432c094c67
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 16c5fa9db81649b30c12fae4d2e57afa8bf094e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662416"
---
# <a name="task-2-uploading-supplier-data-to-mds-using-mds-add-in-for-excel"></a><span data-ttu-id="8c92f-102">Tarea 2: Carga de datos de proveedor en MDS con el complemento MDS para Excel</span><span class="sxs-lookup"><span data-stu-id="8c92f-102">Task 2: Uploading Supplier Data to MDS using MDS Add-in for Excel</span></span>
  <span data-ttu-id="8c92f-103">En esta tarea, publicará los datos limpios y de proveedor en **MDS** mediante el **complemento MDS para Excel**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-103">In this task, you publish the cleansed and supplier data to **MDS** using the **MDS Add-in for Excel**.</span></span> <span data-ttu-id="8c92f-104">Cree una entidad denominada **Supplier** en el modelo **proveedores** que creó en la lección anterior.</span><span class="sxs-lookup"><span data-stu-id="8c92f-104">You create an entity named **Supplier** in the **Suppliers** model you created in the previous lesson.</span></span> <span data-ttu-id="8c92f-105">La entidad tendrá un atributo para cada columna del archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="8c92f-105">The entity will have an attribute for each column in the Excel file.</span></span> <span data-ttu-id="8c92f-106">Los atributos Code y Name de la entidad Supplier corresponden a las columnas **SupplierID** y **Supplier Name** de Excel.</span><span class="sxs-lookup"><span data-stu-id="8c92f-106">The Code and Name attributes of the Supplier entity correspond to the **SupplierID** and **Supplier Name** columns in Excel.</span></span>  
  
1.  <span data-ttu-id="8c92f-107">Abra **Suppliers.xlslimpiadas y coincidentes** en **Excel**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-107">Open **Cleansed and Matched Suppliers.xls** in **Excel**.</span></span>  
  
2.  <span data-ttu-id="8c92f-108">Presione **Ctrl +** a para seleccionar todos los datos.</span><span class="sxs-lookup"><span data-stu-id="8c92f-108">Press **CTRL+A** to select entire data.</span></span> <span data-ttu-id="8c92f-109">Es **importante** que seleccione todos los datos en la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="8c92f-109">It is **important** that you select the entire data in the spreadsheet.</span></span>  
  
3.  <span data-ttu-id="8c92f-110">Haga clic en **Datos maestros** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="8c92f-110">Click **Master Data** on the menu bar.</span></span>  
  
4.  <span data-ttu-id="8c92f-111">Haga clic en el botón **crear entidad** de la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="8c92f-111">Click **Create Entity** button on the ribbon.</span></span>  
  
     <span data-ttu-id="8c92f-112">![Excel - Pestaña de datos maestros - Botón Crear entidad](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel - Pestaña de datos maestros - Botón Crear entidad")</span><span class="sxs-lookup"><span data-stu-id="8c92f-112">![Excel - Master Data Tab - Create Entity Button](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel - Master Data Tab - Create Entity Button")</span></span>  
  
5.  <span data-ttu-id="8c92f-113">En el cuadro de diálogo **Administrar conexiones** , si no ve la conexión al **servidor MDS local** bajo **Conexiones existentes**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8c92f-113">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="8c92f-114">Seleccione **Crear una nueva conexión**y haga clic en el botón **Nuevo** .</span><span class="sxs-lookup"><span data-stu-id="8c92f-114">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="8c92f-115">En el cuadro de diálogo **Agregar nueva conexión** , escriba **servidor MDS local** para **Descripción** y **http: \/ /localhost/MDS** para la **dirección del servidor MDS**y haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8c92f-115">In the **Add New Connection** dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="8c92f-116">En el cuadro de diálogo **Administrar conexiones** , seleccione **servidor MDS local** ( `http://localhost/MDS` ), haga clic en **probar** para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="8c92f-116">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="8c92f-117">Haga clic en **Aceptar** en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="8c92f-117">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="8c92f-118">Haga clic en **conectar** para conectarse al servidor de MDS.</span><span class="sxs-lookup"><span data-stu-id="8c92f-118">Click **Connect** to connect to the MDS server.</span></span>  
  
8.  <span data-ttu-id="8c92f-119">En el cuadro de diálogo **crear entidad** , seleccione **proveedores** para el **modelo**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-119">In the **Create Entity** dialog box, select **Suppliers** for the **Model**.</span></span>  
  
9. <span data-ttu-id="8c92f-120">Asegúrese de que **VERSION_1** está seleccionado para **versión**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-120">Ensure that **VERSION_1** is selected for **Version**.</span></span>  
  
10. <span data-ttu-id="8c92f-121">Escriba **proveedor** para **el nuevo nombre de entidad**.</span><span class="sxs-lookup"><span data-stu-id="8c92f-121">Enter **Supplier** for **New entity name**.</span></span>  
  
11. <span data-ttu-id="8c92f-122">Seleccione **IdProveedor** en **la columna que contiene un identificador único** (también puede generar un código automáticamente).</span><span class="sxs-lookup"><span data-stu-id="8c92f-122">Select **SupplierID** for **the column that contains a unique identifier** field (you can also generate a code automatically).</span></span> <span data-ttu-id="8c92f-123">Básicamente está asignando la columna **SupplierID** en **Excel** al atributo **code** de la entidad **Supplier** .</span><span class="sxs-lookup"><span data-stu-id="8c92f-123">You are essentially mapping the **SupplierID** column in **Excel** to the **Code** attribute of **Supplier** entity.</span></span>  
  
12. <span data-ttu-id="8c92f-124">Seleccione **nombre de proveedor** para **la columna que contiene el campo nombres** .</span><span class="sxs-lookup"><span data-stu-id="8c92f-124">Select **Supplier Name** for **the column that contains names** field.</span></span> <span data-ttu-id="8c92f-125">Básicamente está asignando la columna **Supplier Name** de **Excel** al atributo **Name** de la entidad **Supplier** .</span><span class="sxs-lookup"><span data-stu-id="8c92f-125">You are essentially mapping the **Supplier Name** column in **Excel** to the **Name** attribute of the **Supplier** entity.</span></span> <span data-ttu-id="8c92f-126">Los atributos **code** y **Name** son atributos obligatorios para una entidad en MDS.</span><span class="sxs-lookup"><span data-stu-id="8c92f-126">The **Code** and **Name** attributes are mandatory attributes for an entity in MDS.</span></span>  
  
     <span data-ttu-id="8c92f-127">![Cuadro de diálogo Crear entidad](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Cuadro de diálogo Crear entidad")</span><span class="sxs-lookup"><span data-stu-id="8c92f-127">![Create Entity Dialog Box](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Create Entity Dialog Box")</span></span>  
  
13. <span data-ttu-id="8c92f-128">Haga clic en **Aceptar** para crear la entidad en MDS, publicar los datos maestros en la entidad y cerrar el cuadro de diálogo **crear entidad** .</span><span class="sxs-lookup"><span data-stu-id="8c92f-128">Click **OK** to create the entity on MDS, publish the master data to the entity, and close **Create Entity** dialog box.</span></span>  
  
14. <span data-ttu-id="8c92f-129">Ahora debería ver una nueva hoja titulada **proveedor**, que es el nombre de la entidad, agregada a la hoja de cálculo de Excel y en la parte superior de la hoja de cálculo debería ver que la hoja de cálculo está conectada al servidor MDS.</span><span class="sxs-lookup"><span data-stu-id="8c92f-129">Now, you should see a new sheet titled **Supplier**, which is the name of the entity, added to your Excel spreadsheet and at the top of the worksheet you should see that the worksheet is connected to the MDS server.</span></span> <span data-ttu-id="8c92f-130">Observe que la hoja de cálculo original (titulada **Hoja1**) sigue existiendo.</span><span class="sxs-lookup"><span data-stu-id="8c92f-130">Notice that the original worksheet (titled **Sheet1**) still exists.</span></span>  
  
     <span data-ttu-id="8c92f-131">![Excel - Pestañas Proveedor y Hoja1](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel - Pestañas Proveedor y Hoja1")</span><span class="sxs-lookup"><span data-stu-id="8c92f-131">![Excel - Supplier and Sheet1 Tabs](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel - Supplier and Sheet1 Tabs")</span></span>  
  
     <span data-ttu-id="8c92f-132">![Excel - Mostrar detalles de conexión MDS](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel - Mostrar detalles de conexión MDS")</span><span class="sxs-lookup"><span data-stu-id="8c92f-132">![Excel - Showing MDS Connection Details](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel - Showing MDS Connection Details")</span></span>  
  
15. <span data-ttu-id="8c92f-133">Mantenga abierto **Excel** .</span><span class="sxs-lookup"><span data-stu-id="8c92f-133">Keep **Excel** open.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="8c92f-134">Tarea siguiente</span><span class="sxs-lookup"><span data-stu-id="8c92f-134">Next Task</span></span>  
 [<span data-ttu-id="8c92f-135">Tarea 3: Comprobación de los datos en Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="8c92f-135">Task 3: Verifying the Data in Master Data Manager</span></span>](../../2014/tutorials/task-3-verifying-the-data-in-master-data-manager.md)  
  
  
