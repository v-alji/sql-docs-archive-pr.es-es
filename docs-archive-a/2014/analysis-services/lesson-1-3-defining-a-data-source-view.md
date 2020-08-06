---
title: Definir una vista del origen de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: af00938a-5a06-4fae-b2fc-f3fb0ca3cea5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d59c5fbe5fd4a07596745447567a72499ddabd4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662317"
---
# <a name="defining-a-data-source-view"></a><span data-ttu-id="93db2-102">Definir una vista del origen de datos</span><span class="sxs-lookup"><span data-stu-id="93db2-102">Defining a Data Source View</span></span>
  <span data-ttu-id="93db2-103">Tras definir los orígenes de datos que utilizará en un proyecto de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , el paso siguiente generalmente consiste en definir una vista del origen de datos para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="93db2-103">After you define the data sources that you will use in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, the next step is generally to define a data source view for the project.</span></span> <span data-ttu-id="93db2-104">Una vista del origen de datos es una sola vista unificada de metadatos de las tablas y vistas especificadas que el origen de datos define en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="93db2-104">A data source view is a single, unified view of the metadata from the specified tables and views that the data source defines in the project.</span></span> <span data-ttu-id="93db2-105">Almacenar metadatos en la vista del origen de datos permite trabajar con los metadatos durante el proceso de desarrollo sin ninguna conexión abierta con ningún origen de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="93db2-105">Storing the metadata in the data source view enables you to work with the metadata during development without an open connection to any underlying data source.</span></span> <span data-ttu-id="93db2-106">Para más información, vea [Vistas del origen de datos en modelos multidimensionales](multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="93db2-106">For more information, see [Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
 <span data-ttu-id="93db2-107">En la tarea siguiente, definirá una vista del origen de datos que incluye cinco tablas del origen de datos **AdventureWorksDW2012** .</span><span class="sxs-lookup"><span data-stu-id="93db2-107">In the following task, you define a data source view that includes five tables from the **AdventureWorksDW2012** data source.</span></span>  
  
### <a name="to-define-a-new-data-source-view"></a><span data-ttu-id="93db2-108">Para definir una vista del origen de datos nueva</span><span class="sxs-lookup"><span data-stu-id="93db2-108">To define a new data source view</span></span>  
  
1.  <span data-ttu-id="93db2-109">En el Explorador de soluciones (a la derecha de la ventana de Microsoft Visual Studio), haga clic con el botón derecho en **Vistas del origen de datos**y, después, haga clic en **Nueva vista del origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="93db2-109">In Solution Explorer (on the right of the Microsoft Visual Studio window), right-click **Data Source Views**, and then click **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="93db2-110">En la página inicial del **Asistente para orígenes de datos** , haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93db2-110">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span> <span data-ttu-id="93db2-111">Aparece la página **Seleccionar un origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="93db2-111">The **Select a Data Source** page appears.</span></span>  
  
3.  <span data-ttu-id="93db2-112">En **Orígenes de datos relacionales**, el origen de datos **Adventure Works DW 2012** aparece seleccionado.</span><span class="sxs-lookup"><span data-stu-id="93db2-112">Under **Relational data sources**, the **Adventure Works DW 2012** data source is selected.</span></span> <span data-ttu-id="93db2-113">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="93db2-113">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93db2-114">Para crear una vista del origen de datos que se base en varios orígenes de datos, defina primero una vista del origen de datos que se base en un único origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93db2-114">To create a data source view that is based on multiple data sources, first define a data source view that is based on a single data source.</span></span> <span data-ttu-id="93db2-115">Este origen de datos luego se llama origen de datos principal.</span><span class="sxs-lookup"><span data-stu-id="93db2-115">This data source is then called the primary data source.</span></span> <span data-ttu-id="93db2-116">A continuación, puede agregar tablas y vistas a partir de un origen de datos secundario.</span><span class="sxs-lookup"><span data-stu-id="93db2-116">You can then add tables and views from a secondary data source.</span></span> <span data-ttu-id="93db2-117">Al diseñar dimensiones que contengan atributos basados en tablas relacionadas en varios orígenes de datos, puede que necesite definir un origen de datos de [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] como el origen de datos principal para usar sus capacidades del motor de consultas distribuidas.</span><span class="sxs-lookup"><span data-stu-id="93db2-117">When designing dimensions that contain attributes based on related tables in multiple data sources, you might need to define a [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] data source as the primary data source to use its distributed query engine capabilities.</span></span>  
  
4.  <span data-ttu-id="93db2-118">En la página **Seleccionar tablas y vistas** , seleccione las tablas y vistas de la lista de objetos disponibles del origen de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="93db2-118">On the **Select Tables and Views** page, select tables and views from the list of objects that are available from the selected data source.</span></span> <span data-ttu-id="93db2-119">Puede filtrar esta lista para ayudarle a seleccionar las tablas y vistas.</span><span class="sxs-lookup"><span data-stu-id="93db2-119">You can filter this list to help you select tables and views.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93db2-120">Haga clic en el botón Maximizar situado en la esquina superior derecha para que la ventana ocupe toda la pantalla.</span><span class="sxs-lookup"><span data-stu-id="93db2-120">Click the maximize button in the upper-right corner so that the window covers the full screen.</span></span> <span data-ttu-id="93db2-121">Así es más fácil ver la lista completa de objetos disponibles.</span><span class="sxs-lookup"><span data-stu-id="93db2-121">This makes it easier to see the complete list of available objects.</span></span>  
  
     <span data-ttu-id="93db2-122">En la lista **Objetos disponibles** , seleccione los siguientes objetos.</span><span class="sxs-lookup"><span data-stu-id="93db2-122">In the **Available objects** list, select the following objects.</span></span> <span data-ttu-id="93db2-123">Para seleccionar varias tablas, haga clic en cada una de ellas mientras mantiene presionada la tecla CTRL:</span><span class="sxs-lookup"><span data-stu-id="93db2-123">You can select multiple tables by clicking each while holding down the CTRL key:</span></span>  
  
    -   <span data-ttu-id="93db2-124">**DimCustomer (dbo)**</span><span class="sxs-lookup"><span data-stu-id="93db2-124">**DimCustomer (dbo)**</span></span>  
  
    -   <span data-ttu-id="93db2-125">**DimDate (dbo)**</span><span class="sxs-lookup"><span data-stu-id="93db2-125">**DimDate (dbo)**</span></span>  
  
    -   <span data-ttu-id="93db2-126">**DimGeography (dbo)**</span><span class="sxs-lookup"><span data-stu-id="93db2-126">**DimGeography (dbo)**</span></span>  
  
    -   <span data-ttu-id="93db2-127">**DimProduct (dbo)**</span><span class="sxs-lookup"><span data-stu-id="93db2-127">**DimProduct (dbo)**</span></span>  
  
    -   <span data-ttu-id="93db2-128">**FactInternetSales (dbo)**</span><span class="sxs-lookup"><span data-stu-id="93db2-128">**FactInternetSales (dbo)**</span></span>  
  
5.  <span data-ttu-id="93db2-129">Haga clic en **>** esta opción para agregar las tablas seleccionadas a la lista **objetos incluidos** .</span><span class="sxs-lookup"><span data-stu-id="93db2-129">Click **>** to add the selected tables to the **Included objects** list.</span></span>  
  
6.  <span data-ttu-id="93db2-130">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="93db2-130">Click **Next.**</span></span>  
  
7.  <span data-ttu-id="93db2-131">En el campo Nombre, asegúrese de que aparece **Adventure Works DW 2012** y, después, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="93db2-131">In the Name field, make sure **Adventure Works DW 2012** displays, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="93db2-132">La vista del origen de datos **Adventure Works DW 2012** aparece en la carpeta **Vistas del origen de datos** del Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="93db2-132">The **Adventure Works DW 2012** data source view appears in the **Data Source Views** folder in Solution Explorer.</span></span> <span data-ttu-id="93db2-133">El contenido de la vista del origen de datos también se muestra en el Diseñador de vistas del origen de datos de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93db2-133">The content of the data source view is also displayed in Data Source View Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="93db2-134">Este diseñador contiene los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="93db2-134">This designer contains the following elements:</span></span>  
  
    -   <span data-ttu-id="93db2-135">El panel **Diagrama** , en el que las tablas y sus relaciones se representan gráficamente.</span><span class="sxs-lookup"><span data-stu-id="93db2-135">A **Diagram** pane in which the tables and their relationships are represented graphically.</span></span>  
  
    -   <span data-ttu-id="93db2-136">El panel **Tablas** , en el que las tablas y los elementos de esquema se muestran en una vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="93db2-136">A **Tables** pane in which the tables and their schema elements are displayed in a tree view.</span></span>  
  
    -   <span data-ttu-id="93db2-137">El panel **Organizador de diagramas** , en el que puede crear subdiagramas de modo que pueda ver los subconjuntos de la vista del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93db2-137">A **Diagram Organizer** pane in which you can create subdiagrams so that you can view subsets of the data source view.</span></span>  
  
    -   <span data-ttu-id="93db2-138">Una barra de herramientas específica del Diseñador de vistas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93db2-138">A toolbar that is specific to Data Source View Designer.</span></span>  
  
8.  <span data-ttu-id="93db2-139">Para maximizar el entorno de desarrollo de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] , haga clic en el botón **Maximizar** .</span><span class="sxs-lookup"><span data-stu-id="93db2-139">To maximize the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] development environment, click the **Maximize** button.</span></span>  
  
9. <span data-ttu-id="93db2-140">Para ver las tablas del panel **Diagrama** al 50 por ciento, haga clic en el icono **Zoom** de la barra de herramientas del Diseñador de vistas del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93db2-140">To view the tables in the **Diagram** pane at 50 percent, click the **Zoom** icon on the Data Source View Designer toolbar.</span></span> <span data-ttu-id="93db2-141">De este modo se ocultarán los detalles de columna de cada tabla.</span><span class="sxs-lookup"><span data-stu-id="93db2-141">This will hide the column details of each table.</span></span>  
  
10. <span data-ttu-id="93db2-142">Para ocultar el Explorador de soluciones, haga clic en el botón **Ocultar automáticamente** , que es el icono de marcador de la barra de título.</span><span class="sxs-lookup"><span data-stu-id="93db2-142">To hide Solution Explorer, click the **Auto Hide** button, which is the pushpin icon on the title bar.</span></span> <span data-ttu-id="93db2-143">Para ver el Explorador de soluciones de nuevo, sitúe el puntero sobre la pestaña del Explorador de soluciones situada a la derecha del entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="93db2-143">To view Solution Explorer again, position your pointer over the Solution Explorer tab along the right side of the development environment.</span></span> <span data-ttu-id="93db2-144">Para mostrar el Explorador de soluciones, haga clic de nuevo en el botón **Ocultar automáticamente** .</span><span class="sxs-lookup"><span data-stu-id="93db2-144">To unhide Solution Explorer, click the **Auto Hide** button again.</span></span>  
  
11. <span data-ttu-id="93db2-145">Si las ventanas no se ocultan de manera predeterminada, haga clic en **Ocultar automáticamente** en la barra de título de las ventanas Propiedades y Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="93db2-145">If the windows are not hidden by default, click **Auto Hide** on the title bar of the Properties and Solution Explorer windows.</span></span>  
  
     <span data-ttu-id="93db2-146">Ahora puede ver las tablas y sus relaciones en el panel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="93db2-146">You can now view all the tables and their relationships in the **Diagram** pane.</span></span> <span data-ttu-id="93db2-147">Observe que hay tres relaciones entre la tabla FactInternetSales y la tabla DimDate.</span><span class="sxs-lookup"><span data-stu-id="93db2-147">Notice that there are three relationships between the FactInternetSales table and the DimDate table.</span></span> <span data-ttu-id="93db2-148">Cada venta tiene tres fechas asociadas: de pedido, de vencimiento y de envío.</span><span class="sxs-lookup"><span data-stu-id="93db2-148">Each sale has three dates associated with the sale: an order date, a due date, and a ship date.</span></span> <span data-ttu-id="93db2-149">Para ver los detalles de cualquier relación, haga doble clic en la flecha de relación del panel **Diagrama** .</span><span class="sxs-lookup"><span data-stu-id="93db2-149">To view the details of any relationship, double-click the relationship arrow in the **Diagram** pane.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="93db2-150">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="93db2-150">Next Task in Lesson</span></span>  
 [<span data-ttu-id="93db2-151">Modificar los nombres de tabla predeterminados</span><span class="sxs-lookup"><span data-stu-id="93db2-151">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
  
## <a name="see-also"></a><span data-ttu-id="93db2-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93db2-152">See Also</span></span>  
 [<span data-ttu-id="93db2-153">Vistas del origen de datos en modelos multidimensionales</span><span class="sxs-lookup"><span data-stu-id="93db2-153">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
