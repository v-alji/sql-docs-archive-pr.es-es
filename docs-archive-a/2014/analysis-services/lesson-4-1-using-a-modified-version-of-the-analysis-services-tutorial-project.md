---
title: Usar una versión modificada del proyecto Analysis Services tutorial | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 685aa217-de1b-4df2-bf22-095228c40775
author: minewiskan
ms.author: owend
ms.openlocfilehash: b833a05a567f37443cf89f7356a0855e0827ea73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674419"
---
# <a name="using-a-modified-version-of-the-analysis-services-tutorial-project"></a><span data-ttu-id="20711-102">Usar una versión modificada del proyecto Tutorial de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="20711-102">Using a Modified Version of the Analysis Services Tutorial Project</span></span>
  <span data-ttu-id="20711-103">Las lecciones restantes de este tutorial se basan en una versión mejorada del proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que completó en las tres primeras lecciones.</span><span class="sxs-lookup"><span data-stu-id="20711-103">The remaining lessons in this tutorial are based on an enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons.</span></span> <span data-ttu-id="20711-104">Se han agregado tablas y cálculos con nombre adicionales a la vista del origen de datos **Adventure Works DW 2012** , se han agregado más dimensiones al proyecto y estas nuevas dimensiones se han agregado al cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20711-104">Additional tables and named calculations have been added to the **Adventure Works DW 2012** data source view, additional dimensions have been added to the project, and these new dimensions have been added to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span> <span data-ttu-id="20711-105">Además, se ha agregado un segundo grupo de medidas, que contiene medidas de una segunda tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="20711-105">In addition, a second measure group has been added, which contains measures from a second fact table.</span></span> <span data-ttu-id="20711-106">Este proyecto mejorado le permitirá continuar aprendiendo a agregar funciones adicionales a la aplicación de Business Intelligence sin necesidad de tener que repetir las técnicas ya aprendidas.</span><span class="sxs-lookup"><span data-stu-id="20711-106">This enhanced project will enable you to continue learning how to add functionality to your business intelligence application without having to repeat the skills you have already learned.</span></span>  
  
 <span data-ttu-id="20711-107">Para poder continuar con el tutorial, debe descargar, extraer, cargar y procesar la versión mejorada del proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20711-107">Before you can continue with the tutorial, you must download, extract, load and process the enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span>  <span data-ttu-id="20711-108">Siga las instrucciones de esta lección para asegurarse de que ha realizado todos los pasos.</span><span class="sxs-lookup"><span data-stu-id="20711-108">Use the instructions in this lesson to ensure you have performed all the steps.</span></span>  
  
## <a name="downloading-and-extracting-the-project-file"></a><span data-ttu-id="20711-109">Descargar y extraer el archivo de proyecto</span><span class="sxs-lookup"><span data-stu-id="20711-109">Downloading and Extracting the Project File</span></span>  
  
1.  <span data-ttu-id="20711-110">[Haga clic aquí](https://go.microsoft.com/fwlink/?LinkID=221866) para ir a la página de descarga que proporciona los proyectos de ejemplo relacionados con este tutorial.</span><span class="sxs-lookup"><span data-stu-id="20711-110">[Click here](https://go.microsoft.com/fwlink/?LinkID=221866) to go to the download page that provides the sample projects that go with this tutorial.</span></span> <span data-ttu-id="20711-111">Los proyectos del tutorial se incluyen en la descarga de **Tutorial de Analysis Services SQL Server 2012** .</span><span class="sxs-lookup"><span data-stu-id="20711-111">The tutorial projects are included in the **Analysis Services Tutorial SQL Server 2012** download.</span></span>  
  
2.  <span data-ttu-id="20711-112">Haga clic en **Tutorial de Analysis Services de SQL Server 2012** para descargar el paquete que contiene los proyectos para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="20711-112">Click **Analysis Services Tutorial SQL Server 2012** to download the package that contains the projects for this tutorial.</span></span>  
  
     <span data-ttu-id="20711-113">De forma predeterminada, se guarda un archivo .zip en la carpeta Descargas.</span><span class="sxs-lookup"><span data-stu-id="20711-113">By default, a .zip file is saved to the Downloads folder.</span></span> <span data-ttu-id="20711-114">Debe mover el archivo .zip a una ubicación que tenga una ruta de acceso más corta (por ejemplo, cree una carpeta C:\Tutoriales para almacenar los archivos).</span><span class="sxs-lookup"><span data-stu-id="20711-114">You must move the .zip file to a location that has a shorter path (for example, create a C:\Tutorials folder to store the files).</span></span>  <span data-ttu-id="20711-115">Después puede extraer los archivos contenidos en el archivo .zip.</span><span class="sxs-lookup"><span data-stu-id="20711-115">You can then extract the files contained in the .zip file.</span></span> <span data-ttu-id="20711-116">Si intentar descomprimir los archivos desde la carpeta Descargas, que tiene una ruta de acceso más larga, solo obtendrá la lección 1.</span><span class="sxs-lookup"><span data-stu-id="20711-116">If you attempt to unzip the files from the Downloads folder, which has a longer path, you will only get Lesson 1.</span></span>  
  
3.  <span data-ttu-id="20711-117">Cree una subcarpeta en la unidad raíz, o cerca de ella, por ejemplo C:\Tutorial.</span><span class="sxs-lookup"><span data-stu-id="20711-117">Create a subfolder at or near the root drive, for example, C:\Tutorial.</span></span>  
  
4.  <span data-ttu-id="20711-118">Mueva el archivo **Analysis Services Tutorial SQL Server 2012.zip** a la subcarpeta.</span><span class="sxs-lookup"><span data-stu-id="20711-118">Move the **Analysis Services Tutorial SQL Server 2012.zip** file to the subfolder.</span></span>  
  
5.  <span data-ttu-id="20711-119">Haga clic con el botón derecho en el archivo y seleccione **Extraer todo**.</span><span class="sxs-lookup"><span data-stu-id="20711-119">Right-click the file and select **Extract All**.</span></span>  
  
6.  <span data-ttu-id="20711-120">Vaya a la carpeta **Lesson 4 Start** para buscar el archivo **Analysis Services Tutorial.sln** .</span><span class="sxs-lookup"><span data-stu-id="20711-120">Browse to the **Lesson 4 Start** folder to find the **Analysis Services Tutorial.sln** file.</span></span>  
  
## <a name="loading-and-processing-the-enhanced-project"></a><span data-ttu-id="20711-121">Cargar y procesar el proyecto mejorado</span><span class="sxs-lookup"><span data-stu-id="20711-121">Loading and Processing the Enhanced Project</span></span>  
  
1.  <span data-ttu-id="20711-122">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] , en el menú **archivo** , haga clic en **cerrar solución** para cerrar los archivos que no va a usar.</span><span class="sxs-lookup"><span data-stu-id="20711-122">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **File** menu, click **Close Solution** to close files you won't be using.</span></span>  
  
2.  <span data-ttu-id="20711-123">En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="20711-123">On the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="20711-124">Vaya a la ubicación donde extrajo los archivos del proyecto de tutorial.</span><span class="sxs-lookup"><span data-stu-id="20711-124">Browse to the location where you extracted the tutorial project files.</span></span>  
  
     <span data-ttu-id="20711-125">Busque la carpeta denominada **Lesson 4 Start**y haga doble clic en Analysis Services Tutorial.sln.</span><span class="sxs-lookup"><span data-stu-id="20711-125">Find the folder named **Lesson 4 Start**, and then double-click Analysis Services Tutorial.sln.</span></span>  
  
4.  <span data-ttu-id="20711-126">Implemente la versión mejorada del proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en la instancia local de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], o en otra instancia, y compruebe que el proceso finaliza correctamente.</span><span class="sxs-lookup"><span data-stu-id="20711-126">Deploy the enhanced version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project to the local instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], or to another instance, and verify that processing completes successfully.</span></span>  
  
## <a name="understanding-the-enhancements-to-the-project"></a><span data-ttu-id="20711-127">Comprender las mejoras realizadas en el proyecto</span><span class="sxs-lookup"><span data-stu-id="20711-127">Understanding the Enhancements to the Project</span></span>  
 <span data-ttu-id="20711-128">La versión mejorada del proyecto es distinta de la versión del proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] que completó en las tres primeras lecciones.</span><span class="sxs-lookup"><span data-stu-id="20711-128">The enhanced version of the project is different from the version of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project that you completed in the first three lessons.</span></span> <span data-ttu-id="20711-129">Las diferencias se describen en las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="20711-129">The differences are described in the following sections.</span></span> <span data-ttu-id="20711-130">Revise esta información antes de continuar con las lecciones restantes del tutorial.</span><span class="sxs-lookup"><span data-stu-id="20711-130">Review this information before continuing with the remaining lessons in the tutorial.</span></span>  
  
### <a name="data-source-view"></a><span data-ttu-id="20711-131">Vista del origen de datos</span><span class="sxs-lookup"><span data-stu-id="20711-131">Data Source View</span></span>  
 <span data-ttu-id="20711-132">La vista del origen de datos del proyecto mejorado contiene una tabla de hechos adicional y cuatro tablas de dimensiones adicionales de la base de datos [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20711-132">The data source view in the enhanced project contains one additional fact table and four additional dimension tables from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="20711-133">Observe que, con diez tablas en la vista del origen de datos, el diagrama \<All Tables> empieza a estar demasiado lleno.</span><span class="sxs-lookup"><span data-stu-id="20711-133">Notice that with ten tables in the data source view, the \<All Tables> diagram is becoming crowded.</span></span> <span data-ttu-id="20711-134">Esto dificulta la comprensión de las relaciones entre las tablas y la localización de tablas específicas.</span><span class="sxs-lookup"><span data-stu-id="20711-134">This makes it difficult to easily understand the relationships between the tables and to locate specific tables.</span></span> <span data-ttu-id="20711-135">Para resolver este problema, las tablas están organizadas en dos diagramas lógicos, el diagrama **Internet Sales** y el diagrama **Reseller Sales** .</span><span class="sxs-lookup"><span data-stu-id="20711-135">To solve this problem, the tables are organized into two logical diagrams, the **Internet Sales** diagram and the **Reseller Sales** diagram.</span></span> <span data-ttu-id="20711-136">Estos diagramas están organizados cada uno en una única tabla de hechos.</span><span class="sxs-lookup"><span data-stu-id="20711-136">These diagrams are each organized around a single fact table.</span></span> <span data-ttu-id="20711-137">Crear diagramas lógicos permite ver y utilizar un subconjunto específico de tablas de la vista del origen de datos en lugar de ver siempre todas las tablas y sus relaciones en un único diagrama.</span><span class="sxs-lookup"><span data-stu-id="20711-137">Creating logical diagrams lets you view and work with a specific subset of the tables in a data source view instead of always viewing all the tables and their relationships in a single diagram.</span></span>  
  
#### <a name="internet-sales-diagram"></a><span data-ttu-id="20711-138">Diagrama Internet Sales</span><span class="sxs-lookup"><span data-stu-id="20711-138">Internet Sales Diagram</span></span>  
 <span data-ttu-id="20711-139">El diagrama **Internet Sales** contiene las tablas que están relacionadas con la venta directa de productos de [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] a los clientes a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="20711-139">The **Internet Sales** diagram contains the tables that are related to the sale of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] products directly to customers through the Internet.</span></span> <span data-ttu-id="20711-140">Las tablas del diagrama son las cuatro tablas de dimensiones y la tabla de hechos que agregó a la vista del origen de datos **Adventure Works DW 2012** en la Lección 1.</span><span class="sxs-lookup"><span data-stu-id="20711-140">The tables in the diagram are the four dimension tables and one fact table that you added to the **Adventure Works DW 2012** data source view in Lesson 1.</span></span> <span data-ttu-id="20711-141">Estas tablas son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="20711-141">These tables are as follows:</span></span>  
  
-   <span data-ttu-id="20711-142">**Geografía**</span><span class="sxs-lookup"><span data-stu-id="20711-142">**Geography**</span></span>  
  
-   <span data-ttu-id="20711-143">**Customer**</span><span class="sxs-lookup"><span data-stu-id="20711-143">**Customer**</span></span>  
  
-   <span data-ttu-id="20711-144">**Date**</span><span class="sxs-lookup"><span data-stu-id="20711-144">**Date**</span></span>  
  
-   <span data-ttu-id="20711-145">**Producto**</span><span class="sxs-lookup"><span data-stu-id="20711-145">**Product**</span></span>  
  
-   <span data-ttu-id="20711-146">**InternetSales**</span><span class="sxs-lookup"><span data-stu-id="20711-146">**InternetSales**</span></span>  
  
#### <a name="reseller-sales-diagram"></a><span data-ttu-id="20711-147">Diagrama Reseller Sales</span><span class="sxs-lookup"><span data-stu-id="20711-147">Reseller Sales Diagram</span></span>  
 <span data-ttu-id="20711-148">El diagrama **Reseller Sales** contiene las tablas relacionadas con la venta de productos de [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] realizadas por los distribuidores.</span><span class="sxs-lookup"><span data-stu-id="20711-148">The **Reseller Sales** diagram contains the tables that are related to the sale of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] products by resellers.</span></span> <span data-ttu-id="20711-149">Este diagrama contiene las siete tablas de dimensiones siguientes y una tabla de hechos de la base de datos [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="20711-149">This diagram contains the following seven dimension tables and one fact table from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] database:</span></span>  
  
-   <span data-ttu-id="20711-150">**Reseller**</span><span class="sxs-lookup"><span data-stu-id="20711-150">**Reseller**</span></span>  
  
-   <span data-ttu-id="20711-151">**Promoción**</span><span class="sxs-lookup"><span data-stu-id="20711-151">**Promotion**</span></span>  
  
-   <span data-ttu-id="20711-152">**SalesTerritory**</span><span class="sxs-lookup"><span data-stu-id="20711-152">**SalesTerritory**</span></span>  
  
-   <span data-ttu-id="20711-153">**Geografía**</span><span class="sxs-lookup"><span data-stu-id="20711-153">**Geography**</span></span>  
  
-   <span data-ttu-id="20711-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="20711-154">**Date**</span></span>  
  
-   <span data-ttu-id="20711-155">**Producto**</span><span class="sxs-lookup"><span data-stu-id="20711-155">**Product**</span></span>  
  
-   <span data-ttu-id="20711-156">**Employee**</span><span class="sxs-lookup"><span data-stu-id="20711-156">**Employee**</span></span>  
  
-   <span data-ttu-id="20711-157">**ResellerSales**</span><span class="sxs-lookup"><span data-stu-id="20711-157">**ResellerSales**</span></span>  
  
 <span data-ttu-id="20711-158">Como puede observar, las tablas **DimGeography**, **DimDate**y **DimProduct** se usan tanto en el diagrama **Internet Sales** como en el diagrama **Reseller Sales** .</span><span class="sxs-lookup"><span data-stu-id="20711-158">Notice that the **DimGeography**, **DimDate**, and **DimProduct** tables are used in both the **Internet Sales** diagram and the **Reseller Sales** diagram.</span></span> <span data-ttu-id="20711-159">Las tablas de dimensiones pueden vincularse a varias tablas de hechos.</span><span class="sxs-lookup"><span data-stu-id="20711-159">Dimension tables can be linked to multiple fact tables.</span></span>  
  
### <a name="database-and-cube-dimensions"></a><span data-ttu-id="20711-160">Dimensiones de cubo y base de datos</span><span class="sxs-lookup"><span data-stu-id="20711-160">Database and Cube Dimensions</span></span>  
 <span data-ttu-id="20711-161">El proyecto Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] contiene cinco dimensiones de base de datos nuevas, y el cubo Tutorial de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] contiene las mismas cinco dimensiones que las dimensiones del cubo.</span><span class="sxs-lookup"><span data-stu-id="20711-161">The [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project contains five new database dimensions, and the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube contains these same five dimensions as cube dimensions.</span></span> <span data-ttu-id="20711-162">Estas dimensiones se han definido de modo que contengan jerarquías de usuario y atributos que se modificaron mediante cálculos con nombre, claves de miembro de composición y carpetas para mostrar.</span><span class="sxs-lookup"><span data-stu-id="20711-162">These dimensions have been defined to have user hierarchies and attributes that were modified by using named calculations, composition member keys, and display folders.</span></span> <span data-ttu-id="20711-163">Las nuevas dimensiones se describen en la siguiente lista.</span><span class="sxs-lookup"><span data-stu-id="20711-163">The new dimensions are described in the following list.</span></span>  
  
 <span data-ttu-id="20711-164">Dimensión Reseller</span><span class="sxs-lookup"><span data-stu-id="20711-164">Reseller Dimension</span></span>  
 <span data-ttu-id="20711-165">La dimensión Reseller se basa en la tabla **Reseller** de la vista del origen de datos **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="20711-165">The Reseller dimension is based on the **Reseller** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="20711-166">Dimensión Promotion</span><span class="sxs-lookup"><span data-stu-id="20711-166">Promotion Dimension</span></span>  
 <span data-ttu-id="20711-167">La dimensión Promotion se basa en la tabla **Promotion** de la vista del origen de datos **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="20711-167">The Promotion dimension is based on the **Promotion** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="20711-168">Dimensión Sales Territory</span><span class="sxs-lookup"><span data-stu-id="20711-168">Sales Territory Dimension</span></span>  
 <span data-ttu-id="20711-169">La dimensión Sales Territory se basa en la tabla **SalesTerritory** de la vista del origen de datos **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="20711-169">The Sales Territory dimension is based on the **SalesTerritory** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="20711-170">Dimensión Employee</span><span class="sxs-lookup"><span data-stu-id="20711-170">Employee Dimension</span></span>  
 <span data-ttu-id="20711-171">La dimensión Employee se basa en la tabla **Employee** de la vista del origen de datos **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="20711-171">The Employee dimension is based on the **Employee** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
 <span data-ttu-id="20711-172">Dimensión Geography</span><span class="sxs-lookup"><span data-stu-id="20711-172">Geography Dimension</span></span>  
 <span data-ttu-id="20711-173">La dimensión Geography se basa en la tabla **Geography** de la vista del origen de datos **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="20711-173">The Geography dimension is based on the **Geography** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
#### <a name="analysis-services-cube"></a><span data-ttu-id="20711-174">Cubo Analysis Services</span><span class="sxs-lookup"><span data-stu-id="20711-174">Analysis Services Cube</span></span>  
 <span data-ttu-id="20711-175">El cubo **Tutorial de Analysis Services** contiene ahora dos grupos de medida: el grupo de medida original basado en la tabla **InternetSales** y un segundo grupo de medida basado en la tabla **ResellerSales** de la vista del origen de datos **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="20711-175">The **Analysis Services Tutorial** cube now contains two measure groups, the original measure group based on the **InternetSales** table and a second measure group based on the **ResellerSales** table in the **Adventure Works DW 2012** data source view.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="20711-176">Siguiente tarea de la lección</span><span class="sxs-lookup"><span data-stu-id="20711-176">Next Task in Lesson</span></span>  
 [<span data-ttu-id="20711-177">Definir propiedades de atributo primario en una jerarquía de elementos primarios y secundarios</span><span class="sxs-lookup"><span data-stu-id="20711-177">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>](lesson-4-2-defining-parent-attribute-properties-in-a-parent-child-hierarchy.md) 
  
## <a name="see-also"></a><span data-ttu-id="20711-178">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20711-178">See Also</span></span>  
 [<span data-ttu-id="20711-179">Implementar un proyecto de Analysis Services</span><span class="sxs-lookup"><span data-stu-id="20711-179">Deploying an Analysis Services Project</span></span>](lesson-2-5-deploying-an-analysis-services-project.md)  
  
  
