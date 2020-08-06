---
title: 'Tarea 4 (opcional): combinar, buscar coincidencias y publicar un conjunto de datos nuevo | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 13a13f03-b307-4555-8e33-6d98c459d994
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 9ddcec19fa8b957bf77b6ea5269b4d033779bdf1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663210"
---
# <a name="task-4-optional-combining-matching-and-publishing-new-set-of-data"></a><span data-ttu-id="383a7-102">Tarea 4 (opcional): Combinación, búsqueda de coincidencias y publicación de un conjunto de datos nuevo</span><span class="sxs-lookup"><span data-stu-id="383a7-102">Task 4 (Optional): Combining, Matching, and Publishing New Set of Data</span></span>
  <span data-ttu-id="383a7-103">Con el tiempo, le interesará agregar más datos al repositorio MDS.</span><span class="sxs-lookup"><span data-stu-id="383a7-103">Over time, you will want to add more data to the MDS repository.</span></span> <span data-ttu-id="383a7-104">Antes de agregar datos, puede ser útil comparar los nuevos datos con los datos que ya se administran en MDS, para asegurarse de que no se agregan datos duplicados o inexactos.</span><span class="sxs-lookup"><span data-stu-id="383a7-104">Before adding data, it can be useful to compare the new data to the data that's already managed in MDS, to ensure that you are not adding duplicate or inaccurate data.</span></span> <span data-ttu-id="383a7-105">En el complemento Master Data Services para Excel, puede combinar datos de dos hojas de cálculo y comparar los datos para identificar y quitar duplicados antes de publicar los datos en MDS.</span><span class="sxs-lookup"><span data-stu-id="383a7-105">In the Master Data Services Add-in for Excel, you can combine data from two worksheets and the compare the data to identify and remove duplicates before publishing the data to MDS.</span></span> <span data-ttu-id="383a7-106">La característica de búsqueda de coincidencias del complemento MDS para Excel emplea la funcionalidad de coincidencia de DQS para identificar coincidencias en los datos.</span><span class="sxs-lookup"><span data-stu-id="383a7-106">The matching feature of MDS Excel Add-in uses the DQS matching functionality to identify matches in the data.</span></span> <span data-ttu-id="383a7-107">En esta tarea, combinará datos de dos hojas de cálculo en una y después buscará coincidencias para identificar y quitar duplicados antes de publicar los datos en MDS.</span><span class="sxs-lookup"><span data-stu-id="383a7-107">In this task, you will combine data from a two worksheets into one and then perform the matching activity to identify and remove duplicates before publishing to MDS.</span></span> <span data-ttu-id="383a7-108">Vea [coincidencia de calidad de datos en los temas complemento MDS para Excel](https://msdn.microsoft.com/library/hh548681.aspx) y [combinar datos](https://msdn.microsoft.com/library/hh548680.aspx) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="383a7-108">See [Data Quality Matching in the MDS Add-in for Excel](https://msdn.microsoft.com/library/hh548681.aspx) and [Combine Data](https://msdn.microsoft.com/library/hh548680.aspx) topics for more details.</span></span>  
  
1.  <span data-ttu-id="383a7-109">Inicie una nueva instancia de **Excel**.</span><span class="sxs-lookup"><span data-stu-id="383a7-109">Launch new instance of **Excel**.</span></span> <span data-ttu-id="383a7-110">Haga clic en **Inicio**, seleccione **Ejecutar**, escriba **Excel**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="383a7-110">Click **Start**, point to **Run**, type **Excel**, and click **OK**.</span></span>  
  
2.  <span data-ttu-id="383a7-111">Cambie a la pestaña **datos maestros** haciendo clic en **datos maestros** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="383a7-111">Switch to the **Master Data** tab by clicking **Master Data** on the menu bar.</span></span>  
  
3.  <span data-ttu-id="383a7-112">Haga clic en **conectar** en la cinta de opciones del grupo **conectar y cargar** para conectarse al **servidor MDS**.</span><span class="sxs-lookup"><span data-stu-id="383a7-112">Click **Connect** on the ribbon in the **Connect and Load** group to connect to the **MDS server**.</span></span> <span data-ttu-id="383a7-113">Ha configurado esta conexión anteriormente en esta lección.</span><span class="sxs-lookup"><span data-stu-id="383a7-113">You have configured this connection earlier in this lesson.</span></span>  
  
     <span data-ttu-id="383a7-114">![Excel - Botón Mostrar explorador de la pestaña Datos maestros](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel - Botón Mostrar explorador de la pestaña Datos maestros")</span><span class="sxs-lookup"><span data-stu-id="383a7-114">![Excel - Show Explorer Button on Master Data Tabl](../../2014/tutorials/media/et-combinematchandpublishnewsod-01.jpg "Excel - Show Explorer Button on Master Data Tabl")</span></span>  
  
4.  <span data-ttu-id="383a7-115">Debería ver el panel de **Explorador de datos maestro** a la derecha.</span><span class="sxs-lookup"><span data-stu-id="383a7-115">You should see the **Master Data Explorer** pane to the right.</span></span> <span data-ttu-id="383a7-116">Si no ve el Explorador de datos maestro, haga clic en el botón **Mostrar explorador** de la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="383a7-116">If you do not see the Master Data Explorer, click **Show Explorer** button on the ribbon.</span></span>  
  
5.  <span data-ttu-id="383a7-117">En la ventana de **Explorador de datos maestra** , seleccione **proveedores** en la lista desplegable del **modelo**.</span><span class="sxs-lookup"><span data-stu-id="383a7-117">In the **Master Data Explorer** Window, select **Suppliers** in the drop-down list for the **Model**.</span></span> <span data-ttu-id="383a7-118">Debería ver que el modelo tiene una entidad: **Supplier**.</span><span class="sxs-lookup"><span data-stu-id="383a7-118">You should see that the model has one entity: **Supplier**.</span></span>  
  
     <span data-ttu-id="383a7-119">![Excel - Ventana Explorador de datos maestros](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel - Ventana Explorador de datos maestros")</span><span class="sxs-lookup"><span data-stu-id="383a7-119">![Excel - Master Data Explorer Window](../../2014/tutorials/media/et-combinematchandpublishnewsod-02.jpg "Excel - Master Data Explorer Window")</span></span>  
  
6.  <span data-ttu-id="383a7-120">Haga doble clic en **proveedor** en la lista de entidades para cargar los miembros de la entidad en la hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="383a7-120">Double-click **Supplier** in the entity list to load the entity members into the Excel worksheet.</span></span>  
  
7.  <span data-ttu-id="383a7-121">Haga clic en **Sheet2** en la parte inferior para cambiar a la pestaña **hoja2** . Si no ve **Sheet2**, agregue una nueva hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="383a7-121">Click **Sheet2** at the bottom to switch to the **Sheet2** tab. If you do not see **Sheet2**, add a new worksheet.</span></span>  
  
8.  <span data-ttu-id="383a7-122">Abra **Suppliers.xls** archivo (el archivo de entrada original incluido en los archivos del tutorial) y copie todas (tres) filas de la hoja de cálculo **CombineAndCleanse** a **Sheet2**.</span><span class="sxs-lookup"><span data-stu-id="383a7-122">Open **Suppliers.xls** file (the original input file that is included in the tutorial files) and copy all (three) rows from the **CombineAndCleanse** worksheet to **Sheet2**.</span></span>  
  
9. <span data-ttu-id="383a7-123">Vuelva a la hoja de **proveedores** en el **libro 1: Microsoft Excel** (no la **lista de proveedores limpiados y coincidentes** ) que está conectado a **MDS**.</span><span class="sxs-lookup"><span data-stu-id="383a7-123">Switch back to the **Supplier** sheet in the **Book 1 - Microsoft Excel** (not the **Cleansed and Matched Supplier List** Excel) that is connected to **MDS**.</span></span>  
  
10. <span data-ttu-id="383a7-124">Haga clic en **Datos maestros** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="383a7-124">Click **Master Data** on the menu bar.</span></span>  
  
11. <span data-ttu-id="383a7-125">Haga clic en **combinar datos** en la cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="383a7-125">Click **Combine Data** on the ribbon.</span></span> <span data-ttu-id="383a7-126">Verá el cuadro de diálogo **combinar datos** .</span><span class="sxs-lookup"><span data-stu-id="383a7-126">You will see the **Combine Data** dialog box.</span></span>  
  
12. <span data-ttu-id="383a7-127">En el cuadro de diálogo **combinar datos** , haga clic en el botón situado junto al cuadro de texto **rango que se va a combinar con los datos MDS** , tal como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="383a7-127">In the **Combine Data** dialog box, click the button next to **Range to combine with MDS data** text box as shown in the following image.</span></span>  
  
     <span data-ttu-id="383a7-128">![Excel - Cuadro de diálogo Combinar datos](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel - Cuadro de diálogo Combinar datos")</span><span class="sxs-lookup"><span data-stu-id="383a7-128">![Excel - Combine Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-03.jpg "Excel - Combine Data Dialog Box")</span></span>  
  
13. <span data-ttu-id="383a7-129">Ahora debe ver el cuadro de diálogo reducido.</span><span class="sxs-lookup"><span data-stu-id="383a7-129">You should see the shrunken dialog box now.</span></span> <span data-ttu-id="383a7-130">Ahora, haga clic en **Sheet2** para cambiar a la pestaña **hoja2** que tiene los nuevos datos de proveedor con 4 filas (incluida una fila de encabezado).</span><span class="sxs-lookup"><span data-stu-id="383a7-130">Now, click **Sheet2** to switch to the **Sheet2** tab that has the new supplier data with 4 rows (including one header row).</span></span>  
  
14. <span data-ttu-id="383a7-131">En la **hoja2**, seleccione **todas las filas, incluida la fila de encabezado** (aunque parezca que ya están seleccionadas).</span><span class="sxs-lookup"><span data-stu-id="383a7-131">In the **Sheet2**, select **all rows including the header row** (even if they seem to be already selected).</span></span> <span data-ttu-id="383a7-132">Debería ver que el **intervalo que se va a combinar con los datos de MDS** se actualiza automáticamente.</span><span class="sxs-lookup"><span data-stu-id="383a7-132">You should see the **Range to combine with MDS data** is automatically updated.</span></span>  
  
     <span data-ttu-id="383a7-133">![Excel - Cuadro de diálogo Combinar datos - Minimizado](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel - Cuadro de diálogo Combinar datos - Minimizado")</span><span class="sxs-lookup"><span data-stu-id="383a7-133">![Excel - Combine Data Dialog Box - Minimized](../../2014/tutorials/media/et-combinematchandpublishnewsod-04.jpg "Excel - Combine Data Dialog Box - Minimized")</span></span>  
  
15. <span data-ttu-id="383a7-134">Vuelva a la pestaña **proveedores** sin cerrar el cuadro de diálogo **combinar datos** .</span><span class="sxs-lookup"><span data-stu-id="383a7-134">Switch back to the **Suppliers** tab without closing the **Combine Data** dialog box.</span></span>  
  
16. <span data-ttu-id="383a7-135">Haga clic en el **botón** situado junto al **cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="383a7-135">Click the **button** next to the **text box**.</span></span> <span data-ttu-id="383a7-136">Ahora debe ver que el cuadro de diálogo se ha expandido.</span><span class="sxs-lookup"><span data-stu-id="383a7-136">You should see that the dialog box is expanded now.</span></span> <span data-ttu-id="383a7-137">Debería ver que todas las asignaciones entre las columnas de la **entidad** MDS del **proveedor** a las columnas de **Excel** se rellenan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="383a7-137">You should see all the mappings between columns of the **Supplier** MDS **entity** to **Excel** columns are automatically populated.</span></span>  
  
     <span data-ttu-id="383a7-138">![Excel - Cuadro de diálogo Combinar datos cumplimentado con datos](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel - Cuadro de diálogo Combinar datos cumplimentado con datos")</span><span class="sxs-lookup"><span data-stu-id="383a7-138">![Excel - Combine Data Dialog Box Filled with Data](../../2014/tutorials/media/et-combinematchandpublishnewsod-05.jpg "Excel - Combine Data Dialog Box Filled with Data")</span></span>  
  
17. <span data-ttu-id="383a7-139">Asegúrese de que la columna de entidad **código** esté asignada a la columna **IdProveedor** de la hoja de cálculo y la columna de la entidad **código postal** esté asignada a la columna **código postal** de la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="383a7-139">Ensure that **Code** entity column is mapped to the **SupplierID** column in the worksheet and **Zip Code** entity column is mapped to the **Zip Code** column in the worksheet.</span></span>  
  
18. <span data-ttu-id="383a7-140">En el cuadro de diálogo **combinar datos** , haga clic en **combinar**.</span><span class="sxs-lookup"><span data-stu-id="383a7-140">On the **Combine Data** dialog box, click **Combine**.</span></span>  
  
19. <span data-ttu-id="383a7-141">Confirme que se han agregado tres filas de datos al final de la hoja de cálculo y que están codificadas por colores.</span><span class="sxs-lookup"><span data-stu-id="383a7-141">Confirm that three data rows are added to the bottom of the worksheet and they should be color coded.</span></span>  
  
     <span data-ttu-id="383a7-142">![Excel - Nuevos elementos después de la combinación](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel - Nuevos elementos después de la combinación")</span><span class="sxs-lookup"><span data-stu-id="383a7-142">![Excel - New Elements after Combining](../../2014/tutorials/media/et-combinematchandpublishnewsod-06.jpg "Excel - New Elements after Combining")</span></span>  
  
20. <span data-ttu-id="383a7-143">Haga clic en **datos matemáticos** en la cinta de opciones para identificar duplicados.</span><span class="sxs-lookup"><span data-stu-id="383a7-143">Click **Math Data** on the ribbon to identify duplicates.</span></span> <span data-ttu-id="383a7-144">Esta característica emplea la funcionalidad de coincidencia de DQS.</span><span class="sxs-lookup"><span data-stu-id="383a7-144">This feature uses the matching functionality of DQS.</span></span>  
  
21. <span data-ttu-id="383a7-145">En el cuadro de diálogo **coincidencia de datos** , seleccione **proveedores** para la base de **conocimiento de DQS**.</span><span class="sxs-lookup"><span data-stu-id="383a7-145">In the **Match Data** dialog box, select **Suppliers** for **DQS Knowledge Base**.</span></span>  
  
     <span data-ttu-id="383a7-146">![Excel - Cuadro de diálogo Coincidir datos](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel - Cuadro de diálogo Coincidir datos")</span><span class="sxs-lookup"><span data-stu-id="383a7-146">![Excel - Match Data Dialog Box](../../2014/tutorials/media/et-combinematchandpublishnewsod-07.jpg "Excel - Match Data Dialog Box")</span></span>  
  
22. <span data-ttu-id="383a7-147">Asigne columnas de la hoja de cálculo a dominios como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="383a7-147">Map worksheet columns to domains as shown in the following table.</span></span>  
  
    |<span data-ttu-id="383a7-148">Columna de la hoja de cálculo</span><span class="sxs-lookup"><span data-stu-id="383a7-148">Worksheet Column</span></span>|<span data-ttu-id="383a7-149">Dominio</span><span class="sxs-lookup"><span data-stu-id="383a7-149">Domain</span></span>|  
    |----------------------|------------|  
    |<span data-ttu-id="383a7-150">Code (cargó Id. de proveedor como código de la entidad Proveedor en MDS)</span><span class="sxs-lookup"><span data-stu-id="383a7-150">Code (you uploaded Supplier ID as the Code for the Supplier entity in MDS)</span></span>|<span data-ttu-id="383a7-151">Id. de proveedor</span><span class="sxs-lookup"><span data-stu-id="383a7-151">Supplier ID</span></span>|  
    |<span data-ttu-id="383a7-152">Name (cargó Nombre de proveedor como nombre de la entidad Proveedor en MDS)</span><span class="sxs-lookup"><span data-stu-id="383a7-152">Name (you uploaded Supplier Name as the Name for the Supplier entity to MDS)</span></span>|<span data-ttu-id="383a7-153">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="383a7-153">Supplier Name</span></span>|  
    |<span data-ttu-id="383a7-154">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="383a7-154">ContactEmailAddress</span></span>|<span data-ttu-id="383a7-155">Correo electrónico de contacto</span><span class="sxs-lookup"><span data-stu-id="383a7-155">ContactEmail</span></span>|  
  
23. <span data-ttu-id="383a7-156">Seleccione **requisito previo** para la asignación de columna de **código** .</span><span class="sxs-lookup"><span data-stu-id="383a7-156">Select **Prerequisite** for the **Code** column mapping.</span></span>  
  
24. <span data-ttu-id="383a7-157">Escriba **70%** como el **peso** del **nombre del proveedor** y el **30%** como el **peso** del **correo electrónico de contacto** , tal como se muestra en la imagen.</span><span class="sxs-lookup"><span data-stu-id="383a7-157">Enter **70%** as the **weight** for **Supplier Name** and **30%** as the **weight** for **Contact Email** as shown in the image.</span></span>  
  
25. <span data-ttu-id="383a7-158">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="383a7-158">Click **OK**.</span></span>  
  
26. <span data-ttu-id="383a7-159">El proceso de coincidencia debe identificar un duplicado para el proveedor con **código: S1**.</span><span class="sxs-lookup"><span data-stu-id="383a7-159">The matching process should identify one duplicate for the supplier with **Code: S1**.</span></span>  
  
     <span data-ttu-id="383a7-160">![Excel - Resultados de coincidencias](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel - Resultados de coincidencias")</span><span class="sxs-lookup"><span data-stu-id="383a7-160">![Excel - Matching Results](../../2014/tutorials/media/et-combinematchandpublishnewsod-08.jpg "Excel - Matching Results")</span></span>  
  
27. <span data-ttu-id="383a7-161">Seleccione la **fila duplicada (naranja)**, haga clic con el botón secundario y haga clic en **eliminar** para eliminar la fila.</span><span class="sxs-lookup"><span data-stu-id="383a7-161">Select the **duplicate row (orange)**, right-click, and click **Delete** to delete the row.</span></span>  
  
28. <span data-ttu-id="383a7-162">Elimine la columna de **CLUSTER_ID** porque ya no la necesita.</span><span class="sxs-lookup"><span data-stu-id="383a7-162">Delete the **CLUSTER_ID** column since you don't need it anymore.</span></span>  
  
29. <span data-ttu-id="383a7-163">Haga clic en **publicar** para publicar los otros dos registros nuevos con los **códigos S66** y **S57** en MDS.</span><span class="sxs-lookup"><span data-stu-id="383a7-163">Click **Publish** to publish the other two new records with **Codes S66** and **S57** to MDS.</span></span>  
  
30. <span data-ttu-id="383a7-164">En el cuadro de diálogo **publicar y anotar** , agregue una **anotación**y haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="383a7-164">In the **Publish and Annotate** dialog box, add an **annotation**, and click **Publish**.</span></span>  
  
31. <span data-ttu-id="383a7-165">Cambie a la **aplicación Web de Master Data Manager**.</span><span class="sxs-lookup"><span data-stu-id="383a7-165">Switch to the **Master Data Manager Web application**.</span></span>  
  
32. <span data-ttu-id="383a7-166">En la Página principal, asegúrese de que se ha seleccionado **proveedores** para el **modelo**y haga clic en **Explorador**.</span><span class="sxs-lookup"><span data-stu-id="383a7-166">On the home page, ensure that **Suppliers** is selected for the **Model**, and click **Explorer**.</span></span> <span data-ttu-id="383a7-167">Si ya tiene el **Explorador** abierto, actualice el explorador de Internet.</span><span class="sxs-lookup"><span data-stu-id="383a7-167">If you already have the **Explorer** open, refresh the internet browser.</span></span>  
  
33. <span data-ttu-id="383a7-168">**Ordene** la lista por **código** y busque los registros con **S57** y **S66** como códigos.</span><span class="sxs-lookup"><span data-stu-id="383a7-168">**Sort** the list by **Code** and look for records with **S57** and **S66** as codes.</span></span> <span data-ttu-id="383a7-169">También puede usar el botón **filtro** de la barra de herramientas para buscar un registro específico en la lista.</span><span class="sxs-lookup"><span data-stu-id="383a7-169">You can also use the **Filter** button on the toolbar to search for a specific record in the list.</span></span>  
  
34. <span data-ttu-id="383a7-170">Ahora, cierre **libro1: ventana de Microsoft Excel** sin guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="383a7-170">Now, close **Book1 - Microsoft Excel** window without saving the file.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="383a7-171">siguiente paso</span><span class="sxs-lookup"><span data-stu-id="383a7-171">Next Step</span></span>  
 [<span data-ttu-id="383a7-172">Tarea 5: Creación de un atributo basado en dominio desde Excel</span><span class="sxs-lookup"><span data-stu-id="383a7-172">Task 5: Creating a Domain-Based Attribute from Excel</span></span>](../../2014/tutorials/task-5-creating-a-domain-based-attribute-from-excel.md)  
  
  
