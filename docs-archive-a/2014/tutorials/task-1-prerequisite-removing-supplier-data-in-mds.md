---
title: 'Tarea 1 (requisito previo): eliminación de los datos de proveedor en MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6f0a4287-7fd4-4f18-b7e4-a5191a9d4a3c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e78dc5ff04f95d42cf440e3f80b1b349e0315a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675693"
---
# <a name="task-1-prerequisite-removing-supplier-data-in-mds"></a><span data-ttu-id="0ed45-102">Tarea 1 (requisito previo): Eliminación de datos de proveedor en MDS</span><span class="sxs-lookup"><span data-stu-id="0ed45-102">Task 1 (Prerequisite): Removing Supplier Data in MDS</span></span>
  <span data-ttu-id="0ed45-103">En esta tarea, quitará los datos de proveedor almacenados en MDS.</span><span class="sxs-lookup"><span data-stu-id="0ed45-103">In this task, you remove the supplier data stored in MDS.</span></span> <span data-ttu-id="0ed45-104">En la lección anterior cargó los datos manualmente mediante el **complemento MDS para Excel** .</span><span class="sxs-lookup"><span data-stu-id="0ed45-104">You uploaded the data manually using **MDS Excel Add-in** in the previous lesson.</span></span> <span data-ttu-id="0ed45-105">El paquete de SSIS que cree en esta lección cargará los datos en MDS automáticamente.</span><span class="sxs-lookup"><span data-stu-id="0ed45-105">The SSIS package you create in this lesson will automatically upload the data to MDS for you.</span></span> <span data-ttu-id="0ed45-106">Por tanto, antes de probar el paquete de SSIS, necesita quitar los datos de proveedor de MDS, quitar la jerarquía derivada, quitar las entidades Proveedor y Estado, y crear la entidad Proveedor sin datos.</span><span class="sxs-lookup"><span data-stu-id="0ed45-106">Therefore, before testing the SSIS package, you need to remove the supplier data from MDS, remove the derived hierarchy, remove supplier and state entities, and create the supplier entity with no data.</span></span>  
  
1.  <span data-ttu-id="0ed45-107">Inicie **Master Data Manager** navegando hasta `http://localhost/MDS` o el sitio web y la aplicación que especificó al configurar MDS.</span><span class="sxs-lookup"><span data-stu-id="0ed45-107">Launch **Master Data Manager** by navigating to `http://localhost/MDS` or the website and application you specified when configuring MDS.</span></span> <span data-ttu-id="0ed45-108">Si dejó **Master Data Manager** abierto, haga clic en **SQL Server 2012 Master Data Services** en la parte superior para cambiar a la **página principal**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-108">If you kept the **Master Data Manager** open, click **SQL Server 2012 Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="0ed45-109">Haga clic en **Administración del sistema** en la sección **Tareas administrativas** .</span><span class="sxs-lookup"><span data-stu-id="0ed45-109">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="0ed45-110">Mantenga el mouse sobre **Administrar** en el menú y haga clic en **Jerarquías derivadas**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-110">Hover the mouse over **Manage** on the menu and click **Derived Hierarchies**.</span></span> <span data-ttu-id="0ed45-111">Necesita eliminar la jerarquía derivada **SuppliersInState** antes de eliminar las entidades del modelo **Proveedores** .</span><span class="sxs-lookup"><span data-stu-id="0ed45-111">You need to delete the derived hierarchy **SuppliersInState** before deleting the entities in the **Suppliers** model.</span></span>  
  
4.  <span data-ttu-id="0ed45-112">Seleccione **SuppliersInState** en la lista **Jerarquía derivada** y haga clic en el botón **X (Eliminar)** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="0ed45-112">Select **SuppliersInState** from the **Derived Hierarchy** list and click **X (Delete)** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="0ed45-113">Haga clic en **Aceptar** para confirmar la eliminación.</span><span class="sxs-lookup"><span data-stu-id="0ed45-113">Click **OK** to confirm deletion.</span></span>  
  
6.  <span data-ttu-id="0ed45-114">Mantenga el mouse sobre **Administrar** en el menú y haga clic en **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-114">Hover the mouse over **Manage** on the menu and click **Entities**.</span></span>  
  
7.  <span data-ttu-id="0ed45-115">Haga clic en **Proveedor** y, a continuación, haga clic en el botón **Eliminar (X)** de la barra de herramientas para eliminar la entidad.</span><span class="sxs-lookup"><span data-stu-id="0ed45-115">Click **Supplier** and click **Delete (X)** button on toolbar to delete the entity.</span></span> <span data-ttu-id="0ed45-116">Haga clic en **Aceptar** en los cuadros de mensajes.</span><span class="sxs-lookup"><span data-stu-id="0ed45-116">Click **OK** on message boxes.</span></span>  
  
8.  <span data-ttu-id="0ed45-117">Repita el paso anterior para eliminar la entidad **Estado** .</span><span class="sxs-lookup"><span data-stu-id="0ed45-117">Repeat the previous step to delete **State** entity.</span></span>  
  
9. <span data-ttu-id="0ed45-118">No cierre **Master Data Manager**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-118">Don't close **Master Data Manager**.</span></span>  
  
10. <span data-ttu-id="0ed45-119">Cambie a la ventana de Excel que tiene abierto el archivo **Cleansed and Matched Suppliers.xls** .</span><span class="sxs-lookup"><span data-stu-id="0ed45-119">Switch to the Excel window that has **Cleansed and Matched Suppliers.xls** file open.</span></span> <span data-ttu-id="0ed45-120">Cambie a la pestaña **Hoja1** en la parte inferior.</span><span class="sxs-lookup"><span data-stu-id="0ed45-120">Switch to the **Sheet1** tab at the bottom.</span></span>  
  
11. <span data-ttu-id="0ed45-121">Seleccione solo la **primera fila con encabezados**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-121">Select only the **first row with headers**.</span></span> <span data-ttu-id="0ed45-122">No seleccione ninguna otra fila.</span><span class="sxs-lookup"><span data-stu-id="0ed45-122">Don't select any other row.</span></span> <span data-ttu-id="0ed45-123">Desea crear las entidades basadas en las columnas de Excel pero no desea cargar ningún dato.</span><span class="sxs-lookup"><span data-stu-id="0ed45-123">You want to create the entities based on the Excel columns but don't want to upload any data.</span></span> <span data-ttu-id="0ed45-124">Por tanto, solo selecciona la primera fila con los encabezados.</span><span class="sxs-lookup"><span data-stu-id="0ed45-124">Therefore you select only the first row with the headers.</span></span>  
  
12. <span data-ttu-id="0ed45-125">Haga clic en **Datos maestros** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="0ed45-125">Click **Master Data** on the menu bar.</span></span>  
  
13. <span data-ttu-id="0ed45-126">Haga clic en **Crear entidad** en la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="0ed45-126">Click **Create Entity** from the ribbon.</span></span>  
  
14. <span data-ttu-id="0ed45-127">En el cuadro de diálogo **Administrar conexiones** , si no ve la conexión al **servidor MDS local** bajo **Conexiones existentes**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ed45-127">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="0ed45-128">Seleccione **Crear una nueva conexión**y haga clic en el botón **Nuevo** .</span><span class="sxs-lookup"><span data-stu-id="0ed45-128">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="0ed45-129">En el cuadro de diálogo Agregar nueva conexión, escriba **servidor MDS local** para **Descripción** y **http: \/ /localhost/MDS** para la **dirección del servidor MDS**y haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0ed45-129">In the Add New Connection dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="0ed45-130">En el cuadro de diálogo **Administrar conexiones** , seleccione **servidor MDS local** ( `http://localhost/MDS` ), haga clic en **probar** para probar la conexión.</span><span class="sxs-lookup"><span data-stu-id="0ed45-130">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="0ed45-131">Haga clic en **Aceptar** en el cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="0ed45-131">Click **OK** on the message box.</span></span>  
  
16. <span data-ttu-id="0ed45-132">Haga clic en **Conectar** para establecer una conexión con el servidor MDS.</span><span class="sxs-lookup"><span data-stu-id="0ed45-132">Click **Connect** to make a connection to the MDS server.</span></span>  
  
17. <span data-ttu-id="0ed45-133">En el cuadro de diálogo **Crear entidad** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ed45-133">In the **Create Entity** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="0ed45-134">Confirme que **Rango** está establecido en **$1:$1**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-134">Confirm that **Range** is set to **$1:$1**.</span></span>  
  
    2.  <span data-ttu-id="0ed45-135">Seleccione **Proveedores** en **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-135">Select **Suppliers** for **Model**.</span></span>  
  
    3.  <span data-ttu-id="0ed45-136">Seleccione **VERSION_1** en **Versión**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-136">Select **VERSION_1** for **Version**.</span></span>  
  
    4.  <span data-ttu-id="0ed45-137">Escriba **Proveedor** en **Nuevo nombre de entidad**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-137">Type **Supplier** for **New entity name**.</span></span>  
  
    5.  <span data-ttu-id="0ed45-138">Seleccione **SupplierID** en **Código**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-138">Select **SupplierID** for **Code**.</span></span>  
  
    6.  <span data-ttu-id="0ed45-139">Seleccione **Supplier Name** en **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-139">Select **Supplier Name** for **Name**.</span></span>  
  
    7.  <span data-ttu-id="0ed45-140">Haga clic en **Aceptar** para crear la entidad y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0ed45-140">Click **OK** to create the entity and close the dialog box.</span></span>  
  
18. <span data-ttu-id="0ed45-141">Cierre **Excel** y **no guarde** el archivo.</span><span class="sxs-lookup"><span data-stu-id="0ed45-141">Close **Excel** and **do not save** the file.</span></span>  
  
19. <span data-ttu-id="0ed45-142">En **Master Data Manager**, actualice el navegador de Internet y confirme que aparece la entidad **Supplier** en la lista.</span><span class="sxs-lookup"><span data-stu-id="0ed45-142">In **Master Data Manager**, refresh the internet browser and confirm that **Supplier** entity is displayed in the list.</span></span>  
  
20. <span data-ttu-id="0ed45-143">Vaya a la **página principal** haciendo clic en **SQL Server 2012 Master Data Services** en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="0ed45-143">Switch to the **home page** by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
21. <span data-ttu-id="0ed45-144">Confirme que el modelo **Proveedores** está seleccionado en **Modelo** y **VERSION_1** está seleccionado para **Versión**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-144">Confirm that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**.</span></span>  
  
22. <span data-ttu-id="0ed45-145">Haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-145">Click **Explorer**.</span></span> <span data-ttu-id="0ed45-146">Observe que se crea la entidad **Proveedor** con todos los atributos **sin ningún valor**.</span><span class="sxs-lookup"><span data-stu-id="0ed45-146">Notice that the **Supplier** entity with all the attributes is created with **no values**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="0ed45-147">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="0ed45-147">Next Step</span></span>  
 [<span data-ttu-id="0ed45-148">Tarea 2 &#40;&#41; opcional: crear una vista de suscripciones de MDS con Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="0ed45-148">Task 2 &#40;Optional&#41;: Creating a MDS Subscription View using Master Data Manager</span></span>](../../2014/tutorials/task-2-optional-creating-a-mds-subscription-view-using-master-data-manager.md)  
  
  
