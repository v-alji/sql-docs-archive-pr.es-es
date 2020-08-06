---
title: Definir un origen de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 5a3e83c9-8788-431e-85b0-a68c79377ff3
author: minewiskan
ms.author: owend
ms.openlocfilehash: fdf00b47360341e2b9a99654482d65be83b86503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662322"
---
# <a name="defining-a-data-source"></a><span data-ttu-id="28f4f-102">Definir un origen de datos</span><span class="sxs-lookup"><span data-stu-id="28f4f-102">Defining a Data Source</span></span>
  <span data-ttu-id="28f4f-103">Tras crear un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , generalmente se empieza a trabajar con el mismo definiendo uno o más orígenes de datos que el proyecto usará.</span><span class="sxs-lookup"><span data-stu-id="28f4f-103">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you generally start working with the project by defining one or more data sources that the project will use.</span></span> <span data-ttu-id="28f4f-104">Al definir un origen de datos, se define la información de cadena de conexión que se utilizará para establecer la conexión con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="28f4f-104">When you define a data source, you are defining the connection string information that will be used to connect to the data source.</span></span> <span data-ttu-id="28f4f-105">Para más información, vea [Crear un origen de datos &#40;SSAS multidimensional&#41;](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="28f4f-105">For more information, see [Create a Data Source &#40;SSAS Multidimensional&#41;](multidimensional-models/create-a-data-source-ssas-multidimensional.md).</span></span>  
  
 <span data-ttu-id="28f4f-106">En la tarea siguiente, definirá la base de datos de ejemplo AdventureWorksDWSQLServer2012 como origen de datos para el proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="28f4f-106">In the following task, you define the AdventureWorksDWSQLServer2012 sample database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="28f4f-107">En el caso de este tutorial, esta base de datos se encuentra en el equipo local; no obstante, las bases de datos de origen generalmente se encuentran hospedadas en uno o más equipos remotos.</span><span class="sxs-lookup"><span data-stu-id="28f4f-107">While this database is located on your local computer for the purposes of this tutorial, source databases are frequently hosted on one or more remote computers.</span></span>  
  
### <a name="to-define-a-new-data-source"></a><span data-ttu-id="28f4f-108">Para definir un origen de datos nuevo</span><span class="sxs-lookup"><span data-stu-id="28f4f-108">To define a new data source</span></span>  
  
1.  <span data-ttu-id="28f4f-109">En el Explorador de soluciones (a la derecha de la ventana de Microsoft Visual Studio), haga clic con el botón derecho en **Orígenes de datos**y, después, haga clic en **Nuevo origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="28f4f-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Sources**, and then click **New Data Source**.</span></span>  
  
2.  <span data-ttu-id="28f4f-110">En la página de **inicio** del **Asistente para orígenes de datos**, haga clic en **Siguiente** para abrir la página **Seleccionar cómo definir la conexión** .</span><span class="sxs-lookup"><span data-stu-id="28f4f-110">On the **Welcome to the Data Source Wizard** page of the **Data Source Wizard**, click **Next** to open the **Select how to define the connection** page.</span></span>  
  
3.  <span data-ttu-id="28f4f-111">En la página **Seleccionar cómo definir la conexión** , puede definir un origen de datos basado en una conexión nueva, en una conexión existente o en un objeto de origen de datos definido con anterioridad.</span><span class="sxs-lookup"><span data-stu-id="28f4f-111">On the **Select how to define the connection** page, you can define a data source based on a new connection, based on an existing connection, or based on a previously defined data source object.</span></span> <span data-ttu-id="28f4f-112">En este tutorial, va a definir un origen de datos basado en una conexión nueva.</span><span class="sxs-lookup"><span data-stu-id="28f4f-112">In this tutorial, you define a data source based on a new connection.</span></span> <span data-ttu-id="28f4f-113">Compruebe que la opción **Crear un origen de datos basado en una conexión nueva o existente** está seleccionada y después haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="28f4f-113">Verify that **Create a data source based on an existing or new connection** is selected, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="28f4f-114">En el cuadro de diálogo **Administrador de conexiones** se definen las propiedades de conexión para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="28f4f-114">In the **Connection Manager** dialog box, you define connection properties for the data source.</span></span> <span data-ttu-id="28f4f-115">En el cuadro de lista **Proveedor** , compruebe que está seleccionada la opción **Native OLE DB\SQL Server Native Client 11.0** .</span><span class="sxs-lookup"><span data-stu-id="28f4f-115">In the **Provider** list box, verify that **Native OLE DB\SQL Server Native Client 11.0** is selected.</span></span>  
  
     [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="28f4f-116">también admite otros proveedores, que se muestran en la lista **Proveedor** .</span><span class="sxs-lookup"><span data-stu-id="28f4f-116">also supports other providers, which are displayed in the **Provider** list.</span></span>  
  
5.  <span data-ttu-id="28f4f-117">En el cuadro de texto **nombre del servidor** , escriba `localhost` .</span><span class="sxs-lookup"><span data-stu-id="28f4f-117">In the **Server name** text box, type `localhost`.</span></span>  
  
     <span data-ttu-id="28f4f-118">Para conectarse a una instancia con nombre en el equipo local, escriba **localhost \\<nombre \> de instancia**.</span><span class="sxs-lookup"><span data-stu-id="28f4f-118">To connect to a named instance on your local computer, type **localhost\\<instance name\>**.</span></span> <span data-ttu-id="28f4f-119">Para conectarse al equipo especificado en lugar de al equipo local, escriba el nombre del equipo o la dirección IP.</span><span class="sxs-lookup"><span data-stu-id="28f4f-119">To connect to the specific computer instead of the local computer, type the computer name or IP address.</span></span>  
  
6.  <span data-ttu-id="28f4f-120">Compruebe que la opción **Usar autenticación de Windows** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="28f4f-120">Verify that **Use Windows Authentication** is selected.</span></span> <span data-ttu-id="28f4f-121">En la lista **Seleccione o escriba un nombre de base de datos** , seleccione **AdventureWorksDW2012**.</span><span class="sxs-lookup"><span data-stu-id="28f4f-121">In the **Select or enter a database name** list, select **AdventureWorksDW2012**.</span></span>  
  
7.  <span data-ttu-id="28f4f-122">Haga clic en **Probar conexión** para probar la conexión a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="28f4f-122">Click **Test Connection** to test the connection to the database.</span></span>  
  
8.  <span data-ttu-id="28f4f-123">Haga clic en **Aceptar** y luego en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="28f4f-123">Click **OK**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="28f4f-124">En la página **Información de suplantación** del asistente, debe definir las credenciales de seguridad que [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] debe usar para conectarse al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="28f4f-124">On the **Impersonation Information** page of the wizard, you define the security credentials for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] to use to connect to the data source.</span></span> <span data-ttu-id="28f4f-125">La suplantación afecta a la cuenta de Windows usada para conectarse al origen de datos cuando está seleccionada la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="28f4f-125">Impersonation affects the Windows account used to connect to the data source when Windows Authentication is selected.</span></span> [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="28f4f-126">no admite la suplantación para el procesamiento de objetos OLAP.</span><span class="sxs-lookup"><span data-stu-id="28f4f-126">does not support impersonation for processing OLAP objects.</span></span> <span data-ttu-id="28f4f-127">Seleccione **Usar cuenta de servicio**y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="28f4f-127">Select **Use the service account**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="28f4f-128">En la página **Finalización del asistente** , acepte el nombre predeterminado **Adventure Works DW 2012**y, después, haga clic en **Finalizar** para crear el nuevo origen de datos.</span><span class="sxs-lookup"><span data-stu-id="28f4f-128">On the **Completing the Wizard** page, accept the default name, **Adventure Works DW 2012**, and then click **Finish** to create the new data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28f4f-129">Para modificar las propiedades del origen de datos una vez creado, haga doble clic en el origen de datos en la carpeta **Orígenes de datos** para mostrar las propiedades del origen de datos en el **Diseñador de origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="28f4f-129">To modify the properties of the data source after it has been created, double-click the data source in the **Data Sources** folder to display the data source properties in **Data Source Designer**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="28f4f-130">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="28f4f-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="28f4f-131">Definir una vista del origen de datos</span><span class="sxs-lookup"><span data-stu-id="28f4f-131">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
  
## <a name="see-also"></a><span data-ttu-id="28f4f-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="28f4f-132">See Also</span></span>  
 [<span data-ttu-id="28f4f-133">Crear un origen de datos &#40;SSAS multidimensional&#41;</span><span class="sxs-lookup"><span data-stu-id="28f4f-133">Create a Data Source &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/create-a-data-source-ssas-multidimensional.md)  
  
  
