---
title: 'Tutorial: usar el origen OData [SSIS] | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2c64cf8b-5edb-48df-8ffe-697096258f71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a13b04494ed00251774b490b1cc929769a869acb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676071"
---
# <a name="tutorial-using-the-odata-source-ssis"></a><span data-ttu-id="98b4c-102">Tutorial: Usar el origen OData [SSIS]</span><span class="sxs-lookup"><span data-stu-id="98b4c-102">Tutorial: Using the OData Source [SSIS]</span></span>
  <span data-ttu-id="98b4c-103">En este tutorial se describe el proceso para extraer la colección **Employees** del servicio OData del ejemplo **Northwind** (http://services.odata.org/V3/Northwind/Northwind.svc/) ) y, después, cargarlo en un archivo plano.</span><span class="sxs-lookup"><span data-stu-id="98b4c-103">This tutorial walks you through the process to extract the **Employees** collection from the sample **Northwind** OData service (http://services.odata.org/V3/Northwind/Northwind.svc/), and then load it into a flat file.</span></span>  
  
## <a name="1-create-an-integration-services-project"></a><span data-ttu-id="98b4c-104">1. Crear un proyecto de Integration Services</span><span class="sxs-lookup"><span data-stu-id="98b4c-104">1. Create an Integration Services Project</span></span>  
  
1.  <span data-ttu-id="98b4c-105">Inicie **SQL Server Data Tools** o [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98b4c-105">Launch **SQL Server Data Tools** or [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
2.  <span data-ttu-id="98b4c-106">Haga clic en **Archivo**, seleccione **Nuevo** y, luego, haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-106">Click **File**, point to **New**, and click **Project**.</span></span>  
  
3.  <span data-ttu-id="98b4c-107">En el cuadro de diálogo **Nuevo proyecto** , expanda **Instalado**, expanda **Plantillas**, expanda **Business Intelligence**y haga clic en **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-107">In the **New Project** dialog box, expand **Installed**, expand **Templates**, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
4.  <span data-ttu-id="98b4c-108">Seleccione **Proyecto de Integration Services** como tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="98b4c-108">Select **Integration Services Project** for the type of project.</span></span>  
  
5.  <span data-ttu-id="98b4c-109">Escriba un **nombre** y seleccione una **ubicación** para el proyecto; a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-109">Enter a **name** and select a **location** for the project, and click **OK**.</span></span>  
  
## <a name="2-add-and-configure-odata-source-to-the-ssis-package"></a><span data-ttu-id="98b4c-110">2. Agregar y configurar el origen OData al paquete SSIS</span><span class="sxs-lookup"><span data-stu-id="98b4c-110">2. Add and Configure OData Source to the SSIS Package</span></span>  
  
1.  <span data-ttu-id="98b4c-111">Arrastre y coloque una **Tarea Flujo de datos** desde el **Cuadro de herramientas de SSIS** hasta la superficie de diseño del flujo de control del paquete SSIS.</span><span class="sxs-lookup"><span data-stu-id="98b4c-111">Drag-drop a **Data Flow Task** from the **SSIS Toolbox** on to the control flow design surface of your SSIS package.</span></span>  
  
2.  <span data-ttu-id="98b4c-112">Haga clic en la pestaña **Flujo de datos** o haga doble clic en la **Tarea Flujo de datos** recién agregada para iniciar la **superficie de diseño Flujo de datos**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-112">Click the **Data Flow** tab, or double click on the newly added **Data Flow Task** to launch the **Data Flow design surface**.</span></span>  
  
3.  <span data-ttu-id="98b4c-113">Arrastre y coloque **Origen OData** desde el grupo **Común** del **Cuadro de herramientas de SSIS**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-113">Drag-drop **OData Source** from the **Common** group in the **SSIS Toolbox**.</span></span> <span data-ttu-id="98b4c-114">La primera vez que se instala el **Origen OData** , aparecerá en el grupo **Común** del **Cuadro de herramientas de SSIS**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-114">When the **OData Source** is first installed, it will appear under the **Common** group in the **SSIS Toolbox**.</span></span>  
  
4.  <span data-ttu-id="98b4c-115">Haga doble clic en el componente **Origen OData** para iniciar el cuadro de diálogo **Editor de origen OData** .</span><span class="sxs-lookup"><span data-stu-id="98b4c-115">Double click the **OData Source** component to launch the **OData Source Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="98b4c-116">Haga clic en **Nuevo…** para agregar un nuevo Administrador de conexiones OData.</span><span class="sxs-lookup"><span data-stu-id="98b4c-116">Click **New...** to add a new OData Connection Manager.</span></span>  
  
6.  <span data-ttu-id="98b4c-117">Escriba la dirección URL del servicio OData en **Ubicación de documento de servicio**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-117">Enter the OData service URL for **Service document location**.</span></span> <span data-ttu-id="98b4c-118">Puede ser la dirección URL del documento de servicio, o de una fuente o una entidad específica.</span><span class="sxs-lookup"><span data-stu-id="98b4c-118">This can be the URL to the service document, or to a specific feed or entity.</span></span> <span data-ttu-id="98b4c-119">Para este tutorial, escriba [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/) .</span><span class="sxs-lookup"><span data-stu-id="98b4c-119">For the purpose of this tutorial, type [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/).</span></span>  
  
7.  <span data-ttu-id="98b4c-120">Confirme que se ha seleccionado **Autenticación de Windows** como la **autenticación** que se usará para tener acceso al servicio OData.</span><span class="sxs-lookup"><span data-stu-id="98b4c-120">Confirm that **Windows Authentication** is selected for the **authentication** to use to access the OData Service.</span></span> <span data-ttu-id="98b4c-121">**Autenticación de Windows** está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98b4c-121">**Windows Authentication** is selected by default.</span></span> <span data-ttu-id="98b4c-122">Para usar la autenticación básica, seleccione **Usar este nombre de usuario y esta contraseña**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-122">To use basic authentication, select **Use this user name and password**.</span></span>  
  
8.  <span data-ttu-id="98b4c-123">Haga clic en **Probar conexión** y, a continuación, haga clic en **Aceptar** para crear una instancia del Administrador de conexiones OData.</span><span class="sxs-lookup"><span data-stu-id="98b4c-123">Click **Test Connection** to the connection, and click **OK** to create an instance of OData Connection Manager.</span></span>  
  
9. <span data-ttu-id="98b4c-124">En el cuadro de diálogo **Editor de origen OData** , confirme que se ha seleccionado **Colección** para la opción **Usar colección en la ruta de acceso a recursos** .</span><span class="sxs-lookup"><span data-stu-id="98b4c-124">In the **OData Source Editor** Dialog Box, confirm that **Collection** is selected for **Use collection on resource path** option.</span></span>  
  
10. <span data-ttu-id="98b4c-125">En la lista desplegable **Colección** , seleccione **Employees**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-125">From the **Collection** drop down list, select **Employees**.</span></span>  
  
11. <span data-ttu-id="98b4c-126">Especifique cualquier otra opción o filtro de consulta adicional de OData en **Opciones de consulta**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-126">Enter any additional OData query options or filters for **Query Options**.</span></span> <span data-ttu-id="98b4c-127">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="98b4c-127">Ex.</span></span> <span data-ttu-id="98b4c-128">$orderby=CompanyName&$top=100.</span><span class="sxs-lookup"><span data-stu-id="98b4c-128">$orderby=CompanyName&$top=100.</span></span> <span data-ttu-id="98b4c-129">Para este tutorial, escriba **$top=5**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-129">For the purpose of this tutorial, enter **$top=5**.</span></span>  
  
12. <span data-ttu-id="98b4c-130">Haga clic en **Vista previa** para obtener una vista previa de los datos.</span><span class="sxs-lookup"><span data-stu-id="98b4c-130">Click **Preview** to preview the data.</span></span>  
  
13. <span data-ttu-id="98b4c-131">Haga clic en **Columnas** en el panel de navegación de la izquierda para cambiar a la página **Columnas** .</span><span class="sxs-lookup"><span data-stu-id="98b4c-131">Click **Columns** in the left navigation pane to switch to the **Columns** page.</span></span>  
  
14. <span data-ttu-id="98b4c-132">Seleccione **EmployeeID**, **FirstName**y **LastName** en **Columnas externas disponibles** activando las casillas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="98b4c-132">Select **EmployeeID**, **FirstName**, and **LastName** from **Available External Columns** by checking the check boxes.</span></span>  
  
15. <span data-ttu-id="98b4c-133">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Editor de origen OData** .</span><span class="sxs-lookup"><span data-stu-id="98b4c-133">Click **OK** to close the **OData Source Editor** dialog box.</span></span>  
  
## <a name="3-add-flat-file-destination-and-test-the-solution"></a><span data-ttu-id="98b4c-134">3. Agregar el destino del archivo plano y probar la solución</span><span class="sxs-lookup"><span data-stu-id="98b4c-134">3. Add Flat File Destination and Test the Solution</span></span>  
  
1.  <span data-ttu-id="98b4c-135">Después, arrastre y coloque un **Destino de archivo plano** desde el **Cuadro de herramientas de SSIS** hasta la superficie de diseño Flujo de datos, debajo el componente **Origen OData** .</span><span class="sxs-lookup"><span data-stu-id="98b4c-135">Now, drag-drop a **Flat File Destination** from **SSIS Toolbox** to the Data Flow design surface below the **OData Source** component.</span></span>  
  
2.  <span data-ttu-id="98b4c-136">Conecte el componente **Origen OData** con el componente **Destino de archivo plano** usando la flecha azul.</span><span class="sxs-lookup"><span data-stu-id="98b4c-136">Connect **OData Source** component with the **Flat File Destination** component using blue arrow.</span></span>  
  
3.  <span data-ttu-id="98b4c-137">Haga doble clic en **Destino de archivo plano**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-137">Double-click on **Flat File Destination**.</span></span> <span data-ttu-id="98b4c-138">Debe ver el cuadro de diálogo **Editor de destino de archivos planos** .</span><span class="sxs-lookup"><span data-stu-id="98b4c-138">You should see the **Flat File Destination Editor** dialog box.</span></span>  
  
4.  <span data-ttu-id="98b4c-139">En el cuadro de diálogo **Editor de destino de archivos planos** , haga clic en **Nuevo** para crear un nuevo administrador de conexiones de archivos planos.</span><span class="sxs-lookup"><span data-stu-id="98b4c-139">In the **Flat File Destination Editor** dialog box, click **New** to create a new flat file connection manager.</span></span>  
  
5.  <span data-ttu-id="98b4c-140">En el cuadro de diálogo **Formato del archivo plano** , seleccione **Delimitado**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-140">In the **Flat File Format** dialog box, select **Delimited**.</span></span> <span data-ttu-id="98b4c-141">Debe ver el cuadro de diálogo **Editor del administrador de conexiones de archivos planos** .</span><span class="sxs-lookup"><span data-stu-id="98b4c-141">You should see the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
6.  <span data-ttu-id="98b4c-142">En el cuadro de diálogo **Editor del administrador de conexiones de archivos planos** , en **Nombre de archivo**, escriba **c:\Employees.txt**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-142">In the **Flat File Connection Manager Editor** dialog box, for the **File name**, enter **c:\Employees.txt**.</span></span>  
  
7.  <span data-ttu-id="98b4c-143">En el panel de navegación de la izquierda, haga clic en **Columnas**.</span><span class="sxs-lookup"><span data-stu-id="98b4c-143">In the left navigation pane, click **Columns**.</span></span> <span data-ttu-id="98b4c-144">Puede obtener una vista previa de los datos de esta página.</span><span class="sxs-lookup"><span data-stu-id="98b4c-144">You can preview the data on this page.</span></span>  
  
8.  <span data-ttu-id="98b4c-145">Haga clic en Aceptar para cerrar el cuadro de diálogo **Editor del administrador de conexiones de archivos planos** .</span><span class="sxs-lookup"><span data-stu-id="98b4c-145">Click OK to close the **Flat File Connection Manager** Editor dialog box.</span></span>  
  
9. <span data-ttu-id="98b4c-146">En el cuadro de diálogo **Editor de destino de archivos planos** , haga clic en **Asignaciones** en el panel de navegación de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="98b4c-146">In the **Flat File Destination Editor** dialog box, click **Mappings** in the left navigation pane.</span></span> <span data-ttu-id="98b4c-147">Revise las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="98b4c-147">Review the mappings.</span></span>  
  
10. <span data-ttu-id="98b4c-148">Haga clic en Aceptar para cerrar el cuadro de diálogo **Editor de destino de archivos planos** .</span><span class="sxs-lookup"><span data-stu-id="98b4c-148">Click OK to close the **Flat File Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="98b4c-149">Genere y ejecute el paquete SSIS.</span><span class="sxs-lookup"><span data-stu-id="98b4c-149">Compile and execute the SSIS package.</span></span> <span data-ttu-id="98b4c-150">Compruebe que el archivo de salida creado contiene el ID, First Name y Last Name de 5 empleados de la fuente OData.</span><span class="sxs-lookup"><span data-stu-id="98b4c-150">Verify that the output file is created with ID, First Name, and Last Name for 5 employees from the OData feed.</span></span>  
  
  
